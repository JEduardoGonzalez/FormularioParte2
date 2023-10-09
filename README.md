# FormularioParte2
---
## Los arreglos en JavaScript. 

Un arreglo (array) es una estructura de datos que permite almacenar y organizar una colección ordenada de elementos. Estos elementos pueden ser de cualquier tipo, incluyendo números, cadenas de texto, objetos, funciones y otros arreglos. Puedes declarar un arreglo de varias maneras: 

- const miArreglo = []; // Notación literal
- const otroArreglo = new Array(); // Constructor 
- const numeros = [1, 2, 3, 4, 5]; // Arreglo con elementos

### Características clave sobre los arreglos en JavaScript: 

Los elementos en un arreglo se acceden mediante un índice numérico empezando en 0. Por ejemplo: 

- const miArreglo = [10, 20, 30]; 
- console.log(miArreglo[0]); // 10 
- console.log(miArreglo[2]); // 30 
 
Puedes obtener la longitud de un arreglo utilizando la propiedad length: 

- const miArreglo = [10, 20, 30]; 
- console.log(miArreglo.length); // 3 
 
Puedes modificar elementos en un arreglo asignando un nuevo valor a una posición específica: 

- const miArreglo = [10, 20, 30]; 
- miArreglo[1] = 25; 
- console.log(miArreglo); // [10, 25, 30] 
 
Puedes agregar elementos al final de un arreglo utilizando el método push() y eliminar elementos al final utilizando pop(). También puedes agregar y eliminar elementos al principio utilizando unshift() y shift(), respectivamente: 

- const miArreglo = [1, 2, 3]; 
- miArreglo.push(4); // Agrega 4 al final 
- miArreglo.pop(); // Elimina el último elemento (4) 
- miArreglo.unshift(0); // Agrega 0 al principio 
- miArreglo.shift(); // Elimina el primer elemento (0) 
 
Puedes recorrer los elementos de un arreglo utilizando bucles for, forEach(), map(), for...of y otros métodos de iteración. 

- const miArreglo = [1, 2, 3]; 
for (let i = 0; i < miArreglo.length; i++) { 
    console.log(miArreglo[i]); 
} 
 
- miArreglo.forEach((elemento) => { 
    console.log(elemento); 
}); 
 
Arreglos multidimensionales: Los arreglos en JavaScript pueden contener otros arreglos, lo que permite crear arreglos multidimensionales para estructuras de datos más complejas. 

- const matriz = [ 
    [1, 2, 3], 
    [4, 5, 6], 
    [7, 8, 9] 
]; 
- console.log(matriz[1][2]); // Accede al valor 6 
 
## Almacenamiento del navegador (sessionStorage y localStorage).
El almacenamiento web en los navegadores web se refiere a la capacidad de almacenar datos en el dispositivo del usuario desde una página web. Hay dos tipos principales de almacenamiento en el navegador: sessionStorage y localStorage. 

### sessionStorage: 

Generalmente, sessionStorage tiene una capacidad de almacenamiento de alrededor de 5-10 MB por dominio, aunque esto puede variar según el navegador. Los datos almacenados en sessionStorage permanecen disponibles durante la sesión del navegador. Se eliminan automáticamente cuando se cierra la ventana o la pestaña del navegador. 

**Acceso desde JavaScript:**
Almacenar datos: 
- sessionStorage.setItem("clave", "valor"); 
 
Recuperar datos: 
- const valor = sessionStorage.getItem("clave"); 
 
Eliminar datos: 
- sessionStorage.removeItem("clave"); 

**Ventajas de sessionStorage:**
- Los datos se eliminan automáticamente al cerrar la sesión del navegador, lo que puede ser útil para datos temporales.  
- Mayor seguridad en términos de privacidad, ya que los datos no persisten en el dispositivo después de cerrar la sesión.

**Desventajas de sessionStorage:**  
- Limitado a la duración de la sesión del navegador, lo que significa que los datos no estarán disponibles en sesiones posteriores.  
- Menor capacidad de almacenamiento en comparación con localStorage. 
 

### localStorage: 
localStorage suele tener una mayor capacidad de almacenamiento en comparación con sessionStorage, generalmente alrededor de 5-10 MB por dominio, aunque esto puede variar según el navegador. Los datos almacenados en localStorage persisten incluso después de cerrar y reiniciar el navegador. Permanecen en el dispositivo hasta que se eliminan explícitamente o hasta que se borran todos los datos del sitio web. 

**Acceso desde JavaScript:**
Almacenar datos: 
- localStorage.setItem("clave", "valor"); 
 
Recuperar datos: 
- const valor = localStorage.getItem("clave"); 
 
Eliminar datos: 
- localStorage.removeItem("clave"); 

**Ventajas de localStorage:**

- Los datos persisten incluso después de cerrar y reiniciar el navegador, lo que es útil para mantener preferencias y datos a largo plazo. 
- Mayor capacidad de almacenamiento. 

**Desventajas de localStorage:**
- Mayor riesgo de privacidad, ya que los datos pueden permanecer en el dispositivo a menos que se eliminen explícitamente. 
- No se eliminan automáticamente, lo que puede requerir una gestión manual de la limpieza de datos obsoletos. 

## ¿Qué es JSON? 

JSON (JavaScript Object Notation) es un formato de intercambio de datos ligero y de fácil lectura. Fue derivado de la notación de objetos de JavaScript, pero se utiliza como un formato independiente para representar datos estructurados. JSON se ha convertido en un estándar de facto para el intercambio de datos en aplicaciones web y se utiliza en una variedad de contextos, incluyendo la comunicación entre el cliente y el servidor. 

### Características de JSON: 

- JSON utiliza una sintaxis sencilla basada en pares clave-valor, que es fácil de entender y escribir tanto para humanos como para máquinas. 
- JSON admite tipos de datos comunes como números, cadenas de texto, booleanos, objetos y arreglos (arrays). Esto permite representar estructuras de datos complejas de manera jerárquica. 
- JSON es un formato de datos independiente del lenguaje, lo que significa que puede ser utilizado en una variedad de lenguajes de programación. La mayoría de los lenguajes de programación modernos tienen soporte integrado para analizar y generar datos JSON. 
- La sintaxis de JSON es legible para los humanos, lo que facilita la depuración y la manipulación manual de datos JSON. 
- JSON es un formato de datos ligero, lo que significa que no añade una carga significativa en términos de tamaño de archivo o consumo de recursos. 
- JSON se utiliza ampliamente en la comunicación entre el cliente y el servidor en aplicaciones web, en el almacenamiento de configuraciones y datos, en API REST, y en muchos otros contextos. 

## ¿Qué hacen las funciones JSON.parse() y JSON.stringify() ? 

### JSON.parse(): 

Se utiliza para analizar (parsear) una cadena JSON y convertirla en un objeto JavaScript. Toma una cadena JSON como argumento y devuelve un objeto JavaScript equivalente. La cadena JSON debe tener un formato válido, de lo contrario, se generará una excepción. 

Ejemplo: 
- const jsonString = '{"nombre": "Juan", "edad": 30}'; 
- const objeto = JSON.parse(jsonString); 
- console.log(objeto.nombre); // "Juan" 
 
### JSON.stringify(): 

Se utiliza para convertir un objeto JavaScript en una cadena JSON. Toma un objeto JavaScript como argumento y devuelve una cadena JSON equivalente. Puede aceptar un segundo argumento opcional llamado reemplazador, que permite personalizar la serialización del objeto o un tercer argumento opcional llamado espacios para dar formato con sangría a la cadena JSON resultante. 

Ejemplo: 
- const objeto = { nombre: "Juan", edad: 30 }; 
- const jsonString = JSON.stringify(objeto); 
- console.log(jsonString); // '{"nombre":"Juan","edad":30}' 

## ¿Cómo funciona window.location.href ? 

Es una propiedad de JavaScript que se utiliza para obtener o establecer la URL completa de la página actual en un navegador web. Puedes utilizar esta propiedad para redirigir el navegador a una nueva página o para obtener información sobre la URL actual. 

Si simplemente accedes a window.location.href, obtendrás la URL completa de la página actual como una cadena de caracteres. 
- const urlActual = window.location.href; 
- console.log(urlActual); // "https://www.ejemplo.com/pagina.html" 
 
También puedes usar window.location.href para redirigir el navegador a una nueva página web. Asignando una nueva URL a esta propiedad, el navegador cargará esa URL. Esto es útil para implementar la navegación y la redirección en una aplicación web. 
- window.location.href = "https://www.ejemplo.com/nueva_pagina.html"; 
 
Además, con window.location.href también puedes acceder a otras partes de la URL utilizando otras propiedades relacionadas con window.location. 
- window.location.host: Obtiene el nombre de host (dominio) de la URL. 
- window.location.pathname: Obtiene la ruta (path) de la URL. 
- window.location.protocol: Obtiene el protocolo de la URL (por ejemplo, "http" o "https"). 
- window.location.search: Obtiene la cadena de consulta (query string) de la URL. 

Ejemplo: 
- console.log(window.location.host); // "www.ejemplo.com" 
- console.log(window.location.pathname); // "/pagina.html" 
- console.log(window.location.protocol); // "https:" 
- console.log(window.location.search); // "?parametro=valor" 


## Explique el funcionamiento de scriptResultados.js 
De manera resumida cuenta con las siguientes funciones:

**Cargar datos en una tabla desde el almacenamiento local.**

Cuando se carga la página (evento DOMContentLoaded), el código busca un elemento HTML con el id "tablaResultados". 

Luego de eso, obtiene los datos del almacenamiento local utilizando localStorage.getItem("envios"). Estos datos representan una lista de envíos que están en formato JSON. Si no se encuentran datos en el almacenamiento local, se asigna un arreglo vacío como valor predeterminado. 

Luego, recorre la lista de envíos y crea filas HTML en la tabla para mostrar estos datos. Cada envío se representa como una fila en la tabla. 

**Limpiar la tabla y eliminar datos del almacenamiento local.**

Se agrega un evento click al botón con el id "limpiar". Cuando se hace clic en este elemento, se ejecuta una función. La función event.preventDefault() evita que la página se recargue cuando se hace clic en el botón. 

Luego, se elimina la tabla completa (tablaResultados.remove()). Pero esto no es todo ya que si se actualiza la página reaparecerá la tabla porque los datos siguen en el almacenamiento local, por lo que también se utiliza localStorage.removeItem("envios") para eliminar los datos del almacenamiento local con la clave "envios". 

**Volver a la página anterior.**

Se agrega un evento click al botón con el id "volver". Cuando se hace clic en este elemento, se ejecuta una función. La cual se trata de window.history.back() para retroceder a la página anterior en el historial del navegador. 

**Borrar una fila de la tabla y esos datos del almacenamiento local.**

Se agrega un evento click al botón con el id "borrar". Cuando se hace clic en este elemento, se ejecuta una función. 

La función solicita al usuario que escriba un ID. Luego, busca una fila en la tabla que coincida con ese ID. 

Si encuentra una fila con el ID proporcionado, la elimina de la tabla usando tablaResultados.deleteRow(i) y también elimina los datos correspondientes del almacenamiento local utilizando una función llamada eliminarDatosLocalStorage(id). 

La función eliminarDatosLocalStorage(id) obtiene los datos del almacenamiento local, filtra el envío con el ID proporcionado y actualiza el almacenamiento local con los datos restantes. 
