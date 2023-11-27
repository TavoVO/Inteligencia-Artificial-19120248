# Contar Número de Islas

Del giguiente arreglo, debemos de encontrar las islas que las podemos ver diferenciasdas por 1's

~~~python3
import numpy as np
   
mapa = [
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 1 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 1 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 1 , 0 , 0 , 1 , 1 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 1 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
      ]
~~~

En esta parte definimos la función y dos varibles, una para contar las islas y otra para las posiciones que ya habiamos visitado.

~~~python3
def contador_islas(mapa):
    cont = 0
    visitados = set()
~~~

Con estas dos lineas, con los ciclos for recorremos el arreglo y pasar por cada uno de los puntos:

~~~python
for i in range(len(mapa)):
    for j in range(len(mapa[0])):
~~~

Se checa que la celda donde nos encontramos no la hayamos visitado ya y el and para que si la celda tiene el valor de 1

~~~python
if (i, j) not in visitados and mapa[i][j] == 1:
~~~

si, si se cumple con la condición el contador se suma uno, por la isla que encontro, en la variable de pila se usa para hacer unrecorrido más espceializado desde la celda en la que estamos, explorando las celdas horizontalmente y verticalmente. Luego se actualiza la variable de visitados con las celdas que se recorrieron.

~~~python
cont += 1
pila = [(i, j)]
while pila:
    x, y = pila.pop() #elimina la cooredeanda
    visitados.add((x, y)) #añade la coordenada a visitados
~~~

itera sobre las direcciones (dx, dy) que corresponden a las cuatro posibles direcciones adyacentes: derecha, izquierda, arriba y abajo.

~~~python
    for dx, dy in [(0, 1), (0, -1), (1, 0), (-1, 0)]: 
~~~

Calcula las nuevas coordenadas (nx, ny) basadas en la dirección actual (dx, dy).

~~~python
        nx, ny = x + dx, y + dy
~~~

Esta condición verifica si las nuevas coordenadas (nx, ny) están dentro de los límites del mapa, si no han sido visitadas previamente, y si el valor en el mapa en esas coordenadas es 1

~~~python
        if 0 <= nx < len(mapa) and 0 <= ny < len(mapa[0]) and (nx, ny) not in visitados and mapa[nx][ny] == 1:
~~~

Si la condición anterior es verdadera, se añaden las nuevas coordenadas a la pila stack para que sean exploradas en la siguiente iteración del bucle while.

~~~python
            pila.append((nx, ny))

~~~

Al final la función retorna el núemro de islas encontradas y al final imprimimos el numero total de islas

~~~python
        return count
print(contador_islas(mapa))
~~~

El resultado nos arroja que son 6 Islas en total

~~~python
PS C:\Users\ocvio\Documents\PrgrPython\ProLog> & C:/Users/ocvio/AppData/Local/Programs/Python/Python310/python.exe c:/Users/ocvio/Documents/PrgrPython/ProLog/P1-Nusqueda-de-Islas.py
6
~~~

El codigo completo:

~~~python
import numpy as np
#       1   2   3   4   5   6   7   8   9  10  11  12  13
mapa = [[0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 1 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 1 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 0 , 0 , 0 , 1 , 0 , 0],
       [0 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 1 , 0 , 0 , 1 , 1 , 0],
       [0 , 0 , 0 , 0 , 1 , 1 , 1 , 1 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
       [0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 0],
      ]
def contador_islas(mapa):
    count = 0
    visited = set()
    for i in range(len(mapa)):
        for j in range(len(mapa[0])):
            if (i, j) not in visited and mapa[i][j] == 1:
                count += 1
                stack = [(i, j)]
                while stack:
                    x, y = stack.pop()
                    visited.add((x, y))
                    for dx, dy in [(0, 1), (0, -1), (1, 0), (-1, 0)]:
                        nx, ny = x + dx, y + dy
                        if 0 <= nx < len(mapa) and 0 <= ny < len(mapa[0]) and (nx, ny) not in visited and mapa[nx][ny] == 1:
                            stack.append((nx, ny))
    
    return count

print(contador_islas(mapa))
~~~
