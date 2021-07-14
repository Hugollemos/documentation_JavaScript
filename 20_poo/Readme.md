# OO (Orientação a Objetos)

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
/////////////////////////////////////////////////
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

# Métodos estáticos
  Acessar os métodos de uma classe, sem precisar instânciar um objeto.
Ex:
```
class Calcular{
  static Somar(a,b){
    console.log(a+b);
  }

  static Sub(a,b){
    console.log(a-b);
  }
}

Calcular.Somar(45,55);
Calcular.Sub(10,55);
```


# aula01 do curso de java POO

# Vantagens do uso da Programação Orientada a Objetos (POO)

C-O-M-E-R-N-ada

# Confiável
"O isolamento entre as partes gera software seguro. Ao alterar uma parte, nehuma outra é afetada."

# Oportuno
" Ao dividir tudo em partes, varias delas podem ser desenvolvidas em paratelo."

# Manutenível
" Atualizar um software é mais fácil. Uma pequena modificação vai beneficiar todas as partes que usarem o objeto."

# Extensível
" O software não é estático. Ele deve crescer para permanecer útil."

# Reutilizável
" Podemos usar objetos de um sistema que criamos em outro sistema futuro."

# Natural
" Mais fácil de entender. Você se preocupa mais na funcionalidade do que nos detalhes de implementação."



_Criador da  Orientação a Objetos:Alan kay_
_Objetivo: Aproximar o mundo digital do mundo real_

# aula02 do curso java POO

# Objeto
Coisa material ou abstrata que pode ser percebida pelos sentidos e descrita por meio da suas características, comportamentos e estado atual.

Uma classe tem que responder a 3 perguntas!

__1.coisas que eu tenho(atributo):modelo, cor, ponta, carga, tampada...__

__2.coisas que eu faço(métodos):escrever,rabiscar,pintar,tampar,destampar.__

__3.como eu estou agora(Estado):ponta fina, 40% de carga, destampada, sendo usada.__


OBS:antes de criar uma caneta tenho que criar o molde,
OBS:antes de criar um objeto eu tenho que criar uma class


# Instanciar ?

# instanciar é quando eu tenho uma classe e dela eu gero um objeto.

# c1 = new caneta 

c1 é um objeto, a palavra __new__ serve para instanciar um objeto apartir de uma classe.
O que vem depois de nova é a classe que irei utilizar, o que vem antes do nova é o objeto que irá existir.

# classe
Define os atributos e metodos comuns que serão compartilhados por um objeto.

# Objeto
É uma instância de uma classe

```
Abstração: é o ponto de partida para a criação de programas utilizando POO. trata-se da capacidade de extrair dos personagens ou dois itens presentes no contexto, suas principais caracteristicas, criado, dessa forma objetos. portanto a captura das principais caracteristicas do personagem ou item.
```

# Modificadores de Visibilidade: Indicam o nível de acesso aos componetes internos de uma classe.

*Obs: Utilizar a Linguagem de Modelagem Unificada = UML, ajudara na criação das classes*
__"+" representa a visibilidade pública__
>A classe atual e todas as outras classes podem ter acesso.
Ex: Orelha(telefone público)
)
__"-" representa a visibilidade privada__
>Somente a classe atual pode ter acesso.
Ex: telefone pessoal

__"#" representa a visibilidade protegido__
>Da acesso a classe atual e todas as suas sub-classes.
Ex: telefone de casa

# Aula 04 – Métodos Especiais

# Métodos Acessores(dão acesso a determinada coisa)

__Getters__
ele pega algo/tem acesso a algo.
O propósito de um getter é obter o valor de uma variável declarada como private e permiter sua leitura. 

# Métodos Modificadores(modificam coisas que estão dentro do objeto.
)

__Setters__
Um setter é um método que permite modificar o valor de um atributo da classe, geralmente um atributo que seja privado (e que não seja acessível diretamente).

__Método Construtor__
# Construct
Serve para criar um objeto altomaticamente.


## Métodos Acessores
Metodos get e set são usados para maior segurança da aplicação, sendo que não são obrigados a serem usados

# Encapsular
Ocultar partes independntes da implementação, permitindo construir partes invisíveis ao mundo exterior.

# Interface 
Lista de serviços fornecidos por um componente. É o contato com o mundo exterior, que define o que pode ser feito com um objeto dessa classe.

o funcionanmento dentro da capsula não importa


Obs: Encapsular não é obrigatório, mas é uma boa prática para produduzir Classes mais eficientes.

Vantagens em encapsular:
1.Tornar mudanças invisíveis
2.Facilitar reutilização do código
3.Reduzir efeitos colaterais

obs: interfasses não possuem atributos, somente métodos 

método abstrato: não vai ser desenvolvido na interface.

proteger a capsula de min



# Herança 
Permite basear uma nova classe de uma outra classe previamente exixtnte.

A herança será aplicada tanto para as características quanto para os comportamentos.

# sobre o java 
tecnica  camelcase escrever palavras compostas ou frases, onde cada palavra é iniciada em maiscula e unidas sem espaçoos.
Ex:

1.sempre que a primeira letra for maisúcula ou é classe ou interface (no curso em video não vai ter sobre interface)

AlunosCursoEmVideo


2.se a primeira letra for minuscula e o resto das palavras forem como Camelcase pode ser um atributo, uma variavel ou um método.

meuAtributo
minhaVariável
meuMétodo

3.somente com letras minusculas é o nome do pacote

4. todas as letras maisculas indica uma constante

# System.out.println("Hello, World!");
  Sistema.Saída.Imprimir()
>imprimi uma mensagem na tela.

