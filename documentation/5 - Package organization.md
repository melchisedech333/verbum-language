### :arrow_right: Organização dos pacotes.

Sintaxe do comando <b>use</b>:
```php
use PACKAGE:MODULE-MAIN-FILE
use PACKAGE
```

Exemplo:
```php
use std:io
use string
```

- <b>std</b> = nome do pacote.
- <b>io</b> = nome do arquivo (exports) do módulo (opcional).

<b>Obs:</b> quando não se especifica o nome do módulo, o interpretador insere o mesmo com o mesmo nome do pacote. Por exemplo, ficando: <b>use string:string</b>.

---

Organização do diretório (para um único módulos):
```
- string                        # directory:            nome do pacote
|- package.json                 # file:                 configurações do pacote
|- string.v                     # file:                 arquivo de referência do módulo
```

Organização do diretório (para múltiplos módulos):
```
- std                           # directory:            nome do pacote
|- package.json                 # file:                 configurações do pacote
|- io.v                         # file:                 arquivo de referência do módulo
|- io                           # directory (optional): arquivos do módulo
|- net.v                        # file:                 ...
|- net                          # directory (optional): ...
```

---

#### Funcionamento do carregamento do pacote e módulo.

O interpretador irá executar um arquivo inicial, onde este arquivo, por sua vez, poderá utilizar N pacotes.
Ao iniciar a execução, o diretório raiz onde encontra-se o arquivo que foi inicialmente executado, será utilizado como diretório raiz da aplicação.

Existem dois diretórios raízes:
- O diretório raiz da aplicação (com base no arquivo de código Verbum).
- O diretório onde está instalado o interpretador.

Um pacote é definido por um diretório (com seu nome), e um arquivo de configuração (package.json):

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

Ao executar o instalador do pacote em questão, serão baixadas todas as dependências especificadas em <b>dependencies</b>, e assim sucessivamente, até concluir todos os downloads. Em seguida é verificado a versão dos pacotes. Estando tudo em ordem, o pacote pode ser utilizado nas aplicações Verbum.

Por padrão as dependências do pacote ficam instaladas e disponíveis para todos (instaladas no diretório de instalação da linguagem).
Mas pode-se escolher entre manter as dependências no diretório atual do pacote em questão, ou instalar para uso permanente.

<b>>Pontos importantes:</b>
- Se o pacote é de módulo único, é necessário criar um arquivo dentro do diretório do pacote, com o mesmo nome do diretório, sendo este o nome do próprio pacote. Pois neste arquivo ficará a interface para uso do pacote.
- Se o pacote é de múltiplos módulos (como é o caso da biblioteca padrão contendo módulos: io, net; dentre outros), para cada módulo que será usado posteriormente, é necessário criar um arquivo de interface.






