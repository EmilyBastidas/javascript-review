# Arrays

Un array es una estructura que permite almacenar varios valores en una sola variable.

---

## Crear un array

```js
const gatos = ["Milo", "Luna", "Nina"];
```

---

## Índices

Los arrays comienzan en el índice `0`.

```text
Índice:  0      1      2
Valor:  Milo  Luna   Nina
```

---

## Acceder a elementos

```js
const gatos = ["Milo", "Luna", "Nina"];

console.log(gatos[0]);
```

Resultado:

```text
Milo
```

---

## Longitud

```js
const gatos = ["Milo", "Luna", "Nina"];

console.log(gatos.length);
```

Resultado:

```text
3
```

---

## Agregar elementos

```js
gatos.push("Pelusa");
```

Agrega un elemento al final del array.

---

## Eliminar elementos

```js
gatos.pop();
```

Elimina el último elemento.

---

## Modificar elementos

```js
gatos[1] = "Pelusa";
```

---

## Arrays de objetos

```js
const tareas = [
  { id: 1, title: "Estudiar JS" },
  { id: 2, title: "Practicar React" },
];
```

Acceder a una propiedad:

```js
console.log(tareas[0].title);
```

Resultado:

```text
Estudiar JS
```

---

## PDT

Los índices comienzan en `0`, no en `1`.

Si un array tiene:

```js
["a", "b", "c"];
```

Sus índices son:

```text
0 1 2
```

Aunque su longitud sea:

```js
3;
```

## map()

# map()

`map()` recorre un array y crea un nuevo array.

---

## Sintaxis

```js
array.map((elemento) => {
  return nuevoValor;
});
```

---

## Ejemplo

```js
const numeros = [1, 2, 3];

const dobles = numeros.map((numero) => {
  return numero * 2;
});
```

Resultado:

```js
[2, 4, 6];
```

---

## Forma corta

```js
const dobles = numeros.map((numero) => numero * 2);
```

---

## Con strings

```js
const nombres = ["Emily", "Ana"];

const saludos = nombres.map((nombre) => {
  return "Hola " + nombre;
});
```

Resultado:

```js
["Hola Emily", "Hola Ana"];
```

---

## Con objetos

```js
const usuarios = [{ nombre: "Emily" }, { nombre: "Ana" }];

const nombres = usuarios.map((usuario) => usuario.nombre);
```

Resultado:

```js
["Emily", "Ana"];
```

---

## React

```jsx
{
  tareas.map((task) => <p key={task.id}>{task.title}</p>);
}
```

Se usa para renderizar listas.

---

## PDT

`map()`:

- Recorre un array.
- Devuelve un nuevo array.
- No modifica el array original.

# filter()

`filter()` recorre un array y devuelve un nuevo array con los elementos que cumplen una condición.

---

## Sintaxis

```js
array.filter((elemento) => {
  return condicion;
});
```

---

## Ejemplo

```js
const numeros = [1, 2, 3, 4, 5];

const mayores = numeros.filter((numero) => numero > 3);
```

Resultado:

```js
[4, 5];
```

---

## Con strings

```js
const nombres = ["Ana", "Emily", "Luis"];

const largos = nombres.filter((nombre) => nombre.length > 4);
```

Resultado:

```js
["Emily", "Luis"];
```

---

## Con objetos

```js
const tareas = [
  { id: 1, title: "Estudiar JS", is_done: true },
  { id: 2, title: "Practicar React", is_done: false },
];

const completadas = tareas.filter((task) => task.is_done);
```

---

## React

```js
const pendientes = todos.filter((task) => !task.is_done);

const completadas = todos.filter((task) => task.is_done);
```

---

## Diferencia con map()

map() transforma elementos.

```js
[1, 2, 3]
↓
[2, 4, 6]
```

filter() selecciona elementos.

```js
[1, 2, 3, 4, 5]
↓
[4, 5]
```

---

## PDT

En `filter()`:

```js
true;
```

= el elemento se conserva.

```js
false;
```

= el elemento se elimina.

# find()

`find()` busca el primer elemento que cumple una condición y lo devuelve.

---

## Sintaxis

```js
array.find((elemento) => {
  return condicion;
});
```

---

## Ejemplo

```js
const numeros = [10, 20, 30, 40];

const resultado = numeros.find((numero) => numero > 25);
```

Resultado:

```js
30;
```

---

## Con objetos

```js
const usuarios = [
  { id: 1, nombre: "Emily" },
  { id: 2, nombre: "Ana" },
];

const usuario = usuarios.find((user) => user.id === 2);
```

Resultado:

```js
{
  id: 2,
  nombre: "Ana"
}
```

---

## Si no encuentra nada

```js
const resultado = numeros.find((numero) => numero > 100);
```

Resultado:

```js
undefined;
```

---

## Diferencia con filter()

```js
filter();
```

Devuelve todos los elementos que cumplen.

```js
find();
```

Devuelve únicamente el primero.

---

## PDT

`find()` deja de recorrer el array cuando encuentra la primera coincidencia.

Por eso suele ser más eficiente que `filter()` cuando solo necesitas un elemento.

# forEach()

`forEach()` recorre un array y ejecuta una acción por cada elemento.

---

## Sintaxis

```js
array.forEach((elemento) => {
  // acción
});
```

---

## Ejemplo

```js
const numeros = [1, 2, 3];

numeros.forEach((numero) => {
  console.log(numero);
});
```

Resultado:

```text
1
2
3
```

---

## Obtener el índice

```js
const gatos = ["Milo", "Luna", "Nina"];

gatos.forEach((gato, indice) => {
  console.log(indice, gato);
});
```

Resultado:

```text
0 Milo
1 Luna
2 Nina
```

---

## Diferencia con map()

```js
forEach();
```

Recorre elementos.

```js
map();
```

Recorre y devuelve un nuevo array.

---

## PDT

`forEach()` siempre devuelve:

```js
undefined;
```

Por eso no se usa para transformar datos.
