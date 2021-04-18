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
# função que retorna uma soma 

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