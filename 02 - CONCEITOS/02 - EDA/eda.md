# EDA

## Introdução

A arquitetura orientada a eventos, conhecida como Event Driven Architecture (EDA), é fundamental para sistemas baseados em microsserviços, especialmente aqueles que exigem comunicação assíncrona entre seus componentes. A premissa do EDA é que os microsserviços interagem em resposta a eventos, que representam mudanças de estado no sistema. Um evento é sempre algo que já aconteceu, como uma compra aprovada, uma página acessada, ou um cadastro concluído. Cada um desses eventos carrega informações sobre uma ação passada, que pode ser processada por outros serviços interessados em saber o que ocorreu.

Essa arquitetura é crucial para sistemas distribuídos, pois permite que diferentes partes do sistema fiquem em sincronia em tempo real. Para que isso funcione, é essencial entender os diferentes tipos de eventos, já que eles moldam a forma como os microsserviços se comunicam. Aqui, vamos falar sobre dois tipos principais de eventos utilizados em arquiteturas de microsserviços: Event Notification e Event Sourcing.

A Arquitetura Orientada a Eventos (EDA) é fundamentada em quatro pilares principais: Eventos como Entidades Centrais, Produtores de Eventos, Consumidores de Eventos e Mediadores. Estes pilares trabalham em conjunto para criar sistemas altamente escaláveis, desacoplados e reativos.

## Eventos como Entidades Centrais

### O Que São Eventos?

`Definição`: Um evento é uma notificação de que algo relevante ocorreu em um sistema.

`Estrutura`: Geralmente inclui:

    - Identificador do Evento (ex.: UUID).
    - Timestamp: Quando o evento ocorreu.
    - Payload: Dados associados ao evento (ex.: detalhes de uma compra).
    - Metadata: Informações auxiliares (ex.: versão do evento, origem).

`Tipos de Eventos`:

    - Evento de Domínio: Representa algo significativo no domínio (ex.: "Pedido Criado").
    - Evento de Sistema: Mudanças internas (ex.: "Cache Atualizado").
    - Evento de Integração: Comunicação entre sistemas (ex.: "Usuário Criado em CRM").

### Características dos Eventos

- Imutabilidade: Um evento é uma fotografia do passado, não pode ser alterado.
- Sequencialidade: Eventos devem ser processados na ordem em que ocorreram, se necessário.
- Granularidade: Devem representar ações significativas, mas sem serem excessivamente detalhados.

### Papel Central dos Eventos

- Fonte da Verdade: O sistema evolui reagindo a eventos.
- Desacoplamento: Consumidores só precisam entender o formato do evento, não o funcionamento interno do produtor.
- Replay de Eventos: Eventos podem ser armazenados e reprocessados para reconstruir o estado do sistema.


## Produtores de Eventos

### O Que é um Produtor de Eventos?

- Definição: Componente ou sistema que gera eventos quando uma ação relevante ocorre.
- Exemplo: Um serviço de e-commerce pode gerar um evento "Pedido Criado" após a finalização de uma compra.

### Tipos de Produtores

`Aplicações`:
    - Sistemas de front-end geram eventos de interação do usuário.
`Sensores IoT`:
    - Dispositivos que monitoram ambiente físico.
`Serviços Backend`:
    - Microsserviços que notificam alterações no estado.

### Responsabilidades do Produtor

- Criar Eventos: Definir eventos com estrutura clara e consistente.
- Publicar Eventos: Enviar eventos para um broker ou sistema de mediação.
- Garantir Idempotência: Certificar-se de que um evento publicado não cause efeitos duplicados.


## Consumidores de Eventos

### O Que é um Consumidor de Eventos?

- Definição: Componente ou sistema que escuta eventos para reagir a eles.
- Exemplo: Um serviço de faturamento que reage ao evento "Pedido Criado" gerando uma fatura.

### Tipos de Consumidores

- Passivos: Simplesmente processam eventos.
- Ativos: Processam eventos e geram novos eventos em resposta.

### Responsabilidades do Consumidor

- Subscrição: Inscrever-se em canais ou tópicos específicos.
- Processamento:
    - Validar e interpretar eventos recebidos.
    - Executar ações ou fluxos de trabalho baseados no evento.
- Idempotência: Garantir que eventos duplicados não causem efeitos colaterais indesejados.

### Padrões de Consumo

- Competing Consumers: Vários consumidores processam eventos de um mesmo canal.
- Single Consumer: Um único consumidor é responsável por todos os eventos de um canal.

##  Mediadores (Message Brokers ou Event Brokers)

### O Que é um Mediador?

- Definição: Um componente intermediário que gerencia a comunicação entre produtores e consumidores.
- Exemplo: Apache Kafka, RabbitMQ, NATS.

### Responsabilidades do Mediador

- Receber Eventos: Prover APIs para produtores publicarem eventos.
- Roteamento:
    - Direcionar eventos para os consumidores corretos.
    - Tópicos: Eventos são organizados em categorias.
- Entrega de Eventos:
    - Garantir qualidade no transporte:
        - At-most-once: Um evento é entregue no máximo uma vez.
        - At-least-once: Um evento é entregue pelo menos uma vez (pode ser duplicado).
        - Exactly-once: Um evento é entregue exatamente uma vez.

### Características Comuns

- Persistência: Armazenar eventos para garantir durabilidade.
- Escalabilidade: Suportar alto volume de eventos e consumidores.
- Resiliência: Funcionar mesmo com falhas parciais.

### Tipos de Mediadores

- Message Queues:
    - Entregam mensagens em fila, garantindo ordem.
- Event Streams:
    - Criam logs imutáveis (ex.: Kafka).

## Relação Entre os Pilares

- Produtores criam eventos baseados em ações ou mudanças no sistema.
- Eventos fluem para o mediador, que os distribui para consumidores.
- Mediadores garantem que produtores e consumidores permaneçam desacoplados, aumentando a escalabilidade e a resiliência.

## Event Notification

Event Notification, ou notificação de eventos, é um tipo de evento que transmite informações mínimas e relevantes para outros sistemas que possam estar interessados em uma mudança de estado. Por exemplo, quando uma compra é aprovada em uma aplicação de e-commerce, outros sistemas, como os de nota fiscal, envio e estoque, precisam ser notificados. Nesse caso, a notificação poderia conter apenas o ID do pedido e o novo status, reduzindo o volume de dados transmitidos e otimizando a comunicação entre os microsserviços.

A utilização de notificações leves de eventos é especialmente valiosa em sistemas com alta frequência de interações, como plataformas de comércio eletrônico, onde milhares de mensagens de eventos são processadas por minuto. A limitação dos dados nas notificações ajuda a evitar sobrecarga de rede e custos elevados de processamento, melhorando o desempenho do sistema como um todo.

## Event Sourcing

Já o Event Sourcing tem um propósito mais específico e é usado para registrar um histórico completo de tudo que aconteceu no sistema. Em vez de apenas notificar que um evento ocorreu, o Event Sourcing armazena cada mudança de estado de forma detalhada e sequencial. Imagine que cada etapa de um pedido - aprovado, enviado, entregue - seja armazenada como um evento no banco de dados. Isso permite que qualquer operação seja "reproduzida" para obter o estado atual, garantindo uma visão detalhada do histórico de mudanças.

Essa abordagem é especialmente útil para auditorias, onde é essencial saber a sequência exata de operações realizadas. Com todos os eventos registrados, o sistema pode, por exemplo, recalcular o saldo de uma conta bancária ou refazer o histórico de alterações em um pedido de forma confiável, proporcionando um sistema de auditoria natural.

Em sistemas que utilizam Event Sourcing, muitas vezes também é comum usar o padrão CQRS (Command Query Responsibility Segregation). Esse padrão separa as operações de escrita e leitura de dados, permitindo que cada uma seja otimizada para atender aos requisitos específicos do sistema. Isso proporciona ainda mais segurança e eficiência em ambientes onde o histórico de eventos precisa ser preservado, como em bancos e sistemas de e-commerce.

Esses dois tipos de eventos, Event Notification e Event Sourcing, são fundamentais em arquiteturas de microsserviços e, se aplicados corretamente, contribuem para uma comunicação eficiente e rastreável entre os serviços.


## Características

### Persistência Baseada em Eventos ao invés de Estado Atual

Comparação com Modelos Tradicionais:
- Modelos Tradicionais:
    - Exemplo: Em um sistema de pedidos, um banco de dados salva o estado atual do pedido (ex.: status = "Concluído").
- Event Sourcing:
    - Cada mudança no pedido é registrada como um evento (ex.: "Pedido Criado", "Pagamento Recebido", "Pedido Enviado").

Vantagens:

- Auditabilidade: Todo o histórico está disponível, permitindo auditorias completas.
- Replay e Debugging: O estado atual pode ser refeito a partir dos eventos, permitindo reproduzir cenários do passado.
- Desacoplamento: Os eventos podem ser consumidos por diferentes sistemas, aumentando a flexibilidade.

## Como Funciona o Event Sourcing

###  Registro de Mudanças como Eventos Imutáveis

`Estrutura de um Evento`:

    - ID Único: Para identificar o evento.
    - Timestamp: Momento exato em que o evento ocorreu.
    - Tipo de Evento: Ex.: "Pedido Criado", "Pagamento Recebido".
    - Dados: Informações contextuais específicas do evento.
    - Metadados: Informações auxiliares, como origem ou versão.

`Imutabilidade dos Eventos`:

    - Após um evento ser registrado, ele nunca é alterado.
    - Novos eventos são criados para refletir mudanças subsequentes.

- Exemplo Prático: Imagine um sistema de gerenciamento de contas bancárias:

    - Evento 1: ContaCriada { ID: 123, saldoInicial: 100 }
    - Evento 2: DepositoEfetuado { ID: 123, valor: 50 }
    - Evento 3: SaqueEfetuado { ID: 123, valor: 30 }

`Log de Eventos`:

    - É o registro cronológico de todos os eventos.
    - Armazenado geralmente em um Event Store (ex.: bancos de dados como Kafka, EventStoreDB).

### Reconstrução do Estado Atual a Partir do Log de Eventos

`Estado como Resultado dos Eventos`:

    - O estado atual do sistema não é salvo diretamente.
    - Ele é reconstruído somando os efeitos dos eventos em sequência.

- Exemplo de Reconstrução: Usando o exemplo de conta bancária:
    - Inicializar saldo = 0.
    - Reaplicar eventos:
    - ContaCriada: Saldo = 100.
    - DepositoEfetuado: Saldo = 150.
    - SaqueEfetuado: Saldo = 120.
    - Estado atual: Saldo = 120.

`Snapshots para Eficiência`:

    - Em sistemas com muitos eventos, a reconstrução pode se tornar cara.
    - Snapshotting é a prática de salvar o estado atual em pontos específicos para reduzir o custo de reconstrução.
    - Exemplo: Salvar o saldo de uma conta após cada 1.000 eventos.

## Benefícios do Event Sourcing

- Auditabilidade e Transparência:
    - Todos os eventos são rastreados, permitindo verificar cada mudança no sistema.
- Flexibilidade:
    - Novos consumidores podem processar eventos existentes para criar funcionalidades sem impactar o produtor original.
- Resiliência e Recuperação:
    - O sistema pode ser reconstruído completamente apenas a partir do log de eventos, útil para recuperação de desastres.
- Evolução:
    - Novos comportamentos podem ser implementados ao reprocessar eventos antigos com novas regras.

4. Desafios do Event Sourcing

- Gerenciamento de Volume:
    - Logs de eventos podem crescer rapidamente, exigindo soluções eficientes de armazenamento.
- Complexidade Inicial:
    - A abordagem exige mudanças na mentalidade de design e ferramentas adequadas.
- Evolução de Eventos:
    - Alterações nos esquemas de eventos (ex.: novos campos) podem ser desafiadoras.
