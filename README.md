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

Estas fueron ejemplos de las diferencias y características clave en relación con las variables y tipos en TypeScript en comparación con JavaScript. En general, TypeScript proporciona un sistema de tipos estático opcional que brinda beneficios en términos de seguridad, detección de errores temprana y mantenibilidad del código.
