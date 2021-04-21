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