# funções: conceitos básicos
>funções executam blocos de códigos, recebem ou não argumentos para os parâmetros os parâmetros. Usar-se a palavra reservada "function" para iniciar uma função.
Ex:
```
function saudacao(nome) {
  return(`Bom dia ${nome}`)
}

let variavel = saudacao('hugo')
console.log(variavel)
```
# Função que retorna uma soma, mandando argumentos para o parametrô da função

function soma (x, y) {
  const resultado = x + y;
  return resultado;
}

console.log(soma(2,4))

>colocar um função dentro de uma variavel, faz com que a função seja, anônima.

#### Arrow Functions: declarar funções encurtadas.
1. maneira tradicional; 
```
const raiz = function (n) {
  return n ** 0.5; <br>
}
 ```
 2. maneira mais mordena de fazer funções 
 ```
const raiz = (n) => { 
  return n ** 0.5 <br>
}
console.log(raiz(9));
```
```const raiz = n => n ** 0.5;```

# função auto-executável
>Função anônima é uma função sem nome
```
(function autoExecuta() {
  console.log('Executei');
}());

Ex: var subtrai3numb = function (a, b, c) {
  return a- b -;
}
console.log(subtrai3numb(15, 3, 5));
```
# Funções de callback
Uma função callback é uma função passada a outra função como parametrô, que é então invocado dentro da função externa para completar algum tipo de rotina ou ação.

Ex: 
```
function exibeMensagensNaOrdem(mensagem, callback) {
	console.log(mensagem);
	callback();
}
exibeMensagensNaOrdem('Essa é a primeira mensagem exibida na ordem', function() {
	console.log('Essa é a segunda mensagem exibida na ordem');
});
```

Ex:
### não passando argumentos para afunção 
```
function escreveNome(nome,idade) {
  console.log(nome);
  console.log(idade)
}

escreveNome();
``` 
# Funções imediatas (IIFE)
>“Immediately-invoked function expression”.
Ex:
```
(function(idade, peso, altura) {

  const sobrenome = 'Miranda';
  function criaNome(nome) {
    return nome + ' ' + sobrenome;
  }

  function falaNome() {
    console.log(criaNome('Luiz'))
  }

  falaNome();
  console.log(idade, peso, altura);

})(30, 80, 1.80);
``` 
## Argumentos
>ão passando argumentos, o valor retornado sera "undefined", mas é possivel deixar o valor padão pre-definido dentro de parametrôs, como se estivesse passado argumentos, dessa forma:

Ex:
```
function escreveNome(nome = 'Hugo',idade = '21') {
  console.log(nome);
  console.log(idade)
}

escreveNome();
```

# Fábrica de funções 
> função que retorna objetos

>OBS: método função que esta dentro do objeto 
Ex:
```
function criaPessoa(nome, sobrenome) {
  return {
    nome,
    sobrenome,
    fala: function(assunto) {
      return `${nome} está ${assunto}.`;
    },
  };
}

const p1 = criaPessoa('Luiz', 'Otávio');
console.log(p1.fala('falando sobre JS'));
```
COM THIS
```
function criaPessoa(nome, sobrenome) {
  return {
    nome,
    sobrenome,
    fala: function(assunto) {
      return `${this.peso} está ${assunto}.`;
    },
    peso: 80
  };
}

const p1 = criaPessoa('Luiz', 'Otávio');
console.log(p1.fala('falando sobre JS'));
```
# this 
>função executada com new retorna this <br> 
>this depende muito do contexto a onde ele é executado.

nesta forma this assume escopo global <br>
Ex:
```
function Usuario() {

  console.log(this)
}

Usuario();
``` 
>função executada com new retorna this como objeto da função. <br>
Ex:
```
function Usuario() {

  console.log(this)
}

 new Usuario();


Usuario {}
```
# call
O método call() é uma função capaz de alterar o valor this. Por padrão, o primeiro parâmetro que recebe o valor do this e o demais parâmetros são da função que invoca o método Call.
Ex:
```
function Personagem() {
  console.log(this)
}
 var personagemThis = {
   nome: 'hugo'
 }
Personagem.call(personagemThis, 123, [5])
```
>passando valores 
Ex:
```
function Personagem(p1, p2, p3) {
  console.log(p1, p2, p3)
  console.log(this)
}
 var personagemThis = {
   nome: 'hugo'
 }
Personagem.call(personagemThis, 'pram1', 123, [15])
```
## Apply
a diferença para o call é que no call é passado parametrô por parametrô, no aplly é por array
Ex:
```
function Personagem(p1, p2, p3) {
  console.log(p1, p2, p3)
  console.log(this)
}
 var personagemThis = {
   nome: 'hugo'
 }
Personagem.apply(personagemThis, [ 'pram1', 123, [15]])
```
## bind
não passa função, so passa o this e diz quem é os parametrôs.
O Bind por sua vez funciona de uma maneira diferente de call e apply, ao invés de executar uma função, este retorna uma nova função. O seu primeiro parâmetrô continua recebendo o valor que será atribuído ao this e os demais argumentos serão os parâmetros que definirão os valores atribuídos da primeira função. <br>
Ex:
```
function Personagem(p1, p2, p3) {
  console.log(p1, p2, p3)
  console.log(this)
}
 var personagemThis = {
   nome: 'hugo'
 }
  var pers = Personagem.bind(personagemThis, 'olá') 
  pers ('Mundo', '!!!');
```
# Arrow functions:
não possuem um escopo para o this. Em vez disso, elas passam para um próximo nível de execução. <br>
Ex: 
```
var soma = (a, b) => {
  return a + b;
}
console.log(soma(10, 10))
```

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
# Função Construtora

>A diferença básica é que uma função construtora é usada com a new palavra - chave (que faz com que o JavaScript crie automaticamente um novo objeto.

>defina this dentro da função para esse objeto e retorne o objeto):

>Um construtor é basicamente uma função. Ela pode ser executada como uma função ou pode ser utilizada para instanciar um objeto utilizando a palavra reservada new.

> OBS: começa com letra maiscula
Ex:
```
const soma=new Function("n1,n2","return n1 + n2")
console.log(soma(8,2))
```
# função recursiva 
>Uma função recursiva é uma função que chama a si mesma até encontrar uma instrução de parar. Essa técnica é chamada de recursão. <br>

Ex: 
```
function recursiva(max) {
  console.log(max);
  if (max >= 10) return;
  max++;
  recursiva(max);
}

recursiva(-10);
```
# Funções geradoras

>Geradores são funções cuja execução pode ser interrompida e posteriormente reconduzida. Seus contextos (de associações de variáveis) ficarão salvos entre cada recondução.

Ex:
```
function* geradora1() {
  yield 'Valor 1';
  yield 'Valor 2';
  yield 'Valor 3';
}

const g1 = geradora1();
console.log(g1.next().value);
console.log(g1.next().value);
console.log(g1.next().value);
```
>A palavra-chave yield é usada para pausar e resumir uma generator function (function* or generator function legada).