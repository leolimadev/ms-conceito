# Consumo de Recursos

## Consumo de Recursos em Comunicação Assíncrona para Microsserviços

A comunicação assíncrona traz uma vantagem essencial para microsserviços: a capacidade de se comunicar com vários sistemas sem precisar de respostas instantâneas, o que evita a perda de dados se algum sistema estiver fora do ar. Esse é um dos grandes benefícios para a resiliência, mas há um outro ponto importante a considerar: a economia de recursos.

Quando temos grandes volumes de dados a serem processados, a comunicação assíncrona pode poupar milhões em infraestrutura. Vamos pensar no exemplo de atendimento no aeroporto. Imagine que há 100 pessoas esperando para fazer o check-in, mas apenas cinco atendentes disponíveis. Se precisássemos de uma comunicação síncrona, teríamos que ter 100 atendentes para atender todas as pessoas ao mesmo tempo. Com comunicação assíncrona, porém, conseguimos organizar as solicitações em fila, permitindo que os cinco atendentes atendam gradualmente essas 100 pessoas, reduzindo drasticamente a necessidade de recursos.

Essa abordagem de filas permite que sistemas processem um volume muito maior de solicitações sem precisar de hardware suficiente para processar tudo em tempo real. Imagine que temos um milhão de solicitações de pagamento em um site. Em vez de atender todas ao mesmo tempo, essas solicitações são enfileiradas, e os servidores processam os pagamentos conforme têm capacidade. Assim, mesmo que o processamento leve um minuto ou alguns segundos, o sistema consegue lidar com a demanda de forma mais econômica e escalável.

A comunicação assíncrona, portanto, permite que você escale suas operações de forma eficiente, evitando o uso de recursos em excesso e proporcionando resiliência quando sistemas ficam temporariamente fora do ar. Essa abordagem é crucial para sistemas distribuídos e de alto desempenho.