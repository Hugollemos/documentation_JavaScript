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
> Retorna  valor em si (iteráveis, arrays ou strings)
```
const nome = 'Hugo Lemos'

for (let valor of nome) {
  console.log(valor);
}
```
# while e do while
```
while (expressao)
  instrucao

var contador = 0;
while (contador <= 5) {
  console.log(contador);
  ++contador;
}
```
// ou
>executa primeiro o código para depois checar a condição

do
  instrucao <br>
while (expressao)

BREAK:
O comando “break” serve para encerrar a leitura. O break é um comando que podemos utilizar quando queremos parar/encerrar o laço de repetição na hora.

CONTINUE:
Com este comando, é possível iniciar a próxima repetição do loop. 
Com a instrução continue, você poderá utilizá-la para apenas ignorar  uma iteração de loop.

# setInterval e setTimeout

>setInterval:  executa o comando em tempos em tempos <br>
>setTimeout: executa o comando uma vez 