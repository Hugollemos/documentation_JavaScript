# diferenças entre const,var e let.

## CONST 
##### Const é uma variavel como let e var, mas recebe um valor que fica FIXO, fazendo com que não possa ser reatribuido um valor na mesma constante, mas caso for um objeto ai sim poderar ter alterações.
exemplo com erro:
```
if(true) {
  const d = 50
  d = 10
}
console.log(d)
```
exemplo com objeto:

```
const a = {nome: "Igor"};
a.nome = "José"
console.log(a)
```

##### porém o comando "console.log()" quando é executado fora do escopo da constante da em erro.<br>

exemplo:
```
if(true) {
const ab = 5
}
console.log(ab)
```

## LET
##### Com let é uma variavel que pode ter seu valor alterado como var, mas também precisa estar dentro do seu escopo para funcionar.
exemplo:
```
if(true) {
let ab = 5
ab = 500

console.log(ab)
}
```
## VAR
##### Já com a variavel "var" além de poder modificar seu valor como variavel, ela por si só já tem um escopo global podendo ser chamada em qualquer lugar.<br>
exemplo:
```
if(true) {
  var d = 50
}
console.log(d)

ou

if(true) {
  var d = 50
console.log(d)
}

ou até mesmo

var d = 50

if(true) {
console.log(d)
}
```

const descreve uma variável que não pode ser reatribuída (com o operador de atribuição =). Depois de criá-la, não podemos fazer algo assim:

const nome = 'luiz';
nome = 'joão'; // Erro: Assignment to constant variable.
Porém, existe uma diferença entre variável e valor.

Variáveis são como um apelido para um valor, uma espécie de alias para mencionar algum valor salvo na memória.

Já valores são os dados que realmente ficam salvos na memória e sustentam determinado tipo. Alguns tipos de valores são imutáveis, como number, string, boolean, undefined, null, symbol e bigint (os primitivos todos são imutáveis). Outros tipos são mutáveis, como arrays e objetos (objetos em geral são mutáveis, com exceção de null).

Valores mutáveis geralmente são estruturas de dados mais complexas que sustentam outros valores ou comportamentos internamente. Como é o caso do array, que pode ser composto por vários outros tipos de dados.

Quando usamos const com tipos primitivos, esse valor nunca mais poderá ser alterado. Nesse caso, além de const não permitir reatribuição, o valor também é imutável (consequentemente, nunca podemos alterar essa constante).

Já quando usamos const com valores mutáveis (como arrays e objetos), a variável continua sendo constante, porém os valores dentro do objeto poderão ser alterados. Isso acontece porque quando alteramos um valor interno de um objeto, não ocorre a reatribuição da variável com sinal de atribuição = (a variável continua apontando para o mesmo local na memória), apenas a alteração de um valor interno do mesmo objeto.

Por este motivo, pode-se usar const com objetos mutáveis e ainda assim alterar seus valores internos. A única coisa que não vamos conseguir fazer é reatribuir o valor da variável.

Exemplos:

Isso pode

const array = [1, 2, 3, 4, 5];
array.pop();
array[0] = 1024;
console.log(array); // [ 1024, 2, 3, 4 ]
 
Isso NÃO pode

const array = [1, 2, 3, 4, 5];
array = 'Legal'; // Assignment to constant variable.