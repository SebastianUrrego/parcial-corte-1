# Punto 1

Este repositorio contiene un script en AWK diseñado para reconocer tokens específicos utilizando un Autómata Finito Determinista (AFD) basado en un conjunto de expresiones regulares. El programa recibe un archivo con tokens a evaluar y devuelve el tipo de token según las reglas definidas.

## Descripción del Problema

El programa está basado en un diagrama de estados de un AFD que acepta las siguientes expresiones regulares:

- `+` → **SUMA**
- `++` → **INCR**
- `[0-9]+` → **ENTERO**
- `([0-9]+)\.([0-9]+)` → **REAL**

El autómata se inicia en el estado 0 y avanza según los caracteres leídos, clasificando las secuencias de caracteres en uno de los siguientes tokens:

- **SUMA**: Representado por el símbolo `+`.
- **INCR**: Representado por el símbolo `++`.
- **ENTERO**: Cualquier secuencia de uno o más dígitos (por ejemplo, `7`).
- **REAL**: Un número con parte entera y decimal separados por un punto (por ejemplo, `4.67`).

## Cómo Ejecutar el Programa

1) Primero dirijase al archivo zip del punto1 (punto1.zip) y descarguelo.
2) Una vez instalado proceda a extraer la carpeta comprimida(la carpeta contiene 2 archivos, uno es el Automata.awk que contiene el procesamiento de patrones y tokens, y el archivo prueba.txt, el cual contiene la entrada a probar).
3) Una vez de haber extraido la carpeta, dirijase a la carpeta de descargas usando el comando en la terminal:
```bash
cd Descargas
```
4) Ahora dirijase a la ruta de la carpeta con el comando:
```bash
cd punto1
```
5) Ahora proceda a poner el siguiente comando:
```bash
awk -f Automata.awk prueba.txt
```
6) Por ultimo le deberia salir lo siguiente en la terminal
```bash
SUMA
INCR
ENTERO
REAL
REAL
```

# Punto 2

Este punto implementa un analizador léxico usando Flex para reconocer la sintaxis de funciones lambda en Python. El objetivo es identificar si una expresión lambda dada es aceptada por la gramática definida.

## Descripción del punto

El programa toma como entrada un archivo de texto que contiene código en Python, específicamente una función lambda, y verifica si la sintaxis corresponde a la estructura esperada.

### Ejemplo de Expresión Lambda

El programa está diseñado para reconocer expresiones lambda en Python como el siguiente ejemplo:

```python
square = lambda x: x ** 2
print(square(3))
```
## Archivos del repositorio

- lambda.l: Contiene la especificación léxica en Flex que define las reglas para identificar la sintaxis de las funciones lambda en Python.
- lambda_checker: El ejecutable resultante tras compilar el código generado por Flex. Este programa realiza el análisis léxico.
- lex.yy.c: El código C generado automáticamente por Flex a partir del archivo lambda.l.
- prueba3.txt: Un archivo de ejemplo que contiene una expresión lambda en Python para ser analizada.

## Requisitos previos

Debes tener Flex y un compilador de C (como gcc) instalados en tu sistema. Puedes instalarlos en Ubuntu utilizando los siguientes comandos:
```bash
sudo apt-get update
sudo apt-get install flex
sudo apt-get install gcc
```

## Ejecucion
1) Primero dirijase al archivo zip del punto2 (punto2.zip) y descarguelo.
2) Una vez instalado proceda a extraer la carpeta comprimida(la carpeta contiene 4 archivos).
3) Una vez de haber extraido la carpeta, dirijase a la carpeta de descargas usando el comando en la terminal:
```bash
cd Descargas
```
4) Ahora dirijase a la ruta de la carpeta con el comando:
```bash
cd punto2
```
5) Genere el código C a partir de la especificación léxica:
```bash
flex lambda.l
```
Esto generará el archivo lex.yy.c.
6) Compilar el código generado:
```bash
gcc lex.yy.c -o lambda_checker -lfl
```
Este comando creará el ejecutable lambda_checker.

7)Para ejecutar el programa con un archivo de entrada que contenga la función lambda, utiliza el siguiente comando:
```bash
./lambda_checker prueba3.txt
```
Con el ejemplo implementado en el archivo .txt le deberia salir ACEPTA.

# Punto 3

Este punto consiste en un programa en lenguaje C que cuenta la cantidad de veces que cada palabra aparece en un archivo de texto. El programa lee un archivo de texto, procesa cada palabra, y muestra el conteo de ocurrencias para cada palabra en la consola.

## Archivos en el Repositorio

- **index.c**: El archivo fuente en C que contiene el código para leer el archivo de texto `listado.txt`, procesar las palabras y contar sus ocurrencias.
- **a.out**: El archivo binario ejecutable generado al compilar `index.c`. Este archivo es el programa que realiza el conteo de palabras.
- **listado.txt**: Un archivo de texto de ejemplo que contiene una lista de palabras. Este archivo es utilizado como entrada por el programa.

### Ejemplo del Contenido de `listado.txt`

El archivo `listado.txt` contiene lo siguiente:

```plaintext
caballo
gato
gato
caballo
koala
gato
koala
```
## Como ejecutar
1) Primero dirijase al archivo zip del punto3 (punto3.zip) y descarguelo.
2) Una vez instalado proceda a extraer la carpeta comprimida(la carpeta contiene 3 archivos).
3) Una vez de haber extraido la carpeta, dirijase a la carpeta de descargas usando el comando en la terminal:
```bash
cd Descargas
```
4) Ahora dirijase a la ruta de la carpeta con el comando:
```bash
cd punto3
```
5) Ingrese el siguiente comando:
```bash
gcc index.c
```
6) Por ultimo ejecute el programa con:
```bash
./a.out listado.txt gato
```
en donde le saldra:
```bash
la palabra "gato" se repitio 3 veces en el texto
```
si usted quiere digamos poner un poema o cualquier otro texto solo tiene que meterse al archivo listado.txt y pegar el texto que quiera, y para ejecutar el ultimo comando cambiando gato por la palabra que quiera ver cuantas veces se repite en su texto:
```bash
./a.out listado.txt 'aquie iria la palabra a probar'
```

# Punto 4
Este punti realiza una comparación de rendimiento entre un lenguaje de programación compilado (C) y un lenguaje de programación interpretado (Python) utilizando el algoritmo de QuickSort. El objetivo es analizar las diferencias en el tiempo de ejecución al ordenar un conjunto de datos usando el mismo algoritmo implementado en ambos lenguajes.

## Archivos en el Repositorio

- **quicksort.c**: Implementación del algoritmo QuickSort en C.
- **quicksort.py**: Implementación del algoritmo QuickSort en Python.
- **a.out**: Archivo binario ejecutable generado al compilar `quicksort.c`.
- **quicksort**: Archivo binario adicional relacionado con la compilación de `quicksort.c`.

## Instrucciones para Compilar y Ejecutar

### Requisitos Previos

Para ejecutar y comparar ambos programas, necesitas:

- Un compilador de C como `gcc`.
- Python instalado en tu sistema (Python 3.x recomendado).

### ejecucion de los programas
1) Primero dirijase al archivo zip del punto4 (punto4.zip) y descarguelo.
2) Una vez instalado proceda a extraer la carpeta comprimida(la carpeta contiene 4 archivos).
3) Una vez de haber extraido la carpeta, dirijase a la carpeta de descargas usando el comando en la terminal:
```bash
cd Descargas
```
4) Ahora dirijase a la ruta de la carpeta con el comando:
```bash
cd punto4
```
4) Dependiendo del programa que quiera correr pondra:
```bash
cd python
cd c
```
5) Los comandos para ejecutar c y python son:
c
```bash
gcc -o quicksort quicksort.c
./quicksort
```

python
```bash
python3 quicksort.py
```
## Conclusiones
se comparó la ejecución del algoritmo Quicksort en C (un lenguaje compilado) y en Python (un lenguaje interpretado), midiendo el tiempo de ejecución en ambos casos. Los resultados muestran que C es más rápido al ejecutar este algoritmo, ofreciendo un mejor rendimiento. Esto se debe a que un compilador traduce el código a lenguaje máquina una sola vez, y cada instrucción se analiza solo una vez, no en cada ejecución. En contraste, un intérprete procesa el código fuente línea por línea y lo traduce a lenguaje máquina cada vez que se ejecuta, lo que implica que se traduce en cada ocasión que se corre el programa.

# Punto 5
Este punto es un programa escrito en Java que utiliza ANTLR para calcular valores trigonométricos (Seno, Coseno, Tangente) a partir de expresiones dadas en un archivo de entrada.

## Estructura del Proyecto

- `Trig.g4`: Archivo de gramática que define la sintaxis de las expresiones trigonométricas (`Sin(x)`, `Cos(x)`, `Tan(x)`).
- `TrigLexer.java`, `TrigParser.java`, `TrigBaseVisitor.java`, `TrigVisitor.java`: Archivos generados por ANTLR a partir de la gramática `Trig.g4`.
- `TrigCalc.java`: Clase principal que carga el archivo de entrada, utiliza el parser para analizar las expresiones y calcula los valores trigonométricos utilizando un visitor.
- `expr.in`: Archivo de entrada que contiene las expresiones trigonométricas a evaluar.

## Requisitos

- **Java Development Kit (JDK)**: Asegúrate de tener instalado JDK (al menos versión 8).
- **ANTLR 4**: Necesitas tener ANTLR 4 instalado y configurado en tu sistema.

## Instalación

1. **Instalar ANTLR**:
   - Puedes descargar ANTLR jar desde [la página oficial](https://www.antlr.org/download.html).
   - Añade el siguiente alias a tu `.bashrc` o `.zshrc`:
     ```bash
     alias antlr4='java -jar /path/to/antlr-4.13.0-complete.jar'
     alias grun='java org.antlr.v4.gui.TestRig'
     ```
   - Recarga el archivo de configuración del shell:
     ```bash
     source ~/.bashrc
     ```
   
2. **Extraer la carpeta**:
   1) Primero dirijase al archivo zip del punto5 (punto5.zip) y descarguelo.
   2) Una vez instalado proceda a extraer la carpeta comprimida.
   3) Una vez de haber extraido la carpeta, dirijase a la carpeta de descargas usando el comando en la terminal:
   ```bash
   cd Descargas
   ```
   4) Ahora dirijase a la ruta de la carpeta con el comando:
   ```bash
   cd punto5
   ```.

3. **Generar Lexer, Parser y Visitor**:
   - Abre una terminal y navega al directorio donde se encuentra `Trig.g4`.
   - Ejecuta el siguiente comando para generar el lexer, parser y visitor:
     ```bash
     antlr4 -visitor Trig.g4
     javac Trig*.java
     ```

4. **Compilar el programa**:
   - Compila la clase principal `TrigCalc.java`:
     ```bash
     javac TrigCalc.java
     ```

## Ejecución

1. **Crear el archivo de entrada**:
   - Crea un archivo llamado `expr.in` con las expresiones trigonométricas que deseas evaluar. Ejemplo:
     ```plaintext
     Sin(90)
     Cos(0)
     Cos(180)
     Sin(45)
     ```

2. **Ejecutar el programa**:
   - Ejecuta el programa utilizando el siguiente comando:
     ```bash
     java TrigCalc expr.in
     ```

   - El programa leerá las expresiones en `expr.in`, calculará los valores trigonométricos en radianes y los imprimirá en la consola.

## Ejemplo de Salida

Dado el archivo `expr.in` mencionado anteriormente, la salida del programa será:

```plaintext
1.0
1.0
-1.0
0.7071067811865475
```
