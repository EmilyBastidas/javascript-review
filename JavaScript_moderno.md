# JavaScript Moderno (ES6+)

Las características de ES6+ hacen que el código sea más limpio, legible y fácil de mantener.

---

## Template Literals

Permiten crear strings utilizando comillas invertidas (`` ` ``) e insertar variables con `${}`.

### Antes

```js
const nombre = "Emily";

const mensaje = "Hola, " + nombre;
```

### Ahora

```js
const nombre = "Emily";

const mensaje = `Hola, ${nombre}`;
```

Resultado:

```text
Hola, Emily
```

### Múltiples variables

```js
const nombre = "Emily";
const edad = 25;

const mensaje = `${nombre} tiene ${edad} años`;
```

Resultado:

```text
Emily tiene 25 años
```

### PDT

Usa Template Literals cuando necesites combinar texto y variables.

---

## Destructuring

Permite extraer valores de objetos o arrays y guardarlos en variables.

### Objetos

```js
const usuario = {
  nombre: "Emily",
  edad: 25,
};

const { nombre, edad } = usuario;
```

Ahora:

```js
console.log(nombre);
console.log(edad);
```

Resultado:

```text
Emily
25
```

### Arrays

```js
const colores = ["rojo", "azul", "verde"];

const [primero, segundo] = colores;
```

Resultado:

```js
primero = "rojo";
segundo = "azul";
```

### React

Muy usado en props y estados:

```js
const { title, is_done } = task;
```

---

## Rest & Spread

Aunque usan `...`, tienen propósitos distintos.

### Spread Operator

Sirve para copiar o expandir arrays y objetos.

#### Arrays

```js
const numeros = [1, 2, 3];

const copia = [...numeros];
```

Resultado:

```js
[1, 2, 3];
```

#### Objetos

```js
const usuario = {
  nombre: "Emily",
  edad: 25,
};

const copia = {
  ...usuario,
};
```

---

### Actualizar objetos

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

### React

```js
const updatedTask = {
  ...task,
  is_done: !task.is_done,
};
```

---

### Rest Operator

Agrupa elementos restantes.

```js
const numeros = [1, 2, 3, 4, 5];

const [primero, ...resto] = numeros;
```

Resultado:

```js
primero = 1;

resto = [2, 3, 4, 5];
```

También funciona con objetos:

```js
const usuario = {
  nombre: "Emily",
  edad: 25,
  pais: "Chile",
};

const { nombre, ...datos } = usuario;
```

Resultado:

```js
nombre = "Emily";

datos = {
  edad: 25,
  pais: "Chile",
};
```

### PDT

- Spread → expande o copia.
- Rest → agrupa lo que sobra.

---

## Optional Chaining

Evita errores cuando una propiedad puede no existir.

### Sin Optional Chaining

```js
const usuario = null;

console.log(usuario.nombre);
```

Error:

```text
Cannot read properties of null
```

---

### Con Optional Chaining

```js
const usuario = null;

console.log(usuario?.nombre);
```

Resultado:

```js
undefined;
```

No genera error.

---

### Objetos anidados

```js
const usuario = {
  direccion: {
    ciudad: "Santiago",
  },
};

console.log(usuario?.direccion?.ciudad);
```

Resultado:

```text
Santiago
```

---

Si no existe:

```js
const usuario = {};

console.log(usuario?.direccion?.ciudad);
```

Resultado:

```js
undefined;
```

---

### React

Muy utilizado cuando los datos vienen de una API.

```js
user?.name;

task?.title;

response?.data;
```

---

## PDT

### Template Literals

```js
`Hola ${nombre}`;
```

Sirven para insertar variables dentro de strings.

---

### Destructuring

```js
const { nombre } = usuario;
```

Extrae propiedades o elementos fácilmente.

---

### Spread

```js
const copia = [...array];
```

Copia o expande.

---

### Rest

```js
const [primero, ...resto] = array;
```

Agrupa los elementos restantes.

---

### Optional Chaining

```js
usuario?.nombre;
```

Evita errores cuando una propiedad puede no existir.
