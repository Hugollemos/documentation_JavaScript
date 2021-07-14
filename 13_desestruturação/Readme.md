# Desestruturação com arrays
>Serve para extrair dados de um array e apresenta-los de maneiras mais curta. <br>
# Atribuição normal
Ex:
```
const usuario = ['Hugo',21,2021,'Maracanaú'];

  var nome = usuario[0];
  var idade = usuario[1];
  var ano = usuario[2];
  var cidade = usuario[3];

console.log(nome, idade, ano, cidade);

Hugo 21 2021 Maracanaú
```
# Com Desestruturação
Ex:
```
const usuario = ['Hugo',21,2021,'Maracanaú'];

var [nome, idade , ano, cidade] = usuario
console.log(nome, idade, ano, cidade);

Saída: Hugo 21 2021 Maracanaú
```
# Desestruturação de Objetos

### Atribuição normal
Ex:
```
const pessoa = {
  nome: 'Hugo',
  sobrenome: 'Lemos',
  idade: 21,
  endereco: {
    rua: 'rua do trilho',
    numero: 87
  }
}

const nome = pessoa.nome;
console.log(nome);
```
### Com Desestruturação
Ex:
```
const pessoa = {
  nome: 'Hugo',
  sobrenome: 'Lemos',
  idade: 21,
  endereco: {
    rua: 'rua do trilho',
    numero: 87
  }
}

const {nome, sobrenome} = pessoa;
console.log(nome, sobrenome);
```