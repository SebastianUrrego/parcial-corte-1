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
