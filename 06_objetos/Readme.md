# Objetos:
>Objetos: permitem juntar varios valores e acessá-los por sua propriedade, podendo passar "qualquer valor". <br>
>Usar chaves para criar um objeto { }. <br>
Ex:
```
let pessoa = {
  nome: 'Rafael',
  idade: 25,
  estaAprovado: true,
  sobrenome: 'de Souza'
};

console.log(pessoa);
```
### 1. Acessando os valores dentro do objeto individualmene:

```console.log(pessoa.nome);```

```console.log(pessoa['nome']);``` <br>
### 2. criando uma chave separada por hifen ```ultimo-nome```, precisa-se ser colocada entre aspas ```'ultimo-nome'``` <br>
para imprimir precisa-se colocar entre conchetes e aspas.
```console.log(usuario.['ultimo-nome']);```

### 3. Adicionando uma nova variavel
```pessoa.ano = 2021```

### 4. Apagando uma propriedade
```delete pessoa.idade;```

### 5. maneira mais curta de criar uma função dentro de um objeto:
Ex:
```
digaoi(name) {
  return `olá ${name}`; 
}
```
### 6. maneira mais curta para declarar o valor de uma variavel dentro de um objeto sem precisar declarar a chave.
Ex:
```
var cor = 'azul';

var usuario03 = {
  nome: 'hugo',
  cor 
}
```
### 7. object.assign()
Criando um novo objeto ou alterando um que já exista, a apartir de outros objetos.

passando {} vazias para criar um objeto novo. <br>
Ex:
```
var novoUsuario = object.assign({},usuario4, usuario3);
```

>No segundo parametrô qual objetos quero fazer merge. <br>
Ex:
```
var novoUsuario = object.assign({},usuario4, usuario3);
```

>jogando um objeto dentro de outro. <br>
```
object.assign(,usuario4, usuario3);
```
>Forma mais curta de fazer isso, com o spreader, fazer merjer com objetos.

### 8. spreader

*mesma coisa do object.assign()*
Ex:
```
var novouser = {
  ...usuario4,
  ...estrainfo
};
console.log(novouser)
```
### 9. getters e setters

As classes JavaScript contam com dois métodos especiais: um com o prefixo get que tem a função de retornar um valor, e outro precedido pela palavra set que serve para atribuir um valor.
### 10. destructuring

### Extraindo valores do objeto e armazenando em uma variavel:
*Forma tradicional:*
Ex:
```
var usuario = {
  nome: 'hugo',
  idade: 21,
  pais: 'Brasil'
};

var nome = usuario.nome;
var idade = usuario.idade;
```
*maneira mais curta:*
Ex:
```
var {idade, nome} = usuario;
console.log(idade, nome);
```
>10.1 extraindo a propriedade nome do novoUsuario2 e armazenando na variavel segundoNome.
Ex:
```
var {nome: segundoNome} = usuario;
console.log(segundoNome);
```
>10.2 Extraindo o valor de um objeto que está dentro de dois objetos
Ex:
```
var novoUsuario2 = {
  nome: {
    primeiro: 'hugo',
    ultimo: 'lemos'
  }
};

var {nome: {primeiro}} = novoUsuario2;
console.log(primeiro);
```

### 11. Destructuring com default value
Deixando um valor já pre-definido caso não tenha na propriedade do objeto.
Ex:
```
var novoUsuario2 = {
  nome: {
  primeiro: 'hugo',
  }
};
var {nome: {ultimo = 'lemos'}} = novoUsuario2;
console.log(ultimo);
```

### 12. Destructuring como parâmetro de function
Ex:
```
function imprimir (valor) {
   console.log(usuario.nome);
   console.log(usuario.idade);
   console.log(usuario.sexo);
 }

 var usuario = {
   nome: 'hugo',
   idade: 21,
   sexo: 'M'
 }

 imprimir(usuario);

 modo moderno
 function imprimir ({nome, idade, sexo}) {
  console.log(nome);
  console.log(idade);
  console.log(sexo);
}

var usuario = {
  nome: 'hugo',
  idade: 21,
  sexo: 'M'
}

imprimir(usuario);
```
### 13. Object.keys e Objects.values.
>Devolve um array com todas as chaves de um objeto
```console.log(Object.keys(usuario));```

imprimi somente os valores do objeto
```console.log(Object.values(usuario));```

###  Object.defineProperty() e Object.defineProperties()
Ex:
```
function Produto(nome, preco, estoque) {
  this.nome = nome;
  this.preco = preco;

  Object.defineProperty(this, 'estoque', {
    enumerable: true,
    value: estoque,
    writable: true,
    configurable: true
  });
}

const p1 = new Produto('camiseta', 20, 3);
console.log(Object.keys(p1));

for(let chave in p1) {
  console.log(chave);
}
```