# DOM (Document Object Model)

El DOM es la representación de una página web como un conjunto de objetos que JavaScript puede leer y modificar.

Gracias al DOM, JavaScript puede:

- Seleccionar elementos HTML.
- Escuchar eventos.
- Modificar contenido.
- Cambiar estilos.
- Crear o eliminar elementos.

---

## Selección de elementos

Para manipular un elemento primero debemos seleccionarlo.

### querySelector()

Selecciona el primer elemento que coincida.

HTML:

```html
<h1 id="titulo">Hola Mundo</h1>
```

JavaScript:

```js
const titulo = document.querySelector("#titulo");

console.log(titulo);
```

---

### querySelectorAll()

Selecciona todos los elementos que coincidan.

HTML:

```html
<p>Uno</p>
<p>Dos</p>
<p>Tres</p>
```

JavaScript:

```js
const parrafos = document.querySelectorAll("p");

console.log(parrafos);
```

Resultado:

```text
NodeList(3)
```

---

### Seleccionar por clase

HTML:

```html
<div class="card">Contenido</div>
```

JavaScript:

```js
const card = document.querySelector(".card");
```

---

### Seleccionar por etiqueta

```js
const body = document.querySelector("body");
```

---

## Eventos

Los eventos permiten reaccionar a acciones del usuario.

Ejemplos:

- click
- submit
- input
- change
- keydown

---

### addEventListener()

Permite escuchar eventos.

HTML:

```html
<button id="btn">Click</button>
```

JavaScript:

```js
const boton = document.querySelector("#btn");

boton.addEventListener("click", () => {
  console.log("Botón presionado");
});
```

Resultado:

```text
Botón presionado
```

cada vez que se haga click.

---

### Evento input

HTML:

```html
<input id="nombre" />
```

JavaScript:

```js
const input = document.querySelector("#nombre");

input.addEventListener("input", (event) => {
  console.log(event.target.value);
});
```

Muestra el valor mientras el usuario escribe.

---

### Evento submit

HTML:

```html
<form id="formulario">
  <button>Enviar</button>
</form>
```

JavaScript:

```js
const formulario = document.querySelector("#formulario");

formulario.addEventListener("submit", (event) => {
  event.preventDefault();

  console.log("Formulario enviado");
});
```

---

### preventDefault()

Evita el comportamiento por defecto del navegador.

Muy utilizado en formularios.

```js
event.preventDefault();
```

---

## Manipulación del DOM

Permite modificar elementos existentes.

---

### Cambiar texto

HTML:

```html
<h1 id="titulo">Hola</h1>
```

JavaScript:

```js
const titulo = document.querySelector("#titulo");

titulo.textContent = "Hola Emily";
```

Resultado:

```html
<h1>Hola Emily</h1>
```

---

### Cambiar HTML

```js
titulo.innerHTML = "<span>Hola Emily</span>";
```

Resultado:

```html
<h1>
  <span>Hola Emily</span>
</h1>
```

---

### Cambiar estilos

```js
titulo.style.color = "purple";
```

```js
titulo.style.fontSize = "30px";
```

---

### Agregar clases

```js
titulo.classList.add("activo");
```

---

### Eliminar clases

```js
titulo.classList.remove("activo");
```

---

### Alternar clases

```js
titulo.classList.toggle("activo");
```

Si existe la elimina.

Si no existe la agrega.

---

### Crear elementos

```js
const parrafo = document.createElement("p");

parrafo.textContent = "Nuevo párrafo";
```

---

### Agregar elementos al DOM

```js
document.body.appendChild(parrafo);
```

Resultado:

```html
<body>
  <p>Nuevo párrafo</p>
</body>
```

---

### Eliminar elementos

```js
parrafo.remove();
```

---

## Ejemplo completo

HTML:

```html
<button id="btn">Cambiar texto</button>

<h1 id="titulo">Hola Mundo</h1>
```

JavaScript:

```js
const boton = document.querySelector("#btn");
const titulo = document.querySelector("#titulo");

boton.addEventListener("click", () => {
  titulo.textContent = "Hola Emily";
});
```

Al hacer click:

```text
Hola Mundo
```

↓

```text
Hola Emily
```

---

## Relación con React

En JavaScript puro:

```js
const titulo = document.querySelector("#titulo");

titulo.textContent = "Nuevo texto";
```

En React:

```jsx
const [texto, setTexto] = useState("Hola");

setTexto("Nuevo texto");
```

React actualiza el DOM automáticamente.

Por eso en React casi nunca usamos:

```js
document.querySelector();
```

porque React se encarga de manipular el DOM por nosotros.

---

## Resumen

### Selección

```js
document.querySelector();
document.querySelectorAll();
```

---

### Eventos

```js
addEventListener();
```

---

### Manipulación

```js
textContent;
innerHTML;
style;
classList;
```

---

### Crear elementos

```js
createElement();
appendChild();
remove();
```

---

## PDT

En JavaScript puro:

```js
document.querySelector();
```

se usa constantemente.

En React:

```js
useState();
```

y

```jsx
{datos.map(...)}
```

reemplazan gran parte de la manipulación manual del DOM.
