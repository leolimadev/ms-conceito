1. O que é CQRS (Command Query Responsibility Segregation)?

a) Um padrão que combina comandos e consultas em uma única responsabilidade.
b) Um padrão que separa responsabilidades de comandos e consultas.
c) Uma forma de criar APIs RESTful.
d) Um sistema de gerenciamento de filas de mensagens.

2. Qual é a principal vantagem da separação de comandos e consultas no CQRS?

a) Redução do uso de memória.
b) Melhor controle de permissões.
c) Otimização para operações de leitura e escrita.
d) Simplificação do código, removendo eventos.

3. Qual conceito foi base para o surgimento do CQRS?

a) Arquitetura Hexagonal.
b) Clean Architecture.
c) CQS (Command Query Separation).
d) Event Sourcing.

4. Em uma implementação de CQRS, qual é a característica de comandos?

a) Eles retornam dados diretamente ao usuário.
b) Eles processam e modificam o estado do sistema.
c) São otimizados para consultas rápidas.
d) Geram eventos assíncronos para múltiplos consumidores.

5. Qual benefício principal surge ao separar bancos de dados para leitura e escrita em CQRS?

a) Evitar a replicação de dados.
b) Permitir operações simultâneas de leitura e escrita sem competição.
c) Reduzir custos de armazenamento.
d) Eliminar a necessidade de índices em bancos relacionais.

6. No exemplo de código do CalcularJurosCommand, qual é a principal função do comando?

a) Retornar os juros calculados para o usuário.
b) Modificar o estado do sistema e salvar as parcelas.
c) Recuperar informações de juros de um banco de dados.
d) Gerar notificações para consumidores de eventos.

7. O que caracteriza um evento em uma arquitetura orientada a eventos (EDA)?

a) Algo que está acontecendo em tempo real.
b) Uma notificação de algo que já ocorreu no sistema.
c) Uma mudança de estado prevista para o futuro.
d) Uma tarefa agendada para ser executada posteriormente.

8. Qual é a característica fundamental dos eventos?

a) São mutáveis para ajustes posteriores.
b) Representam ações planejadas para o futuro.
c) São imutáveis e descrevem mudanças passadas.
d) Devem conter todos os dados do sistema para otimização.

9. Qual das opções é um exemplo de evento de domínio?

a) "Cache Atualizado".
b) "Pedido Criado".
c) "Log de Depuração".
d) "Memória Liberada".

10. Qual é a responsabilidade principal de um mediador (Message Broker)?

a) Modificar eventos recebidos.
b) Criar eventos baseados em consultas.
c) Facilitar a comunicação entre produtores e consumidores.
d) Processar dados de eventos diretamente.

11. Qual é um exemplo de produtor de eventos?

a) Uma fila de mensagens vazia.
b) Um serviço backend que emite eventos após ações de usuários.
c) Um banco de dados que somente lê informações.
d) Uma interface gráfica que processa eventos localmente.

12. O que é idempotência no contexto de eventos?

a) Garantir que eventos sejam entregues exatamente uma vez.
b) Permitir que eventos sejam processados múltiplas vezes sem efeitos duplicados.
c) Certificar-se de que eventos sempre gerem respostas rápidas.
d) Reordenar eventos com base no timestamp.

13. O que distingue Event Notification de Event Sourcing?

a) Event Notification armazena todos os eventos no banco de dados.
b) Event Sourcing é usado apenas em sistemas monolíticos.
c) Event Notification transmite informações mínimas sobre mudanças de estado.
d) Event Sourcing reduz o volume de dados transmitidos.


14. Qual é a relação entre CQRS e Event Sourcing?

a) Ambos são incompatíveis em arquiteturas de microsserviços.
b) CQRS fornece a base para replicação de eventos.
c) Event Sourcing registra mudanças de estado e pode complementar CQRS.
d) CQRS elimina a necessidade de armazenamento de eventos.

15. Qual é uma vantagem de usar Event Sourcing em sistemas financeiros?

a) Reduz custos de processamento.
b) Simplifica a lógica de negócios.
c) Permite reconstruir o estado atual a partir de eventos passados.
d) Garante que eventos sejam descartados após o uso.