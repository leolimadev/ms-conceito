# Abordagens para Trabalhar com Filas

Vou mostrar duas abordagens amplamente utilizadas para implementar comunicação assíncrona em microsserviços, cada uma baseada em tecnologias distintas.

A primeira abordagem é o padrão Pub/Sub (Publisher/Subscriber). Nesse modelo, um sistema (o "publicador") envia mensagens que ficam armazenadas em um local chamado de “tópico” (ou fila, dependendo da tecnologia). Sistemas que precisam dessas mensagens se conectam ao tópico e aguardam as mensagens chegarem, lendo-as conforme são publicadas. Esse padrão é muito útil para casos em que queremos que múltiplos consumidores acessem as mesmas mensagens. Algumas tecnologias que implementam Pub/Sub incluem Apache Kafka, Apache Pulsar, AWS Kinesis e Google Pub/Sub.

A segunda abordagem é o uso de uma estrutura de Exchange, como acontece no RabbitMQ. No RabbitMQ, a comunicação assíncrona é configurada com mais flexibilidade. Em vez de enviar mensagens diretamente para uma fila, o publicador envia a mensagem para uma "exchange". A exchange, então, aplica regras de roteamento que distribuem a mensagem para uma ou mais filas específicas. Isso permite que, com base em regras, as mensagens sejam direcionadas de maneira personalizada: uma mensagem pode ser enviada para várias filas ao mesmo tempo ou direcionada para filas específicas dependendo de critérios configurados na exchange.

Um ponto importante é que no RabbitMQ, após a leitura, as mensagens são removidas da fila tradicional. Em contraste, no Apache Kafka, as mensagens permanecem no tópico por um período configurável, permitindo releituras, o que é útil para histórico ou processamento repetido.

Por exemplo:

Imagine que temos publicadores enviando mensagens para uma exchange.
Com as regras configuradas, a exchange determina para quais filas essas mensagens vão. Um publicador pode enviar uma mensagem que será roteada apenas para a fila 1, enquanto outro publicador envia mensagens que serão replicadas em várias filas (por exemplo, fila 2 e fila 3).
Isso mostra como as exchanges permitem controle detalhado sobre o roteamento, baseado em regras, chamado de "keys". Essas regras permitem que a mesma exchange direcione mensagens para destinos diferentes, maximizando a flexibilidade de consumo assíncrono no sistema.

Essas abordagens oferecem benefícios específicos para microsserviços em termos de resiliência e escalabilidade, e são muito úteis em arquiteturas orientadas a eventos (Event-Driven Architecture), que exploraremos mais adiante.