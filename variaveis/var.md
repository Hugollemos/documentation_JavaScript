# diferenças entre const,var e let.

## CONST 
##### Const é uma variavel como let e var, mas recebe um valor que fica FIXO, fazendo com que não possa ser reatribuido um valor na mesma constante.
exemplo:
```
const a = 10

console.log(a)
```
exemplo com erro:
```
const a = 10
a = 20
console.log(a)
```
##### porém o comando "console.log()" quando é executado fora do escopo da constante da em erro.<br>
exemplo:
```
if(true) {
const ab = 5
}
console.log(ab)
```

## LET
##### Com let é uma variavel que pode ter seu valor alterado como var, mas também precisa estar dentro do seu escopo para funcionar.
exemplo:
```
if(true) {
let ab = 5
ab = 500
console.log(ab)
}
```
