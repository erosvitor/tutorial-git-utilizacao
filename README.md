## Sobre
Tutorial básico de utilização dos principais comandos GIT.

## Básico
- Inicializando repositório GIT
```
$ git init
```  

- Configurando usuário
```
$ git config user.name "..."
$ git config user.email "..."
```
  
- Verificando as configurações do repositório
```
$ git config --list
```

- Visualizando histórico de alterações
```
$ git log
```

- Visualizando histórico de alterações exibindo apenas o hash e a mensagem
```
$ git log --oneline
```

- Preparando os arquivos
```
$ git add .
```

- Fazendo 'commit' dos arquivos preparados
```
$ git commit -m "Primeiro commit"
```

- Alterando o nome da branch de 'master' para 'main'
```
$ git branch -M main
```

- Associando o repositório local com o servidor remoto
```
$ git remote add origin https://github.com/<nome-usuario>/<nome-projeto>.git
  
Obs: O endereço 'https://github.com/<nome-usuario>/<nome-projeto>.git' é do repositporio criado no servidor remoto
```

- Verificando se o repositório local foi vinculado ao servidor remoto
```
$ git remote -v
```

- Enviando os commits locais para o servidor remoto
```
$ git push -u origin main
```

## Trabalhando com BRANCH
- Criando uma branch local
```
  $ git branch <nome-branch>
  $ git checkout <nome-branch>
```

- Enviando a branch para o servidor remoto
```
$ git push -u origin <nome-branch>
```

- Removendo a branch localmente
```
$ git branch -d <nome-branch>
```

- Removendo a branch do servidor remoto
```
$ git push --delete origin <nome-branch>
```

## Trabalhando com MERGE
- Cancelar um merge que tenha dado conflito
```
$ git merge --abort

  ou
  
$ git reset --hard
```

## Trabalhando com REBASE
- Fazendo rebase que não gere conflito
```
$ git rebase <nome-branch>
  
Obs: Quando não há conflitos, o comando acima é suficiente
```

- Cancelando um rebase que tenha gerado conflito
```
$ git rebase <nome-branch>
$ git rebase --abort
```

- Continuando o rebase que tenha gerado conflito
```
$ git rebase <nome-branch>

$ <aqui resolve-se os conflitos>

$ git add .

$ git rebase --continue
```

## Trabalhando com COMMIT
- Corrigindo a mensagem de commit
```
$ git commit --amend -m "<nova mensagem>"
  
Obs: O comando acima gera um novo commit. Verificar se tem alguem usando o commit que contem a mensagem errada.
```

- Adicionando um novo arquivo num commit já feito preservando a mensagem
```
$ git commit --amend --no-edit
```

- Acessando um determinado commit
```
$ git checkout <numero-commit>
```

- Voltando para o último commit
```
$ git checkout master
```

## Desfazendo alterações
- Como desfazer alterações de arquivos untracked?
```
$ git clean -f
```

- Como desfazer alterações de arquivos tracked, ou seja, arquivos já commitados que foram alterados?
```
$ git restore <nome-arquivo> | git restore .
```

## Licença
Este projeto está sob licença do MIT. Para mais detalhes, ver o arquivo LICENSE.
