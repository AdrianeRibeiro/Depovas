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

- Entregar software com alta qualidade e grande valor de maneira eficiente, rápida e confiável.

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

# Boas práticas

- pipeline é a única forma de deploy
- manter o pipeline o mais rápido possível - otimize-o
- build no ínicio e apenas uma vez
- build independente do ambiente
- ambiente iguais / semelhantes ao de produção
- ambientes efêmeros (temporários)
- deploy para ambientes de maneira igual

# Pipeline de implantação

```Unit Test --> Aceitação Automatizada --> Homologação --> Produção```

- As etapas existem de forma a receber feedback o mais rápido possível

# Commit Stage

- deve iniciar a cada commit e executar rápido (menos de 10 minutos)
- build: Primeiro passo é buildar a aplicação
- testes unitários e de integração: logo após o build é rodado os testes, pois são mais rápidos (feedback)
- análise de qualidade de código: são gerados relatórios. Podem ser executados em paralelo aos testes de unidade
- após o build e os testes passarem, tem-se:
  - plano de testes pela qualidade
  - relatório de qualidade
  - um artefato do build (jar, docker, gem, zip..)

# Teste de aceitação automatizados (AAT)

- foca em testes funcionais, que testam o sistema todo, por isso são mais caros de escrever e manter
- inicia após o commit stage e é mais demorado
