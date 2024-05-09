O arquivo `.gitignore` é um arquivo de configuração que diz ao git quais arquivos e pastas ele deve ignorar. Isso é útil para evitar que arquivos temporários, arquivos de configuração e outros arquivos desnecessários sejam incluídos no repositório. Caso arquivos e pastas indesejados ja estejam sendo rastreados, você pode removê-los do repositório com o comando `git rm --cached <arquivo>`.

# Lembre-se

não crie o arquivo `.gitignore` manualmente, use os templates desse [repositório](https://github.com/github/gitignore) ou [site](https://www.toptal.com/developers/gitignore)

# Onde colocar e oque colocar

- `.gitignore`: pode ser colocado na raiz do repositório ou em qualquer subdiretório, sendo a prioridade o `.gitignore` dos subdiretórios.

- `$GIT_DIR/info/exclude`: é um arquivo local que ignora arquivos apenas no repositório local, não é compartilhado com outros colaboradores.

- `core.excludesFile`: é um arquivo global que ignora arquivos em todos os repositórios, pode ser configurado com o comando `git config --global core.excludesFile [arquivo gitignore]`.

# Patterns

- `*`: é usado para corresponder a zero ou mais caracteres. Por exemplo, `*.txt` corresponde a todos os arquivos `.txt`. Ele so reconhece tudo menos `/`.

- `#`: é usado para comentários. Coloque um `\#` para ignorar arquivos que começam com `#`.

- ` `: espaços em branco são ignorados. Espaços em branco no final da linha são ignorados, caso queira incluir um espaço em branco no final da linha, use `\ `.

- `!`: é usado para negar um padrão. Por exemplo, `*.txt` ignora todos os arquivos `.txt`, mas `!arquivo.txt` não ignora o arquivo `arquivo.txt`. Caso um arquivo comece com `!`, use `\!`.

- `/`: é usado para corresponder a um diretório. Por exemplo, `diretorio/` ignora todos os arquivos no diretório `diretorio`. Eles podem estar no inicio, meio ou final do pattern. O separador é relativo a localização do `.gitignore`. Se so estiver no final, ele ignora apenas o diretório, se estiver no inicio ou meio, ele ignora o diretório e seus subdiretórios.

- `?`: é usado para corresponder a um único caractere. Por exemplo, `arquivo?.txt` corresponde a `arquivo1.txt`, `arquivo2.txt`, etc. Ele não reconhece `/`.

- `[]`: é usado para corresponder a um único caractere de um conjunto de caracteres. Por exemplo, `arquivo[123].txt` corresponde a `arquivo1.txt`, `arquivo2.txt`, `arquivo3.txt`.

    - `-`: é usado para definir um intervalo de caracteres. Por exemplo, `arquivo[a-z].txt` corresponde a `arquivoa.txt`, `arquivob.txt`, etc.

- `**`: é usado para corresponder a zero ou mais diretórios. Por exemplo, `diretorio/**/arquivo.txt` corresponde a `diretorio/arquivo.txt`, `diretorio/subdiretorio/arquivo.txt`, etc.

