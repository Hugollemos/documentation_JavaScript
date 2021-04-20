## Objeto Date
>permite trabalhar com datas e horas
>para usar a função Date/constutora precisa adicionar "new" na frente do date assim:
```
ex:
const data = new Date();
console.log(data.toString());
```

```
const data = new Date ('2021-04-19 15:38:10');
console.log('Dia', data.getDate());
console.log('Mês', data.getMonth());
console.log('Ano', data.getFullYear());
console.log('Hora', data.getHours());
console.log('Min', data.getMinutes());
console.log('ms', data.getSeconds());
console.log('Dia semana', data.getDay());
console.log('', data.toString());
```