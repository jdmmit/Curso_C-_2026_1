# Arreglos Estáticos en C++

## Introducción
Un arreglo (array) es una estructura de datos que almacena una colección de elementos del **mismo tipo** en ubicaciones de memoria contiguas. "Estático" significa que su tamaño se define al momento de compilar y no puede cambiar durante la ejecución del programa.

## Declaración e Inicialización
Para declarar un arreglo, especificas el tipo de dato, el nombre y el tamaño entre corchetes `[]`.

```cpp
// Tipo Nombre[Tamano];
int puntajes[5]; // Declara un arreglo de 5 enteros (contenido basura inicial)

// Inicializacion explicita
int vocales[5] = {10, 20, 30, 40, 50};

// Inicializacion parcial (el resto se llena con ceros)
int valores[5] = {1, 2}; // {1, 2, 0, 0, 0}

// Deducir tamaño (solo al inicializar)
char saludo[] = "Hola"; // Tamaño 5 (H, o, l, a, \0)
```

## Acceso a Elementos
Se accede a los elementos usando su índice.
**¡IMPORTANTE!**: En C++, los índices empiezan en **0**. Si tienes un arreglo de tamaño `N`, el último elemento está en la posición `N-1`.

```cpp
int x = vocales[0]; // 10
vocales[2] = 99; // Cambia 30 por 99
```

> [!WARNING]
> C++ **no verifica** si te sales de los límites del arreglo (Buffer Overflow). Si intentas acceder a `vocales[10]`, podrías leer memoria basura o hacer que tu programa falle (crash). ¡Ten mucho cuidado!

## Arreglos Multidimensionales
Puedes tener arreglos de arreglos, como matrices (2D) o cubos (3D).

```cpp
// Matriz de 3 filas x 4 columnas
int matriz[3][4] = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12}
};

int valor = matriz[1][2]; // Fila 1 (segunda), Columna 2 (tercera) -> 7
```

## Recorriendo Arreglos
La forma clásica es usar un bucle `for`.

```cpp
int suma = 0;
for (int i = 0; i < 5; i++) {
    suma += vocales[i];
}
```

## Arreglos y Funciones
Cuando pasas un arreglo a una función, en realidad estás pasando un puntero al primer elemento. Por eso, generalmente necesitas pasar también el tamaño del arreglo, ya que la función no sabe cuánto mide.

```cpp
void imprimirArreglo(int arr[], int tamano) {
    for (int i = 0; i < tamano; i++) {
        std::cout << arr[i] << " ";
    }
}
```

---
## Ejercicios Propuestos
1.  **Invertir Arreglo**: Crea un arreglo de 10 números y escribe un código que invierta el orden de sus elementos (sin usar otro arreglo auxiliar si te atreves).
2.  **Máximo y Mínimo**: Encuentra el valor más grande y el más pequeño en un arreglo de 20 números aleatorios.
3.  **Matriz Identidad**: Escribe un programa que genere e imprima una matriz identidad de N*N (donde la diagonal principal son 1s y el resto 0s).
