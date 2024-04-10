# Tareas para la semana del 15 de abril

Después de las clases de esta semana, habéis adquirido los conocimientos necesarios (apartados 7.1 y 7.2) para implementar la búsqueda de pruebas deportivas (FUNC-1). Dado que es el primer caso de uso que vais a implementar en el frontend, os aconsejamos que durante la semana del 15 de abril lo implementéis sin los selectores de provincia y tipo de prueba. Consecuentemente, el formulario de búsqueda sólo contemplará los campos de fecha de inicio y fin.

A continuación, destacamos algunos aspectos relevantes:

- En el componente que genera el formulario de búsqueda se aconseja usar `<input type="date">` (https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date) para los campos correspondientes a las fechas de inicio y fin:

```js
...
const [startDate, setStartDate] = useState('');
const [endDate, setEndDate] = useState('');
...
<input id="startDate" type="date" className="..." value={startDate}
    onChange={e => setStartDate(e.target.value)}/>
<input id="endDate" type="date" className="..." value={endDate}
    onChange={e => setEndDate(e.target.value)}/>
...
```

Los valores de las fechas (`string`) estarán automáticamente en formato ISO (`yyyy-mm-dd`).

- Para cada prueba deportiva que concuerde con la búsqueda, el backend devuelve (entre otras cosas) el identificador del tipo de prueba y el identificador de la provincia en la que se celebra. Dado que el frontend debe mostrar para cada prueba su tipo y el nombre de la provincia en la que se celebra, el frontend debe cachear la lista de tipos de pruebas deportivas y provincias, y a partir de esa información cacheada, obtener el nombre del tipo de prueba y de la provincia. En la búsqueda de productos de pa-shop se procede de la misma manera con respecto a las categorías de los productos (apartado 7.2). En este, sentido:
  - `App.jsx`debe recuperar la lista de tipos de pruebas y provincias del backend, de forma similar a cómo lo hace pa-shop con la lista de categorías.
  - La lista de tipos de pruebas y provincias se debe cachear en el estado de Redux, de forma similar a cómo lo hace pa-shop con la lista de categorías.
