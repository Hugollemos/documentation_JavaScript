# Object.defineProperty() e Object.defineProperties()
//defineProperty/
```
function Produto(nome, preco, estoque) {
  this.nome = nome;
  this.preco = preco;
  
  Object.defineProperty(this, 'estoque', {
    enumerable: true, // mostra a chave
    value: estoque, // valor
    writable: false, // pode alterar
    configurable: true //configurável
  });
}

const p1 = new Produto('Camiseta', 20, 3);
console.log(p1);
```
//defineProperties
```
function Produto(nome, preco, estoque) {
  Object.defineProperty(this, 'estoque', {
    enumerable: true, // mostra a chave
    value: estoque, // valor
    writable: true, // pode alterar
    configurable: true //configurável
  });
  
  Object.defineProperties(this, {
    nome: {
      enumerable: true, // mostra a chave
      value: nome, // valor
      writable: true, // pode alterar
      configurable: true //configurável
    },
    preco: {
      enumerable: true, // mostra a chave
      value: preco, // valor
      writable: true, // pode alterar
      configurable: true //configurável
    },
  });
}

const p1 = new Produto('Camiseta', 20, 3);
console.log(p1);
```
# Prototypes
>Protótipo é o termo usado para se referir ao que foi criado pela primeira vez, servindo de modelo ou molde para futuras produções.

>Todos os objetos tem uma referência interna para um protótipo (__proto__) que vem da propriedade prototype da função construtora que foi usado para criá-lo. Quando tentamos acessar um membro de um objeto, primeiro o motor do JS vai tentar encontrar este membro no próprio objeto e depois a cadeia de protópipos é usada até o topo (null) até encontrar (ou não) tal membro.

```Object.prototype``` <br>
Ex:
```
function Pessoa(nome, sobrenome) {
  this.nome = nome;
  this.sobrenome = sobrenome;
  this.nomeCompleto = () => this.nome + ' ' + this.sobrenome;
}

Pessoa.prototype.estouAqui = 'HAHAHAHAH';

const pessoa1 = new Pessoa('Luiz', '0.');
const pessoa2 = new Pessoa('Maria', 'A.');
const data = new  Date();

console.dir(pessoa1);
console.dir(data);
```
# Herança

>O termo "Herança" é muito usado para descrever que as características de um objeto são passadas para outro objeto. 

Ex:
```
function Produto(nome, preco) {
  this.nome = nome;
  this.preco = preco;
}
 
Produto.prototype.aumento = function (quantia) {
  this.preco += quantia;
};
 
function Camiseta(nome, preco, cor) {
  Produto.call(this, nome, preco);
  this.cor = cor;
}
Camiseta.prototype = Object.create(Produto.prototype);
Camiseta.prototype.constructor = Camiseta;
```

>Camiseta.prototype = Object.create(Produto.prototype);
Estamos, claramente, falando que o Camiseta.prototype é um novo objeto vazio que tem como protótipo Produto.prototype. Dessa forma, estamos adicionando Camiseta.prototype na cadeia de protótipos de Produto. Por consequência, tudo o que não existir em Camiseta nem em Camiseta.prototype será delegado para Produto.prototype (e assim por diante até chegar no topo da cadeia de protótipos). Por isso vejo o termo delegação como mais adequado para este comportamento.
# class

class Carro {
  constructor(){
    console.log("Olá, sou um novo carro")
  }
}

let c1=new Carro()

>em javascript quando um objeto é criado ele possui altomaticamente uma proprieedade que referencia outro objeto, esse objeto é o prototype.

>Todo objeto em js herda propriedades e metodos do seu prototype ascendente;

```Object.prototype``` <br>
Ex:
```
function Pessoa(nome, sobrenome) {
  this.nome = nome;
  this.sobrenome = sobrenome;
  this.nomeCompleto = () => this.nome + ' ' + this.sobrenome;
}

Pessoa.prototype.estouAqui = 'HAHAHAHAH';

const pessoa1 = new Pessoa('Luiz', '0.');
const pessoa2 = new Pessoa('Maria', 'A.');
const data = new  Date();

console.dir(pessoa1);
console.dir(data);
```
# Herança

>O termo "Herança" é muito usado para descrever que as características de um objeto são passadas para outro objeto. 

Ex:
```
function Produto(nome, preco) {
  this.nome = nome;
  this.preco = preco;
}
 
Produto.prototype.aumento = function (quantia) {
  this.preco += quantia;
};
 
function Camiseta(nome, preco, cor) {
  Produto.call(this, nome, preco);
  this.cor = cor;
}
Camiseta.prototype = Object.create(Produto.prototype);
Camiseta.prototype.constructor = Camiseta;
```


>Camiseta.prototype = Object.create(Produto.prototype);
Estamos, claramente, falando que o Camiseta.prototype é um novo objeto vazio que tem como protótipo Produto.prototype. Dessa forma, estamos adicionando Camiseta.prototype na cadeia de protótipos de Produto. Por consequência, tudo o que não existir em Camiseta nem em Camiseta.prototype será delegado para Produto.prototype (e assim por diante até chegar no topo da cadeia de protótipos). Por isso vejo o termo delegação como mais adequado para este comportamento.