# Tareas para la semana del 29 de abril

Os aconsejamos que hagáis las siguientes tareas:

- Implementar el caso de uso que permite inscribir a un participante una prueba deportiva (FUNC-3) en el frontend. Tendréis que desarrollar dos componentes, e.g., `RegistrationForm` (para implementar el formulario de inscripción) y `RegistrationCompleted` (pantalla de éxito). Estos dos componentes son muy parecidos a `BuyForm` y `PurchaseCompleted` en pa-shop (apartado 7.4). Algunos aspectos adicionales a tener en cuenta:
  - `RegistrationForm` se muestra en la pantalla de detalle de una prueba deportiva cuando se cumplen las condiciones necesarias.
  - `RegistrationCompleted`, además de mostrar el código de inscripción y el dorsal asignado, también debe mostrar el nombre de la prueba deportiva.

- Implementar el caso de uso que permite realizar la entrega de dorsales (FUNC-4) en el frontend. A diferencia del caso anterior, sólo  necesitáis desarrollar un componente, e.g., `DeliverDorsalForm`, dado que el mensaje de éxito se muestra dentro del propio componente (no se navega a otra pantalla). Para mostrar el mensaje de éxito, si lo deseáis, podéis usar el componente `Success` (en `src/modules/common/components`). Algunos aspectos adicionales a tener en cuenta:
  - `DeliverDorsalForm` se muestra en la pantalla de detalle de una prueba deportiva cuando se cumplen las condiciones necesarias.
  - ¿Es necesario subscribir `DeliverDorsalForm` a cambios en el estado de Redux para poder mostrar el dorsal que el empleado tiene que entregar?

