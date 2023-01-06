# Introdução ao Git

## 🧭 Visão Geral

1. Controle de versão
2. Armazenamento em nuvem
3. Trabalho em equipe
4. melhorar seu código
5. Reconhecimento

# Navegação via CLI

## 🔮 Comandos básicos (Windows/Unix):

```Bash
# Listar diretório
> dir
$ ls

# Navegar entre diretórios
> cd
$ cd

# Retroceder navegação
> cd ..
$ cd ..

# Limpar o terminal
> cls
$ clear

# Criar diretório
> mkdir workspace
$ mkdir workspace

#Criar arquivo
> echo hello > hello.txt
$ echo hello > hello.txt

#Remover diretório
> rmdir workspace /S /Q
$ rm -rf workspace
```

# Entendendo como o Git funciona

## 🎲 Objetos fundamentais

### SHA-1

A sigla SHA-1 significa _Secure Hash Algorithm_ (Algoritmo de Hash Seguro), é um conjunto de funções hash criptográficas projetadas pela _NSA_ (Agência de Segurança Nacional dos EUA).

### _Blob_

Um blob (objeto binário grande) do Git é o tipo de objeto usado para armazenar o conteúdo de cada arquivo em um repositório. O _hash_ SHA-1 do arquivo é calculado e armazenado no objeto do _blob_.

### _Tree_

Um objeto da árvore do Git cria a hierarquia entre arquivos em um repositório do Git. Você pode usar o objeto da árvore do Git para criar a relação entre diretórios e os arquivos que eles contêm.

### _Commit_

O commit é o objeto que dá o sentindo para alteração que está sendo realizada, trás em sua composição a _tree_, _author_, _message_, _timestamp_. O SHA-1 desse commit é o hash de toda essa informação.

# Primeiros comandos com Git

## 📦 Repositório Local

### Criar novo repositório

    git init

### Verificar estado dos arquivos/diretórios

    git status

### Adicionar arquivo/diretório (staged area)

##### Adicionar um arquivo em específico

    git add meu_arquivo.txt

##### Adicionar um diretório em específico

    git add meu_diretorio

##### Adicionar todos os arquivos/diretórios

    git add .

##### Adicionar um arquivo que esta listado no .gitignore (geral ou do repositório)

    git add -f arquivo_no_gitignore.txt

### Comitar arquivo/diretório

##### Comitar um arquivo

    git commit meu_arquivo.txt

##### Comitar vários arquivos

    git commit meu_arquivo.txt meu_outro_arquivo.txt

##### Comitar informando mensagem

    git commit meuarquivo.txt -m "minha mensagem de commit"

### Remover arquivo/diretório

##### Remover arquivo

    git rm meu_arquivo.txt

##### Remover diretório

    git rm -r diretorio

### Visualizar histórico

##### Exibir histórico

    git log

##### Exibir histórico com diff das duas últimas alterações

    git log -p -2

##### Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-)

    git log --stat

##### Exibir informações resumidas em uma linha (hash completa e comentário)

    git log --pretty=oneline

##### Exibir histórico com formatação específica (hash abreviada, autor, data e comentário)

    git log --pretty=format:"%h - %an, %ar : %s"

- %h: Abreviação do hash;
- %an: Nome do autor;
- %ar: Data;
- %s: Comentário.

##### Exibir historio de um arquivo específico

    git log -- <caminho_do_arquivo>

##### Exibir histórico de um arquivo específico que contêm uma determinada palavra

    git log --summary -S<palavra> [<caminho_do_arquivo>]

##### Exibir histórico modificação de um arquivo

    git log --diff-filter=M -- <caminho_do_arquivo>

- O <D> pode ser substituído por: Adicionado (A), Copiado (C), Apagado (D), Modificado (M), Renomeado (R), entre outros.

##### Exibir historio de um determinado autor

    git log --author=usuario

##### Exibir revisão e autor da última modificação de uma bloco de linhas

    git blame -L 12,22 meu_arquivo.txt

# Introdução ao Github

## 📦 Repositório Remoto

### Exibir os repositórios remotos

    git remote

    git remote -v

### Vincular repositório local com um repositório remoto

    git remote add origin git@github.com:leocomelli/curso-git.git

### Exibir informações dos repositórios remotos

    git remote show origin

### Renomear um repositório remoto

    git remote rename origin curso-git

### Desvincular um repositório remoto

    git remote rm curso-git

### Enviar arquivos/diretórios para o repositório remoto

O primeiro **push** de um repositório deve conter o nome do repositório remoto e o branch.

    git push -u origin master

Os demais **pushes** não precisam dessa informação

    git push

### Atualizar repositório local de acordo com o repositório remoto

##### Atualizar os arquivos no branch atual

    git pull

##### Buscar as alterações, mas não aplica-las no branch atual

    git fetch

### Clonar um repositório remoto já existente

    git clone git@github.com:leocomelli/curso-git.git

### Tags

##### Criando uma tag leve

    git tag vs-1.1

##### Criando uma tag anotada

    git tag -a vs-1.1 -m "Minha versão 1.1"

##### Criando uma tag assinada

Para criar uma tag assinada é necessário uma chave privada (GNU Privacy Guard - GPG).

    git tag -s vs-1.1 -m "Minha tag assinada 1.1"

##### Criando tag a partir de um commit (hash)

    git tag -a vs-1.2 9fceb02

##### Criando tags no repositório remoto

    git push origin vs-1.2

##### Criando todas as tags locais no repositório remoto

    git push origin --tags
