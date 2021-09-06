# 12 Factors

**_Ideia: reunir vários fatores que auxiliam na padronização de código, implantação/deploy e escalabilidade_**

## 1. Base de código

Garante rastreabilidade de código

Sistema distribuído - É possível dividir o Codebase e aplicar 12 fatores para cada repositório individual.

"Existe apenas uma base de código por aplicação, mas existirão vários deploys da mesma. Um deploy (ou implantação) é uma instância executando a aplicação. Isto é tipicamente um local de produção, e um ou mais locais de testes. Adicionalmente, todo desenvolvedor tem uma cópia da aplicação rodando em seu ambiente local de desenvolvimento, cada um desses pode ser qualificado como um deploy."

Todos ambientes compartilham da mesma base de código, mas tem versões diferentes implantadas da mesma.

## 2. Dependências

Declare e isole explicitamente as dependências. A maioria das linguagens de programação oferecen um sistema de pacotes para distribuição de bilbiotecas de apoio.

Pode ser instalada em todo sistema (site packages) ou local no projeto (vendoring ou building)

**Sempre instalar as dependências no projeto e não global**

## 3. Configurações

A configuração de uma aplicação é tudo o que é provável variar entre deploys (homologação, produção, ambientes de desenvolvimento, etc)

**Violação dos 12 Fatores: Armazenar as configurações no código como constantes. Configuração varia substancialmente entre deploys, código não.**

Prova de fogo: A aplicação pode ter código aberto sem comprometer credenciais?

## 4. Serviços de apoio

Tratar serviços de apoio ( serviço externo da aplicação ) como recurso anexado, sendo possível substituir este recurso em tempo de deploy sem a necessidade de altera o código

"O código para um app doze-fatores não faz distinção entre serviços locais e de terceiros. Para o app, ambos são recursos anexados, acessíveis via uma URL ou outro localizador/credenciais na config. Um deploy do app doze-fatores deve ser capaz de trocar um banco de dados MySQL por um gerenciado por terceiros (tais como Amazon RDS) sem realizar quaisquer mudanças no código do app. Da mesma forma, um servidor local SMTP poderia ser trocado por um serviço de terceiros (tais como Postmark) sem as mudanças em código. Em ambos os casos, apenas o identificador de recurso precisa mudar."

## 5. Construa, lance, execute

Base de código transformada em um deploy em 3 estágios:  
Construção - Converte repositório em um pacote executável (construção). Este estágio obtém e fornece dependências e compila binários e ativos.  
Lançamento - Pega a construção e combina com a configuração do ambiente de deploy. Combina construção com configurações  
Execução - Roda o app no ambiente de execução

"O app doze-fatores usa separação estrita entre os estágios de construção, lançamento e execução. Por exemplo, é impossível alterar código em tempo de execução, já que não há meios de se propagar tais mudanças de volta ao estágio de construção."

Qualquer mudança efetuada no código deve gerar um novo lançamento. Lançamentos não podem ser acrescentados

## 6. Processos

Processos doze-fatores são stateless(não armazenam estado) e share-nothing. Quaisquer dados que precise persistir deve ser armazenado em um serviço de apoio stateful(que armazena o seu estado), tipicamente uma base de dados.

A aplicação doze-fatores nunca assume que qualquer coisa cacheada na memória ou no disco, estará disponível em uma futura solicitação ou job – com muitos processos de cada tipo rodando, as chances são altas de que uma futura solicitação será servida por um processo diferente.

Mesmo quando rodando em apenas um processo, um restart pode limpar a memória do estado local

Sistemas web que utilizam sessões persistentes (fazem cache dos dados da sessão do usuário na memória do processo da aplicação) é uma violação do 12 fatores. Dados do estado da sessão precisam ficar em datastore como Redis

## 7. Víncilo de portas

O app web exporta o HTTP como um serviço através da vinculação a uma porta, e escuta as requisições que chegam na mesma.

Num ambiente de desenvolvimento local, o desenvolvedor visita a URL de um serviço como http://localhost:5000/ para acessar o serviço exportado pelo seu app. Num deploy, uma camada de roteamento manipula as requisições de rotas vindas de um hostname público para os processos web atrelados às portas.

Ambiente de execução vincula uma porta para servir as requisições.

Abordagem de vincular portas: um app pode se tornar serviço de apoio para outro app, provendo a URL de apoio como identificador de recurso na configuração do app que irá chamar.

## 8. Concorrência

Arquitetar aplicação para lidar com diversas cargas de trabalho, exemplo: solicitação HTTP manipulada com um processo web e tarefas background de longa duração podem ser manipuladas por um processo trabalhador.

Aumentar escala vertical de modo que aplicação seja capaz de abranger processos em execução em várias máquinas físicas. Melhora escalabilidade.

## 9. Descartabilidade

Processos de um app 12 fatores são descartáveis, podem ser iniciados ou parados a qualquer momento.  
Facilita: Escalonamento elástico, rápido deploy de código ou mudanças de configuração e robustex de deploys de produção.

**Minimizar tempo de inicialização**

Desligar graciosamente  
Em processos web: Para de escutar a porta de serviço (recusando novas requisições) permitindo qualquer requisição em andamento terminar, e então desligando.
Processos de trabalho (worker): Desligamento gracioso é alcançado retornando a tarefa atual para a fila de trabalho.

Processos devem ser robustos contra morte súbita (retornar tarefas à fila quando desconectados). App 12 fatores é arquitetado para lidar com términos não esperados.

## 10. Paridade entre desenvolvimento e produção

Mantenha desenvolvimento, homologação e produção o mais similares possível

3 Lacunas:  
Tempo: desenvolvedor pode demorar para desenvolver o código até ir para produção  
Pessoal: desenvolvedor escreve o código e engenheiros fazer deploy dele  
Ferramentas: ferramentas utilizadas para desenvolver diferentes das ferramentas de produção

App 12 fatores é projetado para ter implantação contínua deixando lacunas entre desenvolvimento e produção pequenas.

Diminua lacuna de tempo: desenvolvedor escreve código e pode ter deploy em horas depois  
Diminua lacuna pessoal: desenvolvedores que escrevem códigos estão envolvidos em realizar deploy e acompanhar comportamento em produção  
Diminua lacuna de ferramentas: mantenha desenvolvimento e produção o mais similares possível

## 11. Logs

Trate logs como fluxo de eventos  
Visibilidade no comportamento de um app em execução

Ordenados por tempo, formato texto sendo um evento por linha  
Sempre terá logs enquanto o aplicativo tiver operante

Um app 12 fatores nunca se preocupa com o roteamento ou armazenagem do fluxo de saída. Os logs devem ser escritos no log do terminar para observação do comportamento do app.

Deploys de homologação ou produção, cada fluxo dos processos serão capturados pelo ambiente de execução e direcionados para um ou mais destinos finais para visualização e arquivamento de longo prazo. Destinos são geridos pelo ambiente de execução.

## 12. Processos administrativos

Rode tarefas de gestão/administração ou manutenção em processos pontuais (como: migrations).  
Estes processos devem ser executados em um ambiente idêntico. Rodam uma versão usando a mesma base de código e configuração como qualquer processo executado com esta versão.

**Referência:**  
WIGGINS, Adam. The Twelve-Factor App. 12factor, 2017. Disponível em: <https://12factor.net/>. Acesso em: 06 de set. de 2021.
