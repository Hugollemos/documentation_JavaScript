# OO (Orientação a Objetos)
>padrão de código mais clean
## OO - Abstração
compreender as coisas do mundo real e trazer para dentro do sistema <br>
Ex:
```Entidade: ContaBancaria; Identidade: x = new ContaBancaria(); Características: agencia, numeroconta, saldo, limite; Ações: depositar, sacar, consultarSaldo.```
```
class ContaBancaria {
  //agencia
  //numeroConta
  //saldo
  //limite
  constructor() {
    this.agencia = 1075
    this.numeroConta = 8351125
    this.saldo = 50
    this.limite = 450
  }

  depositar(valorDeposito) {
    this.saldo += valorDeposito
  }

  sacar(valorSaque) {
    this.saldo -= valorSaque
  }

  consultarSaldo() {
    return this.saldo
  }
}

let x = new ContaBancaria()
let y = new ContaBancaria()

console.log(x.consultarSaldo())
x.depositar(450)
console.log(x.consultarSaldo())
x.sacar(200)
console.log(x.consultarSaldo())
```
## OO - Pilar do Encapsulamento
>Seguro e Reutilizável
Ex:
```
class Tv {
  constructor() {
    this._relacaoCanais = Array(2, 4, 5, 7, 10)
    this._canalAtivo = 5
    this._volume = 5
  }

  //get e set
  get canalAtivo() {
    return this.canalAtivo
  }

  set canalAtivo(canal) {
    this._canalAtivo = canal
  }
}

let tv = new Tv()

Tv.canalAtivo = 10
console.log(Tv.canalAtivo)
```
## OO - Pilar da Herança
>O termo "Herança" é muito usado para descrever que as características de um objeto são passadas para outro objeto. 
>Em OOP, herança refere-se a habilidade de um objeto acessar métodos e outras propriedades de outro objeto. Estes objetos então herdam essas informações de outros objetos e podem utilizá-las da forma que preferirem.
Ex:
```
class Animal {
  constructor() {
    this.cor = ''
    this.tamanho = null
  }

  dormir() {
    console.log('Dormir')
  }
}

class Cachorro extends Animal {
  constructor() {
    super()
    this.orelhas = 'Grandes e caidas'
  }

  correr() {
    console.log('Correr')
  }

  dormir() {
    console.log('Dormir')
  }

  rosnar() {
    console.log('Rosnar')
  }
}

class Passaro extends Animal {
  constructor() {
    super()
    this.bico = 'Curto'
  }

  voar() {
    console.log('Rosnar')
  }

  dormir() {
    console.log('Dormir')
  }
}

let cachorro = new Cachorro()
let passaro = new Passaro()
```
## OO - Pilar do Polimorfismo
>Sobreescrita de métodos

>Polimorfismo é quando queremos que os filhos se comportem diferente dos seus pais, ou seja, temos os mesmo métodos, com os mesmos nomes mas com diferentes comportamentos.



# class
uma class é um conjunto de características e comportamentos que definem o conjunto de objetos pertencentes à essa classe.
class Carro {
  constructor(){
    console.log("Olá, sou um novo carro")
  }
}

let c1=new Carro()


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
##
# Object.defineProperty() e Object.defineProperties()
__//defineProperty/__
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
__//defineProperties__
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
>em javascript quando um objeto é criado ele possui altomaticamente uma proprieedade que referencia outro objeto, esse objeto é o prototype.

>Protótipo é o termo usado para se referir ao que foi criado pela primeira vez, servindo de modelo ou molde para futuras produções.

>Todos os objetos tem uma referência interna para um protótipo (__ proto __) que vem da propriedade prototype da função construtora que foi usado para criá-lo. Quando tentamos acessar um membro de um objeto, primeiro o motor do JS vai tentar encontrar este membro no próprio objeto e depois a cadeia de protópipos é usada até o topo (null) até encontrar (ou não) tal membro.

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
>Em OOP, herança refere-se a habilidade de um objeto acessar métodos e outras propriedades de outro objeto. Estes objetos então herdam essas informações de outros objetos e podem utilizá-las da forma que preferirem.

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



# Getters e Setters
As classes JavaScript contam com dois métodos especiais: um com o prefixo <b>get</b> que tem a função de retornar um valor, e outro precedido pela palavra <b>set</b> que serve para atribuir um valor.
get para obter o valor
```
car obg = {
  get v(){
    return 5;
  }
}
```
```
var _v = 0;

var obj = {
  get v(){
    return 'Value:' + _v;
  },
  set v(value){
    _v = value * 2;
  }
}
```