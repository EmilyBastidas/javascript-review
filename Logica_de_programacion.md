# Lógica de Programación

La lógica de programación es la capacidad de analizar un problema, dividirlo en pasos y construir una solución utilizando instrucciones que una computadora pueda entender.

Aprender sintaxis es importante, pero aprender lógica es lo que realmente permite resolver problemas.

---

## Algoritmos Básicos

Un algoritmo es una secuencia de pasos para resolver un problema.

### Ejemplo

Problema:

```text
Calcular el área de un rectángulo.
```

Algoritmo:

```text
1. Obtener la base.
2. Obtener la altura.
3. Multiplicar base × altura.
4. Mostrar el resultado.
```

Código:

```js
const base = 10;
const altura = 5;

const area = base * altura;

console.log(area);
```

Resultado:

```text
50
```

---

### Pensar antes de programar

Antes de escribir código, pregúntate:

```text
¿Qué datos tengo?
¿Qué resultado necesito?
¿Qué pasos me llevan de uno al otro?
```

---

## Resolución de Problemas

Una estrategia útil es dividir el problema en partes pequeñas.

---

### Ejemplo

Problema:

```text
Mostrar los números pares del 1 al 10.
```

Pensamiento lógico:

```text
1. Recorrer los números del 1 al 10.
2. Verificar cuáles son pares.
3. Mostrar únicamente los pares.
```

Código:

```js
for (let i = 1; i <= 10; i++) {
  if (i % 2 === 0) {
    console.log(i);
  }
}
```

Resultado:

```text
2
4
6
8
10
```

---

### Otro ejemplo

Problema:

```text
Contar cuántas tareas completadas existen.
```

Datos:

```js
const tareas = [{ is_done: true }, { is_done: false }, { is_done: true }];
```

Solución:

```js
const completadas = tareas.filter((tarea) => tarea.is_done);

console.log(completadas.length);
```

Resultado:

```text
2
```

---

## Patrones de pensamiento comunes

---

### Contar

```text
¿Cuántos elementos cumplen una condición?
```

Ejemplo:

```js
const numeros = [1, 2, 3, 4, 5];

const cantidad = numeros.filter((numero) => numero > 2).length;
```

Resultado:

```text
3
```

---

### Buscar

```text
Necesito encontrar un elemento específico.
```

Ejemplo:

```js
const usuario = usuarios.find((user) => user.id === 3);
```

---

### Transformar

```text
Necesito convertir datos en otros datos.
```

Ejemplo:

```js
const dobles = numeros.map((numero) => numero * 2);
```

---

### Acumular

```text
Necesito obtener un resultado único.
```

Ejemplo:

```js
const suma = numeros.reduce((acc, numero) => acc + numero, 0);
```

---

## Ejercicios Prácticos

---

### Ejercicio 1

Mostrar todos los nombres.

```js
const nombres = ["Emily", "Ana", "Luis"];
```

Resultado esperado:

```text
Emily
Ana
Luis
```

---

### Ejercicio 2

Obtener únicamente los números mayores a 10.

```js
const numeros = [5, 12, 8, 20, 15];
```

Resultado esperado:

```js
[12, 20, 15];
```

---

### Ejercicio 3

Duplicar cada número.

```js
const numeros = [1, 2, 3];
```

Resultado esperado:

```js
[2, 4, 6];
```

---

### Ejercicio 4

Encontrar un usuario por id.

```js
const usuarios = [
  { id: 1, nombre: "Emily" },
  { id: 2, nombre: "Ana" },
  { id: 3, nombre: "Luis" },
];
```

Buscar:

```js
id = 2;
```

Resultado esperado:

```js
{
  id: 2,
  nombre: "Ana"
}
```

---

### Ejercicio 5

Sumar todos los números.

```js
const numeros = [10, 20, 30];
```

Resultado esperado:

```text
60
```

---

## Método de resolución

Cuando te enfrentes a cualquier ejercicio:

### 1. Entender el problema

```text
¿Qué me están pidiendo?
```

---

### 2. Identificar los datos

```text
¿Qué información tengo?
```

---

### 3. Dividir en pasos

```text
¿Qué acciones necesito realizar?
```

---

### 4. Elegir herramientas

Pregúntate:

```text
¿Necesito recorrer?
→ for / forEach

¿Necesito transformar?
→ map

¿Necesito filtrar?
→ filter

¿Necesito buscar?
→ find

¿Necesito acumular?
→ reduce
```

---

### 5. Probar

Ejecuta el código y verifica que el resultado sea el esperado.

---

## PDT

Cuando un problema parece difícil:

```text
No intentes resolverlo completo de una vez.
```

Divídelo en problemas pequeños.

La mayoría de los algoritmos complejos son simplemente muchos problemas sencillos resueltos uno después del otro.

---

## PDT Personal

Antes de escribir código:

```text
1. ¿Qué tengo?
2. ¿Qué necesito obtener?
3. ¿Qué pasos me llevan hasta ese resultado?
```

Si puedes responder esas tres preguntas, normalmente ya tienes gran parte de la solución.
