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











