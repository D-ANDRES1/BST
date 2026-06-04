
---

## Implementación del árbol

La clase `ArbolBinarioBusqueda` incluye operaciones completas de manipulación de un BST:

### Operaciones básicas

- Inserción de nodos  
  Se insertan de forma recursiva respetando la regla: menores a la izquierda, mayores a la derecha.

- Búsqueda de valores  
  Recorre el árbol comparando el valor objetivo con cada nodo hasta encontrarlo o llegar a null.

- Eliminación de nodos  
  Se manejan tres casos:
  1. Nodo hoja: se elimina directamente.
  2. Nodo con un hijo: se reemplaza por su hijo.
  3. Nodo con dos hijos: se reemplaza por el sucesor inorden (mínimo del subárbol derecho).

- Mínimo y máximo  
  El mínimo se obtiene recorriendo siempre hacia la izquierda.  
  El máximo se obtiene recorriendo siempre hacia la derecha.

- Altura del árbol  
  Se calcula de forma recursiva determinando la longitud del camino más largo desde la raíz hasta una hoja.

---

### Recorridos del árbol

- InOrden  
  Recorre izquierda → raíz → derecha.  
  En un BST produce los valores ordenados de menor a mayor.

- PreOrden  
  Recorre raíz → izquierda → derecha.  
  Útil para reconstrucción del árbol.

- PostOrden  
  Recorre izquierda → derecha → raíz.  
  Útil para eliminación o procesamiento final de nodos.

- Recorrido por niveles (BFS)  
  Recorre el árbol por niveles utilizando una cola implementada manualmente, sin estructuras de `java.util`.

---

## Ejercicios adicionales implementados

Los siguientes ejercicios refuerzan el uso de recursividad, propiedades de árboles binarios y algoritmos clásicos sobre estructuras no lineales.

---

### 1. Conteo de nodos

Este algoritmo recorre todo el árbol de forma recursiva, visitando cada nodo exactamente una vez.

El principio base es el siguiente:

- Si el nodo es nulo, se retorna 0.
- Si el nodo existe, se cuenta como 1 y se suman recursivamente los nodos del subárbol izquierdo y derecho.

Este enfoque permite obtener el tamaño total del árbol sin utilizar variables auxiliares ni estructuras adicionales.

---

### 2. Verificación de balanceo del árbol

Este algoritmo evalúa si el árbol mantiene una estructura equilibrada.

Un árbol se considera balanceado cuando, para cada nodo, la diferencia entre la altura de su subárbol izquierdo y derecho no es mayor que 1.

El proceso se realiza de manera recursiva evaluando cada subárbol, lo que permite verificar no solo la raíz, sino toda la estructura del árbol.

---

### 3. Validación de propiedad BST

Este procedimiento verifica que el árbol cumpla con las reglas fundamentales de un Árbol Binario de Búsqueda:

- Todos los valores del subárbol izquierdo deben ser menores al nodo actual.
- Todos los valores del subárbol derecho deben ser mayores al nodo actual.

Para garantizar la validez global del árbol, se utiliza un rango dinámico de valores (mínimo y máximo permitido) que se ajusta en cada nivel de la recursión.

Esto asegura que no solo se valide la relación directa padre-hijo, sino toda la estructura del árbol.

---

### 4. LCA (Lowest Common Ancestor)

Este algoritmo determina el ancestro común más bajo entre dos valores dentro del BST.

Se basa directamente en la propiedad de orden del árbol:

- Si ambos valores son menores que el nodo actual, la búsqueda continúa en el subárbol izquierdo.
- Si ambos valores son mayores, la búsqueda continúa en el subárbol derecho.
- En caso contrario, el nodo actual es el punto donde los caminos de ambos valores se separan, por lo que corresponde al LCA.

Este enfoque evita recorrer todo el árbol, aprovechando su estructura ordenada para encontrar la solución de forma eficiente.

---

### 5. Inversión del árbol (espejo)

Este algoritmo transforma el árbol en su versión reflejada intercambiando recursivamente los hijos izquierdo y derecho de cada nodo.

El proceso se realiza de la siguiente manera:

- Se intercambian los punteros izquierdo y derecho del nodo actual.
- Luego se aplica recursivamente el mismo procedimiento en ambos subárboles.

El resultado es un árbol simétrico respecto a su estructura original, también conocido como “espejo” del árbol.

---

## Reglas del BST

- El subárbol izquierdo contiene valores menores al nodo.
- El subárbol derecho contiene valores mayores al nodo.
- No se permiten valores duplicados.

---

## Clase principal

La clase `Principal` contiene pruebas funcionales del árbol:

- Inserción de un conjunto de valores de prueba
- Eliminación de nodos en diferentes casos
- Ejecución de recorridos
- Validación del BST
- Verificación de balanceo
- Pruebas del LCA
- Inversión del árbol

---

## Detalles técnicos

- Altura del árbol:
  - Árbol vacío: -1
  - Nodo hoja: 0
- Todas las operaciones principales están implementadas de forma recursiva.
- No se utiliza `java.util`.
- La cola para BFS es una implementación manual basada en listas enlazadas.