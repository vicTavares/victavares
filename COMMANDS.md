# 📚 Comandos Git - Guia de Referência Rápida

Abaixo estão os principais comandos do Git organizados em duas colunas para facilitar a leitura e consulta.

| Comando Git | Descrição |
|-------------|---------|
| `git init` | Inicia um novo repositório Git na pasta atual. |
| `git clone <URL>` | Baixa um repositório remoto para o seu computador. |
| `git branch` | Lista todas as branches locais (a atual tem `*`). |
| `git branch <nome>` | Cria uma nova branch com o nome especificado. |
| `git checkout <nome>` | Muda para a branch especificada. |
| `git checkout -b <nome>` | Cria uma nova branch e muda para ela. |
| `git switch <nome>` | Muda para a branch especificada (forma moderna). |
| `git switch -c <nome>` | Cria uma nova branch e muda para ela (moderno). |
| `git status` | Mostra o estado dos arquivos (modificados, novos, etc.). |
| `git add <arquivo>` | Adiciona um arquivo específico ao staging. |
| `git add .` | Adiciona todos os arquivos modificados ao staging. |
| `git commit -m "mensagem"` | Salva as alterações com uma mensagem descritiva. |
| `git commit --amend -m "nova"` | Edita a mensagem do último commit (não enviado). |
| `git reset HEAD~1` | Desfaz o último commit, mantendo as alterações no staging. |
| `git reset --hard HEAD~1` | Apaga o último commit e todas as alterações (cuidado!). |
| `git push` | Envia os commits locais para o repositório remoto. |
| `git push -u origin <branch>` | Envia uma nova branch e define o rastreamento. |
| `git pull` | Baixa e mescla as últimas alterações do repositório remoto. |
| `git merge <branch>` | Mescla o conteúdo de outra branch na atual. |
| `git log` | Mostra o histórico completo de commits. |
| `git log --oneline` | Mostra o histórico de commits de forma resumida. |
| `git diff` | Mostra as diferenças nos arquivos não adicionados ao staging. |
| `git diff --staged` | Mostra as diferenças nos arquivos já adicionados (staging). |
| `git remote -v` | Mostra a URL do repositório remoto. |
| `git fetch` | Baixa informações de alterações remotas sem mesclar. |
| `git tag v1.0.0` | Cria uma tag para marcar uma versão (ex: v1.0.0). |
| `git push --tags` | Envia as tags locais para o repositório remoto. |
| `git stash` | Guarda alterações temporariamente sem commit. |
| `git stash pop` | Recupera as alterações guardadas com stash. |
| `git config --global user.name "Nome"` | Define seu nome global para commits. |
| `git config --global user.email "email"` | Define seu e-mail global para commits. |




#############################



| Comando Git | Descrição |
|-------------|---------|
| `git --version` | Verifica se o Git está instalado. |
| `git config --global user.name "nome"` | Define o nome do usuário para o Git. |
| `git config --global user.email "email"` | Define o email do usuário para o Git. |
| `git clone https://git.prodam.am.gov.br/vicente.tavares.git` | Clona o repositório remoto para o computador. |
| `cd vicente.tavares` | Navega para a pasta do repositório clonado. |
| `code .` | Abre a pasta do repositório no Visual Studio Code. |
| `git config --global credential.helper cache` | Armazena temporariamente as credenciais de autenticação. |
| `git config --global credential.helper store` | Salva as credenciais permanentemente (opcional). |
| `git add .` | Adiciona todas as alterações para o commit. |
| `git commit -m "Descrição das alterações"` | Salva as alterações localmente com uma mensagem. |
| `git push origin main` | Envia as alterações para a branch main do repositório remoto. |
| `git pull origin main` | Sincroniza o repositório local com as alterações remotas. |
| `---` | -------------- |
| `git remote add  "origin" (rep. remoto principal)  url` |  estabelecer conexão entre seu repositório local e um repositório remoto. |
| `git remote remove origin` | Rmove um repositorio. |
| `git remote rename origin novo-origin` | Renomeia um repositorio remoto. |






# Git Glossary

The following table provides definitions for common Git and version control terms.

<table style="width: 100%; border-collapse: collapse;">
  <thead>
    <tr style="background-color: #f2f2f2; font-weight: bold;">
      <th style="border: 1px solid #ddd; padding: 8px; text-align: left;">Term</th>
      <th style="border: 1px solid #ddd; padding: 8px; text-align: left;">Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">Branch</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A separate line of development that allows to work on features or fixes independently.</td>
    </tr>
    <tr style="background-color: #e6f3ff;">
      <td style="border: 1px solid #ddd; padding: 8px;">Clone</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A local copy of the remote Git repository on the computer.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">Commit</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A snapshot of the project's current state at a specific point in time, along with a description of the changes made.</td>
    </tr>
    <tr style="background-color: #e6f3ff;">
      <td style="border: 1px solid #ddd; padding: 8px;">Continuous delivery (CD)</td>
      <td style="border: 1px solid #ddd; padding: 8px;">The automated movement of software through the software development lifecycle.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">Continuous integration (CI)</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A software development process in which developers integrate new code into the code base at least once a day.</td>
    </tr>
    <tr style="background-color: #e6f3ff;">
      <td style="border: 1px solid #ddd; padding: 8px;">Distributed version control system (DVCS)</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A system that keeps track of changes to code, regardless of where it is stored. Multiple users work on the same codebase or repository, mirroring the codebase on their computers if needed, while the distributed version control software helps manage synchronization amongst the various codebase mirrors.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">Fork</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A copy of a repository into your GitHub account.</td>
    </tr>
    <tr style="background-color: #e6f3ff;">
      <td style="border: 1px solid #ddd; padding: 8px;">GitHub</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A web-hosted service for the Git repository.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">GitHub branches</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A branch stores all files in GitHub. Branches are used to isolate changes to code. When the changes are complete, they can be merged back into the main branch.</td>
    </tr>
    <tr style="background-color: #e6f3ff;">
      <td style="border: 1px solid #ddd; padding: 8px;">GitLab</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A complete DevOps platform delivered as a single application. It provides access to Git repositories, controlled by source code management.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">Git</td>
      <td style="border: 1px solid #ddd; padding: 8px;">Free and open-source software distributed under the GNU General Public License. It is a distributed version control system that allows users to have a copy of their own project on their computer anywhere in the world.</td>
    </tr>
    <tr style="background-color: #e6f3ff;">
      <td style="border: 1px solid #ddd; padding: 8px;">Merge</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A process to combine changes from one branch to another, typically merging a feature branch into the main branch.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">Pull request</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A process used to request that someone review and approve your changes before they become final.</td>
    </tr>
    <tr style="background-color: #e6f3ff;">
      <td style="border: 1px solid #ddd; padding: 8px;">Repository</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A data structure for storing documents, including application source code. It contains the project folders that are set up for version control.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">SSH Protocol</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A method for secure remote login from one computer to another.</td>
    </tr>
    <tr style="background-color: #e6f3ff;">
      <td style="border: 1px solid #ddd; padding: 8px;">Version control</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A system that allows you to keep track of changes to your documents. This process allows you to recover older versions of the documents if any mistakes are made.</td>
    </tr>
    <tr style="background-color: #f9f9f9;">
      <td style="border: 1px solid #ddd; padding: 8px;">Working directory</td>
      <td style="border: 1px solid #ddd; padding: 8px;">A directory in your file system that contains files and subdirectories on your computer that are associated with a Git repository.</td>
    </tr>
  </tbody>
</table>










