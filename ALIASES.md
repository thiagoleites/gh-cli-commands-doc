# ⚙️ Setup de Aliases Git + GitHub CLI (Bash/Zsh)

Este documento define um conjunto de **aliases personalizados** para acelerar o fluxo de trabalho com **Git + GitHub CLI (gh)** no terminal.

---

## 🚀 Objetivo

Facilitar operações comuns como:

* Criar branches
* Fazer commits
* Enviar código (push)
* Criar repositórios

Tudo com comandos curtos e rápidos.

---

## 📌 Instalação

### 1. Abrir arquivo de configuração

**Bash:**

```bash
nano ~/.bashrc
```

**Zsh:**

```bash
nano ~/.zshrc
```

---

### 2. Adicionar os aliases

Cole o conteúdo abaixo no final do arquivo:

```bash
# 🌿 Criar e trocar para uma nova branch
alias criar-branch='f(){ git checkout -b "$1"; }; f'

# 💾 Adicionar tudo e commitar com mensagem
alias commitar='f(){ git add . && git commit -m "$1"; }; f'

# 🚀 Push da branch atual
alias gh-push='git push origin $(git branch --show-current)'

# 🔥 Commit + push em um comando
alias save='f(){ git add . && git commit -m "$1" && git push origin $(git branch --show-current); }; f'

# 🌍 Criar repositório no GitHub e subir código
alias gh-init='f(){ git init && gh repo create "$1" --public --source=. --remote=origin --push; }; f'

# 🔄 Atualizar repositório (pull)
alias atualizar='git pull origin $(git branch --show-current)'

# 📊 Status rápido
alias gs='git status'

# 🌱 Listar branches
alias gb='git branch'

# ⚡ Commit automático com data/hora
alias quicksave='git add . && git commit -m "auto-save $(date)" && git push'
```

---

### 3. Aplicar alterações

```bash
source ~/.bashrc
```

ou

```bash
source ~/.zshrc
```

---

## 🧠 Como usar

### 🌿 Criar branch

```bash
criar-branch feature/login
```

---

### 💾 Commit

```bash
commitar "ajuste no sistema"
```

---

### 🚀 Push

```bash
gh-push
```

---

### 🔥 Commit + Push

```bash
save "nova funcionalidade"
```

---

### 🌍 Criar repositório e subir projeto

```bash
gh-init meu-projeto
```

---

### 🔄 Atualizar projeto

```bash
atualizar
```

---

### 📊 Ver status

```bash
gs
```

---

## ⚠️ Boas práticas

* Sempre revise antes de commitar:

```bash
git status
```

* Use mensagens de commit claras:

```bash
save "corrige bug no login"
```

* Evite commits muito grandes (prefira pequenos e frequentes)

---

## 💡 Dicas

* O comando `save` é o mais usado no dia a dia
* `criar-branch` ajuda a manter organização do projeto
* `gh-init` é ótimo para iniciar projetos rapidamente

---

## 🏁 Conclusão

Esses aliases tornam o fluxo de trabalho:

* ⚡ Mais rápido
* 🧼 Mais organizado
* 🚀 Mais produtivo

Recomendado para uso diário em qualquer projeto com Git e GitHub CLI.

---
