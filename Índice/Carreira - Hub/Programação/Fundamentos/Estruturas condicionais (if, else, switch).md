# Estruturas Condicionais (if, else, switch)

## O que são estruturas condicionais?

Estruturas condicionais permitem que um programa **tome decisões**.

Elas fazem o código executar diferentes caminhos dependendo de uma condição.

O computador sempre trabalha com uma pergunta:

```
A condição é verdadeira?
```

Resultado:

```
true  → executa um bloco

false → executa outro bloco ou ignora
```

---

# Exemplo do mundo real

Problema:

> Um usuário pode fazer uma solicitação?

Regra:

```
Se o usuário estiver ativo:

    permitir solicitação

Senão:

    bloquear acesso
```

Em código:

```php
if ($usuarioAtivo) {

    echo "Permitido";

} else {

    echo "Bloqueado";

}
```

---

# Estrutura IF

## O que é?

O `if` significa:

```
SE
```

Ele executa um bloco de código apenas quando uma condição é verdadeira.

---

## Sintaxe

```php
if (condição) {

    // código executado se for verdadeiro

}
```

---

## Exemplo

```php
$idade = 20;

if ($idade >= 18) {

    echo "Maior de idade";

}
```

Fluxo:

```
idade = 20

↓

20 >= 18?

↓

true

↓

Executa mensagem
```

Resultado:

```
Maior de idade
```

---

# Condição usando comparação

Normalmente o `if` usa operadores de comparação.

Exemplo:

```php
$saldo = 100;

if ($saldo > 0) {

    echo "Possui saldo";

}
```

O programa pergunta:

```
Saldo é maior que zero?
```

---

# Condição usando boolean

Como boolean já possui true ou false, não precisa comparar.

Exemplo:

```php
$ativo = true;

if ($ativo) {

    echo "Usuário ativo";

}
```

É equivalente a:

```php
if ($ativo == true) {

}
```

---

# Estrutura IF / ELSE

## O que é?

O `else` significa:

```
CASO CONTRÁRIO
```

Ele executa quando o `if` for falso.

---

## Sintaxe

```php
if (condição) {

    // verdadeiro

} else {

    // falso

}
```

---

## Exemplo

```php
$idade = 15;

if ($idade >= 18) {

    echo "Pode entrar";

} else {

    echo "Não pode entrar";

}
```

Fluxo:

```
15 >= 18?

↓

false

↓

Executa else
```

Resultado:

```
Não pode entrar
```

---

# IF / ELSE IF / ELSE

## O que é?

Usado quando existem várias possibilidades.

Estrutura:

```php
if (condição 1) {

}
elseif (condição 2) {

}
else {

}
```

---

## Exemplo

Sistema de notas:

```php
$nota = 6;

if ($nota >= 7) {

    echo "Aprovado";

} elseif ($nota >= 5) {

    echo "Recuperação";

} else {

    echo "Reprovado";

}
```

Fluxo:

```
Nota >= 7?

Não

↓

Nota >= 5?

Sim

↓

Recuperação
```

---

# Quantos elseif posso usar?

Tecnicamente, vários.

Exemplo:

```php
if ($idade < 12) {

}
elseif ($idade < 18) {

}
elseif ($idade < 60) {

}
else {

}
```

Porém, muitos `elseif` podem deixar o código difícil de entender.

Quando existem muitas opções fixas, normalmente usamos `switch`.

---

# Operadores dentro do IF

## AND (&&)

Todas precisam ser verdadeiras.

Exemplo:

```php
$idade = 20;
$temDocumento = true;

if ($idade >= 18 && $temDocumento) {

    echo "Acesso permitido";

}
```

Regra:

```
Tem idade suficiente
E
Tem documento
```

---

## OR (||)

Uma condição basta.

```php
if ($admin || $gerente) {

    echo "Acesso liberado";

}
```

Regra:

```
É admin

OU

É gerente
```

---

## NOT (!)

Inverte.

```php
if (!$ativo) {

    echo "Usuário bloqueado";

}
```

Significa:

```
Se NÃO estiver ativo
```

---

# Condições aninhadas (Nested IF)

É um `if` dentro de outro.

Exemplo:

```php
if ($usuarioExiste) {

    if ($senhaCorreta) {

        echo "Login realizado";

    }

}
```

Fluxo:

```
Usuário existe?

↓

Sim

↓

Senha correta?

↓

Sim

↓

Entrar
```

---

# Problema dos IFs aninhados

Muitos níveis podem deixar o código difícil de ler.

Exemplo ruim:

```php
if ($usuario) {

    if ($ativo) {

        if ($permissao) {

            if ($saldo) {

            }

        }

    }

}
```

Melhor:

```php
if (!$usuario) {
    return;
}

if (!$ativo) {
    return;
}

if (!$permissao) {
    return;
}
```

Isso é chamado de:

```
early return
```

---

# Switch

## O que é?

O `switch` é usado quando temos várias opções baseadas no mesmo valor.

Ele compara uma variável com vários casos.

---

## Sintaxe

```php
switch ($variavel) {

    case valor1:

        // código

        break;


    case valor2:

        // código

        break;


    default:

        // caso nenhum seja encontrado

}
```

---

# Exemplo

Sistema de status:

```php
$status = "aprovado";


switch ($status) {

    case "aprovado":

        echo "Pedido liberado";

        break;


    case "pendente":

        echo "Aguardando análise";

        break;


    case "cancelado":

        echo "Pedido cancelado";

        break;


    default:

        echo "Status inválido";

}
```

---

# Por que existe o break?

O `break` encerra o switch.

Sem ele, o PHP pode continuar executando os próximos casos.

Exemplo:

```php
case "A":

    echo "A";


case "B":

    echo "B";
```

Pode resultar em:

```
AB
```

Com:

```php
break;
```

para no caso correto.

---

# Default

É o equivalente ao `else`.

Executa quando nenhum caso combina.

Exemplo:

```php
default:

echo "Opção inválida";
```

---

# IF vs SWITCH

## Use IF quando:

Existe uma comparação ou lógica mais complexa.

Exemplo:

```php
if ($idade >= 18 && $documento == true) {

}
```

---

## Use SWITCH quando:

Você compara uma mesma variável com valores fixos.

Exemplo:

```php
switch ($status)
```

Casos:

```
aprovado
pendente
cancelado
```

---

# Comparação prática

## Com IF:

```php
if ($status == "aprovado") {

}
elseif ($status == "pendente") {

}
elseif ($status == "cancelado") {

}
```

---

## Com SWITCH:

```php
switch ($status) {

case "aprovado":

break;

case "pendente":

break;

case "cancelado":

break;

}
```

O switch fica mais organizado.

---

# Operador ternário

Existe uma forma curta de escrever um if simples.

Sintaxe:

```php
condição ? verdadeiro : falso;
```

---

Exemplo:

```php
$idade >= 18 ? "Adulto" : "Menor";
```

Equivale a:

```php
if ($idade >= 18) {

    return "Adulto";

} else {

    return "Menor";

}
```

---

# Null coalescing (??)

Muito usado em PHP.

Serve para definir um valor padrão.

Exemplo:

```php
$nome = $_GET['nome'] ?? "Usuário";
```

Significa:

```
Se existir nome:

    usa nome

Senão:

    usa "Usuário"
```

---

# Como o computador executa uma condição

Exemplo:

```php
if ($idade >= 18) {

    echo "Pode entrar";

}
```

Execução:

```
1. Ler variável idade

↓

2. Ler valor armazenado

↓

3. Fazer comparação >=

↓

4. Resultado true ou false

↓

5. Escolher caminho

↓

6. Executar código
```

---

# Boas práticas

## Use nomes claros

Ruim:

```php
if ($x)
```

Bom:

```php
if ($usuarioAtivo)
```

---

## Evite condições gigantes

Ruim:

```php
if ($a && $b && $c && $d && $e)
```

Melhor:

```php
$podeAcessar = $a && $b && $c;

if ($podeAcessar)
```

---

## Sempre pense na regra de negócio

Antes do código:

```
Qual decisão precisa ser tomada?
```

Depois:

```
Qual condição representa essa decisão?
```

---

# Resumo

## IF

Usado para executar algo quando uma condição é verdadeira.

```php
if()
```

---

## ELSE

Executa quando o if falha.

```php
else
```

---

## ELSEIF

Cria múltiplas possibilidades.

```php
elseif()
```

---

## SWITCH

Escolhe entre vários valores fixos.

```php
switch()
```

---

# Conceito principal

Estruturas condicionais permitem que o programa tenha comportamento inteligente.

O programa recebe dados:

```
Variáveis
```

Analisa usando:

```
Operadores
```

Toma decisões usando:

```
if / else / switch
```

E executa diferentes caminhos.