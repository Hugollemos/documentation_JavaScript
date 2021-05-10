# Tratando e lançando erros com: try, catch, finally.
>Resumo: O erro é gerado dentro (try) e passada por (catch) no catch o erro é tratado.

>independente se ocorrer erro o finally é executado.

>Usando o throw, abro uma exceção para um novo erro ```throw new error()```  <br>
<b>Estrutura básica de erro</b>

```
  console.loj('Treinando js')
}catch(e) {
  console.log('erro');
} finally {
  console.log('escrita errada')
}
```