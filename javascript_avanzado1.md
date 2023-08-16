# Iteracion de Arrays y Objetos

### Teoria

La iteración es un proceso en el que recorremos elementos en una colección, como un array o un objeto, para realizar operaciones en cada elemento.

#### Ejemplo de iterar un array
```javascript
  let canciones = ['Canción 1', 'Canción 2', 'Canción 3'];

  for (let i = 0; i < canciones.length; i++) {
    console.log(canciones[i]);
  }

```

#### Ejemplo de iterar un objeto
```javascript
  let persona = {
    nombre: 'Juan',
    edad: 25,
    ciudad: 'Ciudad X'
  };

  for (let propiedad in persona) {
    console.log(propiedad + ': ' + persona[propiedad]);
  }

```

# Funciones, Hoisting y Closures

### Teoria

* Las funciones son bloques de código reutilizables que pueden aceptar argumentos y devolver valores.
* El hoisting es un comportamiento en el que las declaraciones de variables y funciones se mueven al principio del ámbito en el que se encuentran.
* Los closures son funciones que conservan el acceso a variables de su ámbito externo incluso después de que ese ámbito haya finalizado.

#### Ejemplo de Funciones y Hoisting
```javascript
  saludo(); // ¡Funciona incluso antes de declararla!

  function saludo() {
    console.log('¡Hola a todos!');
  }

```

#### Ejemplo de Closures
```javascript
  function contador() {
    let contador = 0;

    return function() {
      contador++;
      console.log('Contador: ' + contador);
    };
  }

  let incrementar = contador();
  incrementar(); // Mostrará 'Contador: 1'
  incrementar(); // Mostrará 'Contador: 2'
```

# Call, Bind y Apply

* 'call()', 'bind()', y 'apply()' son métodos que permiten cambiar la forma en que se llama a una función y controlar el valor de this.

#### Ejemplo de Call
```javascript
  let perro = {
    nombre: 'Fido',
    hacerTruco: function(truco) {
      console.log(this.nombre + ' hace el truco: ' + truco);
    }
  };

  let gato = {
    nombre: 'Pelusa'
  };

  perro.hacerTruco.call(gato, 'Saltar por un aro'); // El gato hace el truco

```

#### Ejemplo de Bind
```javascript
  let perro = {
    nombre: 'Fido',
    hacerTruco: function(truco) {
      console.log(this.nombre + ' hace el truco: ' + truco);
    }
  };

  let perroTruco = perro.hacerTruco.bind(perro);

  perroTruco('Rodar en el suelo'); // Fido hace el truco


```
#### Ejemplo de Apply
```javascript
function saludar(nombre, edad) {
  console.log('Hola, soy ' + nombre + ' y tengo ' + edad + ' años.');
}

let persona = {
  nombre: 'María',
  edad: 20
};

saludar.apply(null, [persona.nombre, persona.edad]); // Hola, soy María y tengo 20 años.


```
### ¿Porque null en el primer parametro?

En el ejemplo que proporcioné anteriormente, el primer argumento null que se pasa a apply() es un valor especial que representa el valor de this dentro de la función a la que se llama apply(). Sin embargo, en el contexto de ese ejemplo, null podría haberse reemplazado con cualquier otro objeto.

El primer argumento de apply() se utiliza para establecer el valor de this dentro de la función que se está llamando. Si no estás interesado en cambiar el valor de this, puedes pasar null o cualquier otro objeto sin afectar el resultado.

Vamos con otro ejemplo:

```javascript
function saludar(nombre, edad) {
  console.log('Hola, soy ' + nombre + ' y tengo ' + edad + ' años.');
}

var persona = {
  nombre: 'María',
  edad: 20
};

// Usar apply con null como primer argumento y un array de argumentos
saludar.apply(null, [persona.nombre, persona.edad]); // Hola, soy María y tengo 20 años.

// También podría usar cualquier otro objeto como primer argumento
var otroObjeto = { mensaje: '¡Hola!' };
saludar.apply(otroObjeto, ['Juan', 25]); // Hola, soy Juan y tengo 25 años.
```

