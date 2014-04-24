PROCESO
    SI
    FINSI
    REPETIR
    HASTAQUE
FINPROCESO

1) Adivina un número 
Dos personas la primera piensa un número y la segunda intenta adivinarlo, cada vez que la segunda dice un número la primera le da una pista si el número que dijo es más alto o más bajo que el número que pensó. Plantear un algoritmo para resolverlo. 
(Variación: frio, caliente, si el número se encuentra más lejos o más cerca que el número dicho anteriormente,templado si está a la misma distancia )
PROCESO Adivina un numero
    - Obtener el numero de la primera persona y guardarlo como dato

    REPETIR
        - Preguntar a la segunda persona que elija un numero e intente adivinar
        SI El numero ingresado es menor al guardado
            - Mostrar un mensaje informado que el numero que se intenta adivinar es mayor
        FINSI
        SI El numero ingresado es mayor al guardado
            - Mostrar un mensaje informado que el numero que se intenta adivinar es menor
        FINSI
        SI El numero ingresado es igual al guardado
            - Mostrar un mensaje informado que el numero fue adivinado
        FINSI
        
    HASTAQUE El numero ingresado sea igual al guardado
FINPROCESO


2)Acertar el blanco 
Un cañón dispara a un objetivo, el cañón puede graduar el angulo de disparo, quien dispara posee unos binoculares que le permiten ver donde cae la bala. Plantear un algoritmo para dar en el blanco.
PROCESO Acertar al blanco
    SETUP
    - Posicionar el blanco aleatoriamente y obtener su posicion

    REPETIR
        - Preguntar al tirador el angulo de disparo
        - Calcular la posicion de impacto de la bala
        SI La posicion de impacto coincide con la posicion del blanco
            - Mostrar un mensaje informado que ha dado en el blanco
        ELSE
            - Calcular la distancia al blanco e informarla para futuras decisiones
            - Llamar recursivamente a Acertar Blanco reduciendo o aumentando el angulo de tiro dependiendo de la distancia calculada
        FINSI
        
    HASTAQUE La bala de cañon colisione con el blanco
FINPROCESO

3)Tres en línea (en ingles tic tac toe).
Un algoritmo para jugar y si es posible, ganar siempre.
Asumiendo la perspectiva del jugador que comienza la ronda
PROCESO Ganar al tic tac toe
    SETUP
    - Hacer una matriz vacia BOARD de 3x3 asumiendo que la primer casilla arriba a la izquierda es m[0,0] entiendase m[FILA, COLUMNA]
    - Hacer una variable bandera TURN que pueda tomar dos valores P1 o P2 indicando de quien es el turno, toma por defecto el valor del jugador que comienza (P1) 
    - Guardar un historial de acciones HIS, que contenga Jugador y Casilla eleigda

    REPETIR
        SI TURN es igual a P1
            SI El tamaño de HIS es cero
                // [ , , ]
                // [ ,X, ]
                // [ , , ]
                Ocupar la casilla central BOARD[1,1]
            ELSE EL tamaño del HIS es > 2
                - Revisar la primer jugada del oponente, en este caso HIS[1]
                SI la celda seleccionada es adyacente, checkear si tiene 1 como valor de fila o culumna
                    // [ , ,_]
                    // [O,X, ]
                    // [ , ,_]
                    - Elegir ocupar una celda perpendicular en la columna opuesta, ej si la columna es 0 optar por la columna 2 y la fila puede se cualquiera mientras que no sea 1
                ELSE La celda seleccionada es perpendicular
                    // [ , ,_]
                    // [ ,X, ]
                    // [O, , ]
                    - Elegir la celda opuesta, que tenga columna y fila distinta a HIS[1].celda y que tenga filas y columnas didistintas de HIS[0].celda o sea distinto de 1 para ambos valores, por ejemplo en caso de HIS[1].celda = [2,0] la respuesta deberia ser BOARD[0,2]
                FINSI
            FINSI
        ELSE
            Preguntar a P2 la casilla elegida y checkear que no este ocupada en BOARD o volver a preguntar 
        FINSI

            
        - Guardar la accion en el HIS
        SI Hay 3 en linea
            - Mostrar un mensaje informado que el juego ha terminado y que el jugador activo es el ganador
        FINSI
        
    HASTAQUE Alguno de los jugadores consiga posicionar 3 en linea
FINPROCESO

4)La batalla naval
El juego de la batalla naval, ¿se puede aplicar un algoritmo para jugar? Antes de escribir un algoritmo, plantear una estrategia.

5)Algoritmo para resolver sopa de letras.
Antes de resolver el algoritmo plantear una estrategia.
