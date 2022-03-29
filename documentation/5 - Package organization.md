### :arrow_right: Organização dos pacotes.

Sintaxe do comando <b>use</b>:
```java
use 'PACKAGE:MODULE-MAIN-FILE'
use 'MODULE-FILE'
```

Exemplo:
```java
use 'std:io'        // Importa módulo 'io' de pacote 'std'.
use 'std:io/file'   // Importa módulo 'file', que está dentro do 
                    // módulo 'io', que por sua vez pertence ao pacote 'std';
use 'string'        // Importa arquivo string.verbum do diretório em questão.
use 'path/file'     // Importa arquivo file.verbum do diretório 'path'.
```

- <b>std</b> = nome do pacote instalado permanentemente.
- <b>io</b> = nome do arquivo do módulo.
- <b>io/file</b> = path do módulo de interesse.


#### Estrutura de pacote.

```
- std                           # directory:            nome do pacote
|- package.json                 # file:                 configurações do pacote
|- io.verbum                    # file:                 arquivo de referência do módulo
|- io                           # directory (optional): arquivos do módulo
|--- file.verbum                # ...
|- net.verbum                   # file:                 ...
|- net                          # directory (optional): ...
```

Exemplo de uso:
```java
use 'std:io'

io.print('Hello world!\n');
```

Um módulo é definido por um arquivo verbum. Opcionalmente pode existir sub-diretórios dentro do diretório do pacote. O ideal, caso necessário, é criar um diretório com o mesmo nome do módulo, para dentro dele implementar o sistema do módulo. Deste modo os arquivos Verbum que ficam dentro do diretório do pacote (std), são todos arquivos de interface para importações.


#### Funcionamento do carregamento do pacote e módulo.

O interpretador irá executar um arquivo inicial, onde este arquivo, por sua vez, poderá utilizar N pacotes.
Ao iniciar a execução, o diretório raiz onde encontra-se o arquivo que foi inicialmente executado, será utilizado como diretório raiz da aplicação.

Existem dois diretórios raízes:
- O diretório raiz da aplicação (com base no arquivo de código Verbum).
- O diretório onde está instalado o interpretador (onde ficam os módulos instalados de modo permanente).

Um pacote é definido por:
- Um diretório com seu nome (por explode: <b>std</b>)
- Um arquivo de importação contendo o mesmo nome do diretório (que é o nome do pacote)
- Um arquivo de configuração <b>package.json</b>

```json
{
    "name": "std",
    "version": "1.0.0",
    "description": "Biblioteca padrão da linguagem Verbum",
    "license": "MIT",

    "repository": {
        "type": "git",
        "url": "https://github.com/melchisedech333/verbum-language.git"
    },

    "author": {
        "name": "Melch1sed3ch",
        "email": "fulano@site.com",
        "url": "http://melchisedech333.github.io/"
    },

    "dependencies": [
        {
            "name": "Biblioteca XYZ",
            "version": ">=1.0.0",
            "repository": {
                "type": "git",
                "url": "https://github.com/melchisedech333/verbum-language.git"
            },
        }
    ]
}
```

Ao executar o instalador do pacote em questão, serão baixadas todas as dependências especificadas em <b>dependencies</b>, e assim sucessivamente, até concluir todos os downloads. Conjuntamente é verificado a versão dos pacotes. Estando tudo em ordem, o pacote pode ser utilizado nas aplicações Verbum.

Por padrão as dependências do pacote ficam instaladas e disponíveis para todos (instaladas no diretório de instalação da linguagem).
Mas pode-se escolher entre manter as dependências no diretório atual do pacote em questão, ou instalar para uso permanente (noção semelhante ao npm).


#### Exemplo de arquivo de interface

<b>Arquivo: io.verbum</b>

```java
use 'string'
use 'io/file'
use 'data-converter:example'

// Define interface.
interface IOInterface {
    fn print (string :str);
}

// Implementa.
class IO implements IOInterface {
    fn print (string :str) {
        _verbum_internal_print(string);
    }
}

// Cria variável global.
var io = new IO();
```

<b>Importação e uso:</b>

```java
use 'std:io'

io.print("Verbum\n");
```

#### Exemplo de interface de sub-módulo

<b>Arquivo: io/file.verbum</b>

```java
use 'string'
use 'data-converter:example'

// Define interface.
interface IOFileInterface {
    fn open (path :str) -> stream;
}

// Implementa.
class IOFile implements IOFileInterface {
    fn print (string :str) -> stream {
        _verbum_internal_open(string);
    }
}

// Cria variável global.
var file = new IOFile();
```

<b>Importação e uso:</b>

```java
use 'std:io/file'

var fp = file.open("archive.txt");
```


