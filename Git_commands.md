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
