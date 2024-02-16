# Tareas para la semana del 19 de febrero

Después de la clase de teoría del 14 de febrero, habéis adquirido los conocimientos necesarios para realizar las 3 tareas que se especifican a continuación dentro de vuestro proyecto.

## Tarea 1: implementar las entidades de la práctica

Debéis recordar que los métodos get/set se pueden generar automáticamente desde IDEA. Como estudiaremos al final del tema 3, a diferencia de ISD, **NO** debéis redefinir `equals` y `hashCode`. Como paso previo, podéis hacer antes un diagrama UML con las entidades para tener una visión global de las relaciones entre ellas. En todo caso, nosotros no os pediremos el diagrama UML.

## Tarea 2: definir las interfaces de los DAOs de las entidades

Recordad que gracias a spring-data-jpa este paso es especialmente sencillo. 

Un caso interesante ocurre en el caso de uso de búsqueda de pruebas deportivas (página 2 del enunciado de la práctica). Este caso de uso requiere que el DAO de las pruebas deportivas proporcione un método de búsqueda apropiado. El problema es que cualquiera de los cuatro campos de búsqueda (provincia, tipo de prueba, fecha de inicio y fecha de fin) es opcional. Conceptualmente se debe generar una consulta con un WHERE con tantas condiciones como campos haya seleccionado/rellenado el usuario. Las convenciones de nombrado de los métodos de los DAOs que nos permite usar spring-data-jpa NO contemplan la situación de que una condición sea opcional. Por este motivo, el método de búsqueda de pruebas deportivas que debe proporcionar el DAO de las pruebas deportivas debe usar la estrategia ilustrada en la diapositiva 54 o en las diapositivas 55-56 del tema 2. 

En este caso, la estrategia más sencilla sería la ilustrada en la diapositiva 54 (`@Query`), empleando un pequeño truco para incluir condicionalmente cada parámetro de búsqueda en la consulta. Por ejemplo, supongamos que queremos implementar un caso de uso de búsqueda de usuarios mediante un formulario con dos campos: nombre y apellidos. Ambos campos son opcionales. Cuantos más campos rellene el usuario de la aplicación, más selectiva será la búsqueda (e.g. si rellenan los dos campos, se recuperarán los usuarios que tengan ese nombre y apellidos; si sólo se rellena el campo del nombre, se recuperarán los usuarios que tienen ese nombre; si no se rellena ningún campo, se recuperarán todos los usuarios; etc.). Para este fin, el DAO de los usuarios podría proporcionar el siguiente método de búsqueda (por sencillez, no usa paginación):

```java
@Query("SELECT u FROM User u WHERE (?1 IS NULL OR u.userName = ?1) AND (?1 IS NULL OR u.lastName = ?2) ORDER BY lastName")
List<User> findUsers(String firstName, String lastName)
```

El incluir `?1 IS NULL`en cada condición provoca que la condición sea verdadera si el valor del parámetro correspondiente es `null`, conceptualmente "eliminando" la condición del WHERE.

## Tarea 3: definir las interfaces de la capa Lógica de Negocio

Cada interfaz incluirá la firma completa de sus operaciones, con las excepciones necesarias.