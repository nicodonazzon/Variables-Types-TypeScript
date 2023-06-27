# Variables-Types-TypeScript
Como comienzo de la parte teórica del curso de TypeScript vamos a hablar de Variables y sus  tipos. 

En TypeScript, al igual que en JavaScript, puedes declarar variables para almacenar y manipular valores. Sin embargo, TypeScript introduce el concepto de "tipado estático", lo que significa que puedes especificar los tipos de datos que se asignarán a las variables. Esto brinda beneficios como detección de errores temprana, autocompletado de código y mejor mantenibilidad del código a medida que el proyecto crece.

Veamos algunas diferencias y características clave de las variables y tipos en TypeScript en comparación con JavaScript:

1. Declaración de variables con tipo:
   En JavaScript, las variables se declaran utilizando la palabra clave `var`, `let` o `const` sin especificar su tipo. En TypeScript, puedes declarar variables con un tipo específico. Por ejemplo:
   
   ```typescript
   let message: string = "Hola";
   ```

   Aquí, se declara una variable `message` con el tipo `string`, y se le asigna el valor `"Hola"`. El tipo especificado ayuda al compilador a realizar verificaciones estáticas en el código.

2. Inferencia de tipos:
   TypeScript también tiene la capacidad de inferir el tipo de una variable en función del valor asignado. Por ejemplo:

   ```typescript
   let count = 5; // TypeScript infiere que count es de tipo numérico (int,etc)
   ```

   En este caso, TypeScript deduce que la variable `count` es de tipo `number` porque se le asigna el valor `5`.

3. Tipos primitivos y personalizados:
   TypeScript admite los tipos de datos primitivos de JavaScript, como `number`, `string`, `boolean`, `null` y `undefined`. Además, también puedes definir tus propios tipos personalizados mediante interfaces o tipos de datos.

4. Tipo "any":
   TypeScript incluye el tipo especial `any`, que permite asignar cualquier tipo de valor a una variable sin realizar verificaciones de tipo. Es útil cuando se trabaja con código JavaScript existente o cuando se necesita flexibilidad en los tipos.

Lo anterior fueron ejemplos de clases primitivas, pero les dejo una lista completo de la mayoria de tipos que provee typescritp:

1. Tipos primitivos:
   - `number`: representa un número, tanto enteros como de punto flotante.
   - `string`: representa una cadena de texto.
   - `boolean`: representa un valor booleano (`true` o `false`).
   - `null`: representa un valor nulo.
   - `undefined`: representa un valor indefinido.
   - `symbol`: representa un identificador único e inmutable.
   - `bigint`: representa números enteros grandes.

2. Estructuras de datos:
   - `Array<T>`: representa un arreglo de elementos del tipo `T`.
   - `Tuple`: representa una secuencia de elementos con tipos específicos y longitud fija.
   - `Map<K, V>`: representa un mapa que asocia claves (`K`) con valores (`V`).
   - `Set<T>`: representa un conjunto de valores únicos del tipo `T`.
   - `WeakMap<K, V>`: es similar a `Map`, pero las claves son débiles y pueden ser recolectadas por el recolector de basura.
   - `WeakSet<T>`: es similar a `Set`, pero los elementos son débiles y pueden ser recolectados por el recolector de basura.

3. Funciones y objetos relacionados:
   - `Function`: representa una función en JavaScript.
   - `Date`: representa una fecha y hora.
   - `RegExp`: representa una expresión regular.
   - `Error`: representa un objeto de error.
   - `Promise<T>`: representa una operación asincrónica que produce un valor del tipo `T`.
   - `Iterable<T>`: representa una secuencia iterable de elementos del tipo `T`.
   - `Iterator<T>`: representa un iterador que puede generar secuencias de valores del tipo `T`.

4. Tipos especiales:
   - `any`: representa cualquier tipo de valor.
   - `void`: indica la ausencia de un valor.
   - `never`: representa un tipo de valor que nunca ocurre.
   - `unknown`: representa un valor desconocido.
   - `this`: representa el tipo "this" en un contexto de objeto.

5. Otros tipos útiles:
   - `Partial<T>`: convierte todos los miembros de un tipo `T` en opcionales.
   - `Required<T>`: convierte todos los miembros opcionales de un tipo `T` en obligatorios.
   - `Readonly<T>`: convierte todos los miembros de un tipo `T` en solo lectura.
   - `Pick<T, K>`: selecciona un subconjunto de propiedades del tipo `T` especificadas por las claves (`K`).
   - `Record<K, T>`: crea un objeto con claves (`K`) y valores (`T`).
   - `Exclude<T, U>`: excluye los tipos de `U` de `T`.
   - `Omit<T, K>`: omite las propiedades del tipo `T` especificadas por las claves (`K`).
   - `NonNullable<T>`: excluye `null` y `undefined` de `T`.
  
Pueden ver ejemplos de estos tipos en este link: [Enlace a Ejemplos](https://github.com/nicodonazzon/example-types/tree/main)

Creando tipos personalizados:

En TypeScript, puedes crear tipos personalizados utilizando interfaces, uniones, intersecciones y la palabra clave `type`. Estas características te permiten definir estructuras de tipos más complejas y flexibles.

1. Interfaces:
   Las interfaces te permiten definir la forma de un objeto, especificando los nombres y tipos de sus propiedades. Puedes utilizar interfaces para describir la forma de un objeto concreto o para definir un contrato que deben cumplir varios objetos.

   Ejemplo:
   ```typescript
   interface Persona {
     nombre: string;
     edad: number;
   }

   const persona: Persona = {
     nombre: "Juan",
     edad: 25
   };
   ```

2. Uniones:
   Las uniones te permiten combinar varios tipos en uno solo. Puedes utilizar el operador de tubería (`|`) para indicar que una variable puede tener uno de varios tipos posibles.

   Ejemplo:
   ```typescript
   type NumeroOTexto = number | string;

   function imprimirValor(valor: NumeroOTexto) {
     console.log(valor);
   }

   imprimirValor(42); // 42
   imprimirValor("Hola"); // "Hola"
   ```

3. Intersecciones:
   Las intersecciones te permiten combinar varios tipos en uno solo, tomando todas las propiedades de cada tipo. Puedes utilizar el operador de intersección (`&`) para combinar los tipos.

   Ejemplo:
   ```typescript
   interface PuedeCaminar {
     caminar(): void;
   }

   interface PuedeNadar {
     nadar(): void;
   }

   type PuedeCaminarYNadar = PuedeCaminar & PuedeNadar;

   function actuar(ser: PuedeCaminarYNadar) {
     ser.caminar();
     ser.nadar();
   }

   const personaAnfibia: PuedeCaminarYNadar = {
     caminar() {
       console.log("Caminando...");
     },
     nadar() {
       console.log("Nadando...");
     }
   };

   actuar(personaAnfibia); // Caminando... Nadando...
   ```

4. Tipo (Type):
   La palabra clave `type` te permite crear alias para tipos existentes o combinar tipos existentes en uno nuevo. Puedes utilizarlo para simplificar la escritura de tipos complejos o para dar nombres más descriptivos a tus tipos personalizados.

   Ejemplo:
   ```typescript
   type Coordenada = [number, number];

   type Punto = {
     x: number;
     y: number;
   };

   type Punto3D = Punto & {
     z: number;
   };

   const punto3D: Punto3D = {
     x: 1,
     y: 2,
     z: 3
   };
   ```

Estas son algunas de las herramientas que TypeScript ofrece para crear tipos personalizados. Puedes combinarlas y utilizarlas de diversas formas para adaptar los tipos a las necesidades específicas de tu proyecto.

Estas fueron ejemplos de las diferencias y características clave en relación con las variables y tipos en TypeScript en comparación con JavaScript. En general, TypeScript proporciona un sistema de tipos estático opcional que brinda beneficios en términos de seguridad, detección de errores temprana y mantenibilidad del código.
