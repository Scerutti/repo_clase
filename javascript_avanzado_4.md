# Tablas Hash (Hash Tables)

## ¿Qué son las Tablas Hash?

Las tablas hash son una estructura de datos que permite almacenar datos en formato clave-valor (key-value) de manera eficiente. Imagina una tabla gigante donde cada elemento tiene un nombre (clave) y un contenido (valor). La magia de las tablas hash radica en cómo organizan y buscan estos datos, haciéndolas muy rápidas para buscar información.

## Función Hash

La función que transforma una clave en una cadena de longitud finita se llama "función hash". Esto es como una especie de receta mágica que convierte palabras en números. Por ejemplo, la palabra "perro" podría convertirse en el número 42 usando una función hash. La analogía con la palabra "hash" es como "picar y mezclar" en el mundo real.

## Estructura de una Tabla Hash

Para crear una tabla hash, necesitamos tres cosas:

1. **Estructura de Datos**: Esto es donde almacenamos nuestros datos. Puede ser un arreglo, un árbol u otra estructura.

2. **Función Hasheadora**: Esta función convierte las claves en números (hashes) que determinan dónde almacenar los datos en la estructura de datos.

3. **Política de Resolución de Colisiones**: ¿Qué sucede cuando dos claves diferentes generan el mismo hash? Aquí definimos cómo manejar esas situaciones.

## Ejemplo de una Clase HashTable

```javascript
class HashTable {
  constructor() {
    this.numBuckets = 35; // Número de buckets
    this.buckets = new Array(this.numBuckets);
  }

  // Función Hash
  hash(key) {
    let total = 0;
    for (let i = 0; i < key.length; i++) {
      total += key.charCodeAt(i);
    }
    return total % this.numBuckets;
  }

  // Almacenar datos en la tabla
  set(key, value) {
    const index = this.hash(key);
    if (!this.buckets[index]) {
      this.buckets[index] = [];
    }
    this.buckets[index].push({ key, value });
  }

  // Obtener datos de la tabla
  get(key) {
    const index = this.hash(key);
    if (!this.buckets[index]) {
      return null;
    }
    for (const item of this.buckets[index]) {
      if (item.key === key) {
        return item.value;
      }
    }
    return null;
  }

  // Verificar si una clave existe en la tabla
  hasKey(key) {
    const index = this.hash(key);
    if (!this.buckets[index]) {
      return false;
    }
    for (const item of this.buckets[index]) {
      if (item.key === key) {
        return true;
      }
    }
    return false;
  }
}

// Uso de la clase HashTable
const miTabla = new HashTable();
miTabla.set("instructora", "Ani");
const instructora = miTabla.get("instructora");
const existeKey = miTabla.hasKey("instructora");
```

### Explicacion:
Hemos creado una clase HashTable que representa una tabla hash. Tiene métodos para hashear claves, almacenar datos, obtener datos y verificar la existencia de claves. Usamos una función hash para calcular en qué "bucket" se almacenarán los datos.

Los buckets son como compartimentos donde almacenamos datos relacionados. Por ejemplo, "instructora" y "Ani" se almacenan en el mismo compartimento.

Las tablas hash son como una súper herramienta para buscar datos rápidamente. Puedes consultar si una clave existe y obtener su valor de manera muy eficiente.