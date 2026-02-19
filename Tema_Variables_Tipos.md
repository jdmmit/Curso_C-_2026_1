# Declaración de Variables y Tipos de Datos Fundamentales en C++

## Introducción
¡Hola! Como tu profesor experto en C++, te guiaré a través de los conceptos fundamentales sobre cómo C++ maneja la información. C++ es un lenguaje de **tipado estático**, lo que significa que debemos decirle al compilador exactamente qué tipo de dato vamos a almacenar en cada variable antes de usarla. Esto permite que el programa sea muy eficiente y seguro en cuanto al uso de memoria.

## Tipos de Datos Fundamentales
En C++, cada tipo de dato tiene un formato específico y ocupa un tamaño determinado en la memoria. Aquí están los principales:

### 1. Booleanos (`bool`)
Representan valores de verdad lógica.
*   **Valores**: `true` (1) o `false` (0).
*   **Tamaño**: 1 byte (8 bits).
*   **Uso**: Condiciones y operaciones lógicas.

### 2. Caracteres (`char`)
Almacenan caracteres individuales (letras, números, símbolos) basados en el código ASCII.
*   **Valores**: Caracteres ASCII o números enteros pequeños (0-255).
*   **Tamaño**: 1 byte (8 bits).
*   **Ejemplo**: `'A'`, `'z'`, `'@'`.

### 3. Enteros (`int`)
Se usan para contar y almacenar números sin decimales.
*   **Tamaño estándar**: 4 bytes (32 bits).
*   **Modificadores**:
    *   `short`: 2 bytes (números pequeños).
    *   `long`: 4 u 8 bytes.
    *   `long long`: 8 bytes (números muy grandes).
    *   `unsigned`: Solo positivos (duplica el rango positivo).
    *   `signed`: Positivos y negativos (por defecto).

### 4. Punto Flotante (Decimales)
Para números reales con decimales, bajo el estándar IEEE 754.
*   `float`: Precisión simple (4 bytes, ~7 dígitos de precisión).
*   `double`: Doble precisión (8 bytes, ~15 dígitos de precisión). Es el más usado.
*   `long double`: Precisión extendida (12-16 bytes).

## Declaración e Inicialización
Una variable debe cumplir con características específicas:
1.  **Tipo de dato**: Qué va a guardar.
2.  **Nombre**: Identificador único (letras, números, `_`, no puede empezar por número).
3.  **Valor de inicialización (Opcional)**: Valor inicial.
4.  **Ubicación (Automática)**: Dirección en memoria asignada por el compilador.

```cpp
// Sintaxis: Tipo Nombre = Valor;
int edad = 25;
float altura = 1.75;
char inicial = 'J';
bool estudiante = true;

// Declaración sin inicialización (cuidado con la basura en memoria)
int contador; 
```

## Arreglos (Arrays)
Colecciones de datos del **mismo tipo**.
*   Se accede a ellos mediante un índice (empezando en 0).
*   Tamaño fijo definido al declarar.

```cpp
int numeros[5] = {10, 20, 30, 40, 50};
char palabra[] = "Hola"; // C-style string
```

### Contenedores Modernos (`std::array` y `std::string`)
En C++ moderno, preferimos usar las herramientas de la librería estándar (STL) por seguridad y facilidad de uso:
*   `std::string`: Para cadenas de texto dinámicas.
*   `std::array`: Para arreglos de tamaño fijo con funciones extra.

```cpp
#include <array>
#include <string>

std::string nombre = "Juan";
std::array<int, 3> coordenadas = {10, 20, 30};
```

## Constantes (`const`)
El calificador `const` asegura que una variable no pueda cambiar su valor después de ser inicializada. Es vital para la seguridad del código.

```cpp
const float PI = 3.14159;
// PI = 3.14; // ¡Error de compilación!
```

---
*Recuerda: Elegir el tipo de dato correcto es el primer paso para escribir software eficiente y libre de errores.*
