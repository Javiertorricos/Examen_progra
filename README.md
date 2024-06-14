# BASE DE DATOS

## EL PROBLEMA
Eres un desarrollador C++ en una empresa y se te ha solicitado crear un modelo de base de datos simple. Pero antes te piden investigar sobre todas las bases de datos existentes y hacer una comparativa para justificar esta implementacion.

Entonces, primero se debe realizar dicha comparativa estudiar las existentes y escribir una justificacion del desarrollo de un nuevo manejador de base de datos.

Luego, es necesario analizar el problema y escribir un programa en C++ que implemente el trabajo con una base de datos simple (abreviado «BD»). El programa se comunicará con el usuario a través de la entrada y salida estándar (flujos stdin y stdout).

Almacenaremos en nuestra BD pares del tipo: fecha, evento. Definiremos la fecha como una cadena en el formato Año-Mes-Día, donde Año, Mes y Día son números enteros.

Definiremos el evento como una cadena de caracteres imprimibles arbitrarios sin separadores dentro (espacios, tabulaciones, etc.). Un evento no puede ser una cadena vacía. En una misma fecha pueden ocurrir muchos eventos diferentes, la BD debe ser capaz de almacenarlos todos. No es necesario guardar eventos idénticos que ocurran el mismo día: basta con guardar solo uno de ellos.

Nuestra BD debe entender ciertos comandos para que se pueda interactuar con ella:
~~~
agregar evento:                                               Add Fecha Evento
eliminar evento:                                              Del Fecha Evento
eliminar todos los eventos de una fecha específica:           Del Fecha
buscar eventos en una fecha específica:                       Find Fecha
imprimir todos los eventos de todas las fechas:               Print
~~~

Todos los comandos, fechas y eventos en la entrada están separados por espacios. Los comandos se leen desde la entrada estándar. En una línea puede haber exactamente un comando, pero se pueden ingresar varios comandos en varias líneas. También pueden haber líneas vacías en la entrada, las cuales deben ser ignoradas, y continuar procesando los nuevos comandos en las líneas siguientes.

### Agregar evento (Add Fecha Evento):
Al agregar un evento, la BD debe recordarlo y luego mostrarlo durante la búsqueda (comando Find) o impresión (comando Print). Si el evento especificado para una fecha determinada yaexiste, se debe ignorar la repetición de su adición. En caso de una entrada correcta, el programa no debe mostrar nada en la pantalla.

### Eliminar evento (Del Fecha Evento):
El comando debe eliminar un evento agregado anteriormente con el nombre especificado en la fecha indicada, si existe. Si el evento se encuentra y se elimina, el programa debe mostrar la línea "Deleted successfully" (sin comillas). Si no se encuentra el evento en la fecha especificada, el programa debe mostrar la línea "Event not found" (sin comillas).

### Eliminar varios eventos (Del Fecha):
El comando elimina todos los eventos previamente agregados para la fecha indicada. El programa siempre debe mostrar una línea en el formato "Deleted N events", donde N es la cantidad de eventos encontrados y eliminados. N puede ser igual a cero si no hubo ningún evento en la fecha especificada.

### Buscar eventos (Find Fecha):
Encuentra e imprime los eventos previamente agregados en la fecha indicada. El programa debe imprimir solo los eventos, uno por línea. Los eventos deben estar ordenados en orden ascendente según la comparación de cadenas (tipo string).

### Imprimir todos los eventos (Print):
Con este comando se puede mostrar todo el contenido de nuestra BD. El programa debe imprimir todas las parejas Fecha Evento, una por línea. Todas las parejas deben estar ordenadas por fecha, y los eventos dentro de una misma fecha deben estar ordenados en orden ascendente según la comparación de cadenas (tipo string). Las fechas deben estar formateadas de manera especial: AAAA-MM-DD, donde A, M, D son los dígitos de los números del año, mes y día respectivamente. Si algún número tiene menos dígitos, debe completarse con ceros, por ejemplo, 0001-01-01 es el primero de enero del primer año. No necesitarás imprimir una fecha con un valor de año negativo.

### Manejo de errores de entrada:
La entrada en esta tarea no siempre es correcta: tu programa debe manejar correctamente algunos errores de entrada.

### Qué errores de entrada manejar

Si el usuario ingresa un comando desconocido, el programa debe informar de ello, mostrando la línea "Unknown command: COMMAND", donde COMMAND es el comando que ingresó el usuario. Se considera comando la primera palabra en la línea (hasta el espacio).Si la fecha no corresponde al formato Año-Mes-Día, donde Año, Mes y Día son números enteros arbitrarios, el programa debe imprimir "Wrong date format: DATE", donde DATE es lo que el usuario ingresó en lugar de la fecha (hasta el espacio). Ten en cuenta que las partes de la fecha están separadas por un guion exacto, y la fecha no debe contener caracteres adicionales ni antes del año ni después del día. Las partes de la fecha no pueden estar vacías, pero pueden ser cero o incluso negativas.
