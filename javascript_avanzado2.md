# Recursividad

### Teoria

La recursividad es un concepto en el que una función se llama a sí misma para resolver un problema. Funciona como un juego de muñecas rusas, donde cada muñeca contiene una versión más pequeña de sí misma.

#### Ejemplo de recursividad
```javascript
  function contarHasta(numero) {
  if (numero <= 0) {
    console.log('¡Hecho!');
  } else {
    console.log(numero);
    contarHasta(numero - 1); // Llamada recursiva
  }
}

contarHasta(5);
```

# Estructuras de Datos: Arrays, Set, Pilas y Colas

### Teoria

* **Arrays**: Son listas ordenadas de elementos. Puedes agregar, quitar y acceder a elementos por su posición.

* **Set**: Es una colección de elementos únicos. No permite duplicados y es útil para almacenar valores únicos.

* **Pilas**: Funcionan como una pila de platos. Puedes agregar platos arriba o quitar el último plato agregado.

* **Colas**: Funcionan como una fila en una tienda. Puedes agregar clientes al final o atender al cliente que está primero en la fila.

#### Ejemplo de arrays
```javascript
  let frutas = ['manzana', 'banana', 'naranja'];
  console.log(frutas[1]); // Mostrará 'banana'
  frutas.push('uva'); // Agregar 'uva' al final
  frutas.pop(); // Eliminar 'uva'

```
#### Ejemplo de set
```javascript
  let colores = new Set();
  colores.add('rojo');
  colores.add('verde');
  colores.add('rojo'); // No se duplica

  console.log(colores.has('verde')); // Mostrará true
  colores.delete('rojo'); // Elimina 'rojo'
```

#### Ejemplo de pilas
```javascript
  let pila = [];
  pila.push('plato1');
  pila.push('plato2');
  pila.pop(); // Saca 'plato2'
  console.log(pila); // Mostrará ['plato1']
```

#### Ejemplo de colas
```javascript
  let cola = [];
  cola.push('cliente1');
  cola.push('cliente2');
  cola.shift(); // Atiende 'cliente1'
  console.log(cola); // Mostrará ['cliente2']
```
