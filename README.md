# Tetris-POO
**Nombre**: Juan José Rodríguez Moreno **Fecha**: 8 / 11 / 2020 
Proyecto N° 2 
## Objetivo
Este segundo proyecto tiene como propósito aplicar lo aprendido del concepto de Programación Orientada a Objetos (POO), con la particularidad, de continuar la temática de usar polyominos para así establecer diferencias y semejanzas con la programación estructurada.
## Descripción del juego
El juego está hecho a partir de las reglas del [tetris](https://es.wikipedia.org/wiki/Tetris) hecho a base de Processing con lenguaje de Java.
## Descripción del código

Clases:

1. Tablero: Es una matriz que contiene los espacios utilizados por las piezas, sus métodos permiten saber cuando las lineas están completas y nos dice cuantas son, ademas de que nos da el valor de cada uno de los espacios si esta lleno o vacío, para determinar si una pieza puede ocupar esa posición.
```
public void draw(){
    for (int x=0;x<=gridWidth-1;x++){
      for (int y=0;y<=gridHeight-1;y++){
        if(grid[y][x]<=6){
          stroke(255);
          fill(colors[grid[y][x]]);
          rect(block*x,block*y,block,block);
        }
        else{
          stroke(0);
          fill(colors[7]);
          rect(block*x,block*y,block,block);
        }
      }
    }
  }
```
En esta función se contruye la cuadricula donde se juega. 
2. Marcador: Contiene los datos de puntuación, nivel y las lineas que llevamos, sus métodos son muy sencillos ya que solo incrementan los contadores.

3. Pieza: Esta clase es la que contiene la forma que tendrá cada figura y sus rotaciones posibles, contiene los métodos para girar la pieza y moverla dentro del tablero.
```
  void draw(){
    stroke(255);
    fill(colors[type]);
    for (int x=0;x<=4;x++){
      for (int y=0;y<=4;y++){
        if(form[type][rot][y][x]!=0){
          stroke(255);
          fill(colors[type]);
          rect(pX+block*x,pY+block*y,block,block);
        }
```        
4. Juego: Esta es la clase que determina las acciones que se pueden realizar, restringe los movimientos de las piezas en el tablero, actualiza los valores del tablero y los valores del marcador; esta clase lleva como parámetros las 3 clases anteriores ya que interactua directamente con sus propiedades y métodos.

Todas las clases cuentan con el método draw() que dibuja en pantalla y restart() para reiniciar los valores cuando inicia un juego nuevo.

## Características del juego
- Con las flechas de izquierda tanto derecha dirigen al tetramino según el jugador desee, con la ayuda de la funcón keyReleased.
- Con flecha de arriba se rota la figura y con la de abajo se acelera la caida.
- Cuando pierde el jugador, es decir, después de que no le quede espacio de poner tetrominos, puede comenzar de nuevo con la tecla R.

## Conclusiones 

- La programación orientada a objetos facilita mucho el trabajo para la interacciones que tienen los diferentes tetraminos con si mismos y con la cuadrícula, a diferencia de la programción estructurada.
- No utilice herencias ni polimorfismos ya que en mi opinión no se necesitaban para las diferentes relaciones entre el tetramino y la cuadricula, aplicando una misma jerarquia de clases.


