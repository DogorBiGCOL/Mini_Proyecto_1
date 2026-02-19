Este script de Python tiene como objetivo generar un conjunto de datos aleatorios con operaciones matemáticas y guardarlo en un archivo CSV.

Aquí está el desglose paso a paso de lo que hace el código:

1.  **Importación de Librerías:**
    *   `pandas`: Used para manipular y estructurar los datos (DataFrame).
    *   `random`: Used para generar números y elecciones aleatorias.
    *   `os`: Used para interactuar con el sistema operativo (crear carpetas).

2.  **Definición de Operaciones:**
    *   Se crea un diccionario `operations` con las claves 'SUM' (Suma), 'SUB' (Resta), 'MUL' (Multiplicación), 'DIV' (División), y 'POW' (Potencia).

3.  **Generación de Datos:**
    *   Se inicia un bucle que se repite 1000 veces (`for _ in range(1000)`).
    *   En cada iteración:
        *   Se elige una **operación** al azar.
        *   Se genera el **primer operando** (`operand_1`) entre 1 y 1000.
        *   Se genera el **segundo operando** (`operand_2`):
            *   Si la operación es **Potencia ('POW')**, el segundo número se limita entre 1 y 10 para evitar resultados excesivamente grandes.
            *   Para el resto de operaciones, es un número entre 1 y 1000.
        *   Se guardan estos tres valores (operación, op1, op2) en una lista.

4.  **Creación del DataFrame:**
    *   Se convierten los datos recolectados en una tabla estructurada (DataFrame de pandas) con las columnas: 'operation', 'operand_1', 'operand_2'.

5.  **Guardado del Archivo:**
    *   Se define la carpeta de salida `./data`.
    *   **Verificación de Carpeta:** El código comprueba si la carpeta `./data` existe. Si no existe, la crea (`os.makedirs`). Esto evita errores al guardar.
    *   Finalmente, guarda el DataFrame como un archivo CSV llamado `math_operations.csv` dentro de esa carpeta, sin incluir el índice de filas.
