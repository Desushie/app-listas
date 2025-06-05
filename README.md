# app-listas
Este programa es una simulación de una aplicación móvil que tiene como propósito organizar tareas por categorías como así también ver el progreso de éstas.<br/>
A medida que se completan las tareas y se marcan las casillas correspondientes, las barras de progreso muestran cuánto ha avanzado.<br/>
**El programa permite a los usuarios:**
1. Organizar tareas en categorías: Las categorías disponibles son Estudio, Trabajo y Hogar. El usuario puede agregar, editar, eliminar y marcar como completas las tareas en cada categoría.
2. Visualizar el progreso por categoría: Cada categoría tiene una barra de progreso que muestra qué porcentaje de tareas se han completado.
3. Navegar entre pantallas:<br/>
**− Pantalla de inicio:** Muestra un resumen general de las tareas organizadas por categoría.<br/>
**− Pantalla de categorías:** Permite gestionar las tareas de manera más detallada (agregar, editar, eliminar).
4. Estilo visual llamativo y diseño funcional:<br/>
− Avatar de perfil circular personalizado.<br/>
− Colores, gradientes y un diseño moderno que hacen la aplicación visualmente atractiva.<br/>
− Mensajes de error y cuadros de diálogo para mejorar la experiencia de usuario.<br/>
Este programa es útil para personas que desean mantener sus tareas organizadas y gestionar su tiempo de forma eficiente.

## Integrantes:
- Alejandro Nicolás González Quiñónez
- Erika Analía Benítez Delgado
- Alexis Rolando Alderete Araujo

## Cambios Realizados

**0. Código Inicial** (Erika Benítez)

**1. La aplicación se pasó al español.** (Nicolás González)

**2. Se agregó una lista desplegable para seleccionar categorías:** (Alexis Alderete)<br/>
Cuando el usuario selecciona una categoría, el programa actualiza la interfaz para mostrar las tareas asociadas a esa categoría. Esto se logra mediante la función mostrar_tareas_categoria.<br/>
El ComboBox permite al usuario seleccionar una categoría específica entre las opciones disponibles: "Estudio", "Trabajo" y "Hogar".<br/>
**−hint_text:** Muestra un texto de sugerencia cuando no se ha seleccionado ninguna opción.<br/>
**−options:** Contiene las opciones disponibles en el combo. Cada opción se define mediante ft.dropdown.Option.<br/>
**-on_change:** Es un evento que se activa cuando el usuario selecciona una opción. Llama a la función mostrar_tareas_categoria y le pasa el valor seleccionado como argumento.

**3. Las barras de progreso se rellenaron de acuerdo a las tareas completadas:** (Nicolás González)<br/>
Representan el porcentaje de tareas completadas para cada categoría.<br/>
− Se usa un Container que contiene un Row (fila) para alinear el nombre de la categoría y la barra de progreso.<br/>
− La barra de progreso (ft.ProgressBar) tiene un valor inicial de 0, y su tamaño está definido por width=200.<br/>
− Actualización dinámica: La función actualizar_barras calcula el progreso de cada categoría y actualiza el valor de la barra:<br/>
− Cálculo del progreso: Divide las tareas completadas entre el total de tareas en la categoría. Si no hay tareas, el progreso es 0.

**4. Las tareas se listaron dependiendo de la categoría:** (Erika Benítez)<br/>
Muestra las tareas asociadas a una categoría en una lista interactiva.<br/>
Cada tarea se representa como una fila (ft.Row) con los siguientes elementos:<br/>
**− Checkbox (ft.Checkbox):** Permite marcar o desmarcar una tarea como completada. Al cambiar su estado, llama a la función cambiar_estado_tarea.<br/>
**− Texto (ft.Text):** Muestra el nombre de la tarea.<br/>
**− Botón de edición (ft.IconButton con ft.icons.EDIT):** Abre un cuadro de diálogo para editar la tarea.<br/>
**− Botón de eliminación (ft.IconButton con ft.icons.DELETE):** Elimina la tarea seleccionada.<br/>
Cuando se selecciona una nueva categoría, se limpia la lista actual (lista_tareas.controls.clear()) y se añaden las tareas correspondientes a la categoría seleccionada.

**5. Se agregaron contadores de tareas:** (Alexis Alderete)<br/>
Muestra un contador que indica cuántas tareas hay en la categoría seleccionada. Cada vez que se agrega, edita o elimina una tarea, el contador se actualiza dinámicamente para reflejar el nuevo número de tareas.

**6. Se agregó una ventana emergente para notificar errores:** (Nicolás González)<br/>
Asegura que las tareas sean válidas antes de agregarlas.<br/>
**− Tarea no vacía:** Verifica que el texto de la tarea no esté vacío (tarea != ""). Si lo está, muestra una alerta.<br/>
**− Categoría válida:** Comprueba que la categoría exista en el diccionario categorias. Si no es válida, también muestra una alerta.

## Cómo ejecutar el proyecto:<br/>
- Instalar las dependencias (Python, Flet) y darle al boton ejecutar 
