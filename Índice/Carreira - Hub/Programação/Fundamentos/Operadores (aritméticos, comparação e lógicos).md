# Operadores em Programação

## O que são operadores?

Operadores são símbolos ou palavras reservadas usados para realizar operações com valores e variáveis.

Eles permitem:

- fazer cálculos;
- comparar informações;
- tomar decisões;
- combinar condições.

Exemplo:

```php
$idade = 24;

if ($idade >= 18) {
    echo "Maior de idade";
}
```

Nesse caso:

```
>=
```

é um operador de comparação.

---

# Tipos de operadores

Os principais tipos são:

1. Operadores aritméticos
2. Operadores de comparação
3. Operadores lógicos

---

# 1. Operadores Aritméticos

São usados para realizar operações matemáticas.

Principais operadores:

| Operador | Nome | Exemplo |
|---|---|---|
| + | Soma | `$a + $b` |
| - | Subtração | `$a - $b` |
| * | Multiplicação | `$a * $b` |
| / | Divisão | `$a / $b` |
| % | Módulo (resto) | `$a % $b` |
| ** | Potência | `$a ** $b` |

---

# Soma (+)

Adiciona valores.

Exemplo:

```php
$a = 10;
$b = 5;

$resultado = $a + $b;
```

Resultado:

```
15
```

---

# Subtração (-)

Remove um valor de outro.

```php
$saldo = 100;

$gasto = 30;

$resultado = $saldo - $gasto;
```

Resultado:

```
70
```

---

# Multiplicação (*)

Multiplica valores.

```php
$preco = 10;

$quantidade = 5;

$total = $preco * $quantidade;
```

Resultado:

```
50
```

---

# Divisão (/)

Divide valores.

```php
$total = 100;

$pessoas = 5;

$resultado = $total / $pessoas;
```

Resultado:

```
20
```

---

# Módulo (%)

Retorna o resto de uma divisão.

Exemplo:

```php
$resultado = 10 % 3;
```

Cálculo:

```
10 dividido por 3

3 x 3 = 9

resto = 1
```

Resultado:

```
1
```

---

## Uso comum do módulo

Verificar se um número é par.

```php
$numero = 10;

if ($numero % 2 == 0) {

    echo "É par";

}
```

Explicação:

```
10 dividido por 2

resto = 0

então é par
```

---

# Incremento e decremento

Servem para aumentar ou diminuir valores.

## Incremento (++)

Adiciona 1.

```php
$contador++;

```

Equivale a:

```php
$contador = $contador + 1;
```

---

## Decremento (--)

Remove 1.

```php
$contador--;
```

Equivale a:

```php
$contador = $contador - 1;
```

---

# Operadores de atribuição

O operador básico:

```php
=
```

Atribui um valor.

Exemplo:

```php
$nome = "João";
```

---

Também existem operadores combinados:

| Operador | Significado |
|---|---|
| += | soma e atribui |
| -= | subtrai e atribui |
| *= | multiplica e atribui |
| /= | divide e atribui |

---

Exemplo:

```php
$saldo = 100;

$saldo += 50;
```

É igual a:

```php
$saldo = $saldo + 50;
```

Resultado:

```
150
```

---

# 2. Operadores de Comparação

São usados para comparar valores.

Eles sempre retornam:

```
true
```

ou

```
false
```

Ou seja:

```
Verdadeiro
ou
Falso
```

---

# Igualdade (==)

Verifica se os valores são iguais.

Exemplo:

```php
10 == 10
```

Resultado:

```
true
```

---

Exemplo:

```php
$idade = 18;

if ($idade == 18) {

    echo "Tem 18 anos";

}
```

---

# Igualdade estrita (===)

Compara:

- valor;
- tipo.

Exemplo:

```php
10 === "10"
```

Resultado:

```
false
```

Porque:

```
10 → inteiro

"10" → texto
```

Mesmo valor visual, tipos diferentes.

---

# Diferença (!=)

Verifica se os valores são diferentes.

```php
10 != 5
```

Resultado:

```
true
```

---

# Diferença estrita (!==)

Compara valor e tipo.

```php
10 !== "10"
```

Resultado:

```
true
```

---

# Maior que (>)

```php
10 > 5
```

Resultado:

```
true
```

---

# Menor que (<)

```php
5 < 10
```

Resultado:

```
true
```

---

# Maior ou igual (>=)

```php
18 >= 18
```

Resultado:

```
true
```

---

# Menor ou igual (<=)

```php
17 <= 18
```

Resultado:

```
true
```

---

# Exemplo prático

Sistema de acesso:

```php
$idade = 20;

if ($idade >= 18) {

    echo "Acesso permitido";

}
```

O programa pergunta:

```
idade é maior ou igual a 18?
```

Resposta:

```
true
```

Executa o bloco.

---

# 3. Operadores Lógicos

Servem para combinar várias condições.

Principais:

| Operador | Nome | Significado |
|---|---|---|
| && | AND | E |
| || | OR | OU |
| ! | NOT | Não |

---

# AND (&&)

Todas as condições precisam ser verdadeiras.

Exemplo:

```php
$idade = 20;
$temCarteira = true;

if ($idade >= 18 && $temCarteira) {

    echo "Pode dirigir";

}
```

O programa verifica:

```
Tem idade suficiente?
E
Tem carteira?
```

Se:

```
idade = true

carteira = true
```

Resultado:

```
true
```

---

Tabela do AND:

| Condição 1 | Condição 2 | Resultado |
|-|-|-|
| true | true | true |
| true | false | false |
| false | true | false |
| false | false | false |

---

# OR (||)

Apenas uma condição precisa ser verdadeira.

Exemplo:

```php
$admin = true;
$gerente = false;

if ($admin || $gerente) {

    echo "Tem acesso";

}
```

Pergunta:

```
É administrador?
OU
É gerente?
```

Resultado:

```
true
```

---

Tabela do OR:

| Condição 1 | Condição 2 | Resultado |
|-|-|-|
| true | true | true |
| true | false | true |
| false | true | true |
| false | false | false |

---

# NOT (!)

Inverte um valor booleano.

Exemplo:

```php
$ativo = true;

if (!$ativo) {

    echo "Usuário inativo";

}
```

O operador:

```
!
```

transforma:

```
true → false

false → true
```

---

# Precedência de operadores

Alguns operadores são executados antes de outros.

Exemplo:

```php
$resultado = 10 + 5 * 2;
```

Primeiro:

```
5 * 2 = 10
```

Depois:

```
10 + 10 = 20
```

Resultado:

```
20
```

---

Para deixar claro:

```php
$resultado = (10 + 5) * 2;
```

Agora:

Primeiro:

```
10 + 5 = 15
```

Depois:

```
15 * 2 = 30
```

---

# Operadores em decisões

Grande parte da programação usa operadores em condições.

Exemplo:

```php
$consumo = 800;

$minimo = 750;

if ($consumo >= $minimo) {

    echo "Solicitação liberada";

} else {

    echo "Consumo insuficiente";

}
```

Fluxo:

```
Pega valores

↓

Compara

↓

Resultado true ou false

↓

Escolhe caminho
```

---

# Resumo

## Aritméticos

Usados para cálculos:

```
+
-
*
/
%
++
--
```

---

## Comparação

Usados para verificar relações:

```
==
===
!=
!==
>
<
>=
<=
```

Retornam:

```
true
false
```

---

## Lógicos

Usados para juntar condições:

```
&&  (E)

||  (OU)

!   (NÃO)
```

---

# Como pensar como programador

Sempre pergunte:

## Operação matemática:

"Preciso calcular algum valor?"

Use:

```
+ - * / %
```

---

## Decisão:

"Preciso comparar alguma coisa?"

Use:

```
== > < >= <=
```

---

## Regra com várias condições:

"Preciso juntar verificações?"

Use:

```
&& || !
```

---

# Conceito principal

Operadores são ferramentas que permitem transformar dados em decisões e comportamentos.

Variáveis guardam informações.

Operadores manipulam e analisam essas informações.

Juntos, eles formam a base da lógica de programação.