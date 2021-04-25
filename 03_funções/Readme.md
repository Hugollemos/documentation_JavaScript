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

(function autoExecuta() {
  console.log('Executei');
}());

>Função anônima é uma função sem nome
Ex: var subtrai3numb = function (a, b, c) {
  return a- b -;
}
console.log(subtrai3numb(15, 3, 5));

# Funções de callback
Uma função callback é uma função passada a outra função como argumento, que é então invocado dentro da função externa para completar algum tipo de rotina ou ação

Ex: 
```
function somaCallback(a,b, fncallback) {
  return fncallback(a+b);
}

console.log(somacallback(10,3, function(total){
  return total * 2;
}));
```

# função de callback

function somaCallback(a, b, fnCallback) {
  return fnCallback(a + b);
}

console.log(somaCallback(10, 3, function(total) {
  return total * 2;
}));

# não passando argumentos para afunção 
```
function escreveNome(nome,idade) {
  console.log(nome);
  console.log(idade)
}

escreveNome();
``` 
### não passando argumentos, o valor retornado sera "undefined", mas é possivel deixar o valor padão pre-definido dentro de parametrôs, como se estivesse passado argumentos, dessa forma:
Ex:
```
function escreveNome(nome = 'Hugo',idade = '21') {
  console.log(nome);
  console.log(idade)
}

escreveNome();
```