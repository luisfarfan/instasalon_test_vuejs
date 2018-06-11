## Frontend

Esta parte evalúa tus conocimientos de HTML, CSS y Javascript.

Tenemos una lista de tareas por implementar, 
necesitamos que le asignes una prioridad 
(ordenando las tareas, primero la más importante, y al último la menos importante),
 y nos expliques ¿Qué tomaste en cuenta para hacer esa priorización?

- Paginación, cargar más resultados al hacer scroll al final de la página.
- Implementar una vista donde el usuario pueda buscar un servicio por nombre.
- Ordenar los resultados de la búsqueda por duración.
- Ordenar los resultados de la búsqueda por precio.
- Visualizar el detalle del servicio en un modal.

# Juntando las tareas!

Juntando las tareas, seria algo como un buscador(input #componente1) donde el usuario
podra escribir un nombre, y segun vaya escribiendo se mostraran los resultados
en una lista ordenada(#componente2) configurada para que muestre una cantidad de registros
limitados la primera vez, cosa que cuando se haga scroll en el ultimo registro 
(el infinity scroll seria una #directiva1),
se vayan cargando más registros (a esta funcionalidad se le llama infinity scroll).
Esta lista podra ser ordenada por duración y/o precio,
supongamos que este ordenamiento sean un checkbox cada uno, y que la data ordenada
segun el filtro venga desde Backend (los checkbox serian #componente3).
Lo ultimo seria que cuando yo haga click sobre un servicio especifico, el detalle
de este servicio se muestre en un modal (el modal seria un #componente4)

# Resumiento en componentes y directivas:
- componente1: input de busqueda
- componente2: lista ordenada donde se filtraran los resultados.
- componente3: checkboxes que segun sean checkeados dispararan un evento de emision para ordenar la lista del #componente2
- componente4: Modal donde se mostrara la información detallada.
- directiva1: esta directiva agregara la funcionalidad de infinity scroll al componente2.

# Priorizando de mas importante a menos:
- 1. El mas importante seria el #componente2, ya que ahi se centraria toda la información,
ademas que su funcionalidad sera extendida por una directiva (#directiva1). Y ya que los demás componentes
interactuan con este componente, entonces se tendria que implementar métodos para que los demás
componentes puedan modificar la información o funcionalidad. Por esta razón este seria el mas importante.
- 2. El segundo seria el #componente3, ya que este alteraria la información del #componente2, 
pongamonos en el caso, de que el orden segun los filtros seria hecho por javascript, entonces este
componente tendria que interactuar con el #componente2, y avisarle que realize dicho filtro.
- 3. El tercero seria el input de busqueda, este componente sera el iniciador del flujo, la manera
en como se comunique este #componente1 con el #componente2 seria mediante un servicio, el cual este
servicio recibira una palabra, y el servicio se comunicara con el backend para traer la data que corresponde
a esta palabra, una vez que traiga la información el servicio mandara la información al #componente2.
Para temas de performance, se puede aplicar la tecnica llamada debounceTime, esta tecnica hace que despues
de un tiempo especificado, se emita un valor.
- 4. Por ultimo y no menos importante, el modal (#componente4), este modal solo mostrara la información
del elemento seleccionado.
