
=======================###CASO 1###=========================
El evento está mal escrito, el event debe ir en mayuscula la primera letra ("addEventListener")
 guessSubmit.addeventListener('click', checkGuess());



=======================###CASO 2###=========================
 // Faltaba un punto en lowOrHi la cual es parte de la sintaxis
   const lowOrHi = document.querySelector('lowOrHi');
//SOLUCION: colocar el punto al principio en el parametro de querySelector
      const lowOrHi = document.querySelector('.lowOrHi');


//SOLUCION
  guessSubmit.addEventListener('click', checkGuess());


=======================###CASO 3###=========================
El numero de intento es de 10 y el que esta definido era de 5

  const ATTEMPS = 5;
//SOLUCION:
  const ATTEMPS = 10;

=======================###CASO 4###=========================
Convertir el tipo de dato a un Number para que se pueda reconocer en el proceso
//SOLUCION
let userGuess = Number(guessField.value);



=======================###CASO 5###=========================
La estructura de la condicional está mal planteada, la condicion deberia ser al reves, ya que el conteo de turnos muestra el mensaje de "perdiste" cuando llega a 10, en el caso del codigo esta al contrario por lo cual muestra el mensaje de "felicidades..."
   if (userGuess === randomNumber) {
      lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'black';
      lowOrHi.textContent = '';
      setGameOver();
    } else if (guessCount === ATTEMPS) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();
    }
//SOLUCION
  if (userGuess === randomNumber) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      
      lastResult.style.backgroundColor = 'green';
      lowOrHi.textContent = '';
      setGameOver();
    } else if (guessCount === ATTEMPS) {      
      lastResult.textContent = '!!!Pérdistes!!!';
      setGameOver();

    } 


=======================###CASO 6###=========================
Los colores de las alertas estan mal colocadas y algunos no corresponden donde deberian estar.

SOLUCION
//1: para este caso tenia el color rojo, pero era el verde lo cual se hizo el cambio
lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      
      lastResult.style.backgroundColor = 'green';
//2: en este caso el color que estaba asignado era el negro, se procedio a cambiar al color rojo ya que eso era parte del requerimiento
else if (guessCount === ATTEMPS) {      
      lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();

    } 
//3: el color colocado para este texto era verde y en el requerimiento solicitan el color negro, se procedió a realizar el cambio.
 lastResult.textContent = 'Incorrecto! ';
      lastResult.style.backgroundColor = 'black';




=======================###CASO 7###=========================
Se procedio a crear la condicional segun lo requerido que permite identificar si estan ingresando numeros, en este caso se evalua el tipo de dato y se retorna un mensaje en caso de que el valor ingresado sea distinto aun numero entero.

//SOLUCION:
    if(isNaN(userGuess)){
      return  lastResult.textContent = 'El valor ingresado es incorrecto ';
    }