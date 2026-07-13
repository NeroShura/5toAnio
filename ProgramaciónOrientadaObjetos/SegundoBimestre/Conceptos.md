# Conceptos Clave — Programación Orientada a Objetos (POO) en Processing

## Programación Orientada a Objetos (POO)
Paradigma de programación que organiza un programa en **objetos**, donde cada objeto contiene sus propios datos (atributos) y acciones (métodos).

## Programación Estructurada
Forma de programar utilizando variables, funciones, estructuras de control y algoritmos. Es adecuada para programas pequeños, pero puede volverse difícil de mantener en proyectos grandes.

## Clase
Es el **molde o diseño** que define cómo serán los objetos, especificando sus atributos y métodos.

## Objeto
Es una **instancia** creada a partir de una clase. Cada objeto tiene sus propios valores y existe de forma independiente.

## Instancia
Objeto creado mediante la palabra reservada `new`.

## Instanciar
Proceso de crear un objeto a partir de una clase.

## Atributo
Variable que almacena información o el estado de un objeto.

## Método
Función perteneciente a una clase que define el comportamiento o las acciones que puede realizar un objeto.

## Estado
Conjunto de valores que poseen los atributos de un objeto en un momento determinado.

## Comportamiento
Acciones que un objeto puede ejecutar mediante sus métodos.

## Constructor
Método especial que se ejecuta automáticamente al crear un objeto con `new`. Se utiliza para inicializar sus atributos.

## Constructor con parámetros
Constructor que recibe datos al momento de crear un objeto para asignarle valores iniciales diferentes.

## `new`
Palabra reservada que crea un objeto, reserva memoria y ejecuta el constructor.

## PVector
Clase incorporada en Processing para representar vectores matemáticos, utilizada para posiciones, velocidades, direcciones, aceleraciones y fuerzas.

## Componentes de PVector
Son los atributos del vector:
- `x`
- `y`
- `z`

## Métodos de PVector
Funciones incorporadas para operar con vectores, como:
- `add()`
- `sub()`
- `mult()`
- `div()`
- `mag()`
- `normalize()`
- `limit()`

## Referencia
Variable que apunta a la ubicación de un objeto en memoria. Dos referencias pueden señalar al mismo objeto.

## Copia de un objeto
Creación de un objeto independiente utilizando métodos como `copy()`.

## Clase Movil
Ejemplo de clase que almacena una posición y una velocidad mediante objetos `PVector`.

## actualizar()
Método que modifica la posición del objeto según su velocidad.

## dibujar()
Método encargado de representar gráficamente un objeto en la pantalla.

## Responsabilidad
Principio que indica que cada clase debe encargarse únicamente de su propia función.

## Sobrecarga de Constructores
Posibilidad de definir varios constructores en una misma clase con diferentes parámetros.

## Encapsulamiento
Principio que agrupa datos y métodos dentro de una misma clase, protegiendo el estado interno del objeto.

## Variables privadas (`private`)
Atributos que solo pueden ser modificados desde la propia clase.

## Variables públicas (`public`)
Atributos o métodos accesibles desde cualquier otra clase.

## Modularidad
Organización del programa en clases independientes para facilitar el mantenimiento y la reutilización.

## Organización de archivos
Separación de cada clase en pestañas o archivos distintos para mantener el proyecto ordenado.

## Array de Objetos
Arreglo que almacena múltiples objetos de una misma clase.

## Sistemas de partículas
Conjunto de muchos objetos simples que interactúan para producir efectos complejos.

## Interacción entre objetos
Comunicación entre objetos mediante el envío de otros objetos como parámetros a los métodos.

## Sistemas emergentes
Comportamientos complejos que aparecen a partir de la interacción de muchos objetos simples.

## Herencia
Mecanismo que permite que una clase herede atributos y métodos de otra clase, evitando repetir código.

## Superclase
Clase general de la que heredan otras clases.

## Subclase
Clase que hereda las características de una superclase y puede agregar o modificar comportamientos.

## `extends`
Palabra reservada utilizada para indicar que una clase hereda de otra.

## `super()`
Llamada al constructor de la superclase desde una subclase.

## Jerarquía de clases
Organización de clases mediante relaciones de herencia.

## Polimorfismo
Capacidad de diferentes objetos de responder de manera distinta al mismo método.

## Sobrescritura de métodos
Proceso mediante el cual una subclase redefine un método heredado para darle un comportamiento propio.

## Arrays polimórficos
Arreglos que almacenan objetos de distintas subclases utilizando el tipo de la superclase.

## Abstracción
Proceso de representar únicamente las características importantes de un objeto para resolver un problema.

## Método de instancia
Método que pertenece a un objeto específico y modifica su propio estado.

## Método estático (`static`)
Método que pertenece a la clase y puede utilizarse sin crear un objeto.

## Atributo estático (`static`)
Variable compartida por todos los objetos de una misma clase.

## Reutilización de código
Ventaja de la POO que permite aprovechar clases y métodos existentes en nuevos programas.

## Escalabilidad
Capacidad de ampliar un programa agregando nuevas clases o funcionalidades sin modificar su estructura principal.

## Mantenimiento
Facilidad para corregir errores, mejorar y actualizar un programa gracias a una buena organización del código.