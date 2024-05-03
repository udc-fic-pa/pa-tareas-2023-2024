# Tareas para la semana del 6 de mayo

Para terminar la implementación del frontend ya sólo os quedan por completar las siguientes tareas:

- Visualización del histórico de las inscripciones (FUNC-5). La implementación de este caso de uso en el frontend es similar a la visualización de los pedidos de un usuario en pa-shop. Podéis consultar el código fuente de pa-shop.

- Puntuación de una prueba deportiva (FUNC-6). La implementación de este caso de uso en el frontend es similar a los casos de uso de inscripción y entrega de dorsal. 


Algunos aspectos adicionales a tener en cuenta:
- Tal y como se comenta en el enunciado de la práctica, en la pantalla de visualización del histórico de inscripciones, en cada inscripción se mostrará un enlace o un botón para poder puntuar la prueba asociada si se cumplen las condiciones necesarias. La opción del botón os resultará más sencilla. A continuación os mostramos una forma de hacerlo. La implementación de `onClick`, entre otras cosas, tiene que provocar una navegación (hook `useNavigate`) a la pantalla que muestra el formulario de puntuación.

  ```js
  <td>
      {registration.ratingEnabled ?
          <button className="btn btn-primary" onClick={() => {
              ...
          }}> 
              <FormattedMessage id="...rate"/>
          </button>
          :
          <FormattedMessage id="...rated"/>
      }
  </td>
  ```

- La pantalla de puntuación debe mostrar el nombre de la prueba deportiva. ¿Hay que dejar algo en el estado de Redux antes de navegar a la pantalla de puntuación?


