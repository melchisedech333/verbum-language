### :arrow_right: Descrição geral da sintaxe Verbum.

#### Comentários
```
// Comentário de única linha.

/*
    Comentário de
    múltiplas linhas.
*/
```


#### Importações
```php
// Biblioteca padrão.
use std:io
use std:net

// Arquivo: test.v.
use test

// Arquivo: path/test.v
use path/test

// Multiplas declarações.
use std:io, std:net, test

// Meslcando todos os modos.
use std:io, path/test, other
```


#### Tipos primitivos
```javascript
var variable :int       = 31337;
var variable :uint      = 31337;
var variable :float     = 3.1337;
var variable :double    = 3.1337;
var variable :bool      = true;
var variable :str       = "Verbum 😃";
```


#### Constantes.
```javascript
var variable :const     = 31337;
var variable :const     = 3.1337;
var variable :const     = true;
var variable :const     = "Verbum 😃";
```


#### Array
```javascript
var variable :array = [ 3, 1, 3, 3, 7 ];
var variable :array = [ 'V', true, "Verbum 😃" ];
var variable :array = [ 10 :int, 20 :uint, 30.3, 40 :float, true, n ];
var variable :array = [ ];

var variable :array = [
    1, 2, 3,
    [
        'a', 'b', 'c',
        "Verbum", "Divinus",
        3.1337
    ],
    [
        a, b, c,
        10 :int, 20 :uint, 30 :float
    ]
];

var variable :array = [
    name: "Verbum",
    value: "Divinus"
];

var variable :array = [
    [ name: "Verbum" ],
    [ name: "Divinus" ],
];

var variable :array = [
    items: [
        [ name: "Verbum" ],
        [ name: "Divinus" ],
    ]
];

```


#### Condicionais
```python
if (expression) 
    print("value 1");
elif (expression)
    print("value 2");
else
    print("value 3");
```

#### Loops
```c++
for (int a =0; a<100; a++)
    print("Hello world\n");
```

#### Funções
```rust
fn example (a: int, b: int) -> int {
    ret (a * b) + 31337;
}

fn primary (a: int, b: int) -> int {
    fn secondary (a: int, b: int) -> int {
        ret (a * b) + 31337;
    }

    ret secondary(a, b);
}
```


#### Operadores
```mysql
// Aritméticos.
+           Soma
-           Subtração
*           Multiplicação
/           Divisão
%           Módulo
++          Incremento
--          Decremento

// Relacionais.
==          Igual
!=          Não igual
>           Maior que
<           Menor que
>=          Maior ou igual
<=          Menor ou igual
```


#### OOP
#### Estrutura geral

```javascript
space station

class Example {
    priv var attributeA :uint = 31337;
    priv var attributeB :str  = "Verbum 😃";

    Example (a: uint, b :str) {
        this.attributeA = a;
        this.attributeB = b;
    }

    pub fn getValues () -> [] {
        ret [
            this.attributeA,
            this.attributeB
        ];
    }
}

var obj :Example = new Example(31337, "Verbum");
var result :array = obj.getValues();

print("a: {}, b: {}\n", result[0], result[1]);
```


