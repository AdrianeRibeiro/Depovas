# Integração Contínua (CI)

- Significa integrar as alterações no mainline (master ou trunk) diariamente. Isso é feito utilizando um sistema de controle de versão (VCS)

- Com a Integração Contínua, diminui os problemas de integração (como merge hell), melhora a comunicação entre desenvolvedores e antecipa a descoberta de bugs

- Commits nas master todos os dias

- Visa diminuir o risco no desenvolvimento de software

<br>

# Sistema de controle de versão

- Ferramenta não importa

- Commita tudo necessário para a construção do projeto
  - código
  - script
  - migrações, schemas
  - IDE configs

- Não commita o que pode ser construído (gem, jar, image, modules)

<br>

# Organização dos repositórios

- Multi-repo: cada projeto tem seu repositório
  - vantagem: definir permissão por projeto; clone, commits e build do projeto simples e rápido

- Mono-repo: um único repositório com todos os projetos
  - desvantagem: repositório muito grande
  - vantagem: administração pode ser mais fácil

<br>

# Boas práticas

- Commits simples e lançáveis, orientados às tarefas

- Branches atrasam a integração, seguram o código

- Branches de vida curta -> merges mais simples

- Muitas branches -> mais burocracia

<br>

# Branching Models

- Temporários (branches locais)

- Feature branches

- Historical branches (Master e develop)

- Environment branches (Staging e production)

- Maintenance branches (Release e hotfix)

<br>

# Testes automatizados

- As integrações do novo código no repositório precisam ser verificadas o tempo todo. Isso só é possível com uma bateria de testes, executadas de maneira automatizada. É isso que vai garantir a corretude do código.

- Fazem parte da construção

- Rodar antes do commit
  - se não for viável, rodar os testes dos arquivos impactados ou essenciais do sistema

- TDD pode ajudar, porém não é essencial

- Desempenho (tempo para rodar os testes) importa

- Tipos de testes: unidade, integração e funcional 

<br>

# Builds automatizados

- Build a cada commit

- Tudo automatizado / single comando

- Build sem depender da IDE

- Tudo está no repositório

<br>

# Build contínuo

- Deve ser feito no servidor de integração contínua a cada commit

- Se o build não passar, corrigir os builds quebrados imediatamente (prioridade do time)

<br>

# Servidor de Integração Contínua

- Monitora o repositório do código

  - Ao detectar uma alteração deve iniciar o build do projeto
  - O build deve acontecer a cada novo commit
  - O resultado do build deve ser publicado
  - Os desenvolvedores devem ser notificados sobre o status do build
