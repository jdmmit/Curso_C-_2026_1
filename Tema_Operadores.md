# Operadores en C++

## Introducción
Los operadores son los símbolos que le dicen al compilador que realice manipulaciones matemáticas, lógicas o textuales específicas. C++ es muy rico en operadores y entender su precedencia (orden de evaluación) es crucial para evitar errores lógicos.

## Clasificación por Operandos
*   **Unarios**: Un operando (ej. `-a`, `!a`, `++a`).
*   **Binarios**: Dos operandos (ej. `a + b`, `a && b`).
*   **Ternarios**: Tres operandos (el único es `?:`).

## Tipos de Operadores

### 1. Aritméticos
Para operaciones matemáticas básicas.
*   `+`, `-`, `*`, `/` (Suma, resta, multiplicación, división).
*   `%` (Módulo): Devuelve el **residuo** de la división. Solo funciona con enteros.
*   `++`, `--`: Incremento y decremento en 1. Pueden ser prefijos (`++a`) o sufijos (`a++`).

### 2. Relacionales (Comparación)
Devuelven `true` (1) o `false` (0).
*   `==` (Igualdad), `!=` (Desigualdad).
*   `<`, `>`, `<=`, `>=`.

### 3. Lógicos
Para conectar condiciones booleanas.
*   `&&` (AND): Verdadero si **ambos** son verdaderos.
*   `||` (OR): Verdadero si **al menos uno** es verdadero.
*   `!` (NOT): Invierte el valor (de verdadero a falso y viceversa).

### 4. Asignación
Asignan valor a una variable, a menudo combinando una operación.
*   `=`: Asignación simple.
*   `+=`, `-=`, `*=`, `/=`, `%=`: Operación y asignación (ej. `x += 5` es `x = x + 5`).

### 5. A nivel de Bit (Bitwise)
Operan directamente sobre la representación binaria de los enteros.
*   `&` (AND binario), `|` (OR binario), `^` (XOR binario).
*   `~` (Complemento a uno/NOT binario).
*   `<<`, `>>` (Desplazamiento de bits a izq. o der.).

### 6. Otros Operadores Importantes
*   `sizeof()`: Devuelve el tamaño en bytes de un tipo de dato o variable.
*   `?:` (Ternario): `condicion ? valor_si_true : valor_si_false`. Sustituto compacto del `if-else`.

## Jerarquía de Operadores (Precedencia)
El orden en que se resuelven las operaciones es crítico. Un error común es asumir un orden incorrecto.

1.  **Mayor prioridad**: Paréntesis `()`, corchetes `[]`, acceso a miembros `.`, `->`.
2.  **Unarios**: `++`, `--`, `!`, `~`, `sizeof`, `new`, `delete`.
3.  **Aritméticos Multiplicativos**: `*`, `/`, `%`.
4.  **Aritméticos Aditivos**: `+`, `-`.
5.  **Desplazamiento**: `<<`, `>>`.
6.  **Relacionales**: `<`, `<=`, `>`, `>=` (y luego `==`, `!=`).
7.  **Bitwise**: `&`, luego `^`, luego `|`.
8.  **Lógicos**: `&&` (AND) tiene más prioridad que `||` (OR).
9.  **Ternario y Asignación**: Son los de **menor prioridad** (se evalúan al final).

### Ejemplo de Precedencia
```cpp
int x = 5 + 3 * 2; // x es 11, NO 16. (3*2 se evalúa primero)
bool b = 8 >= 4 && 4 >= 2; // (8>=4) AND (4>=2) -> true AND true -> true
```

### El Operador `sizeof`
Es muy útil para conocer la arquitectura de la máquina:
```cpp
sizeof(int); // Usualmente 4
sizeof(char); // Siempre 1
```

---
*Consejo de experto: Ante la duda sobre la prioridad de los operadores, usa paréntesis `()`. No solo asegura que el código haga lo que quieres, sino que lo hace más legible para otros programadores.*
