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
|   1  |   15  | illegal character: '#' | léxico | precio# --> precio |
|   2  |   17  | ';' expected | sintáctico | añadir ";" al final de sc.nextInt() |
|   3  |   29  | incompatible types: possible lossy conversion from double to int | semántico | int total --> double total |

Captura del programa funcionando: capturas/reto2.png

Cálculo a mano (precio 60, cantidad 2, socio):

- Base: 60 × 2 = 120 €
- Descuento: 10 % por superar 100 € (12 €) + 5 % por ser socio (6 €) = 18 €
- Total: (120 − 18) × 1,21 = 102 × 1,21 = **123,42 €**

El programa da 137,94 € porque solo resta 6 € de descuento: (120 − 6) × 1,21 = 137,94 €. Hay un error lógico que se depura en el reto 3.

## Reto 3 · Depuración del error lógico

| Variable  | Valor esperado | Valor real |
| :-------- | :------------- | :--------- |
| descuento | 18,00 €        | 6,00 €     |
| total     | 123,42 €       | 137,94 €   |

- Línea del error y explicación: línea 27, `descuento = base * 0.05;`. Con el depurador (punto de ruptura en la línea 23, datos 60, 2 y s) se ve que `descuento` vale 0.0 al principio, 12.0 después del primer `if` (correcto) y 6.0 después del segundo. El `=` sustituye el descuento del 10 % por el del socio en lugar de sumarlos, así que se pierden los 12 €.
- Corrección: `descuento = descuento + base * 0.05;`. Comprobado con 60, 2 y s: Descuento 18,00 € y Total con IVA 123,42 €.
- Mi propia prueba (producto, precio, cantidad, socio -> total): Ratón inalámbrico, 40, 2, s -> 91,96 €. La base es 80 €, no supera 100 € y solo se aplica el 5 % de socio (4 €): (80 − 4) × 1,21 = 91,96 €. Coincide con el cálculo a mano.
Captura del depurador: capturas/reto3.png

## Reto 4 · Reutilización
- Métodos creados y para qué sirve cada uno:

calcularDescuento(double base, boolean socio) --> calcular el descuento según la base(precio sin descuento y si IVA) y si es socio.
aplicarIVA(double importe) --> aplica 21% de IVA al dinero restado con descuento, dando así el final total de dinero.

- ¿Qué ventaja tiene frente al código anterior?

El código queda más limpio ordenado con el método main y es más fácil de modificar si cambia la regla de descuento o el %IVA, ya que solo hay que cambiar el método correspondiente sin tocar los de más códigos. Además, al cambiar la variable 'socio' a tipo 'bolean',la condición son más limpia, directa y aparecen menos eerores de texto.

## Reto 5 · ¿Qué lenguaje elegirías?
- Caso A (web de la tienda):
- Caso B (propuesta en ensamblador):
