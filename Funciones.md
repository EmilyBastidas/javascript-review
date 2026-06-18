# Declaración de funciones

Las funciones son bloques de código reutilizables que realizan una tarea específica.

---

## Sintaxis básica

```js
function saludar() {
  console.log("Hola");
}
```

Para ejecutar la función:

```js
saludar();
```

Resultado:

```text
Hola
```

---

## Parámetros

Los parámetros son variables que recibe una función.

```js
function saludar(nombre) {
  console.log("Hola " + nombre);
}
```

---

## Argumentos

Los argumentos son los valores enviados a la función.

```js
saludar("Emily");
```

En este ejemplo:

- `nombre` → parámetro
- `"Emily"` → argumento

---

## Return

Permite devolver un valor.

```js
function sumar(a, b) {
  return a + b;
}
```

Uso:

```js
const resultado = sumar(5, 3);

console.log(resultado);
```

Resultado:

```text
8
```

---

## Ejemplo práctico

```js
function calcularTotal(precio, cantidad) {
  return precio * cantidad;
}

const total = calcularTotal(10, 3);

console.log(total);
```

Resultado:

```text
30
```

---

## PDT

Una función no se ejecuta cuando se declara.

```js
function saludar() {
  console.log("Hola");
}
```

Solo se ejecuta cuando es llamada:

```js
saludar();
```

---

## PDT

No confundir:

```js
function saludar(nombre) {}
```

- `nombre` → parámetro

```js
saludar("Emily");
```

- `"Emily"` → argumento

## PDT: Cómo analizar una función con parámetros

Ejemplo:

```js
function multiplicar(a, b) {
  return a * b;
}

console.log(multiplicar(2, 4));
```

Paso 1:

```js
a = 2;
b = 4;
```

Paso 2:

```js
return 2 * 4;
```

Resultado:

```js
8;
```

Paso 3:

```js
console.log(8);
```

Salida:

```text
8
```

### Regla rápida

Cuando una función recibe argumentos:

```js
miFuncion(valor1, valor2);
```

JavaScript asigna:

```js
parámetro1 = valor1;
parámetro2 = valor2;
```

antes de ejecutar el código de la función.

## PDT: ¿Qué guarda una variable cuando llamo una función?

Ejemplo:

```js
function saludar(nombre) {
  return "Hola " + nombre;
}

const mensaje = saludar("Emily");
```

Paso a paso:

```js
nombre = "Emily";
```

```js
return "Hola Emily";
```

Entonces:

```js
mensaje = "Hola Emily";
```

### Regla rápida

Cuando una función tiene `return`, la variable guarda el resultado que devuelve la función, no el código de la función ni sus parámetros por separado.

## PDT: Una función puede participar en expresiones

El valor devuelto por una función puede utilizarse igual que cualquier otro dato.

```js
function sumar(a, b) {
  return a + b;
}

const resultado = sumar(10, 5) + sumar(2, 3);
```

Paso a paso:

```js
sumar(10, 5); // 15
sumar(2, 3); // 5
```

La expresión se convierte en:

```js
15 + 5;
```

Resultado:

```js
20;
```

Una función devuelve un valor que puede almacenarse, compararse o utilizarse en otras operaciones.

# Arrow Functions

Las Arrow Functions son una forma más corta y moderna de escribir funciones en JavaScript.

---

## Función tradicional

```js
function saludar(nombre) {
  return "Hola " + nombre;
}
```

---

## Arrow Function

```js
const saludar = (nombre) => {
  return "Hola " + nombre;
};
```

---

## Sin parámetros

```js
const saludar = () => {
  return "Hola";
};
```

---

## Un parámetro

```js
const saludar = (nombre) => {
  return "Hola " + nombre;
};
```

---

## Return implícito

```js
const sumar = (a, b) => a + b;
```

Es equivalente a:

```js
const sumar = (a, b) => {
  return a + b;
};
```

---

## Ejemplo

```js
const multiplicar = (a, b) => a * b;

console.log(multiplicar(2, 4));
```

Resultado:

```text
8
```

---

## PDT

Las siguientes funciones hacen exactamente lo mismo:

```js
function sumar(a, b) {
  return a + b;
}
```

```js
const sumar = (a, b) => {
  return a + b;
};
```

```js
const sumar = (a, b) => a + b;
```

La diferencia está en la sintaxis, no en el resultado.

## PDT: Arrow Functions en React

En React es muy común encontrar funciones declaradas así:

```js
const handleAddTask = () => {
  console.log("Nueva tarea");
};
```

o

```js
const handleDeleteTask = (id) => {
  console.log(id);
};
```

Por eso es importante sentirse cómodo leyendo y escribiendo Arrow Functions.

# Scope

# Scope (Alcance)

El scope determina dónde puede ser utilizada una variable.

---

## Scope global

Las variables declaradas fuera de funciones o bloques son globales.

```js
const nombre = "Emily";

function saludar() {
  console.log(nombre);
}
```

La función puede acceder a `nombre` porque es una variable global.

---

## Scope local (de función)

Las variables declaradas dentro de una función solo existen dentro de ella.

```js
function saludar() {
  const mensaje = "Hola";
  console.log(mensaje);
}
```

Esto produce error:

```js
console.log(mensaje);
```

porque `mensaje` solo existe dentro de la función.

---

## Scope de bloque

Las variables declaradas con `let` o `const` solo existen dentro del bloque donde fueron creadas.

```js
if (true) {
  const edad = 25;
}
```

Esto produce error:

```js
console.log(edad);
```

---

## Diferencia entre var, let y const

```js
if (true) {
  var a = 1;
  let b = 2;
  const c = 3;
}

console.log(a); // 1
console.log(b); // Error
console.log(c); // Error
```

### Resumen

```text
var   → Scope de función
let   → Scope de bloque
const → Scope de bloque
```

---

## PDT

Piensa en el scope como habitaciones.

Las variables internas pueden acceder a variables externas.

Las variables externas no pueden acceder a variables internas.

```text
Dentro → puede mirar hacia afuera
Fuera  → no puede mirar hacia adentro
```

# Parámetros y Retorno

## Parámetros

Los parámetros son las variables que recibe una función.

```js
function saludar(nombre) {
  console.log("Hola " + nombre);
}
```

En este ejemplo:

```js
nombre;
```

es un parámetro.

---

## Argumentos

Los argumentos son los valores enviados a la función.

```js
saludar("Emily");
```

En este ejemplo:

```js
"Emily";
```

es un argumento.

---

## Return

`return` devuelve un valor desde una función.

```js
function sumar(a, b) {
  return a + b;
}
```

---

## Guardar el resultado

```js
const resultado = sumar(10, 5);
```

La variable guarda el valor retornado:

```js
resultado = 15;
```

---

## Diferencia entre console.log y return

### console.log

```js
function sumar(a, b) {
  console.log(a + b);
}
```

Muestra el resultado en consola.

### return

```js
function sumar(a, b) {
  return a + b;
}
```

Devuelve el resultado para poder reutilizarlo.

---

## PDT

Cuando una función recibe argumentos:

```js
miFuncion(valor1, valor2);
```

JavaScript asigna:

```js
parametro1 = valor1;
parametro2 = valor2;
```

antes de ejecutar el código de la función.

---

## PDT

Una variable guarda el resultado del `return`, no los parámetros ni el código de la función.

```js
const resultado = sumar(10, 5);
```

equivale a:

```js
const resultado = 15;
```
