# DUB Ministays · versión instalable y en equipo

Esta carpeta contiene la aplicación preparada para instalarse en el ordenador como una app más (con su icono, su propia ventana y funcionando sin conexión). Puede usarla una sola persona o varias a la vez compartiendo los mismos datos en la carpeta de un equipo de Teams.

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La aplicación |
| `manifest.webmanifest` | Nombre, colores e icono de la app instalada |
| `sw.js` | Permite instalarla y usarla sin internet |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Iconos |

## 1. Publicarla en GitHub Pages (una sola vez)

1. En GitHub, crea un repositorio nuevo, por ejemplo `ministays` (si ya publicaste la app con otro nombre, basta con sustituir los archivos en ese mismo repositorio).
2. Pulsa **Add file → Upload files** y sube los seis archivos de la tabla (este documento no hace falta).
3. Ve a **Settings → Pages**. En *Source* elige **Deploy from a branch**, rama **main** y carpeta **/ (root)**. Guarda.
4. En uno o dos minutos la app estará en `https://TU-USUARIO.github.io/ministays/`.

En el repositorio solo está el programa: los datos de familias y alumnos **no se suben nunca**, se quedan guardados en tu ordenador. No subas al repositorio las copias de seguridad (`.json`).

## 2. Instalarla

1. Abre la dirección anterior con **Edge** o **Chrome**.
2. Pulsa **Instalar la aplicación** en la barra lateral (abajo a la izquierda). También puedes usar el icono de instalar de la barra de direcciones o el menú **⋯ → Aplicaciones → Instalar**.
3. Aparecerá «Ministays» en el menú Inicio y podrás anclarla a la barra de tareas.

## 3. Trabajar en equipo (varias personas con los mismos datos)

Los datos se guardan en un archivo, `acogida-datos.json` (conserva ese nombre para que las carpetas que ya usabais sigan funcionando), dentro de la carpeta de Documentos del equipo de Teams. Cada persona lo abre desde su ordenador gracias a la sincronización de OneDrive.

**Una sola vez, la persona que empieza:**

1. En Teams, ve al canal del equipo → **Archivos** y crea una carpeta, por ejemplo `Ministays`.
2. Pulsa **Sincronizar** (o **Agregar acceso directo a Mis archivos**). La carpeta aparecerá en el Explorador de Windows, dentro de OneDrive.
3. Abre la app instalada. La primera vez pregunta cómo vas a usarla: elige **En equipo**, escribe tu nombre y pulsa **Elegir la carpeta del equipo**. Selecciona la carpeta `Ministays` sincronizada.
4. Si en tu ordenador ya tenías datos, la app te ofrece **subirlos a la carpeta**. Si no, empieza vacía y puedes usar **Restaurar copia** con tu último `.json`.

**Cada compañero:**

1. Sincroniza la misma carpeta del equipo en su ordenador (paso 2).
2. Abre la app instalada, elige **En equipo**, escribe su nombre y selecciona esa carpeta. Verá los mismos datos.

**Día a día:**

- Al abrir la app, el navegador puede pedir permiso para usar la carpeta: pulsa **Conectar**.
- Los cambios de cada persona se guardan en el archivo compartido y OneDrive los lleva a los demás en unos segundos. La app comprueba cada 15 segundos si hay cambios y se actualiza sola. Abajo a la izquierda se ve cuándo se sincronizó y quién hizo el último cambio.
- Los cambios se unen ficha a ficha: si una persona edita una familia y otra un alumno a la vez, se conservan los dos.
- Si dos personas cambian **la misma ficha** casi a la vez, se queda la versión más reciente y la app avisa a las dos. Quien perdió su cambio puede recuperarlo desde **Equipo: … → Recuperar mi versión**.
- Si OneDrive crea una copia en conflicto del archivo (con el nombre del ordenador), la app la une y la borra sola.
- Cada día se guarda una copia automática en la subcarpeta `copias`. SharePoint también guarda el historial de versiones del archivo.

**Límites:** está pensado para un grupo pequeño (2–5 personas). No es tiempo real: los cambios tardan de unos segundos a un minuto en llegar. Hace falta Edge o Chrome y tener la carpeta sincronizada con OneDrive.

## 4. Pasar tus datos a la app instalada (si la usas solo en tu ordenador)

La app instalada empieza vacía, porque guarda los datos aparte de la versión que usabas hasta ahora.

1. En la versión antigua: **Guardar copia de seguridad…**
2. En la app instalada: **Restaurar copia** y elige ese archivo.

## 5. Actualizar la app más adelante

1. Sustituye `index.html` en el repositorio por la versión nueva.
2. Edita `sw.js` y cambia el número de `VERSION` (por ejemplo, de `ministays-v16` a `ministays-v17`).
3. La próxima vez que abras la app te avisará de que hay una versión nueva: ciérrala y vuelve a abrirla.

## Cosas a tener en cuenta

- En modo «Solo en este ordenador», los datos viven en ese ordenador y en ese navegador. Si cambias de ordenador, usa la copia de seguridad.
- Si desinstalas la app, Edge o Chrome pueden preguntarte si borrar sus datos: guarda antes una copia.
- Funciona sin internet. Solo necesita conexión para leer archivos Excel de Forms la primera vez y para generar los códigos QR; después quedan guardados.
- Dentro de la app instalada, «Guardar copia de seguridad…» sí deja elegir carpeta, por ejemplo la carpeta del equipo de Teams sincronizada con OneDrive.
