as instrings sao indexadas, ou seja cada caractere tem um indece, exemplo
```
01234567
um texto
```
se eu guiserce a posição de um caraxtere como o "t" usarei esse código.
```
let string = "um texto"

console.log(string[6]);
```
caso eu busque uma posição não exixstenet como:

let string = "um texto"

console.log(string[9]);

o resultado sera: Undefined

# formas de concatnar:
 
console.log(string.concat(' em um lindo dia.'));
console.log(string + ' em um lnido dia. ');
console.log(`${string} em um lindo dia. `);

quero saber em qual indice a palvra "texto" está, devo usar:

let string = "um texto"

console.log(`${string.indexOf('texto')} `);

se eu quiser buscar alguma palavra espesifica começando de tal letra, devo usar osequinte código

onsole.log(`${string.indexOf('o',3)} `);
ira buscar a letra "o", a partir da posição 3

começando a bucar de tras frente 
console.log(`${string.lastIndexOf('o')} `);

para ler o tamanho da strings
console.log(string.length);

quero saber a posição espesifica entre posições:
console.log(string.slice(2,6));