>função executada com new retorna this <br> 
>this depende muito do contexto a onde ele é executado.

nesta forma this assume escopo global <br>
Ex:
```
function Usuario() {

  console.log(this)
}

Usuario();
``` 
>função executada com new retorna this como objeto da função. <br>
Ex:
```
function Usuario() {

  console.log(this)
}

 new Usuario();


Usuario {}
```
# call
O método call() é uma função capaz de alterar o valor this. Por padrão, o primeiro parâmetro que recebe o valor do this e o demais parâmetros são da função que invoca o método Call.
Ex:
```
function Personagem() {
  console.log(this)
}
 var personagemThis = {
   nome: 'hugo'
 }
Personagem.call(personagemThis, 123, [5])
```
>passando valores 
Ex:
```
function Personagem(p1, p2, p3) {
  console.log(p1, p2, p3)
  console.log(this)
}
 var personagemThis = {
   nome: 'hugo'
 }
Personagem.call(personagemThis, 'pram1', 123, [15])
```
# Apply
a diferença para o call é que no call é passado parametrô por parametrô, no aplly é por array
Ex:
```
function Personagem(p1, p2, p3) {
  console.log(p1, p2, p3)
  console.log(this)
}
 var personagemThis = {
   nome: 'hugo'
 }
Personagem.apply(personagemThis, [ 'pram1', 123, [15]])
```
# bind
não passa função, so passa o this e diz quem é os parametrôs.
O Bind por sua vez funciona de uma maneira diferente de call e apply, ao invés de executar uma função, este retorna uma nova função. O seu primeiro parâmetrô continua recebendo o valor que será atribuído ao this e os demais argumentos serão os parâmetros que definirão os valores atribuídos da primeira função. <br>
Ex:
```
function Personagem(p1, p2, p3) {
  console.log(p1, p2, p3)
  console.log(this)
}
 var personagemThis = {
   nome: 'hugo'
 }
  var pers = Personagem.bind(personagemThis, 'olá') 
  pers ('Mundo', '!!!');
```
# Arrow functions:
não possuem um escopo para o this. Em vez disso, elas passam para um próximo nível de execução. <br>
Ex: 
```
var soma = (a, b) => {
  return a + b;
}
console.log(soma(10, 10))
```