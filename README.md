# C++ - Repaso para Examen

## Programa Básico en C++
```cpp
int main()
{                                    // Función principal del programa
    cout << "¡Hola, mundo!" << endl; // Muestra un mensaje en pantalla
    return 0;                        // Indica que el programa finalizó correctamente
}
```

## Variables y Tipos de Datos
### Datos Primitivos
```cpp
int edad = 23;       // Entero (número sin decimales)
float altura = 1.75; // Número decimal de precisión simple
double peso = 70.5;  // Número decimal de doble precisión
char inicial = 'J';  // Un solo carácter
bool activo = true;  // Valor booleano (true o false)
```

### Datos no primitivos
```cpp
struct Persona
{
    char nombre[50];
    int edad;
};

class Persona
{
public:
    string nombre;
    int edad;
};
```
## Operadores
### Operadores aritméticos
```cpp
int a = 10, b = 5;
int suma = a + b;  // Suma: 15
int resta = a - b; // Resta: 5
int mult = a * b;  // Multiplicación: 50
int div = a / b;   // División: 2
int mod = a % b;   // Módulo (resto de la división): 0
```
### Operadores relacionales
```cpp
int a = 10, b = 5;
bool igual = (a == b);      // Igual a: false
bool diferente = (a != b);  // Diferente de: true
bool mayor = (a > b);       // Mayor que: true
bool menor = (a < b);       // Menor que: false
bool mayorIgual = (a >= b); // Mayor o igual que: true
bool menorIgual = (a <= b); // Menor o igual que: false
```
### Operadores lógicos
```cpp
bool a = true, b = false;
bool andLogico = (a && b); // AND lógico: false
bool orLogico = (a || b);  // OR lógico: true
bool notLogicoA = (!a);    // NOT lógico de a: false
bool notLogicoB = (!b);    // NOT lógico de b: true
```
## Estructuras de Control
### if
```cpp
int edad = 18;
if (edad >= 18)
{
    std::cout << "Eres mayor de edad." << std::endl;
}
```
### if-else
```cpp
edad = 15;
if (edad >= 18)
{
    std::cout << "Eres mayor de edad." << std::endl;
}
else
{
    std::cout << "Eres menor de edad." << std::endl;
}
```
### if-elseif-else
```cpp
edad = 15;
if (edad >= 18)
{
    std::cout << "Eres mayor de edad." << std::endl;
}
else if (edad >= 13)
{
    std::cout << "Eres un adolescente." << std::endl;
}
else
{
    std::cout << "Eres un niño." << std::endl;
}
```
### switch-case
```cpp
int opcion = 2;
switch (opcion) {
    case 1:
        cout << "Opción 1";
        break;
    case 2:
        cout << "Opción 2";
        break;
    default:
        cout << "Opción no válida";
}
```
## Ciclos
### for
```cpp
for (int i = 0; i < 5; i++)
{
    cout << "Iteración " << i << endl;
}
```
### while
```cpp
int i = 0;
while (i < 5) {
    cout << "Iteración " << i << endl;
    i++;
}
```
### do-while
```cpp
i = 0;
do {
    cout << "Iteración " << i << endl;
    i++;
} while (i < 5);
```
## Funciones
```cpp

int suma(int a, int b) {
    return a + b;
}

int main() {
    cout << "Suma: " << suma(5, 3);
}
```
## Arreglos y Matrices
### ARREGLO
```cpp
int numeros[] = {1, 2, 3, 4, 5};
cout << numeros[0]; // Accede al primer elemento
```
### MATRIZ
```cpp
int matriz[2][3] = {{1, 2, 3}, {4, 5, 6}};
```
## Programación Orientada a Objetos
### Clases y objetos
```cpp
class Persona {
public:
    string nombre; // Atributo
    int edad; // Atributo

    // Método
    void mostrarDatos() {
        cout << "Nombre: " << nombre << ", Edad: " << edad << endl;
    }
};
```
### Superclase Persona
```cpp
class Persona
{
protected: // Se puede acceder desde clases derivadas
    int edad;

public:
    std::string nombre;

    // Constructor
    Persona(std::string _nombre, int _edad)
    {
        nombre = _nombre;
        edad = _edad;
        std::cout << "Objeto Persona creado" << std::endl;
    }

    // Método público
    void mostrarDatos()
    {
        std::cout << "Nombre: " << nombre << ", Edad: " << edad << std::endl;
    }

    // Destructor
    ~Persona()
    {
        std::cout << "Objeto Persona eliminado" << std::endl;
    }
};
```
### Clase derivada (hija) de Persona
```cpp
class Estudiante : public Persona
{
private:
    int carnet;

public:
    // Constructor
    Estudiante(std::string _nombre, int _edad, int _carnet) : Persona(_nombre, _edad)
    {
        carnet = _carnet;
    }

    // Setter para modificar el carnet
    void setCarnet(int _carnet)
    {
        carnet = _carnet;
    }

    // Getter para obtener el carnet
    int getCarnet()
    {
        return carnet;
    }

    // Método para mostrar datos del estudiante
    void mostrarDatos()
    {
        std::cout << "Nombre: " << nombre << ", Edad: " << edad << ", Carnet: " << carnet << std::endl;
    }

    // Destructor
    ~Estudiante()
    {
        std::cout << "Objeto Estudiante eliminado" << std::endl;
    }
};
```
### Instanciación y manipulación
```cpp
int main()
{
    // Instanciación de un objeto de la clase Estudiante
    Estudiante estudiante1("TILIN", 23, 12345);

    // Usar métodos del objeto
    estudiante1.mostrarDatos();

    // Modificar el carnet usando el setter
    estudiante1.setCarnet(67890);

    // Obtener el carnet usando el getter
    std::cout << "Carnet actualizado: " << estudiante1.getCarnet() << std::endl;

    return 0;
}
```
## Libreria <iostream> - Entrada y Salida de Datos
### Entrada
```cpp
int edad;
std::cout << "Ingresa tu edad: ";
std::cin >> edad;
```
### Salida
```cpp
std::cout << "Tu edad es: " << edad << std::endl;
```
### Cerr
```cpp
std::cerr << "Error al abrir el archivo" << std::endl;
```
### Salto de linea
```cpp
std::cout << "Hola" << std::endl; // Salto de línea
std::cout << "Mundo" << std::endl; // Salto de línea
```
## Librería iomanip - Formateo de Salida
```cpp
#include <iomanip> // Incluye la librería iomanip

// SETW
std::cout << std::setw(10) << "Nombre" << std::setw(10) << "Edad" << std::endl;

// SETFILL
std::cout << std::setfill('*') << std::setw(10) << "Nombre" << std::setw(10) << "Edad" << std::endl;

// SETPRECISION Y FIXED
double pi = 3.14159; 
std::cout << std::fixed << std::setprecision(2) << pi << std::endl; // salida: 3.14

// LEFT Y RIGHT
std::cout << std::left << std::setw(10) << "Nombre" << std::right << std::setw(10) << "Edad" << std::endl; // Nombre     Edad
```
