# Objeto Math: conceitos básicos
>A função Math.max() retorna o maior de um ou mais números.
#### temos let num1 = 9.6548430 
para arredondar para baixo 
exemplo
```
let num1 = 9.5456;
let2 num2 = Math.floor(num1);
```
arredondnado para cima;
exemplo:
```
let num1 = 9.5456;
let2 num2 = Math.ceil(num1);
```

math.round arredonda da metade pra baixo ou pra cima 
exemplo:
```
let num1 = 9.49;
let2 num2 = Math.round(num1);
console.log(num2);
9
------------------

let num1 = 9.51;
let2 num2 = Math.round(num1);
console.log(num2);
```
>para escolher o maior número de uma seguência 
```console.log(Math.max(1, 2,4, -5, -8, 15000, 0, 6))```

>para escolher o menor número de uma seguência 
```console.log(Math.min(1, 2,4, -5, -8, 15000, 0, 6))```

>math.random() me volta números aleatorios <br>
```
const aleatorio = Math.random();
console.log(aleatorio);
```

#### números aleatorios entre 10 e 5
```
const aleatorio = math.random() * (10 - 5) + 5 
10 seria o máximo o minimo o 5
```

##### potência 
```
math.pow(2, 10) ou sonsole.log(2 ** 10);
raiz quadrada 
console.log(var ** (1/2)
```