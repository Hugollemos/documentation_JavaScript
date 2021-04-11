# diferenças entre const,var e let.

## const:
Const é uma variavel como let e var, mas  que recebe um valor que fica FIXO, fazendo com que não possa ser reatribuido um valor na mesma constante.
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