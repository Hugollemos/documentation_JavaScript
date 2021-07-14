# OO (Orientação a Objetos)

## OO - Abstração
__Abstrair de um todo somente as partes importantes no contexto atual.__<br>
Ex:
  __Entidade: ContaBancaria; <br>
  Características: agencia, numeroconta, saldo, limite; <br>
  Ações: depositar, sacar, consultarSaldo.__
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

## Pilar do Encapsulamento
__Seguro e Reutilizável__ <br>
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
## Pilar da Herança
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
## Pilar do Polimorfismo
>Sobreescrita de métodos

>Polimorfismo é quando queremos que os filhos se comportem diferente dos seus pais, ou seja, temos os mesmo métodos, com os mesmos nomes mas com diferentes comportamentos.

# class
__Uma class é um conjunto de características e comportamentos que definem o conjunto de objetos pertencentes à essa classe.__
```
class Carro {
  constructor(){
    console.log("Olá, sou um novo carro")
  }
}

let c1=new Carro()
```

# Getters e Setters
__As classes JavaScript contam com dois métodos especiais: um com o prefixo <b>get</b> que tem a função de retornar um valor, e outro precedido pela palavra <b>set</b> que serve para atribuir um valor.__
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

# Métodos estáticos
__Acessar os métodos de uma classe, sem precisar instânciar um objeto.__
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

__Vantagens em encapsular:
1.Tornar mudanças invisíveis <br>
2.Facilitar reutilização do código <br>
3.Reduzir efeitos colaterais__

obs: interfasses não possuem atributos, somente métodos 

método abstrato: não vai ser desenvolvido na interface.

proteger a capsula de min



# Herança 
Permite basear uma nova classe de uma outra classe previamente exixtnte.

A herança será aplicada tanto para as características quanto para os comportamentos.


## tecnica  camelcase escrever palavras compostas ou frases, onde cada palavra é iniciada em maiscula e unidas sem espaçoos.

Ex: <b>
1.sempre que a primeira letra for maisúcula ou é classe ou interface (no curso em video não vai ter sobre interface)

2. Se a primeira letra for minuscula e o resto das palavras forem como Camelcase pode ser um atributo, uma variavel ou um método.

meuAtributo
minhaVariável
meuMétodo

3.somente com letras minusculas é o nome do pacote

4.todas as letras maisculas indica uma constante