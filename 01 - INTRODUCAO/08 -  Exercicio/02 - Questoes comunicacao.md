Questionário sobre Comunicação Assíncrona e Arquitetura de Microsserviços

1. Qual é uma característica fundamental da comunicação assíncrona em microsserviços?

A) Dependência direta entre sistemas envolvidos<br/>
B) Comunicação em tempo real entre serviços<br/>
C) Redução do acoplamento entre sistemas<br/>
D) Processamento síncrono e imediato<br/>

2. O que acontece quando um sistema receptor está indisponível em uma comunicação assíncrona?

A) As mensagens são descartadas automaticamente<br/>
B) As mensagens permanecem em uma fila ou tópico para serem processadas mais tarde<br/>
C) A comunicação falha e deve ser reiniciada manualmente<br/>
D) Os dados são enviados novamente ao publicador<br/>

3. Qual das opções abaixo é um exemplo de tecnologia que implementa o padrão Pub/Sub?

A) REST<br/>
B) Apache Kafka<br/>
C) SOAP<br/>
D) SQL Server<br/>

4. Qual é a principal vantagem do uso de filas em comunicação assíncrona?

A) Processamento mais rápido em todos os serviços<br/>
B) Garantia de que os dados nunca serão perdidos<br/>
C) Escalabilidade e processamento conforme a capacidade dos serviços<br/>
D) Centralização do fluxo de trabalho<br/>

5. No modelo de orquestração, qual é a função do orquestrador?

A) Gerenciar a comunicação direta entre dois microsserviços<br/>
B) Armazenar todas as mensagens enviadas pelos serviços<br/>
C) Coordenar e controlar o fluxo de atividades entre os serviços<br/>
D) Monitorar o desempenho da infraestrutura<br/>

6. Qual é uma desvantagem do modelo de orquestração em microsserviços?

A) Escalabilidade limitada pela centralização<br/>
B) Dificuldade em monitorar os processos do sistema<br/>
C) Alta complexidade na gestão de contratos entre serviços<br/>
D) Maior dificuldade de implementar regras de roteamento<br/>

7. Em que situação o modelo de coreografia pode ser mais adequado que o de orquestração?

A) Quando os processos exigem controle centralizado<br/>
B) Quando os serviços precisam ser autônomos e independentes<br/>
C) Quando a visibilidade do fluxo é uma prioridade<br/>
D) Quando a arquitetura depende de mensagens descartáveis<br/>

8. Qual é uma desvantagem significativa do modelo de coreografia?

A) Maior acoplamento entre os serviços<br/>
B) Dependência de um ponto central de controle<br/>
C) Complexidade na gestão de interações entre os serviços<br/>
D) Necessidade de infraestrutura de alta capacidade<br/>

9. Qual das opções descreve corretamente uma mensagem no RabbitMQ?

A) Permanece disponível para releitura após ser consumida<br/>
B) É excluída após ser consumida por um serviço<br/>
C) É armazenada indefinidamente no tópico até ser excluída manualmente<br/>
D) É roteada aleatoriamente para filas disponíveis<br/>

10. Qual é uma vantagem do uso de comunicação assíncrona em sistemas distribuídos?

A) Processamento síncrono de alta performance<br/>
B) Redução da infraestrutura necessária para alta demanda<br/>
C) Dependência de disponibilidade instantânea dos sistemas<br/>
D) Complexidade reduzida em arquiteturas massivas<br/>