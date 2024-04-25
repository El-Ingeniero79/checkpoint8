<a name="top"></a>
# MANUAL JAVASCRIPT_CONCEPTOS AVANZADOS_ EQUIPO DEV-PRO

## Introducción
Antes de nada enhorabuena  por haber llegado hasta aqui, veo que has ido avanzando rapidamente y consolidandote en el equipo **Dev-Pro**.

En este manual te dare a conocer herramientas y conocimientos que haran que tu trabajo sea incluso más profesional. Espero te sea de ayuda

## Indice de contenidos

[¿Qué tipo de bucles hay en JS?](#item1)

[¿Cuáles son las diferencias entre const, let y var?](#item2)

[¿Qué es una función de flecha?](#item3)

[¿Qué es la deconstrucción de variables?](#item4)

[¿Qué hace el operador de extensión en JS?](#item5)

[¿Qué es la programación orientada a objetos?](#item6)

[¿Qué es una promesa en JS?](#item7)

[¿Qué hacen async y await por nosotros?](#item8)

---
<a name="item1"></a>
### ¿Qué tipo de bucles hay en JS?

Una de las principales ventajas de la programación es la posibilidad de crear **bucles y repeticiones** para tareas específicas, y que no tengamos que realizar el mismo código varias veces de forma manual.
![enter image description here](/imagenes8/bucles-iteraciones.png)

Antes de comenzar a aprender como funcionan los diferentes tipos de bucles existen, es necesario conocer algunos conceptos básicos relacionados con los bucles.

![enter image description here](/imagenes8/bucles-flujo-repeticion.png)

Al igual que en los condicionales `if`, en los bucles se va a **evaluar una condición** para saber si se debe seguir repetiendo el bucle o se debe finalizar. Habitualmente, lo que se suele hacer es establecer que si la condición es verdadera, se vuelve a repetir el bucle. Por el contrario, si es falsa, se finaliza. Sin embargo, esta condición puede variar dependiendo de la implementación que le indique el programador.

Otro concepto que usaremos mucho dentro de un bucle es el concepto de **Iteración**. Esto se refiere a cada una de las repeticiones de un bucle. Por ejemplo, si un bucle se repite como en el gráfico superior de este artículo (_de 0 a 3_*), se dice que hay **4 iteraciones**.

Muchas veces, los bucles que creamos incorporan un contador, que no es más que algo que irá guardando un número para contar el número de repeticiones realizadas, y así finalizar cuando se llegue a otro número concreto. Dicho contador hay que inicializarlo (_crearlo y darle un valor_) antes de comenzar el bucle.

Al igual que tenemos un contador en un bucle, también debemos tener una parte donde hagamos un **incremento** (_o un decremento_) de dicho contador. Si no lo tuvieramos, el contador no cambiaría y la condición siempre sería veradera, por lo que sería imposible salir del bucle.

Cuando estamos aprendiendo a programar, es muy común que cometamos un error creando el bucle y nos quedemos en un **bucle infinito**, es decir, en una situación donde nuestro programa se queda eternamente en bucle y nunca termina. Como programadores, esta situación siempre hay que evitarla. Para ello, lo que debemos hacer es siempre comprobar que existe un incremento (_o decremento_) y que en algún momento la condición va a ser falsa y se podrá salir del bucle.


 #### Bucle **While**

El primer tipo de bucle se denomina **bucle  `while`**. Este bucle se caracteriza en que se repite, revisando la condición en cada iteración y sólo se detiene cuando la condición es falsa. es el mas simple, pero que mejor que entenderlo con un ejemplo:
```
let i = 0;  // Inicialización de la variable contador

// Condición: Mientras la variable contador sea menor de 5
while (i < 5) {
  console.log("Valor de i:", i);

  i = i + 1; // Incrementamos el valor de i
}
```
Veamos que es lo que ocurre a la hora de ejecutar este código:

1.  Antes de entrar en el bucle  `while`, se inicializa la variable  `i`  al valor  `0`.
2.  Antes de realizar la primera  **iteración**  del bucle, comprobamos la  **condición**.
3.  Si la condición es  **verdadera**, hacemos las tareas que están indentadas dentro del bucle.
4.  Mostramos por pantalla el valor de  `i`.
5.  Luego, incrementamos el valor de  `i`  sumándole  `1`  a lo que ya teníamos en  `i`.
6.  Terminamos la iteración del bucle, por lo que volvemos al inicio del  `while`  a hacer una  **nueva iteración**.
7.  Volvemos al punto  `2)`  donde comprobamos de nuevo la  **condición**  del bucle.
8.  Repetimos hasta que la condición sea  **falsa**. Entonces, salimos del bucle y continuamos el programa.

**CUIDADO**
El bucle **while** es muy simple, pero requiere no olvidarse accidentalmente de la inicialización y el incremento (_además de la condición_), para no generar un error o un bucle infinito. Más adelante veremos otro tipo de bucle denominado bucle `for`, que tiene una sintaxis diferente y, habitualmente, se suele utilizar más en el día a día.

  #### Bucle **Do/While**
  
 Existe una variación del bucle  `while`  denominado  **bucle  `do while`**. La diferencia fundamental, a parte de variar un poco la sintaxis, es que este tipo de bucle siempre se ejecuta una vez, al contrario que el bucle  `while`  que en algún caso podría no ejecutarse nunca.

Para entenderlo bien, antes de ver el bucle  `do while`  vamos a analizar el siguiente ejemplo:
```
let i = 5;

while (i < 5) {
  console.log("Hola a todos");
  i = i + 1;
}

console.log("Bucle finalizado");

```
Observa, que aún teniendo un bucle, este ejemplo nunca mostrará el texto  `Hola a todos`, puesto que la condición nunca será verdadera, porque ya ha empezado como falsa (_`i`  ya vale  `5`  desde el inicio_). Por lo tanto, nunca se llega a realizar el interior del bucle.

Con el bucle  `do while`  podemos obligar a que  **siempre**  se realice el interior del bucle  **al menos una vez**:
```
let i = 5;

do {
  console.log("Hola a todos");
  i = i + 1;
} while (i < 5);

console.log("Bucle finalizado");
```
Observa los siguientes detalles de la variación  `do while`:

1.  En lugar de utilizar un  `while`  desde el principio junto a la condición, escribimos  `do`.
2.  El  `while`  con la condición se traslada al final del bucle.
3.  Lo que ocurre en este caso es que el interior del bucle se realiza  **siempre**, y sólo se analiza la condición al terminar el bucle, por lo que aunque no se cumpla, se va a realizar  **al menos una vez**.

#### Blucle **For**

El segundo tipo de bucle que veremos se denomina **bucle  `for`**. Este bucle se caracteriza en que se va a repetir, revisando la condición en cada iteración, hasta que no se cumpla la condición propuesta.

```
// for (inicialización; condición; incremento)
for (let i = 0; i < 5; i++) {
  console.log("Valor de i:", i);
}
```
Como vemos, la sintaxis de un  **bucle for**  es mucho más compacta y rápida de escribir que la de un  **bucle  `while`**, sin embargo puede parecernos más críptica cuando la vemos por primera vez.

La sintaxis del bucle for es mucho más práctica porque te obliga a escribir la  **inicialización**, la  **condición**  y el  **incremento**  antes del propio bucle, y eso hace que no te olvides de estos tres puntos fundamentales, cosa que suele ocurrir en los bucles  `while`, lo que suele desembocar en un bucle infinito. Aunque también puede ocurrir en el bucle for, suele ser menos habitual.

Analicemos la sintaxis del bucle:

1.  Separemos por  `;`  lo que establecemos dentro de los paréntesis del  `for`.
2.  Lo primero es la inicialización  `let i = 0`. Esto ocurre sólo una vez antes de empezar el bucle.
3.  Lo segundo es la condición  `i < 5`. Esto se comprueba al principio de cada iteración.
4.  Lo tercero es el incremento  `i++`, es decir,  `i = i + 1`. Esto ocurre al final de cada iteración.

#### Bucle For/in
El bucle iterará sobre todas las propiedades enumerables del objeto en sí y aquellas que el objeto hereda de su cadena de prototipos (las propiedades de los prototipos más cercanos tienen prioridad sobre las de los prototipos más alejados del objeto en su cadena de prototipos).

no te asustes por esta definicion, te pongo un ejemplo sencillo para que lo entiendas facilmente:

```
var obj = { a: 1, b: 2, c: 3 };

for (const prop in obj) {
  console.log(`obj.${prop} = ${obj[prop]}`);
}

// Produce:
// "obj.a = 1"
// "obj.b = 2"
// "obj.c = 3"
```

#### Bucle For/of
El bucle for/of nos  **facilita la escritura de nuestro bucle al tener un contador interno.**  Esto hace que se reduzcan los elementos que debemos definir dentro de nuestro bucle. Entonces, el bucle  _for of_ está compuesto por dos elementos:  **una variable temporal en la que tenemos el valor actual dentro del  _loop_  y un  _array_ a recorrer**. La variable temporal es una forma de almacenar el valor de cada ciclo del  _loop._

El funcionamiento del bucle  for/of  se puede entender en los siguientes pasos:

1.  **Iteración sobre Elementos:**  El bucle itera sobre cada uno de los elementos del iterable.
2.  **Asignación de Valor:**  En cada iteración, el valor del elemento actual se asigna a la variable especificada en  variable.
3.  **Ejecución del Bloque de Código:**  Se ejecuta el bloque de código dentro del bucle para cada elemento del iterable.
Por tanto, para escribir un bucle de este tipo podemos escribir lo siguiente:

```
//for in for of javascript 
for (let currentLanguage of languageArr) {
  console.log ('Language is     ${currentLanguage} ')
}
```
["Subir"](#top)
---
<a name="item2"></a>
### ¿Cuáles son las diferencias entre const, let y var?

Aunque  _const_,  _let_  y  _var_  se utilizan para declarar variables en JavaScript, cada una tiene sus propias características y particularidades, que es importante entender al aprender sobre «**let en java**» y «**var javascript**«.

-   **const**: se utiliza para declarar una variable cuyo valor no cambiará a lo largo del programa. Una vez que se le asigna un valor, no se puede reasignar. Las variables declaradas con const tienen un alcance de bloque.
-   **let**: se emplea para declarar una variable cuyo valor puede cambiar a lo largo del programa. Las variables declaradas con  _let_  tienen un alcance de bloque y son una parte clave cuando se aprende JavaScript.
-   **var**: sirve para declarar una variable cuyo valor puede cambiar a lo largo del programa. Las variables declaradas con  _var_  tienen un alcance de función y son una pieza fundamental al entender variables en JavaScript.

¿No te ha quedado claro claro con esta definición? , te pongo un ejemplo para aclararlo:

```
var controlador = true;

if(controlador) {

// Declaración de variables con const, let y var

  const a = 1;

  let b = 2;

  var c = 3;

}

// Intentar reasignar los valores de las variables

a = 4; // No se permite la reasignación porque a es una constante`

b = 5; // No se permite la reasignación fuera de su bloque, ilustrando "let vs"`

c = 6; // Se permite la reasignación, mostrando "var y" su flexibilidad`
```

["Subir"](#top)
---

<a name="item3"></a>
### ¿Qué es una función de flecha?

Es una forma moderna y corta de definir una función, es muy parecida a una expresión de función.

Se llama “funciones de flecha”, porque se ve así:

``` 
let func = (arg1, arg2, ..., argN) => expression;
 ```

Esto crea una función  `func`  que acepta los parámetros  `arg1..argN`, luego evalúa la  `expression`  del lado derecho mediante su uso y devuelve su resultado.

En otras palabras, es la versión más corta de:

```
let func = function(arg1, arg2,..., argN){
  return expression;
};
 ```

Veamos un ejemplo concreto:

```
let sum = (a, b) => a + b;
// Esta función de flecha es una forma más corta de:
//let sum = function(a, b) {return a + b;};

alert( sum(1, 2) ); // 3
```

Como puedes ver,  `(a, b) => a + b`  significa una función que acepta dos argumentos llamados  `a`  y  `b`. Tras la ejecución, evalúa la expresión  `a + b`  y devuelve el resultado.

-   Si solo tenemos un argumento, se pueden omitir paréntesis alrededor de los parámetros, lo que lo hace aún más corto.
    
    Por ejemplo:
    
 ```
    let double = n => n * 2;

// Más o menos lo mismo que: let double = function(n) { return n * 2 }

 
alert( double(3) ); // 6
```
    
-   Si no hay parámetros, los paréntesis estarán vacíos; pero deben estar presentes:
    
```   

let sayHi = () => alert("¡Hola!");  

sayHi();
 ```
    

Las funciones de flecha se pueden usar de la misma manera que las expresiones de función.

Por ejemplo, para crear dinámicamente una función:

``` 
let age = prompt("What is your age?", 18);
let welcome = (age < 18) ? () => alert('¡Hola!') : () => alert("¡Saludos!");

welcome(); 
```

Las funciones de flecha pueden parecer desconocidas y poco legibles al principio, pero eso cambia rápidamente a medida que los ojos se acostumbran a la estructura.

Son muy convenientes para acciones simples de una línea, cuando somos demasiado flojos para escribir muchas palabras.


Las funciones de flecha que estuvimos viendo eran muy simples. Toman los parámetros a la izquierda de  `=>`, los evalúan y devuelven la expresión del lado derecho.

A veces necesitamos una función más compleja, con múltiples expresiones o sentencias. En ese caso debemos encerrarlos entre llaves. La diferencia principal es que las llaves necesitan usar un  `return`  para devolver un valor (tal como lo hacen las funciones comunes).

Como esto:

```
let sum = (a, b) => { // la llave abre una función multilínea
  let result = a + b;
  return result; // si usamos llaves, entonces necesitamos un "return" explícito
};
  alert(sum(1, 2));// 3 
  ```

["Subir"](#top)
---
<a name="item4"></a>
### ¿Qué es la deconstrucción de variables?

Los objetos y arreglos en JavaScript nos permiten **agrupar variables y valores en un solo lugar.** Aunque esto es muy útil, hay momentos en los que queremos desempacar o deconstruir esta agrupación para acceder a una sola variable o a un solo valor. Esto te sera de mucha utilidad y por ello te incluyo este apartado en el manual

La deconstruccion  es una sintaxis o forma de escritura que nos permite  **extraer valores de un  _array_ o propiedades de un objeto en secciones más pequeñas.**  Esta deconstruccion hace que podamos acceder a elementos específicos de un conjunto más grande por medio de distintas variables. Esto abre la posibilidad de  **pintar un único valor o conjunto de valores de las variables de un objeto**, al igual que pintar determinadas propiedades de un valor de un  _array_.

A continuación, te explico como aplicarlo en los diferentes casos:

#### _**deconstruir objetos**_

Para ejemplificar cómo puedes deconstruir objetos en JavaScript,  **primero debemos tener un objeto en mente.** Supongamos entonces que tenemos el objeto  _character,_ que tiene las propiedades  _name, kind_ y  _role,_ cada una con un valor determinado.
```
let character = {

name: ‘Aragorn’,

kind: ‘human’,

role: ‘King of humans’

}
```
Entonces, con la deconstrucción de JavaScript  **podemos capturar una sola de estas propiedades en una nueva variable, fuera del objeto.**  Para ello, utilizamos cualquiera de las palabras clave de variables, luego encerramos la propiedad en las llaves { } y, finalmente, la igualamos al objeto del que proviene.  **A continuación, te mostramos exactamente cómo se escribe esto**:
```
let {role} = character
```
Ten presente que la deconstrucción  **sucede a la izquierda del operador aritmético de  _igual_. Es decir, sucede dentro de las llaves de la variable.** Ahora que hemos deconstruido la variable de su objeto, podemos acceder a ella de manera singular. Esto nos permite, por ejemplo, pintar el valor de esta variable únicamente. Para ello, utilizamos el comando  _console.log_ y pintamos el nombre de la nueva variable, como puedes ver en las siguientes líneas de código:
```
console.log (role)

// resultado pintado por pantalla: King of humans
```
También podemos capturar más de una propiedad de un elemento al separarlas por comas dentro de la deconstrucción. A continuación, verás la forma en la que lo haríamos para las propiedades  _name_  y  _role_:
```
let {name, role} = character;
```
Ahora, con estas variables deconstruidas podemos acceder a ellas para imprimir un  _string_:
```
console.log (‘${name} is ${role}’)

// resultado pintado por pantalla: ‘Aragorn is king of humans’
```
De este modo, podemos deconstruir las propiedades de un objeto  y pasarlas a ser variables individuales.

#### _**Deconstruir arrays**_

Con la sintaxis de desestructuración en JavaScript también podemos  **deconstruir  _arrays_ para extraer las propiedades de cada uno de sus valores.** Una de las propiedades básicas que podemos extraer en un  _array_  es el índice. .

**Para deconstruir un  _array_  en JavaScript debemos utilizar el método  _array.entries_**. Te pongo un ejemplo para hacerlo mas sencillo:
```
const arr = [1, 2, 3]
```
Usando el método  _arr.entries_ podemos deconstruir este  _array_ para acceder a su índice y pintar las parejas de este método:
```
const iteratorOfTheArr = arr.entries ( );

for (const [index, value] of iteratorOfTheArr ( )) {

console.log (index, value)

}
```
El resultado de estas líneas de código sería el siguiente (el primer numero es el índice y el segundo numero es el valor):
```
0 1 // indice 0 valor 1
1 2 // indice 1 valor 2
2 3 // indice 2 valor 3
```

La deconstrucción en JavaScript puede encontrarse mucho más en relación a los objetos. Esto sucede porque este lenguaje de programación es muy rico en las posibilidades que nos da para nombrar propiedades y valores en un objeto. De manera general, **cuando tenemos que estructurar datos, utilizamos los objetos.**  Por ello, serán los elementos que más se beneficien de la actividad de deconstruir. Por su parte, un  _array_ funciona más para acumular elementos.

["Subir"](#top)
---
<a name="item5"></a>
### ¿Qué hace el operador de extensión en JS?

El operador spread en JavaScript es una sintaxis introducida en ECMAScript 6 (ES6) que te permite propagar los elementos de un iterable (como arrays, cadenas u objetos), en otro iterable o llamada a función.

Se denota con tres puntos «`...`» seguidos de una expresión o un iterable. El operador spread es una potente herramienta que proporciona una forma concisa y flexible de trabajar con datos en JavaScript.

Puede utilizarse para concatenar arrays, crear copias superficiales de arrays, convertir cadenas en arrays de caracteres, fusionar o clonar objetos y pasar dinámicamente valores a funciones o constructores, entre otros casos de uso.

El operador spread simplifica las operaciones complejas y permite un código más expresivo y eficiente. Esto lo convierte en una función muy popular entre los  desarrolladores de JavaScript.

Con toda esta definicion estaras un poco perdido, asi que tranquilidad que te pongo unos ejemplos que clarificaran todos los conceptos:

#####  Concatenar Arrays[

Puedes utilizar el operador spread para distribuir los elementos de un array en otro array. Esto es especialmente útil para concatenar arrays o crear una copia superficial de una array.

Ejemplo:

```js
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];

// Concatenate arrays using spread operator
const concatenatedArr = [...arr1, ...arr2];
console.log(concatenatedArr); // Output: [1, 2, 3, 4, 5, 6]
```

##### Extendiendo Cadenas de Texto

Puedes utilizar el operador spread para desglosar los caracteres de una cadena en un array. Esto es útil para convertir una cadena en un array de caracteres, que puede manipularse o combinarse con otros arrays utilizando métodos de array.

Ejemplo:

```js
const str = "Hello";

// Spread characters of a string into an array
const charArray = [...str];
console.log(charArray); // Output: ['H', 'e', 'l', 'l', 'o']
```

##### Fusionar y Clonar Objetos
Puedes utilizar el operador spread para propagar las propiedades de un objeto en otro objeto. Esto es útil para fusionar o clonar objetos, crear un nuevo objeto con algunas propiedades anuladas o extraer propiedades específicas de un objeto.

Ejemplo:

```js
const obj1 = { a: 1, b: 2 };
const obj2 = { b: 3, c: 4 };

// Merge objects using spread operator
const mergedObj = { ...obj1, ...obj2 };
console.log(mergedObj); // Output: { a: 1, b: 3, c: 4 }

// Clone an object using spread operator
const clonedObj = { ...obj1 };
console.log(clonedObj); // Output: { a: 1, b: 2 }
```

##### Extender Argumentos de Función
El operador spread también puede ser usado en otros contextos, como los argumentos de una función, para pasar valores de manera dinámica a una función o constructor.

Ejemplo:

```js
// Pass array elements as arguments to a function using the spread operator
const numbers = [1, 2, 3];

const sum = (a, b, c) => a + b + c;

console.log(sum(...numbers)); // Output: 6
```

##### Combinación del Operador Spread con el Parámetro rest

El operador spread puede utilizarse junto con otras funciones modernas de JavaScript, como la desestructuración de arrays y objetos, para habilitar potentes técnicas de programación funcional. Te permite extraer y manipular elementos de arrays o propiedades de objetos con una sintaxis concisa y expresiva.

Ejemplo:

```js
const numbers = [1, 2, 3, 4, 5];
const [first, second, ...rest] = numbers;

console.log(first); // Output: 1
console.log(second); // Output: 2
console.log(rest); // Output: [3, 4, 5]
```

Los ejemplos anteriores muestran la versatilidad y flexibilidad del operador spread en JavaScript, convirtiéndolo en una herramienta poderosa para manipular y combinar datos de manera concisa y eficiente.

##### Comprender el Operador Spread y las Copias Superficiales

Es importante tener en cuenta que el operador spread crea copias superficiales de matrices y objetos, y puede tener implicaciones de rendimiento cuando se utiliza con arrays u objetos grandes.

```js
const originalArray = [[1, 2, 3, 4], 12];
const copiedArray = [...originalArray];

copiedArray[0].push(99);

console.log(originalArray); // Output: [[1, 2, 3, 4, 99], 12]
console.log(copiedArray); // Output: [[1, 2, 3, 4, 99], 12]
```

En este código,  `originalArray`  es una array con cuatro elementos. Utilizando el operador spread, creamos un nuevo array  `copiedArray`  y propagamos en él los elementos de  `originalArray`. A continuación, modificamos el primer elemento de  `copiedArray`  añadiendo  `99`  con el método  `push`.

Cuando obtengas la salida de  `copiedArray`, la salida mostrará que se ha añadido  `99`  al array del primer elemento, pero hay un problema con la copia superficial que hace el operador spread. El cambio en  `copiedArray`  afecta a  `originalArray`.

Esto se debe a que el operador spread no crea copias completamente nuevas de los elementos o propiedades, sino que comparte referencias a los elementos o propiedades originales. Esto puede tener implicaciones de rendimiento cuando se trabaja con arrays u objetos grandes.

Por lo tanto, si trabajas con arrays u objetos grandes, o si necesitas hacer modificaciones profundas en el array u objeto copiado sin afectar al original, quizá debas considerar otros enfoques, como la copia profunda o el uso de  [bibliotecas](https://kinsta.com/es/blog/bibliotecas-javascript/)  diseñadas específicamente para manejar estructuras de datos complejas.

Es esencial utilizar el operador spread con criterio y tener en cuenta las mejores prácticas para un rendimiento y una capacidad de mantenimiento óptimos.

##### Consejos para Optimizar el Rendimiento y Evitar Errores Comunes

Para optimizar el rendimiento y evitar errores comunes al utilizar el operador spread, ten en cuenta los siguientes consejos:

1.  Evita extender arrays u objetos grandes, especialmente en rutas de código críticas para el rendimiento.
2.  Ten en cuenta los posibles efectos secundarios al extender objetos anidados, y considera la posibilidad de utilizar técnicas de clonación profunda si es necesario.
3.  Utiliza el operador spread con criterio y considera enfoques alternativos si el rendimiento es un problema.

##### Resumen

El operador spread (…) permite concatenar arrays de forma concisa y limpia, clonar arrays y objetos, fusionar objetos, crear argumentos de función de forma dinámica, clonar objetos y arrays anidados complejos, etc.

Debido a su flexibilidad, el operador spread desempeña un papel importante en el futuro del desarrollo de JavaScript, ya que permite a los desarrolladores escribir código más conciso, legible y eficiente.

["Subir"](#top)
---
<a name="item6"></a>
### ¿Qué es la programación orientada a objetos?

La  **programación orientada a objetos (POO)**  es un paradigma de programación que se enfoca en el uso de objetos y sus interacciones para modelar y resolver problemas de la vida real.

**En JavaScript**, cada objeto tiene un prototipo,  que es otro objeto del que hereda propiedades y métodos.  Esto permite a los objetos compartir comportamiento entre sí de manera eficiente, en lugar de tener que definir todas sus propiedades y métodos individualmente. 
 
Por ejemplo, podemos crear un objeto person que tenga un prototipo personProto:

```
const personProto = {
  greet() {
    console.log('Hello!');
  },
};

const person = Object.create(personProto);

```

En este caso, el objeto person hereda el método greet() del objeto personProto. Luego, podemos llamar al método greet() en el objeto person:

```
person.greet(); // Hello!

```

**La POO se basa en cuatro principios fundamentales: abstracción, encapsulamiento, herencia y polimorfismo.**

-   **Abstracción**  
    En JavaScript se refiere a la habilidad de un programa para manipular y trabajar con objetos de manera genérica, sin tener que conocer los detalles de su implementación concreta. Esto permite escribir código que se pueda aplicar a diferentes tipos de objetos, y no solo a uno en particular.  
    
    Sería como tomar lo esencial o estrictamente necesario de un objeto para luego, a partir de este, crear otros y agregar características. De acuerdo a esto, lo “esencial” varía de acuerdo al contexto o finalidad de la aplicación que se realiza

```
class Animal {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(`${this.name} hace un sonido.`);
  }
}

```

En el ejemplo (muy muy simple) se puede ver que lo más básico que necesitaría es un nombre para un animal y un método “speak” para luego a partir de estos crear otros animales en otras clases. Lo verán más adelante en la herencia.

-   **Encapsulamiento**  
    Es un principio de programación que consiste en ocultar los detalles de implementación de una clase o objeto, y exponer solo la interfaz necesaria para que otros componentes puedan interactuar con él. De esta manera, se garantiza que los componentes dependan solo de la interfaz de la clase o objeto, y no de su implementación concreta.
    
    ```
      Para acceder a estas propiedades y métodos "ocultos" se pueden usar getters y setters
    
      **Los getters** son funciones que se utilizan para obtener el valor de una propiedad de un objeto
    
      **Los setters** son funciones que se utilizan para establecer un nuevo valor para una propiedad de un objeto.**		
    
    ```
    
-   **Herencia**  
    Es un concepto de programación orientada a objetos que permite que una clase adquiera las propiedades y comportamientos de otra clase. En JavaScript, la herencia se logra mediante el uso de la palabra clave ** extends** y permite que una clase hija herede las propiedades y métodos de una clase padre.
    

```
class Animal {
  constructor(name) {
    this.name = name;
  }
  speak() {
    console.log(`${this.name} hace un sonido.`);
  }
}
class Dog extends Animal {
  constructor(name, type) {
    super(name);
    this.type = type;
  }
}

```

_En el ejemplo la clase  **Dog**  toma el método “speak” y la propiedad “name” de la clase  **Animal**  y adicionalmente añade otra propiedad “type”_

-   **Polimorfismo**  
    Es un concepto de la programación orientada a objetos que se refiere a la habilidad de una función o método para tratar objetos de diferentes tipos de manera diferente. Esto permite a una función o método tener comportamientos diferentes dependiendo del tipo de objeto con el que se llame.  
    En JavaScript, el  polimorfismo se puede lograr mediante la herencia y la sobrecarga de métodos. La herencia se refiere a la capacidad de una clase hija de heredar las propiedades y métodos de una clase padre, y luego modificarlos o extenderlos para adaptarse a sus necesidades. La sobrecarga de métodos se refiere a la capacidad de una clase de tener múltiples implementaciones de un mismo método, con diferentes parámetros o tipos de retorno.

_**Ejemplo de sobrecarga:**_

Tenemos una clase Calculator que tiene un método add() que recibe dos números y devuelve su suma:

```
class Calculator {
  add(a, b) {
    return a + b;
  }
}

```

Luego, podemos agregar otra implementación de add() que recibe un solo número y devuelve ese número incrementado en uno:

```
class Calculator {
  add(a, b) {
    return a + b;
  }

  add(a) {
    return a + 1;
  }
}

```

En este caso la clase puede ejecutar el método “add” de dos formas para así obtener distintos resultados.

Ejemplo de Polimorfismo de reemplazo:  
Mantenemos la clase Animal con su método “speak”

```
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    console.log(`${this.name} makes a noise.`);
  }
}

```

Luego al crear la clase Dog podemos modificar el comportamiento del método “speak” para obtener otro resultado

```
class Dog extends Animal {
  constructor(name, breed) {
    super(name);
    this.breed = breed;
  }

  speak() {
    console.log(`${this.name} barks.`);
  }
}
```

["Subir"](#top)
---
<a name="item7"></a>
### ¿Qué es una promesa en JS?

Una promesa es un objeto que representa un valor que puede estar disponible ahora, en el futuro o nunca. Esta representación encapsula el resultado (éxito o error) de una operación asíncrona.
En otras palabras, proporcionan una forma más estructurada y legible de manejar operaciones asíncronas, permitiendo que el código sea más claro y más fácil de mantener al escribir acciones de JavaScript.

Las promesas en JavaScript sirven para manejar operaciones asíncronas de manera más estructurada y legible. Cuando realizas tareas que no se completan de inmediato, como llamadas a API, lecturas de archivos o consultas a bases de datos,  **JavaScript necesita una forma de gestionar estas operaciones sin bloquear la ejecución del código**.

Las promesas cumplen varias funciones clave:

##### Manejo del flujo asíncrono óptimo

Te permiten escribir un código más limpio y comprensible al evitar el anidamiento excesivo de callbacks. En lugar de anidar múltiples callbacks, puedes encadenar métodos **.then()** de manera más legible.

##### Gestión de errores

Brindan un mecanismo más efectivo para manejar errores en operaciones asíncronas. Puedes usar el método **.catch()** para capturar errores que ocurren en cualquier parte de la cadena de promesas.

##### Encadenamiento de operaciones

Permiten encadenar múltiples operaciones asíncronas de una manera más intuitiva. El resultado de una promesa puede ser pasado como entrada a la siguiente promesa en la cadena utilizando el método .**then()**.

##### Manejo de paralelismo

Puedes utilizar constructores como  **Promise.all()**  y  **Promise.race()** para manejar múltiples promesas al mismo tiempo. El primero espera a que todas las promesas se cumplan antes de continuar, mientras que el segundo se resuelve tan pronto como una de las promesas se cumple.

##### Legibilidad y mantenibilidad

Las promesas hacen que el código asíncrono sea más fácil de leer y mantener, ya que proporcionan una estructura clara para manejar resultados exitosos y errores, en lugar de tener que rastrear flujos de control complejos en callbacks anidados.

##### Compatibilidad con async/await

Asimismo, forman la base de las funciones  **async**  y  **await,**  una característica introducida en versiones más recientes de JavaScript.  **async/await** simplifica aún más el manejo de código asíncrono al hacer que parezca código síncrono, mejorando la legibilidad (en el próximo apartado te ampliare mas la información de  **async/await**).

#### Estados posibles de una promesa en JavaScript

Una promesa tiene tres estados posibles:

##### Pendiente (pending)

El estado «Pendiente» (pending) es uno de los tres posibles estados en los que una promesa puede encontrarse en JavaScript.  **Una promesa está en estado pendiente cuando se crea, pero la operación asíncrona asociada aún no ha sido completada ni ha fallado.**  En otras palabras, la promesa está en espera de que la operación asíncrona se resuelva o se rechace.

Durante el estado «Pendiente», la promesa está en una especie de limbo. Aunque la operación asincrónica está en curso, la promesa misma no tiene acceso directo al resultado final ni al error que pueda ocurrir. Sin embargo, la promesa se mantiene receptiva a su futuro estado cumplido (**fulfilled**) o rechazado (**rejected**).

Cuando la operación asíncrona se completa satisfactoriamente, la promesa pasa del estado «Pendiente» al estado «Cumplido» (fulfilled). En este punto, el valor resultante de la operación se convierte en el resultado de la promesa y puede ser accedido mediante el método  **.then()**.

Por otro lado, si la operación asíncrona encuentra un error, la promesa cambia de estado «Pendiente» al estado «Rechazado» (rejected). En este caso, se llama al método  **reject()** en la definición de la promesa o en cualquier lugar donde se rechace explícitamente, y el error proporcionado se convierte en el motivo del rechazo. El manejo de errores se realiza comúnmente usando el método .**catch()**  o utilizando bloques  **try/catch**  en combinación con  **async/await**.

##### Cumplida (fulfilled)

Una promesa entra en el estado «Cumplida» cuando la operación asíncrona asociada se ha completado con éxito y ha producido un valor resultante.

En este estado, la promesa contiene el valor resultante de la operación asíncrona. Esto significa que la promesa ha cumplido su propósito y tiene un resultado con el que trabajar. Este valor puede ser cualquier tipo de dato, como un número, una cadena de texto, un objeto o incluso otra promesa. El valor cumplido se pasa como argumento a la función **resolve()** cuando se crea la promesa.

Para acceder al valor cumplido de una promesa, se utiliza el método  **.then()** y se proporciona una función que se ejecutará una vez que la promesa esté en el estado «Cumplida».

**Es importante destacar que una vez que una promesa está en el estado «Cumplida» no puede cambiar a otro.**  Esto significa que si una promesa se cumple con un valor, permanecerá en ese estado y no se puede volver a «Pendiente» ni cambiar a «Rechazada».

##### Rechazada (rejected)

Una promesa entra en el estado «Rechazada» cuando la operación asíncrona asociada ha fallado y se ha producido un error.

En este estado, la promesa contiene información sobre el motivo del fallo, es decir, el error que ocurrió durante la operación asíncrona. El motivo del rechazo se pasa como argumento a la función **reject()** cuando se crea la promesa.

Para manejar el estado «Rechazada» y el motivo del rechazo, se utiliza el método  **.catch()**  o se pueden manejar errores con bloques  **try/catch** en combinación con **async/await**.

#### Estructura básica de una promesa en JavaScript

La estructura es la siguiente:

```javascript

const myPromise = new Promise((resolve, reject) => {
  // Aquí se realiza la operación asíncrona
  // Si la operación es exitosa, se llama a resolve(valor)
  // Si ocurre un error, se llama a reject(error)
});

myPromise
  .then(resultado => {
    // Manejar el resultado si la promesa se cumple
  })
  .catch(error => {
    // Manejar el error si la promesa es rechazada
  });

```

La función  **resolve** se utiliza para cumplir la promesa con un valor, mientras que la función  **reject** se utiliza para rechazar la promesa con un error.

Las promesas también permiten encadenar múltiples operaciones asíncronas usando el método  **.then()**, lo que hace que el código sea más legible y evita el anidamiento excesivo.

**Nota:**  como hemos dicho, en versiones más recientes de JavaScript (a partir de ES6), se introdujeron  **async/await**, que proporcionan una forma aún más cómoda de trabajar con código asíncrono basado en promesas, haciendo que parezca que se está trabajando con código síncrono, pero detrás de escena sigue siendo asincrónico.

#### Cómo implementar las promesas en JavaScript: ejemplos

##### Ejemplo de transacción de pago en línea

Supongamos que deseamos simular una transacción de pago en línea y queremos asegurarnos de que se manejen correctamente tanto los pagos exitosos como los fallidos, utilizando promesas.

```javascript

// Simulación de una función que procesa un pago
function procesarPago(total) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const exito = Math.random() < 0.8; // Simulamos que el 80 % de las veces el pago es exitoso

      if (exito) {
        resolve("Pago exitoso");
      } else {
        reject(new Error("Error en el pago"));
      }
    }, 1500); // Simulamos un retraso de 1.5 segundos para el proceso de pago
  });
}

// Ejemplo de uso de la función de procesamiento de pagos
const totalAPagar = 100; // Monto total del pago

procesarPago(totalAPagar)
  .then(resultado => {
    console.log(resultado); // Se ejecutará en caso de pago exitoso
    // Aquí podríamos realizar acciones adicionales, como actualizar la base de datos, enviar un recibo por correo, etc.
  })
  .catch(error => {
    console.error(error.message); // Se ejecutará en caso de pago fallido
    // Aquí podemos ofrecer al usuario la opción de intentar nuevamente o mostrar un mensaje de error
  });

```

En este ejemplo, la función  **procesarPago()** simula una transacción de pago en línea. Dependiendo de un valor aleatorio, la función decide si el pago es exitoso o fallido. La promesa que se devuelve se cumple si el pago es exitoso (el 80 % de las veces) y se rechaza si el pago falla.

Luego, utilizamos  **.then()**  para manejar el caso de pago exitoso, donde podemos realizar acciones adicionales, como actualizar la base de datos o enviar un recibo por correo electrónico. Empleamos  **.catch()** para manejar el caso de pago fallido, donde es posible ofrecer al usuario opciones para resolver el problema o mostrar un mensaje de error.

##### Ejemplo de base de datos

En este caso, supondremos que estamos trabajando con datos de usuarios y queremos simular la adición de múltiples usuarios a una base de datos, teniendo en cuenta casos exitosos y fallidos.

```javascript

// Simulación de una función que agrega usuarios a una base de datos
function agregarUsuarios(usuarios) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const exito = Math.random() < 0.7; // Simulamos que el 70 % de las veces la operación es exitosa

      if (exito) {
        resolve("Usuarios agregados exitosamente");
      } else {
        reject(new Error("Error al agregar usuarios"));
      }
    }, 2000); // Simulamos un retraso de 2 segundos para la operación de almacenamiento
  });
}

// Datos de ejemplo de usuarios a agregar a la base de datos
const nuevosUsuarios = [
  { id: 1, nombre: "Usuario 1" },
  { id: 2, nombre: "Usuario 2" },
  { id: 3, nombre: "Usuario 3" }
];

// Uso de la función de agregación de usuarios
agregarUsuarios(nuevosUsuarios)
  .then(resultado => {
    console.log(resultado); // Se ejecutará en caso de operación exitosa
    // Aquí podríamos realizar acciones adicionales, como actualizar la interfaz de usuario o notificar al usuario
  })
  .catch(error => {
    console.error(error.message); // Se ejecutará en caso de operación fallida
    // Aquí podríamos ofrecer al usuario la opción de intentar nuevamente o mostrar un mensaje de error
  });

```

-   **Definición de la función agregarUsuarios():**  esta función simula el proceso de agregar usuarios a una base de datos. Devuelve una promesa que se cumple si la operación es exitosa (el 70 % de las veces) y se rechaza si la operación falla. La función toma un arreglo de usuarios como argumento.
-   **Simulación de retardo:** para simular el tiempo que puede llevar almacenar datos en una base de datos, utilizamos setTimeout() para introducir un retraso de 2 segundos.
-   **Uso de la función de agregación de usuarios:**  pasamos el arreglo nuevosUsuarios a la función agregarUsuarios(). Luego utilizamos .then() para manejar el caso de éxito, donde podríamos realizar acciones adicionales, y .catch() para manejar el caso de falla, donde podríamos mostrar un mensaje de error.
-   **Datos de ejemplo de usuarios:**  creamos un arreglo de objetos que representan a los usuarios que deseamos agregar a la base de datos.

Como ves, las promesas en JavaScript son una herramienta esencial para manejar operaciones asíncronas de manera más legible, estructurada y eficiente. Proporcionan una forma de lidiar con el flujo de control en código asíncrono, permitiendo  **gestionar resultados exitosos y errores de una manera más ordenada**. En resumen, han allanado el camino para un manejo más elegante y eficiente de operaciones asíncronas, lo que mejora la calidad del código y la experiencia del desarrollador en la creación de aplicaciones modernas y robustas.

["Subir"](#top)

---

<a name="item8"></a>
### Conceptos básicos de Async / Await en JavaScript

Como te he adelantado en el párrafo anterior, tenemos dos partes cuando usamos  `async/await`  en nuestro código.

En primer lugar, tenemos la palabra clave  `async`  , que se pone delante de una declaración de función para convertirla en una función async.

Una función asíncrona es una función que sabe que es posible que se use la palabra clave `await`  dentro de ella para invocar código asíncrono.

_La palabra clave_ `_async_` _se añade a las funciones para que devuelvan una promesa en lugar de un valor directamente._

```jsx
const cargarDatos = async () => {
  const url = "https://jsonplaceholder.typicode.com/todos/1";
  const res = await fetch(url);
  const datos = await res.json();
  console.log(datos);
};
cargarDatos();
```

```jsx
// output en la consola
{
  completed: false,
  id: 1,
  title: "delectus aut autem",
  userId: 1
}
```

#### Cómo **usar Async/Await** con manejo de errores

Podemos manejar errores usando un bloque try catch como este:

```jsx
const cargarDatos = async () => {
  try{
	  const url = "https://jsonplaceholder.typicode.com/todos/1";
	  const res = await fetch(url);
	  const datos = await res.json();
	  console.log(datos);
  } catch(err) {
    console.log(err)
  }
};

cargarDatos();
```

El try-catch anterior solamente manejará errores al obtener los datos, como una sintaxis incorrecta, nombres de dominio incorrectos, errores de red, etc.

Cuando quieras manejar un mensaje de error del código de respuesta de la API, puedes usar  `res.ok`  (  `res`  es la variable en la que se almacena la respuesta). Te dará un Boolean con el valor verdadero si el código de respuesta está entre 200 y 209.

```jsx
const cargarDatos = async () => {
  try{
	  const url = "https://jsonplaceholder.typicode.com/todos/qwe1";
	  const res = await fetch(url);
	  if(res.ok){ 
	    const datos = await res.json();
	    console.log(datos);
	  } else {
	    console.log(res.status); // 404
	  }
  } catch(err) {
    console.log(err)
  }
};

cargarDatos();

// OUTPUT
// 404
```

#### Cómo una función Async devuelve una promesa

Este es uno de los rasgos de las funciones asíncronas — se garantiza que sus valores de retorno se convertirán en promesas. Para manejar los datos devueltos por una función  `async`  podemos usar una palabra clave  `then`  para obtener los datos.

```jsx
const cargarDatos = async () => {
  try{
    const url = "https://jsonplaceholder.typicode.com/todos/1";
    const res = await fetch(url);
    const datos = await res.json();
    return datos
  } catch(err) {
    console.log(err)
  }
};

const datos = cargarDatos().then(datos => console.log(datos));
```

```jsx
// usa una IIFE asincrona 
(async () => {
  const datos = await cargarDatos();
  console.log(datos);
})();
```

`await`  solo funciona dentro de funciones asíncronas en JavaScript normal. Pero puede usarlo por sí misma con  módulos JavaScript.

#### Cómo usar Promise.all () en JavaScript

`Promise.all()`  es muy útil cuando queremos llamar a varias APIs.

Utilizando una función con  `await`  de manera tradicional, tenemos que esperar a que se complete cada solicitud antes de pasar a la siguiente. Esto puede ser un problema cuando cada solicitud tarda en completarse. Esto puede hacer que la respuesta sea muy lenta.

Usando  `Promise.all()`, podemos llamar a cada una de estas API en paralelo .

_Ten cuidado cuando uses_ `_Promise.all()_`_, – si una de las solicitudes con await falla, todo el .all() falla._

```js
const cargarDatos = async () => {
  try{
    const url1 = "https://jsonplaceholder.typicode.com/todos/1";
    const url2 = "https://jsonplaceholder.typicode.com/todos/2";
    const url3 = "https://jsonplaceholder.typicode.com/todos/3";
    const resultados = await Promise.all([
      fetch(url1),
      fetch(url2),
      fetch(url3)
    ]);
    const promesasDeDatos = await resultados.map(result => result.json());
    const datosFinales = Promise.all(promesasDeDatos);
    return datosFinales
  } catch(err) {
    console.log(err)
  }
};

const datos = cargarDatos().then(datos => console.log(datos));
```

```jsx
// output en la consola
[{
  completed: false,
  id: 1,
  title: "delectus aut autem",
  userId: 1
}, {
  completed: false,
  id: 2,
  title: "quis ut nam facilis et officia qui",
  userId: 1
}, {
  completed: false,
  id: 3,
  title: "fugiat veniam minus",
  userId: 1
}]
```

#### Conclusión

En la mayoría de las situaciones, podemos usar  `async/await`  con un bloque  `try catch`  para manejar tanto los resultados como los errores.

Por el momento,  `await`  no funcionará en el código al nivel superior. Esto quiere decir que si estamos fuera de una función asíncrona (`async`  ), no podemos usar `await`  sintácticamente. En este caso, lo habitual es agregar  `.then/catch`  para manejar el resultado final o el error.

_A nivel superior en el_ código _,  `await`_ está  _disponible en Node.js  `v14.8`  o superior y solamente en módulos ES._

["Subir"](#top)
