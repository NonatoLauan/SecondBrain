# Estruturas de Repetição (for, while, foreach)

## O que são estruturas de repetição?

Estruturas de repetição, também chamadas de **loops** ou **laços de repetição**, permitem executar um bloco de código várias vezes sem precisar escrever o mesmo código repetidamente.

Exemplo:

Sem repetição:

```php
echo "Olá";
echo "Olá";
echo "Olá";
echo "Olá";
echo "Olá";
```

Problema:

- código repetido;
- difícil de alterar;
- pouco eficiente.

Com repetição:

```php
for ($i = 0; $i < 5; $i++) {

    echo "Olá";

}
```

Resultado:

```
Olá
Olá
Olá
Olá
Olá
```

---

# Por que usamos loops?

Eles são usados quando precisamos:

- percorrer listas;
- processar vários registros;
- repetir uma operação;
- esperar uma condição mudar;
- executar uma tarefa para vários elementos.

Exemplos reais:

- mostrar todos os usuários cadastrados;
- enviar notificações para vários clientes;
- calcular valores de vários produtos;
- percorrer resultados do banco de dados.

---

# Como um loop funciona?

Todo loop possui normalmente:

1. Inicialização
2. Condição
3. Execução
4. Atualização

Exemplo:

```php
for ($i = 0; $i < 5; $i++) {

    echo $i;

}
```

Fluxo:

```
Cria variável

↓

Verifica condição

↓

Executa código

↓

Atualiza variável

↓

Volta para condição
```

---

# 1. FOR

## O que é?

O `for` é usado quando sabemos aproximadamente quantas vezes queremos repetir algo.

Exemplo:

> Quero executar 10 vezes.

Usamos:

```php
for
```

---

# Sintaxe do FOR

```php
for (inicialização; condição; incremento) {

    // código repetido

}
```

Possui três partes:

```php
for ($i = 0; $i < 10; $i++)
```

---

## Inicialização

Executa uma vez no começo.

```php
$i = 0;
```

Cria o contador.

---

## Condição

Define quando o loop continua.

```php
$i < 10;
```

Enquanto for verdadeiro, continua.

---

## Incremento

Executado no final de cada repetição.

```php
$i++;
```

Aumenta o contador.

---

# Exemplo básico

```php
for ($i = 0; $i < 5; $i++) {

    echo $i;

}
```

Execução:

Primeira volta:

```
$i = 0

0 < 5?

Sim

Mostra 0
```

Segunda:

```
$i = 1

1 < 5?

Sim

Mostra 1
```

Continua até:

```
$i = 5

5 < 5?

Falso

Para
```

Resultado:

```
0
1
2
3
4
```

---

# Contador crescente

```php
for ($i = 1; $i <= 10; $i++) {

    echo $i;

}
```

Resultado:

```
1
2
3
4
5
6
7
8
9
10
```

---

# Contador regressivo

```php
for ($i = 10; $i >= 0; $i--) {

    echo $i;

}
```

Resultado:

```
10
9
8
7
...
0
```

---

# Usando FOR com arrays

Exemplo:

```php
$nomes = [
    "João",
    "Maria",
    "Pedro"
];
```

Podemos acessar pela posição:

```php
for ($i = 0; $i < 3; $i++) {

    echo $nomes[$i];

}
```

Resultado:

```
João
Maria
Pedro
```

---

# Problema do FOR com arrays

Precisamos saber o tamanho.

Exemplo:

```php
$i < 3
```

Mas e se amanhã tiver 100 usuários?

Por isso existe o `count()`:

```php
for ($i = 0; $i < count($nomes); $i++) {

    echo $nomes[$i];

}
```

---

# 2. WHILE

## O que é?

O `while` executa enquanto uma condição for verdadeira.

Tradução:

```
ENQUANTO
```

Exemplo:

> Enquanto houver tentativas disponíveis, continue tentando.

---

# Sintaxe

```php
while (condição) {

    // código

}
```

---

# Exemplo

```php
$contador = 0;

while ($contador < 5) {

    echo $contador;

    $contador++;

}
```

Resultado:

```
0
1
2
3
4
```

---

# Importante: atualização da variável

No while, normalmente você precisa atualizar a variável manualmente.

Exemplo errado:

```php
$contador = 0;

while ($contador < 5) {

    echo $contador;

}
```

Problema:

A condição nunca muda.

Resultado:

```
loop infinito
```

O programa fica preso.

---

# Quando usar WHILE?

Use quando você não sabe exatamente quantas vezes vai repetir.

Exemplos:

- tentar conexão até conseguir;
- esperar uma condição mudar;
- processar dados enquanto existirem.

---

# Exemplo real

Sistema de tentativas:

```php
$tentativas = 0;

while ($tentativas < 3) {

    tentarLogin();

    $tentativas++;

}
```

Fluxo:

```
Tentativa 1

↓

Tentativa 2

↓

Tentativa 3

↓

Para
```

---

# 3. FOREACH

## O que é?

O `foreach` é usado principalmente para percorrer arrays.

Ele significa:

```
PARA CADA ITEM
```

---

# Sintaxe

```php
foreach ($array as $valor) {

    // código

}
```

---

# Exemplo básico

Array:

```php
$usuarios = [
    "João",
    "Maria",
    "Pedro"
];
```

Loop:

```php
foreach ($usuarios as $usuario) {

    echo $usuario;

}
```

Resultado:

```
João
Maria
Pedro
```

---

# Como funciona?

Primeira repetição:

```
$usuario = João
```

Segunda:

```
$usuario = Maria
```

Terceira:

```
$usuario = Pedro
```

---

# FOREACH com chave e valor

Em arrays associativos:

```php
$usuario = [

    "nome" => "João",

    "idade" => 24

];
```

Podemos pegar chave e valor:

```php
foreach ($usuario as $chave => $valor) {

    echo $chave;
    echo $valor;

}
```

Resultado:

```
nome
João

idade
24
```

---

# Comparação FOR x WHILE x FOREACH

| Loop | Quando usar |
|-|-|
| for | Quando sabe a quantidade de repetições |
| while | Quando depende de uma condição |
| foreach | Quando percorre uma lista/array |

---

# Exemplo prático comparando

Temos:

```php
$produtos = [
    "Mouse",
    "Teclado",
    "Monitor"
];
```

---

## Com FOR

```php
for ($i = 0; $i < count($produtos); $i++) {

    echo $produtos[$i];

}
```

Precisamos controlar o índice.

---

## Com FOREACH

```php
foreach ($produtos as $produto) {

    echo $produto;

}
```

Mais simples.

---

# Break

O `break` interrompe o loop.

Exemplo:

```php
for ($i = 0; $i < 10; $i++) {

    if ($i == 5) {

        break;

    }

    echo $i;

}
```

Resultado:

```
0
1
2
3
4
```

Quando chega no 5, para.

---

# Continue

O `continue` pula uma repetição.

Exemplo:

```php
for ($i = 0; $i < 5; $i++) {

    if ($i == 2) {

        continue;

    }

    echo $i;

}
```

Resultado:

```
0
1
3
4
```

O 2 foi ignorado.

---

# Loops aninhados

É um loop dentro de outro.

Exemplo:

```php
for ($i = 1; $i <= 3; $i++) {

    for ($j = 1; $j <= 3; $j++) {

        echo "$i - $j";

    }

}
```

Usado em:

- tabelas;
- matrizes;
- estruturas complexas.

---

# Cuidado com loops infinitos

Acontecem quando a condição nunca fica falsa.

Exemplo:

```php
while (true) {

    echo "Executando";

}
```

Nunca termina.

---

# Performance em loops

Loops podem executar milhares de vezes.

Evite:

```php
for ($i = 0; $i < count($usuarios); $i++)
```

Em casos grandes:

```php
$total = count($usuarios);

for ($i = 0; $i < $total; $i++)
```

Porque evita calcular o tamanho várias vezes.

---

# Loops e banco de dados

Muito comum em sistemas:

Exemplo:

Buscar usuários:

```php
$usuarios = buscarUsuarios();

foreach ($usuarios as $usuario) {

    enviarEmail($usuario);

}
```

Fluxo:

```
Busca usuários

↓

Percorre lista

↓

Executa ação para cada usuário
```

---

# Como escolher o loop correto?

Pergunte:

## Sei quantas vezes vou repetir?

Sim:

```
for
```

Exemplo:

"Executar 10 vezes"

---

## Depende de uma condição?

Sim:

```
while
```

Exemplo:

"Enquanto houver registros"

---

## Estou percorrendo uma lista?

Sim:

```
foreach
```

Exemplo:

"Para cada usuário"

---

# Resumo

## FOR

Estrutura:

```php
for(início; condição; atualização)
```

Usado para quantidade conhecida.

---

## WHILE

Estrutura:

```php
while(condição)
```

Usado enquanto algo for verdadeiro.

---

## FOREACH

Estrutura:

```php
foreach(lista as item)
```

Usado para percorrer arrays.

---

# Conceito principal

Loops permitem que programas façam tarefas repetitivas automaticamente.

Sem loops:

```
Repetir código manualmente
```

Com loops:

```
Definir uma regra

↓

Computador repete sozinho
```

Programação é transformar repetições cansativas em instruções automáticas.