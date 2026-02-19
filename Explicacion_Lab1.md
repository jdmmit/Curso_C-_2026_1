# Explicación del Laboratorio 1: Introducción a C++ y Algoritmos

## Objetivo del Laboratorio
El propósito principal de este laboratorio es que te familiarices con el entorno de desarrollo (IDE) QtCreator y practiques la sintaxis básica de C++. Además, busca desarrollar tu **lógica algorítmica** a través de una serie de problemas clásicos de programación.

Como tu profesor, te sugiero que no solo copies y pegues código, sino que intentes resolver cada problema en papel primero (prueba de escritorio) antes de codificar.

## Estructura del Laboratorio

### Parte 1: Familiarización con el IDE
*   Aprenderás a crear proyectos de consola en QtCreator.
*   Uso del **depurador (debugger)**: Esta es una herramienta vital. Aprende a poner *breakpoints* (puntos de interrupción) y a inspeccionar variables paso a paso.

### Parte 2: Ejercicios (1-30)
Estos son problemas cortos enfocados en conceptos específicos.
*   **Básicos (I/O y Aritmética)**: Suma, resta, residuo (`%`), potencias, mayor/menor. (Ejercicios 1-6)
*   **Bucles (Loops) y Acumuladores**: Sumatorias, factoriales, tablas de multiplicar. (Ejercicios 7, 8, 11, 15)
*   **Condiciones y Lógica**: Par/Impar, años bisiestos (implícito), validación de triángulos. (Ejercicios 2, 18, 26)
*   **Algoritmos Clásicos**:
    *   **Números Primos** (Ejercicio 19): Un número es primo si solo es divisible por 1 y por sí mismo.
    *   **Palíndromos** (Ejercicio 20): Números que se leen igual al revés (ej. 121).
    *   **Conversión de caracteres** (Ejercicio 21): Moverse en la tabla ASCII (Mayúscula <-> Minúscula).
    *   **Geometría**: Círculos, áreas.
*   **Juegos**: Adivinar un número (Ejercicio 29-30). Usa `rand()` y bucles `while`.

### Parte 3: Problemas (1-17)
Estos son retos más complejos que requieren combinar múltiples conceptos. Aquí te doy algunas pistas de experto:

#### Problema 2: Cajero Automático (Desglose de Moneda)
*   **Pista**: Usa el operador división (`/`) para saber cuántos billetes caben y el módulo (`%`) para saber cuánto dinero sobra para el siguiente billete. Ve del billete más grande al más pequeño.

#### Problema 4: Suma de Tiempos
*   Leer hora y duración como enteros (ej. `1245` y `345`) requiere separar horas y minutos.
*   **Tip**: `minutos = tiempo % 100`, `horas = tiempo / 100`. Suma minutos, si pasa de 60, incrementa horas.

#### Problema 7: Fibonacci y Pares
*   Genera la serie: 1, 1, 2, 3, 5, 8...
*   Solo suma los que sean **pares** (ej. 2, 8, 34...) y menores que `n`.

#### Problema 10 y 13: Números Primos
*   Necesitarás una función auxiliar `esPrimo(n)` que retorne verdadero o falso.
*   Para el problema 10, usa un contador de primos encontrados hasta llegar al enésimo.

#### Problema 14: Palíndromo más grande
*   Itera con dos bucles anidados desde 999 hasta 100. Multiplica `i * j` y verifica si el producto es palíndromo. Guarda el máximo encontrado.

#### Problema 15: Espiral Numérica
*   Este es un problema clásico (similar al Proyecto Euler #28).
*   **Pista**: Observa las esquinas. En una espiral 5x5, la esquina superior derecha es 25 ($5^2$). Las esquinas diagónales siguen un patrón cuadrático.

#### Problema 16: Serie de Collatz
*   **Regla**: Si es par $\rightarrow n/2$. Si es impar $\rightarrow 3n+1$.
*   El problema pide cuál semilla menor a `k` genera la secuencia más larga. Tendrás que probar todas las semillas desde 1 hasta `k` y contar los pasos.

---
### Recomedación Final
La depuración es tu mejor amiga. Si un bucle infinito congela tu programa, o un cálculo da resultados extraños, usa el depurador de QtCreator para ver qué está pasando 'por dentro'. ¡Mucho éxito!
