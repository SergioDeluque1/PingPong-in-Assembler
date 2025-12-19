# Ping Pong - Proyecto Nand2Tetris

Proyecto desarrollado para el curso de **Organización de Computadores - S2566-1045**.

## Autores

- **Felipe Giraldo Neiva**
- **Sergio DeLúquez Gonzalez**

## Requisitos Previos

+  Java Runtime Environment (JRE)

+  Software Suite Nand2Tetris (Desktop Version) ó
+  Nand2Tetris Web IDE   

## Compilación y Ejecución

 **IMPORTANTE:** 
   - No cambies los nombres de las carpetas o archivos
   - No muevas archivos de lugar
   - Mantén la estructura original del ZIP
   
### Web IDE

   1. sube la carpeta al IDE web
   2. habilita recibir entrada de teclado
   3. habilita mostrar pantalla
   4. corre el archivo principal (Main.jack)

## Controles del Juego

### Jugador 1 (Paleta Izquierda):
- **Q** - Mover paleta hacia arriba
- **A** - Mover paleta hacia abajo

### Jugador 2 (Paleta Derecha):
- **P** - Mover paleta hacia arriba
- **L** - Mover paleta hacia abajo


### Características
- **Rebotes:** La pelota rebota en las paredes superior e inferior
- **Colisiones:** La pelota rebota en las paletas de los jugadores
- **Puntuación:** Se actualiza automáticamente cuando alguien anota
- **Aceleración:** La pelota aumenta su velocidad horizontal cada vez que rebota con una paleta (sin límite)
- **Dirección inteligente:** Después de un gol, la pelota se reinicia apuntando hacia el jugador que perdió el punto

## Clases del Proyecto

### Main.jack
- Punto de entrada del programa
- Crea una instancia de `Game` y ejecuta el bucle principal

### Game.jack
- Controla el ciclo principal del juego
- Maneja la inicialización, actualización y renderizado
- Detecta colisiones y goles
- Coordina todos los elementos del juego

### Ball.jack
- Representa la pelota
- Maneja movimiento, rebotes y velocidad
- Aumenta velocidad progresivamente con cada rebote

### Paddle.jack
- Representa las paletas de los jugadores
- Maneja movimiento vertical
- Detecta colisiones con la pelota

### ScoreBoard.jack
- Maneja el sistema de puntuación
- Muestra el marcador en pantalla
- Actualiza puntuaciones cuando hay goles

### Características Implementadas para la Rúbrica

- Dos jugadores (uno en cada lado)
- Movimiento de paletas
- Sistema de colisiones completo
- Sistema de puntuación
- Detección de ganador (3 goles)
- Funcionamiento correcto en el emulador Jack
- Sin errores de ejecución
- Código bien documentado y comentado

## Créditos

- Basado en el curso Nand2Tetris de Noam Nisan y Shimon Schocken
- Implementación del juego Ping Pong en lenguaje Jack


