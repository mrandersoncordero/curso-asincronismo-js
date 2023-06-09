## Que es el asincronismo?
⏳ El asincronismo es una manera de aprovechar el tiempo y los recursos de la aplicación, ejecutando tareas y procesos mientras otros son resueltos en background (como la llegada de la información de una API), para posteriormente continuar con las tareas que requerían esa información que no tenías de manera instantánea.

✍🏾 Conceptos importantes para entender el asincronismo:

 - 🧵 Thread: Thread para Javascript permite realizar programación multihilos en este entorno. En realidad, simula la creación y ejecución de hilos, pero para el desarrollador es lo mismo. Ésto simplifica muchísimo la creación de aplicaciones Javascript.
 - 🚫 Bloqueante: Una llamada u operación bloqueante no devuelve el control a la aplicación hasta que se ha completado. Por tanto el thread queda bloqueado en estado de espera.
 - 🚿 No bloqueante: Una tarea no bloqueante se devuelve inmediatamente con independencia del resultado. Si se completó, devuelve los datos. Si no, un error.
 - 🎞️ Síncrono: Las tareas se ejecutan de forma secuencial, se debe esperar a que se complete para continuar con la siguiente tarea.
 - 🚦 Asíncrono: Las tareas pueden ser realizadas más tarde, lo que hace posible que una respuesta sea procesada en diferido. La finalización de la operación I/O (entrada/salida) se señaliza más tarde, mediante un mecanismo específico como por ejemplo un callback, una promesa o un evento, lo que hace posible que la respuesta sea procesada en diferido.
 - 🛤️ Paralelismo: El paralelismo es la ejecución simultánea de dos o más tareas. Algunas tareas se pueden dividir en partes más pequeñas que pueden ser resueltas simultáneamente.
 -🎮 Concurrencia: La concurrencia es la capacidad de un algoritmo o programa para ejecutar más de una tarea a la vez. El concepto es similar al procesamiento paralelo, pero con la posibilidad de que muchos trabajos independientes hagan diferentes cosas a la vez en lugar de ejecutar el mismo trabajo.
 - 🌀 Eventloop o Loop de eventos: El bucle de eventos es un patrón de diseño que espera y distribuye eventos o mensajes en un programa.

📝 Formas de manejar la asincronía en JavaScript:

 - 📩 Callbacks: Una función que se pasa como argumento de otra función y que será invocada.
 - 🫱🏼‍🫲🏾 Promesas: (implementado en ES6) Una promesa es una función no-bloqueante y asíncrona la cual puede retornar un valor ahora, en el futuro o nunca. 
 - 🛣️ Async / Await: (implementado en ES2017) Permite estructurar una función asincrónica sin bloqueo de una manera similar a una función sincrónica ordinaria.

📌 En JavaScript casi todas las operaciones de I/O (Entrada y Salida) no se bloquean. A esto se le conoce como asíncronismo. Lo único que no es procesado antes de que termine la operación son los callbacks, ya que éstos están amarrados a una operación y esperan a que sea finalizada para poder ejecutarse.

## Que es el Event loop?

💬 El Event loop es el encargado de preguntar al Call Stack si ya ha terminado todas sus tareas. Entonces, si y solo si el Call Stack está vacío, el Event loop moverá las funciones que están en el Callback queue para que se ejecuten.

## Function Callback
Una función de callback es una función que se pasa a otra función como un argumento, que luego se invoca dentro de la función externa para completar algún tipo de rutina o acción.

```js
function sum(num1, num2){
    return num1 + num2;
}

function calc(num1, num2, callback){
    return callback(num1, num2);
}

console.log(calc(2, 3, sum));
```