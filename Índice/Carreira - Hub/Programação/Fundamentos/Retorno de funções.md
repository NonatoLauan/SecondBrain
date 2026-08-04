# Retorno de Funções (return)

## O que é o retorno de uma função?

O retorno de uma função é o valor que ela devolve para o código que chamou essa função.

O comando usado para retornar um valor é:

```php
return
```

Exemplo:

```php
function somar($a, $b) {

    return $a + $b;

}
```

Quando chamamos:

```php
$resultado = somar(10, 5);
```

A função executa:

```
10 + 5
```

Depois devolve:

```
15
```

Então:

```php
$resultado = 15;
```

---

# Fluxo de uma função com retorno

Exemplo:

```php
function calcularPreco($valor) {

    $resultado = $valor * 2;

    return $resultado;

}


$total = calcularPreco(50);
```

Execução:

```
1. Chama calcularPreco(50)

↓

2. Recebe o valor 50 no parâmetro

↓

3. Calcula:

50 * 2 = 100

↓

4. Executa return

↓

5. Devolve 100

↓

6. Guarda em $total
```

Resultado:

```
$total = 100
```

---

# Return não imprime na tela

Um dos erros mais comuns de iniciantes é confundir:

```
return
```

com:

```
echo
```

---

# Echo

O `echo` apenas mostra uma informação.

Exemplo:

```php
function mostrarNome() {

    echo "João";

}
```

Chamada:

```php
mostrarNome();
```

Resultado na tela:

```
João
```

Mas a função não entregou nenhum valor.

---

# Return

O `return` entrega um valor.

Exemplo:

```php
function buscarNome() {

    return "João";

}
```

Uso:

```php
$nome = buscarNome();
```

Agora:

```
$nome = "João"
```

O valor pode ser usado depois.

---

# Diferença prática

## Echo

```php
function calcular(){

    echo 10 + 5;

}
```

Resultado:

```
15
```

Mas:

```php
$resultado = calcular();
```

Não recebe nada.

---

## Return

```php
function calcular(){

    return 10 + 5;

}
```

Agora:

```php
$resultado = calcular();
```

Resultado:

```
$resultado = 15
```

---

# Por que usar retorno?

Retorno permite:

- reutilizar resultados;
- guardar informações;
- passar dados para outras funções;
- separar lógica de apresentação.

---

Exemplo ruim:

```php
function calcularTotal($preco, $quantidade){

    echo $preco * $quantidade;

}
```

Problema:

A função só sabe mostrar.

Não conseguimos:

```php
$total = calcularTotal(10, 5);
```

---

Melhor:

```php
function calcularTotal($preco, $quantidade){

    return $preco * $quantidade;

}
```

Agora:

```php
$total = calcularTotal(10, 5);

echo $total;
```

---

# Retorno de diferentes tipos de dados

Uma função pode retornar qualquer tipo.

---

## Retornando string

```php
function buscarNome(){

    return "Maria";

}
```

Retorno:

```
Maria
```

---

## Retornando inteiro

```php
function buscarIdade(){

    return 24;

}
```

Retorno:

```
24
```

---

## Retornando float

```php
function buscarPreco(){

    return 10.50;

}
```

---

## Retornando boolean

```php
function usuarioAtivo(){

    return true;

}
```

Uso:

```php
if (usuarioAtivo()) {

    echo "Liberado";

}
```

---

## Retornando array

```php
function buscarUsuarios(){

    return [
        "João",
        "Maria"
    ];

}
```

Uso:

```php
$usuarios = buscarUsuarios();
```

Resultado:

```
[
 João,
 Maria
]
```

---

## Retornando objeto

```php
function buscarUsuario(){

    return $usuario;

}
```

Muito usado em frameworks.

---

# Retorno em condições

Uma função pode retornar valores diferentes dependendo da situação.

Exemplo:

```php
function verificarIdade($idade){

    if ($idade >= 18) {

        return "Maior";

    }

    return "Menor";

}
```

Uso:

```php
$resultado = verificarIdade(20);
```

Resultado:

```
Maior
```

---

# Return encerra a função

Quando o PHP encontra um `return`, a função termina naquele momento.

Exemplo:

```php
function teste(){

    return "Fim";

    echo "Nunca executa";

}
```

Resultado:

```
Fim
```

O `echo` nunca acontece.

---

# Múltiplos returns

Uma função pode ter vários retornos.

Exemplo:

```php
function validarSenha($senha){

    if ($senha == "") {

        return false;

    }

    return true;

}
```

Fluxo:

```
Senha vazia?

Sim → retorna false

Não → retorna true
```

---

# Return vazio

Também podemos usar:

```php
return;
```

Ele apenas encerra a função.

Exemplo:

```php
function verificar(){

    if (erro) {

        return;

    }

}
```

---

# Tipo de retorno (Type Hint)

PHP permite definir o tipo que a função deve retornar.

Exemplo:

```php
function somar(int $a, int $b): int {

    return $a + $b;

}
```

Significa:

Parâmetros:

```
inteiros
```

Retorno:

```
inteiro
```

---

# Exemplos:

## String

```php
function nome(): string {

    return "João";

}
```

---

## Boolean

```php
function valido(): bool {

    return true;

}
```

---

## Array

```php
function usuarios(): array {

    return [];

}
```

---

# Retorno e composição de funções

Uma função pode usar o retorno de outra.

Exemplo:

```php
function calcularPreco(){

    return 100;

}


function aplicarDesconto($valor){

    return $valor - 20;

}


$total = aplicarDesconto(calcularPreco());
```

Fluxo:

```
calcularPreco()

↓

100

↓

aplicarDesconto(100)

↓

80
```

Resultado:

```
$total = 80
```

---

# Retorno em sistemas reais

Exemplo de login:

```php
function autenticarUsuario($email, $senha){

    if ($dadosCorretos) {

        return true;

    }

    return false;

}
```

Uso:

```php
if (autenticarUsuario($email, $senha)) {

    entrarSistema();

}
```

A função não precisa saber o que acontece depois.

Ela apenas responde:

```
sim
```

ou

```
não
```

---

# Retorno x alteração direta

Uma função bem organizada normalmente retorna valores.

Exemplo:

```php
function calcularValor(){

    return $valor;

}
```

Em vez de alterar variáveis externas.

Isso torna o código:

- previsível;
- fácil de testar;
- mais seguro.

---

# Funções que fazem ações x funções que calculam

## Função de ação

Executa algo:

```php
enviarEmail();
salvarArquivo();
deletarUsuario();
```

Nem sempre precisa retornar.

---

## Função de cálculo

Produz um resultado:

```php
calcularTotal();
buscarPreco();
validarUsuario();
```

Normalmente retorna algo.

---

# Boas práticas

## Sempre retorne quando precisar reutilizar um valor

Bom:

```php
$total = calcularTotal();
```

---

## Evite misturar retorno e saída

Evite:

```php
function calcular(){

    echo "Resultado:";
    return 100;

}
```

Melhor separar:

```php
$total = calcular();

echo $total;
```

---

## Retorne valores claros

Ruim:

```php
return 1;
```

Bom:

```php
return true;
```

ou:

```php
return "Usuário encontrado";
```

---

# Resumo

## Return

Entrega um valor:

```php
return valor;
```

---

## Echo

Mostra algo:

```php
echo valor;
```

---

## Return encerra a função

Depois dele, o código não continua.

---

## Uma função pode retornar:

- string;
- número;
- boolean;
- array;
- objeto;
- qualquer tipo de dado.

---

# Conceito principal

Uma função recebe dados:

```
Parâmetros
```

Processa informações:

```
Lógica interna
```

Entrega um resultado:

```
Return
```

Fluxo:

```
Entrada

↓

Processamento

↓

Saída
```

O retorno é o mecanismo que permite que funções conversem entre si e construam sistemas maiores.