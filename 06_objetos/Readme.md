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
```
digaoi(name) {
  return `olá ${name}`; 
}
```
### 6. maneira mais curta para declarar o valor de uma variavel dentro de um objeto sem precisar declarar a chave.
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

### Extraindo valores de objeto e armazenando em variavel:
da forma tradicional
```
var usuario = {
  nome: 'hugo',
  idade: 21,
  pais: 'Brasil'
};

var nome = usuario.nome;
var idade = usuario.idade;
```
maneira mais curta 
var {idade, nome} = usuario;
console.log(idade, nome);

extraindo a propriedade e armazenando em outra variavel
var {nome: segundoNome} = usuario;
console.log(segundoNome);

var novoUsuario2 = {
  nome: {
    primeiro: 'hugo',
    ultimo: 'lemos'
  }
};

var {nome: {primeiro}} = novoUsuario2;
console.log(primeiro);


# Destructuring com default value

var novoUsuario2 = {
  nome: {
    primeiro: 'hugo',
    
  }
};
var {nome: {ultimo = 'lemos'}} = novoUsuario2;
console.log(ultimo);

pra deixar um valor já pre definido caso eu não tenho achado a propriedade no objeto

Destructuring como parâmetro de function

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

Object.keys e Objects.values
Devolve um array com todas as chaves de um objeto
console.log(Object.keys(usuario));

console.log(Object.values(usuario));
imprimi somente os valores do objeto
