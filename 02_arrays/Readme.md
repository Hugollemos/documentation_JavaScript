# Arrays
 __serve para guarda valores em uma única variável, uma "lista de coisas". [ ]__<br>
Ex:
 ``` const alunos = ['Hugo', 'elon', 'bill']; ```

__cada Array é indexado, para acessar algum array usar-se:__ ```console.log(alunos[n])```

## Acessando arrays

__Separa os arrays:__ ```alunos.join:``` <br>
__tira uma parte do array "fatia"__: ```alunos.slice()``` <br>
__tamanho do array:__```alunos.length``` <br>
__para retirar um array do final:__ ``` alunos.pop();``` <br>
__para adicionar um array no final:__ ``` alunos.push('nome');``` <br>
__para adicionar um array no começo:__ ``` alunos.unshift('nome')``` <Br>
__Fatiar: selecionar um grupo de arrays específicos__```console.log(alunos.slice(0,2))```

# Método Splice
```
nomes.slice(índice, delete, elemente, elem1, elem2, elem3);```
```
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
# Find
Ex:
```
 var victor = {
  nome: "victor Lima",
  empresa: "Guia do programador"
}

var david = {
  nome: "David",
  empresa: "umbler"
}

var erik = {
  nome: "Eril fig",
  empresa: "udemy"
}

var users = [victor, david, erik];

var usuario = users.find(user => user.nome == "victor Lima");

console.log(usuario);
```

### includes 
O método includes() determina se um array contém um determinado elemento, retornando true ou false apropriadamente.
Ex: 
```
let curso="Estudo"
let c = "tu"
console.log(curso.includes(c) ? "verdadeiro" : "falso")
```