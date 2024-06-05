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

```

```

- 3. Diseñe un programa en C/C++ que muestre el número menor y la cantidad de veces que se
repite dentro de un vector de n posiciones, siendo n una variable ingresada por el usuario

```

```

- 4. Diseñe un programa en C/C++ que dado 2 vectores de n posiciones, siendo n una variable
ingresada por el usuario, validar que los 2 vectores tengan igual tamaño, ordene de forma
creciente el primer vector, decreciente el segundo vector y en el tercer vector muestre la
suma del primero con el segundo.

```

```

- 5. Diseñe un programa en C/C++ que dado un vector de n posiciones, siendo n una variable
ingresada por el usuario, calcule el promedio de los datos ingresados y muestre cuales son
mayores

```

```

- 6. Diseñe un programa en C/C++ que dado 2 vector de n posiciones, siendo n una variable
ingresada por el usuario, multiplique el primer vector por el segundo vector y lo guarde en
un tercer vector de la siguiente manera:
  - **Primer vector** [5, 2, 8, 7, 9]
  - **Segundo vector** [23, 45, 2, 6]
  - **tercer vector** [(5*23)+(5*45)+(5*2)+(5*6)][xxx][xxx][xxx]

```

```

- 7. Diseñe un programa en C/C++ que dado un vector de n cantidad de posiciones, siendo n un variable
ingresada por el usuario, guardar en un segundo vector los datos pero de forma inversa es decir:
  - **A.** [5, 2, 8, 7, 9]
  - **B.** [9, 7, 8, 2, 5]

```

```

- 8. Diseñe un programa en C/C++ que dado 2 vectores de n cantidad de posiciones, siendo n variable
ingresada por el usuario, validar que los 2 vectores tengan igual tamaño, guardar en un tercer vector
los datos comunes entre los 2 vectores, que se encuentran tanto en el primero vector como en el
segundo vector, es decir :
  - **A.** [`24`, 55, 6, 15, 90]
  - **B.** [45, `15`, 66, 34, 24]
  - **C.** [24, 15]

```

```

- 9. Diseñe un programa en C/C++ que me permita saber cuántos los números positivos, negativos y ceros
en vector de n posiciones, siendo n una variable ingresada por el usuario.

```

```

- 10. Diseñe un programa en C/C++ que me permita saber cuántos números hay en un rango dado por el
usuario, en un vector de n posiciones siendo n una variable ingresada por el usuario.

```

```


## ¡Gracias por leer hasta aquí! Tu apoyo es muy valioso para mí. Si te ha gustado el contenido, no dudes en compartirlo y seguirme en mis redes sociales. ¡Hasta la próxima!👋
