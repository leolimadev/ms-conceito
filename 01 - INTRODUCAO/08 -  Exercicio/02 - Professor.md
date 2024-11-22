Questionário sobre Comunicação Assíncrona e Arquitetura de Microsserviços

1. Qual é uma característica fundamental da comunicação assíncrona em microsserviços?

A) Dependência direta entre sistemas envolvidos
B) Comunicação em tempo real entre serviços
C) Redução do acoplamento entre sistemas
D) Processamento síncrono e imediato

Resposta: C

2. O que acontece quando um sistema receptor está indisponível em uma comunicação assíncrona?

A) As mensagens são descartadas automaticamente
B) As mensagens permanecem em uma fila ou tópico para serem processadas mais tarde
C) A comunicação falha e deve ser reiniciada manualmente
D) Os dados são enviados novamente ao publicador

Resposta: B

3. Qual das opções abaixo é um exemplo de tecnologia que implementa o padrão Pub/Sub?

A) REST
B) Apache Kafka
C) SOAP
D) SQL Server

Resposta: B

4. Qual é a principal vantagem do uso de filas em comunicação assíncrona?

A) Processamento mais rápido em todos os serviços
B) Garantia de que os dados nunca serão perdidos
C) Escalabilidade e processamento conforme a capacidade dos serviços
D) Centralização do fluxo de trabalho

Resposta: C

5. No modelo de orquestração, qual é a função do orquestrador?

A) Gerenciar a comunicação direta entre dois microsserviços
B) Armazenar todas as mensagens enviadas pelos serviços
C) Coordenar e controlar o fluxo de atividades entre os serviços
D) Monitorar o desempenho da infraestrutura

Resposta: C

6. Qual é uma desvantagem do modelo de orquestração em microsserviços?

A) Escalabilidade limitada pela centralização
B) Dificuldade em monitorar os processos do sistema
C) Alta complexidade na gestão de contratos entre serviços
D) Maior dificuldade de implementar regras de roteamento

Resposta: A

7. Em que situação o modelo de coreografia pode ser mais adequado que o de orquestração?

A) Quando os processos exigem controle centralizado
B) Quando os serviços precisam ser autônomos e independentes
C) Quando a visibilidade do fluxo é uma prioridade
D) Quando a arquitetura depende de mensagens descartáveis

Resposta: B

8. Qual é uma desvantagem significativa do modelo de coreografia?

A) Maior acoplamento entre os serviços
B) Dependência de um ponto central de controle
C) Complexidade na gestão de interações entre os serviços
D) Necessidade de infraestrutura de alta capacidade

Resposta: C

9. Qual das opções descreve corretamente uma mensagem no RabbitMQ?

A) Permanece disponível para releitura após ser consumida
B) É excluída após ser consumida por um serviço
C) É armazenada indefinidamente no tópico até ser excluída manualmente
D) É roteada aleatoriamente para filas disponíveis

Resposta: B

10. Qual é uma vantagem do uso de comunicação assíncrona em sistemas distribuídos?

A) Processamento síncrono de alta performance
B) Redução da infraestrutura necessária para alta demanda
C) Dependência de disponibilidade instantânea dos sistemas
D) Complexidade reduzida em arquiteturas massivas

Resposta: B