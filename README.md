# 📘 Manual de Sobrevivência do 1º Ano Técnico

**Repositório Modelo — Atividade Prática de Gitflow**

Este repositório foi criado como modelo de referência para a atividade prática da disciplina de Desenvolvimento de Sistemas na ETEC Boituva. Ele demonstra o fluxo completo de trabalho colaborativo utilizando **Git**, **GitHub** e a metodologia **Gitflow**.

---

## 🎯 Objetivo

Servir como gabarito/exemplo para o professor avaliar a atividade dos alunos, demonstrando:

- Inicialização de repositório e primeiro commit
- Criação e uso da branch `develop`
- Criação de feature branches individuais por aluno
- Merge via Pull Request (simulado com `--no-ff`)
- Publicação (merge de `develop` → `main`)
- Correção de emergência com `hotfix`

---

## 🏗️ Estrutura de Branches

```
[ main ]         ══════════════════════════> (Produção — versão final + hotfix)
  \                          /         /
[ develop ]      ══════════════════════> (Integração — todos os capítulos)
  \        \        \        \
[ feature/* ]   ══════════════>          (Trabalho isolado de cada aluno)

[ hotfix/* ]     ─────────────────────> (Correção emergencial direto da main)
```

---

## 📂 Branches disponíveis

| Branch | Autor | Descrição |
|--------|-------|-----------|
| `main` | Líder (Aluno A) | Versão de produção — manual completo + hotfix |
| `develop` | Equipe | Linha de integração — todos os capítulos reunidos |
| `feature/dicas-prazos` | Aluno A (Líder) | Capítulo 1: Dicas para não esquecer os prazos |
| `feature/mochila-aula-tecnica` | Aluno B | Capítulo 2: O que levar na mochila |
| `feature/lanches-perto` | Aluno C | Capítulo 3: Salgados perto da escola |
| `feature/regras-trabalho-equipe` | Aluno D | Capítulo 4: Regras para trabalho em equipe |
| `hotfix/ajuste-cantina` | Líder / Designado | Correção do nome e preço da cantina |

---

## 📋 Conteúdo do Manual (`guia.md`)

O arquivo principal contém 4 capítulos escritos colaborativamente:

1. **Dicas para não esquecer os prazos das tarefas** — Aluno A
2. **O que levar na mochila nos dias de aula técnica** — Aluno B
3. **Onde encontrar os melhores salgados perto da escola** — Aluno C
4. **Regras de ouro para trabalhar em equipe sem treta** — Aluno D

---

## 🔄 Fluxo de Trabalho Executado

1. **Líder** cria o repositório com commit inicial
2. **Líder** cria a branch `develop` e convida colaboradores
3. **Cada aluno** cria sua `feature/*` a partir da `develop`
4. **Cada aluno** escreve seu capítulo e faz push da feature
5. **Colegas** revisam e aprovam os Pull Requests para `develop`
6. **Líder** faz merge de `develop` → `main` (publicação)
7. **Professor** anuncia mudança urgente (cantina mudou!)
8. **Líder** cria `hotfix/ajuste-cantina` a partir da `main`, corrige e faz merge para `main` e `develop`

---
<img width="322" height="203" alt="image" src="https://github.com/user-attachments/assets/17aa0982-e238-4bb9-99f2-48f04473f0d1" />
---

## 📖 Documentação Adicional

- [`ROTEIRO_COMANDOS.md`](ROTEIRO_COMANDOS.md) — Sequência completa de comandos Git para reproduzir este repositório do zero.

---

## 🛠️ Como Reproduzir

Consulte o arquivo [ROTEIRO_COMANDOS.md](ROTEIRO_COMANDOS.md) para a lista completa de comandos organizados por passo e por responsável.

---

## 📚 Referências

- [Git Documentation](https://git-scm.com/doc)
- [Gitflow Workflow (Atlassian)](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)
- [GitHub Flow](https://docs.github.com/en/get-started/quickstart/github-flow)

---

## 👨‍🏫 Professor

**Alexandre Ballestero de Paula**  
ETEC Boituva — Desenvolvimento de Sistemas  
1º Ano do Ensino Médio Técnico
