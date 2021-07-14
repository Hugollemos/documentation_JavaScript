# Strings
__as strings são indexadas, ou seja cada caractere tem um índice.__ <br>
Ex:
```
01234567
um texto
```
__Para ter a posição de um caractere como o "t".__ <br>
Ex:
```
let exemplo = "um texto"

console.log(exemplo[6]);
```
__Buscando uma posição, caso ela não exista, voltará: Undefined.__<br>
Ex:
```
let string = "um texto"

console.log(string[9]);

o resúltado será: Undefined
```
__Buscando o índice da palavra "texto":__<br>
Ex:
```
let string = "um texto"

console.log(`${string.indexOf('texto')} `);
```
__Buscando uma letra específica começando na posição 3:__ <br>

Ex:
```
console.log(`${string.indexOf('o',3)} `);
```

__Buscando uma letra específica de trás pra frente.__
```
console.log(`${string.lastIndexOf('o')} `);
```
__Lendo o tamanho da string__
```
console.log(string.length);
```
__Buscando trechos específica entre posições:__
```
console.log(string.slice(2,6));
```
# StartsWith
__Determinando se uma string começa com os caracteres especificados, retornará true ou false.__
Ex:
```
let curso="Estudo"
let c = "c"
console.log(curso.startsWith(c) ? "verdadeiro" : "falso")
```
# EndsWith
__O método endsWith() indica se uma string termina com determinados caracteres, retornando true ou false.__
Ex:
```
let curso="Estudo"
let c = "o"
console.log(curso.endsWith(c) ? "verdadeiro" : "falso")
```