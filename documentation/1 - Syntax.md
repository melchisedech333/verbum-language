### :arrow_right: Descrição geral da sintaxe Verbum.


#### Operadores
```
Aritméticos.
+                       Soma
-                       Subtração
*                       Multiplicação
/                       Divisão
%                       Módulo
++                      Incremento
--                      Decremento

Relacionais.            
==                      Igual
!=                      Não igual
>                       Maior que
<                       Menor que
>=                      Maior ou igual
<=                      Menor ou igual

Lógicos.            
!                       Not (Negação)
||                      Or (Ou)
&&                      And (E)

Atribuições.            
=                       Atribui valor
+=                      Atribui com soma
-=                      Atribui com subtração
*=                      Atribui com multiplicação
/=                      Atribui com divisão
%=                      Atribui com módulo

Outros / gerais.
()                      Definição de escopo (usado em expressões)
{}                      Definição de escopo (código), e inclusão de dados em strings
[]                      Definição de escopo de array
;                       Finalização de comando
: ->                    Prefixação para uso tipos, e importações
.                       Acessa elemento de objeto, e arrays
\                       Caracteres especiais dentro de strings
/**/ //                 Comentários
```


#### Comandos especiais
```
use                     Importação de módulos / bibliotecas
var                     Declaração de variáveis
if, elif, else          Condicionais
for                     Loops
fn                      Funções
ret                     Retorno usado em funções e métodos

space                   Definição de área (semelhante a namespace e package)
class                   Definição de classe
extends                 Realização de herança
pub, priv, static       Definição de atributos e métodos
this                    Referência ao objeto instanciado
new                     Instancia novo objeto
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
```


#### Symbol
```javascript
/// Declaração.
var variable :symbol = {
    items: [
        { name: "Verbum" },
        { name: "Divinus" },
        {
            values: [
                10, 20, 30:float, { name: "Member" }
            ]
        },
        31337
    ]
};

// Acessos.
variable.items[0].name              // Verbum
variable.items[1].name              // Divinus
variable.items[2].values[0]         // 10
variable.items[2].values[3].name    // Member
variable.items[3]                   // 31337
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


#### OOP
#### Estrutura geral

```javascript
// Namespace / Package
// Herança
// Polimorfismo
space Station

class Other {
    // ...
}

class Example extends Other {
    priv var attributeA :uint = 31337;
    pub var attributeB :str  = "Verbum 😃";

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

    pub fn getValues (index :int) -> uint {
        if (index == 1)
            ret this.attributeA;
        ret -1;
    }
}

var obj :Example   = new Example(31337, "Verbum");
var resultA :array = obj.getValues();
var resultB :uint  = obj.getValues(1);

print("ResultA = a: {}, b: {}\n", resultA[0], resultA[1]);
print("resultB = {}\n", resultB);
```


