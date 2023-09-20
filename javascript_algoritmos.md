# Algoritmos en JavaScript

## ¿Qué es un algoritmo?

Un algoritmo es una serie de pasos o instrucciones que se siguen para realizar una tarea específica. Piensa en ello como una receta para cocinar tu plato favorito. Los algoritmos son esenciales en la programación, ya que ayudan a las computadoras a realizar tareas de manera eficiente.

## ¿Qué hace bueno a un algoritmo?

Un buen algoritmo es aquel que resuelve un problema de manera eficiente y rápida. Esto significa que debería poder manejar grandes cantidades de datos sin volverse lento o consumir demasiada memoria. También debe ser fácil de entender y mantener.

## ¿Cómo medimos la eficiencia de un algoritmo?

Para medir la eficiencia de un algoritmo, utilizamos algo llamado "Análisis Asintótico". Esto implica estudiar cómo crece el tiempo de ejecución o el uso de memoria a medida que aumenta el tamaño de los datos de entrada. Queremos que nuestro algoritmo sea rápido incluso cuando trabajamos con muchos datos.

### Ejemplo de algoritmo 1: Adivinando un número

```javascript
function adivinarNumero(numeroObjetivo) {
  let intentos = 0;
  let numeroAdivinado = 0;

  while (numeroAdivinado !== numeroObjetivo) {
    numeroAdivinado = Math.floor(Math.random() * 100) + 1;
    intentos++;
  }

  return intentos;
}

const numeroObjetivo = 42;
const intentos = adivinarNumero(numeroObjetivo);
console.log(`Adiviné el número en ${intentos} intentos.`);
```
### Ejemplo de algoritmo 2: Búsqueda Lineal
```javascript
function busquedaLineal(lista, elemento) {
  for (let i = 0; i < lista.length; i++) {
    if (lista[i] === elemento) {
      return i;
    }
  }
  return -1;
}

const miLista = [3, 7, 1, 9, 5, 2];
const elementoABuscar = 9;
const indiceEncontrado = busquedaLineal(miLista, elementoABuscar);

if (indiceEncontrado !== -1) {
  console.log(`Encontré el elemento en el índice ${indiceEncontrado}.`);
} else {
  console.log(`El elemento no se encontró en la lista.`);
}
```

### Complejidad de un algoritmo
La complejidad de un algoritmo se refiere a cuánto tiempo o recursos (como memoria) necesita para ejecutarse. Queremos algoritmos con una complejidad baja, para que sean rápidos y eficientes.

### Algoritmos de búsqueda
Los algoritmos de búsqueda son herramientas útiles para encontrar elementos en una lista o conjunto de datos.

### Busqueda lienal
```javascript
function busquedaLineal(lista, elemento) {
  for (let i = 0; i < lista.length; i++) {
    if (lista[i] === elemento) {
      return i;
    }
  }
  return -1;
}

const miLista = [3, 7, 1, 9, 5, 2];
const elementoABuscar = 9;
const indiceEncontrado = busquedaLineal(miLista, elementoABuscar);

if (indiceEncontrado !== -1) {
  console.log(`Encontré el elemento en el índice ${indiceEncontrado}.`);
} else {
  console.log(`El elemento no se encontró en la lista.`);
}
```

------------------------------------------------------------------------------------------------------------------------

### Algoritmo de Insercion (Insertion Sort)

#### **Explicacion:**
El algoritmo de inserción funciona dividiendo la lista de elementos en dos partes: una parte ordenada y una parte desordenada. Inicialmente, la parte ordenada contiene un solo elemento (el primer elemento de la lista). Luego, en cada iteración, se toma un elemento de la parte desordenada y se coloca en la posición correcta dentro de la parte ordenada. Esto se hace comparando el elemento con los elementos en la parte ordenada y moviendo los elementos mayores hacia la derecha.

#### **Uso:**
El algoritmo de inserción es eficiente para listas pequeñas o casi ordenadas. También es útil cuando se está construyendo una lista ordenada incrementalmente.

### **EJEMPLO**

```javascript
function insertionSort(arr) {
  for (let i = 1; i < arr.length; i++) {
    let current = arr[i];
    let j = i - 1;
    while (j >= 0 && arr[j] > current) {
      arr[j + 1] = arr[j];
      j--;
    }
    arr[j + 1] = current;
  }
  return arr;
}

const miArray = [5, 2, 9, 3, 1];
const arrayOrdenado = insertionSort(miArray);
console.log(arrayOrdenado); // [1, 2, 3, 5, 9]

```

------------------------------------------------------------------------------------------------------------------------


### Algoritmo de Selección (Selection Sort)

#### **Explicacion:**
El algoritmo de selección funciona dividiendo la lista en dos partes: una parte ordenada y una parte desordenada. En cada iteración, encuentra el elemento mínimo en la parte desordenada y lo mueve a la parte ordenada al intercambiarlo con el primer elemento de la parte desordenada. Esto se repite hasta que toda la lista esté ordenada.

#### **Uso:**
El algoritmo de selección es simple pero ineficiente para listas grandes, ya que requiere un número fijo de comparaciones y movimientos, independientemente de si la lista está ordenada o no.

### **EJEMPLO**

```javascript
function selectionSort(arr) {
  for (let i = 0; i < arr.length - 1; i++) {
    let minIndex = i;
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }
    if (minIndex !== i) {
      [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
    }
  }
  return arr;
}

const miArray = [5, 2, 9, 3, 1];
const arrayOrdenado = selectionSort(miArray);
console.log(arrayOrdenado); // [1, 2, 3, 5, 9]
```

------------------------------------------------------------------------------------------------------------------------

### Algoritmo de Burbuja (Bubble Sort)

#### **Explicacion:**
El algoritmo de burbuja compara pares de elementos adyacentes en la lista y los intercambia si están en el orden incorrecto. Esto hace que los elementos más grandes "burbujeen" hacia el final de la lista en cada iteración. El proceso se repite hasta que no se realicen más intercambios en una iteración completa.

#### **Uso:**
El algoritmo de burbuja es simple pero ineficiente y se utiliza principalmente con fines educativos. No es adecuado para listas grandes.

### **EJEMPLO**

```javascript
function bubbleSort(arr) {
  let swapped;
  do {
    swapped = false;
    for (let i = 0; i < arr.length - 1; i++) {
      if (arr[i] > arr[i + 1]) {
        [arr[i], arr[i + 1]] = [arr[i + 1], arr[i]];
        swapped = true;
      }
    }
  } while (swapped);
  return arr;
}

const miArray = [5, 2, 9, 3, 1];
const arrayOrdenado = bubbleSort(miArray);
console.log(arrayOrdenado); // [1, 2, 3, 5, 9]

```

------------------------------------------------------------------------------------------------------------------------

### Quick Sort

#### **Explicacion:**
El algoritmo Quick Sort utiliza una estrategia de "dividir y conquistar" para ordenar la lista. Se elige un elemento pivote de la lista y se divide la lista en dos subconjuntos: elementos menores que el pivote y elementos mayores que el pivote. Luego, se aplica el algoritmo de manera recursiva a ambos subconjuntos. Finalmente, se combinan los subconjuntos ordenados.

#### **Uso:**
Quick Sort es uno de los algoritmos de ordenamiento más eficientes y se utiliza ampliamente en la práctica. Tiene un rendimiento óptimo en listas grandes y es una elección común para la ordenación en la mayoría de las bibliotecas de programación.

### **EJEMPLO**

```javascript
function quickSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }

  const pivot = arr[0];
  const left = [];
  const right = [];

  for (let i = 1; i < arr.length; i++) {
    if (arr[i] < pivot) {
      left.push(arr[i]);
    } else {
      right.push(arr[i]);
    }
  }

  return [...quickSort(left), pivot, ...quickSort(right)];
}

const miArray = [5, 2, 9, 3, 1];
const arrayOrdenado = quickSort(miArray);
console.log(arrayOrdenado); // [1, 2, 3, 5, 9]
```
------------------------------------------------------------------------------------------------------------------------

### Merge Sort

#### **Explicacion:**
El algoritmo Merge Sort también utiliza una estrategia de "dividir y conquistar". Divide la lista en dos mitades iguales y ordena cada mitad de manera recursiva. Luego, combina las dos mitades ordenadas en una sola lista ordenada utilizando una operación de "mezcla".

#### **Uso:**
Merge Sort es un algoritmo de ordenamiento eficiente y estable que es adecuado para listas grandes y se utiliza en muchas implementaciones de bibliotecas. Su rendimiento es constante y predecible.

### **EJEMPLO**

```javascript
function mergeSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }

  const middle = Math.floor(arr.length / 2);
  const left = arr.slice(0, middle);
  const right = arr.slice(middle);

  return merge(mergeSort(left), mergeSort(right));
}

function merge(left, right) {
  let result = [];
  let leftIndex = 0;
  let rightIndex = 0;

  while (leftIndex < left.length && rightIndex < right.length) {
    if (left[leftIndex] < right[rightIndex]) {
      result.push(left[leftIndex]);
      leftIndex++;
    } else {
      result.push(right[rightIndex]);
      rightIndex++;
    }
  }

  return result.concat(left.slice(leftIndex), right.slice(rightIndex));
}

const miArray = [5, 2, 9, 3, 1];
const arrayOrdenado = mergeSort(miArray);
console.log(arrayOrdenado); // [1, 2, 3, 5, 9]
```