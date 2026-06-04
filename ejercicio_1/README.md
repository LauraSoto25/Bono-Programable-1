# Ejercicio 1: Calculadora de Factoriales y Permutaciones

[![View Notebook](https://img.shields.io/static/v1?label=&message=View%20Notebook&color=pink&style=flat-square&logo=github)](https://github.com/LauraSoto25/Bono-Programable-1/blob/main/ejercicio_1/Ejercicio_1.ipynb)

>  Toda la fundamentación matemática (títulos, fórmulas, descripciones teóricas y conclusiones de rendimiento) está documentada al detalle dentro de este cuaderno interactivo. Puede revisarlo directamente aquí en GitHub haciendo clic en el botón de **"View Notebook"** de arriba; si desea ejecutar el código, la plataforma le habilitará la opción de abrirlo en el entorno de Google Colab.

## Resumen del ejercicio

Este ejercicio está dividido en dos partes principales:
1. **La Calculadora:** Un menú interactivo que procesa tanto el factorial puro de un número ($n!$) como la fórmula de permutaciones $P(n, r) = \frac{n!}{(n-r)!}$, validando de forma estricta las entradas para evitar errores matemáticos, números negativos o el ingreso de letras.
2. **La Comparativa:** Una prueba de eficiencia que calcula el tiempo exacto en microsegundos de dos enfoques (iterativo vs. recursivo), demostrando de forma práctica las ventajas de optimizar el uso de la memoria en Python ante números grandes.

---

## Instrucciones de Ejecución en Google Colab

El código de este ejercicio está estructurado en módulos independientes dentro del cuaderno `Ejercicio_1.ipynb`. Para ejecutar la aplicación correctamente, siga estos pasos:

1. Dé clic en el botón **Open In Colab** ubicado en la parte superior de esta portada.
2. Una vez abra el entorno de Colab, vaya a la sección **`4. Codigo Funcional`**.
3. Ejecute primero el bloque de celdas bajo el subtítulo **`Funciones`** (esto cargará los motores matemáticos, validaciones y librerías `time` y `sys` en la memoria del entorno).
4. Posteriormente, ejecute la celda bajo el subtítulo **`Programa Principal`** (la cual invoca la función maestra `calculadora()`).
5. Interactúe con el menú numérico (opciones 0 a 5) directamente desde la consola interactiva que se desplegará en la parte inferior de la celda.

---

## Estructura de este Módulo en GitHub

* `Ejercicio_1.ipynb`: Cuaderno de desarrollo completo con el reporte y el código segmentado en bloques.
* `evidencias/`: Carpeta que almacena las capturas de pantalla del programa en ejecución para la verificación del laboratorio.

---

## Evidencias de Pruebas Ejecutadas

Para demostrar la estabilidad del programa y comprobar los casos obligatorios del laboratorio, se realizaron las siguientes pruebas en la consola de Colab:

### Prueba 1: $P(10, 3)$
* **Entrada:** Opción 2 | $n = 10, r = 3$
* **Resultado:** `720`
![Evidencia de la Prueba 1](evidencias/prueba1.png)

### Prueba 2: $P(20, 5)$
* **Entrada:** Opción 2 | $n = 20, r = 5$
* **Resultado:** `1860480`
![Evidencia de la Prueba 2](evidencias/prueba2.png)

### Prueba 3: $P(5, 5)$
* **Entrada:** Opción 2 | $n = 5, r = 5$
* **Resultado:** `120` *(Demuestra que $P(5,5)$ equivale al factorial puro $5!$, ya que el denominador se convierte en $0! = 1$)*.
![Evidencia de la Prueba 3](evidencias/prueba3.png)

### Prueba 4: $P(8, 0)$
* **Entrada:** Opción 2 | $n = 8, r = 0$
* **Resultado:** `1` *(Validación correcta: solo hay una forma de ordenar cero objetos)*.
![Evidencia de la Prueba 4](evidencias/prueba4.png)

### Prueba 5: $P(1, 1)$
* **Entrada:** Opción 2 | $n = 1, r = 1$
* **Resultado:** `1`
![Evidencia de la Prueba 5](evidencias/prueba5.png)

---

## Control de Errores y Validaciones
El código está blindado para evitar caídas o errores en la terminal mediante dos filtros principales:
* **Evita datos inválidos:** Si se ingresan letras o caracteres invalidos, el programa detecta el error y pide ingresar el número otra vez.
* **Control matemático:** Detecta valores negativos y combinaciones imposibles (como intentar sacar un subgrupo $r$ que sea mayor al total $n$).
