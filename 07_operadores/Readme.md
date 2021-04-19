## Operadores de comparação:
```
> maior que
>= maior que ou igual a 
< menor que
<= menor que ou igual a 
== igualde (valor)
=== igualdade estrita (valor e tipo)
!= diferente (valor)
!== diferente (valor e tipo)
```
## Operadores Lógicos:
```
&& -> AND -> E -> Todas as expressoões precisam ser verdadeiras para retornar true 
|| -> OR -> OU -> Se uma espressão for negativa outra assumirá como verdadeira 
! -> NOT -> NÃO -> inverte o valor da espressão 
```
## Operadores ternários:
```
const pontuacaoUsuario = 1000;
const nivelUsuario = pontuacaoUsuario >= 1000 ? 'Usuário VIP' : 'Usuário normal';
console.log(nivelUsuario)
```