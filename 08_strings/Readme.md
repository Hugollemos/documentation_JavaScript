## strings
#### as strings sao indexadas, ou seja cada caractere tem um índice. 
exemplo
```
01234567
um texto
```
Para ter a posição de um caractere como o "t" usar-se esse código: string[6]
```
let string = "um texto"

console.log(string[6]);
```
Buscando uma posição, caso ela não exista, voltara: Undefined.<br>
Exemplo
```
let string = "um texto"

console.log(string[9]);

o resultado sera: Undefined
```

# formas de concatnar:
 
console.log(string.concat(' em um lindo dia.'));<br>
console.log(string + ' em um lindo dia. ');<br>
console.log(`${string} em um lindo dia. `);
-------------------------------------------------------------
### quero saber em qual índice a palavra "texto" está, devo usar:<br>
```
let string = "um texto"

console.log(`${string.indexOf('texto')} `);
```
### se eu quiser buscar alguma palavra específica começando com alguma letra, devo usar:

```
console.log(`${string.indexOf('o',3)} `);
```
ira buscar a letra "o", a partir da posição 3

começando a bucar de tras frente 
```
console.log(`${string.lastIndexOf('o')} `);
```
para ler o tamanho da strings
```
console.log(string.length);
```
quero saber a posição espesifica entre posições:
```
console.log(string.slice(2,6));
```
### startsWith
caso comece com o valor indicado;
Ex:
```
let curso="Estudo"
let c = "c"
console.log(curso.startsWith(c) ? "verdadeiro" : "falso")
```
### endsWith
caso termine com o valor indicado;
Ex:
```
let curso="Estudo"
let c = "o"
console.log(curso.endsWith(c) ? "verdadeiro" : "falso")
```
### includes 
verefica se o termo está na função;
Ex: 
```
let curso="Estudo"
let c = "tu"
console.log(curso.includes(c) ? "verdadeiro" : "falso")
```