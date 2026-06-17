# ¿Qué son las variables?

Una variable es un espacio donde guardas información para poder usarla más adelante en tu programa, piensa en una variable como una caja con una etiqueta.

Por ejemplo:

let nombre = "Pedro";

Aquí:

nombre → es la etiqueta de la caja.
"Pedro" → es lo que guardaste dentro de la caja.

Luego puedes usar esa información cuando quieras:

console.log(nombre);

Resultado:

Pedro

## ¿Para qué sirven?

Imagina que estás haciendo una aplicación de tareas

let tarea = "Estudiar JavaScript";

En lugar de escribir "Estudiar JavaScript" una y otra vez, la guardas en una variable y la reutilizas, las variables permiten almacenar información para utilizarla posteriormente en un programa.

## Tipos de declaración

### var

Fue la forma original de declarar variables en JavaScript. Tiene alcance de función y actualmente se utiliza poco en proyectos modernos, es la forma antigua de declarar variables

var ciudad = "Santiago";

Hoy en día se recomienda usar let y const en lugar de var.

### let

Permite declarar variables cuyo valor puede cambiar durante la ejecución del programa, o sea, let se usa cuando el valor puede cambiar

let edad = 25;

edad = 26;

console.log(edad);

Resultado:

26

### const

Permite declarar variables cuyo identificador no puede ser reasignado después de su creación, se usa cuando no quieres reasignar la variable

const nombre = "Pedro";

console.log(nombre);

Esto funciona

Pero:

const nombre = "Pedro";

nombre = "Ana";

Produce un error porque const no permite reasignar el valor.

## Buenas prácticas

- Utilizar `const` por defecto.
- Utilizar `let` cuando el valor necesite cambiar.
- Evitar `var` en código moderno.
- Usar nombres descriptivos para las variables.

### Ejemplos

```js
let edad = 25;
edad = 26;

const nombre = "Emily";

const usuario = {
  nombre: "Emily",
  edad: 25,
};
```

## Cómo piensa el computador

Cuando escribes:

let nombre = "Pedro";

El computador hace algo parecido a:

Memoria:

nombre → "Pedro"

Y cuando escribes:

console.log(nombre);

Busca en memoria la variable nombre y muestra el valor asociado.

Ejemplo de la vida real
const usuario = "Pedro";
let tareasPendientes = 3;

console.log(usuario);
console.log(tareasPendientes);

Salida:

Pedro
3

Sin variables sería imposible almacenar datos, usuarios, tareas, configuraciones o cualquier información en una aplicación.

# ¿Qué es un tipo de dato?

Un tipo de dato le dice al computador qué clase de información está almacenando una variable, por ejemplo:

let nombre = "Pedro";

El computador sabe que "Pedro" es texto, por lo tanto es un string.

## Tipos de datos primitivos

JavaScript tiene varios, pero los más importantes al principio son:

1. String (texto)

Todo texto va entre comillas.

let nombre = "Pedro";
let ciudad = 'Santiago';

También puede ser una cadena vacía:

let mensaje = "";

Puedes verificar el tipo:

console.log(typeof nombre);

Resultado:

string

2. Number (números)

Incluye enteros y decimales

let edad = 25;
let precio = 19.99;
console.log(typeof edad);

Resultado:

number

3. Boolean (verdadero o falso)

Solo puede tener dos valores:

let estaLogueado = true;
let tieneTareas = false;
console.log(typeof estaLogueado);

Resultado:

boolean

4. Undefined

Significa que existe una variable, pero todavía no tiene valor.

let nombre;
console.log(nombre);

Resultado:

undefined

5. Null

Representa la ausencia intencional de un valor,

let usuario = null;

Ejemplo:

let fotoPerfil = null;

Porque el usuario todavía no ha subido una foto.

## Tipos de datos de referencia

6. Array (arreglo)

Sirve para guardar múltiples valores.

let gatos = ["Luna", "Milo", "Nina"];

Acceder a un elemento:

console.log(gatos[0]);

Resultado:

Luna

## PDT:

En programación la mayoría de las estructuras que utilizan índices comienzan a contar desde `0`, no desde `1`, por ejemplo:

```js
const gatos = ["Luna", "Milo", "Nina"];

console.log(gatos[0]); // Luna
console.log(gatos[1]); // Milo
console.log(gatos[2]); // Nina
```

Aunque para las personas el primer elemento suele ser el número 1 para JavaScript el primer elemento se encuentra en la posición 0

7. Object (objeto)

Permite agrupar información relacionada.

let usuario = {
nombre: "María",
edad: 25,
ciudad: "Santiago"
};

Acceder a una propiedad:

console.log(usuario.nombre);

Resultado:

María

### Regla rápida para recordar

- Primitivos: guardan un valor directamente

String
Number
Boolean
Undefined
Null

Ejemplos:

let nombre = "Maria";
let edad = 25;
let activa = true;
let x;
let usuario = null;

- De referencia: guardan estructuras más complejas

Object
Array

Ejemplos:

const usuario = {
nombre: "Emily"
};

const gatos = ["Luna", "Milo"];
