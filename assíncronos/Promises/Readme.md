>promises é um objeto

promises veio para subistituir as função calback
>Promises são um padrão de desenvolvimento que visam representar a conclusão de operações assíncronas. 

Uma Promise pode assumir quatro estados principais:
Pending: O estado inicial da Promise, ela foi iniciada mas ainda não foi realizada nem rejeitada
Fulfilled: Sucesso da operação, é o que chamamos de uma Promise realizada (ou, em inglês, resolved) — eu, pessoalmente, prefiro o termo resolvida.
Rejected: Falha da operação, é o que chamamos de uma Promise rejeitada (em inglês, rejected)
Settled: É o estado final da Promise, quando ela já sabe se foi resolved ou rejected

```
let p = new Promise((resolve, reject) => {
  let a = 1 + 1
  if (a ==2) {
    resolve('Sucess')
  } else {
    reject('Failed')
  }
})

p.then((message) => {
  console.log('This is in the then ' + message)
}).catch((err) => {
  console.log('This is the catch ' + err)
})
```

uma promise é um objeto que representa o sucesso ou a falha de uma operação assíncrona 