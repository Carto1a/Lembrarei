# Configuração inicial de repositório
## init
## clone
## config
## remote

# Adição e commit de alterações
## add
## commit

### Em qual momento fazer o commit:

- **Após concluir uma funcionalidade ou uma parte significativa do trabalho:** Quando você finalizar uma funcionalidade, uma correção de bug ou uma parte importante do seu projeto, faça um commit para registrar essas mudanças e marcar um ponto de referência no histórico do projeto.

- **Antes de iniciar uma nova tarefa ou experimento:** Antes de começar a trabalhar em uma nova tarefa ou fazer alterações significativas, faça um commit das alterações atuais para garantir que você tenha um ponto de restauração se precisar voltar atrás.

- **Quando atingir um marco significativo no projeto:** Se você alcançar um marco significativo no desenvolvimento do projeto, como o lançamento de uma versão importante ou a conclusão de uma etapa importante, faça um commit para marcar esse ponto no histórico.

- **Depois de revisar e confirmar suas alterações:** Após revisar suas alterações e confirmar que estão prontas para serem incluídas no repositório, faça um commit para enviá-las.

- **Regularmente e de forma incremental:** Faça commits regularmente e de forma incremental à medida que você avança no desenvolvimento do seu projeto. Isso ajuda a manter um histórico claro e organizado das alterações feitas ao longo do tempo.

### Como escrever uma boa mensagem no commit

[[Commit Message]]

# Ramificação, mesclagem e reorganização de histórico
## branch
## checkout
## merge
## rebase

# Atualização e sincronização
## fetch
## pull
## push

# Desfazer alterações
## checkout
## reset
## revert

# Visualização e inspeção do histórico
## log
O comando `git log` é utilizado no Git para visualizar o histórico de commits de um repositório. Ele exibe uma lista detalhada de todos os commits feitos, incluindo informações como o hash do commit, autor, data e hora do commit, e a mensagem associada ao commit.

`git log [<options>] [<revision-range>] [[--] <path>…]`

### Opções comuns:
`git log` - Exibe o histórico de commits do repositório.
Exemplo:
```
commit 53efe2e9dede8023cbc74b31693b3326fe92cdb4 (HEAD -> main)
Author: Carto1a <49589600+Carto1a@users.noreply.github.com>
Date:   Thu May 9 14:55:30 2024 -0300

    coisas: Move Git commands, lembrar ssh

commit 7213f084f079ba27568b09cee0f94942f40ad11f
Author: Carto1a <49589600+Carto1a@users.noreply.github.com>
Date:   Thu May 9 12:18:56 2024 -0300

    feat: about gitignore

```

`git log --oneline` - Exibe o histórico de commits em uma única linha.
Exemplo:
```
53efe2e (HEAD -> main) coisas: Move Git commands, lembrar ssh
7213f08 feat: about gitignore
81a1fc1 (origin/main) feat: More Git commands
654f517 feat: Commit messages
3033391 feat: Basico de Git
008c2c5 init
```

`git log -p` - Exibe o histórico de commits com as diferenças de cada commit.
Exemplo:
```
commit 53efe2e9dede8023cbc74b31693b3326fe92cdb4 (HEAD -> main)
Author: Carto1a <49589600+Carto1a@users.noreply.github.com>
Date:   Thu May 9 14:55:30 2024 -0300

    coisas: Move Git commands, lembrar ssh

diff --git a/Git/Comandos.md b/Git/Comandos.md
new file mode 100644
index 0000000..bde888c
--- /dev/null
+++ b/Git/Comandos.md
@@ -0,0 +1,60 @@
+exemplo de adição
-exemplo de remoção
```

`git log --graph` - Exibe o histórico de commits em forma de grafo.
Exemplo:
```
* commit 303339108f79450d57bc38c940530272da84560f
| Author: Carto1a <49589600+Carto1a@users.noreply.github.com>
| Date:   Thu May 9 10:12:46 2024 -0300
|
|     feat: Basico de Git
|
* commit 008c2c5e9652615974b29a5d5bfa6e26362ff2d1
  Author: Carto1a <49589600+Carto1a@users.noreply.github.com>
  Date:   Thu May 9 09:32:54 2024 -0300

      init
```

`git log --format=<format>` - Exibe o histórico de commits com um formato personalizado.
Exemplo:
```
git log --pretty="%H %an"
53efe2e9dede8023cbc74b31693b3326fe92cdb4 Carto1a
7213f084f079ba27568b09cee0f94942f40ad11f Carto1a
81a1fc1af5f41d7a90f0599c8993e7fd5b698e2c Carto1a
654f51709067f4d58606c914642438a572b2b97f Carto1a
303339108f79450d57bc38c940530272da84560f Carto1a
008c2c5e9652615974b29a5d5bfa6e26362ff2d1 Carto1a
```

para saber mais ->

## status
O comando `git status` é uma ferramenta essencial no Git que permite aos desenvolvedores verificar o estado atual do repositório. Ele fornece informações sobre arquivos modificados, arquivos adicionados, arquivos removidos, e o estado da área de preparação (staging area)

`git status [<options>] [--] [<pathspec>…]`

### Opções comuns:
`git status` - Exibe o estado atual do repositório.

## diff
O comando `git diff` é utilizado no Git para exibir as diferenças entre os arquivos no seu diretório de trabalho e o estado atual da área de preparação (staging area), ou entre commits, branches, ou qualquer outro ponto de referência no histórico do Git.
```
git diff [<options>] [<commit>] [--] [<path>…]
git diff [<options>] --cached [--merge-base] [<commit>] [--] [<path>…]
git diff [<options>] [--merge-base] <commit> [<commit>…] <commit> [--] [<path>…]
git diff [<options>] <commit>…<commit> [--] [<path>…]
git diff [<options>] <blob> <blob>
git diff [<options>] --no-index [--] <path> <path>
```

### Opções comuns:
`git diff` - Exibe as diferenças entre os arquivos no diretório de trabalho e o estado atual da área de preparação (staging area).

`git diff --cached` - Exibe as diferenças entre os arquivos na área de preparação (staging area) e o último commit.

`git diff <commit>` - Exibe as diferenças entre os arquivos no diretório de trabalho e um commit específico.

`git diff <commit> <commit>` - Exibe as diferenças entre dois commits específicos.

`git diff <branch>` - Exibe as diferenças entre os arquivos no diretório de trabalho e um branch específico.

`git diff <branch>..<branch>` - Exibe as diferenças entre dois branches específicos.

`git diff --name-only` - Exibe apenas os nomes dos arquivos que foram modificados.

`git diff --stat` - Exibe estatísticas resumidas das diferenças.

## blame
## show
O comando `git show` é utilizado no Git para exibir informações detalhadas sobre um commit específico. Ele mostra as alterações introduzidas por um commit, juntamente com metadados como autor, data e hora do commit, e a mensagem associada ao commit.

`git show [<options>] [<object>...]`

### Opções comuns:
`git show` - Exibe informações detalhadas sobre o commit mais recente.famoso `git show HEAD`.

`git show [inicio ou toda a hash de um commit]` - Exibe informações detalhadas sobre um commit específico. um git log -p para um commit específico.

# Modificação de arquivos
## rm
## mv

# Outros
## tag
## submodule
## stash
## bisect
## clean
## cherry-pick
## switch
## restore




