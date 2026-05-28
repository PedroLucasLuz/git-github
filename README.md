# Guia Completo de Git e GitHub

Um guia completo sobre Git e GitHub, cobrindo desde os conceitos básicos até fluxos de trabalho profissionais utilizados no mercado.

---

# Sumário

1. Introdução ao Git
2. Controle de Versão
3. Instalação do Git
4. Configuração Inicial
5. Criando Repositórios
6. Estados dos Arquivos
7. Principais Comandos
8. Trabalhando com Commits
9. Histórico e Logs
10. Branches
11. Merge
12. Rebase
13. GitHub
14. Clonando Repositórios
15. Trabalhando com Repositórios Remotos
16. Pull Requests
17. Resolução de Conflitos
18. Git Ignore
19. Tags e Versionamento
20. Git Stash
21. Git Reset
22. Git Revert
23. Boas Práticas
24. Fluxos de Trabalho Profissionais
25. Git Flow
26. Conventional Commits
27. SSH no GitHub
28. Dicas Avançadas
29. Troubleshooting
30. Cheatsheet
31. Fluxo Completo de Trabalho
32. Glossário
33. Próximos Passos
34. Conclusão
35. Recursos Extras

---

# 1. Introdução ao Git

Git é um sistema de controle de versão distribuído criado por Linus Torvalds.

Ele permite:

* Controlar alterações em arquivos
* Trabalhar em equipe
* Restaurar versões anteriores
* Criar funcionalidades isoladas através de branches
* Integrar código com segurança
* Manter histórico completo do projeto

---

# 2. Controle de Versão

Controle de versão é um sistema responsável por registrar alterações em arquivos ao longo do tempo.

Sem um sistema de versionamento, é comum encontrar situações como:

```txt id="jlwm0y"
projeto-final.zip
projeto-final-agora-vai.zip
projeto-final-definitivo.zip
```

Com Git:

```bash id="8s8p0s"
git commit -m "Adiciona sistema de login"
```

Cada alteração fica registrada no histórico do projeto.

---

# 3. Instalação do Git

## Windows

Download oficial:

```txt id="k8yv98"
https://git-scm.com/download/win
```

## Linux

Ubuntu/Debian:

```bash id="7hlhsp"
sudo apt update
sudo apt install git
```

Fedora:

```bash id="o1ubsv"
sudo dnf install git
```

## macOS

```bash id="6wyy7r"
brew install git
```

---

# 4. Configuração Inicial

Defina seu nome e email:

```bash id="5b4hhi"
git config --global user.name "Seu Nome"
git config --global user.email "email@exemplo.com"
```

Verificar configurações:

```bash id="8kc2ha"
git config --list
```

---

# 5. Criando Repositórios

Inicializar um repositório Git:

```bash id="cy9i5f"
git init
```

O comando cria a pasta oculta:

```txt id="vafszn"
.git/
```

Ela contém todo o histórico e configuração do repositório.

---

# 6. Estados dos Arquivos

| Estado    | Descrição                     |
| --------- | ----------------------------- |
| Untracked | Arquivo ainda não monitorado  |
| Modified  | Arquivo alterado              |
| Staged    | Arquivo preparado para commit |
| Committed | Alteração salva no histórico  |

---

# 7. Principais Comandos

## Verificar status

```bash id="udbgxp"
git status
```

## Adicionar arquivos

Arquivo específico:

```bash id="k8nqj8"
git add arquivo.txt
```

Todos os arquivos:

```bash id="z4b3w4"
git add .
```

## Criar commit

```bash id="jql92e"
git commit -m "Mensagem do commit"
```

---

# 8. Trabalhando com Commits

Commits representam snapshots do projeto em determinado momento.

Exemplo:

```bash id="hbb2gh"
git commit -m "Corrige bug no login"
```

Boas práticas:

* Criar commits pequenos
* Utilizar mensagens claras
* Manter um único objetivo por commit

---

# 9. Histórico e Logs

Visualizar histórico completo:

```bash id="kxzbzh"
git log
```

Histórico resumido:

```bash id="g6yl0y"
git log --oneline
```

Histórico gráfico:

```bash id="74n4ks"
git log --graph --all --decorate
```

---

# 10. Branches

Branches permitem desenvolver funcionalidades isoladas sem afetar a branch principal.

Criar e trocar para uma nova branch:

```bash id="u2ib7m"
git switch -c nova-feature
```

Trocar de branch:

```bash id="h7g6rq"
git switch main
```

Listar branches:

```bash id="ccvj6u"
git branch
```

Remover branch:

```bash id="fjg6yy"
git branch -d nome-branch
```

---

# 11. Merge

Merge une alterações entre branches.

```bash id="67frb7"
git switch main
git merge nova-feature
```

---

# 12. Rebase

Rebase reorganiza commits mantendo um histórico linear.

```bash id="8d0jvn"
git switch feature
git rebase main
```

Diferença principal:

* Merge cria commit de merge
* Rebase reorganiza o histórico

---

# 13. GitHub

GitHub é uma plataforma de hospedagem de repositórios Git.

Principais funcionalidades:

* Hospedagem de código
* Pull Requests
* Issues
* Actions
* CI/CD
* Colaboração em equipe

---

# 14. Clonando Repositórios

```bash id="8g1l0n"
git clone URL
```

Exemplo:

```bash id="c1hr8y"
git clone https://github.com/user/projeto.git
```

---

# 15. Trabalhando com Remotos

Adicionar repositório remoto:

```bash id="m9hjfa"
git remote add origin URL
```

Enviar alterações:

```bash id="ej4bgb"
git push origin main
```

Baixar alterações:

```bash id="6fdlfh"
git pull origin main
```

---

# 16. Pull Requests

Pull Requests são solicitações de integração de código.

Fluxo comum:

```txt id="h4ch3n"
Branch → Commit → Push → Pull Request → Review → Merge
```

---

# 17. Resolução de Conflitos

Conflitos ocorrem quando duas alterações modificam a mesma parte do código.

Exemplo:

```txt id="6nt64j"
<<<<<<< HEAD
console.log("A")
=======
console.log("B")
>>>>>>> feature
```

Passos para resolver:

1. Editar manualmente
2. Remover marcações
3. Criar novo commit

---

# 18. Git Ignore

O arquivo `.gitignore` define arquivos que não devem ser versionados.

Exemplo:

```txt id="32ivdh"
node_modules/
.env
dist/
```

---

# 19. Tags e Versionamento

Criar tag:

```bash id="5qvg4u"
git tag v1.0.0
```

Enviar tags:

```bash id="8bclm2"
git push origin --tags
```

---

# 20. Git Stash

Salvar alterações temporariamente:

```bash id="6rk4pn"
git stash
```

Recuperar alterações:

```bash id="moc6mr"
git stash pop
```

---

# 21. Git Reset

Soft reset:

```bash id="l32kll"
git reset --soft HEAD~1
```

Hard reset:

```bash id="ub2c0n"
git reset --hard HEAD~1
```

---

# 22. Git Revert

Desfaz commits preservando histórico:

```bash id="x4r7mb"
git revert HASH
```

---

# 23. Boas Práticas

* Fazer commits pequenos
* Nomear branches corretamente
* Atualizar branches frequentemente
* Revisar código antes de merge
* Utilizar `.gitignore`
* Padronizar commits

---

# 24. Fluxos de Trabalho Profissionais

## GitHub Flow

```txt id="y2f70u"
main → feature → Pull Request → merge
```

## Git Flow

```txt id="ixn0jl"
main
develop
feature/*
hotfix/*
release/*
```

---

# 25. Git Flow

Inicializar Git Flow:

```bash id="5iqmnu"
git flow init
```

---

# 26. Conventional Commits

| Prefixo  | Uso                 |
| -------- | ------------------- |
| feat     | Nova funcionalidade |
| fix      | Correção            |
| docs     | Documentação        |
| refactor | Refatoração         |
| test     | Testes              |
| chore    | Manutenção          |

Exemplo:

```txt id="3shjlwm"
feat(auth): adiciona login JWT
```

---

# 27. SSH no GitHub

Gerar chave SSH:

```bash id="j5o6y8"
ssh-keygen -t ed25519 -C "email@exemplo.com"
```

Adicionar chave ao agente SSH:

```bash id="0u7yyt"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

---

# 28. Dicas Avançadas

Ver diferenças:

```bash id="twl40f"
git diff
```

Alterar último commit:

```bash id="s8g8lf"
git commit --amend
```

Remover arquivo do stage:

```bash id="7emv90"
git restore --staged arquivo.txt
```

---

# 29. Troubleshooting

Abortar merge:

```bash id="0ylwjr"
git merge --abort
```

Descartar alterações locais:

```bash id="cl54jk"
git restore .
```

Remover arquivos não rastreados:

```bash id="v5r86s"
git clean -fd
```

---

# 30. Cheatsheet

```bash id="2s3n5l"
git init
git clone URL
git status
git add .
git commit -m "msg"
git push
git pull
git switch -c feature
git merge feature
git log
git diff
git reset
git revert
```

---

# 31. Fluxo Completo de Trabalho

```bash id="2l2t35"
git switch -c nova-feature

# editar arquivos

git add .
git commit -m "feat: nova funcionalidade"

git push origin nova-feature
```

Fluxo final:

1. Criar Pull Request
2. Revisar código
3. Realizar merge

---

# 32. Glossário

| Termo  | Significado                       |
| ------ | --------------------------------- |
| Commit | Snapshot do código                |
| Branch | Linha paralela de desenvolvimento |
| Merge  | União de branches                 |
| Rebase | Reorganização do histórico        |
| Remote | Repositório remoto                |
| Clone  | Cópia do repositório              |
| Pull   | Baixar alterações                 |
| Push   | Enviar alterações                 |

---

# 33. Próximos Passos

Após dominar Git e GitHub:

* GitHub Actions
* CI/CD
* Docker
* Kubernetes
* Open Source

---

# 34. Conclusão

Git é uma das ferramentas mais importantes do desenvolvimento moderno.

Dominar Git permite:

* Trabalhar em equipe
* Versionar projetos corretamente
* Evitar perda de código
* Manter histórico confiável
* Trabalhar em projetos profissionais

---

# 35. Recursos Extras

Documentação oficial:

```txt id="tnm3gi"
https://git-scm.com/doc
```

GitHub Docs:

```txt id="55qlxk"
https://docs.github.com/
```

Aprender Git interativamente:

```txt id="bg7j0c"
https://learngitbranching.js.org/
```
