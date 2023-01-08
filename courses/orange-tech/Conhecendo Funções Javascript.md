# Conhecendo Funções JavaScript

## Funções

### Aula:

```Javascript

// Função é um bloco de código que pode ser executado quando chamado.
// Funções são usadas para executar uma tarefa específica.
// Funções são executadas quando "algo as invoca" (chama).
function func_quadrado(n) {
  return n * n;
}

function func_media(n1, n2) {
  return (n1 + n2) / 2;
}

function func_calculaImc(peso, altura) {
  const imc = peso / (altura * altura);
  return imc;
}

const quadrado = func_quadrado(10);
const media = func_media(10, 20);
const imc = func_calculaImc(80, 1.8);

console.log(quadrado);
console.log(media);
console.log(imc);

```

### Desafio:

```Javascript

// Refatoração do código de IMC para usar funções:

function calcularIMC(peso, altura) {
  return peso / Math.pow(altura, 2);
}

function classificarIMC(imc) {
  if (imc < 18.5) {
    return `o seu IMC é de: ${imc.toFixed(2)}. você está abaixo do peso. `;
  } else if (imc >= 18.5 && imc < 25) {
    return `o seu IMC é de: ${imc.toFixed(2)}. você está com o peso normal. `;
  } else if (imc >= 25 && imc < 30) {
    return `o seu IMC é de: ${imc.toFixed(2)}. você está acima do peso. `;
  } else if (imc >= 30 && imc <= 40) {
    return `o seu IMC é de: ${imc.toFixed(2)}. você está com obesidade. `;
  } else {
    return `o seu IMC é de: ${imc.toFixed(2)}. você está com obesidade grave. `;
  }
}

(function main() {
  const peso = 75;
  const altura = 1.75;

  const imc = calcularIMC(peso, altura);
  console.log(classificarIMC(imc));
})();

```

## Praticando com Funções

### Exercício 01:

```Javascript

function escrevaNome(name) {
  console.log("Meu nome é:", name);
}

escrevaNome("Diego");

function verificaIdade(idade) {
  if (idade >= 18) return true;
  return false;
}

if (verificaIdade(18)) {
  console.log("Maior de idade");
} else {
  console.log("Menor de idade");
}


```

### Exercício 02:

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

// Função para aplicar desconto
function aplicarDesconto(valor, desconto) {
  return valor - valor * desconto;
}

// função de seta é uma forma mais curta de escrever uma função
aplicarJuros = (valor, juros) => valor + valor * juros;

// Preço do produto
const Etiqueta = 100;
const formaDePagamento = 4;

// Verificação da forma de pagamento
if (formaDePagamento === 1) {
  console.log(
    `O valor final do produto é R$ ${aplicarDesconto(Etiqueta, 0.1)}`
  );
}

if (formaDePagamento === 2) {
  console.log(
    `O valor final do produto é R$ ${aplicarDesconto(Etiqueta, 0.15)}`
  );
}

if (formaDePagamento === 3) {
  console.log(`O valor final do produto é R$ ${Etiqueta}`);
}

if (formaDePagamento === 4) {
  console.log(`O valor final do produto é R$ ${aplicarJuros(Etiqueta, 0.1)}`);
}

```
