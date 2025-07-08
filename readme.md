# Guía de Aprendizaje: Git y GitHub Colaborativo

¡Bienvenidos, aventureros del código! Este repositorio es nuestro campo de entrenamiento para dominar el arte de la colaboración utilizando Git y GitHub, dos de las herramientas más importantes en el mundo del desarrollo de software.

En lugar de trabajar con código complejo, nuestro proyecto consiste en escribir un **cuento de forma colaborativa**. Esto nos permite centrarnos en el flujo de trabajo, la comunicación y la resolución de problemas típicos de un equipo de desarrollo.

## 📖 Nuestro Cuento

Toda la historia, aportaciones y desarrollo de la trama de nuestro "Cuento Colaborativo" se encuentra en el siguiente archivo:

➡️ **[cuento.colaborativo.md](cuento.colaborativo.md)** ⬅️

---

## 🚀 Flujo de Trabajo del Colaborador (Paso a Paso)

Esta es el ayuda memoria que debes seguir cada vez que quieras añadir una nueva parte a la historia.

### 1. Sincronizar (¡Siempre antes de empezar!)
Antes de escribir una sola letra, asegúrate de tener la última versión del proyecto.

```bash
# 1. Ve a la rama principal
git checkout main

# 2. Descarga y fusiona todos los cambios desde GitHub
git pull
```

### 2. Crear tu Rama de Trabajo
Nunca trabajes directamente en la rama `main`. Crea una rama nueva y descriptiva para tu aportación. Es una buena práctica usar prefijos como `feature/` (para una nueva parte de la historia), `fix/` (para corregir un error ortográfico) o `docs/` (para mejorar este README).

```bash
# Crea una nueva rama y muévete a ella
git checkout -b feature/introducir-al-ogro-programador
```

### 3. ¡A Escribir! (Hacer Cambios y Commit)
Abre `cuento.colaborativo.md` y haz tu magia. Una vez que estés contento con tu aportación, guarda los cambios en un "commit".

```bash
# 1. Añade tu archivo modificado al "staging area"
git add cuento.colaborativo.md

# 2. Guarda los cambios con un mensaje descriptivo y claro
git commit -m "feat: Añade al personaje del ogro que solo habla en Python"
```

### 4. Compartir tu Trabajo (Push y Pull Request)
Sube tu rama a GitHub para que el resto del equipo pueda verla y crea un Pull Request (PR) para proponer que tus cambios se incluyan en la historia principal.

```bash
# Sube tu rama a GitHub (la primera vez usa --set-upstream o -u)
git push --set-upstream origin feature/introducir-al-ogro-programador
```
Después de ejecutar este comando, ve a la página del repositorio en GitHub. Verás un banner para **crear un Pull Request**. Haz clic, escribe un buen título, una descripción si es necesario, y **asigna al Líder del Proyecto como revisor**.

### 5. Revisión y Fusión
El líder del proyecto (y otros compañeros) revisarán tu aportación. Pueden dejar comentarios o solicitar cambios. Una vez que todo esté aprobado, el líder **fusionará (Merge)** tu Pull Request a la rama `main`.

### 6. Limpieza y Sincronización Final
Una vez que tu PR se ha fusionado, tu `main` local está desactualizado de nuevo. ¡Repite el paso 1 para ponerte al día!

```bash
# Vuelve a main y actualiza
git checkout main
git pull
```

---

## 💣 Cómo Resolver un Conflicto de Merge

A veces, dos personas editan la misma línea. ¡No entres en pánico! Es normal. Si tu Pull Request tiene un conflicto, es tu responsabilidad arreglarlo.

1.  **Actualiza tu `main` local:** `git checkout main` y luego `git pull`.
2.  **Vuelve a tu rama de trabajo:** `git checkout tu-rama-con-conflicto`.
3.  **Trae el conflicto a tu máquina:** `git merge main`. La terminal te avisará del conflicto.
4.  **Abre el archivo en conflicto** (ej. `cuento.md`). Verás algo así:
    ```
    <<<<<<< HEAD
    El ogro dijo: "print('¡Hola!')".
    =======
    El ogro gruñó: "System.out.println("¡Hola!");".
    >>>>>>> main
    ```
5.  **Edita el archivo:** Habla con tu equipo para decidir la versión final. **Borra** los marcadores `<<<<<<<`, `=======`, `>>>>>>>` y deja el texto como debería ser.
6.  **Finaliza la resolución:**

```bash
# Marca el archivo como resuelto
git add cuento.colaborativo.md

# Haz un commit para guardar la resolución
git commit

# Sube los cambios a tu rama. El PR se actualizará automáticamente
git push
```

## 📝 Ayuda Memoria Rápida (Cheatsheet)

-   `git clone [URL]` → Descargar un repositorio por primera vez.
-   `git pull` → Traer los cambios del repositorio remoto a tu rama local.
-   `git push` → Enviar tus commits locales al repositorio remoto.
-   `git checkout -b [nombre-rama]` → Crear una nueva rama y moverse a ella.
-   `git checkout [nombre-rama]` → Moverse a una rama existente.
-   `git add [archivo]` → Preparar un archivo para el próximo commit.
-   `git commit -m "mensaje"` → Guardar una instantánea de tus cambios.
-   `git status` → Ver el estado de tus archivos y en qué rama estás.
-   `git log` → Ver el historial de commits.

```