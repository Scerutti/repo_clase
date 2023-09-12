# Clases en JavaScript

## ¿Qué es una clase?

Una clase en JavaScript es como un plano o una plantilla que define cómo deben crearse los objetos. Las clases nos permiten crear objetos que tienen propiedades (variables) y métodos (funciones) comunes.

## Ejemplo de Clase

Supongamos que queremos crear una clase para representar un "Perro". La clase puede tener propiedades como "nombre" y "raza", y métodos como "ladrar" y "correr".

```javascript
class Perro {
  constructor(nombre, raza) {
    this.nombre = nombre;
    this.raza = raza;
  }

  ladrar() {
    console.log(`${this.nombre} está ladrando.`);
  }

  correr() {
    console.log(`${this.nombre} está corriendo a toda velocidad.`);
  }
}

// Crear instancias de la clase Perro
const perro1 = new Perro("Max", "Labrador");
const perro2 = new Perro("Luna", "Golden Retriever");

// Llamar a métodos de las instancias
perro1.ladrar(); // Imprimirá "Max está ladrando."
perro2.correr(); // Imprimirá "Luna está corriendo a toda velocidad."
```


## Explicacion
- class Perro { ... }: Aquí definimos la clase Perro. El constructor es un método especial que se llama cuando creamos un nuevo objeto de esta clase.

- constructor(nombre, raza): El constructor es donde establecemos las propiedades del objeto cuando lo creamos. En este caso, establecemos las propiedades nombre y raza del perro.

- ladrar() y correr(): Estos son métodos de la clase Perro. Los objetos creados a partir de esta clase pueden llamar a estos métodos para realizar acciones específicas.

- Creación de instancias: Usamos la clase Perro para crear dos instancias de perros, perro1 y perro2. Cada instancia tiene sus propias propiedades y métodos.

- Llamada a métodos: Usamos perro1.ladrar() y perro2.correr() para llamar a los métodos de las instancias y realizar acciones específicas para cada perro.

Las clases en JavaScript son una forma organizada y eficiente de crear objetos con propiedades y comportamientos comunes. Puedes usar clases para modelar y trabajar con diferentes tipos de objetos en tu programa.