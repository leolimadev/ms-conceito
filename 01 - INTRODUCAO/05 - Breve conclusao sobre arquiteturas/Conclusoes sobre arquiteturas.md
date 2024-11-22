# Quando utilizar cada arquitetura

## Monolitos:

### Baixa quantidade de desenvolvedores

Se sua equipe é pequena, a implementação e a manutenção de microsserviços podem ser desafiadoras. Dividir o sistema em múltiplos serviços aumenta a complexidade do trabalho e a coordenação necessária entre os desenvolvedores. Com um monolito, sua equipe pode trabalhar de forma mais integrada, com menos barreiras e conflitos entre contextos, facilitando o desenvolvimento e o deploy. Microsserviços exigem experiência e maturidade em governança, portanto, para uma equipe pequena e sem histórico com essa abordagem, um monolito é geralmente a escolha mais viável.

### Governança simplificada

Quando a estrutura de governança e a arquitetura corporativa ainda não estão bem estabelecidas, criar microsserviços pode resultar em um ambiente caótico, com dificuldade de comunicação e integração. Um monolito permite que a empresa tenha um único ponto de referência, um sistema mais unificado e processos bem definidos, sem a necessidade de uma governança robusta que garanta a comunicação entre serviços. Para empresas menores, ou sem uma arquitetura claramente definida, o monolito tende a ser uma abordagem mais controlada.

### Restrições orçamentárias

Microsserviços, por sua natureza distribuída, podem gerar custos operacionais altos devido à infraestrutura necessária, como serviços de monitoramento, log, cache e CI/CD para múltiplos serviços. Um monolito, por outro lado, concentra essas necessidades em um único sistema, tornando os custos de infraestrutura e de operações consideravelmente mais baixos. Em ambientes com restrições de orçamento, o monolito pode ser a escolha mais econômica, evitando despesas que poderiam rapidamente ultrapassar o orçamento alocado.

### Projeto sem conhecimento de todos os contextos

No início de um projeto, é comum não ter total clareza dos requisitos e do modelo de negócios. Esse cenário de incerteza torna um monolito mais adequado, pois ele oferece flexibilidade para pivotar rapidamente com menos esforço do que uma estrutura de microsserviços, que envolveria contratos e pontos de integração entre serviços. Conforme o entendimento do projeto aumenta, o monolito pode evoluir, e somente quando houver um conhecimento sólido de todos os contextos é que se pode considerar a transição para microsserviços.

### POC de sistemas

Para uma prova de conceito (POC), o monolito é uma excelente escolha. Ele permite testar rapidamente uma ideia de sistema sem a complexidade de um ambiente de microsserviços. Como uma POC visa validar um conceito com agilidade, a simplicidade do monolito reduz riscos e permite fazer mudanças e descartes rapidamente, caso o conceito não se mostre viável. Se a POC der certo, o sistema poderá ser redesenhado em microsserviços posteriormente.

### Possibilidade de mudanças críticas afetando todos os sistemas

Quando o projeto é novo e as regras de negócio estão em constante mudança, microsserviços podem complicar o processo, pois cada mudança afetará múltiplos serviços, contratos e pipelines. Em um monolito, é possível fazer alterações críticas em um único sistema, simplificando a implementação e o deploy dessas mudanças. Em startups e projetos onde há grande necessidade de pivotar rapidamente, um monolito oferece a flexibilidade necessária, evitando o retrabalho e a complexidade de manter vários microsserviços atualizados simultaneamente.

## Microsserviços

### Necessidade de Tecnologia Específica para Resolução de Problemas Específicos

Optar por microsserviços faz mais sentido quando o sistema exige tecnologias variadas para resolver diferentes desafios de maneira eficiente. Imagine um contexto onde o processamento intensivo de dados, machine learning ou análises em tempo real são necessários. A arquitetura baseada em microsserviços permite que cada parte do sistema seja construída com a tecnologia mais adequada, oferecendo uma vantagem competitiva ao adaptar-se às demandas específicas. Em um sistema menor e mais simples, essas exigências não se aplicariam, e o custo de manter essa diversidade de tecnologias seria desnecessário.

### Contextos Bem Definidos nas Unidades de Negócio

Microsserviços se tornam uma opção vantajosa quando há clareza nos contextos e limites das unidades de negócio. Com uma separação bem definida entre as funções, torna-se possível isolar responsabilidades e criar serviços que se comuniquem de forma coordenada. Esse tipo de arquitetura brilha em cenários onde se sabe com precisão onde cada contexto começa e termina, permitindo que os desenvolvedores trabalhem com mais autonomia e com objetivos bem definidos. Para empresas que ainda estão descobrindo esses contextos, um monolito pode ser uma abordagem mais eficaz.

### Escala de Times / Grande Quantidade de Desenvolvedores

Quando o time de desenvolvimento é grande, trabalhar com microsserviços possibilita uma divisão mais fácil do trabalho, já que diferentes equipes podem focar em serviços específicos sem interferir no código das demais. Em um sistema monolítico, centenas ou milhares de desenvolvedores atuando no mesmo código-base geram conflitos frequentes e dificultam a gestão. Nesses casos, dividir o sistema em microsserviços reduz a complexidade da colaboração em larga escala e aumenta a produtividade.

### Necessidade de Escala para Contextos Específicos

Uma das vantagens dos microsserviços é permitir a escalabilidade seletiva de componentes. Imagine um grande evento de compras online, como a Black Friday: durante esse período, o serviço responsável pelo catálogo de produtos pode demandar alta escalabilidade para suportar o pico de acessos, enquanto outras partes do sistema podem seguir com o mesmo nível de operação. Em um monolito, seria necessário escalar todo o sistema, o que pode ser ineficiente e caro. Com microsserviços, é possível expandir apenas o componente necessário, economizando recursos e tornando a arquitetura mais ágil e flexível.
