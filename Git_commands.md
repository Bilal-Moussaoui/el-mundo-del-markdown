# Cómo crear un repositorio local y hacer commit

Un **repositorio** en el contexto de un **sistema de control de versiones** es un lugar o espacio digital donde se *almacenan* y *gestionan* una serie de archivos junto con su historial de versiones.

**Aspectos clave:**
1. La gestión de versiones actúa como un **chekpoint** para tener siempre respaldos en caso de errores.
2. La ventaja de tener un **repositorio** es que permite a varias personas trabajar en un mismo proyecto. Esto mantiene el orden, ya que cada cambio propuesto en una nueva versión está firmado por el autor.

## Procedimiento (Comandos y Pasos)

1. Primero, iniciamos la gestión de versiones con el comando **git init** (Asegúrate de tener Git instalado en tu sistema Linux y vinculado a tu cuenta).
2. Luego, revisamos el estado de nuestro proyecto con el comando **git status**.

En este punto, en nuestra carpeta, hay varios tipos de archivos. No importa si son textos, código u otros. Estamos en proceso, aún no hay nada definitivo. Estos archivos suelen ser el código fuente de un proyecto de software, pero también pueden incluir documentos, imágenes u otros tipos de archivos que formen parte del proyecto.

3. Cuando tengamos algo definitivo, lo añadiremos a la **Staging area**, que es el paso previo a hacer el commit. Aquí mostramos un producto más acabado pero aún no definitivo.
    * El comando es: **git add <archivos>**. Si deseas añadir todos los archivos de la ruta en la que estamos, utiliza **git add .**

**Importante**

`
Los archivos que están en la Staging area pueden ser actualizados por otras versiones en cualquier momento. Por ejemplo, si hacemos un cambio de último momento en un archivo que se encuentra en la Staging Area, lo volvemos a poner en ella con su versión final usando el comando git add.
`

4. Una vez tengamos la versión final, la almacenamos en nuestro repositorio como una nueva versión. Hacemos un commit con el comando: **git commit -m <mensaje>**.

5. Para consultar el historial de cambios de versiones, es decir, todas las versiones que hemos ido subiendo al repositorio, usamos el comando **git log**.

# ¿Qué significa trabajar con ramas en un proyecto?

Imagina que estás trabajando en un proyecto grande y complejo, donde tienes una parte central que constituye la base del proyecto. En lugar de realizar cambios directamente en esta parte central (llamada "rama principal" o "rama master"), puedes utilizar una estrategia llamada "trabajar en ramas" para hacer modificaciones adicionales de manera organizada y segura.

Una rama es una especie de **copia virtual del proyecto en un estado específico**. Te permite trabajar en nuevas funcionalidades o correcciones **sin afectar directamente la rama principal**. Esto es útil porque puedes experimentar y desarrollar cambios **sin arriesgar la estabilidad del proyecto principal.**

## Crear una nueva rama

 Antes de comenzar a trabajar en una nueva característica o solución, puedes crear una rama separada para ello. Esto se hace usando el comando: 
 
 **git branch nombre-de-la-rama**

 Esto creará una nueva rama y te cambiará automáticamente a ella para que puedas comenzar a trabajar en tu tarea sin afectar la rama principal.

* Para cambiar de rama usaremos: **git switch <nombre_de_la_rama>**
* Para cambiar y crear una nueva rama: **git switch -c <nombre_de_la_nueva_rama>**
* Finalmente, para consultar las ramas que hay: **git branch**

## Realizar cambios y confirmar

 Una vez en tu nueva rama, puedes realizar cambios en los archivos como lo harías normalmente. Después de hacer los cambios, debes confirmarlos en la rama con el siguiente proceso:
```
git add archivo-modificado
git commit -m "Mensaje descriptivo de los cambios"
```

## Branch Merge (Fusión de Ramas)

Imagina que estás trabajando en un proyecto con un equipo y todos tienen sus propias versiones de archivos. La fusión de ramas en Git es como combinar estas diferentes versiones en una sola.

- **¿Por qué hacerlo?** Digamos que tú y tu compañero trabajaron en diferentes partes de un proyecto en ramas separadas. Ahora quieres combinar sus cambios en la rama principal para tener una versión completa del proyecto.

- **Cómo hacerlo:** Primero, asegúrate de estar en la rama donde deseas juntar los cambios. Luego, usa el comando `git merge <nombre_de_la_rama>` para combinar los cambios de la otra rama. Si no hay problemas, Git automáticamente mezclará los cambios. Si hay problemas, tendrás que solucionarlos y luego confirmar la mezcla.

El proceso general para realizar una fusión de ramas es el siguiente:

1. Asegúrate de estar en la rama en la que deseas fusionar los cambios. Por ejemplo, si deseas fusionar cambios de una rama de función en la rama principal, primero cambia a la rama principal: **git switch main**.

2. Luego, utiliza el comando **git merge <nombre_de_la_rama>** para fusionar los cambios de la otra rama en la rama actual. Por ejemplo, si deseas fusionar una rama llamada *feature-branch*, el comando sería: **git merge feature-branch**.

3. Git intentará fusionar los cambios automáticamente. Si no hay conflictos, los cambios se integrarán y se creará un nuevo commit de fusión.

4. Si hay conflictos, Git te notificará y te mostrará los archivos en conflicto. Deberás resolver estos conflictos manualmente, editar los archivos para corregir los problemas y luego hacer un commit para finalizar la fusión.

## Branch Rebase (Reorganización de Ramas)

Ahora imagina que en lugar de simplemente combinar las versiones, deseas reorganizar el trabajo en una línea más recta y ordenada.

- **¿Por qué hacerlo?** Supongamos que tienes cambios en tu rama y también hay cambios nuevos en la rama principal. Quieres incorporar estos cambios en tu rama, pero deseas que se vea como si hubieras trabajado en tu rama después de los cambios en la rama principal.

- **Cómo hacerlo:** Primero, asegúrate de estar en tu rama. Luego, utiliza el comando `git rebase <nombre_de_la_rama>` para reorganizar tus cambios en la parte superior de los cambios de la otra rama. Git aplicará tus cambios uno por uno, ajustándolos a los cambios nuevos. Esto crea una línea más limpia de cambios.

El proceso de rebasing implica los siguientes pasos:

1. Asegúrate de estar en la rama en la que deseas aplicar los cambios. Por ejemplo, si deseas reorganizar una rama de función en la rama principal, primero cambia a la rama principal: **git switch main**.

2. Luego, utiliza el comando **git rebase <nombre_de_la_rama>** para reorganizar la rama actual con los cambios de la otra rama. Por ejemplo, si deseas reorganizar una rama llamada *feature-branch*, el comando sería: **git rebase feature-branch**.

3. Git aplicará los cambios uno por uno desde la rama que estás reorganizando y resolverá los conflictos, si los hay, en el proceso.

4. Una vez completado el proceso de rebase, tendrás una rama actualizada con los cambios de la otra rama aplicados directamente encima de ella.

Es importante notar que el rebase puede cambiar el historial existente, lo que podría ser complicado si otros también están trabajando en tu rama. En resumen, la fusión y el rebase son formas de combinar cambios, pero elige la que mejor se adapte a tu situación y cómo quieres mantener el registro de cambios en tu proyecto.
