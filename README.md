# app-listas
Este programa es una simulación de una aplicación móvil que tiene como propósito organizar tareas por categorías como así también ver el progreso de éstas.
A medida que se completan las tareas y se marcan las casillas correspondientes, las barras de progreso muestran cuánto ha avanzado.
El programa permite a los usuarios:
1. Organizar tareas en categorías: Las categorías disponibles son Estudio, Trabajo y Hogar. El usuario puede agregar, editar, eliminar y marcar como completas las tareas en cada categoría.
2. Visualizar el progreso por categoría: Cada categoría tiene una barra de progreso que muestra qué porcentaje de tareas se han completado.
3. Navegar entre pantallas:
− Pantalla de inicio: Muestra un resumen general de las tareas organizadas por categoría.
− Pantalla de categorías: Permite gestionar las tareas de manera más detallada (agregar, editar, eliminar).
4. Estilo visual llamativo y diseño funcional:
− Avatar de perfil circular personalizado.
− Colores, gradientes y un diseño moderno que hacen la aplicación visualmente atractiva.
− Mensajes de error y cuadros de diálogo para mejorar la experiencia de usuario.
Este programa es útil para personas que desean mantener sus tareas organizadas y gestionar su tiempo de forma eficiente.

Integrantes:
- Alejandro Nicolás González Quiñónez
- Erika Analía Benítez Delgado
- Alexis Rolando Alderete Araujo

Cambios Realizados
0. Código Inicial (Erika Benítez)

1. La aplicación se pasó al español. (Nicolás González)

2. Se agregó una lista desplegable para seleccionar categorías: (Alexis Alderete)
Cuando el usuario selecciona una categoría, el programa actualiza la interfaz para mostrar las tareas asociadas a esa categoría. Esto se logra mediante la función mostrar_tareas_categoria.
El ComboBox permite al usuario seleccionar una categoría específica entre las opciones disponibles: "Estudio", "Trabajo" y "Hogar".
− hint_text: Muestra un texto de sugerencia cuando no se ha seleccionado ninguna opción.
− options: Contiene las opciones disponibles en el combo. Cada opción se define mediante ft.dropdown.Option.
− on_change: Es un evento que se activa cuando el usuario selecciona una opción. Llama a la función mostrar_tareas_categoria y le pasa el valor seleccionado como argumento.

3. Las barras de progreso se rellenaron de acuerdo a las tareas completadas: (Nicolás González)
Representan el porcentaje de tareas completadas para cada categoría.
− Se usa un Container que contiene un Row (fila) para alinear el nombre de la categoría y la barra de progreso.
− La barra de progreso (ft.ProgressBar) tiene un valor inicial de 0, y su tamaño está definido por width=200.
− Actualización dinámica: La función actualizar_barras calcula el progreso de cada categoría y actualiza el valor de la barra:
− Cálculo del progreso: Divide las tareas completadas entre el total de tareas en la categoría. Si no hay tareas, el progreso es 0.

4. Las tareas se listaron dependiendo de la categoría: (Erika Benítez)
Muestra las tareas asociadas a una categoría en una lista interactiva.
Cada tarea se representa como una fila (ft.Row) con los siguientes elementos:
− Checkbox (ft.Checkbox): Permite marcar o desmarcar una tarea como completada. Al cambiar su estado, llama a la función cambiar_estado_tarea.
− Texto (ft.Text): Muestra el nombre de la tarea.
− Botón de edición (ft.IconButton con ft.icons.EDIT): Abre un cuadro de diálogo para editar la tarea.
− Botón de eliminación (ft.IconButton con ft.icons.DELETE): Elimina la tarea seleccionada.
Cuando se selecciona una nueva categoría, se limpia la lista actual (lista_tareas.controls.clear()) y se añaden las tareas correspondientes a la categoría seleccionada.

5. Se agregaron contadores de tareas: (Alexis Alderete)
Muestra un contador que indica cuántas tareas hay en la categoría seleccionada. Cada vez que se agrega, edita o elimina una tarea, el contador se actualiza dinámicamente para reflejar el nuevo número de tareas.

6. Se agregó una ventana emergente para notificar errores: (Nicolás González)
Asegura que las tareas sean válidas antes de agregarlas.
− Tarea no vacía: Verifica que el texto de la tarea no esté vacío (tarea != ""). Si lo está, muestra una alerta.
− Categoría válida: Comprueba que la categoría exista en el diccionario categorias. Si no es válida, también muestra una alerta.

Cómo ejecutar el proyecto:
- Instalar las dependencias (Python, Flet) y darle al boton ejecutar 
