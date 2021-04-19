# if, else if e else
```
> if -> se 
> else -> se não 
> else if -> se nenhuma das condições anteriores for satisfeita execute isso. 
```
Estrutura condicional que avalia uma condição booleana, se é true or false e executa um determinado código.
Ex:
```
const hora = 18;

if (hora >= 0 && hora <= 11) {
  console.log('Bom dia');
} else if (hora >= 12 && hora <= 17) {
  console.log('Boa tarde');
} else if (hora >= 18 && hora <= 23) {
  console.log('boa noite');
}
```