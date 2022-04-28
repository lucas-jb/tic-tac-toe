# tic-tac-toe

**Tic tac toe** console game in just 21 lines!

To play we only have to input the number with the position where we want to place our chip.

***
¡**3 en raya** por consola en tan solo 21 lineas!

Para jugar tan solo tendremos que introducir el número que indique la posición donde queramos colocar nuestra ficha.

***

![Table1](https://raw.githubusercontent.com/lucas-jb/tic-tac-toe/main/images/table1.png)

![Table2](https://raw.githubusercontent.com/lucas-jb/tic-tac-toe/main/images/table2.png)

![Table3](https://raw.githubusercontent.com/lucas-jb/tic-tac-toe/main/images/table3.png)

***

```python
import os;clearConsole = lambda: os.system('cls' if os.name in ('nt', 'dos') else 'clear');clearConsole();j1,j2,map,move = "♥","♦",[1,2,3,4,5,6,7,8,9],1 #Variables globales
def comprobar(move, j): #Función para comprobar si el movimiento es válido
    if type(map[move-1]) == int: map[move-1] = j 
    else:print("Posición ocupada");move=int(input());comprobar(move, j) 
def win(player): #Función para verificar si hay un ganador
    if map[0] == map[4] == map[8] == player: return fin_juego("Gana " + player)
    elif map[2] == map[4] == map[6] == player: return fin_juego("Gana " + player)
    for i in [0,1,2]: #Comprobamos las filas
        if map[3*i] == map[3*i+1] == map[3*i+2] == player: return fin_juego("Gana " + player)
        elif map[i] == map[i+3] == map[i+6] == player: return fin_juego("Gana " + player)
        elif all(type(x) != int for x in map): fin_juego("Empate")
    return False
def printear_tablero(): print("[ " + str(map[0]) + " ]"+ "[ " + str(map[1]) + " ]"+ "[ " + str(map[2]) + " ]"+"\n"+"[ " + str(map[3]) + " ]"+"[ " + str(map[4]) + " ]"+"[ " + str(map[5]) + " ]"+"\n"+"[ " + str(map[6]) + " ]"+"[ " + str(map[7]) + " ]"+"[ " + str(map[8]) + " ]") #Función para imprimir el tablero
def fin_juego(msg):print(msg);return True #Función para terminar el juego
if __name__ == '__main__': 
    fin=False;printear_tablero() 
    while not fin:
        for i in [j1,j2]:
            print("Jugador "+str(i)+" selecciona una posición: ");move = int(input());comprobar(move, i);clearConsole();printear_tablero() 
            if win(i):fin=True;break
    print("Fin del juego") #by lucas-jb
```
