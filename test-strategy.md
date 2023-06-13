## -Fallo en la generación del número aleatorio: 
En la línea 44 let randomNumber = Math.random() * 10;, el código generaba un número aleatorio entre 0 y 10, en lugar de generar un número aleatorio entre 1 y 100. Se corrigió utilizando Math.floor(Math.random() * 100) + 1 para obtener un número aleatorio entre 1 y 100.
## -Fallo en los intentos que tiene el jugador:
 en la linea  46 la variable estaba incializada para que el jugador solo tuviera 5 intentos  const ATTEMPS = 5; se realizo la modificacion para que se cumpla con los 10 intentos const ATTEMPS = 10;
## -Fallo en la selección del elemento lowOrHi:
 En la línea const lowOrHi = document.querySelector('lowOrHi');, el código no utilizaba el selector de clase adecuado. Se corrigió agregando un punto antes de "lowOrHi". Debe ser const lowOrHi = document.querySelector('.lowOrHi');
## -Fallo en la validación del número ingresado por el jugador:
 el código no valida si el número ingresado por el jugador es un número entero. Esto podría causar problemas si el jugador ingresa un valor no numérico, se realizo una modificacion a la variable let userGuess = guessField.value; por let userGuess = Number(guessField.value); para que solo acepte numeros enteros asi mismo se agrego una condicion para validar si se ingresa un numero no valido
if (!Number.isInteger(userGuess)) {
  alert("Por favor, ingresa un número entero.");
  return;
}
## -Fallo en el evento click:
 En las lineas de codigo guessSubmit.addeventListener('click', checkGuess); y resetButton.addeventListener('click', resetGame);, la función addEventListener estaba escrita incorrectamente. La "e" en "addeventListener" debe estar en mayuscula. Se corrigió cambiándola a guessSubmit.addEventListener('click', checkGuess); y resetButton.addEventListener('click', resetGame);
## -Fallo en el cálculo del número aleatorio al reiniciar el juego:
 En la línea randomNumber = Math.floor(Math.random()) + 1;, la función Math.random() no estaba aplicada correctamente. Se realizo un cambio a randomNumber = Math.floor(Math.random() * 100) + 1; para generar un número aleatorio entre 1 y 100.
## -Fallo en el mensaje de Pérdistes y Felicitaciones! adivinaste el número:
  el mensaje de pérdida debe ser "!!!Pérdistes!!!" en color rojo. Sin embargo, en el código el mensaje de pérdida es "Felicitaciones! adivinaste el número!" en color rojo, la correccion que se realizo fue que en la condicion if(userGuess === randomNumber) se realizo un cambio para que aparezca el mensaje de lastResult.textContent = 'Felicitaciones! adivinaste el número!'; lastResult.style.backgroundColor = 'green' asi mismo aparecera en la otra condicion if(guessCount === ATTEMPS) el mensaje de lastResult.textContent = '!!!Pérdistes!!!'; lastResult.style.backgroundColor = 'red'; esto hara que al ganar apareza Felicitaciones! adivinaste el número en color verde y al perder  salga perdistes en color rojo
## -Fallo en el color que muestra la palabra incorrecto:
 Al poner un numero incorrecto mostraba el mensaje en color verde lastResult.textContent = 'Incorrecto! ';
      lastResult.style.backgroundColor ='green';, se hizo la correccion del codigo para que se mostrara de color negro: lastResult.textContent = 'Incorrecto! ';
      lastResult.style.backgroundColor = 'black';
## -Fallo al no mostrar el numero aleatorio:
Al perder el jugador no puede saber que numero es el que tenia que adivinar, se realizo una modificacion a la linea de codigo lastResult.textContent = '!!!Pérdistes!!!'; a lastResult.textContent = '!!!Pérdistes!!!El número correcto era ' + randomNumber; asi al momento de perder los 10 intentos le mostrara al jugador el numero aleatorio.