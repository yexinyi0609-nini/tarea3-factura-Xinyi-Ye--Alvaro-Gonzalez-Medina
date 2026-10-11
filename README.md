# Tarea 3 · La factura bajo el microscopio
Pareja: Xinyi Ye y AAnax · GitHub: yexinyi0609-nini, AAnax
## Reto 1 · Compilar desde la terminal
- Comando usado y resultado (captura: capturas/reto1.png)dir
- ¿Qué es Factura.java? ¿Y Factura.class? ¿Quién ejecuta el .class?

Factura.java es el archivo de código fuente escrito en lenguaje Java que contiene las instrucciones legibles por humanos.

Factura.class es el archivo de bytecode (código intermedio) generado por el compilador(javac) a partir del código fuente.

.class lo ejecuta Java Virtual Machine(JVM).

- ¿Por qué no se ha generado Factura.class la primera vez?

Porque el código contenía errores de compilación, por lo que el compilador se detuvo y no llegó a generar el bytecode.

## Reto 2 · Errores de compilación

|   Nº | Línea | Mensaje de javac | Tipo (léxico / sintaxis / semántica) | Corrección |
| :--- | :---- | :--------------- | :----------------------------------- | :--------- |
|   1  |       |                  |                                      |            |
|   2  |       |                  |                                      |            |
|   3  |       |                  |                                      |            |

Captura del programa funcionando: capturas/reto2.png
## Reto 3 · Depuración del error lógico

| Variable  | Valor esperado | Valor real |
| :-------- | :------------- | :--------- |
| descuento |                |            |
| total     |                |            |

- Línea del error y explicación:
- Corrección:
- Mi propia prueba (producto, precio, cantidad, socio -> total):
Captura del depurador: capturas/reto3.png
## Reto 4 · Reutilización
- Métodos creados y para qué sirve cada uno:
- ¿Qué ventaja tiene frente al código anterior?
## Reto 5 · ¿Qué lenguaje elegirías?
- Caso A (web de la tienda):
- Caso B (propuesta en ensamblador):