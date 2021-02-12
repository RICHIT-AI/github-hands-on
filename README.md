# GitHub Hands-On
Este hands-on sirve para que los miembros de RICH IT se familiaricen con el flujo de trabajo en GitHub

## Primeros pasos
1. Clona este repositorio en local para que puedas trabajar en el:
   ```bash
   git clone https://github.com/RICHIT-AI/github-hands-on.git
   ```

2. El repositorio tiene 2 ramas (**branch**) la rama `main` y la rama `develop`, posiblemente tenga más ramas como `feature-*` por el momento has caso omiso de estas ramas

3. Desde tu terminal cambiate a la rama `develop` con el siguiente comando, ***es importante que hagas esto, de lo contrario podrías perderte de los ultimos cambios en desarrollo***
   ```bash
   git checkout develop
   ```
4. Crea tu propia rama siguiendo la nomenclatura, `feature-<nombre-correo>` Ej. `feature-fgarcia`
   ```bash
   git checkout -b feature-<nombre-correo>
   ```
5. El comando anterior solamente creará tu rama en tu máquina local, verifica que te encuentras en ella con el siguiente comando:
   ```bash
   git branch
   ```
   La salida será la siguiente, el asterisco indica la rama en la que estas trabajando actualmente:
   ```bash
      develop
    * feature-<nombre-correo>
      main
    ```
6. Posteriormente actualiza el repositorio que se encuentra en GitHub con tu rama:
   ```bash
   git push -u origin feature-<nombre-correo>
   ```
   Una vez completado ve a la pagina web del repositorio en GitHub y verifica que tu rama ya esté publicada

## Momento de contribuir
1. En este momento ya tienes todo lo necesario para trabajar, tienes tu rama, tu rama está en GitHub disponible para que los demás puedan visualizarla, y lo más importante en tu espacio de trabajo local te encuentras en tu rama. Importante: verifica que asi sea.

2. Y es momento de empezar a contribuir editando tus archivos en el IDE de tu preferencia, una sugerencia es [Visual Studio Code](https://code.visualstudio.com/)

3. Crea tu primer archivo, siguiendo la siguiente nomenclatura: `<nombre-correo>.md`. Los archivos `.md` son archivos [Markdown](https://commonmark.org/help/), si quieres resaltar, crear links o simplemente dar formato puedes guiarte dando click en el link

4. Comienza a trabajar en ese archivo escribiendo:
   * Nombre completo
   * Puesto en RICH IT
   * Cual fue la escuela en la que estudiaste
   * Los proyectos en los que colaboras o has colaborado en RICH IT
   * Información adicional
     * Pasatiempos
     * Gustos
     * Libros
     * Musica
     * O lo que tu prefieras compartir

5. Una vez que ya hayas finalizado tu trabajo es hora de publicar tus cambios.

6. Todo archivo en Git tiene 4 estados **Untracked**, **Unmodified**, **Modified** y **Staged**, el archivo que acabas de crear tiene el estado **Untracked**.

7. Para publicar tus cambios es necesario realizar un **commit**, pero antes de hacer un commit es necesario cambiar de estado los archivos en **Untracked** y **Modified** al estado **Staged**, y eso se hace de la siguiente manera:
   ```bash
   git add <nombre-correo>.md
   ```
   Y esto deja preparados los archivos para que se etiqueten a través de un commit

   **Sugerencia**: Evitar hacer el uso de `git add *`, ya que al agregar el añadir todos los archivos se puede perder el objetivo del commit al agregar en 1 solo commit cambios de código, documentación, configuración, entre otros. 

   **Recomendación**: todos los archivos que pertenezcan a un tipo de commit agruparlos con el commando `git add <archivo>` y ejecutar el commit, posteriormente agrupar otros archivos que pertenezcan a otro tipo de commit y agruparlos de igual forma y asi por cada tipo de cambio. Esto permite a futuro a los demás desarrolladores a entender el cambio y hacer referencia a por número de commit. 

   **Recomendación**: Los IDEs facilitan el trabajo de marcar los archivos como **Staged**, hacer uso de un IDE en lugar de la linea de commandos

8. Finalmente una vez agrupados los cambios es momento de etiquetarlos con el comando `commit`:
   ```bash
   git commit -a
   ```
   Y escribe: **"`:books:` [docs] Se agrego el perfil de nombre-correo"**

   **Sugerencia**: De ser posible hacer uso del formato que se indica en el commando ya que ayuda a identificar el tipo de cambio

   **Recomendación**: El hacer uso de un IDE facilita la creción de commits, ya que se le pueden agregar varias lineas al commit, la primer linea para el título, la segunda para una descripción más especifica del cambio, y las siguientes lineas sirven para hacer referencias a **issues**, o hacer notas adicionales.

9. Una vez que ya se tiene el commit listo es hora de publicar los cambios pero primero verificar que estás en tu rama:
   ```bash
   git branch
   ```
   Y posteriormente hacer push en tu rama:
   ```bash
   git push
   ```
10. Ahora tus cambios estan en GitHub, para que todos los miembros del equipo puedan visualizar tus cambios

## Es hora de la colaboración y retroalimentación
1. Pudes coninuar trabajando y publicando tus avances de forma continua

2. De preferencia la primera vez que crees tu rama sube un cambio muy pequeño como la creación de un **README.md**, y una vez que lo subas desde GitHub has un **Pull Request** a la rama **develop** con el siguiente formato:

    **[Tipo de cambio] Título del cambio**
    
    **Nombre:**

    **Descripción:**

    **Funcionalidad**

    **Pruebas:**

    **Anotaciones:**

    En el **Pull Request** se mostrará una lista con el historial de los commits que hayas publicado, esta sección es la sección donde empieza la colaboración

3. Has un **Pull Request** de tu rama `feature-<nombre-correo>` con la rama `develop` de la siguiente manera:

    **[doc] `<tu-nombre>`**
    
    **Nombre:** Perfil de `<tu-nombre>`

    **Descripción:** Se actualizó el repositorio con la información del contribuidor(a) `<tu-nombre>` para que todos los miembros del equipo lo conozcan

    **Funcionalidad:** Con un archivo en Markdown es necesario que el contribuidor(a) publique su perfil y sea visible para todos los miembros del equipo

    **Pruebas:** Que exista un archivo en GitHub con su perfil

    **Anotaciones:** Si es necesario agregar notas adicionales

4. Finalmente crear el **Pull Request** y esperar a que otro integrante del equipo haga sus comentarios al **Pull Request**

5. Hacer 1 comentario en al menos 3 **Pull Request** de los demás compañeros

6. Una vez que acaben de comentar todos los participantes hacer un **Merge Pull Request** a la rama **develop**

7. Finalmente una vez que visualices tus cambios en **develop** puedes eliminar tu rama de GitHub.

## Liberación del software
1. Una vez que todos hayan hecho su **merge** a la rama develop el laboratorio ha concluido, y los administradores de el repositorio crearán una rama **release-vX.X.X** que será revisada durante el transcurso de la siguiente semana al laboratorio por todos los involucrados en el **Hands-on** 
2. Una vez que todos los involucrados estén satisfechos con la rama **release-vX.X.X** se hará un merge de esta rama con **develop** y con **main**, la rama **main** se le etiquetará con el número de versión del release
3. Se eliminará finalmente la rama **release-vX.X.X**