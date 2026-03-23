# Documentação Completa do GitHub CLI (gh)

## Introdução

O GitHub CLI (gh) é uma ferramenta de linha de comando que permite interagir com o GitHub diretamente do terminal. Ele facilita tarefas como criar repositórios, gerenciar issues, pull requests, gists e muito mais, sem precisar abrir o navegador.

Esta documentação cobre a instalação, autenticação, uso básico e todos os comandos disponíveis no GitHub CLI.

## Instalação

### Windows
Baixe o instalador MSI do [site oficial](https://cli.github.com/) ou use o winget:
```
winget install --id GitHub.cli
```

### macOS
Use o Homebrew:
```
brew install gh
```

### Linux
Use o gerenciador de pacotes da sua distribuição. Por exemplo, no Ubuntu:
```
sudo apt update
sudo apt install gh
```

Ou baixe o binário diretamente do [site oficial](https://cli.github.com/).

Verifique a instalação:
```
gh --version
```

## Autenticação

Antes de usar o gh, você precisa se autenticar com sua conta do GitHub.

Execute:
```
gh auth login
```

Isso abrirá um navegador para você fazer login. Alternativamente, use um token pessoal:
```
gh auth login --with-token <TOKEN>
```

Para sair:
```
gh auth logout
```

## Uso Básico

O comando geral é `gh <comando> <subcomando> [opções]`.

Para ver ajuda:
```
gh --help
```

Para ajuda de um comando específico:
```
gh <comando> --help
```

## Comandos Principais

### Autenticação (auth)

- `gh auth login`: Faz login no GitHub.
- `gh auth logout`: Faz logout.
- `gh auth refresh`: Atualiza a autenticação.
- `gh auth setup-git`: Configura o Git para usar credenciais do GitHub.
- `gh auth status`: Mostra o status da autenticação.
- `gh auth token`: Exibe o token de autenticação atual.

### Repositórios (repo)

- `gh repo clone <repo>`: Clona um repositório.
- `gh repo create <nome>`: Cria um novo repositório.
- `gh repo delete <repo>`: Deleta um repositório (requer confirmação).
- `gh repo edit <repo>`: Edita configurações do repositório.
- `gh repo fork <repo>`: Faz fork de um repositório.
- `gh repo list`: Lista repositórios do usuário ou organização.
- `gh repo rename <novo-nome>`: Renomeia um repositório.
- `gh repo sync`: Sincroniza um fork com o repositório upstream.
- `gh repo view <repo>`: Visualiza detalhes do repositório no navegador.

### Issues (issue)

- `gh issue create`: Cria uma nova issue.
- `gh issue close <número>`: Fecha uma issue.
- `gh issue comment <número>`: Adiciona um comentário a uma issue.
- `gh issue delete <número>`: Deleta uma issue.
- `gh issue edit <número>`: Edita uma issue.
- `gh issue list`: Lista issues do repositório.
- `gh issue reopen <número>`: Reabre uma issue.
- `gh issue status`: Mostra status das issues.
- `gh issue transfer <número> <repo>`: Transfere uma issue para outro repositório.
- `gh issue view <número>`: Visualiza uma issue.

### Pull Requests (pr)

- `gh pr create`: Cria um novo pull request.
- `gh pr close <número>`: Fecha um pull request.
- `gh pr comment <número>`: Adiciona um comentário a um pull request.
- `gh pr diff <número>`: Mostra o diff do pull request.
- `gh pr edit <número>`: Edita um pull request.
- `gh pr list`: Lista pull requests.
- `gh pr merge <número>`: Mescla um pull request.
- `gh pr ready <número>`: Marca um pull request como pronto para review.
- `gh pr reopen <número>`: Reabre um pull request.
- `gh pr review <número>`: Faz review de um pull request.
- `gh pr status`: Mostra status dos pull requests.
- `gh pr view <número>`: Visualiza um pull request.

### Gists (gist)

- `gh gist clone <id>`: Clona um gist.
- `gh gist create <arquivos>`: Cria um novo gist.
- `gh gist delete <id>`: Deleta um gist.
- `gh gist edit <id>`: Edita um gist.
- `gh gist list`: Lista gists do usuário.
- `gh gist view <id>`: Visualiza um gist.

### Releases (release)

- `gh release create <tag>`: Cria uma nova release.
- `gh release delete <tag>`: Deleta uma release.
- `gh release download <tag>`: Baixa assets de uma release.
- `gh release edit <tag>`: Edita uma release.
- `gh release list`: Lista releases.
- `gh release upload <tag> <arquivos>`: Faz upload de assets para uma release.
- `gh release view <tag>`: Visualiza uma release.

### Workflows (workflow)

- `gh workflow list`: Lista workflows do repositório.
- `gh workflow run <id>`: Executa um workflow.
- `gh workflow view <id>`: Visualiza um workflow.

### Run (para Actions)

- `gh run list`: Lista execuções de workflows.
- `gh run view <id>`: Visualiza uma execução.
- `gh run watch <id>`: Observa uma execução em tempo real.
- `gh run download <id>`: Baixa artifacts de uma execução.
- `gh run rerun <id>`: Reexecuta uma execução.

### Codespaces

- `gh codespace create`: Cria um codespace.
- `gh codespace delete <nome>`: Deleta um codespace.
- `gh codespace list`: Lista codespaces.
- `gh codespace logs <nome>`: Mostra logs de um codespace.
- `gh codespace ssh <nome>`: Conecta via SSH a um codespace.
- `gh codespace stop <nome>`: Para um codespace.

### Outros Comandos

- `gh alias`: Gerencia aliases para comandos.
- `gh api <endpoint>`: Faz chamadas diretas para a API do GitHub.
- `gh browse`: Abre o repositório no navegador.
- `gh config`: Gerencia configurações.
- `gh extension`: Gerencia extensões.
- `gh label`: Gerencia labels (issues/PRs).
- `gh search`: Busca repositórios, issues, etc.
- `gh secret`: Gerencia secrets (para Actions).
- `gh ssh-key`: Gerencia chaves SSH.
- `gh variable`: Gerencia variáveis (para Actions).

## Exemplos de Uso

### Criar um repositório
```
gh repo create meu-projeto --public --description "Meu novo projeto"
```

### Criar uma issue
```
gh issue create --title "Bug encontrado" --body "Descrição do bug"
```

### Criar um pull request
```
gh pr create --title "Nova feature" --body "Descrição da feature"
```

### Listar issues abertas
```
gh issue list --state open
```

### Mesclar um pull request
```
gh pr merge 123 --merge
```

## Configuração

Use `gh config` para definir preferências:
- `gh config set editor vim`: Define o editor padrão.
- `gh config set git_protocol ssh`: Define o protocolo Git.

## Extensões

O GitHub CLI suporta extensões para funcionalidades adicionais. Instale com:
```
gh extension install <nome-da-extensao>
```

Liste extensões: `gh extension list`

## Dicas e Truques

- Use `--help` em qualquer comando para mais detalhes.
- Combine com Git: `gh pr create` detecta automaticamente a branch atual.
- Use aliases: `gh alias set co 'pr checkout'` para criar atalhos.
- Para automação, use tokens em CI/CD.

## Recursos Adicionais

- [Documentação Oficial](https://cli.github.com/manual/)
- [GitHub CLI no GitHub](https://github.com/cli/cli)
- Comunidade: Issues e discussões no repositório oficial.

Esta documentação é baseada na versão mais recente do GitHub CLI. Verifique `gh --version` para confirmar.