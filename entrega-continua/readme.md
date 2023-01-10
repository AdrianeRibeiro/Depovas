# Entrega contínua

- Visa diminuir o risco na hora do deploy do software através de deploys frequentes e bem testados. Dessa forma, a publicação do software deve ser:
  - Granular: deploys menores
  - Frequente
  - Automatizada

- Sua base é a Integração Contínua

<br>

# Entrega Contínua X Deploy Contínuo

- O deploy coloca qualquer alteração em produção. Já a entrega não coloca qualquer alteração em produção, mas só por motivos de negócio.

<br>

# Antipatterns

- Gerenciamento manual de ambiente

  - Resultado: Deploy não confiável

  - Regra: Todos os ambientes são tratados como código, versionado e criados de maneira automatizada

<br>

- Deploy Manual

  - Tarefas que devem ser executadas manualmente: 
    - 1) escolher a versão do release e 
    - 2) Click no "deploy button"

<br>

- Deploy apenas no fim do ciclo de desenvolvimento

<br>

# Princípios

> Entregar software com alta qualidade e grande valor de maneira eficiente, rápida e confiável.

I) Automatize

II) Versione

III) Repita

IV) Garanta qualidade

V) Defina "done"

VI) Cria delivery team (Todos os envolvidos na criação são resposáveis pela entrega)

VII) Usa melhoria contínua

<br>

# Elementos da Entrega Contínua

- Cultura Devops
- Patters
- Arquitetura: testability, deployability, algumas mudanças para facilitar a testability e deployability

<br>

# Boas práticas

- pipeline é a única forma de deploy
- manter o pipeline o mais rápido possível - otimize-o
- build no ínicio e apenas uma vez
- build independente do ambiente
- ambiente iguais / semelhantes ao de produção
- ambientes efêmeros (temporários)
- deploy para ambientes de maneira igual

<br>

# Pipeline de implantação

> ```Unit Test --> Aceitação Automatizada --> Homologação --> Produção```

- As etapas existem de forma a receber feedback o mais rápido possível

<br>

# Commit Stage

- deve iniciar a cada commit e executar rápido (menos de 10 minutos)
- build: Primeiro passo é buildar a aplicação
- testes unitários e de integração: logo após o build é rodado os testes, pois são mais rápidos (feedback)
- análise de qualidade de código: são gerados relatórios. Podem ser executados em paralelo aos testes de unidade
- após o build e os testes passarem, tem-se:
  - plano de testes pela qualidade
  - relatório de qualidade
  - um artefato do build (jar, docker, gem, zip..)

<br>

# Teste de aceitação automatizados (AAT)

- foca em testes funcionais, que testam o sistema todo, por isso são mais caros de escrever e manter
- inicia após o commit stage e é mais demorado

<br>

# Homologação (User Acceptance Testing Stage)

- serve para o usuário final validar se o software atende aos requisitos e expectativas
- objetivos:
  - testar o deploy no ambiente igual ao de produção
  - dar feedback para a equipe sobre a aceitação e usabilidade do software
  - validar se o software atende as expectativas

<br>

# Testes de carga (Capacity Testing Stage)

- deve ter metas claras, com monitoração do sistema
- usar ferramentas de monitoração
- JMeter..
- não precisam rodar a cada build, mas idealmente seguem um ciclo constante

<br>

# Atributos que influenciam a entrega contínua

- Testabilidade: todo pipeline é relacionado com testes e o feedback deles. Um software sem teste ou que é difícil testar, não atende a integração e nem a a entrega contínua.

- Deployabilidade: define a facilidade de implantar o software. 

<br>

# Deploy x Release

- São duas operações distintas. Possível fazer deploy da aplicação, mas não publicar as novas releases.
- Deploy é colocar as alterações em produção.        
- Release é deixar as alterações visíveis.

<br>

# Release Pattern

- `Blue/Green Deployment`

  - já fez o deploy
  - tem-se duas versões: a antiga (azul) e a nova (verde)
  - em algum momento é feito o switch entre essas versões
  - todos os usuários vão ser direcionados para o novo ambiente
  - o azul vai continuar funcionando por um tempo
  - cliente não percebe essa mudança

<br>

- `Canary Release`

  - as duas versão versões (antiga (azul) e nova (verde)) estão sendo utilizadas ao mesmo tempo, porém a nova versão não está sendo usada por todos

<br>

- `Feature Toggles`

  - estratégia de dark launching - features invísiveis, mas o cliente ainda não tem acesso (ou só alguns clientes).
  - feito via configuração - if






