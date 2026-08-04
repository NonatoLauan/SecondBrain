# Variáveis e Tipos de Dados

## O que são variáveis?

Uma variável é um espaço na memória do computador usado para armazenar informações que podem ser utilizadas e modificadas durante a execução de um programa.

Pense em uma variável como uma "caixa" que possui:

- um nome;
- um valor armazenado;
- um tipo de dado.

Exemplo:

```php
$nome = "Nonato";
```

Nesse caso:

```
Nome da variável:
nome

Valor armazenado:
"Nonato"

Tipo:
String
```

---

# Por que usamos variáveis?

Sem variáveis, precisaríamos escrever os valores diretamente no código.

Exemplo sem variável:

```php
echo "Nonato";
echo "Nonato";
echo "Nonato";
```

Problema:

Se o nome mudar, precisamos alterar vários lugares.

Com variável:

```php
$nome = "Nonato";

echo $nome;
echo $nome;
echo $nome;
```

Agora basta alterar uma vez:

```php
$nome = "João";
```

Todas as utilizações recebem o novo valor.

---

# Como uma variável funciona na memória?

Quando criamos uma variável:

```php
$idade = 24;
```

O computador reserva um espaço na memória.

Representação:

```
Memória

+-------------+
| idade       |
|-------------|
| 24          |
+-------------+
```

Quando usamos:

```php
echo $idade;
```

O programa procura o valor guardado naquela posição.

Resultado:

```
24
```

---

# Declaração e atribuição

## Declaração

Criar uma variável.

Exemplo:

```php
$nome;
```

A variável existe, mas ainda não possui valor.

---

## Atribuição

Colocar um valor na variável.

Exemplo:

```php
$nome = "Maria";
```

O operador:

```
=
```

significa:

"receba"

Não significa igualdade matemática.

Exemplo:

```php
$idade = 24;
```

Leia:

"idade recebe 24"

---

# Alterando valores de variáveis

Variáveis podem mudar durante a execução.

Exemplo:

```php
$saldo = 100;

$saldo = 150;
```

Primeiro:

```
saldo → 100
```

Depois:

```
saldo → 150
```

O valor antigo é substituído.

---

# Regras para nomes de variáveis

Cada linguagem possui regras próprias.

Em PHP:

## Deve começar com $

Exemplo:

```php
$nome;
```

---

## Não pode começar com número

Errado:

```php
$1nome;
```

Correto:

```php
$nome1;
```

---

## Não pode ter espaços

Errado:

```php
$nome completo;
```

Correto:

```php
$nomeCompleto;
```

---

## Pode usar números depois da primeira letra

Exemplo:

```php
$usuario1;
```

---

## Evite nomes genéricos

Ruim:

```php
$x;
$a;
```

Bom:

```php
$quantidadeBobinas;
$usuarioLogado;
```

O nome deve explicar o que guarda.

---

# Boas práticas para nomes

Use nomes descritivos.

Ruim:

```php
$x = 10;
```

Bom:

```php
$quantidadeProdutos = 10;
```

---

Use camelCase:

```php
$nomeUsuario;
$dataCadastro;
$valorTotal;
```

---

Evite abreviações:

Ruim:

```php
$qtdBob;
```

Melhor:

```php
$quantidadeBobinas;
```

---

# Tipos de dados

Um tipo de dado define qual tipo de informação uma variável pode guardar.

Exemplos:

```
Texto
Número
Verdadeiro/Falso
Lista
Objeto
```

O tipo define:

- como o valor será armazenado;
- quais operações podem ser feitas;
- quanto espaço ocupa na memória.

---

# String

## O que é?

String representa textos.

Exemplos:

```php
$nome = "João";

$email = "joao@email.com";
```

Strings são conjuntos de caracteres.

Exemplo:

```
J
o
ã
o
```

---

## Strings podem conter números

Exemplo:

```php
$codigo = "12345";
```

Apesar de ter números, é texto.

Diferença:

```php
$numero = 12345;
```

Número.

```php
$codigo = "12345";
```

Texto.

---

## Operações com strings

Concatenação:

```php
$nome = "João";

echo "Olá " . $nome;
```

Resultado:

```
Olá João
```

---

# Integer (int)

## O que é?

Representa números inteiros.

Sem casas decimais.

Exemplos:

```php
$idade = 24;

$quantidade = 10;
```

Valores:

```
0
1
2
100
-5
```

---

# Float

## O que é?

Representa números decimais.

Exemplos:

```php
$preco = 10.50;

$altura = 1.83;
```

Possuem casas decimais.

---

# Boolean

## O que é?

Representa apenas dois estados:

```
true
false
```

Verdadeiro ou falso.

Exemplo:

```php
$usuarioAtivo = true;
```

Uso comum:

- permissões;
- status;
- validações.

Exemplo:

```php
if ($usuarioAtivo) {

    echo "Usuário liberado";

}
```

---

# Null

## O que é?

Representa ausência de valor.

Exemplo:

```php
$telefone = null;
```

Significa:

"essa variável existe, mas não possui valor."

---

Diferença:

String vazia:

```php
$nome = "";
```

Tem valor.

Null:

```php
$nome = null;
```

Não tem valor.

---

# Array

## O que é?

Um array é uma estrutura que guarda vários valores dentro de uma única variável.

Exemplo:

```php
$usuarios = [
    "João",
    "Maria",
    "Pedro"
];
```

Representação:

```
usuarios

0 → João
1 → Maria
2 → Pedro
```

---

# Array associativo

Usa chaves nomeadas.

Exemplo:

```php
$usuario = [
    "nome" => "João",
    "idade" => 24
];
```

Representação:

```
usuario

nome → João

idade → 24
```

---

# Object

## O que é?

Objeto representa uma entidade com dados e comportamentos.

Exemplo:

```php
$usuario->nome;
```

Um objeto pode possuir:

Dados:

```
nome
idade
email
```

Comportamentos:

```
salvar()
editar()
excluir()
```

Muito usado em programação orientada a objetos.

---

# Tipagem dinâmica

PHP é uma linguagem de tipagem dinâmica.

Isso significa que o tipo é definido automaticamente pelo valor.

Exemplo:

```php
$valor = 10;
```

PHP entende:

```
valor = Integer
```

Depois:

```php
$valor = "dez";
```

Agora:

```
valor = String
```

O tipo mudou.

---

# Verificando o tipo de uma variável

PHP possui:

```php
var_dump();
```

Exemplo:

```php
$idade = 24;

var_dump($idade);
```

Resultado:

```
int(24)
```

---

Outro exemplo:

```php
$nome = "João";

var_dump($nome);
```

Resultado:

```
string(4) "João"
```

---

# Conversão de tipos (Type Casting)

Às vezes precisamos transformar um tipo em outro.

Exemplo:

String:

```php
$numero = "10";
```

Transformar em inteiro:

```php
$numero = (int) $numero;
```

Agora:

```
10
```

é um número.

---

# Conversões comuns

String para inteiro:

```php
(int)
```

String para float:

```php
(float)
```

Para boolean:

```php
(bool)
```

---

# Diferença entre valor e referência

Normalmente uma variável guarda um valor.

Exemplo:

```php
$a = 10;

$b = $a;
```

Resultado:

```
a → 10

b → 10
```

São independentes.

Alterar:

```php
$b = 20;
```

Não altera:

```
a → 10
```

---

# Constantes

Uma constante é um valor que não muda.

Variável:

```php
$idade = 24;
```

Pode mudar.

Constante:

```php
define("PI", 3.14);
```

Não deve mudar.

Uso comum:

- configurações;
- valores fixos;
- regras do sistema.

---

# Variável dentro do fluxo do programa

Exemplo:

```php
$preco = 100;

$desconto = 10;

$total = $preco - $desconto;

echo $total;
```

Execução:

1. Guarda 100 em `$preco`.
2. Guarda 10 em `$desconto`.
3. Calcula.
4. Guarda resultado em `$total`.
5. Exibe.

Resultado:

```
90
```

---

# Resumo dos principais tipos

| Tipo | Guarda | Exemplo |
|---|---|---|
| String | Texto | `"João"` |
| Integer | Número inteiro | `24` |
| Float | Número decimal | `1.83` |
| Boolean | Verdadeiro/Falso | `true` |
| Null | Ausência de valor | `null` |
| Array | Lista de valores | `["A","B"]` |
| Object | Objetos | `$usuario` |

---

# Perguntas que um programador deve fazer ao criar uma variável

1. O que essa variável representa?
2. Qual tipo de dado ela guarda?
3. O nome está claro?
4. Ela precisa mudar ou deveria ser uma constante?
5. Qual parte do código precisa acessar esse valor?

---

# Conceito principal

Uma variável é uma forma de dar um nome a um valor armazenado na memória.

O programa usa esse nome para acessar, modificar e manipular informações durante sua execução.