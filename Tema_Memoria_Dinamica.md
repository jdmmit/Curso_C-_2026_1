# Memoria Dinámica en C++

## Introducción
Hasta ahora hemos usado **Memoria Estática** (ej. `int x;`) y **Memoria Automática** (ej. variables locales en funciones). Estas tienen un tamaño fijo y vida útil limitada al bloque donde se declaran.
La **Memoria Dinámica** nos permite solicitar memoria manualmente al sistema operativo durante la ejecución del programa, ideal cuando no sabemos cuántos datos vamos a necesitar (ej. leer un archivo de tamaño desconocido).

## Regiones de Memoria
*   **Stack (Pila)**: Memoria rápida, gestionada automáticamente (variables locales, llamadas a funciones). Tamaño limitado.
*   **Heap (Montón)**: Memoria grande, gestionada manualmente (tu responsabilidad). Aquí vive la memoria dinámica.
*   **Data Segment**: Variables globales y estáticas.
*   **Code Segment**: Instrucciones del programa (tu código compilado).

## Operadores `new` y `delete`
Para usar el Heap, usamos punteros.

### 1. Reservar Memoria (`new`)
Devuelve un puntero al espacio reservado. Si falla (memoria llena), lanza una excepción `std::bad_alloc`.

```cpp
int *p = new int; // Reserva un entero en el Heap
*p = 10;

// Arreglos dinámicos
int tamano;
std::cout << "¿Cuantos elementos quieres? ";
std::cin >> tamano;
int *arr = new int[tamano]; // El tamaño se decide en tiempo de ejecución
```

### 2. Liberar Memoria (`delete`)
¡CRÍTICO! Cuando termines de usar la memoria, **debes liberarla** o tendrás "fugas de memoria" (Memory Leaks), que ralentizan y eventualmente bloquean el sistema.

```cpp
delete p; // Libera el entero apuntado por p
p = nullptr; // Buena práctica: evitar punteros colgantes (Dangling Pointers)

delete[] arr; // Libera el arreglo COMPLETO (nota los corchetes [])
arr = nullptr;
```

## Errores Comunes
1.  **Memory Leak**: Olvidar el `delete`.
2.  **Dangling Pointer**: Usar un puntero después de hacer `delete`.
3.  **Double Free**: Hacer `delete` dos veces al mismo puntero (Error grave, crash).

---
## Ejercicios Propuestos
1.  **Arreglo Dinámico**: Pide al usuario el tamaño de un arreglo, llénalo con números aleatorios y calcula su promedio. Al final, libera la memoria.
2.  **Redimensionar**: Simula un `vector`. Crea un arreglo dinámico de tamaño 5. Cuando se llene, crea uno nuevo de tamaño 10, copia los datos antiguos, borra el viejo y apunta al nuevo.
3.  **Matriz Dinámica**: Crea una matriz de N x M usando punteros a punteros (`int **matriz`). Recuerda liberar cada fila y luego el arreglo de filas.
