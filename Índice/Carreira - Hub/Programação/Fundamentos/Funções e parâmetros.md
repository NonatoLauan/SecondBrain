# Funções e Parâmetros

## O que são funções?

Uma função é um bloco de código criado para executar uma tarefa específica.

Ela agrupa instruções que podem ser executadas várias vezes sempre que forem chamadas.

Exemplo:

Sem função:

```php
echo "Olá João";
echo "Olá Maria";
echo "Olá Pedro";
```

Problema:

- código repetido;
- difícil de alterar;
- difícil de manter.

Com função:

```php
function cumprimentar($nome) {

    echo "Olá " . $nome;

}
```

Agora podemos reutilizar:

```php
cumprimentar("João");

cumprimentar("Maria");

cumprimentar("Pedro");
```

Resultado:

```
Olá João
Olá Maria
Olá Pedro
```

---

# Por que usamos funções?

Funções ajudam a:

- evitar repetição de código;
- organizar o programa;
- facilitar manutenção;
- separar responsabilidades;
- reutilizar lógica.

Exemplo em um sistema:

Sem função:

```php
// validar usuário

// salvar usuário

// enviar email

// gerar relatório
```

Com funções:

```php
validarUsuario();

salvarUsuario();

enviarEmail();

gerarRelatorio();
```

O código fica mais fácil de entender.

---

# Estrutura de uma função

Sintaxe:

```php
function nomeDaFuncao() {

    // código executado

}
```

Exemplo:

```php
function mostrarMensagem() {

    echo "Olá mundo";

}
```

---

# Chamando uma função

Criar a função não executa o código.

Ela só fica disponível.

Para executar:

```php
mostrarMensagem();
```

Fluxo:

```
Cria função

↓

Chama função

↓

Executa código dentro dela
```

---

# Nome de funções

Boas práticas:

Use nomes que expliquem a ação.

Ruim:

```php
function x()
```

Bom:

```php
function calcularTotal()
```

---

Normalmente usamos verbos:

```php
buscarUsuario()

salvarPedido()

calcularPreco()

enviarEmail()
```

Porque funções fazem ações.

---

# Parâmetros

## O que são?

Parâmetros são valores que uma função recebe para trabalhar.

Eles tornam a função mais flexível.

---

Sem parâmetro:

```php
function cumprimentar() {

    echo "Olá João";

}
```

Problema:

Sempre cumprimenta João.

---

Com parâmetro:

```php
function cumprimentar($nome) {

    echo "Olá " . $nome;

}
```

Agora:

```php
cumprimentar("João");

cumprimentar("Maria");
```

Resultado:

```
Olá João

Olá Maria
```

---

# Parâmetro x argumento

Existe uma diferença:

## Parâmetro

É a variável criada na função.

Exemplo:

```php
function somar($a, $b) {

}
```

Aqui:

```
$a e $b são parâmetros
```

---

## Argumento

É o valor enviado quando chama.

Exemplo:

```php
somar(10, 5);
```

Aqui:

```
10 e 5 são argumentos
```

---

# Função com vários parâmetros

Exemplo:

```php
function calcularTotal($preco, $quantidade) {

    echo $preco * $quantidade;

}
```

Uso:

```php
calcularTotal(10, 5);
```

Resultado:

```
50
```

---

# Ordem dos parâmetros

A ordem importa.

Exemplo:

```php
function apresentar($nome, $idade) {

    echo $nome;
    echo $idade;

}
```

Chamando:

```php
apresentar("João", 24);
```

Resultado:

```
João
24
```

Mas:

```php
apresentar(24, "João");
```

Ficaria errado:

```
24
João
```

---

# Valores padrão (default)

Podemos definir um valor padrão.

Exemplo:

```php
function cumprimentar($nome = "Usuário") {

    echo $nome;

}
```

Chamando:

```php
cumprimentar();
```

Resultado:

```
Usuário
```

Chamando:

```php
cumprimentar("João");
```

Resultado:

```
João
```

---

# Retorno de funções

Uma função pode devolver um valor usando:

```php
return
```

Exemplo:

```php
function somar($a, $b) {

    return $a + $b;

}
```

Uso:

```php
$resultado = somar(10, 5);
```

Resultado:

```
$resultado = 15
```

---

# Echo x Return

## Echo

Mostra algo na tela.

```php
function teste() {

    echo "Olá";

}
```

Resultado:

```
Olá
```

Mas não podemos reutilizar o valor.

---

## Return

Entrega um valor para quem chamou.

```php
function teste() {

    return "Olá";

}
```

Podemos guardar:

```php
$mensagem = teste();
```

---

# Exemplo real

Calculando desconto:

```php
function calcularDesconto($valor, $porcentagem) {

    $desconto = $valor * ($porcentagem / 100);

    return $valor - $desconto;

}
```

Uso:

```php
$total = calcularDesconto(100, 10);
```

Processo:

```
Valor:
100

Desconto:
10%

Resultado:
90
```

---

# Funções sem retorno

Nem toda função precisa retornar algo.

Exemplo:

```php
function enviarEmail($email) {

    echo "Email enviado para " . $email;

}
```

Ela executa uma ação.

---

# Funções com retorno

Usadas quando precisamos de um resultado.

Exemplo:

```php
function buscarNome() {

    return "João";

}
```

Podemos usar:

```php
$nome = buscarNome();
```

---

# Tipos de retorno (PHP)

Podemos definir o tipo esperado.

Exemplo:

```php
function somar(int $a, int $b): int {

    return $a + $b;

}
```

Significa:

Recebe:

```
inteiros
```

Retorna:

```
inteiro
```

---

# Funções e variáveis

Variáveis criadas dentro da função possuem escopo próprio.

Exemplo:

```php
function teste() {

    $nome = "João";

}
```

A variável:

```
$nome
```

existe apenas dentro da função.

---

# Parâmetros recebem cópias dos valores

Exemplo:

```php
function alterar($valor) {

    $valor = 100;

}


$numero = 10;

alterar($numero);
```

Resultado:

```
$numero continua 10
```

Porque a função recebeu uma cópia.

---

# Passagem por referência

Usando:

```php
&
```

Podemos alterar a variável original.

Exemplo:

```php
function alterar(&$valor) {

    $valor = 100;

}


$numero = 10;

alterar($numero);
```

Agora:

```
$numero = 100
```

---

# Funções dentro de funções

Uma função pode chamar outra.

Exemplo:

```php
function salvarUsuario() {

    validarUsuario();

    gravarBanco();

}
```

Fluxo:

```
Salvar usuário

↓

Validar

↓

Gravar
```

---

# Funções e organização de código

Um código ruim:

```php
// buscar usuário

// validar usuário

// calcular preço

// enviar email

// salvar dados
```

Tudo misturado.

---

Código organizado:

```php
buscarUsuario();

validarUsuario();

calcularPreco();

enviarEmail();

salvarDados();
```

Cada função possui uma responsabilidade.

---

# Funções puras

Uma função pura depende apenas dos valores recebidos.

Exemplo:

```php
function somar($a, $b) {

    return $a + $b;

}
```

Sempre:

```php
somar(2,3)
```

Retorna:

```
5
```

---

# Funções impuras

Dependem de algo externo.

Exemplo:

```php
function buscarUsuario() {

    consultarBanco();

}
```

O resultado depende do banco.

---

# Funções em sistemas reais

Exemplo de fluxo:

```php
public function salvarPedido($dados)
{

    validarPedido($dados);

    calcularValor($dados);

    salvarBanco($dados);

    enviarNotificacao();

}
```

Cada parte fica separada.

---

# Como criar boas funções?

Uma boa função deve:

## Ter uma responsabilidade

Ruim:

```php
cadastrarUsuarioEnviarEmailGerarRelatorio()
```

Bom:

```php
cadastrarUsuario()

enviarEmail()

gerarRelatorio()
```

---

## Ter nomes claros

Ruim:

```php
processar()
```

Bom:

```php
calcularFrete()
```

---

## Evitar funções enormes

Ruim:

```php
function sistemaCompleto(){

// 500 linhas

}
```

Melhor dividir.

---

# Resumo

## Função

Bloco de código reutilizável.

```php
function nome(){

}
```

---

## Parâmetro

Valor recebido pela função.

```php
function teste($valor){

}
```

---

## Argumento

Valor enviado na chamada.

```php
teste(10);
```

---

## Return

Devolve um resultado.

```php
return valor;
```

---

# Conceito principal

Funções são ferramentas para transformar código repetido em blocos organizados e reutilizáveis.

O fluxo é:

```
Criar função

↓

Receber parâmetros

↓

Executar lógica

↓

Retornar resultado

↓

Usar em outros lugares
```

Um programador bom não apenas faz o código funcionar: ele organiza o código em funções que outras pessoas conseguem entender e modificar.