# Arquitetura baseada em microsserviços

## Maior complexidade de setup / inicialização / projeto

Ao trabalhar com microsserviços, a complexidade do setup aumenta significativamente. Cada microsserviço exige pipelines de CI/CD, análise de código, e processos de deployment dedicados, além de code reviews específicos para cada serviço. Quando temos um sistema monolítico, todos esses passos são concentrados em um único fluxo. Porém, em um ambiente com microsserviços, cada serviço precisa desses processos de forma independente. Se a implantação de um sistema monolítico já é complexa, imagine multiplicar esse esforço para diversos microsserviços, com pods no Kubernetes, testes de stress e configurações específicas de CPU e memória. Por isso, muitas empresas grandes criam equipes de plataforma dedicadas a padronizar e otimizar esses setups, permitindo que desenvolvedores foquem em seu código sem precisar lidar diretamente com toda a infraestrutura de deployment.

## Equipes com mais especialização de negócio especializadas por microsserviços

Um dos pontos positivos dos microsserviços é a possibilidade de especializar equipes para trabalharem em áreas de negócio específicas. Isso significa que desenvolvedores se tornam especialistas em uma determinada funcionalidade ou contexto, como processamento de nota fiscal. Essa especialização permite que cada equipe desenvolva um conhecimento profundo no seu domínio, garantindo resiliência e melhorias contínuas na solução. Por exemplo, uma equipe especializada soluções de pagamento se torna cada vez mais competente em tecnologias de hardware e comunicação, o que traz agilidade e qualidade nas entregas para esse contexto específico.

## Múltiplas tecnologias

Com microsserviços, é possível escolher tecnologias e linguagens que melhor atendam as necessidades de cada serviço. Isso permite a utilização da tecnologia mais adequada para resolver cada problema, aumentando a flexibilidade. Embora isso traga vantagens, também exige um gerenciamento cuidadoso para manter consistência e integridade entre as diversas tecnologias usadas nos microsserviços, o que pode exigir conhecimentos adicionais das equipes.

## Escalabilidade facilitada, deploy menos arriscado

Microsserviços permitem escalar serviços individuais conforme necessário, sem impacto direto nos outros serviços. Esse modelo também reduz os riscos durante o deployment. Se o deployment de um microsserviço falhar, os outros microsserviços continuam funcionando normalmente, degradando apenas parcialmente a aplicação, sem derrubar todo o sistema. Em contrapartida, com sistemas monolíticos, um erro no deploy pode deixar toda a aplicação offline, o que representa um risco maior.

