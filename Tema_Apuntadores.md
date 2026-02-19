# Apuntadores (Pointers) en C++

## Introducción
Los apuntadores son una de las características más poderosas y a la vez temidas de C++. Un apuntador es simplemente una variable que almacena la **dirección de memoria** de otra variable.

## ¿Por qué usarlos?
*   Permiten modificar variables fuera del alcance local (Paso por referencia).
*   Son esenciales para la **Memoria Dinámica**.
*   Permiten trabajar con estructuras de datos complejas (Listas, Árboles).
*   Son muy eficientes al pasar grandes cantidades de datos a funciones (evitan copias).

## Sintaxis Básica
*   **Declaración**: `tipo *nombre;` (El asterisco indica que es un puntero a ese tipo).
*   **Operador de Dirección (`&`)**: Obtiene la dirección de memoria de una variable.
*   **Operador de Indirección/Desreferencia (`*`)**: Accede al valor almacenado en la dirección a la que apunta.

```cpp
int numero = 42;
int *puntero = &numero; // puntero guarda la dirección de numero

std::cout << numero;   // Imprime 42
std::cout << &numero;  // Imprime una dirección (ej. 0x7ffd...)
std::cout << puntero;  // Imprime la misma dirección (0x7ffd...)
std::cout << *puntero; // Imprime 42 (Va a la dirección y lee el valor)

*puntero = 100; // Cambia el valor de numero a 100 indirectamente
```

## Punteros y Arreglos
En C++, el nombre de un arreglo es en realidad un puntero al primer elemento del arreglo.

```cpp
int numeros[3] = {10, 20, 30};
int *p = numeros; // Apunta a numeros[0]

std::cout << *p;     // 10
std::cout << *(p+1); // 20 (Arithmética de Punteros)
```

## Puntero `void*` (Genérico)
Es un puntero que puede apuntar a cualquier tipo de dato, pero no se puede desreferenciar directamente sin un *cast* (conversión explícita).

## Puntero `nullptr` (C++11)
Siempre inicializa tus punteros. Si no apuntan a nada válido, usa `nullptr`.
`int *p = nullptr;` es mucho más seguro que `int *p = 0;` o `NULL`.

---
## Ejercicios Propuestos
1.  **Intercambio (Swap)**: Escribe una función `void swap(int *a, int *b)` que intercambie los valores de dos enteros usando punteros.
2.  **Longitud de Cadena**: Escribe tu propia versión de `strlen` usando punteros para recorrer una cadena de caracteres hasta encontrar el carácter nulo `\0`.
3.  **Invertir Arreglo con Punteros**: Usa dos punteros (uno al inicio y otro al final) para invertir un arreglo.
