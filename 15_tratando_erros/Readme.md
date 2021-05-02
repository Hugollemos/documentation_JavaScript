# Tratando e lançando erros com: try, catch, finally.

rotinas que trata erros, dando um feeedback sobre o possivel erro

O erro é gerado dentro (try) e passada por (catch) no catch o erro é tratado.

independente se ocorra erro o finally via ser executado

usando o throw, abro uma ecessao para um novo erro throw new error
Estrutura básica de erro
```
try {
  console.loj('Treinando js')
}catch(e) {
  console.log('erro');
}
```

try { //É Executado quando não há erros
} catch(e) { //é executado quando há erros 
} finally {
  //sempre
}