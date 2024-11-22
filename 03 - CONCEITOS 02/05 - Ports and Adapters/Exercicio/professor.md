1. Qual é o principal objetivo do padrão Saga em sistemas distribuídos?

A) Reduzir a latência das chamadas REST
B) Melhorar a segurança entre microsserviços
C) Coordenar etapas de uma transação distribuída e lidar com falhas
D) Evitar a comunicação entre microsserviços

Resposta: C

2. No padrão Saga, o que ocorre quando uma etapa falha?

A) Todo o sistema para até que a falha seja resolvida
B) O orquestrador encerra a saga imediatamente
C) O orquestrador inicia um processo de compensação para reverter as operações anteriores
D) O erro é ignorado para continuar as etapas restantes

Resposta: C

3. Qual dos seguintes exemplos ilustra melhor a aplicação do padrão Saga?

A) Atualização de um banco de dados centralizado
B) Coordenação de um pedido de e-commerce, desde pagamento até entrega
C) Envio de uma única mensagem entre dois serviços
D) Processamento de dados em tempo real em um pipeline

Resposta: B

4. Qual é a diferença fundamental entre orquestração e coreografia no padrão Saga?

A) Coreografia não utiliza microsserviços, enquanto orquestração utiliza
B) Orquestração é síncrona, enquanto coreografia é assíncrona
C) Na orquestração, um orquestrador central gerencia as etapas; na coreografia, os serviços decidem de forma independente
D) Coreografia é mais eficiente que orquestração em todos os cenários

Resposta:  C

5. Ao utilizar comunicação síncrona (REST), qual estratégia pode ajudar em caso de falha na comunicação?

A) Ignorar o erro e continuar a execução
B) Implementar mecanismos de retry, como backoff exponencial
C) Utilizar apenas chamadas HTTP GET
D) Garantir que todos os serviços estejam sempre disponíveis

Resposta:  B

6. Qual é uma vantagem do uso de filas em sistemas distribuídos?

A) Menor uso de memória em microsserviços
B) Redução de erros em tempo de execução
C) Maior resiliência, pois as mensagens são armazenadas até que o serviço esteja disponível
D) Garantia de que todas as mensagens serão entregues imediatamente

Resposta: C

7. O que é um tópico de erros em um sistema baseado em filas?

A) Uma lista de logs gerados pelos serviços
B) Um local onde falhas de compensação são registradas para monitoramento e resolução
C) Uma funcionalidade de backup de dados sensíveis
D) Um mecanismo que ignora mensagens com erro

Resposta:  B

8. Por que sistemas modernos utilizam comunicação assíncrona entre microsserviços?

A) Para eliminar a necessidade de monitoramento
B) Para aumentar a resiliência e desacoplar os serviços
C) Para evitar o uso de bancos de dados independentes
D) Para garantir respostas imediatas entre os serviços

Resposta: B

9. Qual é a principal desvantagem da comunicação síncrona entre serviços?

A) Alto consumo de recursos de hardware
B) Dependência da disponibilidade imediata dos serviços chamados
C) Complexidade na implementação de retries
D) Redução da escalabilidade do sistema

Resposta:  B

10. Na Arquitetura Hexagonal, o que os “Ports” representam?

A) Conexões diretas com o banco de dados
B) Classes que implementam lógica de negócio
C) Pontos de comunicação entre a aplicação e o mundo externo
D) Serviços que gerenciam os dados da aplicação

Resposta: C

11. Qual é a principal vantagem da Arquitetura Hexagonal?

A) Redução do tempo de desenvolvimento inicial
B) Flexibilidade para substituir tecnologias externas sem afetar o núcleo do sistema
C) Simplicidade na estrutura do código
D) Menor consumo de recursos no runtime

Resposta: B

12. Como a Arquitetura Hexagonal melhora a testabilidade de sistemas?

A) Fornecendo um modelo único para testes integrados
B) Ao isolar as interações tecnológicas em Adapters, permitindo testes independentes do núcleo do sistema
C) Garantindo que todas as classes sejam mockadas
D) Substituindo o Domain Layer por uma implementação simplificada

Resposta: B

13. O que é o Infrastructure Layer na Arquitetura Hexagonal?

A) A camada onde ficam as regras de negócio
B) A camada que permite a comunicação com o mundo externo, como bancos de dados e APIs externas
C) A camada que gerencia as transações distribuídas
D) A camada que conecta o Domain diretamente à interface do usuário

Resposta: B

14. Qual dos seguintes cenários seria mais adequado para aplicar a Arquitetura Hexagonal?

A) Um sistema monolítico com poucas interações externas
B) Um sistema de microsserviços que precisa trocar tecnologias de armazenamento frequentemente
C) Uma aplicação com lógica de negócio trivial e poucos pontos de integração
D) Uma aplicação estática que não será alterada no futuro

Resposta: B

15. Quais são as principais desvantagens da Arquitetura Hexagonal?

A) Redução da flexibilidade e aumento de bugs
B) Necessidade de frameworks proprietários e maior dependência externa
C) Mais esforço inicial para implementar abstrações e risco de overengineering
D) Dificuldade em gerenciar interações entre microsserviços

Resposta: C