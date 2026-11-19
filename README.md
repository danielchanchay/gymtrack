# GymTrack

Registro personal de gimnasio, comida y progreso en una sola app, pensada para usarse con una mano entre series.

**[Pruébala aquí →](https://danielchanchay.github.io/gymtrack/)**

La construí porque ninguna app que probé hacía las dos cosas que necesitaba, entrenamiento y alimentación, sin obligarme a buscar cada dato en listas interminables. La uso todos los días.

| Hoy | Entreno | Comida | Progreso |
| --- | --- | --- | --- |
| ![Hoy](capturas/01-hoy.png) | ![Entreno](capturas/02-entreno.png) | ![Comida](capturas/03-comida.png) | ![Progreso](capturas/04-progreso.png) |

## Qué hace

- **Hoy:** la semana de un vistazo, la rutina que toca y las calorías y macros del día.
- **Rutinas:** varios gimnasios, una rutina por día de la semana y un catálogo de ejercicios ampliable.
- **Entreno:** cronómetro, series con tipo (calentamiento, efectiva, drop set…), comparación con la sesión anterior, sugerencia de cuándo subir el peso, dibujo de los discos que hay que cargar en la barra y temporizador de descanso con aviso.
- **Comida:** búsqueda de alimentos con sus macros, alimentos propios, porciones ajustables y copiar y pegar comidas entre comidas y entre días.
- **Progreso:** volumen levantado, marca estimada a una repetición por ejercicio, balance entre lo que comes y lo que gastas, peso corporal y recomendaciones automáticas.

## Cómo está hecha

Es un solo archivo HTML, sin frameworks ni dependencias: HTML, CSS y JavaScript.

La app funciona de dos maneras:

- **Dentro de Claude**, como artefacto: guarda los datos en la cuenta del usuario y los sincroniza entre dispositivos, y tiene un asistente que responde preguntas sobre el propio historial («¿cómo voy en press de banca?»).
- **Como página suelta**, que es la demo de este repositorio: guarda todo en el navegador de quien la usa. No hay servidor ni cuentas, así que cada visitante empieza con la app vacía y nadie ve los datos de otro. Para explorarla sin registrar nada, usa el botón **Ver con datos de ejemplo** en Progreso.

Algunas decisiones de diseño:

- **El asistente no inventa números.** Responde leyendo el historial real de entrenos y comidas, no con datos generales.
- **Nada se rellena solo.** Si marcas una serie sin escribir las repeticiones, la app te las pide en vez de suponerlas, para que el historial solo tenga lo que de verdad hiciste.
- **El equipo define el volumen.** En los ejercicios con dos mancuernas se escribe el peso de una y el total cuenta las dos.
- **Los fallos se ven.** Si el guardado en la cuenta falla, la app reintenta y, si no lo logra, lo avisa en pantalla en vez de seguir en silencio.

## Limitaciones conocidas

- Si se registran datos en dos dispositivos al mismo tiempo sin que uno alcance a sincronizar, el último en guardar puede reemplazar lo del otro en ese mes.
- En la demo pública no están el asistente ni la sincronización entre dispositivos, porque dependen de Claude.
- Los valores nutricionales de la lista base son aproximados por porción.

## Cómo se construyó

La diseñé y la construí con Claude, un asistente de IA, como proyecto personal. Yo definí qué debía hacer, la probé en el gimnasio y decidí qué cambiar; el código se escribió y se revisó con ayuda de la IA, incluidas auditorías del código antes de publicarla.

## Autor

Daniel Chanchay · [GitHub](https://github.com/danielchanchay)

Licencia MIT: puedes usar y adaptar el código citando la fuente.
