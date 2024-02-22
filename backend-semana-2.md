# Tareas para la semana del 26 de febrero

Después de la clase de teoría del 21 de febrero, habéis adquirido los conocimientos necesarios (temas 2 y 3) para implementar la capa Modelo y las pruebas automatizadas de los servicios locales (capa Lógica de Negocio).

Para la semana del 26 de febrero, os aconsejamos que hagáis las siguientes tareas en la capa Modelo:

- **Tarea 1**: Implementación del caso de uso "búsqueda de pruebas deportivas (FUNC-1)", así como sus pruebas automatizadas.

- **Tarea 2**: Implementación de los casos de uso: recuperación de todas las provincias y recuperación de todos los tipos de prueba, así como sus pruebas automatizadas. Ambos casos de uso son necesarios para generar los desplegables de provincia y tipo de prueba en el formulario de búsqueda de pruebas deportivas del frontend (de forma similar a `CatalogService.findAllCategories` en pa-shop). En los commits de esta tarea podéis usar la etiqueta FUNC-1, dado que son tareas necesarias para la implementación de FUNC-1 a nivel global (frontend y backend).

- **Tarea 3**: Implementación del caso de uso "visualización de la información detallada de una prueba deportiva (FUNC-2)", así como sus pruebas automatizadas.

- **Tarea 4**: Implementación del caso de uso "inscripción en una prueba deportiva (FUNC-3)", así como sus pruebas automatizadas.

Un aspecto que tenéis que tener en cuenta es que, a diferencia del enfoque que seguisteis en ISD, la implementación de los casos de uso en los servicios locales no deben realizar validaciones básicas de formato de datos (aquellas que en ISD originaban que se devolviese `InputValidationException`). Por ejemplo, la implementación del caso de uso "inscripción en una prueba deportiva" no debe verificar si la tarjeta bancaria tiene un determinado número de caracteres (e.g. 16). Como aprenderéis en el tema 4, este tipo de validaciones las haréis cómodamente desde la capa de servicios REST usando un enfoque declarativo basado en anotaciones. Consecuentemente, las operaciones de los servicios locales no devolverán ninguna excepción del tipo `InputValidationException`.