# tic-tac-toe

**Tic tac toe** console game in just 21 lines!

To play we only have to input the number with the position where we want to place our chip.

![](/docs/demo.gif)

# Code
```python
import os;clearConsole = lambda: os.system('cls' if os.name in ('nt', 'dos') else 'clear');clearConsole();j1,j2,map,move = "♥","♦",[1,2,3,4,5,6,7,8,9],1
def comprobar(move, j):
    if type(map[move-1]) == int: map[move-1] = j 
    else:print("Position held");move=int(input());comprobar(move, j) 
def win(player):
    if map[0] == map[4] == map[8] == player: return fin_juego(player + " wins!")
    elif map[2] == map[4] == map[6] == player: return fin_juego(player + " wins!")
    for i in [0,1,2]:
        if map[3*i] == map[3*i+1] == map[3*i+2] == player: return fin_juego(player + " wins!")
        elif map[i] == map[i+3] == map[i+6] == player: return fin_juego(player + " wins!")
        elif all(type(x) != int for x in map): fin_juego("Draw")
    return False
def printear_tablero(): print("[ " + str(map[0]) + " ]"+ "[ " + str(map[1]) + " ]"+ "[ " + str(map[2]) + " ]"+"\n"+"[ " + str(map[3]) + " ]"+"[ " + str(map[4]) + " ]"+"[ " + str(map[5]) + " ]"+"\n"+"[ " + str(map[6]) + " ]"+"[ " + str(map[7]) + " ]"+"[ " + str(map[8]) + " ]")
def fin_juego(msg):print(msg);return True
if __name__ == '__main__': 
    fin=False;printear_tablero() 
    while not fin:
        for i in [j1,j2]:
            print("Player "+str(i)+" select a position: ");move = int(input());comprobar(move, i);clearConsole();printear_tablero() 
            if win(i):fin=True;break
    print("End of the game") #by lucas-jb
```
