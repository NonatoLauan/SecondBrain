# Git e GitHub - Fundamentos

## O que é Git?

O **Git** é um sistema de controle de versão distribuído.

Ele registra todas as alterações feitas em um projeto ao longo do tempo, permitindo:

- voltar para versões anteriores;
- trabalhar em equipe;
- criar funcionalidades sem afetar a versão principal;
- saber quem alterou cada parte do código.

### Analogia

Imagine que você está escrevendo um livro.

Sem Git:

```
Livro
Livro Novo
Livro Novo Final
Livro Final Mesmo
Livro Final Agora Vai
```

Com Git:

```
Livro

↓
Versão 1

↓
Versão 2

↓
Versão 3
```

Cada versão fica salva e pode ser recuperada.

---

# O que é GitHub?

O **GitHub** é uma plataforma que hospeda repositórios Git na internet.

Enquanto o Git controla o histórico do projeto, o GitHub permite:

- armazenar projetos online;
- compartilhar código;
- colaborar com outras pessoas;
- revisar alterações;
- integrar mudanças.

## Resumindo

- Git = ferramenta de controle de versão.
- GitHub = serviço que hospeda repositórios Git.

---

# O que é um repositório?

Um repositório (**repository** ou **repo**) é uma pasta monitorada pelo Git.

Quando executamos:

```bash
git init
```

é criada uma pasta oculta:

```
.git
```

Ela contém todo o histórico do projeto.

---

# Como o Git funciona?

O Git salva **snapshots** (fotografias) do projeto.

Exemplo:

```
Foto 1

index.php
login.php
style.css
```

Depois:

```
Foto 2

index.php
login.php
style.css
cadastro.php
```

Depois:

```
Foto 3

index.php
login.php
style.css
cadastro.php
dashboard.php
```

Cada fotografia é um **commit**.

---

# O ciclo do Git

```
Working Directory
        ↓
     git add
        ↓
   Staging Area
        ↓
    git commit
        ↓
      Histórico
```

---

# Working Directory

É onde você trabalha normalmente.

Tudo que modifica no VSCode fica aqui inicialmente.

Exemplo:

```
index.php
```

Você altera o arquivo.

O Git sabe que houve uma mudança, mas ela ainda não faz parte da próxima versão.

---

# Staging Area

A **Staging Area** é uma área temporária.

Ela guarda exatamente quais alterações entrarão no próximo commit.

É como uma "caixa de preparação".

Você coloca nela apenas aquilo que deseja salvar.

---

# git add

O comando:

```bash
git add
```

move alterações da **Working Directory** para a **Staging Area**.

Ele **não salva** o projeto.

Ele apenas prepara as alterações.

---

# O que significa o ponto (.)

Quando fazemos:

```bash
git add .
```

o ponto significa:

> A pasta atual.

Na prática:

```
git add .
```

quer dizer:

> Adicione todas as alterações da pasta atual e de todas as suas subpastas para a Staging Area.

---

## Exemplo

Projeto:

```
index.php
css/style.css
js/app.js
```

Você modifica os três arquivos.

Antes do `git add`:

```
Working Directory

index.php
style.css
app.js
```

Depois:

```bash
git add .
```

Todos passam para a Staging Area.

---

# git status

Mostra o estado do repositório.

Antes do `git add`:

```
Changes not staged for commit
```

Depois:

```
Changes to be committed
```

---

# git commit

Depois de preparar as alterações:

```bash
git commit -m "Corrige tela de login"
```

O Git cria uma nova versão do projeto.

Um commit possui:

- identificador (hash);
- autor;
- data;
- mensagem.

---

# HEAD

O HEAD aponta para o commit atual.

Exemplo:

```
A

↓

B

↓

C ← HEAD
```

Se voltar para B:

```
A

↓

B ← HEAD

↓

C
```

Você passa a visualizar aquela versão.

---

# Branch

Uma branch é uma linha de desenvolvimento independente.

```
main

A

↓

B

↓

C
```

Criando uma branch:

```
feature-login

A

↓

B

↓

C

↓

D

↓

E
```

A branch permite desenvolver novas funcionalidades sem alterar a principal.

---

# Merge

Merge significa unir duas branches.

Antes:

```
main

A

↓

B

↓

C


feature

      D

      ↓

      E
```

Depois:

```
A

↓

B

↓

C

↓

F (merge)
```

---

# Conflito

Quando duas pessoas alteram a mesma parte do arquivo.

Pessoa A:

```php
echo "Olá";
```

Pessoa B:

```php
echo "Bem-vindo";
```

O Git não consegue decidir automaticamente qual manter.

Você escolhe manualmente.

---

# Clone

```bash
git clone URL
```

Baixa um repositório completo.

Inclui:

- arquivos;
- commits;
- branches;
- histórico.

---

# Push

```bash
git push
```

Envia seus commits locais para o repositório remoto.

---

# Pull

```bash
git pull
```

Baixa alterações do repositório remoto e as integra ao seu projeto.

Na prática:

```
git pull

=

git fetch
+
git merge
```

---

# Fetch

```bash
git fetch
```

Baixa as novidades do servidor, mas não altera sua branch atual.

---

# Fluxo básico

```
Editar arquivos

↓

git status

↓

git add .

↓

git commit -m "Mensagem"

↓

git push
```

---

# Quando usar git add .

Use quando todas as alterações pertencem ao mesmo trabalho.

Exemplo:

Você terminou completamente um ticket.

Mudou:

- Controller
- View
- CSS
- Model

Tudo faz parte da mesma funcionalidade.

Então:

```bash
git add .
git commit -m "Implementa notificações"
```

é a escolha correta.

---

# Quando não usar git add .

Imagine que você:

- corrigiu um bug;
- iniciou outra funcionalidade;
- alterou um arquivo apenas para testes.

Nesse caso:

```bash
git add .
```

irá adicionar tudo.

É melhor selecionar apenas os arquivos necessários:

```bash
git add app/Controller/BobinasController.php
git add app/View/Bobinas/index.ctp
```

ou apenas um:

```bash
git add login.php
```

---

# Desfazer um git add

Se adicionou arquivos por engano:

```bash
git restore --staged .
```

Os arquivos saem da Staging Area, mas suas alterações continuam existindo.

---

# Principais comandos

| Comando | Função |
|----------|---------|
| `git init` | Inicializa um repositório |
| `git clone` | Clona um repositório |
| `git status` | Mostra o estado atual |
| `git add` | Prepara alterações |
| `git commit` | Cria uma nova versão |
| `git log` | Mostra o histórico |
| `git diff` | Mostra diferenças entre versões |
| `git branch` | Lista ou cria branches |
| `git switch` | Troca de branch |
| `git merge` | Une branches |
| `git fetch` | Baixa alterações do remoto |
| `git pull` | Baixa e integra alterações |
| `git push` | Envia commits para o remoto |
| `git restore` | Restaura arquivos ou desfaz alterações locais |
| `git reset` | Remove commits ou desfaz o staging, dependendo da opção |

---

# Resumo

## Git

- Sistema de controle de versão.
- Salva o histórico do projeto.
- Permite voltar no tempo.
- Permite trabalhar em equipe.

## GitHub

- Plataforma para hospedar repositórios Git.
- Compartilhamento de código.
- Colaboração.
- Revisão de código.

## Fluxo mental

```
Modificar arquivos

↓

git status

↓

git add

↓

git commit

↓

git push
```

Sempre pense:

- **Working Directory:** onde você está editando.
- **Staging Area:** o que será salvo.
- **Commit:** a versão criada.
- **GitHub:** onde essa versão será compartilhada.