# Árboles (Trees) - TEORIA

Los árboles son una forma especial de organizar datos que se asemeja a un árbol boca abajo. Aquí hay algunas palabras clave para entenderlos:

- **Raíz**: El punto de inicio del árbol.
- **Nodo**: Un punto en el árbol que contiene información.
- **Padre**: Un nodo con hijos.
- **Hijo**: Un nodo descendiente de otro nodo.
- **Hermanos**: Nodos que tienen el mismo padre.
- **Hojas**: Nodos que no tienen hijos.
- **Nivel**: La distancia desde la raíz hasta un nodo.
- **Camino**: La secuencia de nodos para llegar de uno a otro.

### Árbol Binario

Un tipo especial de árbol donde cada nodo puede tener hasta dos hijos. Pueden estar equilibrados (mismo número de nodos en ambos lados) o no. Si están equilibrados, son excelentes para buscar datos rápidamente.

### Árbol AVL

Un árbol binario de búsqueda que siempre se mantiene equilibrado. Esto lo hace genial para buscar datos, pero las operaciones de inserción y eliminación pueden ser más lentas.

### Heap

Otro tipo de árbol binario con reglas especiales. Cada nodo tiene un valor mayor o igual que sus hijos. Esto se utiliza para encontrar rápidamente el elemento más grande o más pequeño en un conjunto de datos.

## Otras Estructuras de Datos

Hay muchas más estructuras de datos, pero estas son las más importantes. La elección de cuál usar depende del problema que quieras resolver.

## Resumen

¡Hemos completado la aventura de las estructuras de datos! Aca tenemos una tabla para recordar cuándo usar cada estructura:

| Estructura         | Ventajas                        | Desventajas                    |
| ------------------ | ------------------------------- | ------------------------------- |
| Arreglo            | Rápida inserción, acceso rápido | Búsqueda y borrado lentos      |
| Pila               | Fácil de usar (LIFO)            | Acceso lento a otros elementos |
| Cola               | Fácil de usar (FIFO)            | Acceso lento a otros elementos |
| Lista Enlazada     | Inserción y borrado rápidos     | Búsqueda lenta                 |
| Árbol Binario      | Rápido si está equilibrado      | Borrado complicado             |
| Árbol AVL          | Búsqueda rápida                 | Inserción y borrado lentos     |
| Heap               | Inserción y borrado rápidos     | Acceso lento a otros elementos |
| Hash               | Búsqueda y inserción rápidas    | Borrado lento, uso de memoria  |
