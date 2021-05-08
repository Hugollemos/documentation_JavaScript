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
function* cont(n){
  let c=0
  while(c<n){
    console.log(c)
    c++
  }
}

const ct=cont(10)

console.log(ct.next())
```

>A palavra-chave yield é usada para pausar e resumir uma generator function (function* or generator function legada).

