# ⚙️ Auto Git

> **Ferramenta CLI desenvolvida em Bash para otimizar operações frequentes de gerenciamento de branches no Git.**

O **Auto Git** é uma ferramenta de linha de comando desenvolvida em **Bash Shell**, criada com o objetivo de simplificar e agilizar algumas operações recorrentes durante o desenvolvimento de projetos versionados com Git.

O projeto foi desenvolvido como parte dos estudos de **Git e GitHub**, aplicando na prática conceitos de versionamento de código, gerenciamento de branches, automação de tarefas e desenvolvimento de scripts para terminal.

A ferramenta utiliza o **fzf (Fuzzy Finder)** para criar uma interface interativa diretamente no terminal, permitindo que o usuário selecione branches e operações sem precisar digitar manualmente todos os comandos.

---

## 🎯 Problema que o projeto resolve

Durante o desenvolvimento de software, operações como troca de branches, merge e exclusão de branches são realizadas frequentemente.

O Auto Git busca tornar essas tarefas mais práticas através de um **menu interativo**, reduzindo a necessidade de memorizar e digitar comandos individualmente.

Em vez de executar manualmente comandos como:

```bash
git branch
git switch <branch>
git merge <branch>
git branch -d <branch>
```

o usuário pode iniciar o programa e selecionar a operação desejada através de uma interface interativa.

---

## 🚀 Funcionalidades

O programa possui atualmente três operações principais:

### 🔀 Switch Branch

Permite visualizar as branches disponíveis e selecionar aquela para a qual o usuário deseja alternar.

Durante a seleção, o programa também apresenta uma prévia do histórico de commits da branch através do `git log --oneline`.

Após a seleção, a troca é realizada utilizando:

```bash
git switch <branch>
```

---

### 🔗 Git Merge Branch

Permite selecionar uma branch para realizar o merge com a branch atualmente selecionada.

Durante a escolha, o programa apresenta uma prévia das diferenças entre a branch atual e a branch selecionada utilizando `git diff`.

Após a seleção:

```bash
git merge <branch>
```

---

### 🗑️ Delete Branch

Permite selecionar uma branch existente para exclusão.

Assim como na troca de branch, o programa disponibiliza uma prévia do histórico de commits antes da seleção.

A exclusão é realizada através de:

```bash
git branch -d <branch>
```

---

## 🛠️ Tecnologias e ferramentas

| Tecnologia     | Utilização                                             |
| -------------- | ------------------------------------------------------ |
| **Bash Shell** | Desenvolvimento da aplicação e automação dos comandos  |
| **Git**        | Gerenciamento de branches e operações de versionamento |
| **fzf**        | Interface interativa para seleção de opções e branches |
| **GitHub**     | Hospedagem e versionamento do projeto                  |

---

## 💻 Conceitos aplicados

O desenvolvimento deste projeto permitiu colocar em prática diferentes conceitos relacionados ao desenvolvimento e ao ambiente de versionamento:

* Shell Script;
* Bash Functions;
* Variáveis;
* Arrays;
* Estruturas condicionais;
* `case`;
* Manipulação de comandos no terminal;
* Códigos de saída de processos;
* Git Branch;
* Git Switch;
* Git Merge;
* Git Diff;
* Git Log;
* Automação de tarefas;
* Ferramentas CLI;
* Configuração de aliases no `.bashrc`;
* Versionamento utilizando Git e GitHub.

A estrutura principal do programa utiliza funções independentes para cada operação e uma função `main()` responsável pelo menu e direcionamento da execução.

---

## 🧩 Arquitetura do script

O código foi organizado de forma modular, separando as principais responsabilidades em funções:

```text
auto-git.sh
│
├── exit_exception()
│
├── switch_branch()
│
├── merge()
│
├── delete_branch()
│
└── main()
```

Essa organização permite manter cada operação isolada e facilita futuras alterações ou inclusão de novas funcionalidades.

O `main()` concentra o menu principal e utiliza uma estrutura `case` para direcionar a execução conforme a opção escolhida pelo usuário.

---

## 🔎 Interface interativa com fzf

Um dos principais recursos utilizados no projeto é o **fzf**, responsável pela interação do usuário com o programa.

A ferramenta permite apresentar as branches disponíveis de maneira visual e possibilita a utilização de recursos como:

* Seleção interativa;
* Navegação pelo teclado;
* Cabeçalhos personalizados;
* Bordas;
* Layout reverso;
* Pré-visualização de informações;
* Personalização visual do terminal.

Por exemplo, durante a seleção de uma branch, o programa apresenta o histórico de commits correspondente à opção selecionada.

---

## ⚙️ Tratamento de interrupções

O programa também possui um mecanismo para tratar a interrupção da execução pelo usuário.

A função `exit_exception()` verifica o código de saída do processo e encerra o programa de maneira controlada quando a operação é interrompida.

Esse tratamento contribui para uma execução mais previsível da aplicação no terminal.

---

## 📦 Pré-requisitos

Para executar o projeto, é necessário possuir:

* **Bash**
* **Git**
* **fzf**
* Ambiente compatível com Shell Script

Verifique a instalação do Git:

```bash
git --version
```

E do fzf:

```bash
fzf --version
```

---

## 🚀 Instalação

Clone o repositório:

```bash
git clone <URL_DO_REPOSITORIO>
```

Acesse o diretório:

```bash
cd <NOME_DO_REPOSITORIO>
```

Conceda permissão de execução ao script:

```bash
chmod +x auto-git.sh
```

---

## 🔗 Configuração do Alias

Para tornar a ferramenta acessível diretamente pelo terminal, é necessário configurar um **alias no arquivo `.bashrc` local**.

Abra o arquivo:

```bash
nano ~/.bashrc
```

Adicione no final do arquivo:

```bash
alias autogit='/caminho/para/auto-git.sh'
```

> `autogit` é apenas um exemplo. O usuário pode escolher a nomenclatura que desejar.

Após salvar o arquivo:

1. Feche o terminal;
2. Abra o terminal novamente;
3. Execute o alias definido.

Por exemplo:

```bash
autogit
```

A partir desse momento, o programa estará disponível diretamente pelo terminal através do alias configurado.

---

## 🖥️ Fluxo de utilização

O fluxo básico da ferramenta pode ser representado da seguinte maneira:

```text
                 ┌─────────────────┐
                 │   Executar      │
                 │    Auto Git     │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │  Menu interativo│
                 │      fzf        │
                 └────────┬────────┘
                          │
          ┌───────────────┼───────────────┐
          ▼               ▼               ▼
   Switch Branch      Git Merge      Delete Branch
          │               │               │
          ▼               ▼               ▼
     git switch       git merge      git branch -d
```

---

## 📚 Objetivo de aprendizado

Este projeto foi desenvolvido com foco na aplicação prática dos conhecimentos adquiridos durante os estudos de **Git e GitHub**, indo além da utilização convencional dos comandos.

A construção da ferramenta permitiu explorar como comandos Git podem ser combinados com **Bash Script** e ferramentas de terminal para criar uma solução automatizada e interativa.

O projeto também serviu para consolidar conhecimentos sobre:

* Controle de versão;
* Fluxo de trabalho com branches;
* Automação através de Shell Script;
* Organização de código em funções;
* Interação com ferramentas CLI;
* Utilização de comandos Git através de scripts;
* Configuração e utilização de aliases;
* Organização e documentação de projetos no GitHub.

---

## 💼 Competências demonstradas

Este projeto demonstra, na prática, conhecimentos em:

**Git & GitHub**

* Gerenciamento de branches;
* Switch de branches;
* Merge;
* Histórico de commits;
* Diff entre branches;
* Versionamento de código.

**Bash / Shell**

* Criação de scripts;
* Funções;
* Variáveis;
* Arrays;
* Estruturas condicionais;
* Automação de comandos;
* Tratamento de códigos de saída.

**CLI & Automação**

* Criação de interfaces interativas no terminal;
* Integração com `fzf`;
* Automatização de tarefas recorrentes;
* Configuração de aliases.

---

## 🔮 Possíveis evoluções

O projeto foi estruturado de forma que novas funcionalidades possam ser incorporadas posteriormente.

Entre as possibilidades de evolução estão:

* Criação de novas operações Git;
* Visualização de status do repositório;
* Visualização de commits;
* Operações relacionadas a `pull` e `push`;
* Criação de branches através do menu;
* Integração com outros comandos Git;
* Melhorias na interface interativa.

---

## 👨‍💻 Sobre o projeto

O **Auto Git** representa um projeto prático de estudo e portfólio, desenvolvido para demonstrar a aplicação conjunta de **Git, GitHub, Bash Shell e ferramentas de linha de comando**.

Mais do que executar comandos Git individualmente, o projeto busca demonstrar a capacidade de **identificar tarefas recorrentes, automatizá-las e transformá-las em uma ferramenta reutilizável**.

---

### 📌 Status

**Projeto desenvolvido para fins de estudo, prática e composição de portfólio profissional.**

---
