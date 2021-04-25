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

### 2. Adicionando uma nova variavel
```pessoa.ano = 2021```

### 3. Apagando uma propriedade
```delete pessoa.idade;```

maneira mais curta de criar uma função dentro de um objeto:

digaoi(name) {
  return `olá ${name}`; 
}

maneira mais curta de declarar o valor de uma variavel dentro de um objeto sem precisar declarar uma chave e deixa-la redundante caso o nome da variavel seja iqual a uma propriedade do objewto, o valor da variavel cor sera armazenada na propriedade cor do objeto
var cor = 'azul';

var usuario03 = {
  nome: 'hugo',
  cor 
}
criando um novo objeto ou alterando um que ja exista

object.assign()

passando {} vazias, diz quer dizer quer criar um objeto novo, no segundo parametrô falo qual objetos quero juntarr
var novoUsuario = object.assign({},usuario4, usuario3);

jogando um objeto dentro de outro, é so não colocar as chacves {}, o objeto alvo sera usuario4,
caso eu queira colocar os atributos de um objeto dentro de outro objeto
object.assign(,usuario4, usuario3);
Existe uma forma mais curta de fazer isso, com o spreader
forma mais curta de fazer merjer com objetos 
>spreader
vai espelhar as proprieddes dos objetos para demntro do objeto novouser
mesca coisa do object.assign()

var novouser = {
  ...usuario4,
  ...estrainfo
};
console.log('novouser)

# getters e setters

As classes JavaScript contam com dois métodos especiais: um com o prefixo get que tem a função de retornar um valor, e outro precedido pela palavra set que serve para atribuir um valor.
 # destructuring
# para armazenar valores de chaves de um objeto em uma variavel(extraindo seus valores)

var usuario = {
  nome: 'hugo',
  idade: 21,
  pais: 'Brasil'
};
da forma tradicional
var nome = usuario.nome;
var idade = usuario.idade;
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
