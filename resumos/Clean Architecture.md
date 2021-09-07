# Clean Architecture

![Clean Archtecture](https://github.com/maisasb/learning-summaries/blob/main/resumos/imagens/CleanArchitecture.jpg)

Vários tipos de arquitetura (Hexagonal, Onion, Screamin, DCI, BCE)  
Objetivo: Separação dos conceitos  
Todas conseguem atingir dividindo o software em layers

Características:

- Sistemas independente de frameworks.
- Sistemas fáceis de testar.
- Sistemas com interfaces independentes (UI pode atualizar sem ter que atualizar o resto do sistema)
- Sistemas com banco de dados independentes
- Sistemas com independência de agentes externos

## A regra de dependência

A teoria da arquitetura limpa é que os circulos externos são mecanismos e os circulos internos políticas.  
A regra da dependência diz o seguinte: A dependência do código deve apontar apenas para dentro, nada dentro dos circulos internos pode saber sobre os circulos externos. Nada declarado em um circulo externo pode ser mencionado em um circulo interno (funções, classes, variáveis)

As camadas mais internas são mais estáveis, raramente modificadas. A regra da dependência garante que as entidades e casos de uso sejam classes que não contenham serviços externos ao sistema.

## Entidades

Encapsula regra de negócio da empresa toda.  
Pode ser um objeto com métodos ou apenas estrutura de dados com funções.  
Podem ser utilizadas por diferentes partes da aplicação  
Encapsula um alto level de regra de negócio  
Muito pouco provável de mudar se algo externo alterar.

## Use Cases

Contém regras de negócio específicas da aplicação. Encapsula e implementa todos casos de uso do sistema.  
Orquestra o fluxo de dados entre entidades  
Alterações neste layer não pode afetar entidades. E este layer não pode ser afetado por externos como banco de dados, UI ou frameworks.

Mudanças na operação afetam este layer caso regras de negócio específicas mudem.

## Interface Adapters

O software deste layer é um conjunto de adaptadores que convertem os dados utilizados nos casos de uso e entidades para o formato mais conveniente de agentes externos como: Banco de dados ou Web. Neste layer contém a arquitetura MVC por exemplo, ficaria todas as views, controllers e presenters. Esta camada é responsável pela conversão dos dados para outras camadas.  
Esta camada não tem conhecimento do Banco de dados.

Exemplo: se o sistema utilizar API REST para comunicação com cliente, as classes adaptadores serão responsáveis por implementar os endpoints REST da API. Elas devem receber as requisições e direcioná-las para o caso de uso correspondente. E também fazer o caminho inverso: receber dados dos casos de uso e converter para JSON que será encaminhado para o cliente.

## Frameworks and Drivers

O círculo mais externo é composto por frameworks e ferramentas como o Banco de dados , framework web, etc. Geralmente não tem muito código neste layer, apenas o código que irá comunicar com os círculos mais internos.  
Este layer comporta todos os detalhes, Web, Banco de dados, etc, esses detalhes são mantidos do lado de fora onde não podem causar problemas na regra de negócio e nos círculos internos.

## Only Four Circles?

A quantidade de camadas depende da aplicação, é possível acrescentar mais de quatro camadas dependendo da necessidade do desenvolvimento. Não existe uma regra dizendo que você precisa ter apenas estes quatro círculos.
A regra da dependência sempre é aplicada, mesmo com mais camadas, a dependência de código sempre age para dentro, quanto mais para dentro dos circulos, mais abstração encontra e políticas mais de alto nível. O círculo interno é o mais geral, circulo externo possui detalhes concretos de baixo nível.

## Crossing boundaries

Presenter e Controller comunicam com UseCase.  
Na arquitetura limpa o fluxo segue de fora para dentro, por exemplo uma classe externa X pode criar um objeto da classe interna Y e chamar um método deste objeto. No entanto alguns cenários, um caso de uso pode precisar chamar um controller.

Se necessário, para que o caso de uso se comunique com presenter/controller é utilizado o princípio de inversão de dependência, onde existe interfaces e relações opostas ao fluxo de controle em pontos específicos através da fronteira. Não é possível chamar diretamente o Presenter porque violaria a regra de dependência. Para isso, o useCase chama uma interface (usecase output port) no circulo interno e o presenter (no circulo externo) implementa ela.  
A mesma técnica é utilizada para cruzar fronteiras nas arquiteturas. É tirado vantagem do polimorfismo dinâmico para criar códigos com dependências que se opõe ao fluxo de controle para que entre em conformidade com a regra de dependência, não importando em qual direção o fluxo está indo.

## What data coresses the boudaries

Basicamente o dado que cruza as fronteiras são estrutura de dados, estruturas básicas ou objetos de transferência de dados. Não se pode passar entidades ou linhas de banco de dados. Não podemos ter estrutura de dados violando a regra de dependência.  
Por exemplo: muitos frameworks de banco de dados retornam um dado formatado conveniente na resposta da query. Nós não podemos passar esta estrutura através da fronteira. Isso violaria a regra de dependência pois força o circulo interno ter conhecimento do circulo externo.  
Então quando passamos um dado através da fronteira, é sempre na forma mais conveniente para o circulo interno.

**Referência:**  
MARTIN, Robert C. The Clean Architecture. The Clean Code Blog, 2012. Disponível em: <https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html>. Acesso em: 06 de set. de 2021.
