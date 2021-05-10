# Estruturas de repetições

## 1. For clássico 
> geralmente com iteráveis (array ou strings) <br>

Ex:
```
for (let i = 0; i <= 10; i++) {
  console.log(i)
}
```
## 2. For in 
> Retorna o índice ou chave (string, array ou objetos)
> percorrer atributos de um objeto

Ex:
>para ter as chaves
```
const pessoa = {
  nome: 'Hugo',
  sobrenome: 'Lemos',
  idade: 30
};

for (let chave in pessoa) {
  console.log(chave)
}
------------
nome
sobrenome
idade
```
### para pegar os valores das chaves
```
const pessoa = {
  nome: 'Hugo',
  sobrenome: 'Lemos',
  idade: 30
};

for (let chave in pessoa) {
  console.log(chave, pessoa[chave])
}
--------------
nome Hugo
sobrenome Lemos
idade 30
```

## 3. For of
>percorrer arrays
> Retorna  valor em si (iteráveis, arrays ou strings)
```
const nome = 'Hugo Lemos'

for (let valor of nome) {
  console.log(valor);
}
```
# while e do while
<b>while</b>

```
while (expressao)
  instrucao

var contador = 0;
while (contador <= 5) {
  console.log(contador);
  ++contador;
}
```
<b>do while</b>
>Executa primeiro o código para depois checar a condição.

```
var contador = 0;
do { 
  console.log('contador');
  contador++;
}while (contador<10);
```
BREAK:
O comando “break” serve para encerrar a leitura. O break é um comando que podemos utilizar quando queremos parar/encerrar o laço de repetição na hora.

CONTINUE:
Com este comando, é possível iniciar a próxima repetição do loop. 
Com a instrução continue, você poderá utilizá-la para apenas ignorar  uma iteração de loop.

# setInterval e setTimeout

>setInterval: Repete a função enquanto o intervalo existir.
Ex:
```
setInterval(function() {
  console.log("Testando o setTimeout");

}, 1000);
```
>setTimeout: faz a chamada da função em tempo especificado.
Ex:
```
setTimeout(function() {
  console.log("Testando o setTimeout");

}, 2000);
```