# Asincronía

La asincronía permite ejecutar tareas que pueden tardar tiempo (peticiones a APIs, lectura de archivos, temporizadores, etc.) sin bloquear la ejecución del programa.

---

## ¿Qué significa que algo sea asíncrono?

JavaScript ejecuta el código línea por línea.

Código síncrono:

```js
console.log("Inicio");
console.log("Proceso");
console.log("Fin");
```

Resultado:

```text
Inicio
Proceso
Fin
```

---

En una tarea asíncrona, JavaScript puede continuar ejecutando otras instrucciones mientras espera una respuesta.

```js
console.log("Inicio");

setTimeout(() => {
  console.log("Han pasado 2 segundos");
}, 2000);

console.log("Fin");
```

Resultado:

```text
Inicio
Fin
Han pasado 2 segundos
```

---

## Promises

Una Promise representa una operación que terminará en el futuro.

Puede tener tres estados:

```text
Pending   → Pendiente
Fulfilled → Completada correctamente
Rejected  → Ocurrió un error
```

---

### Crear una Promise

```js
const promesa = new Promise((resolve, reject) => {
  const exito = true;

  if (exito) {
    resolve("Operación exitosa");
  } else {
    reject("Ocurrió un error");
  }
});
```

---

### Consumir una Promise

```js
promesa
  .then((resultado) => {
    console.log(resultado);
  })
  .catch((error) => {
    console.log(error);
  });
```

Resultado:

```text
Operación exitosa
```

---

### PDT

```js
.then()
```

Se ejecuta cuando todo sale bien.

```js
.catch()
```

Se ejecuta cuando ocurre un error.

---

## Async / Await

Es una forma más limpia de trabajar con Promises.

---

### Ejemplo

```js
const obtenerDatos = async () => {
  return "Hola";
};
```

---

### Esperar una Promise

```js
const obtenerDatos = async () => {
  return "Hola";
};

const mostrarDatos = async () => {
  const resultado = await obtenerDatos();

  console.log(resultado);
};

mostrarDatos();
```

Resultado:

```text
Hola
```

---

### ¿Qué hace await?

```js
await
```

Le dice a JavaScript:

> Espera a que esta Promise termine antes de continuar.

---

### PDT

```js
await
```

Solo puede usarse dentro de funciones:

```js
async;
```

---

## Fetch API

Permite realizar peticiones HTTP a servidores o APIs.

---

### GET

Obtener información.

```js
const getUsers = async () => {
  const response = await fetch("https://jsonplaceholder.typicode.com/users");

  const data = await response.json();

  console.log(data);
};
```

---

### ¿Qué ocurre aquí?

```js
const response = await fetch(...)
```

Obtiene la respuesta del servidor.

---

```js
const data = await response.json();
```

Convierte la respuesta a JavaScript.

---

### Flujo

```text
fetch()
↓
Response
↓
response.json()
↓
Objeto o Array JavaScript
```

---

## POST

Enviar información.

```js
const createUser = async () => {
  const response = await fetch("https://jsonplaceholder.typicode.com/users", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
    },
    body: JSON.stringify({
      name: "Emily",
    }),
  });

  const data = await response.json();

  console.log(data);
};
```

---

## Manejo de errores

Siempre es recomendable usar:

```js
try/catch
```

---

### Ejemplo

```js
const getUsers = async () => {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/users");

    const data = await response.json();

    console.log(data);
  } catch (error) {
    console.error(error);
  }
};
```

---

### ¿Qué hace?

```js
try
```

Intenta ejecutar el código.

---

```js
catch
```

Captura errores si algo falla.

---

### Ejemplo práctico

```js
try {
  const data = await getTasks();
  setTodos(data);
} catch (error) {
  console.error("Error obteniendo tareas:", error);
}
```

---

## Verificar response.ok

Una petición puede completarse pero devolver un error del servidor.

Por eso es común hacer:

```js
const response = await fetch(url);

if (!response.ok) {
  throw new Error("Error en la petición");
}
```

---

### Ejemplo completo

```js
const getTasks = async () => {
  try {
    const response = await fetch(API_URL);

    if (!response.ok) {
      throw new Error("Error obteniendo tareas");
    }

    const data = await response.json();

    return data;
  } catch (error) {
    console.error(error);
  }
};
```

---

## Relación con Taskify

Listar tareas:

```js
const data = await getTasks();
```

---

Crear tarea:

```js
await createTask(newTask);
```

---

Actualizar tarea:

```js
await updateTask(id, updatedTask);
```

---

Eliminar tarea:

```js
await deleteTask(id);
```

---

## Resumen

### Promise

Representa una operación futura.

```js
.then()
.catch()
```

---

### Async

Convierte una función en asíncrona.

```js
async function ejemplo() {}
```

---

### Await

Espera la resolución de una Promise.

```js
const data = await fetch(...)
```

---

### Fetch

Permite realizar peticiones HTTP.

```js
fetch(url);
```

---

### Try/Catch

Permite manejar errores.

```js
try {
  ...
} catch (error) {
  ...
}
```

---

## PDT

Flujo típico en proyectos React:

```js
try {
  const response = await fetch(url);

  if (!response.ok) {
    throw new Error("Error");
  }

  const data = await response.json();

  return data;
} catch (error) {
  console.error(error);
}
```

Este patrón aparece constantemente al trabajar con APIs y bases de datos.
