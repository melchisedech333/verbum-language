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
var variable :bool      = false;
var variable :char      = 'V';
var variable :cstr      = "Verbum";
var variable :ustr      = "Verbum 😃";
```


#### Estruturas de dados
```
array
struct
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


