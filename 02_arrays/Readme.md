# Arrays
 >serve para guarda valores em uma única variável, uma "lista de coisas". [ ] <br>

Ex:
 ``` const alunos = ['Hugo', 'elon', 'bill']; ```

>cada Array é indexado, para acessar algum array usar-se: ```console.log(alunos[n])```

Separa os arrays: ```alunos.join:``` <br>
tira uma parte do array "fatia": ```alunos.slice()``` <br>
tamanho do array: ```alunos.length``` <br>
para retirar um array do final: ``` alunos.pop();``` <br>
para adicionar um array no final: ``` alunos.push('nome');``` <br>
para adicionar um array no começo: ``` alunos.unshift('nome')``` <Br>
Fatiar: selecionar um grupo de arrays específicos ``` console.log(alunos.slice(0,2))```

# Método Splice

```nomes.slice(índice, delete, elemente, elem1, elem2, elem3);```
```
const nomes = ['Maria', 'João', 'Eduardo', 'Gabriel', 'Júlia'];
nomes.splice(4,1); //retirado o índice 4, segundo parametrô quantos elementos.
console.log(nomes);
```
<b>trabalhando com números negativos</b> <br>
Ex:

```
const nomes = ['Maria', 'João', 'Eduardo', 'Gabriel', 'Júlia'];
nomes.splice(-2,1);
console.log(nomes);*/
//substituindo 
const nomes = ['Maria', 'João', 'Eduardo', 'Gabriel', 'Júlia'];
nomes.splice(-2,1, 'Hugo');
console.log(nomes);
```
### push
Ex: <br>
```
const nomes = ['Maria', 'João', 'Eduardo', 'Gabriel', 'Júlia'];
nomes.splice(nomes.length, 0, 'Luiz', 'Otávio', 'Miranda');
console.log(nomes);
```
### Unshift
Ex:
```
const nomes = ['Maria', 'João', 'Eduardo', 'Gabriel', 'Júlia'];
nomes.splice(0, 0, 'Luiz', 'Otávio');
console.log(nomes);
```
# fillter, map, reduce 

### Filter - Filtrando o array
Ex:
```
const numeros = [5, 10, 80, 1, 2, 3, 5, 8, 7, 11, 15, 22, 27];

function CallbackFilter(valor) {
  return valor > 10;
}

const numeros02 = numeros.filter(CallbackFilter);
console.log(numeros02);
```
# Map - Mapeando o array
Ex:
```
const numeros = [5, 10, 80, 1, 2, 3, 5, 8, 7, 11, 15, 22, 27];

const numerosEmDobro = numeros.map(function(valor) {
  return valor * 2;
});
console.log(numerosEmDobro);
```
# Reduce - Reduzindo o array
Ex:
```
const numeros = [5, 10, 80, 1, 2, 3, 5, 8, 7, 11, 15, 22, 27];
const total = numeros.reduce(function(acumulador, valor, indice, array){
  acumulador += valor;
  return acumulador;
}, 0);
console.log(total);
```
# ForEach
Ex:
```
>somente interação 
const a1 = [10, 20, 30];
let total = 0;

a1.forEach(valor => {
  total += valor;
});

console.log(total);
```