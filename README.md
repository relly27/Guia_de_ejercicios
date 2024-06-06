# Guía de ejercicios N° 1
- 1. Diseñe un programa en C/C++ que muestre el número mayor y la cantidad de veces que se
repite dentro de un vector de n posiciones, siendo n una variable ingresada por el usuario.

```c++
#include <iostream>
using namespace std;

int main() {
    int n;
    char opcion;

    do {
        //limpiar pantalla
        //clscr()
        cout << "Ingrese la cantidad de elementos del vector: ";
        cin >> n;

        int vec[n];
        cout << "Ingrese los elementos del vector:\n";
        for (int i = 0; i < n; ++i) {
            cout << "Elemento " << i + 1 << ": ";
            cin >> vec[i];
        }

        // Encontrar el número mayor y contar repeticiones
        int mayor = vec[0];
        int repeticiones = 1;
        for (int i = 1; i < n; ++i) {
            if (vec[i] > mayor) {
                mayor = vec[i];
                repeticiones = 1;
            } else if (vec[i] == mayor) {
                ++repeticiones;
            }
        }

        // Mostrar los resultados
        cout << "\nEl numero mayor es: " << mayor << endl;
        cout << "Se repite " << repeticiones << " veces.\n";

        // Preguntar si el usuario quiere continuar o salir
        cout << "\n¿Desea realizar otra operación? (s/n): ";
        cin >> opcion;

    } while (opcion == 's' || opcion == 'S');

    cout << "Programa finalizado.\n";

    return 0;
}
```

- 2. Diseñe un programa en C/C++ que lea la temperatura al mediodía, durante todos los días
de un mes y muestre la temperatura promedio y el día que más hizo calor y el que más hizo
frio. Sabiendo que la temperatura máxima es 60 grados y mínima -90 grados.

```c++
#include <iostream>

int main() {
    using namespace std;
    
     int DIAS_EN_UN_MES;
     int TEMPERATURA_MAXIMA = 60;
     int TEMPERATURA_MINIMA = -90;
     
     cout << "Cuantos dias vas a calcular la temperatura promedio" << endl;
     
     cin >> DIAS_EN_UN_MES;

    char opcion;
    
    do {
        int temperaturas[DIAS_EN_UN_MES];
        int sumaTemperaturas = 0;
        int temperaturaPromedio;
        int temperaturaMaxima = TEMPERATURA_MINIMA - 1;
        int temperaturaMinima = TEMPERATURA_MAXIMA + 1;
        int diaMasCaluroso, diaMasFrio;

        // Leer temperaturas para cada día del mes
        for (int dia = 0; dia < DIAS_EN_UN_MES; ++dia) {
            cout << "Ingrese la temperatura para el día " << (dia + 1) << ": ";
            cin >> temperaturas[dia];

            // Validar que la temperatura esté en el rango permitido
            while (temperaturas[dia] < TEMPERATURA_MINIMA || temperaturas[dia] > TEMPERATURA_MAXIMA) {
                cout << "Error. La temperatura debe estar entre " << TEMPERATURA_MINIMA << " y " << TEMPERATURA_MAXIMA << " grados." << endl;
                cout << "Ingrese la temperatura para el día " << (dia + 1) << ": ";
                cin >> temperaturas[dia];
            }

            // Calcular suma de temperaturas para el promedio
            sumaTemperaturas += temperaturas[dia];

            // Actualizar temperaturas máxima y mínima
            if (temperaturas[dia] > temperaturaMaxima) {
                temperaturaMaxima = temperaturas[dia];
                diaMasCaluroso = dia + 1;
            }

            if (temperaturas[dia] < temperaturaMinima) {
                temperaturaMinima = temperaturas[dia];
                diaMasFrio = dia + 1;
            }
        }

        // Calcular temperatura promedio
        temperaturaPromedio = sumaTemperaturas / DIAS_EN_UN_MES;

        // Mostrar resultados
        cout << "\nTemperatura promedio : " << temperaturaPromedio << " grados" << endl;
        cout << "Día más caluroso: Día " << diaMasCaluroso << " con " << temperaturaMaxima << " grados" << endl;
        cout << "Día más frío: Día " << diaMasFrio << " con " << temperaturaMinima << " grados" << endl;

        cout << "\n¿Desea volver a ejecutar el programa? (S/N): ";
        cin >> opcion;
        cin;  // Limpiar el buffer de entrada

    } while (opcion == 'S' || opcion == 's');

    return 0;
}
```

- 3. Diseñe un programa en C/C++ que muestre el número menor y la cantidad de veces que se
repite dentro de un vector de n posiciones, siendo n una variable ingresada por el usuario

```c++
#include <iostream>
using namespace std;



int main() {
    int n;
    char opcion;

    do {
        //borrar pantalla
        //clscr()
        cout << "Ingrese la cantidad de elementos del vector: ";
        cin >> n;

        int vec[n];
        cout << "Ingrese los elementos del vector:\n";
        for (int i = 0; i < n; ++i) {
            cout << "Elemento " << i + 1 << ": ";
            cin >> vec[i];
        }

        // Encontrar el número menor y contar repeticiones
        int menor = vec[0];
        int repeticiones = 1;
        for (int i = 1; i < n; ++i) {
            if (vec[i] < menor) {
                menor = vec[i];
                repeticiones = 1;
            } else if (vec[i] == menor) {
                ++repeticiones;
            }
        }

        // Mostrar los resultados
        cout << "\nEl numero menor es: " << menor << endl;
        cout << "Se repite " << repeticiones << " veces.\n";

        // Preguntar si el usuario quiere continuar o salir
        cout << "\n¿Desea realizar otra operación? (s/n): ";
        cin >> opcion;

    } while (opcion == 's' || opcion == 'S');

    cout << "Programa finalizado.\n";

    return 0;
}

```

- 4. Diseñe un programa en C/C++ que dado 2 vectores de n posiciones, siendo n una variable
ingresada por el usuario, validar que los 2 vectores tengan igual tamaño, ordene de forma
creciente el primer vector, decreciente el segundo vector y en el tercer vector muestre la
suma del primero con el segundo.

```c++
#include <iostream>
using namespace std;
int main() {
    
    char opcion;
    
    do{
    
    int n1;
    int n2;
    
    cout << "Ingrese el tamaño de su primer vector" << endl;
    
    cin >> n1;
    
    cout << "Ingrese el tamaño de su segundo vector" << endl;
    
    cin >> n2;
    
    int vector1[n1];
    int vector2[n2];
    
    for(int i=0; i< n1; i++){
        cout << "ingrese numero " << i + 1 << " de su primer vector: " << endl;
        cin >> vector1[i];
        
    }
    
    for(int i=0; i< n2; i++){
        cout << "ingrese numero " << i + 1 << " de su segunddo vector: " << endl;
        cin >> vector2[i];
    }
    
    int totalTam = n1;
    
    if(n1>n2){
        cout << "tu primer vector es mayor a tu segundo vector" << endl;
        totalTam = n1;
    }else if(n2>n1){
        cout << "tu segundo vector es mayor a tu primer vector" << endl;
        totalTam = n2;
    }else{
        cout << "tus vectores tienen el mismo tamaño" << endl;
    }
    
    
    cout << endl;
    
    for (int i = 0; i < n1 - 1; ++i) {
        for (int j = 0; j < n1 - i - 1; ++j) {
            if (vector1[j] > vector1[j + 1]) {
                int temp = vector1[j];
                vector1[j] = vector1[j + 1];
                vector1[j + 1] = temp;
            }
        }
    }
    
    for (int i = 0; i < n2 - 1; ++i) {
        for (int j = 0; j < n2 - i - 1; ++j) {
            if (vector2[j] < vector2[j + 1]) {  // 
                int temp = vector2[j];
                vector2[j] = vector2[j + 1];
                vector2[j + 1] = temp;
            }
        }
    }
    
    
    cout << "Primer vector ordenado de forma creciente: ";
    for (int i = 0; i < n1; ++i) {
        cout << vector1[i] << " ";
    }
   
   cout << endl;
   
    cout << "Segundo vector ordenado de forma decreciente: ";
    for (int i = 0; i < n2; ++i) {
        cout << vector2[i] << " ";
    }
    
    int vectorSuma[totalTam];
    
    for (int i = 0; i < totalTam; ++i) {
        vectorSuma[i] = vector1[i] + vector2[i];
    }
    
    cout << endl;
    cout << "Vectores sumados: ";
    for (int i = 0; i < totalTam; ++i) {
        cout << vectorSuma[i] << " ";
    }
    
    cout << endl;
    
     cout << "\n¿Desea volver a ejecutar el programa? (S/N): ";
        cin >> opcion;
        cout << endl;

    } while (opcion == 'S' || opcion == 's');
    
    return 0;
}
```

- 5. Diseñe un programa en C/C++ que dado un vector de n posiciones, siendo n una variable
ingresada por el usuario, calcule el promedio de los datos ingresados y muestre cuales son
mayores

```c++
#include <iostream>
using namespace std;

int main() {
    int n;
    char opcion;

    do {
        cout << "Ingrese la cantidad de elementos del vector: ";
        cin >> n;

        int vec[n];
        cout << "Ingrese los elementos del vector (" << n << " elementos):" << endl;
        for (int i = 0; i < n; i++) {
            cout << "Elemento " << i + 1 << ": ";
            cin >> vec[i];
        }

        // Calcular la suma
        int suma = 0;
        for (int i = 0; i < n; i++) {
            suma += vec[i];
        }

        // Calcular el promedio
        // Se utiliza división entera, lo que asegura que la división sea precisa
        int promedio = suma / n;

        // Mostrar el promedio
        cout << "\nEl promedio de los elementos ingresados es: " << promedio << endl;

        // Mostrar los elementos mayores que el promedio
        cout << "Elementos mayores que el promedio:" << endl;
        for (int i = 0; i < n; i++) {
            if (vec[i] > promedio) {
                cout << "Elemento " << i + 1 << ": " << vec[i] << endl;
            }
        }

        // Preguntar si el usuario quiere continuar o salir
        cout << "\n¿Desea realizar otra operación? (s/n): ";
        cin >> opcion;

    } while (opcion == 's' || opcion == 'S');

    cout << "Programa finalizado.\n";

    return 0;
}
```

- 6. Diseñe un programa en C/C++ que dado 2 vector de n posiciones, siendo n una variable
ingresada por el usuario, multiplique el primer vector por el segundo vector y lo guarde en
un tercer vector de la siguiente manera:
  - **Primer vector** [5, 2, 8, 7, 9]
  - **Segundo vector** [23, 45, 2, 6]
  - **tercer vector** [(5*23)+(5*45)+(5*2)+(5*6)][xxx][xxx][xxx]

```c++
#include <iostream>
using namespace std;

const int n1 = 5; // Tamaño del primer vector
const int n2 = 4; // Tamaño del segundo vector

int vectorA[n1], vectorB[n2], resultado[n1];

int main() {
    int opcion;
    bool continuar = true;

    while (continuar) {
        // Mostrar menú
        cout << "\nMenu:\n";
        cout << "1. Ingresar elementos del primer vector\n";
        cout << "2. Ingresar elementos del segundo vector\n";
        cout << "3. Calcular y mostrar resultados\n";
        cout << "4. Salir\n";
        cout << "Seleccione una opción: ";
        cin >> opcion;

        switch (opcion) {
            case 1: {
                // Ingresar elementos del primer vector
                cout << "Ingrese los elementos del primer vector (" << n1 << " elementos):" << endl;
                for (int i = 0; i < n1; i++) {
                    cout << "Elemento " << i + 1 << ": ";
                    cin >> vectorA[i];
                }
                break;
            }
            case 2: {
                // Ingresar elementos del segundo vector
                cout << "Ingrese los elementos del segundo vector (" << n2 << " elementos):" << endl;
                for (int i = 0; i < n2; i++) {
                    cout << "Elemento " << i + 1 << ": ";
                    cin >> vectorB[i];
                }
                break;
            }
            case 3: {
                // Calcular multiplicaciones
                cout << "Resultado de las multiplicaciones y sumas:" << endl;
                for (int i = 0; i < n1; i++) {
                    resultado[i] = 0;
                    for (int j = 0; j < n2; j++) {
                        resultado[i] += vectorA[i] * vectorB[j];
                    }
                    cout << "Resultado para el elemento " << i + 1 << " del primer vector: " << resultado[i] << endl;
                }
                break;
            }
            case 4:
                continuar = false;
                cout << "Saliendo del programa..." << endl;
                break;
            default:
                cout << "Opción no válida, intente nuevamente." << endl;
        }
    }

    return 0;
}
```

- 7. Diseñe un programa en C/C++ que dado un vector de n cantidad de posiciones, siendo n un variable
ingresada por el usuario, guardar en un segundo vector los datos pero de forma inversa es decir:
  - **A.** [5, 2, 8, 7, 9]
  - **B.** [9, 7, 8, 2, 5]

```c++
#include <iostream>
using namespace std;



int main() {
    int n;
    char opcion;

    do {
        //borrar pantalla
        //clscr()
        cout << "Ingrese la cantidad de elementos del vector: ";
        cin >> n;

        int vec[n], vecInverso[n];
        cout << "Ingrese los elementos del vector (" << n << " elementos):" << endl;
        for (int i = 0; i < n; i++) {
            cout << "Elemento " << i + 1 << ": ";
            cin >> vec[i];
        }

        // Guardar los elementos en orden inverso en el segundo vector
        for (int i = 0; i < n; i++) {
            vecInverso[i] = vec[n - 1 - i];
        }

        // Mostrar el segundo vector
        cout << "\nVector original:" << endl;
        for (int i = 0; i < n; i++) {
            cout << vec[i] << " ";
        }
        cout << endl;

        cout << "Vector invertido:" << endl;
        for (int i = 0; i < n; i++) {
            cout << vecInverso[i] << " ";
        }
        cout << endl;

        // Preguntar si el usuario quiere continuar o salir
        cout << "\n¿Desea realizar otra operación? (s/n): ";
        cin >> opcion;

    } while (opcion == 's' || opcion == 'S');

    cout << "Programa finalizado.\n";

    return 0;
}
```

- 8. Diseñe un programa en C/C++ que dado 2 vectores de n cantidad de posiciones, siendo n variable
ingresada por el usuario, validar que los 2 vectores tengan igual tamaño, guardar en un tercer vector
los datos comunes entre los 2 vectores, que se encuentran tanto en el primero vector como en el
segundo vector, es decir :
  - **A.** [`24`, 55, 6, `15`, 90]
  - **B.** [45, `15`, 66, 34, `24`]
  - **C.** [24, 15]

```c++
#include <iostream>
using namespace std;

int main() {
    int n;
    char opcion;

    do {
        //borrar pantalla
        //clscr()
        cout << "Ingrese la cantidad de elementos de los vectores: ";
        cin >> n;

        if (n <= 0) {
            cout << "La cantidad de elementos debe ser mayor que 0. Intente nuevamente." << endl;
            continue;
        }

        int vecA[n], vecB[n], vecC[n];
        int k = 0; // contador para elementos comunes

        cout << "Ingrese los elementos del primer vector (" << n << " elementos):" << endl;
        for (int i = 0; i < n; i++) {
            cout << "Elemento " << i + 1 << ": ";
            cin >> vecA[i];
        }

        cout << "Ingrese los elementos del segundo vector (" << n << " elementos):" << endl;
        for (int i = 0; i < n; i++) {
            cout << "Elemento " << i + 1 << ": ";
            cin >> vecB[i];
        }

        // Encontrar elementos comunes y guardarlos en vecC
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (vecA[i] == vecB[j]) {
                    bool alreadyInVecC = false;
                    for (int m = 0; m < k; m++) {
                        if (vecC[m] == vecA[i]) {
                            alreadyInVecC = true;
                            break;
                        }
                    }
                    if (!alreadyInVecC) {
                        vecC[k] = vecA[i];
                        k++;
                    }
                    break;
                }
            }
        }

        // Mostrar el tercer vector con los elementos comunes
        cout << "\nElementos comunes entre los dos vectores:" << endl;
        if (k == 0) {
            cout << "No hay elementos comunes." << endl;
        } else {
            for (int i = 0; i < k; i++) {
                cout << vecC[i] << " ";
            }
            cout << endl;
        }

        // Preguntar si el usuario quiere continuar o salir
        cout << "\n¿Desea realizar otra operación? (s/n): ";
        cin >> opcion;

    } while (opcion == 's' || opcion == 'S');

    cout << "Programa finalizado.\n";

    return 0;
}
```

- 9. Diseñe un programa en C/C++ que me permita saber cuántos los números positivos, negativos y ceros
en vector de n posiciones, siendo n una variable ingresada por el usuario.

```c++
#include <iostream>
using namespace std;

int main() {
    int n;
    char opcion;

    do {
        //borrar pantalla
        //clscr()
        cout << "Ingrese la cantidad de elementos del vector: ";
        cin >> n;

        while (n <= 0) {
            cout << "La cantidad de elementos debe ser mayor que 0. Intente nuevamente: ";
            cin >> n;
        }

        int vec[n];
        int positivos = 0, negativos = 0, ceros = 0;

        cout << "Ingrese los elementos del vector (" << n << " elementos):" << endl;
        for (int i = 0; i < n; i++) {
            cout << "Elemento " << i + 1 << ": ";
            cin >> vec[i];

            if (vec[i] > 0) {
                positivos++;
            } else if (vec[i] < 0) {
                negativos++;
            } else {
                ceros++;
            }
        }

        // Mostrar los resultados
        cout << "\nCantidad de números positivos: " << positivos << endl;
        cout << "Cantidad de números negativos: " << negativos << endl;
        cout << "Cantidad de ceros: " << ceros << endl;

        // Preguntar si el usuario quiere continuar o salir
        cout << "\n¿Desea realizar otra operación? (s/n): ";
        cin >> opcion;

    } while (opcion == 's' || opcion == 'S');

    cout << "Programa finalizado.\n";

    return 0;
}
```

- 10. Diseñe un programa en C/C++ que me permita saber cuántos números hay en un rango dado por el
usuario, en un vector de n posiciones siendo n una variable ingresada por el usuario.

```c++
#include <iostream>
using namespace std;

int main() {
    int n;
    char opcion;

    do {
        //borrar pantalla
        //clscr()
        cout << "Ingrese la cantidad de elementos del vector: ";
        cin >> n;

        while (n <= 0) {
            cout << "La cantidad de elementos debe ser mayor que 0. Intente nuevamente: ";
            cin >> n;
        }

        int vec[n];
        cout << "Ingrese los elementos del vector (" << n << " elementos):" << endl;
        for (int i = 0; i < n; i++) {
            cout << "Elemento " << i + 1 << ": ";
            cin >> vec[i];
        }

        int rangoInicio, rangoFin;
        cout << "Ingrese el inicio del rango: ";
        cin >> rangoInicio;
        cout << "Ingrese el final del rango: ";
        cin >> rangoFin;

        // Asegurar que el rangoInicio sea menor o igual a rangoFin
        if (rangoInicio > rangoFin) {
            int temp = rangoInicio;
            rangoInicio = rangoFin;
            rangoFin = temp;
        }

        int cantidadEnRango = 0;
        for (int i = 0; i < n; i++) {
            if (vec[i] >= rangoInicio && vec[i] <= rangoFin) {
                cantidadEnRango++;
            }
        }

        // Mostrar el resultado
        cout << "\nCantidad de números en el rango [" << rangoInicio << ", " << rangoFin << "]: " << cantidadEnRango << endl;

        // Preguntar si el usuario quiere continuar o salir
        cout << "\n¿Desea realizar otra operación? (s/n): ";
        cin >> opcion;

    } while (opcion == 's' || opcion == 'S');

    cout << "Programa finalizado.\n";

    return 0;
}
```


## ¡Gracias por leer hasta aquí! Tu apoyo es muy valioso para mí. Si te ha gustado el contenido, no dudes en compartirlo y seguirme en mis redes sociales. ¡Hasta la próxima!👋
