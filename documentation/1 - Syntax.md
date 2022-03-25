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

// Arquivo: test.v
use test
```


#### Tipos primitivos
```javascript
var variable :int       = 31337;
var variable :uint      = 31337;
var variable :float     = 3.1337;
var variable :double    = 3.1337;
var variable :bool      = true;
var variable :char      = 'V';
var variable :str       = "Verbum 😃";
```


#### Array
```javascript
var variable :array = [ 3, 1, 3, 3, 7 ];
var variable :array = [ 'V', true, "Verbum 😃" ];
var variable :array = [ 10 :int, 20 :uint, 30.3, 40 :float, n ];
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
```

#### OOP
```
class
attributes
method
instance / new
```


