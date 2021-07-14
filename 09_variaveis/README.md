# Const, Var e Let.

## CONST 
__Const é uma variavel como let e var, mas recebe um valor que fica FIXO, fazendo com que não possa ser reatribuido um valor na mesma constante, mas caso for um objeto, poderar ter alterações.__

__Alguns tipos de valores são imutáveis, como number, string, boolean, undefined, null, symbol e bigint (os primitivos todos são imutáveis). Outros tipos são mutáveis, como arrays e objetos (objetos em geral são mutáveis, com exceção de null).__

_Isso pode_
```
const array = [1, 2, 3, 4, 5];
array.pop();
array[0] = 1024;
console.log(array); // [ 1024, 2, 3, 4 ]
```
```
if(true) {
  const d = 50
  d = 10
}
console.log(d)
```
 
_Isso NÃO pode_
```
const array = [1, 2, 3, 4, 5];
array = 'Legal'; // Assignment to constant variable.
exemplo com erro:
exemplo com objeto:
```
```
const a = {nome: "Igor"};
a.nome = "José"
console.log(a)
```

##### Comando "console.log()" quando é executado fora do escopo da constante da em erro.<br>

exemplo:
```
if(true) {
const ab = 5
}
console.log(ab)
```

## LET
#####  Let é uma variavel que pode ter seu valor alterado como var, mas também precisa estar dentro do seu escopo(Global,Local e bloco) para funcionar.
exemplo:
```
if(true) {
let ab = 5
ab = 500

console.log(ab)
}
```
## VAR
##### var, além de poder modificar seu valor como variavel, ela por si só já tem um escopo global e local podendo ser chamada em qualquer lugar.<br>
exemplo:
```
if(true) {
  var d = 50
}
console.log(d)

ou

if(true) {
  var d = 50
console.log(d)
}

ou até mesmo

var d = 50

if(true) {
console.log(d)
}
```
