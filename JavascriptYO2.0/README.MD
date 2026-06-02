
NOTAS SOBRE JAVASCRIPT:

 En este archivo buscare  entender todo el temario Javascript, pero solamente lo escencial, la sintaxis y su logica, para poder realizar el reto que tengo pendiente, con estrucuturas de datos (  CRUD , SPA, API'S etc.).

VARIABLES: Entendemos que las varibales, es esa parte donde almacenamos la informacion ingresada ya sea momentanea o no. se diferencian en tres tipos:
     
     let: En esta variable se pueden modificar los datos ingresados y reutilizar en el mismo codigo a futuro.

     const: Contrario a la anterior, Se usa para constantes, es decir, valores que no van a cambiar nunca una vez asignados.

     var: es la forma antigua. Hoy en día no se recomienda usarla porque tiene comportamientos extraños con el alcance de los datos que solían causar muchos errores.

     TIPOS DE DATOS:

     String = Cadena de texto ("")
     Number = Numerios (1,2,3,4 o   3,21, 3,14....)
     boolean = 2 valores ( true o false)
     Array = Es una lista [1,2,3,4 ]


    ESTRUCTURAS DE DATOS: 
    Para realizar las condiciones, se utiliza parentesis () y el codigo que se ejecuta en llaves {}
    
    EJ:
let hora = 14;
if (hora < 12) {
    console.log("Buenos días");
} else if (hora < 18) {
    console.log("Buenas tardes"); // Se ejecutará esto
} else {
    console.log("Buenas noches");


    
}

BUCLES:
El bucle for universal en JS se escribe así:
// (Inicio; Condición de parada; Incremento paso a paso)
for (let i = 1; i <= 5; i++) {
    console.log("Número: " + i);
}

Nota de sintaxis: i++ es la forma corta en JS de decir "súmale 1 a la variable i".

- . El bucle for...of (Para elementos de una colección)

Este bucle llegó en ES6 y es una maravilla. Sirve para recorrer los valores de elementos iterables como Arrays, Strings, Maps o Sets. Olvídate de los contadores i++.

- . El bucle for...in (Para propiedades de un objeto)

A diferencia del anterior, este bucle está diseñado para recorrer las claves o propiedades (keys) de un objeto.(⚠️ Cuidado: No se recomienda usar for...in para arrays, ya que recorre los índices como strings y puede iterar sobre propiedades heredadas en el prototipo, lo que causa comportamientos extraños.)

- . El bucle for...in (Para propiedades de un objeto)

A diferencia del anterior, este bucle está diseñado para recorrer las claves o propiedades (keys) de un objeto. (⚡ Dato importante: A diferencia de for o for...of, no puedes usar break o continue dentro de un .forEach(). Si necesitas detener el bucle a mitad de camino, este no es el indicado.)

- El bucle do...while (Ejecuta y luego pregunta)

Es el hermano menor del while. La única diferencia (pero crucial) es que siempre se ejecuta al menos una vez, porque la condición se evalúa al final del ciclo, no al principio.


FUNCIONES:

Las funciones en JavaScript son sumamente poderosas. Tradicionalmente se escriben con la palabra function, pero la sintaxis moderna (ES6) introdujo las famosas Funciones Flecha (Arrow Functions), que son más cortas y estilizadas.

function saludar(nombreUsuario) {
    return "Hola " + nombreUsuario;
}


5. El Corazón de JS: Objetos y Arrays

JavaScript organiza la información compleja usando estos dos pilares:
Arrays (Listas indexadas)

Guardan elementos ordenados por una posición que empieza en 0.

let frutas = ["Manzana", "Banana", "Uva"];
console.log(frutas[0]); // Imprime "Manzana"


Objetos (Estructuras Clave-Valor)

Son la gloria de JavaScript. Te permiten mapear el mundo real en el código usando propiedades.

esumen de Reglas de Oro de JavaScript:

    Sensible a mayúsculas: miVariable y mivariable son dos cosas totalmente distintas.

    CamelCase: Por convención, en JS las variables y funciones se escriben empezando en minúscula y cada nueva palabra en mayúscula (ej: calcularPrecioFinal).

    El punto y coma ;: Aunque el navegador suele perdonarte si lo olvidas, ponerlo al final de cada instrucción sigue siendo una excelente práctica para evitar errores visuales u ocultos.





    El Manejo de Errores (Saber fallar con estilo)

Los programas fallan. Es una ley universal. Un buen programador no es el que escribe código sin errores, sino el que sabe qué hacer cuando algo sale mal para que la aplicación no se cierre o se congele.

En JavaScript (y en casi todos los lenguajes modernos) esto se maneja con el bloque try / catch (Intentar / Capturar):

ejemplo:

try {
    // Intentamos ejecutar este código
    let resultado = funcionQueNoExiste(); 
} catch (error) {
    // Si lo de arriba falla, el programa no se muere; viene aquí y resolvemos el problema
    console.log("¡Ups! Hubo un error, pero lo tenemos controlado: " + error.message);
}



¡Perfecto! Aquí tienes una explicación súper descriptiva, estructurada y limpia, lista para que la copies y la guardes en tus apuntes o Notion.

Incluye la teoría, la sintaxis y ejemplos claros de cada condicional avanzado en JavaScript.
Guía Completa de Condicionales en JavaScript

En JavaScript, más allá del clásico if / else, existen estructuras y operadores avanzados que permiten controlar el flujo de la aplicación de forma más limpia, eficiente y legible.
1. Operador Ternario (? :)

Es una alternativa compacta al if / else tradicional. Se utiliza principalmente para asignar un valor a una variable o retornar un resultado basado en una condición en una sola línea de código.
Sintaxis:
JavaScript

condicion ? expresion_si_es_verdadero : expresion_si_es_falso;

Ejemplo Descriptivo:
JavaScript

const edad = 20;

// Si la edad es mayor o igual a 18, asigna "Permitido", de lo contrario "Denegado"
const acceso = edad >= 18 ? "Permitido" : "Denegado";

console.log(acceso); // Resultado: "Permitido"

2. Estructura switch

Se utiliza cuando una sola variable o expresión debe ser comparada con múltiples valores posibles (casos). Es la alternativa limpia a encadenar demasiados else if.
Componentes clave:

    case: Define el valor con el que se comparará la expresión.

    break: Detiene la ejecución del bloque. Si se omite, el código seguirá ejecutando los casos de abajo automáticamente.

    default: El bloque que se ejecuta si ninguno de los casos anteriores coincide (funciona como el else final).

Ejemplo Descriptivo:
JavaScript

const metodoPago = "tarjeta";

switch (metodoPago) {
  case "efectivo":
    console.log("Pago con efectivo. No aplica comisión.");
    break;
  case "tarjeta":
    console.log("Pago con tarjeta. Se aplica un 3% de comisión.");
    break;
  case "paypal":
    console.log("Pago con PayPal. Redirigiendo a la plataforma...");
    break;
  default:
    console.log("Método de pago no reconocido.");
}
// Resultado: "Pago con tarjeta. Se aplica un 3% de comisión."

3. Condicionales de Cortocircuito (Short-Circuit Evaluation)

JavaScript evalúa las expresiones lógicas de izquierda a derecha y se detiene (hace "cortocircuito") tan pronto como encuentra un resultado definitivo. Esto permite usarlos como condicionales rápidos.
A. Operador AND (&&)

Evalúa la segunda parte solo si la primera parte es verdadera (Truthy). Si la primera es falsa, se detiene inmediatamente.
JavaScript

const usuarioPremium = true;

// Solo se enviará el regalo si 'usuarioPremium' es verdadero
usuarioPremium && console.log("Enviando regalo exclusivo..."); 
// Resultado: "Enviando regalo exclusivo..."

B. Operador OR (||)

Devuelve el primer valor si este es verdadero (Truthy). Si el primer valor es falso (como null, undefined, 0, "", NaN), evalúa y devuelve el segundo valor. Se usa para asignar valores por defecto.
JavaScript

let nombreIngresado = ""; // Un string vacío cuenta como valor "Falsy"

// Como el nombre está vacío, toma el valor por defecto "Invitado"
let nombrePerfil = nombreIngresado || "Invitado";

console.log(nombrePerfil); // Resultado: "Invitado"

4. Operador de Fusión Nula (??) - Nullish Coalescing

Este operador nació para corregir un comportamiento estricto del operador OR (||). El operador ?? solo devuelve el valor de la derecha si el valor de la izquierda es estrictamente null o undefined.

A diferencia de ||, respeta los valores falsos válidos como el número 0 o un string vacío "".
Ejemplo Descriptivo:
JavaScript

let contadorMensajes = 0; // El usuario tiene 0 mensajes (un valor válido)

// Usando OR (Falla porque ve el 0 como "falso" y pone el respaldo)
let notificacionesOR = contadorMensajes || "Sin mensajes"; 

// Usando Nullish (Funciona porque 0 no es null ni undefined)
let notificacionesNullish = contadorMensajes ?? "Sin mensajes";

console.log(notificacionesOR);      // Resultado: "Sin mensajes" (Incorrecto)
console.log(notificacionesNullish); // Resultado: 0 (Correcto)

5. Encadenamiento Opcional (?.) - Optional Chaining

No es un condicional con palabras clave, pero actúa como un guardián condicional. Permite acceder a propiedades de objetos anidados sin peligro de romper la aplicación con un error si alguna de las propiedades intermedias es null o undefined.
Ejemplo Descriptivo:
JavaScript

const cliente = {
  nombre: "Ana",
  detalles: {
    // El objeto 'direccion' no fue definido por el usuario
  }
};

// Sin el ?. el código lanzaría el error: "Cannot read properties of undefined"
// Con el ?. el código se detiene pacíficamente y devuelve 'undefined'
const ciudadCliente = cliente.detalles.direccion?.ciudad;

console.log(ciudadCliente); // Resultado: undefined (La app no se rompe)