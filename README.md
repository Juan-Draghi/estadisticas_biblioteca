# Análisis de Datos de Gestión Bibliotecaria con Python en Google Colab

Este repositorio contiene un cuaderno de Google Colab diseñado para automatizar y agilizar el análisis de varios conjuntos de datos relacionados con las operaciones y servicios de la Biblioteca CPAU, utilizando scripts de Python y la biblioteca `pandas`.

El cuaderno permite cargar planillas de cálculo (generadas a partir de sistemas o formularios) en el entorno de Google Colab, realizar análisis específicos y mostrar los resultados en formato tabular.

## Propósito

El objetivo principal es transformar datos brutos de operaciones bibliotecarias en resúmenes informativos que ayuden a comprender patrones, medir actividades y respaldar la toma de decisiones, mejorando la eficiencia del trabajo recurrente.

## Análisis Incluidos

El cuaderno está dividido en varias secciones, cada una dedicada al análisis de un tipo específico de datos:

1.  **Análisis de Consultas Generales:**
    * Analiza datos de consultas registradas (ej. desde un formulario).
    * Permite filtrar los datos por un mes específico.
    * Genera un resumen que incluye: conteo por tipo de usuario, medio de consulta, sala de lectura, referencia; sumatoria de servicios de digitalización y venta; conteo específico de "Reclamos" en uso de colección.
      
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

## Autor

Juan Draghi - Biblioteca del Consejo Profesional de Arquitectura y Urbanismo
