### Ex:
```
function enviar(carpo, para, callback) {
  setTimeout(() => {
    console.log(`
      Para: ${para}
      --------------------------
      ${para}
      --------------------------
      De: Victor Lima
    `)

    callback();
  }, 3000)
}

enviar("Oi, seja bem vindo.", "Hugollemosdasilva.hu@gmail.com", () => {
  console.log("chamado do callback")
});
```