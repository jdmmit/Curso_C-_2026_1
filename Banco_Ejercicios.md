# Banco de Ejercicios y Ejemplos Prácticos en C++

## Introducción
Este documento contiene ejercicios extra y ejemplos de código completos para que practiques y afiances tus conocimientos en C++.

---

## 1. Variables y Tipos de Datos
### Ejemplo: Tipos de Datos
```cpp
#include <iostream>

int main() {
    int entero = 10;
    float decimal = 3.1416;
    char letra = 'A';
    bool esVerdad = true;

    std::cout << "Entero: " << entero << std::endl;
    std::cout << "Decimal: " << decimal << std::endl;
    std::cout << "Caracter: " << letra << std::endl;
    std::cout << "Booleano: " << esVerdad << std::endl;

    return 0;
}
```

### Ejercicios Propuestos
1.  **Conversión Celsius a Fahrenheit**: Crea un programa que pida una temperatura en Celsius y la convierta a Fahrenheit usando `F = (C * 9/5) + 32`.
2.  **Área de un Triángulo**: Pide base y altura (pueden ser decimales) y calcula el área.
3.  **Intercambio de Valores**: Pide dos números `a` y `b`, e intercambia sus valores sin usar una tercera variable auxiliar (Pista: usa sumas y restas).

---

## 2. Operadores
### Ejemplo: Operadores Lógicos
```cpp
#include <iostream>

int main() {
    int a = 5, b = 10;
    bool resultado = (a < b) && (b > 0); // true AND true = true

    if (resultado) {
        std::cout << "Ambas condiciones son verdaderas" << std::endl;
    }
    return 0;
}
```

### Ejercicios Propuestos
1.  **Par o Impar (Bitwise)**: Determina si un número es par o impar usando el operador `&` (AND a nivel de bits).
2.  **Calculadora de Descuentos**: Si el monto es mayor a 1000 Y el usuario es miembro, aplica 20% de descuento. Si no es miembro pero monto > 1000, 10%.
3.  **Año Bisiesto**: Un año es bisiesto si es divisible por 4, EXCEPTO si es divisible por 100, A MENOS que sea divisible por 400. Escribe la expresión lógica.

---

## 3. Estructuras de Control
### Ejemplo: Bucle For Anidado
```cpp
#include <iostream>

int main() {
    // Tabla de multiplicar del 1 al 5
    for(int i = 1; i <= 5; i++) {
        std::cout << "Tabla del " << i << ":" << std::endl;
        for(int j = 1; j <= 10; j++) {
            std::cout << i << " x " << j << " = " << (i*j) << std::endl;
        }
        std::cout << "----------------" << std::endl;
    }
    return 0;
}
```

### Ejercicios Propuestos
1.  **Pirámide de Asteriscos**: Pide al usuario la altura y dibuja una pirámide centrada.
2.  **Números Primos**: Pide un número y determina si es primo usando un bucle `for` y `break`.
3.  **Adivina el Número (While)**: El programa genera un número aleatorio (1-100) y el usuario debe adivinarlo. El programa dice "Más alto" o "Más bajo".

---

## 4. Arreglos y Arrays
### Ejemplo: Buscar en un Arreglo
```cpp
#include <iostream>

int main() {
    int numeros[] = {4, 8, 15, 16, 23, 42};
    int buscar = 16;
    bool encontrado = false;

    for(int num : numeros) {
        if(num == buscar) {
            encontrado = true;
            break;
        }
    }

    if(encontrado) std::cout << "Numero encontrado!" << std::endl;
    else std::cout << "Numero no encontrado." << std::endl;

    return 0;
}
```

### Ejercicios Propuestos
1.  **Promedio y Desviación**: Calcula el promedio de 10 notas. Luego imprime cuántas están por encima del promedio.
2.  **Buscar Duplicados**: Escribe un programa que detecte s hay algún número repetido en un arreglo de 10 enteros.
3.  **Rotación de Arreglo**: Mueve todos los elementos una posición a la derecha (el último pasa al principio).

---

## 5. Funciones
### Ejemplo: Función Recursiva
```cpp
#include <iostream>

// Factorial: 5! = 5 * 4 * 3 * 2 * 1
unsigned long long factorial(int n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

int main() {
    std::cout << "Factorial de 5 es: " << factorial(5) << std::endl;
    return 0;
}
```

### Ejercicios Propuestos
1.  **Potencia Manual**: Crea una función `potencia(base, exponente)` que use un bucle para calcular el resultado.
2.  **Validar Contraseña**: Crea una función `bool esSegura(string pass)` que retorne `true` si tiene más de 8 caracteres, una mayúscula y un número.
3.  **Sobrecarga**: Crea funciones `imprimir(int)` que imprima un número e `imprimir(string)` que imprima texto entre corchetes `[Texto]`.

---

## 6. Punteros y Memoria
### Ejemplo: Punteros y Funciones
```cpp
#include <iostream>

void duplicar(int *p) {
    *p = (*p) * 2;
}

int main() {
    int numero = 5;
    duplicar(&numero);
    std::cout << "El doble es: " << numero << std::endl; // 10
    return 0;
}
```

### Ejercicios Propuestos
1.  **Intercambio con Punteros**: Implementa `void swap(float *a, float *b)`.
2.  **Arreglo Dinámico Inverso**: Pide `N` al usuario, crea un arreglo dinámico de tamaño `N`, llénalo, imprímelo al revés y libera la memoria.
3.  **Puntero a Puntero**: Declara un `int x`. Declara un `int *p` que apunte a `x`. Declara un `int **pp` que apunte a `p`. Cambia el valor de `x` usando `pp`.
