# ¡Hola! Soy Esau 👋

Bienvenido a mi perfil de GitHub. Soy un apasionado del desarrollo de software y me encanta trabajar en proyectos que desafían mis habilidades y conocimientos. Aquí te presento uno de mis proyectos básicos en C++: una calculadora.

## Calculadora Básica en C++

Este proyecto es una calculadora simple que permite realizar las siguientes operaciones matemáticas:

- Suma
- Resta
- Multiplicación
- División

### ¿Cómo funciona?

La calculadora presenta un menú al usuario con las opciones de operaciones disponibles. Después de seleccionar una operación, el usuario ingresa dos números y la calculadora muestra el resultado de la operación seleccionada. El proceso se repite hasta que el usuario decide salir.

### Ejemplo de Uso

```cpp
// Calculadora Básica en C++
// Autor: Esau
// Descripción: Esta calculadora permite realizar operaciones básicas como suma, resta, multiplicación y división.

#include <iostream>
using namespace std;

class Calculadora {
public:
    void presentar() {
        cout << "Hola, soy Esau, y esta es una calculadora básica en C++.\n";
    }

    void menu() {
        cout << "Seleccione la operación que desea realizar:\n";
        cout << "1. Suma\n";
        cout << "2. Resta\n";
        cout << "3. Multiplicación\n";
        cout << "4. División\n";
        cout << "5. Salir\n";
    }

    void ejecutar() {
        int opcion;
        double num1, num2;

        do {
            menu();
            cin >> opcion;

            if (opcion == 5) {
                break;
            }

            cout << "Ingrese dos números: ";
            cin >> num1 >> num2;

            switch (opcion) {
                case 1:
                    cout << "Resultado: " << suma(num1, num2) << endl;
                    break;
                case 2:
                    cout << "Resultado: " << resta(num1, num2) << endl;
                    break;
                case 3:
                    cout << "Resultado: " << multiplicacion(num1, num2) << endl;
                    break;
                case 4:
                    cout << "Resultado: " << division(num1, num2) << endl;
                    break;
                default:
                    cout << "Opción no válida. Intente nuevamente.\n";
            }

        } while (opcion != 5);
    }

private:
    double suma(double a, double b) {
        return a + b;
    }

    double resta(double a, double b) {
        return a - b;
    }

    double multiplicacion(double a, double b) {
        return a * b;
    }

    double division(double a, double b) {
        if (b != 0) {
            return a / b;
        } else {
            cout << "Error: División por cero.\n";
            return 0;
        }
    }
};

int main() {
    Calculadora calc;
    calc.presentar();
    calc.ejecutar();
    return 0;
}
