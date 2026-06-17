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
