# numbers: conceitos  básicos
para trasnformar um number em uma string <br>
EX:
```
console.log(varialQualquer.toString() + varialQualquer);
```
representação binária de um número. <br>
Ex:
```
let num = 10;
console.log(num.toString(2));
```
#### caso o número tenha muitas casas decimais, para deixar-lo com X casas decimas usar-se "tofixed(n), também ira arredondar".
Ex:
```
let num = 10.132164231000408480484

console.log(num.toFixed(2));
10.58
```
#### caso eu queira saber se o número é um inteiro ou não, usar-se "isInteger(n) para retornar um valor boolean (true ou false)".
Ex:
```
let num = 10.888
console.log(Number.isInter(num));
false
```