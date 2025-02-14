[![Leia em Português](https://img.shields.io/badge/%F0%9F%87%A7%F0%9F%87%B7%20Portugu%C3%AAs-F0FFFF.svg)](COMANDOSGIT.md)
[![Leia em Inglês](https://img.shields.io/badge/%F0%9F%87%BA%F0%9F%87%B8%20English-gray.svg)](GITCOMMANDS.md)

##  Índice
- [💻 Sistemas de controle versão](#controle-versao)
- [⚙️ Configurando o Git](#configurando-o-git)
- [🗂Criando e Clonando Repositorios](#criando-clonando-repositorios)
- [📝O que é GiHub](#GitHub)
- [📝Salvando Alteraçõs no Repositório](#salvando-alteracoes-no-repositório)
- [↩Desfazendo Aterações](#desfazendo-alteracoes)
- [❓O que são branchs?](#Branchs)
  - [➕ Criando branchs](Criando-Cranchs)
  - [➕Criando branchs teste](Criando-Cranchs-Teste)

# 💻 Resumo das aulas Git GitHub
## O que um Sistema de Controle de Versão faz? 
-  Controlam a versão de um arquivo ao longo do tempo 
-  Registra o histórico de atualização de um arquivo. 
-  Gerencia quais forma as alterações, a data, autor , etc... 
-  Organização, controle e segurança.
<a id="controle-versao"></a>
## Dentre os Sistemas de controle de versão (VCS), temos:
1. **VCS Centralizado (CVCS)**:
  Um servidor Central com banco de todas as Versões. </br>
  No caso se o servidor ficar fora do ar pode dificultar a colaboração para alteração no projeto, da mesma formar que se um arquivo for corropido e tiver uma perca de dados, se não tiver o beckup, pode acabar perdendo o projeto.
  -  Exemplos: Subversion,  CVS
2. **VCS distribuído**:
     O banco de versão é duplicado localmente, os colaboradores do projeto terão uma cópia do projeto.</br>
Clona o repositório completo, o que inclui o histórico de versões.<br>
Cada Clone é como um backup. </br>
Possibilita um Fluxo de trabalho flexivel<br>
Possibilidade de trabalhar sem conexão a rede<br>
-  Exemplos: Git, Mercurial

  <a id="configurando-o-git"></a>
## ⚙️ Configurando o Git

- **Configurando seu e-mail**:
  ```bash
  $ git config user.email [seu_email_aqui]
  ```

- **Configurando seu nome de usuário**:
  ```bash
  $ git config user.name [seu_usuario_aqui]
  ```

Se você precisar especificar o escopo para sua configuração, use as tags abaixo:

- **Escopo local** (específico para o repositório atual):
  ```bash
  $ git config --local user.email [seu_email_aqui]
  ```

- **Escopo global** (aplica-se a todos os repositórios em seu sistema):
  ```bash
  $ git config --global user.email [seu_email_aqui]
  ```

- **Escopo do sistema** (aplica-se a todo o sistema, afetando todos os usuários):
  ```bash
  $ git config --system user.email [seu_email_aqui]
  ```
  <a id="GitHub"></a>
## O que é Git GitHub?
É um Sistema de Controle de versão distribuido, 
gratuito open source, com
ramificações (branching) e fusões (merging) eficientes.

<a id="criando-clonando-repositorios"></a>
## Criando e Clonando Repositórios

Existem formas de obter um repositório git na sua 
maquina

 1. **Transformando um diretório local que não esta sob 
controle de versão num repositório git**:

| Comandos | Descrição |
| --- | --- |
|  mkdir nome-da-pasta | Criar pasta |
| cd nome-da-pasta | entrar na pasta |
| git init | transformar a pasta em repositório git |
| ls | listar o que tem dentro da pasta |

2. **Clonando um repositório existente**:
   
| Comandos | Descrição |
| --- | --- |
| git clone novo-nome-diretório | clonar repositório existente do github |
| git remote add origin repositório-github | associa um repositório local a um repositório remoto no sistema de controle de versão Git |

 <a id="salvando-alteracoes-no-repositório"></a>
## Salvando Alterações no Repositório
| Comandos | Descrição |
| --- | --- |
| touch README.md | cria arquivo na linguagem de marcação readme.md |
| git add README.m | adiciona novo arquivo README.md na area de prepação para commit |
| git status | mostra o espaço de preparação para dar commits |
| git commit -m"commit inicial" | grava alterações no repositório com uma mensagem |
| git log | mostra commits feitos |
| echo pasta-irrelevante/> .gitignore  | cria arquivo.gitignore para colocar as pastas que não vai aparecer para commitar |

  <a id="desfazendo-alteracoes"></a>
## Desfazendo Alterações

| Comandos | Descrição |
| --- | --- |
| rm -rf .git | desfazer um git init na pasta errada |
| git restore arquivo1 | voltar para o commit antigo depois de alteração salva em um arquivo1 |
| git commit --amend -m "correção" | corrigir ultimo commit feito |
| git reflog | mostra histórico mais detalhado de commits |
| git restore --staged url-do-arquvo | Tira um arquivo da area de preparação |

## Desfazer commit com 3 tipos de git reset

## 🔸git reset soft
| Comandos | Descrição |
| --- | --- |
| git reset --soft | o arquivo volta dos commits para a area de preparação |
| git log <br>  git reset --soft numero-do-commit-retornado-do-git-log | mostra commits feitos anteriores e exclui arquivo do commit citado acima |

## 🔸git reset --mixed
O "git reset" padão pode ser escrito tambem como apenas"git reset"
| Comandos | Descrição |
| --- | --- |
| git status <br> git add .| mostra o arquivo do commit excluido foi removido e o remove com git add . |
| git log <br> git reset --mixed numero-do-commit-retornado-do-git-log <br> git status <br> git add . | O comando “git reset --mixed” faz o repositório apontar para o commit especificado e reverte o(s) arquivo(s) modificado(s) para unstaged. Assim, após executar “git reset --mixed”, é necessário usar “git add” antes de usar “git commit”. |

## 🔸git reset --hard

| Comandos | Descrição |
| --- | --- |
| git reset --hard | Ignora completamente os arquivos que estavam no meu commit anterior e desfaz ele |
| git log | para confirmar que o arquivo commit foi desfeito |

<a id="Branchs"></a>
## Trabalhando com Branches
De maneira simplista, uma Branch (em tradução, "ramo") é uma ramificação do seu projeto.
É um ponteiro móvel para commit no histórico do repositório;
Quando você cria uma nova Branch a partir de outra existente a nova 
se inicia apontando para o mesmo commit da Branch que estava quando foi criada.<br>

<a id= "Criando-Branchs"></a>
### Criando Branchs e fazendo uma apontar para outra;

```jsx
echo "commit-0" > commit-0.txt
git status
git add .
git commit -m"commit-0"

echo "commit-1" > commit-1.txt
git status
git add .
echo git commit -m"commit-1"

echo "commit-2" > commit-2.txt
git status
gitt add .
git commit -m"commit-2"
 ```
<a id= "Criando-Branchs-Teste"></a>
### Como fazer uma branch teste;

| Comandos | Descrição |
| --- | --- |
| git checkout -b teste | aponta para branch teste  |
| git log |  |
| echo "commit-3-teste">commit-3-teste.txt  | cria novo arquivo.txt |
| git commit -m"commit-3-teste" |  |
| git add . |  |
| git commit -m"commit-3" |  |
| git checkout main | volta para branch main, assim todos os arquivosda branch teste serão excluidos |
| git branch -v | para ver o ultimo commit de cada branch |
| git merge nome-da-branch-a-mesclar | Mescla a branch com a branch main para fazer com que as alterações feitas lá na branch teste serem executadas |
| git branch | listar as branchs criadas |
| git branch -d nome-branch-a-excluir | Exclui branch |
