# Monólitos

## Introdução

Antes de iniciarmos a conversa sobre Microsserviços, precisamos entender o que são monólitos. A intenção não é detalhar exatamente o que são monólitos, vamos passar pelas principais características.

### Mais simplificado para iniciar um projeto.

Um aspecto crucial dos sistemas monolíticos é a facilidade de iniciar um novo projeto. Isso ocorre porque tudo fica centralizado em um único projeto, facilitando a organização das pastas e eliminando a necessidade de configurações complexas de comunicação entre sistemas. Em vez de implementar filas ou fazer múltiplas chamadas REST para obter dados de diferentes sistemas, você tem tudo disponível em um mesmo contexto e, geralmente, no mesmo banco de dados. Isso simplifica a geração de relatórios e outras operações internas. Assim, ao começar um novo projeto, trabalhar com um sistema monolítico tende a ser “mais simples” – dentro das demandas e complexidade do negócio – tornando-o uma escolha prática para o desenvolvimento inicial.

### Todos os escopos dentro de um mesmo sistema.

Sistemas monolíticos são aqueles onde todos os módulos e funcionalidades estão contidos em um único sistema. Podemos imaginar um sistema monolítico como uma aplicação unificada, onde todos os componentes, áreas e contextos estão integrados. Tudo o que é necessário para o funcionamento do sistema está centralizado dentro dessa mesma estrutura. Comumente, quando trabalhamos em uma empresa ou desenvolvemos uma aplicação, é provável que estejamos lidando com um sistema monolítico. A comunicação entre as partes do sistema é direta e simplificada: basta instanciar uma classe, fazer uma chamada a um serviço, e já estamos interagindo com outros componentes do mesmo sistema.

### Todas as equipes trabalhando em um mesmo sistema.

Uma característica importante dos sistemas monolíticos é que todas as equipes trabalham em um único sistema integrado. Isso significa que, independentemente do número de squads – uma, duas, três ou mais –, todas elas contribuem para o mesmo código-base. Por exemplo, se várias squads estiverem trabalhando em um sistema financeiro monolítico, cada uma tentará se concentrar em áreas diferentes para evitar conflitos e melhorar a eficiência do trabalho. A colaboração requer organização para evitar conflitos no Git e impedir que uma modificação quebre o trabalho de outra equipe.

Para isso, a presença de testes automatizados é fundamental. Em um ambiente monolítico, qualquer alteração feita por uma equipe pode, involuntariamente, afetar outras áreas do sistema. Testes automatizados ajudam a garantir que essas alterações não quebrem funcionalidades em outras partes, criando uma segurança mínima necessária para que todos possam desenvolver de forma colaborativa e confiável.

### Facilidade no processo de comunicação.

Outro ponto importante em sistemas monolíticos é a simplicidade no processo de comunicação. Em arquiteturas de microsserviços, cada serviço é independente e desempenha uma função específica, o que demanda comunicação entre diferentes sistemas por meio de filas, REST, gRPC, GraphQL, entre outros. Já em um monolito, onde tudo está integrado em uma única aplicação, essa complexidade desaparece: a comunicação entre módulos ocorre em memória e dentro da mesma aplicação.

Essa centralização elimina a necessidade de implementar recursos como Circuit Breakers e políticas de retry, o que simplifica a arquitetura. Além disso, o troubleshooting é muito mais direto em um sistema monolítico, já que eventuais erros ficam localizados dentro do mesmo contexto, facilitando a identificação e correção, sem a necessidade de rastrear problemas em múltiplos sistemas.

### Restrição em diversas tecnologias.

Outro ponto importante nos sistemas monolíticos, que não é exatamente uma desvantagem, mas uma característica com a qual é preciso se adaptar, é a limitação no uso de múltiplas tecnologias, especialmente linguagens de programação. Isso significa que, se você está desenvolvendo seu monolito inteiro em PHP, mas identifica uma rotina específica que poderia ser mais eficiente em Go ou Java, você não terá flexibilidade para usar outra linguagem. A escolha inicial de tecnologia define o padrão do sistema, e todas as partes precisam seguir essa mesma linguagem, o que é o custo de um monolito.

Por outro lado, essa restrição também traz benefícios: ter tudo na mesma linguagem assegura uniformidade e facilita a manutenção, já que todos os desenvolvedores estarão familiarizados com o mesmo stack. Além disso, ao treinar a equipe em uma única tecnologia, você pode alcançar maior produtividade, pois todos estarão alinhados com o mesmo ambiente e padrões de desenvolvimento.

### Atende grandes partes dos projetos em diversos tipos de empresa.

Uma vantagem significativa dos sistemas monolíticos é que eles atendem bem à maioria dos projetos em diversos tipos de empresa. Em grande parte dos casos, sistemas monolíticos serão suficientes para as demandas, pois tudo está centralizado em uma única aplicação. Isso facilita o processo de deploy, exigindo apenas uma pipeline de CI/CD e uma estrutura de organização única para colocar o sistema em produção. Com o ciclo de testes simplificado, a gestão do projeto também se torna mais prática.

Além disso, a simplicidade de um monolito pode trazer economia para a empresa: os custos com infraestrutura tendem a ser menores, e o sistema exige menos recursos computacionais para o deploy. Em muitos cenários, optar por um sistema monolítico é uma escolha vantajosa, tanto em termos de desenvolvimento quanto de investimento financeiro.

### Riscos no processo de deploy.

Um ponto crítico ao discutir sistemas monolíticos é o processo de deploy. Em um monolito, quando realizamos o deploy, estamos lidando com um sistema único que concentra todas as funcionalidades. Isso significa que, se algo der errado, pode comprometer toda a aplicação, afetando várias áreas da empresa de uma só vez — é o que chamamos de "colocar todos os ovos na mesma cesta". Em contraste, uma arquitetura de microsserviços permite que cada serviço funcione de forma independente; se um serviço falha, os demais continuam operando, reduzindo o impacto geral.

Por isso, em monolitos, é essencial adotar políticas de teste robustas e estratégias de deploy confiáveis, como o blue-green deployment. Com o blue-green, replicamos a infraestrutura e direcionamos o tráfego para a nova versão; se tudo correr bem, a infraestrutura antiga é desativada, mas, se houver problemas, o tráfego pode ser rapidamente redirecionado de volta, minimizando interrupções.