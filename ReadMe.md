# Curso Básico de Git :) :) :)
## Introducción

Git y GitHub son herramientas fundamentales para el desarrollo de software moderno. Este curso está diseñado para enseñar los conceptos básicos y el flujo de trabajo esencial con Git, así como entender cómo interactuar con GitHub.

### ¿Qué es Git?

Git es un **sistema de control de versiones distribuido** que permite gestionar y registrar los cambios realizados en el código fuente de un proyecto de manera eficiente. A diferencia de los sistemas centralizados, Git ofrece una copia completa del historial de versiones en cada máquina que participa en el proyecto, lo que lo hace más robusto y confiable.

#### Características principales de Git:
- **Control de versiones:** Permite guardar diferentes estados de un proyecto en el tiempo, lo que facilita volver a versiones anteriores si es necesario.
- **Distribuido:** Cada colaborador tiene una copia completa del historial del proyecto.
- **Colaborativo:** Facilita el trabajo en equipo mediante la creación de ramas y la fusión de cambios.
- **Rendimiento:** Optimizado para manejar proyectos grandes y pequeños con rapidez.

Git es una herramienta esencial para evitar problemas como el uso de múltiples versiones del proyecto nombradas manualmente (`proyecto_v1`, `proyecto_final`, etc.).

### ¿Qué es GitHub?

GitHub es una **plataforma de alojamiento para proyectos gestionados con Git**, que permite colaborar de manera eficiente con otras personas. Proporciona una interfaz gráfica para gestionar repositorios, revisar cambios, realizar comentarios, y más.

#### Diferencias clave entre Git y GitHub:
| **Git**                    | **GitHub**                                        |
|----------------------------|--------------------------------------------------|
| Es una herramienta de control de versiones. | Es una plataforma para alojar repositorios de Git. |
| Funciona en tu máquina local.               | Funciona en la nube, permitiendo colaboración remota. |
| No depende de GitHub.                       | Requiere Git para gestionar los repositorios.       |

GitHub también ofrece herramientas adicionales como:
- **Issues y Pull Requests:** Para gestionar tareas y colaboraciones.
- **GitHub Actions:** Automatización de flujos de trabajo.
- **Hosting de páginas web estáticas:** A través de GitHub Pages.

En resumen, mientras que Git es la herramienta de control de versiones, GitHub es un servicio que facilita la colaboración y el trabajo en equipo utilizando Git.


## Instalación de Git en Windows

### Descarga e instalación

1. **Descargar Git:**
   - Ve a la página oficial de Git: [git-scm.com](https://git-scm.com/).
   - Haz clic en el botón de descarga que detecta automáticamente tu sistema operativo (Windows).

2. **Ejecutar el instalador:**
   - Una vez descargado, ejecuta el archivo `.exe` para iniciar el proceso de instalación.
   - Sigue las instrucciones en pantalla. A continuación, se explican las configuraciones recomendadas:

### Configuración recomendada durante la instalación

Durante la instalación, verás varias opciones. Aquí te indicamos cómo configurarlas para una experiencia óptima:

1. **Seleccionar el editor predeterminado:**
   - Git te pedirá que selecciones un editor de texto. Por defecto, sugiere Vim, pero puedes elegir un editor más amigable como Visual Studio Code o Notepad++.

2. **Ajustar la variable de entorno PATH:**
   - Selecciona la opción: `Git from the command line and also from 3rd-party software`.
   - Esto asegura que puedas usar Git desde la terminal de Windows y otras aplicaciones.

3. **Elegir el método HTTPS:**
   - Selecciona `Use the OpenSSL library`.

4. **Configurar el estilo de final de línea:**
   - Para Windows, selecciona: `Checkout Windows-style, commit Unix-style line endings`.

5. **Configurar la terminal predeterminada:**
   - Selecciona `Use MinTTY (the default terminal of MSYS2)` para usar Git Bash como terminal principal.

6. **Opciones adicionales:**
   - Activa las opciones de instalación predeterminadas para habilitar características como Git Credential Manager y el soporte para fuentes de sistema.

### Qué incluye la instalación

1. **Git CLI (Command Line Interface):**
   - La herramienta principal para usar Git desde la terminal de Windows.

2. **Git Bash:**
   - Una terminal basada en Bash que proporciona un entorno Unix en Windows.
   - Permite ejecutar comandos de Git y otras utilidades Unix, como `ls`, `rm`, `cat`, entre otros.

3. **Git GUI:**
   - Una interfaz gráfica básica para realizar operaciones comunes de Git (opcional durante la instalación).

4. **Git Credential Manager:**
   - Un administrador de credenciales que facilita el manejo de accesos para servicios remotos como GitHub, GitLab, entre otros.

5. **Documentación:**
   - Incluye manuales y recursos locales para aprender y usar Git.

### Verificar la instalación

1. Abre una terminal (Git Bash o CMD).
2. Escribe el siguiente comando para verificar que Git se instaló correctamente:
   ```bash
   git --version
   ```
   - Deberías ver un mensaje indicando la versión instalada, por ejemplo:
     ```
     git version 2.41.0.windows.1
     ```

### Configuración inicial después de la instalación

Antes de empezar a usar Git, configura tu nombre de usuario y correo electrónico:

1. **Configurar el nombre de usuario:**
   ```bash
   git config --global user.name "Tu Nombre"
   ```

2. **Configurar el correo electrónico:**
   ```bash
   git config --global user.email "tu_email@example.com"
   ```

3. **Verificar la configuración:**
   ```bash
   git config --list
   ```
   - Esto mostrará la configuración actual, incluyendo el nombre de usuario y correo electrónico.

---

## Comandos básicos en la terminal

Antes de trabajar con Git, es importante familiarizarse con comandos básicos de la terminal que te permiten navegar y gestionar archivos y directorios. Estos comandos son esenciales para crear, mover y visualizar archivos antes de empezar a versionarlos con Git.

---

### **1. Navegación entre directorios**
   - **Cambiar de directorio:**
     ```bash
     cd nombre_del_directorio
     ```
     - Ejemplo: Para entrar en una carpeta llamada `proyecto`:
       ```bash
       cd proyecto
       ```
   - **Volver al directorio anterior:**
     ```bash
     cd ..
     ```
   - **Ir al directorio raíz:**
     ```bash
     cd /
     ```

---

### **2. Listar archivos y directorios**
   - **Mostrar el contenido del directorio actual:**
     ```bash
     ls
     ```
   - **Listar archivos con detalles adicionales:**
     ```bash
     ls -l
     ```
   - **Mostrar también archivos ocultos (como `.git`):**
     ```bash
     ls -a
     ```

---

### **3. Crear archivos y directorios**
   - **Crear un archivo vacío:**
     ```bash
     touch nombre_del_archivo
     ```
     - Ejemplo: Crear un archivo `hello_git.py`:
       ```bash
       touch hello_git.py
       ```
   - **Crear un directorio:**
     ```bash
     mkdir nombre_del_directorio
     ```
     - Ejemplo: Crear una carpeta llamada `mi_proyecto`:
       ```bash
       mkdir mi_proyecto
       ```

---

### **4. Ver el contenido de un archivo**
   - **Mostrar el contenido de un archivo en la terminal:**
     ```bash
     cat nombre_del_archivo
     ```
   - Ejemplo:
     ```bash
     cat hello_git.py
     ```

---

### **5. Eliminar archivos y directorios**
   - **Eliminar un archivo:**
     ```bash
     rm nombre_del_archivo
     ```
   - **Eliminar un directorio vacío:**
     ```bash
     rmdir nombre_del_directorio
     ```
   - **Eliminar un directorio con contenido:**
     ```bash
     rm -r nombre_del_directorio
     ```

---

### **6. Mover y renombrar archivos**
   - **Mover un archivo a otro directorio:**
     ```bash
     mv nombre_del_archivo ruta/destino
     ```
     - Ejemplo: Mover `hello_git.py` a la carpeta `src`:
       ```bash
       mv hello_git.py src/
       ```
   - **Renombrar un archivo:**
     ```bash
     mv nombre_original nuevo_nombre
     ```
     - Ejemplo: Renombrar `hello_git.py` a `main.py`:
       ```bash
       mv hello_git.py main.py
       ```

---

### **7. Limpiar la terminal**
   - **Limpiar la pantalla de la terminal:**
     ```bash
     clear
     ```

---

### **8. Ver la ubicación actual**
   - **Mostrar el directorio actual en el que estás trabajando:**
     ```bash
     pwd
     ```
     - Ejemplo de salida:
       ```
       /home/usuario/proyecto
       ```

---

## Primeros comandos en Git

En esta sección aprenderás los comandos más básicos y esenciales de Git para iniciar un proyecto, gestionar el estado del repositorio y navegar por el historial de cambios.

---

### **1. Inicializar un repositorio: `git init`**

El comando `git init` convierte una carpeta en un repositorio de Git. Esto crea un directorio oculto llamado `.git` que almacenará toda la información del control de versiones.

#### Uso:
```bash
git init
```

#### Resultado:
- El directorio actual estará listo para usar Git.
- Aparece un mensaje como:
  ```
  Initialized empty Git repository in /ruta/a/tu/proyecto/.git/
  ```

---

### **2. Añadir archivos al área de preparación: `git add`**

El comando `git add` prepara archivos para el próximo commit. Esto los mueve al área de preparación (staging area).

#### Uso:
- Añadir un archivo específico:
  ```bash
  git add nombre_del_archivo
  ```
- Añadir todos los archivos del directorio:
  ```bash
  git add .
  ```

---

### **3. Ver el estado del repositorio: `git status`**

Este comando muestra el estado actual del repositorio, incluyendo:
- Archivos nuevos no rastreados.
- Archivos que han sido modificados.
- Archivos listos para ser confirmados.

#### Uso:
```bash
git status
```

#### Resultado:
- Indica qué archivos están en cada estado. Por ejemplo:
  ```
  On branch main
  No commits yet
  Untracked files:
    (use "git add <file>..." to include in what will be committed)
    hello_git.py
  ```

---

### **4. Crear un commit: `git commit`**

El comando `git commit` guarda los cambios preparados en el área de preparación (staging area) en el historial de Git. Cada commit debe tener un mensaje descriptivo.

#### Uso:
- Crear un commit con un mensaje:
  ```bash
  git commit -m "Mensaje descriptivo"
  ```

---

### **5. Ver el historial de commits: `git log`**

Este comando muestra una lista de los commits realizados, incluyendo detalles como:
- El identificador único (hash) del commit.
- Autor del commit.
- Fecha y mensaje asociado.

#### Uso:
```bash
git log
```

---

### **6. Ver un log gráfico simplificado: `git log --oneline --graph --all`**

Este comando muestra el historial en un formato gráfico y resumido, incluyendo todas las ramas.

#### Uso:
```bash
git log --oneline --graph --decorate --all
```

---

### **7. Crear un alias para simplificar comandos: `git alias`**

Puedes crear accesos rápidos para comandos frecuentes o largos usando alias.

#### Uso:
- Crear un alias para un log gráfico simplificado:
  ```bash
  git config --global alias.tree "log --oneline --graph --decorate --all"
  ```
- Usar el alias creado:
  ```bash
  git tree
  ```

---

### **8. Cambiar a otro commit o rama: `git checkout`**

El comando `git checkout` permite:
1. Cambiar entre ramas.
2. Moverse a un commit específico para revisar su contenido.
3. Restaurar un archivo a su estado en un commit previo.

#### Uso:
- Cambiar a una rama existente:
  ```bash
  git checkout nombre_rama
  ```
- Moverse a un commit específico:
  ```bash
  git checkout commit_hash
  ```
  - **Nota:** El `commit_hash` es el identificador único del commit (los primeros 7 caracteres suelen ser suficientes).
- Restaurar un archivo modificado:
  ```bash
  git checkout -- nombre_del_archivo
  ```

---

### **9. Restablecer cambios: `git reset`**

El comando `git reset` permite deshacer cambios en el historial de commits o en el área de preparación (staging area).

#### Modos comunes:
1. **Restablecer el área de preparación:**
   - Mueve los archivos del área de preparación (staging area) a un estado no preparado (unstaged).
   ```bash
   git reset nombre_del_archivo
   ```

2. **Restablecer al commit anterior (sin perder cambios locales):**
   - Deshace el último commit, pero mantiene los archivos en tu directorio.
   ```bash
   git reset --soft HEAD~1
   ```

3. **Restablecer al commit anterior (eliminando cambios locales):**
   - Deshace el último commit y elimina los cambios del área de trabajo.
   ```bash
   git reset --hard HEAD~1
   ```

4. **Mover el HEAD a un commit específico:**
   ```bash
   git reset --hard commit_hash
   ```

#### Precaución:
- Usar `--hard` eliminará los cambios no confirmados. Asegúrate de que no hay archivos importantes sin guardar antes de usarlo.

---


### **Capítulo: Ignorar archivos con `.gitignore`**

El archivo `.gitignore` te permite especificar qué archivos o directorios Git debe ignorar. Esto es útil para evitar que archivos temporales, configuraciones locales o datos sensibles sean incluidos en el repositorio.

#### **Creación de un archivo `.gitignore`**
1. Crea un archivo llamado `.gitignore` en la raíz del repositorio:
   ```bash
   touch .gitignore
   ```

2. Abre el archivo `.gitignore` y agrega las rutas o patrones de archivos que deseas ignorar. Ejemplo:
   ```gitignore
   # Ignorar carpetas
   /node_modules/
   /build/

   # Ignorar archivos de configuración
   .env
   config.local.json

   # Ignorar archivos de sistema
   .DS_Store
   Thumbs.db
   ```

3. Añade el archivo `.gitignore` al control de versiones:
   ```bash
   git add .gitignore
   git commit -m "Añade archivo .gitignore"
   ```

#### **Notas importantes**
- **Archivos ya versionados:** Los archivos que ya fueron añadidos al repositorio antes de crear el archivo `.gitignore` no serán ignorados automáticamente. Para eliminarlos del seguimiento:
   ```bash
   git rm --cached nombre_del_archivo
   ```
- **Uso de comodines:**
  - `*.log` ignora todos los archivos con extensión `.log`.
  - `build/` ignora el directorio `build` completo.

#### **Verificación**
- Comprueba qué archivos están siendo ignorados:
   ```bash
   git status
   ```

---

### **Capítulo: Comparar cambios con `git diff`**

El comando `git diff` es fundamental para inspeccionar los cambios realizados en tus archivos antes de confirmarlos con un commit. Te ayuda a identificar qué líneas han cambiado y revisar su impacto.

#### **Uso básico**
- Ver los cambios en el área de trabajo (sin preparar):
   ```bash
   git diff
   ```

#### **Comparaciones avanzadas**
1. **Ver diferencias en el área de preparación (staging area):**
   ```bash
   git diff --staged
   ```

2. **Comparar un archivo específico:**
   ```bash
   git diff nombre_del_archivo
   ```

3. **Comparar con un commit específico:**
   ```bash
   git diff commit_hash
   ```

#### **Ejemplo de salida**
Cuando ejecutas `git diff`, obtendrás una salida similar a esta:
```diff
diff --git a/archivo.txt b/archivo.txt
index 83db48f..f735e3b 100644
--- a/archivo.txt
+++ b/archivo.txt
@@ -1,3 +1,3 @@
-Hola Mundo
+Hola Git
```
- **`-`**: Indica las líneas eliminadas.
- **`+`**: Indica las líneas añadidas.

#### **Ejemplo práctico**
1. Haz cambios en un archivo:
   ```bash
   echo "print('Hola Mundo')" > hola.py
   git add hola.py
   echo "print('Hola Git')" > hola.py
   ```

2. Verifica los cambios realizados:
   ```bash
   git diff hola.py
   ```

---
Aquí tienes el capítulo actualizado, incorporando información sobre las ramas, sus beneficios y cómo interactúan con los comandos relevantes:

---

### **Capítulo: Desplazamiento por la rama y gestión del historial**

En Git, **las ramas** son fundamentales para trabajar en paralelo, permitiéndote desarrollar nuevas características, corregir errores o experimentar sin afectar el código principal. Este capítulo cubre cómo moverte entre commits y ramas, además de deshacer y recuperar cambios.

---

#### **¿Qué es una rama?**

Una rama en Git es un puntero móvil que apunta a un commit. Por defecto, Git crea una rama principal llamada `main` o `master`. 

- Las ramas te permiten **trabajar en paralelo** en diferentes versiones del proyecto sin interferir con el código principal.
- Cada rama tiene su propio historial de commits y puede fusionarse con otras ramas cuando el trabajo esté listo.

---

### **Beneficios de usar ramas**

1. **Trabajo aislado**:
   - Cada rama puede enfocarse en una característica o tarea específica sin afectar el código principal.

2. **Colaboración**:
   - Diferentes miembros del equipo pueden trabajar en diferentes ramas simultáneamente.

3. **Historial limpio**:
   - Las ramas permiten mantener un historial claro al fusionar cambios importantes con el código principal.

4. **Experimentos seguros**:
   - Puedes crear ramas para probar ideas nuevas sin temor a romper el proyecto principal.

---

### **Conceptos clave: `HEAD` y `main`**

1. **`HEAD`**:
   - Es el puntero que indica el commit actual en el que estás trabajando.
   - Cambia al moverte entre commits o ramas.

2. **`main`**:
   - Es la rama principal del proyecto en la que normalmente se mantiene el código de producción.

---

### **Comandos para trabajar con ramas**

#### Crear una nueva rama:
```bash
git branch nombre_rama
```

#### Cambiar a otra rama:
```bash
git checkout nombre_rama
```

#### Crear y cambiar a una nueva rama al mismo tiempo:
```bash
git checkout -b nombre_rama
```

#### Listar todas las ramas:
```bash
git branch
```

#### Renombrar una rama (por ejemplo, de `master` a `main`):
```bash
git branch -m main
```

---

### **Navegar por el historial con `git checkout`**

El comando `git checkout` te permite:
1. Cambiar entre ramas.
2. Moverte a un commit específico.
3. Restaurar archivos individuales al estado del último commit.

#### Uso básico:
1. **Cambiar a otra rama:**
   ```bash
   git checkout nombre_rama
   ```

2. **Moverse a un commit específico:**
   ```bash
   git checkout commit_hash
   ```
   - Esto te sitúa en un estado de **detached HEAD**, donde puedes inspeccionar el commit pero no realizar cambios directamente en una rama.

3. **Restaurar un archivo al último commit:**
   ```bash
   git checkout -- nombre_archivo
   ```

---

### **Deshacer cambios con `git reset --hard`**

El comando `git reset` te permite deshacer cambios en tu historial. Con `--hard`, todos los cambios no guardados serán descartados.

#### Uso básico:
1. **Volver al último commit:**
   ```bash
   git reset --hard
   ```

2. **Moverse a un commit anterior:**
   ```bash
   git reset --hard commit_hash
   ```

#### Precaución:
- Usar `--hard` elimina cualquier cambio no confirmado. Úsalo solo cuando estés seguro de que no necesitas esos archivos.

---

### **Recuperar commits eliminados con `git reflog`**

El comando `git reflog` registra todos los movimientos del puntero `HEAD`, incluidos resets y checkouts. Es útil para recuperar commits que parecían perdidos.

#### Uso básico:
1. **Ver el historial del `HEAD`:**
   ```bash
   git reflog
   ```

   Salida de ejemplo:
   ```
   a3d9f00 (HEAD -> main) HEAD@{0}: commit: Añade un archivo
   8c92d01 HEAD@{1}: reset: moving to HEAD~1
   f7b1c92 HEAD@{2}: checkout: moving to main
   ```

2. **Recuperar un commit perdido:**
   ```bash
   git checkout commit_hash
   ```

3. **Volver a un estado anterior:**
   ```bash
   git reset --hard HEAD@{n}
   ```
   - Donde `n` es la posición en el reflog.

#### Crear una nueva rama para guardar un commit recuperado:
```bash
git branch nombre_rama commit_hash
git checkout nombre_rama
```

---

### **Ejemplo práctico: Trabajo con ramas y recuperación**

1. Crea y cambia a una nueva rama:
   ```bash
   git checkout -b feature_nueva
   echo "print('Nueva característica')" > nueva_funcion.py
   git add nueva_funcion.py
   git commit -m "Añade nueva función"
   ```

2. Cambia de nuevo a la rama principal:
   ```bash
   git checkout main
   ```

3. Recupera un commit perdido:
   ```bash
   git reflog
   git checkout commit_hash
   ```

4. Fusiona la rama de la nueva característica al `main` (se verá más adelante):
   ```bash
   git merge feature_nueva
   ```

---

### Resumen de comandos clave:
| Comando                           | Descripción                                       |
|-----------------------------------|---------------------------------------------------|
| `git branch nombre_rama`          | Crear una nueva rama.                            |
| `git checkout nombre_rama`        | Cambiar a otra rama.                             |
| `git checkout commit_hash`        | Moverse a un commit específico.                  |
| `git reset --hard commit_hash`    | Volver a un commit eliminando cambios no guardados. |
| `git reflog`                      | Ver el historial del puntero `HEAD`.             |
| `git branch -m nuevo_nombre`      | Renombrar una rama existente.                    |


```

### **Capítulo: Uso de etiquetas en Git (`git tag`)**

Las etiquetas o "tags" en Git son útiles para marcar puntos importantes en el historial del repositorio. Generalmente, se utilizan para identificar versiones, hitos o estados específicos de un proyecto.

---

### **¿Qué es un tag en Git?**

- **Definición:** Un tag (etiqueta) es un marcador estático que apunta a un commit específico en el historial.
- **Usos comunes:**
  - Marcar versiones de un proyecto (ejemplo: `v1.0.0`).
  - Señalar puntos de referencia en el desarrollo.
  - Facilitar la navegación y el manejo de versiones en producción.

---

### **Creación y uso de etiquetas**

#### **1. Crear un tag sencillo**
Para etiquetar el commit actual:
```bash
git tag nombre_tag
```

#### **2. Crear un tag con anotación**
Incluye un mensaje descriptivo y metadatos adicionales:
```bash
git tag -a nombre_tag -m "Mensaje del tag"
```

#### **3. Listar todos los tags**
Para ver las etiquetas creadas:
```bash
git tag
```

#### **4. Moverse a un tag específico**
Con el comando `git checkout`, puedes desplazarte al commit asociado a un tag:
```bash
git checkout nombre_tag
```

---

### **Ejemplo práctico de etiquetas**

1. **Crear una etiqueta:**
   ```bash
   git tag clase_1
   ```

   Esto crea una referencia llamada `clase_1` apuntando al commit actual. Si verificas con `git log`, verás algo como:
   ```
   commit_hash (HEAD -> main, tag: clase_1)
   ```

2. **Avanzar en el proyecto:**
   Añade un archivo nuevo y realiza un commit:
   ```bash
   echo "print('Hello Git 3')" > hello_git_3.py
   git add .
   git commit -m "Añade hello_git_3.py"
   ```

   Ahora, el `HEAD` apunta al nuevo commit, pero el tag `clase_1` permanece en el commit anterior.

3. **Moverse a un tag específico:**
   Usa el siguiente comando para regresar al commit etiquetado:
   ```bash
   git checkout clase_1
   ```

   El puntero `HEAD` cambiará al commit asociado al tag.

4. **Volver al final de la rama:**
   ```bash
   git checkout main
   ```

---

### **Beneficios de usar etiquetas**

1. **Referencias rápidas y claras:**
   - Los tags son útiles para marcar versiones importantes como `v1.0.0` o hitos como `release_candidate`.

2. **Fácil navegación:**
   - Permiten moverte a puntos específicos del historial sin necesidad de recordar hashes largos de commits.

3. **Gestión de versiones:**
   - En proyectos colaborativos, los tags ayudan a identificar exactamente qué versión del código se está utilizando.

---

### **Resumen de comandos clave**

| Comando                    | Descripción                                   |
|----------------------------|-----------------------------------------------|
| `git tag nombre_tag`       | Crear una etiqueta ligera.                   |
| `git tag -a nombre_tag -m` | Crear una etiqueta anotada con un mensaje.   |
| `git tag`                  | Listar todas las etiquetas existentes.       |
| `git checkout nombre_tag`  | Moverse al commit asociado a una etiqueta.   |

---


### **Capítulo: Gestión de ramas con `git branch` y `git switch`**

Las ramas son una característica clave de Git que permiten trabajar en paralelo en diferentes partes de un proyecto sin afectar la rama principal. Este capítulo explica cómo crear, gestionar y moverte entre ramas usando los comandos `git branch` y `git switch`.

---

### **¿Qué es una rama en Git?**

- **Definición:** Una rama en Git es un puntero móvil que apunta a un commit específico.
- **Por defecto:** Al inicializar un repositorio, se crea una rama principal llamada `main`.
- **Uso:** Las ramas permiten trabajar en diferentes características, correcciones de errores o experimentos, manteniendo el código principal intacto.

---

### **Beneficios de usar ramas**

1. **Trabajo aislado:**
   - Cada rama es independiente, lo que permite desarrollar nuevas características sin afectar el código estable.

2. **Colaboración eficiente:**
   - Varios miembros del equipo pueden trabajar en diferentes ramas al mismo tiempo.

3. **Historial limpio:**
   - Las ramas facilitan la integración de cambios importantes sin saturar la historia principal.

4. **Experimentación segura:**
   - Permiten probar ideas nuevas sin riesgo de dañar el proyecto principal.

---

### **Gestión de ramas con `git branch`**

#### **1. Crear una nueva rama**
```bash
git branch nombre_rama
```

- Esto crea una nueva rama apuntando al mismo commit que la rama actual, pero no cambia automáticamente a esa rama.

#### **2. Listar todas las ramas**
```bash
git branch
```

- La rama activa estará marcada con un asterisco `*`.

#### **3. Renombrar una rama**
```bash
git branch -m nombre_nuevo
```

- Si estás en la rama que deseas renombrar, no necesitas especificar el nombre actual.

#### **4. Eliminar una rama**
```bash
git branch -d nombre_rama
```

- Esto elimina una rama local. Si no estás seguro de querer eliminarla, Git te advertirá si los cambios no han sido fusionados.

#### **5. Forzar la eliminación de una rama**
```bash
git branch -D nombre_rama
```

---

### **Moverse entre ramas con `git switch`**

#### **1. Cambiar a una rama existente**
```bash
git switch nombre_rama
```

#### **2. Crear y cambiar a una nueva rama**
```bash
git switch -c nombre_nueva_rama
```

- Esto combina la creación de una rama (`git branch`) y el cambio a esa rama (`git switch`).

---

### **Flujo básico de trabajo con ramas**

1. **Crea una nueva rama para trabajar en una característica:**
   ```bash
   git branch feature_nueva
   ```

2. **Cambia a la nueva rama:**
   ```bash
   git switch feature_nueva
   ```

3. **Haz cambios en la rama y realiza commits:**
   ```bash
   echo "print('Nueva característica')" > nueva_funcion.py
   git add nueva_funcion.py
   git commit -m "Añade nueva característica"
   ```

4. **Vuelve a la rama principal:**
   ```bash
   git switch main
   ```

5. **Elimina la rama después de fusionarla:**
   ```bash
   git branch -d feature_nueva
   ```

---

### **Comandos útiles para trabajar con ramas**

| Comando                             | Descripción                                          |
|-------------------------------------|------------------------------------------------------|
| `git branch nombre_rama`            | Crear una nueva rama.                                |
| `git branch`                        | Listar todas las ramas.                             |
| `git branch -m nuevo_nombre`        | Renombrar una rama.                                  |
| `git branch -d nombre_rama`         | Eliminar una rama local.                             |
| `git branch -D nombre_rama`         | Forzar la eliminación de una rama local.            |
| `git switch nombre_rama`            | Cambiar a una rama existente.                       |
| `git switch -c nombre_rama`         | Crear y cambiar a una nueva rama.                   |

---

### **Ejemplo práctico: Creación y gestión de ramas**

1. **Crear una nueva rama para una característica:**
   ```bash
   git branch feature_login
   git switch feature_login
   ```

2. **Desarrollar en la nueva rama:**
   ```bash
   echo "print('Página de login')" > login.py
   git add login.py
   git commit -m "Añade página de login"
   ```

3. **Volver a la rama principal:**
   ```bash
   git switch main
   ```

4. **Fusionar los cambios de la rama de la característica con la principal:**
   ```bash
   git merge feature_login
   ```

5. **Eliminar la rama de la característica después de fusionarla:**
   ```bash
   git branch -d feature_login
   ```

### **Capítulo: Fusionar ramas con `git merge` y resolución de conflictos**

La fusión de ramas es un aspecto clave del trabajo con Git. Con el comando `git merge`, puedes integrar los cambios de una rama en otra, permitiendo combinar el trabajo de diferentes ramas o colaboradores.

---

### **¿Qué es `git merge`?**

- **Definición:** `git merge` toma los cambios de una rama (fuente) y los combina con la rama activa (destino).
- **Uso común:** Fusionar ramas después de completar una característica, corrección de errores o trabajo colaborativo.

---

### **Tipos de fusión**

1. **Fast-forward merge (avance rápido):**
   - Ocurre cuando la rama destino no tiene cambios adicionales respecto a la fuente.
   - La rama destino simplemente avanza al commit de la fuente.

2. **Three-way merge (fusión a tres bandas):**
   - Se realiza cuando la rama destino tiene cambios propios que necesitan combinarse con los de la fuente.
   - Git crea un nuevo commit que combina ambos historiales.

---

### **Flujo básico de fusión**

1. **Crea y trabaja en una nueva rama:**
   ```bash
   git branch feature_nueva
   git switch feature_nueva
   echo "Nueva funcionalidad" > funcionalidad.txt
   git add funcionalidad.txt
   git commit -m "Añade nueva funcionalidad"
   ```

2. **Cambia de nuevo a la rama principal (`main`):**
   ```bash
   git switch main
   ```

3. **Fusiona la rama `feature_nueva` en `main`:**
   ```bash
   git merge feature_nueva
   ```

4. **Elimina la rama fusionada (opcional):**
   ```bash
   git branch -d feature_nueva
   ```

---

### **Conflictos en `git merge`**

#### **¿Qué es un conflicto?**
Un conflicto ocurre cuando Git no puede combinar automáticamente los cambios de dos ramas. Esto suele suceder cuando:
- Dos ramas modifican la misma línea de un archivo.
- Se eliminan o cambian archivos de manera contradictoria.

#### **Cómo identificar un conflicto**
Al ejecutar un `git merge`, Git mostrará un mensaje indicando los conflictos, como:
```
CONFLICT (content): Merge conflict in archivo.txt
Automatic merge failed; fix conflicts and then commit the result.
```

Al ejecutar `git status`, verás los archivos en conflicto:
```
Unmerged paths:
  (both modified): archivo.txt
```

---

### **Resolución de conflictos**

1. **Abrir los archivos en conflicto:**
   - Busca las secciones marcadas por Git con `<<<<<<`, `=======` y `>>>>>>`:
     ```text
     <<<<<<< HEAD
     Cambio en la rama principal.
     =======
     Cambio en la rama feature_nueva.
     >>>>>>> feature_nueva
     ```
   - Edita manualmente estas secciones para elegir o combinar los cambios.

2. **Marcar el archivo como resuelto:**
   ```bash
   git add archivo.txt
   ```

3. **Completar la fusión:**
   ```bash
   git commit
   ```

---

### **Ejemplo práctico de resolución de conflictos**

1. **Crea una situación de conflicto:**
   - En la rama `main`:
     ```bash
     echo "Línea en main" > archivo.txt
     git add archivo.txt
     git commit -m "Añade línea en main"
     ```

   - En la rama `feature_conflicto`:
     ```bash
     git switch -c feature_conflicto
     echo "Línea en feature_conflicto" > archivo.txt
     git add archivo.txt
     git commit -m "Añade línea en feature_conflicto"
     ```

2. **Fusiona las ramas:**
   - Cambia a `main` y fusiónala con `feature_conflicto`:
     ```bash
     git switch main
     git merge feature_conflicto
     ```

   - Git detectará el conflicto:
     ```
     CONFLICT (content): Merge conflict in archivo.txt
     ```

3. **Resuelve el conflicto:**
   - Edita `archivo.txt` para resolver el conflicto:
     ```text
     Línea en main
     Línea en feature_conflicto
     ```
   - Marca el archivo como resuelto:
     ```bash
     git add archivo.txt
     ```

4. **Completa la fusión:**
   ```bash
   git commit -m "Resuelve conflicto entre main y feature_conflicto"
   ```

---

### **Opciones útiles para manejar conflictos**

- **Abortar una fusión:**
  Si decides no continuar con la fusión:
  ```bash
  git merge --abort
  ```

- **Ver conflictos con mayor claridad:**
  Utiliza herramientas gráficas para resolver conflictos, como:
  ```bash
  git mergetool
  ```

---

### **Resumen de comandos clave**

| Comando                       | Descripción                                           |
|-------------------------------|-------------------------------------------------------|
| `git merge nombre_rama`       | Fusionar una rama con la actual.                     |
| `git merge --abort`           | Abortar una fusión en curso.                         |
| `git status`                  | Ver archivos en conflicto tras una fusión.           |
| `git add archivo.txt`         | Marcar un archivo en conflicto como resuelto.        |
| `git commit`                  | Completar la fusión después de resolver conflictos.  |
| `git mergetool`               | Abrir una herramienta gráfica para resolver conflictos. |

---
### **Capítulo: Uso de `git stash`**

`git stash` es una herramienta útil en Git que permite guardar temporalmente los cambios no confirmados en el área de trabajo, para que puedas cambiar de contexto sin perder tu progreso.

---

### **¿Qué es `git stash`?**

- **Definición:** `git stash` guarda tus cambios en un "almacén" temporal (stash) y deja tu área de trabajo limpia.
- **Uso común:**
  - Interrumpir el trabajo actual para cambiar de rama.
  - Preparar el repositorio para aplicar un parche o realizar pruebas.
  - Mantener cambios locales mientras sincronizas con el repositorio remoto.

---

### **Comandos básicos de `git stash`**

#### **1. Guardar los cambios en el stash**
```bash
git stash
```

- Guarda los cambios no confirmados y limpia el área de trabajo.
- Opcionalmente, puedes añadir un mensaje descriptivo:
  ```bash
  git stash push -m "Cambios en la funcionalidad X"
  ```

#### **2. Ver las entradas en el stash**
```bash
git stash list
```

- Muestra las entradas guardadas, por ejemplo:
  ```
  stash@{0}: WIP on main: Cambios en la funcionalidad X
  stash@{1}: WIP on feature_branch: Corrección de errores
  ```

#### **3. Recuperar los cambios del stash**
- **Aplicar los cambios y mantenerlos en el stash:**
  ```bash
  git stash apply stash@{n}
  ```
  (Reemplaza `stash@{n}` con el índice del stash deseado).

- **Aplicar los cambios y eliminarlos del stash:**
  ```bash
  git stash pop
  ```

#### **4. Eliminar entradas del stash**
- **Eliminar una entrada específica:**
  ```bash
  git stash drop stash@{n}
  ```

- **Eliminar todas las entradas del stash:**
  ```bash
  git stash clear
  ```

---

### **Flujo de trabajo con `git stash`**

#### **1. Guardar cambios en progreso**
Supongamos que estás trabajando en la rama `main` y necesitas cambiar a otra rama, pero tienes cambios sin confirmar.

```bash
git stash
```

Tu área de trabajo estará limpia y podrás cambiar de rama:
```bash
git switch feature_branch
```

#### **2. Recuperar cambios guardados**
Cuando regreses a la rama original, puedes recuperar los cambios:
```bash
git stash pop
```

---

### **Opciones útiles**

1. **Guardar solo archivos modificados (sin nuevos archivos):**
   ```bash
   git stash --keep-index
   ```

2. **Guardar con nuevos archivos (`git add` pero no confirmados):**
   ```bash
   git stash -u
   ```

3. **Ver detalles de un stash específico:**
   ```bash
   git stash show stash@{n}
   ```

4. **Restaurar un stash en otra rama:**
   ```bash
   git stash branch nueva_rama stash@{n}
   ```

---

### **Ejemplo práctico**

1. Haz cambios en un archivo:
   ```bash
   echo "Trabajo en progreso" >> progreso.txt
   ```

2. Guarda los cambios con `git stash`:
   ```bash
   git stash
   ```

3. Verifica que el área de trabajo esté limpia:
   ```bash
   git status
   ```

4. Cambia de rama:
   ```bash
   git switch feature_branch
   ```

5. Vuelve a la rama original y aplica los cambios:
   ```bash
   git switch main
   git stash pop
   ```

---

### **Resumen de comandos clave**

| Comando                       | Descripción                                             |
|-------------------------------|---------------------------------------------------------|
| `git stash`                   | Guarda los cambios no confirmados en el stash.          |
| `git stash push -m "mensaje"` | Guarda los cambios con un mensaje descriptivo.          |
| `git stash list`              | Lista las entradas en el stash.                        |
| `git stash apply`             | Recupera los cambios del stash sin eliminarlos.         |
| `git stash pop`               | Recupera los cambios y los elimina del stash.           |
| `git stash drop stash@{n}`    | Elimina una entrada específica del stash.               |
| `git stash clear`             | Elimina todas las entradas del stash.                   |

---
