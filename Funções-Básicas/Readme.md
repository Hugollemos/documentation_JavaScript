# funções conceitos básicos
funções executam blocos de códigos 
usar-se a palavra reservada "function" para iniciar uma função
exeplo:

function saudacao(nome) {
  return  `Bora estudar ${nome} minino`;
}

const variavel = saudacao('hugo');
console.log(variavel)

podendo inviar parametros nas fnunções atravez de argumentos  
# função que retorna uma soma 

function soma (x, y) {
  const resultado = x + y;
  return resultado;
}

console.log(soma(2,4))

# hero functions
maneira mais mordena de fazer funções 

const raiz = function (n) {
  return n ** 0.5;
}
 
const raiz = (n) => {
  return n ** 0.5
}
console.log(raiz(9));

const raiz = n => n ** 0.5;

const raiz = function (n) => {
** 0.5;
} 