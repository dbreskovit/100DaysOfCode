# Importação e Exportação com JavaScript

## Desvendando as Funções "gets" e "print" dos Desafios de Código

### Aula:

##### aula.js

```Javascript

// Importando o módulo function_aux.js
// Destructuring é uma forma de desestruturar um objeto ou array em variáveis
const { gets, print } = require("./function_aux.js");

print(gets());


```

##### function_aux.js

```Javascript

const entradas = [5, 50, 10, 98, 23];
let  i = 0;

function gets() {
  return entradas[i++];
}

function gets_aux() {
  return "1";
}

function print(texto) {
  console.log(texto);
}

module.exports = { gets, print };

```

## Praticando os Conceitos de Importação e Exportação

### Exercício 01:

```Javascript

/*
    Uma sala contém 5 alunos e para cada aluno foi sorteado um número de 1 à 100.
    Faça um programa que receba os 5 números sorteados para os alunos e mostre o maior número sorteado.

    Dados de entrada:
    5
    50
    10
    98
    23

    Saída:
    98
*/

const { gets, print } = require("../function_aux.js");

let maiorValorEncontrado = 0;

for (let i = 0; i < 5; i++) {
  const numerosSorteados = gets();
  if (numerosSorteados > maiorValorEncontrado) {
    maiorValorEncontrado = numerosSorteados;
  }
}

print(maiorNumero);

```
