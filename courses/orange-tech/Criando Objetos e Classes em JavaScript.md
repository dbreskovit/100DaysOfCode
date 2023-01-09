# Criando Objetos e Classes em JavaScript

## Entendendo Objetos e Classes

### Aula:

```Javascript

// Objetos são estruturas que armazenam dados e comportamentos relacionados a um mesmo contexto.
// Um objeto é uma coleção de propriedades, e uma propriedade é uma associação entre um nome (ou chave) e um valor.
// Um valor de propriedade pode ser uma função, que é então considerada um método do objeto.

/*

    // Objeto literal -> forma mais simples de criar um objeto

    const Diego = {
    // Atributos
    nome: "Diego",
    idade: 17,
    altura: 1.7,
    faculdade: null,

    // Métodos

    descrever: function () {
        console.log(
        `${this.nome} tem ${this.idade} anos e ${this.altura}m de altura.`
        );
    },
    };
*/

// Classes são estruturas que permitem criar objetos com atributos e métodos pré-definidos.
// A sintaxe de uma classe é muito parecida com a de uma função, mas ao invés de utilizar a palavra function, utilizamos a palavra class.
// Uma instancia de uma classe é chamada de objeto.

class Pessoa {
  //Atributos
  nome;
  idade;
  altura;
  faculdade;

  //Métodos
  descrever() {
    console.log(
      `${this.nome} tem ${this.idade} anos e ${this.altura}m de altura.`
    );
  }

  //Construtor
  constructor(nome, idade, altura, faculdade) {
    this.nome = nome;
    this.idade = idade;
    this.altura = altura;
    this.faculdade = faculdade;
  }
}

const Diego = new Pessoa("Diego", 17, 1.7, null);

function compararPessoas(p1, p2) {
  if (p1.idade > p2.idade) {
    console.log(`${p1.nome} é mais velho que ${p2.nome}.`);
  } else if (p1.idade < p2.idade) {
    console.log(`${p1.nome} é mais novo que ${p2.nome}.`);
  } else {
    console.log(`${p1.nome} e ${p2.nome} têm a mesma idade.`);
  }
}

```

## Praticando com Objetos e Classes

### Exercício 01:

```Javascript

/*
    Crie uma classe para representar carros.
    Os carros possuem uma marca, uma cor e um gasto médio de combustível por km rodados.
    Crie um método que dado à quantidade  de km e o preço do combustível nos dê o valor
    gasto em reais para realizar este percurso.
*/

class Carro {
  marca;
  cor;
  gastoMedioCombustivelPorKm;

  constructor(marca, cor, gastoMedioCombustivelPorKm) {
    this.marca = marca;
    this.cor = cor;
    this.gastoMedioCombustivelPorKm = gastoMedioCombustivelPorKm;
  }

  calcularGastoCombustivel(km, precoCombustivel) {
    return km * this.gastoMedioCombustivelPorKm * precoCombustivel;
  }
}

const c1 = new Carro("Fiat", "Vermelho", 0.15);
console.log(c1.calcularGastoCombustivel(100, 4.5));

```

### Exercício 02:

```Javascript

/*

    Crie uma classe para representar pessoas. Para cada pessoa teremos os atributos:
    nome, peso, altura. Aas pessoas devem ter a capacidade de dizer o valor do seu IMC
    instancie uma pessoa chamada José, que tenha 70kg de peso, 1.75 de altura
    e peça ao José para dizer o valor do seu IMC.
    IMC em adultos:
        - abaixo de 18.5 (abaixo do peso);
        - entre 18.5 e 25 (peso normal);
        - entre 25 e 30 (acima do peso);
        - entre 30 e 40 (obeso);
        - acima de 40 (obesidade grave);
*/

class Pessoa {
  nome;
  peso;
  altura;

  constructor(nome, peso, altura) {
    this.nome = nome;
    this.peso = peso;
    this.altura = altura;
  }

  calcularIMC() {
    return this.peso / this.altura ** 2;
  }

  dizerIMC() {
    const imc = this.calcularIMC();

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
  }
}

const Jose = new Pessoa("José", 70, 1.75);
Jose.dizerIMC();

```
