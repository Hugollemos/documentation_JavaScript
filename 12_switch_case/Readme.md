# Switch e case 
>Se caso tiver uma estrutura de código que cheque varios valores em uma só variavel, com uma só comparação, switch é mais recomendado.
```

switch (diaSemana) {
  case 0:
    diaSemanaTexto = 'Domingo';
    break; //<- caso ache termine aqui.
  case 1:
    diaSemanaTexto = 'Segunda';
    break; //<- caso ache termine aqui.
  case 2:
    diaSemanaTexto = 'Terça';
    break; //<- caso ache termine aqui.
  case 3:
    diaSemanaTexto = 'Quarta';
    break; //<- caso ache termine aqui.
  case 4:
    diaSemanaTexto = 'Quinta';
    break; //<- caso ache termine aqui.
  case 5:
    diaSemanaTexto = 'Sexta';
    break; //<- caso ache termine aqui.
  case 6:
    diaSemanaTexto = 'Sábado';
    break; //<- caso ache termine aqui.
}
```