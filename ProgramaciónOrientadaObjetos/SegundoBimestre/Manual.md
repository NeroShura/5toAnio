# Resumen del Manual de Programación Orientada a Objetos en Processing

# Introducción

Hasta este momento, los programas realizados en Processing se desarrollaban utilizando **programación estructurada**, es decir, organizando el código mediante variables, funciones, estructuras de control y algoritmos.

Este enfoque es muy útil para aprender a programar y para resolver problemas pequeños. Sin embargo, cuando los programas aumentan de tamaño comienzan a aparecer inconvenientes:

- Muchas variables relacionadas entre sí.
- Código repetido.
- Dificultad para encontrar errores.
- Poco aprovechamiento del código ya escrito.
- Programas difíciles de mantener y ampliar.

Para solucionar estos problemas surge la **Programación Orientada a Objetos (POO)**.

La POO propone organizar un programa como un conjunto de **objetos**, donde cada uno es responsable de administrar su propia información y comportamiento.

Cada objeto reúne:

- **Atributos:** almacenan información.
- **Métodos:** realizan acciones utilizando esa información.

La programación estructurada no desaparece; simplemente pasa a formar parte de una organización más grande basada en clases y objetos.

Gracias a esto los programas se vuelven:

- Más organizados.
- Más fáciles de entender.
- Más reutilizables.
- Más escalables.
- Más fáciles de mantener.

---

# Parte I — Primeras ideas sobre Objetos

## Pensar el mundo como objetos

La POO intenta representar los elementos del mundo real mediante objetos.

Por ejemplo:

- Botella
- Bicicleta
- Automóvil
- Celular
- Lámpara

Todos los objetos poseen dos componentes fundamentales.

## Características

Son los datos que describen al objeto.

Ejemplos:

- Color
- Altura
- Tamaño
- Capacidad
- Peso

En programación reciben el nombre de **atributos**.

---

## Comportamientos

Son las acciones que un objeto puede realizar.

Ejemplos:

- Abrirse
- Cerrarse
- Avanzar
- Frenar
- Vaciarse
- Llenarse

En programación reciben el nombre de **métodos**.

---

# La fábrica de botellas

El manual utiliza el ejemplo de una fábrica para explicar las clases.

Existe un diseño que indica cómo deben construirse todas las botellas.

Ese diseño especifica:

- Material
- Forma
- Capacidad
- Tipo de tapa

A partir de ese diseño pueden construirse miles de botellas.

En programación sucede exactamente lo mismo.

## Clase

Es el diseño o molde.

Define cómo serán todos los objetos.

## Objeto

Es una instancia concreta creada utilizando ese molde.

Cada objeto es independiente de los demás.

---

# Clase y Objeto

La diferencia principal es:

## Clase

- Es un modelo.
- No representa un objeto real.
- Define atributos y métodos.

## Objeto

- Es una instancia creada desde una clase.
- Existe en memoria.
- Posee valores propios.

---

# Atributos

Los atributos representan el estado del objeto.

Ejemplo de una botella:

- Color
- Capacidad
- Cantidad de líquido

Aunque dos objetos pertenezcan a la misma clase, cada uno puede tener valores diferentes.

---

# Métodos

Los métodos representan las acciones del objeto.

Ejemplo:

- llenar()
- vaciar()
- mostrar()

Los métodos utilizan los atributos para modificar el estado del objeto.

---

# Instancias

Crear un objeto recibe el nombre de **instanciar**.

Primero solamente se declara una variable:

```processing
Botella botella1;
```

Aquí todavía no existe una botella.

Solo existe una variable capaz de guardar un objeto.

Para crearla se utiliza:

```processing
botella1 = new Botella();
```

La palabra **new**:

- Reserva memoria.
- Ejecuta el constructor.
- Crea un nuevo objeto.

Cada vez que se utiliza **new** se genera una instancia completamente independiente.

---

# Constructor

El constructor es un método especial.

Características:

- Tiene el mismo nombre que la clase.
- No devuelve ningún valor.
- Se ejecuta automáticamente al utilizar **new**.

Su función principal consiste en inicializar correctamente todos los atributos.

Ejemplo:

```processing
Botella() {
    capacidad = 500;
    cantidadLiquido = 0;
}
```

También existen constructores con parámetros.

Ejemplo:

```processing
Botella(color c, float capacidad)
```

Esto permite que cada objeto nazca con características diferentes.

---

# Parte II — Objetos en Processing

## La clase PVector

Processing ya incluye muchas clases listas para utilizar.

La más importante es **PVector**.

Un PVector representa un vector matemático.

Puede utilizarse para almacenar:

- Posiciones.
- Velocidades.
- Direcciones.
- Fuerzas.
- Aceleraciones.

En lugar de escribir:

```processing
float x;
float y;
```

podemos escribir:

```processing
PVector posicion;
```

Toda la información queda agrupada dentro de un solo objeto.

---

## Componentes de PVector

Todo objeto PVector posee tres atributos:

- x
- y
- z

Ejemplo:

```processing
PVector posicion = new PVector(100,200);
```

El constructor inicializa automáticamente los valores del vector.

---

## Métodos importantes de PVector

PVector incorpora muchas operaciones matemáticas.

Los métodos más utilizados son:

- add()
- sub()
- mult()
- div()
- mag()
- normalize()
- limit()

Esto evita escribir funciones matemáticas cada vez que se necesitan.

---

# Movimiento utilizando PVector

Antes:

```processing
float x;
float y;
float velX;
float velY;
```

Ahora:

```processing
PVector posicion;
PVector velocidad;
```

Actualizar la posición se reduce a una sola línea:

```processing
posicion.add(velocidad);
```

Este patrón es utilizado constantemente en:

- Videojuegos.
- Animaciones.
- Simulaciones.
- Sistemas interactivos.

---

# Referencias

Los objetos funcionan mediante referencias.

Ejemplo:

```processing
PVector a = new PVector(100,200);
PVector b = a;
```

Aquí **a** y **b** apuntan exactamente al mismo objeto.

Modificar uno modifica al otro.

Si se necesita una copia independiente se utiliza:

```processing
PVector copia = posicion.copy();
```

Ahora ambos objetos son completamente distintos.

---

# Parte III — Crear nuestras propias clases

## Clase Movil

El manual propone construir una clase llamada **Movil**.

Esta clase posee:

- Una posición.
- Una velocidad.

Ambas utilizando PVector.

```processing
class Movil{
    PVector pos;
    PVector vel;
}
```

---

## Constructor de Movil

El constructor crea automáticamente los objetos internos.

```processing
Movil(float x,float y){
    pos = new PVector(x,y);
    vel = new PVector(random(-3,3),random(-3,3));
}
```

Cada objeto obtiene sus propios vectores.

---

## Métodos de Movil

### actualizar()

Actualiza la posición.

```processing
pos.add(vel);
```

---

### dibujar()

Representa el objeto.

```processing
circle(pos.x,pos.y,20);
```

Cada objeto sabe moverse y dibujarse por sí mismo.

---

# Responsabilidades

Cada clase debe encargarse únicamente de su propia tarea.

La clase **Movil** administra:

- Posición.
- Velocidad.
- Movimiento.
- Dibujo.

Mientras tanto, **draw()** solamente coordina el funcionamiento general del programa.

Esta separación mejora enormemente la organización.

---

# Sobrecarga de Constructores

Una clase puede tener varios constructores.

Ejemplo:

- Sin parámetros.
- Con posición inicial.
- Con distintos atributos.

Esto ofrece mayor flexibilidad al crear objetos.

---

# Encapsulamiento

El encapsulamiento consiste en reunir:

- Datos.
- Métodos.
- Reglas internas.

Todo dentro del mismo objeto.

Los demás objetos no necesitan conocer cómo funciona internamente.

Simplemente utilizan sus métodos.

Por ejemplo:

```processing
pos.add(vel);
```

No importa cómo está implementada la suma.

Solo utilizamos el método.

---

# Variables privadas

Processing permite utilizar:

- public
- private

**private** impide que otras clases modifiquen directamente los atributos.

En lugar de hacer:

```processing
m.pos.x = 500;
```

es mejor crear métodos específicos como:

```processing
mover();
```

De esta forma el objeto controla su propio estado.

---

# Organización y Modularidad

La POO divide programas grandes en clases pequeñas.

Ejemplo:

- Jugador
- Enemigo
- Partícula
- Bala
- Movil

Cada clase tiene una responsabilidad específica.

Esto facilita:

- El mantenimiento.
- La lectura.
- La reutilización.
- La ampliación del proyecto.

---

# Organización de archivos

Processing permite separar cada clase en una pestaña distinta.

Ejemplo:

- Main
- Jugador
- Enemigo
- Movil

Esto mantiene el proyecto mucho más ordenado.

---

# Parte IV — Relaciones entre Objetos

## Arrays de Objetos

En lugar de crear:

```processing
Movil m1;
Movil m2;
Movil m3;
```

Se utiliza:

```processing
Movil[] moviles = new Movil[100];
```

Primero se crea el array.

Luego se crean todos los objetos.

```processing
for(int i=0;i<moviles.length;i++){
    moviles[i]=new Movil(random(width),random(height));
}
```

---

# Trabajar con muchos objetos

Después de inicializarlos:

```processing
for(int i=0;i<moviles.length;i++){
    moviles[i].actualizar();
    moviles[i].dibujar();
}
```

Cada objeto:

- Mantiene su propio estado.
- Posee su propia velocidad.
- Ejecuta sus propios métodos.

---

# Sistemas de partículas

Muchas instancias de una misma clase permiten crear sistemas complejos.

Ejemplos:

- Partículas.
- Enjambres.
- Tráfico.
- Videojuegos.
- Simulaciones.

La complejidad aparece gracias a la interacción entre muchos objetos simples.

---

# Interacción entre objetos

Los objetos también pueden comunicarse.

Ejemplo:

```processing
void colisionar(Movil otro)
```

Aquí un objeto recibe otro objeto como parámetro.

Puede comparar posiciones y reaccionar.

---

# Sistemas emergentes

Cuando muchos objetos interactúan aparecen comportamientos complejos.

Ejemplos:

- Bandadas.
- Tráfico.
- Ecosistemas.
- Simulaciones físicas.

Cada objeto sigue reglas simples, pero el comportamiento colectivo resulta mucho más complejo.

---

# Parte V — Herencia y Polimorfismo

# Herencia

Cuando varias clases poseen código repetido se utiliza la herencia.

Se crea una clase general.

Ejemplo:

```processing
Movil
```

Luego otras clases heredan de ella.

```processing
class Pelota extends Movil
```

```processing
class Enemigo extends Movil
```

Las subclases heredan automáticamente:

- Atributos.
- Métodos.
- Comportamientos.

---

# Superclases y Subclases

## Superclase

Clase general.

Ejemplo:

```processing
Movil
```

## Subclases

Clases específicas.

Ejemplos:

- Jugador
- Pelota
- Enemigo
- Partícula

Todas son tipos de Movil.

---

# super()

Cuando una subclase posee constructor utiliza:

```processing
super(x,y);
```

Esto ejecuta el constructor de la superclase.

---

# Jerarquías

```text
Movil
├── Jugador
├── Pelota
├── Enemigo
└── Particula
```

Todas comparten el comportamiento general del movimiento.

---

# Polimorfismo

El polimorfismo permite utilizar distintos objetos mediante un mismo tipo.

Ejemplo:

```processing
Movil a = new Pelota();
Movil b = new Enemigo();
```

Ambos ejecutan:

```processing
dibujar();
```

Pero cada uno produce un resultado distinto.

Esto recibe el nombre de **sobrescritura de métodos**.

---

# Arrays Polimórficos

```processing
Movil[] objetos;
```

Dentro del mismo array pueden almacenarse:

- Jugadores.
- Enemigos.
- Pelotas.
- Partículas.

Todos pueden actualizarse mediante el mismo código.

---

# Abstracción

Abstraer significa representar únicamente aquello que resulta importante para el programa.

Por ejemplo, para una pelota interesa:

- Posición.
- Velocidad.
- Color.
- Tamaño.

No interesa:

- Temperatura.
- Marca.
- Composición química.

La abstracción permite construir modelos simples y útiles.

---

# Métodos de Instancia

Pertenecen a un objeto específico.

Ejemplo:

```processing
pos.add(vel);
```

Modifican el estado del propio objeto.

---

# Métodos Estáticos

Pertenecen a la clase.

Ejemplos:

```processing
PVector.random2D();
PVector.add();
PVector.sub();
PVector.dist();
```

No requieren un objeto previamente creado.

Generalmente crean nuevos objetos o realizan cálculos generales.

---

# Atributos Estáticos

Los atributos estáticos pertenecen a toda la clase.

Ejemplo:

```processing
static int cantidad;
```

Todos los objetos comparten el mismo valor.

Se utilizan para:

- Contadores.
- Constantes.
- Configuraciones globales.

No es recomendable abusar de ellos porque generan dependencias globales.

---

# Glosario

## Clase

Molde que define atributos y métodos.

---

## Objeto

Instancia concreta creada a partir de una clase.

---

## Instancia

Objeto creado mediante la palabra **new**.

---

## Atributo

Variable que almacena información del objeto.

---

## Método

Acción o comportamiento del objeto.

---

## Constructor

Método especial que inicializa un objeto al crearlo.

---

## Encapsulamiento

Principio que reúne datos y comportamientos dentro de un mismo objeto, protegiendo su estado interno.

---

## Herencia

Mecanismo que permite reutilizar atributos y métodos de otra clase.

Representa una relación del tipo **"es un"**.

---

## Polimorfismo

Capacidad de que diferentes objetos respondan de manera distinta al mismo método.

---

## Abstracción

Proceso de simplificar un problema modelando únicamente los aspectos necesarios para el funcionamiento del programa.
