# Primeiros Passos Com Javascript

## Variáveis e Operadores

### Aula:

```Javascript

// Variáveis são espaços na memória que armazenam valores
// Podemos criar variáveis com let ou const

let variable = 10; // let é uma variável que podemos mudar seu valor
const constant = 20; // const não é possível modificar pois se trata de uma constante

console.log(variable);

```

### Desafio:

```Javascript

/*
Faça um programa para calcular o valor gasto de combustível em uma viagem.
Você terá três variáveis, sendo elas:
    - 1: preço do combustível;
    - 2: gasto médio do combustível do carro por km;
    - 3: distância em km da viagem.
*/

// Preço do combustível:
const preçoCombustível = 4.86;
//Gasto médio do carro:
let valorMédioGasto = 12;
//Distância da viagem percorrida:
let distanciaViagem = 180.4;

const litrosConsumidos = preçoCombustível / valorMédioGasto;
const valorGasto = litrosConsumidos * distanciaViagem;

console.log(`Valor gasto de combustível: R\$${valorGasto.toFixed(2)}`);

```

## Estruturas Condicionais

### Aula:

```Javascript

let numero = 10;

// Variáveis booleans são variáveis que só podem ter dois valores: true ou false
// % é o operador de resto da divisão
// === é o operador de igualdade estrita
const ehNumeroPar = numero % 2 === 0;
// !== é o operador de desigualdade estrita
const ehNumeroImpar = numero % 2 !== 0;

// if é uma estrutura condicional que executa um bloco de código se a condição for verdadeira
if (ehNumeroPar) {
  console.log(`O número ` + numero + ` é par`);
}

if (ehNumeroImpar) {
  console.log(`O número ` + numero + ` é ímpar`);
}

```

### Desafio:

```Javascript

/*
Faça um programa para calcular o valor de uma viagem.
Você terá cinco variáveis, sendo elas:
    1 - preço do etanol;
    2 - preço da gasolina;
    3 - o tipo de combustível que está no seu carro;
    4 - o gasto médio de combustível do carro por km;
    5 - distância em km da viagem.
*/

// Preços dos combustíveis:
const preçoEtanol = 4.5;
const preçoGasolina = 5.5;
let valorMédioGasto = 10;

//Distância da viagem percorrida:
let distanciaViagem = 100;

// Tipo de combustível que está no carro:
let isEtanol = true;

if (isEtanol) {
  const litrosConsumidos = distanciaViagem / valorMédioGasto;
  const valorGasto = litrosConsumidos * preçoEtanol;
} else if (!isEtanol) {
  const litrosConsumidos = distanciaViagem / valorMédioGasto;
  const valorGasto = litrosConsumidos * preçoGasolina;
} else {
  console.log("Tipo de combustível inválido");
}

console.log(`Valor gasto de combustível: R\$${valorGasto.toFixed(2)}`);

```

## Praticando com Variáveis, Operadores e Estruturas Condicionais

### Exercício 01:

```Javascript

/*
    1) Faça um algoritmo que dado as três notas tiradas por um aluno em um semestre da faculdade calcule a sua média e mostre as seguintes mensagens de acordo com cada situação:

    Médio = (nota1 + nota2 + nota3) / 3

    Classificação:
    - Se a média for maior ou igual a 7,0: Aprovado
    - Se a média for maior ou igual a 5,0 e menor que 7,0: Recuperação
    - Se a média for menor que 5,0: Reprovado
*/

// Notas do aluno
const nota1 = 7.5;
const nota2 = 6.5;
const nota3 = 9.5;

// Calculo da média
const media = (nota1 + nota2 + nota3) / 3;

// Verificação da situação do aluno
if (media >= 7) {
  console.log("Aprovado");
}

if (media >= 5 && media < 7) {
  console.log("Recuperação");
}

if (media < 5) {
  console.log("Reprovado");
}

console.log("Média: " + media.toFixed(2));

```

### Exercício 02:

```Javascript

/*
        O IMC - Índice de Massa Corporal é um critério da Organização Mundial de Saúde para dar uma indicação
        sobre a condição de peso de uma pessoa adulta.
        fórmula do IMC:

        IMC = peso / (altura * altura);

        Elabore um algoritmo que dado o peso e a altura de um adulto, mostre sua condição de acordo com a table abaixo:

        Tabela de valores do IMC em adultos:
            - abaixo de 18.5 (abaixo do peso);
            - entre 18.5 e 25 (peso normal);
            - entre 25 e 30 (acima do peso);
            - entre 30 e 40 (obeso);
            - acima de 40 (obesidade grave);
*/

// Peso e altura do usuário
const peso = 80;
const altura = 1.8;

// Cálculo do IMC
const imc = peso / Math.pow(altura, 2);

// Verificação da situação do usuário
if (imc < 18.5) {
  console.log("Abaixo do peso");
}

if (imc >= 18.5 && imc < 25) {
  console.log("Peso normal");
}

if (imc >= 25 && imc < 30) {
  console.log("Acima do peso");
}

if (imc >= 30 && imc < 40) {
  console.log("Obeso");
}

if (imc >= 40) {
  console.log("Obesidade grave");
}

```

### Exercício 03:

```Javascript

/*
    Elabore um algoritmo  que calcule o que deve ser pago por um produto, considerando o preço normal de etiqueta e a escolha da condição de pagamento.
    Utilize os códigos da tabela a seguir para ler qual condição de pagamento escolhida e efetuar o cálculo adequado.

    Código condição de pagamento:
        1 - à vista no débito, recebe 10% de desconto;
        2 - à vista no dinheiro ou pix, recebe 15% de desconto;
        3 - em duas vezes, preço normal de etiqueta sem juros;
        4 - acima de duas vezes, preço normal de etiqueta mais juros de 10%.
*/

// Preço do produto
const Etiqueta = 100;
const formaDePagamento = 1;

// Verificação da forma de pagamento
if (formaDePagamento === 1) {
  console.log(`O valor final do produto é R$ ${Etiqueta * 0.9}`);
}

if (formaDePagamento === 2) {
  console.log(`O valor final do produto é R$ ${Etiqueta * 0.85}`);
}

if (formaDePagamento === 3) {
  console.log(`O valor final do produto é R$ ${Etiqueta}`);
}

if (formaDePagamento === 4) {
  console.log(`O valor final do produto é R$ ${Etiqueta * 1.1}`);
}

```
