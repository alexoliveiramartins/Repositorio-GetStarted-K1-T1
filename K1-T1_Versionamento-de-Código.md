#### Configurar usuário global git

```bash
git config --global user.name "Alex Martins"
```

```bash
git config --global user.email "alex.oliveiramartins05@gmail.com"
```

Se retirar os argumentos, você consegue ver os atuais `user.name` e `user.email`
#### Ver status do repositório
```bash
git status
```

#### Adicionar arquivos modificados / untracked
Adicionar um arquivo individual
```bash
git add "nome_do_arquivo"
```
Para adicionar todos os arquivos no diretorio atual
```bash
git add .
```
Para adicionar todos os arquivos no diretorio atual mas não dar stage em arquivos deletados
```bash
git add *
```
Para adicionar todos os arquivos modificados / untracked do repositório
```bash
git add -A
```

#### Unstage / Untrack / Remover arquivo
```bash
git rm --cached "arquivo"
```
Para remover todos os arquivos:
```bash
git rm --cached -r .
```

#### Commitar arquivos staged
```bash
git commit -m "mensagem_commit"
```

#### Vizualizar mudanças nos arquivos
```bash
git diff
```

#### Vizualizar histórico de commits
```bash
git log
```

```bash
git log --oneline
```

#### Descartar commit e commitar de novo
```bash
git commit --amend -m "mensagem"
```
Para não mudar a mensagem do commit
```bash
git commit --amend --no-edit
```

ps.: *Usar com cuidado pois deleta o ultimo commit!*

#### Mudar repositorio local para outro commit
```bash
git checkout "id_do_commit"
```
Para voltar pro último commit (volta os arquivos **rastreados** para a versão do último commit)
```bash
git checkout .
```

Limpar arquivos não rastreados
```bash
git clean
```
Voltar **tudo** para o último commit (descarta todas as alterações):
```bash
git reset --hard
```

#### Parar de rastrear um arquivo ja commitado
```bash
git update-index --skip-worktree main.html
```
Para voltar a rastrear
```bash
git update-index --no-skip-worktree main.html
```

#### Clonando repositório
Repositório local
```bash
git clone "repositorio_original" "repositorio_a_ser_criado"
```
Repositório remoto:
```bash
git clone "htts://link.do.repositorio/"
```

#### Adicionando repositório à servidor remoto
```bash
git remote add origin "https://github.com/exemplo/repositorio.git"
```
Ps.: `origin` é só como o servidor vai ser chamado pelo repositório, pode ter qualquer nome

Para ver os repositórios remotos configurados:
```bash
git remote -v
```

#### Enviando alterações (commits) para o repositório remoto
```shell
git push
```

Para **receber** as alterações do repositório remoto:
```shell
git pull
```

#### Branches
Para ver as branches do repositório:
```bash
git branch
```
Criar uma branch nova:
```bash
git branch "nome_da_branch"
```
Trocar para outra branch:
```bash
git checkout "nome_da_branch"
```
Caso a branch não exista:
```bash
git checkout -b "nome_da_branch"
```
ou usar o git switch (melhor):
```bash
git switch "nome_da_branch"
```
Caso a branch não exista:
```bash
git switch -c "nome_da_branch"
```

Para alternar entre branches:
```bash
git switch -
```

Para trocar de branch e descartar todos as modificações não commitadas:
```bash
git checkout -f "nome_da_branch"
```

Para "enviar" uma branch nova para o repositório remoto:
```bash
git push --set-upstream origin "nome_da_branch"
```

Para deletar uma branch local:
```bash
git branch -d "nome_da_branch"
```
Para deletar e ignorar avisos:
```bash
git branch -d "nome_da_branch"
```

Para deletar uma branch remota:
```bash
git push --delete origin "nome_da_branch"
```

Para ver o histórico de alterações de uma branch:
```bash
git log "nome_da_branch"
```

#### Merge de branches
Para trazer as alterações de outra branch para a branch atual
```bash
git merge "outra_branch"
```
Para listar as branches que ainda não foram merged
```bash
git branch --no-merged
```
Para listar as que já foram:
```bash
git branch --merged
```
Cancelar merge com conflitos:
```bash
git merge --abort
```

#### Reverter Commits
Reverter um commit específico (HEAD reverte o último)
```bash
git revert ID_COMMIT
```
ps.: Isso cria um novo commit de reversão

Para reverter o estado do repositório para o último commit
```bash
git reset --hard HEAD
```
Para reverter para o $n$ésimo commit
```bash
git reset --hard HEAD~n
```

---
### Conceitos git
- **HEAD**: Último commit
- **origin**: Geralmente nome utilizado para o repositório remoto
