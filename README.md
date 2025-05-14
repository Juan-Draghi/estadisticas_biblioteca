# Análisis de Datos de Gestión Bibliotecaria con Python en Google Colab

Este repositorio contiene un cuaderno de Google Colab (`Datos_estadísticas_Biblioteca_CPAU.ipynb`) diseñado para automatizar y agilizar el análisis de varios conjuntos de datos relacionados con las operaciones y servicios de una biblioteca, utilizando scripts de Python y la biblioteca `pandas`.

El cuaderno permite cargar planillas de cálculo (generadas a partir de sistemas o formularios) directamente desde tu ordenador en el entorno de Google Colab, realizar análisis específicos y mostrar los resultados en formato tabular.

## Propósito

El objetivo principal es transformar datos brutos de operaciones bibliotecarias en resúmenes informativos que ayuden a comprender patrones, medir actividades y respaldar la toma de decisiones, mejorando la eficiencia del trabajo recurrente.

## Análisis Incluidos

El cuaderno está dividido en varias secciones, cada una dedicada al análisis de un tipo específico de datos:

1.  **Análisis de Consultas Generales:**
    * Analiza datos de consultas registradas (ej. desde un formulario).
    * Permite filtrar los datos por un mes específico.
    * Genera un resumen que incluye: conteo por tipo de usuario, medio de consulta, sala de lectura, referencia; sumatoria de servicios de digitalización y venta; conteo específico de "Reclamos" en uso de colección.
    * 
2.  **Análisis de Comunicaciones:**
    * Analiza datos de actividades de comunicación (newsletters, posteos en redes, etc.).
    * Permite filtrar los datos por un mes específico.
    * Calcula la sumatoria de la cantidad de actividades por cada categoría (correos, noticias, boletines, posteos por red social, sitio web) para el mes seleccionado.
      
3.  **Análisis de Circulación (Préstamos):**
    * Calcula la sumatoria de préstamos por destino, discriminada por nivel bibliográfico (Monografías/Revistas).
    * Genera un conteo de préstamos por destino para cada título de revista.
      
4.  **Análisis de Temas Consultados (CDU):**
    * Procesa datos de consultas por clasificación CDU.
    * Suma la cantidad de obras por código CDU principal (ignorando auxiliares entre paréntesis).
    * Ordena los temas por cantidad de ocurrencias de mayor a menor.
    * Presenta una tabla con el Top 10 de temas más consultados, mapeando el código CDU a un nombre usando un diccionario interno.

## Requisitos

* Una cuenta de Google para acceder y ejecutar Google Colab.
* Los archivos de datos exportados en formato de hoja de cálculo (`.xlsx` es el formato principal esperado por los scripts, aunque `.csv` podría funcionar en algunos casos si se ajusta `pd.read_csv`).
* **Importante:** Los archivos de datos deben contener las columnas con los **nombres exactos** que se especifican en la sección "Archivos de Datos Esperados".

## Archivos de Datos Esperados

Para cada sección de análisis, el script solicitará la carga de un archivo específico. Asegúrate de que tus archivos contengan las siguientes columnas con estos nombres exactos:

* **Para Análisis de Circulación:**
    * `Destino`
    * `Nivel bibliográfico`
    * `Título`
    * `Autor Principal`
      
* **Para Análisis de Temas Consultados (CDU):**
    * `TOTAL` (cantidad de obras)
    * `MATERIA` (clasificación CDU)
      
* **Para Análisis de Consultas Generales:**
    * `Marca temporal` (fecha y hora)
    * `Tipo de usuario`
    * `Medio de consulta`
    * `Sala de lectura`
    * `Referencia`
    * `Servicios de digitalización internos`
    * `Venta de publicaciones y merchandising`
    * `Uso de la colección`
    * *(La columna 'Número de matrícula' no es requerida por el script de análisis).*
      
* **Para Análisis de Comunicaciones:**
    * `Marca temporal` (fecha y hora)
    * `Cantidad de correos enviados`
    * `Noticias`
    * `Boletín`
    * `Sitio web`
    * `Posteos en Facebook`
    * `Posteos en Instagram`
    * `Posteos en Twitter`
    * `Posteos en YouTube`
    * `Posteos en Issuu`

## Cómo Usar el Cuaderno

1.  **Descargar:** Clona este repositorio o descarga el archivo `Datos_estadísticas_Biblioteca_CPAU.ipynb`.
2.  **Abrir en Colab:** Ve a [Google Colab](https://colab.research.google.com/) y abre el cuaderno descargado (`Archivo > Subir cuaderno`).
3.  **Ejecutar Celdas:** Recorre el cuaderno ejecutando cada celda de código secuencialmente.
4.  **Cargar Archivos:** Cuando cada sección de análisis te lo solicite (verás un mensaje pidiendo "subir el archivo...") utiliza la interfaz de carga de archivos de Colab para seleccionar el archivo de hoja de cálculo correspondiente desde tu ordenador.
5.  **Ingresar Datos:** Para los análisis de Consultas y Comunicaciones, el script te pedirá que ingreses el número del mes (1-12) que deseas analizar. Escribe el número en la caja de entrada que aparece y presiona Enter.
6.  **Ver Resultados:** Los resultados del análisis (tablas, sumatorias, conteos) se mostrarán directamente en la salida de la celda de código correspondiente dentro del cuaderno de Colab.

Puedes ejecutar las secciones de análisis de Temas Consultados, Consultas y Comunicaciones múltiples veces (subiendo diferentes archivos o seleccionando diferentes meses) para obtener resultados comparativos.

## Diccionario CDU

El análisis de Temas Consultados (CDU) utiliza un diccionario de mapeo (`temas_CDU`) incrustado directamente en la celda de código correspondiente. Si necesitas actualizar los nombres de los temas o añadir nuevos códigos CDU, deberás editar este diccionario dentro del código de la celda.

## Salida

Los resultados de cada análisis se imprimen en la salida de la celda de Colab en un formato tabular o de resumen fácil de leer, utilizando las opciones de visualización de `pandas` para mostrar los datos completos.

## Agradecimientos

Este cuaderno fue desarrollado por Juan Draghi con la asistencia de Gemini (Google AI).
