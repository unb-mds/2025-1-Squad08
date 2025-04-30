# Guia Básico de Estudo sobre Git

Este guia cobre os conceitos e comandos fundamentais do Git para controle de versão.

## O que é Git?

Git é um sistema de controle de versão distribuído, gratuito e de código aberto, projetado para lidar com tudo, desde projetos pequenos a muito grandes, com velocidade e eficiência. Ele permite que múltiplos desenvolvedores trabalhem juntos no mesmo projeto sem sobrescrever o trabalho uns dos outros.

## Configuração Inicial

Antes de começar, configure seu nome de usuário e email no Git. Isso será usado para identificar seus commits.

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```

## Comandos Essenciais

1.  **`git init`**: Inicializa um novo repositório Git em um diretório existente. Cria uma subpasta oculta `.git` que contém todos os metadados necessários.
    ```bash
    # Navegue até a pasta do seu projeto
    cd meu-projeto
    git init
    ```

2.  **`git clone <url>`**: Cria uma cópia local de um repositório remoto existente.
    ```bash
    git clone https://github.com/usuario/repositorio.git
    ```

3.  **`git status`**: Mostra o estado atual do diretório de trabalho e da área de staging (arquivos modificados, adicionados, não rastreados).
    ```bash
    git status
    ```

4.  **`git add <arquivo>`** ou **`git add .`**: Adiciona alterações do diretório de trabalho para a área de staging (index). O `.` adiciona todos os arquivos modificados e novos.
    ```bash
    # Adiciona um arquivo específico
    git add README.md
    
    # Adiciona todos os arquivos modificados/novos no diretório atual e subdiretórios
    git add .
    ```

5.  **`git commit -m "<mensagem>"`**: Grava as alterações que estão na área de staging permanentemente no histórico do repositório, com uma mensagem descritiva.
    *   **Importante:** Use [Conventional Commits](https://www.conventionalcommits.org/) para mensagens claras e padronizadas (veja o guia específico do projeto).
    ```bash
    git commit -m "feat: adicionar funcionalidade de login"
    ```

6.  **`git log`**: Mostra o histórico de commits do branch atual, do mais recente para o mais antigo.
    ```bash
    git log
    # Para um log mais conciso
    git log --oneline --graph --decorate
    ```

7.  **`git branch`**: Lista todos os branches locais. Com um nome, cria um novo branch.
    ```bash
    # Listar branches
    git branch
    
    # Criar um novo branch chamado 'nova-feature'
    git branch nova-feature
    ```

8.  **`git checkout <nome-do-branch>`** ou **`git switch <nome-do-branch>`**: Muda para o branch especificado.
    ```bash
    git checkout nova-feature
    # Ou o comando mais moderno:
    git switch nova-feature
    
    # Para criar e mudar para um novo branch de uma vez:
    git checkout -b outra-feature
    # Ou:
    git switch -c outra-feature
    ```

9.  **`git merge <nome-do-branch>`**: Combina o histórico do branch especificado com o branch atual.
    ```bash
    # Estando no branch 'main', para mesclar 'nova-feature':
    git switch main
    git merge nova-feature
    ```

10. **`git remote -v`**: Lista os repositórios remotos configurados.
    ```bash
    git remote -v
    ```

11. **`git push <remoto> <branch>`**: Envia os commits do branch local para o repositório remoto.
    ```bash
    # Enviar o branch 'main' para o remoto 'origin'
    git push origin main
    
    # Enviar um novo branch 'nova-feature' para 'origin'
    git push origin nova-feature
    ```

12. **`git pull <remoto> <branch>`**: Busca as alterações do repositório remoto e as mescla no branch local atual. É um atalho para `git fetch` seguido de `git merge`.
    ```bash
    # Atualizar o branch 'main' local com as mudanças do 'origin/main'
    git pull origin main
    ```

## Fluxo Básico

1.  Atualize seu repositório local: `git pull origin main` (ou o nome do seu branch principal).
2.  Crie um novo branch para sua tarefa: `git switch -c <nome-do-branch>`.
3.  Faça suas alterações no código.
4.  Adicione as alterações à área de staging: `git add .`
5.  Faça o commit das alterações com uma mensagem clara: `git commit -m "<tipo>(<escopo>): <descrição>"`.
6.  Envie seu branch para o repositório remoto: `git push origin <nome-do-branch>`.
7.  Abra um Pull Request no GitHub.

Este guia é apenas uma introdução. O Git é uma ferramenta poderosa com muitos outros recursos. Consulte a [documentação oficial do Git](https://git-scm.com/doc) para aprender mais.
