# Microsserviços

## Independentes e autônomos

Um ponto crucial ao lidar com microsserviços é que eles devem ser independentes e autônomos. Em outras palavras, mesmo que todos os outros microsserviços estejam fora do ar, o seu microsserviço precisa continuar funcionando. Esse é um dos maiores desafios, pois criar um microsserviço sem dependência direta de outros sistemas externos é complexo, mas viável. A questão é que ele não deve depender diretamente de outro serviço.

Para isso, é necessário implementar mecanismos de fallback para os casos em que o microsserviço de que você depende está temporariamente indisponível. Imagine, por exemplo, um sistema bancário em que um microsserviço exibe o saldo do usuário. Se o serviço responsável pelo cálculo do saldo estiver fora do ar, o ideal não é exibir um erro, mas mostrar a última informação disponível — mesmo que ela tenha alguns segundos ou minutos de atraso. Assim, o usuário vê o saldo atualizado há, digamos, 15 segundos, mantendo uma experiência minimamente satisfatória.

Essa prática é chamada de graceful degradation, ou degradação graciosa, em que o sistema mantém parte de suas funcionalidades mesmo em condições adversas, evitando um erro total para o usuário. Esse tipo de abordagem é desafiador de implementar, mas é essencial em momentos críticos para garantir que o usuário final receba valor, mesmo que de forma parcial. Em essência, um microsserviço independente faz parte de um sistema maior e trabalha para manter a operação contínua desse ecossistema, mesmo que precise reduzir temporariamente suas funcionalidades.


## Uma parte de um todo

Microsserviços são sempre componentes de uma estrutura maior. Se você está desenvolvendo um sistema independente, sem um ecossistema ao seu redor, provavelmente está criando um pequeno monólito, e não um microsserviço. Microsserviços têm características específicas: cada um possui um escopo bem definido, é independente e autônomo, e integra uma arquitetura mais ampla e complexa.

Ao abordar microsserviços, é inevitável falar de uma arquitetura orientada a serviços, que discutiremos em breve. Mas é essencial pensar neles como peças interdependentes de um sistema maior, cuja comunicação é mais complexa e, por isso, exige que o serviço degrade de forma controlada quando suas dependências falham.

Esse é um ponto que, para quem já trabalha com microsserviços, pode parecer repetitivo, mas vale a pena refletir: sempre há algo novo a considerar que pode otimizar ainda mais essa arquitetura.

## Propósito e escopo bem definidos

Mas o que são microsserviços? Microsserviços são aplicações com escopos e objetivos bem delimitados. Em essência, eles são sistemas como qualquer outro. A diferença não está na essência, mas na escala e na responsabilidade. Um sistema monolítico geralmente abrange múltiplos escopos e possui várias responsabilidades, o que significa que ele pode ser alterado por uma série de razões diferentes. Microsserviços, por outro lado, devem ter apenas uma razão para mudar.

Aqui, vale lembrar do Princípio da Responsabilidade Única (SRP), o “S” do SOLID, proposto por Uncle Bob. Esse princípio sugere que um componente — seja ele uma classe ou um microsserviço — deve ter apenas um motivo para sofrer modificações. Em microsserviços, essa ideia é ampliada: se um serviço está sendo alterado para refletir necessidades de diferentes áreas, como suporte ao cliente e vendas, provavelmente ele está fora do escopo ideal e deveria ser dividido.

É aí que o Domain-Driven Design (DDD) entra em cena, com o conceito de Bounded Contexts (contextos delimitados). Um contexto delimitado fornece uma visão clara de onde o microsserviço deve atuar. Embora nem sempre haja uma correspondência direta entre um contexto delimitado e um microsserviço, ele é um ótimo ponto de partida. Em resumo, um microsserviço deve ter um escopo específico para resolver um tipo de problema, com um propósito bem definido e único.