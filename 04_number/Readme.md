# numbers.
para trasnformar um number em uma string <br>
EX:
```
function numberToString(num) {
  return num.toString();
}

console.log(typeof(numberToString(123)));
```
__representação binária de um número.__ <br>
Ex:
```
let num = 10;
console.log(num.toString(2));
```
#### Caso o número tenha muitas casas decimais, para deixá-lo com X casas decimas usar-se "tofixed(n), também ira arredondar".
Ex:
```
let num = 10.132164231000408480484

console.log(num.toFixed(2));
10.58
```
#### caso eu queira saber se o número é um inteiro ou não "isInteger(n) para retornar um valor boolean (true ou false)".
Ex:
```
let num = 10.888
console.log(Number.isInter(num));
false
```