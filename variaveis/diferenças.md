# diferenças entre const,var e let.

## CONST 
##### Const é uma variavel como let e var, mas recebe um valor que fica FIXO, fazendo com que não possa ser reatribuido um valor na mesma constante, mas caso for um objeto ai sim poderar ter alterações.
exemplo com erro:
```
if(true) {
  const d = 50
  d = 10
}
console.log(d)
```
exemplo com objeto:

```
const a = {nome: "Igor"};
a.nome = "José"
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
## VAR
##### Já com a variavel "var" além de poder modificar seu valor como variavel, ela por si só já tem um escopo global podendo ser chamada em qualquer lugar.<br>
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