# Estructuras de Control en C++

## Introducción
Las estructuras de control permiten modificar el flujo de ejecución de un programa. Sin ellas, el código se ejecutaría siempre línea por línea de arriba a abajo. En C++, tenemos estructuras para tomar decisiones (condicionales) y para repetir tareas (bucles).

## Estructuras Condicionales

### 1. `if` y `else`
Evalúa una condición booleana. Si es verdadera, ejecuta un bloque; si es falsa, puede ejecutar otro (opcional).

```cpp
int edad = 18;

if (edad >= 18) {
    std::cout << "Eres mayor de edad." << std::endl;
} else if (edad > 12) {
    std::cout << "Eres adolescente." << std::endl;
} else {
    std::cout << "Eres un niño." << std::endl;
}
```

### 2. `switch`
Útil cuando quieres comparar una variable contra múltiples valores constantes posibles. Es más limpio que muchos `if-else` encadenados.
*   **Importante**: No olvides el `break` al final de cada caso para evitar que se ejecuten los siguientes ("fall-through").

```cpp
char opcion = 'A';

switch (opcion) {
    case 'A':
        std::cout << "Seleccionaste A" << std::endl;
        break;
    case 'B':
        std::cout << "Seleccionaste B" << std::endl;
        break;
    default:
        std::cout << "Opcion invalida" << std::endl;
}
```

## Estructuras Repetitivas (Bucles)

### 1. `while`
Repite un bloque de código **mientras** una condición sea verdadera. La condición se evalúa al principio.
*   **Cuidado**: Asegúrate de que la condición eventualmente sea falsa, o tendrás un bucle infinito.

```cpp
int contador = 0;
while (contador < 5) {
    std::cout << contador << " ";
    contador++; // Importante: actualizar la variable de control
}
// Salida: 0 1 2 3 4
```

### 2. `do-while`
Similar al `while`, pero garantiza que el bloque se ejecute **al menos una vez**, ya que la condición se evalúa al final.

```cpp
int n;
do {
    std::cout << "Ingresa un numero positivo: ";
    std::cin >> n;
} while (n <= 0); // Sigue pidiendo mientras no sea positivo
```

### 3. `for`
Es el bucle más usado cuando sabes de antemano cuántas veces quieres repetir algo. Compacta la inicialización, la condición y la actualización en una sola línea.

```cpp
// for (inicializacion; condicion; actualizacion)
for (int i = 0; i < 5; i++) {
    std::cout << "Iteracion " << i << std::endl;
}
```

### 4. `for-each` (Range-based for loop)
Introducido en C++11, es ideal para recorrer arreglos o contenedores completos sin preocuparse por índices.

```cpp
int numeros[] = {10, 20, 30};
for (int num : numeros) {
    std::cout << num << " ";
}
```

## Sentencias de Salto
*   `break`: Sale inmediatamente del bucle o switch más cercano.
*   `continue`: Salta el resto del código en la iteración actual y pasa a la siguiente.

---
## Ejercicios Propuestos
1.  **Calculadora con Switch**: Crea un programa que pida dos números y un operador (+, -, *, /) y use `switch` para mostrar el resultado.
2.  **Suma de Pares**: Usa un bucle `for` para sumar todos los números pares del 1 al 100.
3.  **Adivina el Número**: Usa un `do-while` para pedir al usuario que adivine un número secreto.
