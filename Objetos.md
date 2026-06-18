# Objetos

Los objetos permiten almacenar información relacionada mediante pares de clave y valor.

## Propiedades

Las propiedades son los datos que guarda un objeto.

```js
const usuario = {
  nombre: "Emily",
  edad: 25,
  estudiante: true,
};
```

Acceder a una propiedad:

```js
console.log(usuario.nombre);
```

Resultado:

```text
Emily
```

También se puede acceder con corchetes:

```js
console.log(usuario["edad"]);
```

Resultado:

```text
25
```

---

## Métodos

Los métodos son funciones que viven dentro de un objeto.

```js
const usuario = {
  nombre: "Emily",

  saludar() {
    return `Hola, soy ${this.nombre}`;
  },
};
```

Uso:

```js
console.log(usuario.saludar());
```

Resultado:

```text
Hola, soy Emily
```

### PDT

`this` hace referencia al objeto que está ejecutando el método.

---

## Desestructuración

Permite extraer propiedades de un objeto y guardarlas en variables.

```js
const usuario = {
  nombre: "Emily",
  edad: 25,
};

const { nombre, edad } = usuario;
```

Ahora podemos usar:

```js
console.log(nombre);
console.log(edad);
```

Resultado:

```text
Emily
25
```

### ¿Por qué es útil?

Evita escribir:

```js
usuario.nombre;
usuario.edad;
usuario.nombre;
usuario.edad;
```

muchas veces.

Muy utilizado en React:

```js
const { title, is_done } = task;
```

---

## Spread Operator

El operador spread (`...`) permite copiar o combinar objetos.

Objeto original:

```js
const usuario = {
  nombre: "Emily",
  edad: 25,
};
```

Copiar:

```js
const copia = {
  ...usuario,
};
```

Resultado:

```js
{
  nombre: "Emily",
  edad: 25
}
```

---

Modificar mientras se copia:

```js
const actualizado = {
  ...usuario,
  edad: 26,
};
```

Resultado:

```js
{
  nombre: "Emily",
  edad: 26
}
```

---

Agregar propiedades:

```js
const usuarioCompleto = {
  ...usuario,
  gatos: 4,
};
```

Resultado:

```js
{
  nombre: "Emily",
  edad: 25,
  gatos: 4
}
```

---

### React

Muy común para actualizar estado sin modificar el objeto original:

```js
const updatedTask = {
  ...task,
  is_done: !task.is_done,
};
```

---

## PDT

- Las propiedades almacenan datos.
- Los métodos son funciones dentro de objetos.
- La desestructuración extrae propiedades fácilmente.
- El spread operator copia y actualiza objetos sin modificar el original.
