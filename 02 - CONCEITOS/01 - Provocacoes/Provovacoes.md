# Provocações

## Pilares Necessários para Trabalhar com Microsserviços

Ao optar pela arquitetura de microsserviços, algumas capacidades técnicas e organizacionais se tornam essenciais para lidar com as complexidades e exigências que essa abordagem impõe. Aqui, abordaremos alguns tópicos fundamentais que ajudam a estruturar e maturar o ambiente e a equipe para operar com eficiência em um cenário de microsserviços.

## Maturidade do Time

A equipe deve possuir maturidade no desenvolvimento e gestão de sistemas complexos, como pipeline de CI/CD, containers e gestão de imagens. A habilidade de coordenar esses processos é vital, pois em microsserviços a complexidade e a necessidade de organização são ampliadas. Além disso, o time precisa entender os princípios fundamentais de microsserviços para garantir autonomia e consistência nos serviços.

## Containers

Em ambientes de microsserviços, os containers se tornaram uma tecnologia essencial. Eles são fundamentais para gerenciar a complexidade e a escalabilidade de sistemas distribuídos. Conhecer containers vai além do simples uso de ferramentas; trata-se de entender como eles suportam a arquitetura de microsserviços, otimizam o desempenho e simplificam operações.

## Arquitetura de Software

Trabalhar com microsserviços exige um nível elevado de conhecimento em arquitetura de software. Diferente de monólitos, onde o foco é integrar funcionalidades, microsserviços demandam uma arquitetura distribuída que facilite a comunicação entre serviços e otimize a escalabilidade e o desempenho.

## Arquitetura de Solução

A visão de arquitetura de solução deve ser aprimorada. Com microsserviços, você não está mais gerenciando um único sistema, mas um ecossistema de serviços interdependentes. Conhecimento de arquiteturas como Event-Driven e Domain-Driven Design (DDD) ajuda a organizar e modularizar os serviços.

## Comunicação Assíncrona

Comunicação assíncrona é um aspecto central em microsserviços. Utilizar message brokers como Apache Kafka, RabbitMQ ou AWS SQS reduz o acoplamento e aumenta a resiliência dos serviços, diminuindo a dependência de chamadas diretas (REST), que podem criar gargalos e fragilizar o sistema.

## Concorrência

Em um ambiente distribuído, é comum que múltiplos serviços acessem recursos simultaneamente. Saber lidar com concorrência por meio de técnicas como locks (pessimistas e otimistas) e mutex é essencial para evitar problemas de race condition. Em cenários de alto tráfego, é necessário garantir que as operações se mantenham consistentes sem comprometer a performance.

## Cache

O uso de cache distribuído é outro requisito. Além de melhorar a performance, ele reduz a carga sobre bancos de dados. Ferramentas como Redis e Memcached são exemplos comuns de caches distribuídos que podem ser integrados para acelerar o acesso a dados frequentemente utilizados.

## Bancos Individuais por Serviço

Cada microsserviço deve ser independente, o que significa que ele precisa de seu próprio banco de dados para evitar acoplamento. Isso permite autonomia, mas também cria desafios na integração de dados. Para relatórios, é preciso considerar técnicas como Event Sourcing ou flat tables para consolidar dados de diferentes serviços.

## Domain-Driven Design (DDD)

DDD é altamente recomendado para modelar microsserviços. Ele ajuda a entender o escopo de cada serviço e evita sobreposições, facilitando o desenvolvimento e a manutenção dos serviços ao longo do tempo. Com DDD, cada serviço opera dentro de seu próprio contexto delimitado (bounded context), o que melhora a organização e clareza do sistema.

## Observabilidade

Em um ambiente distribuído, a visibilidade sobre o sistema é essencial. Observabilidade em microsserviços vai além de apenas ter logs; ela se estende a métricas, tracing distribuído, e correlação de eventos.

- Logs: A padronização dos logs é crucial. É importante que todos os microsserviços mantenham um formato uniforme para que informações relevantes possam ser extraídas com facilidade em caso de falhas.
- Métricas: É importante monitorar tanto as métricas específicas de cada serviço quanto as métricas do sistema como um todo. Assim, é possível identificar anomalias e agir proativamente.
- Tracing Distribuído: Em microsserviços, o tracing distribuído permite rastrear uma transação que percorre diversos serviços, facilitando a identificação de falhas e gargalos. O uso de Correlation ID é uma prática recomendada para rastrear chamadas entre microsserviços.

## Conclusão

Esses tópicos representam uma base sólida para a transição para microsserviços. Embora não seja necessário aplicar tudo de uma vez, é fundamental que o time esteja ciente da complexidade de cada aspecto, à medida que o sistema se expande. Trabalhar com microsserviços não significa apenas utilizar um novo tipo de arquitetura, mas dominar um conjunto de habilidades e ferramentas que garantirão a performance e a resiliência da aplicação em um cenário distribuído.