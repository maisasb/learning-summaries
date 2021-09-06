# O codificador limpo

## Assumindo responsabilidades

Fazer coisas correndo sem passar por todas as etapas do processo de software (definição, requisitos, prototipação, desenvolvimento, testes) para atender prazos mal estabelecidos é irresponsável, pois assim não é possível saber se a entrega executada está realmente pronta e se vai ou não causar problemas aos clientes.

Para sermos profissionais não podemos criar bugs, o software precisa estar funcionando, ou seja, sem bugs. Como um software é algo muito complexo para ser garantido sem bugs, é indispensável que o desenvolvedor seja responsável pelas suas imperfeições (bugs).

O desenvolvedor precisa assumir o erro e corrigí-lo, com a experiência a taxa de erros é provável de diminuir.

Antes de enviar um código para um Analista de Qualidade é necessário ter certeza que este está "perfeito", não é profissional enviar um código que não foi checado previamente pelo desenvolvedor. Mesmo garantindo a qualidade de software um QA pode ainda encontrar bugs, é importante se desculpar e analisar como conseguiram escapar para que não aconteça de novo.

Apenas com testes é possível saber se um código está realmente funcionando. Caso perceba que está levando muito tempo para testar, automatize os testes.

O software precisa ser flexível e sustentável, fácil e rápido de ser alterado. O código é uma estrutura viva, sempre é necessário fazer mudanças para refinar sua estrutura. Um software estático é perigoso, se não torná-lo flexível, quando precisar fazer uma mudança irá encontrá-lo rígido.

O Profissional precisa ter um aprendizado contínuo, dedicar algumas horas do dia para aprender coisas sobre a profissão e aumentar a fatia do conhecimento adquirido. Praticar conhecimentos obtidos afim de potencializar habilidades.

É necessário conhecer o domínio sobre o qual está programando, entender o assunto, seja contabilidade, agência de viagens, experiência do consumidor. Codificar em cima de especulação é antiprofissional, pois não tem como saber se faz sentido para o negócio.

## Dizendo não

Um profissional tem que saber o momento certo de dizer não, quando uma demanda não será possível de ser entregue em um prazo estipulado, por exemplo.

Meta ideal da equipe é quando gerente e desenvolvedores partilham da decisão sobre prazos e entregas. Para isso acontecer, tem que haver discussão para atingir a meta comum aceitável.

A melhor forma de ter uma relação saudável com a equipe e profissional é dizendo a verdade, se um prazo não poderá ser cumprido por qualquer motivo que seja, diga a verdade e coloque um novo prazo, dizer apenas "Vou tentar cumprir o prazo mesmo assim" é colaborar para o fracasso.  
Dizer que irá tentar mesmo não sendo possível é admitir que a equipe não estava se esforçando o bastante ou irão fazer um esforço adicional para entregar no prazo estipulado.
Dizer que irá tentar precisa de um novo plano, falar que vai tentar sem ter um plano em mente é saber que a meta não será atingida.

## Dizendo sim

Ao se comprometer com algo, seja tarefa ou serviço, é necessário ser honesto, ter certeza que será possível fazer aquilo, no prazo estipulado ou a função necessária. Dizer que vai fazer só por fazer não é profissional.
Comprometer com algo e não cumprir, não é bom quando alguém confia nas promessas realizadas.

Frases como "Vamos fazer isso...", "precisamos fazer isso", "esperamos fazer isso até dia ..." são subjetivas e não assumem personalidade, como se os problemas estivessem fora das nossas mãos. Agora, "Eu vou fazer", está estabelecendo um critério de responsabilidade e compromisso.

Existem 3 situações que atrapalham o comprometimento:

1. Quando depende de outra pessoa: só se pode comprometer com coisas que você tem pleno controle. Caso parte do processo esteja dependendo de outra pessoa, é possível comprometer-se com funções específicas que tragam mais próximo do objetivo.
2. Não saber se pode ser feito: descobrir se algo pode ser feito é uma das ações que levam ao comprometimento, e ações específicas podem trazer mais perto da meta.
3. Simplesmente, não conseguirei: é possível que o comprometimento com uma tarefa seja difícil ou impossível de alcançar, neste caso é necessário mudar as expectativas o mais rápido possível.

## Codificando

A chave para o domínio é a confiança e o senso de erro, ter senso de erro é sentir que algo não esta certo e poder recuperar rapidamente.

1. O código precisa funcionar, é preciso entender o problema que precisa ser resolvido e resolvê-lo. O código precisa ser consistente com a linguagem, plataforma, arquitetura e peculiaridades do sistema.
2. O código precisa resolver o problema proposto pelo cliente. É necessário entender o que o cliente precisa e negociar a melhor forma de atender.
3. O código precisa enquadrar no sistema que já existe. Não pode aumentar a rigidez, fragilidade ou opacidade do sistema. As dependências precisam ser bem gerenciadas. O código precisa seguir sólidos princípios de engenharia
4. O código precisa ser inteligível para outros programadores. Não apenas escrever comentários agradáveis, mas deixar que o código transpareça as intenções.

Codificar preocupado - ninguém trabalha bem quando possui algo deixando inquieto e ansioso, quando acontecer isso, passe uma hora tentando resolver o problema ou pelo menos aquietá-lo, para depois voltar para o código

Depuração do código é um grande aliado para identificar onde está ocorrendo algum problema, algumas disciplinas auxiliam no desenvolvimento para que não seja necessário depurar tanto o código, como o TDD.

Programar é estabelecer um ritmo de codificação seguro, sem extrapolar a energia e criatividade, é necessário saber a hora de se afastar, descansar e recuperar. Às vezes afastar do problema pode trazer a solução.

Atrasos acontecem, ao detectá-los é necessário ser transparente consigo, com a equipe e gerência. Atualize os números e seja honesto.

Programar com ajuda de outros programadores é o melhor caminho, pois pensamentos e ideias de outra pessoa podem contribuir para um código mais bem feito e inteligível. Pedir ajuda e oferecer ajuda é sempre necessário. Colaborar é essencial para uma programação eficiente.

## TDD

Desenvolvimento guiado por testes, testar o código que ainda não foi escrito.
Disciplina que potencializa a certeza, coragem, redução de falhas, documentação e o design.

Três leis do TDD

1. Você não pode escrever nenhum código até que tenha escrito antes um teste de unidade que detecte uma falha.
2. Você não pode escrever mais de um teste de unidade do que o suficiente para a falha, e não compilar é não ter efeito
3. Você não pode escrever mais códigos de produção que sejam suficientes para passar pelo atual teste de unidade.

Comece com uma pequena porção de teste de unidade, em poucos segundos você terá que mencionar o nome de alguma classe ou função que ainda não escreveu, fazendo com que o teste de unidade falhe ao compilar. Então, será preciso escrever o código que fará com que o teste compile. Mas você não pode escrever mais do que isso, portanto comece a escrever mais testes de unidade, e o ciclo continua.

Os benefícios do TDD é poder refatorar e corrigir códigos sem ter medo de quebrar algo.
Outro benefício é a documentação, testes de unidade bem feitos descrevem como o sistema deve ser usado. Testes de unidade são a descrição de como utilizar as funções do sistema e para que servem.

O problema de testar códigos é que é preciso isolá-los, costuma ser difícil testar uma função se aquela unção chama outras funções. Para escrever esse teste, você precisa descobrir alguma forma de dissociar a função das demais. Em outras palavras, a necessidade para testar primeiro o força a pensar em um bom design.  
Deixar para escrever testes depois pode ser que seja testado apenas o output e input final e não as funções individuais.

Testes escritos depois do código são defensivos, testes escritos antes são ofensivos. Testes escritos após são feitos por alguém que já sabe como o problema foi resolvido. Não são tao incisivos quanto os que são escritos antes.

## Prática

Todo profissional pratica para poder se tornar melhor, com desenvolvedores não é diferente, para resolver uma situação ou pensar em uma solução ágil é necessário prática.

Coding Dojo - Treinamento de programação com outras pessoas ou sozinho, onde se resolve pequenos problemas computacionais  
Atividades:  
Kata: Prática de problemas já conhecidos  
Wasa: Kata praticado em dupla (uma pessoa escreve o teste e a outra faz funcionar e vice-versa)
Randori: Kata praticado em grupo (cada pessoa escreve um pedaço do código)

## Teste de aceitação

A comunicação dos requisitos é a parte mais complexa em um desenvolvimento de software, muitas vezes o que o cliente pede pode não ser o melhor para ele ou pode não funcionar, e este impasse pode levar a problemas futuros.

Muitas vezes, ao mostrar o requerimento funcionando dá ao empregador novas informações do que ele realmente deseja.

Prever quando um sistema ficará pronto é quase impossível, pois os requerimentos mudam durante o projeto.  
Os requisitos precisam ser o mais claros possível, é necessário remover toda a ambiguidade encontrada para poder desenvolver o programa esperado pelos stakeholders.

Testes de aceitação - escritos por stakeholders e desenvolvedores para definir quando um requisito está pronto. É necessário garantir que todos estejam cientes do que está prestes a ser construído. Elimina a deficiência na comunicação entre stakeholders e desenvolvedores, pois serve de documentação.

A definição de "Acabado" - quando terminou de desenvolver e está testado? está pronto para teste? Apenas terminou de desenvolver?  
Acabado é todo o código foi escrito, todos os testes foram feitos e os stakeholders aceitaram.

Testes de aceitação devem ser automatizados. Ferramentas que auxiliam na construção de testes automatizados : robot, selenium. Uma vez escrito os testes automatizados não será necessário executar testes manuais.  
Testes de aceitação precisam ser escritos antes do recurso ser implementado. O desenvolvedor precisa conectar o teste de aceitação ao sistema e fazer com que eles passem.

Testes de aceitação não são testes de unidades. Testes de unidades são escritos por programadores para programadores, documento que descreve em nível mais baixo como o código deve ser comportar. Testes de aceitação são escritos para o pessoal de negócio, são pedidos formais que especificam como um sistema deve se comportar. Eles podem testar as mesmas coisas mas fazer por caminhos diferentes.

Testes de GUI - tratar o GUI como se fosse uma API ao invés de um conjunto de botões, sliders , menus.
Princípio da responsabilidade única - separar as coisas que mudam por diferentes razões e agrupar as que mudam pelas mesmas razões. Quando escrever testes de aceitação para GUI, aproveita vantagem das abstrações que não mudam com frequência. Exemplo, um clique de botão, testar o clique por meio de um ID único ao invés de sua posição na tela.

Testar GUI é sempre complicado pois ela sempre mudará, o que deixa os testes frágeis. É mais fácil testar a API do que a interface, mas alguns testes são necessários testar apenas a GUI. Quanto mais testes de GUI tiver menor a probabilidade de mantê-los.

Integração contínua - os testes devem ser rodados automaticamente e os resultados enviados para a equipe.

## Estratégias de teste

A meta do desenvolvimento é que a equipe de qualidade de não encontre nada errado com o sistema. Quando acontece de encontrar uma falha a equipe de desenvolvimento precisa tomar ações para que elas não ocorram no futuro.

Equipe de qualidade deve trabalhar como especificadores, criar testes de aceitação automatizados para que se tornem documentos de especificação e requisitos do sistema, e também como caracterizadores, explorando o sistema a fim de identificar comportamentos incorretos.

Testes unitários: cobertura de 90% a 100%, escritos antes de codificar as funções do sistema como forma de especificar aquilo que está sendo desenvolvido.

Testes de componentes: Testes de aceitação que seguem as regras estipuladas da empresa. Testa um componente específico desassociando ele dos outros componentes, imputando a entrada e verificando a saída. Cobrem metade do sistema e são direcionados a situações de caminho feliz.

Testes de integração: Só fazem sentido para sistemas grandes com muitos componentes. Monta um grupo de componentes e testa a comunicação uns com os outros. Estes testes são coreografados, não testam as regras da empresa, testam a composição dos componentes e o funcionamento deles. São executados periodicamente por terem duração mais longa.

Testes de sistema: Teste automatizado do sistema integrado completo, executados com menos frequência dependendo da duração. Cobrem por volta de 10% do sistema, intenção é garantir a construção correta do sistema.

Testes exploratórios manuais: Testes não automatizados, explorar o sistema em busca de comportamentos inesperados. A meta não é cobertura, é garantir que o sistema se comporte bem sob operação humana.

## Geranciamento de tempo

Saber gerenciar o tempo para poder desenvolver na sua melhor capacidade. Algumas situações podem atrapalhar o gerenciamento do tempo como: reuniões, foco, discussões, sono. Por isso temos que ter um planejamento e saber lidar com essas diversas situações.

Reuniões:
Precisam ser importantes e focadas, o custo de uma reunião é muito alto. Reuniões de planejamento de iterações são as mais demoradas, por isso os itens precisam ser previamente discutidos, avaliados e com testes de aceitação esboçados, cada item deve ser brevemente discutido, se demorar demais, é necessário agendar uma nova reunião para discutir aquele item específico.

Quando uma discussão não puder ser resolvida em 5 minutos, ela não pode ser resolvida pela discussão, pois não existe evidências claras dando suporte a ambos os lados. Para isso é necessário obter mais dados.

Foco: Aproveitar quando o foco está ativo e realizar tarefas menos produtiva quando inativo.  
Sono: O sono interfere muito no foco e desenvolvimento, por isso é importante estar com ele em dia.

Técnica pomodoro para melhorar o foco: programar um timer de 25 minutos e durante este tempo nada pode tirar do foco, como uma ligação, uma dúvida, etc. Quando o timer tocar, pare o que estiver fazendo e lide com as interrupções que ocorreram durante o período. Depois faça uma pausa de 5 minutos e programe o timer para mais 25 minutos e comece novamente. A cada 4 momentos de foco, faça uma pausa maior, de 30 minutos. Com esta técnica é possível quantificar o quanto o dia foi produtivo baseado na quantidade de momentos de foco que teve.

Importante ter a mete aberta para soluções alternativas e atividades prioritárias, saber reconhecer quando uma solução não está adequada e ajustar uma nova forma de resolver.

## Estimativa

O que é uma estimativa? A empresa gosta de ver estimativas como comprometimentos e desenvolvedores gostam de vê-las como palpites.  
Se comprometer com algo é preciso cumprir, ao se comprometer com uma meta outras pessoas estarão fazendo planos em cima do comprometimento e o não cumprimento dele pode ser custoso e ruim para reputação. Não se comprometa caso não tenha 100% de certeza de sucesso.  
Estimativa é um palpite, não tem um comprometimento implícito.  
Ao estimar uma atividade devemos distribuir suas probabilidades, pensar na estimativa otimista ou se tudo der errado, quanto tempo irá levar.

PERT - Programa de avaliação e revisão de técnicas - criado para auxiliar a marina norte-americana no projeto do submarino Polaris, o programa oferece um conversor de estimativas em distribuição de probabilidades. Nele, é fornecido 3 números: a estimativa otimista, a estimativa normal (maior chance de sucesso) e a estimativa pessimista. Com esses números é calculado a probabilidade da tarefa ficar pronta.  
Wideband Delphi - um método para calcular estimativa onde a equipe discute até chegar em um acordo de quanto tempo a tarefa pode ser concluída. Mais pessoas incluídas na discussão da estimativa pode ser mais preciso, pois outras pessoas podem ver o que algumas não podem e vice-versa.

Técnicas para estimar:  
Dedos voadores - a equipe se reúne em volta de uma mesa e cada tarefa é discutida sobre suas implicações e implementações e então os participantes levantam dedos simultaneamente (0-5) de acordo com quanto tempo elas pensam que a tarefa demora para ser concluída. Após exibidas as estimativas há uma discussão até que cheguem a uma conclusão.  
Pôquer planejado - cada integrante da equipe recebe uma mão de cartas de 0 a 5, a tarefa é discutida, cada um escolhe uma carta conforme a estimativa que aquela pessoa acha e todos mostram simultaneamente.  
Estimativa de afinidade - as tarefas são escritas em cartões e espalhadas sobre a mesa, os membros da equipe começam a sortear os cartões, tarefas que levam mais tempo são movidas para a direita e menos tempo para a esquerda, todos podem mover os cartões a qualquer momento, mesmo que este cartão já tenha sido movido, qualquer cartão que tenha sido movido mais do que X vezes é deixado de lado para discussão.

Dividir uma tarefa grande em várias tarefas menores é melhor para estimar e dá um pouco mais de precisão.

## Pressão

O desenvolvedor profissional é calmo e decisivo sob pressão. Conforme a pressão cresce ele recorre ao treinamento e disciplinas, sabendo que ambos são a melhor forma para cumprir os prazos e compromissos que estão pressionando.  
A melhor forma de permanecer calmo sob pressão é evitar as situações que a causam. Isso pode não eliminar a pressão completamente, porém pode minimizar e abreviar os períodos em que ela é alta.

Compromissos - importante evitar se comprometer com algo que não se tem certeza se será cumprido. É necessário garantir que os riscos sejam quantificados e apresentados de forma que a empresa possa gerenciá-los. Quando este compromisso não são assumidos pelos desenvolvedores e sim da empresa direto com o cliente, o desenvolvedor tem a obrigação de ajudar a empresa a encontrar o melhor caminho para cumprir os compromissos, mas não tem a obrigação de aceitá-los. Se não for possível encontrar uma maneira de cumprir uma meta comprometida, as pessoas que fizeram o comprometimento terá que arcar com as responsabilidades.

Desenvolvedores profissionais não sucumbem a tentação de criar uma bagunça de modo a ir mais rápido, a melhor forma de cumprir os prazos é ficar limpo, manter o sistema, código e design o mais limpo possível. Mesmo em tempos de crise é necessário manter a disciplina.

A melhor forma de lidar com a pressão é diminuir o stress, dormir bem, diminuir o ritmo e analisar o problema e seguir em direção do resultado em um passo constante e razoável. Comunicar os superiores que está com problemas, seja aberto a sugestões evite criar surpresas. E por fim, peça ajuda.

## Colaboração

A maior parte dos softwares são criados por equipes. Elas são mais eficientes quando membros colaboram profissionalmente. Não é profissional ser um solitário ou excluído em uma equipe.

A primeira responsabilidade do programador é ir de encontro das necessidades do empregador, isso significa, colaborar com gerentes, analistas de negócio, testadores e outros membros da equipe, você precisa entender porque esta escrevendo os códigos e como o negócio se beneficia deles.

Código de propriedade - programadores que constroem um muro em volta de seus códigos e não permitem que outras pessoas possam editá-los.
Propriedade coletiva - código não é de um indivíduo e sim da equipe, qualquer um da equipe pode fazer checagem de um módulo ou efetuar mudanças.  
Trabalhos em duplas - trabalhar em dupla é a forma mais eficiente de resolver um problema, partilhar conhecimento e revisar o código.

## Projetos e equipes

Projetos não se misturam, não é interessante alocar trabalhadores meio período em um projeto e meio período em outro. Isso não é uma equipe, pois uma equipe demora a ser formada, seus membros demoram a ter relacionamentos e aprender a colaborar uns com os outros. Uma equipe bem entrosada pode fazer as coisas acontecerem, seus membros antecipam ações uns dos outros e dão suporte mutualmente.

Uma equipe sólida é composta de diferentes áreas, testadores, programadores, analistas de negócios e gerente de projeto.

Alocar uma equipe sólida a um projeto é mais interessante que formar uma equipe em torno de um projeto, pois equipes sólidas demoram a ser constituídas.

## Ensino, aprendizagem e habilidade

A prática e mentoria é muito importante para a aprendizagem. Designar um sistema de software para um desenvolvedor incapacitado pode acarretar perdas financeiras significativas. Períodos de treinamento com supervisão são importantes para de fato capacitar um novo profissional.  
Mestres - programadores sêniores com mais de 10 anos de experiência, que já trabalhou em diversos sistemas, com várias linguagens, sabem coordenar equipes e são designers e arquitetos de software.  
Operadores - programadores treinados e competentes, aprendem a trabalhar bem e até se tornar líder. Tem conhecimento da tecnologia atual, mas carece da experiência com muitos sistemas. Tem a tendência de conhecerem poucas linguagens e plataformas, mas sempre estão em busca de novos conhecimentos. São supervisionados de perto por sêniores até ganharem autonomia.  
Aprendizes - recém-graduados, eles não têm autonomia e são supervisionados de perto pelos operadores. No começo não recebem nenhuma tarefa, apenas dão assistência aos operadores (programação em par). Operadores são professores, eles asseguram que os aprendizes conheçam princípios e padrões de design, disciplinas e rituais.

O programador artesão - experiente e competente, trabalha rapidamente, sem se apressar. Dá estimativas razoáveis e cumpre seus compromissos. Sabe quando dizer não, mas tenta dizer sim ao máximo.

**Referência:**  
MARTIN, Robert C. O Codificador Limpo: Um código de conduta para programadores profissionais. 1ª Edição. Rio de Janeiro: Alta Books Editora, 2012.
