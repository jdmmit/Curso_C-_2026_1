# Funciones y Paso de Parámetros en C++

## Introducción
Las funciones permiten dividir un programa grande en pequeñas piezas reutilizables y manejables. Cada función realiza una tarea específica.

## Definición
```cpp
// TipoRetorno NombreFuncion(Parametros) { Cuerpo }

int sumar(int a, int b) {
    return a + b;
}

void saludar() { // void significa que no retorna nada
    std::cout << "Hola!" << std::endl;
}
```

## Prototipos (Declaración vs Definición)
En C++, debes declarar la función antes de usarla (`main` suele ir al final, o usas prototipos arriba).

```cpp
// Prototipo
int multiplicar(int, int);

int main() {
    std::cout << multiplicar(5, 3);
}

// Definición
int multiplicar(int x, int y) {
    return x * y;
}
```

## Paso de Parámetros

### 1. Paso por Valor (Por defecto)
Se crea una **copia** de la variable dentro de la función. Los cambios dentro de la función NO afectan a la variable original.

```cpp
void incremetar(int x) {
    x = x + 1; // Solo cambia la copia local
}
```

### 2. Paso por Referencia (`&`)
La función recibe la **dirección** de la variable original, pero se usa con la sintaxis de una variable normal. Los cambios SÍ afectan a la original. Es más eficiente (evita copias).

```cpp
void incrementarReal(int &x) {
    x = x + 1; // Cambia la variable original
}
```

### 3. Paso por Puntero (`*`)
Similar a la referencia, pero usando sintaxis de punteros. Es herencia de C.

```cpp
void incrementarPuntero(int *x) {
    *x = *x + 1;
}
// Llamada: incrementarPuntero(&numero);
```

## Funciones `inline`
Sugieren al compilador que inserte el cuerpo de la función en el lugar de la llamada para optimizar velocidad (útil para funciones muy pequeñas).

## Sobrecarga de Funciones
Puedes tener múltiples funciones con el **mismo nombre** siempre que sus parámetros sean diferentes (en cantidad o tipo).

```cpp
int area(int lado); // Cuadrado
int area(int base, int altura); // Rectángulo
```

---
## Ejercicios Propuestos
1.  **Calculadora Modular**: Reescribe tu calculadora para que cada operación (suma, resta, etc.) sea una función separada.
2.  **Referencias**: Escribe una función que reciba un `double` y devuelva su parte entera y su parte fraccionaria en dos variables distintas (pasadas por referencia).
3.  **Factorial Recursivo**: Escribe una función que calcule el factorial de un número llamándose a sí misma.
