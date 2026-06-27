# Roteiro de Comandos — Repositório Modelo da Atividade Gitflow

> **Objetivo:** O professor executa todos os comandos abaixo para construir um repositório modelo funcional que demonstra o fluxo completo da atividade (Aula 2 — Atividade Prática Gitflow).
>
> **Pré-requisitos:** Git instalado, conta no GitHub, terminal aberto.
>
> Para simular os diferentes alunos, o professor pode usar `git config` local ou simplesmente indicar nos commits quem está agindo. Abaixo, cada bloco identifica **quem** executa o comando.

---

## 📁 PASSO 1 — Configuração Inicial (LÍDER / Aluno A)

```bash
# Criar a pasta do projeto e entrar nela
mkdir manual-sobrevivencia
cd manual-sobrevivencia

# Iniciar o repositório Git
git init

# Criar o arquivo guia.md com o título principal
echo "# Manual de Sobrevivência do 1º Ano Técnico" > guia.md

# Adicionar e fazer o primeiro commit
git add guia.md
git commit -m "chore: commit inicial do manual"

# Criar o repositório no GitHub (usando GitHub CLI — gh)
# Se não tiver o gh instalado, crie manualmente no site e copie a URL
gh repo create manual-sobrevivencia --public --source=. --remote=origin

# Enviar para o GitHub
git push -u origin main
```

> **Nota:** Se não usar `gh`, crie o repositório no GitHub manualmente e execute:
> ```bash
> git remote add origin https://github.com/SEU_USUARIO/manual-sobrevivencia.git
> git push -u origin main
> ```

---

## 🌿 PASSO 2 — Criação da Branch develop (LÍDER / Aluno A)

```bash
# Criar e mudar para a branch develop
git checkout -b develop

# Enviar a branch develop para o GitHub
git push -u origin develop
```

---

## 🚀 PASSO 3 — Simulação do Aluno A (Líder) escrevendo o Capítulo 1

```bash
# Já está na develop, criar a feature branch
git checkout -b feature/dicas-prazos
```

Editar o arquivo `guia.md` — adicionar o conteúdo do Capítulo 1:

```markdown
## Capítulo 1: Dicas para não esquecer os prazos das tarefas

- Use um aplicativo de agenda (Google Calendar, Notion) para registrar prazos.
- Anote tudo no caderno assim que o professor falar a data de entrega.
- Coloque alarmes no celular 2 dias antes de cada prova ou trabalho.
```

```bash
# Verificar status, adicionar e commitar
git status
git add guia.md
git commit -m "feat: adicionado capitulo 1 - dicas de prazos"

# Enviar a feature branch
git push -u origin feature/dicas-prazos

# Simular o merge (Pull Request) para develop com --no-ff
git checkout develop
git merge --no-ff feature/dicas-prazos -m "Merge pull request: feature/dicas-prazos -> develop"
git push origin develop
```

---

## 🚀 PASSO 4 — Simulação do Aluno B escrevendo o Capítulo 2

```bash
# Voltar para develop e atualizar
git checkout develop
git pull origin develop

# Criar a feature branch do Aluno B
git checkout -b feature/mochila-aula-tecnica
```

Editar o arquivo `guia.md` — adicionar o conteúdo do Capítulo 2:

```markdown
## Capítulo 2: O que levar na mochila nos dias de aula técnica

- Pendrive ou HD externo para salvar projetos do laboratório.
- Fone de ouvido para assistir tutoriais sem atrapalhar os colegas.
- Caderno de anotações para rascunhar lógica antes de programar.
```

```bash
git status
git add guia.md
git commit --author="Aluno B <alunob@etec.sp.gov.br>" -m "feat: adicionado capitulo 2 - mochila aula tecnica"
git push -u origin feature/mochila-aula-tecnica

# Simular o merge (Pull Request) para develop
git checkout develop
git merge --no-ff feature/mochila-aula-tecnica -m "Merge pull request: feature/mochila-aula-tecnica -> develop"
git push origin develop
```

---

## 🚀 PASSO 5 — Simulação do Aluno C escrevendo o Capítulo 3

```bash
git checkout develop
git pull origin develop

git checkout -b feature/lanches-perto
```

Editar o arquivo `guia.md` — adicionar o conteúdo do Capítulo 3:

```markdown
## Capítulo 3: Onde encontrar os melhores salgados perto da escola

- Cantina da Dona Maria: coxinha por R$5,00 e pastel por R$4,50.
- Padaria do Zé (50m da escola): pão de queijo quentinho a R$3,00.
- Trailer do Carlos: misto quente grande por R$7,00 no intervalo.
```

```bash
git status
git add guia.md
git commit --author="Aluno C <alunoc@etec.sp.gov.br>" -m "feat: adicionado capitulo 3 - lanches perto da escola"
git push -u origin feature/lanches-perto

# Simular o merge (Pull Request) para develop
git checkout develop
git merge --no-ff feature/lanches-perto -m "Merge pull request: feature/lanches-perto -> develop"
git push origin develop
```

---

## 🚀 PASSO 6 — Simulação do Aluno D escrevendo o Capítulo 4

```bash
git checkout develop
git pull origin develop

git checkout -b feature/regras-trabalho-equipe
```

Editar o arquivo `guia.md` — adicionar o conteúdo do Capítulo 4:

```markdown
## Capítulo 4: Regras de ouro para trabalhar em equipe sem treta

- Divida as tarefas de forma justa logo no primeiro dia do trabalho.
- Use um grupo no WhatsApp só para avisos do projeto (sem memes!).
- Se alguém não fizer a parte, converse antes de reclamar pro professor.
```

```bash
git status
git add guia.md
git commit --author="Aluno D <alunod@etec.sp.gov.br>" -m "feat: adicionado capitulo 4 - regras de equipe"
git push -u origin feature/regras-trabalho-equipe

# Simular o merge (Pull Request) para develop
git checkout develop
git merge --no-ff feature/regras-trabalho-equipe -m "Merge pull request: feature/regras-trabalho-equipe -> develop"
git push origin develop
```

---

## 🏁 PASSO 7 — Publicação: Merge de develop para main (LÍDER / Aluno A)

```bash
# Ir para a main
git checkout main
git pull origin main

# Fazer o merge da develop (simula o PR de publicação)
git merge --no-ff develop -m "Merge pull request: develop -> main (publicação do manual completo)"

# Enviar para o GitHub
git push origin main
```

---

## 🚨 PASSO 8 — HOTFIX: Simulação da Correção de Emergência (LÍDER ou Aluno designado)

O professor anuncia: *"A cantina mudou de nome e o preço subiu!"*

```bash
# Garantir que está na main atualizada
git checkout main
git pull origin main

# Criar a branch de hotfix a partir da main
git checkout -b hotfix/ajuste-cantina
```

Editar o arquivo `guia.md` — corrigir o Capítulo 3:

> Alterar a linha:
> `- Cantina da Dona Maria: coxinha por R$5,00 e pastel por R$4,50.`
>
> Para:
> `- Cantina da Dona Ana: coxinha por R$6,50 e pastel por R$5,00.`

```bash
# Após salvar a edição:
git status
git add guia.md
git commit -m "fix: corrigido nome e valor do salgado na cantina"
git push -u origin hotfix/ajuste-cantina

# Merge do hotfix para a main (simula PR aprovado)
git checkout main
git merge --no-ff hotfix/ajuste-cantina -m "Merge pull request: hotfix/ajuste-cantina -> main"
git push origin main

# Atualizar a develop com o hotfix (manter tudo sincronizado)
git checkout develop
git merge --no-ff hotfix/ajuste-cantina -m "Merge hotfix/ajuste-cantina -> develop (sincronização)"
git push origin develop
```

---

## ✅ Resultado Final

Ao fim da execução, o repositório terá:

| Branch | Estado |
|--------|--------|
| `main` | Manual completo + hotfix aplicado |
| `develop` | Manual completo + hotfix sincronizado |
| `feature/dicas-prazos` | Capítulo 1 (já mergeada) |
| `feature/mochila-aula-tecnica` | Capítulo 2 (já mergeada) |
| `feature/lanches-perto` | Capítulo 3 (já mergeada) |
| `feature/regras-trabalho-equipe` | Capítulo 4 (já mergeada) |
| `hotfix/ajuste-cantina` | Correção emergencial (já mergeada) |

### Histórico de Commits esperado (`git log --oneline --graph --all`):

```
*   Merge hotfix/ajuste-cantina -> develop (sincronização)
|\
| | *   Merge pull request: hotfix/ajuste-cantina -> main
| | |\
| |/ |
| * | fix: corrigido nome e valor do salgado na cantina
| |/
| *   Merge pull request: develop -> main (publicação do manual completo)
| |\
|/ |
*  |  Merge pull request: feature/regras-trabalho-equipe -> develop
|\ |
| * | feat: adicionado capitulo 4 - regras de equipe
|/ |
*  |  Merge pull request: feature/lanches-perto -> develop
|\ |
| * | feat: adicionado capitulo 3 - lanches perto da escola
|/ |
*  |  Merge pull request: feature/mochila-aula-tecnica -> develop
|\ |
| * | feat: adicionado capitulo 2 - mochila aula tecnica
|/ |
*  / feat: adicionado capitulo 1 - dicas de prazos
|/
* chore: commit inicial do manual
```

---

## 📝 Resumo de Responsabilidades

| Quem | Ações |
|------|-------|
| **Líder (Aluno A)** | Cria repositório, branch `develop`, escreve Cap. 1, faz merge final para `main`, executa hotfix |
| **Aluno B** | Clona, cria `feature/mochila-aula-tecnica`, escreve Cap. 2, faz PR para `develop` |
| **Aluno C** | Clona, cria `feature/lanches-perto`, escreve Cap. 3, faz PR para `develop` |
| **Aluno D** | Clona, cria `feature/regras-trabalho-equipe`, escreve Cap. 4, faz PR para `develop` |
| **Qualquer colega** | Revisa e aprova PRs dos outros membros |

---

## 💡 Dica para o Professor

Para rodar tudo de forma automatizada (sem abrir notepad), substitua os blocos de edição manual por um script PowerShell que cria o arquivo completo de uma vez:

```powershell
@"
# Manual de Sobrevivência do 1º Ano Técnico

## Capítulo 1: Dicas para não esquecer os prazos das tarefas
- Use um aplicativo de agenda para registrar prazos.
- Anote tudo no caderno assim que o professor falar a data de entrega.
- Coloque alarmes no celular 2 dias antes de cada prova ou trabalho.
"@ | Set-Content -Path guia.md
```

Assim é possível construir o estado do arquivo em cada etapa sem depender de edição manual.
