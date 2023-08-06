# Repositorio-GetStarted-K1-T1
Projeto introdutório trilha (K1-T1): Versionamento de Código

# **O que é versionamento de código?**

Criação de diferentes ramos em paralelo que representam diferentes instâncias de um mesmo programa, uma com alteração e a outra inalterada. O versionamento consiste em estratégias para gerenciar as diferentes versões de um código, de um sistema ou de um modelo. É uma forma de administrar as mudanças, que são feitas e de garantir mais segurança na transição de uma versão para outra.

---

# Como enviar um arquivo para o Git

### É um comando único que você usa durante a configuração inicial de um novo repositório.

```jsx
git init
```

### Verifica o status dos meus arquivos:

```jsx
git status
```

---

### Adiciona todos os arquivo para staged área.

```jsx
git add .
```

### Commit para adicionar uma observação antes de enviar.

```jsx
git commit -m "Adicionando arquivos das aulas"
```

Enviando para meu repositório

```jsx
git push origin main
```

---

## Como puxar arquivos do Git

```jsx
git pull origin
```

### Como verificar quais linhas fiz modificação. Existe duas formas quando já temos uma cópia e quero comparar bastar dar um:

```jsx
git diff

```

### Caso não tenha uma versão pra comparar aí basta dar um ele verificar a modificação dá área de preparação para área que já está comitada:

```jsx
git diff --staged
```

```jsx
git diff --cached
```

### Como remover um arquivo quando tem dados sensíveis e não quero que vá para meu repositório.

```jsx
git rm--cached nomedoarquivo.txt
```

---

https://lh4.googleusercontent.com/IXtHefgXMcOVOKthmW1HhFJd6yOu8DoVfVtCj2Udyv8CAXyHASnGQCqglEYiCn03c-Jh6swXKogjseqKPpZBa8p_7fV_yOy6LBw5D2PKrZ7XsvtzWfyOatpNI6PxWJMgcnVPxwxtTN-kqtMmVEBCFrU

## Como verificar o histórico dos commits os logs

Mostra quem alterou e quando alterou e qual foi a mensagem de commit que o autor colocou.

Também é possível colocar **git log -3** onde mostra apenas os 3 últimos.

```jsx
git log
```

### Quando quer ver em apenas uma linha mais resumida dou: o mesmo posso fazer no **oneline colocando -2** na frente vai aparece as duas ultimas resumidas

```jsx
git log --oneline
```

Atualização dos meus commits o p é de patch que seria uma pacote de atualização.

```jsx
git log -p
```

Ou

```jsx
git log --patch
```

### Ou o stat que mostra o padrão mais os arquivos que foram modificados.

```jsx
git log --stat
```

Podemos dar um short stat que mostra apenas os arquivos que foram mudados tendo menos detalhes.

```jsx
git log --shortstat
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/263a00b8-cfd7-4c5a-a511-2e7d27748d0c/Untitled.png)

### Alterando Commit, esse comando é um pouco perigoso, pois ele muda o código do commit, porém a vantagem é que ele corrige a mensagem do commit./

```jsx
git commit --amend -m "Alteração de arquivo"
```

Quando quero ver o arquivo do commit basta usar: 

```jsx
code .
```

---

### Navegando entre commits

Podemos navegar utilizando primeiro o oneline para ver o código de depois entrando no código em si.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2f5655e2-51c9-4294-a751-b110d8ce14c8/Untitled.png)

```jsx
git log --oneline
```

```jsx
git checkout ab76182b
```

Para voltar utilizo o checkout master para voltar para o último.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/235aacb9-9149-42e4-9a5c-5e36c2ce0da9/Untitled.png)

```jsx
git checkout master
```

Stach —> Estudar.

---

## #O git checkout com o nome do arquivo reverte o arquivo para última versão **perdendo todas as informações** de commits.

Já o git checkout remove arquivos tracked rastreados, arquivos modificados. Nessa função também não funciona se eu tiver dado um git add nesse arquivo.

```jsx
git checkout main.txt
```

Essa função limpa arquivos não rastreados untracked. Quando dou um clean antes essa função não funciona porque eu já rastreei.

```jsx
git clean - f
```

Remove um arquivo.

```jsx
git rm --cached main.txt
```

---

## Função para ver qual é o repositório:

```jsx
git remote -v
```

Função para direcionar qual é o meu diretório. O nome origin pode ser modificado inclusive posso mandar para um temporário tipo git remote add temporário https…

```jsx
git remote add origin https://github...
```

Posso direcionar também para um nova url

```jsx
git remote set-url origin https://...
```

---

# Como clonar um repositório

```jsx
git clone https://... nomeDapasta
```

## Enviando os dados para o git com os dados do meu commit

```jsx
git push
```

## Para atualizar as informações do meu repositório que já foi clonado e que fiz alguma alteração em algum arquivo no git e quero que atualize na minha máquina.

```jsx
git pull
```

### Dentro do Github temos a função de fork nela podemos gerar uma cópia do repositório de outra pessoa para o meu. E quando faço isso é bom porque posso ver as mudanças que a pessoa fez.

---

# Pull request

É uma proposta de mudança que eu fiz para o projeto inicial, ótimo para antes de fazer um commit, pois outra pessoa pode verificar antes de fazer o commit.

---

# Issues, milestones, labels

## Issue é um problema, dentro do github posso abrir um issue informando qual é o problema. É muito bom de utilizar por conta da **visibilidade**. O issue  pode ser também sugestões.

## Labels: São categorias que apenas o dev dono pode administrar. Usado para categorizar os problemas.

## Milestones: Seria um marco como se fosse uma comemoração. No git normalmente é usado quando um site novo será lançado e dentro dele possui as issues ligadas a ele.

---

## Arquivo Readme

Se trata de uma explicação do meu repositório.
Esse site é bom como exemplo para saber criar bem um arquivo readme

[Online Markdown Editor - Dillinger, the Last Markdown Editor ever.](https://dillinger.io/)

---

# Chave SSH

### Alguns projetos usam por conta dá segurança. 
Lembrando que a chave ssh não é por repositório e sim por conta.

Como adicionar/ gerar uma SSH Key.

https://www.youtube.com/watch?v=7WUSApSgGTA

```jsx
ssh-keygen
```

```jsx
cat ~/.ssh/id_rsa.pub
```

### Como adicionar a chave ssh na mão.

```jsx
eval $(ssh-agent)
```

```jsx
ssh-add ~/.ssh/nomeDaChaveQue é o titulo que coloquei lá no git.
```

```jsx
git clone https://... nomeDapastaNoComputador
```

---

# Bitbucket

Ferramenta de gerenciamento de projetos Git, serve para dar suporte. E tem integração com o Atlassian dá microsoft.

---

# Branch

É uma ramificação do meu projeto que permite que funcionalidade sejam desenvolvidas separadamente sem impactar funcionalidades estáveis no projeto.

Ocorre quando estou trabalhando em diferentes tasks e a finalidade final de dar um merge que é unir essas tasks.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/296c577b-ac40-431c-ba25-487da0c47f6e/Untitled.png)

Como faço para listar as minhas Branches

```jsx
git branch --list
```

Como criar uma nova branch

```jsx
git branch teste
```

Para usar essa branch

```jsx
git checkout teste
```

Alterações feitas na branch que eu criei não altera na main.

Como que faço para voltar para main

```jsx
git checkout main
```

Como criar uma nova branch e mudar para ela direto.

```jsx
git checkout -b TASK-1
```

Como mudar para uma branch que eu já criei.

```jsx
git switch teste
```

Ou para voltar para ultima que selecionamos

```jsx
git switch -
```

Posso criar pelo switch também o -c é de create.

```jsx
git switch -c TASK-2
```

Posso criar também uma sub ramificação.

```jsx
git checkout -b TASK-2.1
```

Para voltar para main

```jsx
git switch main
```

Quando quero desfazer as alterações rastreadas na minha branch o -f faz com o git ignore os arquivos com status modified e desfaz minhas alterações. Tudo é perdido precisa tomar cuidado.

```jsx
git checkout -f teste
```

---

# Detached head

Quando minha cabeça não está no mesmo ponto que a minha main.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/607267ba-f0c2-4cca-892f-3d59f8a31557/Untitled.png)

Quando ocorre esse ponto que significa essa mensagem no git.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7e6c9251-0505-4837-b983-7020979176c2/Untitled.png)

Eu posso criar uma nova branch já com a cabeça também direcionada a ela.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/41360da8-63f5-4177-80a1-2075066ade2a/Untitled.png)

```jsx

git switch -c head teste2
```

Nesse caso, quando crio dessa forma, mesmo eu criando uma nova branch o head vem junto.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fafb5567-a48d-46c4-bee8-da51db62582d/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b2f84c46-b83e-402a-b288-a6be71da00cb/Untitled.png)

---

Como eu envio as informações de uma branch para o meu repositório.
Normalmente o nome dá nossa branch também é nome do servidor. Colocando minha branch local sincronizada com a minha branch no servidor.

```jsx
git push --set-upstream origin teste

Ou também posso usar esse código:

git push -u origin teste
```

Depois que minha branch já está mapeada basta dar um:

```jsx
git push
```

---

## Como apagar minha branchs locais.

Quando eu apago uma branch eu também apago o histórico.

```jsx
git branch -d TASK-1
Posso forçar a removação usando o código
git branch -D TASK-1
```

---

## Como apagar minha branchs remota

```jsx
git push --delete origin TAKS-2
```

---

## Renomeando Branchs

Quando já estou na branch que quero mudar o nome.

```jsx
git branch checkout -b TASK-1
git branch -m TASK-10
```

Quando não estou ai preciso dar o código.

```jsx
git branch -m TASK-10 TASK-1
```

No servido não é possível mudar o nome depois de criado. Para fazer isso teria que remover a branch com o delete e depois renomear minha branch e enviar novamente.

```jsx
git push --delete origin TASK-1
git branch -m TASK10
git push --setupstream origind TASK10
```

---

## Variação do comando git log

```jsx
git log --oneline -5
Posso passar o nome da branch que quero
git log teste --oneline -5
```

---

# Não existe diferença ente git switch e git checkout o switch é mais novo apenas isso.

---

# Merge

Eu sempre trago as mudanças que branch que estou. Ele traz as mudanças para branch main

```jsx
Quando estou em outra branch
git switch main
code .
git merge teste
```

Posso ver quais branches ainda não foram mergeadas

```jsx
git branch --no merged
```

Também tenho comando para saber quais já foram mergeadas

```jsx
git branch --merged
```

---

Quando temos falha no merge que normalmente ocorre quando temos mudança na mesma linha e teve mais de uma mudança na mesma linha em diferentes branches

Eu posso desistir do merge

```jsx
git merge --abort
```

Ou posso verificar o conflito, para esse caso posso editar o arquivo que estava dando problema e remover a linha que estava dando conflito.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/60310dd6-5053-4ace-8b7e-fbd68772f6cd/Untitled.png)

---

# SCM - Source Code Management

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/581f07cd-28a2-4865-9dba-177e2975320f/Untitled.png)

---

# Network Graph

É uma representação real de como está nossa branches

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/83c9d460-0470-405c-b369-0faa8693d58a/Untitled.png)

---

# Tags

A tag é um ponteiro, normalmente indica um marco em versões lançadas.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ba8e6990-ef42-4614-b14d-0e646f8b5e5a/Untitled.png)

```jsx
git tag v1
```

Quando quero uma tag, mas com mensagem. Ele marca quem fez como se fosse um commit

```jsx
git tag -a -m "Tag criada V2" V2
```

Para ver essa mensagem basta dar um :

```jsx
git show
Ou mais resumido
git tag -n
```

# E quando não passo informação nenhum aí fica como se fosse um list

### Como criar tag em commit antigo.

```jsx
git tag asd09da8

Se quiser com mensagem

git tag -a -m "Versão 0" v0.1 asd09da8
```

## Enviando tag para o meu repositório.

```jsx
git push origin v0

Se eu quiser mandar todas as tags de uma vez basta dar um :
Mas esse não é recomendado pois ele não liga para o que estava no servidor.

git push --tags
```

## Usar uma tag é muito mais fácil que um commit por tanto eu posso.

Nesse exemplo comparo o que mudou entre uma tag e outra.

```jsx
git diff v0 v1
```

# Como remover uma tag

o d é de delete

```jsx
git tag -d v0.1
```

Depois envio para o meu servidor informando que removi a tag

```jsx
git push --delete origin v0.1
```

---

# Stash - Importante

Quando estou fazendo mudança, mas não quero enviar ainda eu dou o stash e volto para main e posso continuar fazendo outras coisas.

```jsx
git stash

Quando quero ver as mudanças que fiz

git stash list
```

Por último dou:

```jsx
git stash apply
```

Se tiver várias stash posso aplicar em um específico e informo a posição.

```jsx
git stash apply stash@{0}
```

Quando quero que depois que apliquei suma da minha lista dou um. 

```jsx
git stash pop
```

E quando quero remover um stash dou um drop

```jsx

git stash drop stash@{0}
```

Posso criar uma branch a partir de uma stash

```jsx
git stash branch feature-1 stash@{0}

Ou

git stash branch feature-1
```

---

## Revertendo Commits

Isso acontece quando fiz às vezes um commit que quebrou o site e não tenho tempo de ver o que aconteceu. Quando eu faço a reversão eu não desfaço nada, apenas faço como se fosse um novo commit em cima. Aq

```jsx
git revert HEAD
```

---

# Desfazendo um commit

Quando eu desfaço eu realmente removo um commit ele ignora apaga os commits do meu projeto.

```jsx
git reset --hard HEAD

Quando quero ser mais especifica dou um ~ aqui posso passar quantos que quiser reverter

git reset --hard HEAD~1
```

Posso dá um soft também ai ele já desfaz dando um comando add automaticamente.

---

## GIT PUSH FORCE - Envio de mudanças forçadas

É uma função que ajuda a dar um push passando por cima de algumas mudanças. E essa função precisa ter mais cuidado, pois ele subscreve a linha do tempo.

```jsx
git push --force

Essa é uma variação

git push --force-with-lease
```

O mais seguro de ser usado é o 

---

# Rebase

Usado quando temos mudanças na linha do tempo da main e na linha de uma branch e nos dois possui mudança e quando peço para unir o git dá um merge commit dos dois e as pessoas veem ele como algo que polui, pois não possui nada apenas uma integração. Simplesmente porque a linha do tempo não é mais linear e o Rebase serve para corrigir esse problema.

Quando dou o rebase eu saí dá base, eu troco a base e crio um novo commit sem ter linha do tempo e vira tudo uma coisa só. Ajuda a ficar linear.

Ele é um pouco perigoso por conta disso por que altera a timeline e o histórico dá branch e a orientação é não fazer isso em uma branch publica.

```jsx
git rebase main
```

Quando vou fazer o rebase, mas tenho um conflito.

```jsx
Caso eu queira parar

git rebase --abort

Quando já fiz o ajuste no arquivo que estava dando conflito e dou:

git rebase --continue
```

---

## Rebase - Pull

Ele pegará as mudanças na main do meu repositório, vai buscar as commits remotas, vai ver o que eu não tenho e aplicar em cima da minha branch main e se eu tive algum commit ele será reescrito em cima da mudança que veio do servidor.

```jsx
git pull --rebase
```

---

# Fetch - Trazer atualizações

A branch é trazida parcialmente do meu repositório local. E ele criar a branch do meu servidor. Serve para ignorar minha branch local e trago uma do meu servidor. Ele traz commits, branches e tags. 

```jsx
git fetch origin develop
```

```jsx
git diff origin/main
```

Traz atualizações do nosso repositório remoto mas ainda não executando no nosso repositório local, para que exista a oportunidade caso necessário de investigar o que está acontecendo para então sim fazer uma junção.

---

# Squash - Fusão

Squash é comprimir seria eu pego várias branches que fiz e faço uma fusão em um. Essa função também altera a timeline do meu projeto.

```jsx
git rebase -interactive HEAD~3
```

---

# Cherry Pick

Vou trazer algo para onde estou caso eu esteja na main trago para main. Esse algo é a hash do meu projeto. Muito usando quando tenho uma branch muito importante que quero trazer para main.

```jsx
git cherry-pick as776as
```

---

# Bisect

É um comando que ajuda a identificar um problema que está acontecendo pela primeira vez. Ele faz uma busca binária em elementos ordenados, ela pega o conjunto e divide no meio e pergunto para o usuário se é o que eu estou buscando e ele vai divindo na metade até dar no máximo 20 tentativas. Eu informo qual hash que a hash estava funcionando e quando pagou de funcionar.

Ele é ótimo pois nos ajuda a identificar onde que deu problema.

```jsx
git bisect start
git bisect good 1j2kl23h
git bisect bad 12jhk2ad
```

---

# Alias - Abreviação (configuração)

Tem comandos que são essenciais para o uso do git e posso configura algumas abreviações.

```jsx
git alias

git config --global alias.s status

Quando faço isso o meu git status virá só git s

git s

Outro exemplo

git config --global alias.l log

git l
```

Caso eu queira desfazer basta aqui vou descartar

```jsx
git config --global --unset

Exemplo:

git config --global --unset alias.s
git config --global --unset alias.l
```

---

# Grep

Nesse caso ele filtra exemplo todas as branches que tem a letra a ou que tem alguma mensagem no commit

Se trata de um filtro

```jsx
git branch | grep a

Ou buscar commit na mensagem ou com C maiusculo

git log --oneline | grep commit
git log --oneline | grep Commit
```

---

# Sourcetree

Ferramenta que ajuda a ser mais visual para ver nosso repositório. Muito bom que não precisa usar tanto o terminal.

---

# GitKraken

Parecido com o sourcetree
