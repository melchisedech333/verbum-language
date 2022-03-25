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
()                      Definição de escopo (expressões)
{}                      Definição de escopo (código), e inclusão de dados em strings
[]                      Definição de escopo de array
;                       Finalização de comando
: ->                    Prefixação para uso tipos, uso nas importações, e declaração em arrays associativos
.                       Acessa elemento de objeto, e arrays
\                       Caracteres especiais dentro de strings
<>                      Utilizado com o comando "use" para importar múltiplos pacotes, especificar o tipo em arrays associativos
" '                     Aspas simples e duplas são aceitas para caracteres e strings
/**/ //                 Comentários
```


#### Comandos especiais
```
use                     Importação de módulos / bibliotecas
var                     Declaração de variáveis
if, elif, else          Condicionais
for, break, next        Loops
fn                      Funções
ret                     Retorno usado em funções e métodos

space                   Definição de área (semelhante a namespace e package)
class                   Definição de classe
extends                 Realização de herança
pub, priv, pro, static  Definição de atributos e métodos
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
use std:<io,net>, test

// Meslcando todos os modos.
use std:io, path/test, other

// Todos arquivos dentro de um pacote ou diretório.
use std:*
use path/*
```


#### Tipos simples
```javascript
// Para valores comuns o tipo é inferido automaticamente.
// Os caracteres e strings são UNICODE.
var variable :int       = 31337;
var variable :float     = 1.337;
var variable :double    = 3.1337;
var variable :bool      = true;
var variable :char      = '♥';
var variable :str       = 'Verbum 😍';

// O UNICODE é aceito no uso comum da linguagem.
var λ = 'Verbum ♥';
var π = 3.14;
```


#### Constantes
```javascript
// Constantes aceitam apenas valores comuns.
var variable :const     = 31337;
var variable :const     = 3.1337;
var variable :const     = true;
var variable :const     = "Verbum 😍";
```


#### Array
```javascript
// Indexados, com acesso via número do index.
var variable :array = [ 3, 1, 3, 3, 7 ];
var variable :array = [ 'V', '♥', true, "Verbum 😍" ];
var variable :array = [ 10 :int, 20 :int, 30.3, 40 :float, true, n ];
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
        10 :int, 20 :int, 30 :float
    ]
];

// Associativos, com acesso via chave/hash.
var variable :array = {
    items: [
        { name: "Verbum"  },
        { name: "Divinus" },
        {
            values: [
                10, 20, 30:float, { name: "Member" }
            ]
        },
        31337
    ]
};

var variable = {
    value: 1.337 <:double> // Neste caso, quando necessário especificar o tipo
                           // usa-se as setas laterais de abetura e fechamento.
};

// Exemplo de acessos em arrays associativos.
variable.items[0].name              // Verbum
variable.items[1].name              // Divinus
variable.items[2].values[0]         // 10
variable.items[2].values[3].name    // Member
variable.items[3]                   // 31337

// Outros exemplos.
var variable : array = [
    { name: "Verbum" },
    10, 20, 30,
    {
        values: [
            31337 :double, { name: "Divinus" }
        ] 
    }
];

// Função como elemento de um array.
// Com arrays indexados.
var variable = [
    31337,
    fn (a :int, b :int) -> int {
        ret a + b;   
    }
];

var value = variable[1](10, 20);

// Com arrays associativos.
var variable = {
    identifier : 'onclick',
    callback   : fn (a :int, b :int) -> int {
        ret a + b;   
    }
};

var value = variable.callback(10, 20);
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
for (a:int = 0; a<100; a++)
    print("Hello world\n");

for (a:int = 0; ; a++) {
    if (a >= 100)
        break;
}

for (a:int = 0; ; a++) {
    if (a < 100)
        next;
}
```

#### Funções
```rust
// Uso comum.
fn example (a: int, b: int) -> int {
    ret (a * b) + 31337;
}

// Concatenação de funções.
fn primary (a: int, b: int) -> int {
    var value = 31337;

    fn secondary (a: int, b: int) -> int {
        ret (a * b) + value;
    }

    ret secondary(a, b);
}

// Funções anonimas.
print("Value: {}\n", 
    (fn (value :int) -> int { 
        ret value * 3; 
    })(31337)
);
```

---
#### OOP

<b>Conceitos:</b>
- Interface: definição dos métodos que devem necessariamente ser implementados.
- Abstração: permite criar uma abstração de uma classe, contendo métodos não implementados (abstratos). É um mecanismo que representa os recursos essenciais sem incluir detalhes de implementação. Ou seja, ocultação de implementação.
- Herança: quando uma classe ou interface, herda as propriedades de outra.
- Encapsulamento/visibilidade: com os comandos pub, priv e pro, se define a visibilidade dos atributos e métodos. Encapsulamento é o empacotamento de "dados" e "funções operando nesses dados" em um único componente e restringindo o acesso a alguns dos componentes do objeto. Encapsulamento significa que a representação interna de um objeto geralmente fica oculta fora da definição do objeto. Ou seja, ocultação de implementação.
- Polimorfismo estático (sobrecarga): quando há vários métodos com o mesmo nome, mas com assinatura diferente (todos válidos).
- Polimorfismo dinâmico (sobrescrita): quando se sobrescreve um método herdado de uma outra classe.

```php
// Interface comum...
interface FirstTemplate {
    pub fn getValues () -> array;
    pub fn getValues (index :int) -> int;
}

// Interface com herança.
interface ExampleTemplate extends FirstTemplate {
    pub fn checkString (string :str);
}

// Classe abstrata.
class AbstractClass {
    abstract pro fn abstractMethod ();
}

// Classe.
class Common extends AbstractClass {
    // ...
    pub fn checkString (string :str) -> int { /* ... */ }

    // Implementa método abstrato.
    pro fn abstractMethod () {
        // ...
    }
}

// Classe com herança e implementação de interface.
class Example extends Common implements ExampleTemplate {

    // Atributos.
    priv var attributeA :uint = 31337;
    pub var attributeB :str  = "Verbum 😃";

    // Construtor.
    Example (a: uint, b :str) {
        this.attributeA = a;
        this.attributeB = b;
    }

    // Declaração dos métodos e sobrecarga.
    pub fn getValues () -> array {
        ret [
            this.attributeA,
            this.attributeB
        ];
    }

    pub fn getValues (index :int) -> int {
        if (index == 1)
            ret this.attributeA;
        ret -1;
    }

    // Sobrescreve método herdado (polimorfismo).
    pro fn abstractMethod () {
        print("Verbum\n");
    }
}

// Instanciamento e uso.
var obj     :Example  = new Example(31337, "Verbum");
var resultA :array    = obj.getValues();
var resultB :int      = obj.getValues(1);
var resultC :int      = obj.checkString("Verbum Divinus");

print("ResultA = a: {}, b: {}\n", resultA[0], resultA[1]);
print("resultB = {}\n", resultB);
print("Check String = {}\n", resultC);

```


