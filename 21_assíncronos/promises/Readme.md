# promises

#### promises veio para subistituir as funções callbacks.

Uma Promise pode assumir quatro estados principais:
__Pending__: O estado inicial da Promise, ela foi iniciada mas ainda não foi realizada nem rejeitada.
__Fulfilled__: Sucesso da operação, é o que chamamos de uma Promise realizada (ou, em inglês, resolved).
__Rejected__: Falha da operação, é o que chamamos de uma Promise rejeitada (em inglês, rejected).
__Settled__: É o estado final da Promise, quando ela já sabe se foi resolved ou rejected.

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

OBS: Uma promise é um objeto que representa o sucesso ou a falha de uma operação assíncrona. 