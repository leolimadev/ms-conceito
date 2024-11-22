# Rest

## Comunicação Assíncrona com REST em Microsserviços

Em microsserviços, a comunicação assíncrona costuma ser uma abordagem mais segura e resiliente para a troca de dados, especialmente em cenários onde evitar perda de dados é fundamental. Vamos explorar por quê.

Imagine que temos um Sistema 1 enviando uma transação importante de, digamos, um milhão de reais para um Sistema 2 através de uma chamada REST. Essa comunicação direta funciona bem quando ambos os sistemas estão online. Porém, se o Sistema 2 estiver indisponível, a transação não será concluída, levando à perda de dados, o que é crítico em sistemas de grande escala.

Muitos desenvolvedores seguem a prática padrão de integrar sistemas por meio de chamadas REST diretas, algo que aprendemos desde o início ao desenvolver APIs. Contudo, à medida que a complexidade do sistema cresce, precisamos considerar cenários em que um ou mais serviços podem estar temporariamente indisponíveis. Em um sistema distribuído, essas falhas são inevitáveis, e perder dados por conta de uma dependência em tempo real se torna inaceitável.

Para resolver isso, a comunicação assíncrona evita que os sistemas fiquem dependentes de disponibilidade instantânea. Utilizando filas, tópicos de mensagens ou middlewares especializados, um sistema pode enviar dados sem esperar uma resposta imediata, garantindo que, mesmo se algum serviço estiver fora do ar, as informações fiquem armazenadas e possam ser processadas assim que todos os sistemas estejam novamente ativos.

Assim, ao projetar microsserviços, considere cuidadosamente onde você realmente precisa de chamadas REST síncronas e onde a comunicação assíncrona poderá oferecer a resiliência que seu sistema precisa. A análise desse equilíbrio pode reduzir falhas e ajudar a garantir a integridade dos dados em diferentes cenários.

