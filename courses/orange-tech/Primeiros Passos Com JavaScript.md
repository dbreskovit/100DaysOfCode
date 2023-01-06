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
