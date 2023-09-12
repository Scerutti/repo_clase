# Estructuras de Datos: Listas Enlazadas

## Teoría

Las listas enlazadas son una estructura de datos en la que cada elemento, llamado "nodo", contiene dos partes: un valor o dato y una referencia al siguiente nodo en la lista. Esta estructura permite organizar datos de manera secuencial y eficiente, ya que los nodos se enlazan entre sí, formando una cadena.

### Ejemplo de lista enlazada

```javascript
class Nodo {
  constructor(valor) {
    this.valor = valor;       // Valor o dato del nodo
    this.siguiente = null;   // Referencia al siguiente nodo
  }
}

// Creación de nodos
const nodo1 = new Nodo(10);
const nodo2 = new Nodo(20);
const nodo3 = new Nodo(30);

// Enlace de nodos
nodo1.siguiente = nodo2;
nodo2.siguiente = nodo3;

// La lista enlazada ahora contiene: 10 -> 20 -> 30
```

## Ventajas de las Listas Enlazadas
Las listas enlazadas ofrecen varias ventajas:

1. Inserción Eficiente: Puedes insertar o eliminar elementos en cualquier posición de la lista sin necesidad de desplazar otros elementos, lo que lo hace eficiente en términos de tiempo.

2. Tamaño Dinámico: Las listas enlazadas pueden crecer o reducirse dinámicamente según sea necesario, a diferencia de los arrays que tienen un tamaño fijo.

3. Uso Eficiente de Memoria: Solo se utiliza la memoria necesaria para almacenar los nodos y sus enlaces, evitando la asignación estática de memoria.

4. Búsqueda Eficiente: La búsqueda se realiza de manera secuencial, lo que puede ser rápido si la lista está ordenada y se utiliza una búsqueda binaria.

## Desventajas de las Listas Enlazadas
Sin embargo, también tienen algunas desventajas:

1. Acceso Ineficiente: El acceso a elementos en una lista enlazada es más lento que en un array, ya que debes recorrer la lista desde el principio hasta el elemento deseado.

3. Uso de Memoria Adicional: Cada nodo en una lista enlazada requiere espacio adicional para almacenar la referencia al siguiente nodo, lo que puede aumentar el uso de memoria.

4. No es Ideal para Todos los Escenarios: Las listas enlazadas son ideales para ciertas situaciones, como la implementación de pilas y colas, pero pueden no ser la mejor opción en otros casos.

En resumen, las listas enlazadas son una estructura de datos versátil que se utiliza en programación para organizar y gestionar datos de manera flexible y eficiente, aunque su elección depende de los requisitos específicos de cada problema.