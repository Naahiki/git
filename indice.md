### Índice del Curso Básico de Git y GitHub

#### **1. Introducción a Git y GitHub**
   - ¿Qué es Git?
   - ¿Qué es GitHub?
   - Diferencias entre Git y GitHub.
   - Ventajas del control de versiones.

---

#### **2. Instalación de Git**
   - Instalación de Git en Windows.
   - Configuración inicial:
     - `git config --global user.name`
     - `git config --global user.email`

---

#### **3. Comandos Básicos de la Terminal**
   - Navegación: `cd`, `pwd`
   - Creación de archivos y carpetas: `touch`, `mkdir`
   - Listar archivos: `ls`
   - Eliminar archivos y carpetas: `rm`, `rmdir`
   - Ver contenido de un archivo: `cat`

---

#### **4. Inicialización y Configuración**
   - `git init`: Crear un repositorio.
   - `git status`: Ver el estado del repositorio.
   - `.gitignore`: Ignorar archivos y carpetas.

---

#### **5. Flujo Básico de Git**
   - `git add`: Añadir archivos al área de preparación.
   - `git commit`: Guardar cambios en el historial.
   - `git log`: Ver el historial de commits.
   - `git log --oneline --graph`: Visualización gráfica del historial.

---

#### **6. Ramas en Git**
   - Crear una rama: `git branch`
   - Cambiar de rama: `git switch`
   - Crear y cambiar de rama: `git switch -c`
   - Listar ramas: `git branch`
   - Renombrar ramas: `git branch -m`

---

#### **7. Fusión de Ramas**
   - `git merge`: Fusionar cambios de una rama.
   - Tipos de merge: Fast-forward y three-way merge.
   - Resolución de conflictos:
     - `git status` para identificar conflictos.
     - `git add` para marcar archivos resueltos.
     - `git merge --abort` para cancelar una fusión.

---

#### **8. Sincronización con Repositorios Remotos**
   - `git remote add`: Conectar un repositorio local con GitHub.
   - `git push`: Subir cambios al repositorio remoto.
   - `git fetch`: Descargar cambios del repositorio remoto.
   - `git pull`: Descargar y fusionar cambios del repositorio remoto.
   - `git clone`: Clonar un repositorio.

---

#### **9. Colaboración en GitHub**
   - Crear un repositorio en GitHub.
   - `git fork`: Crear una copia de un repositorio en tu cuenta.
   - Pull Requests: Solicitar la fusión de cambios en un repositorio.

---

#### **10. Gestión Avanzada**
   - `git stash`: Guardar cambios temporalmente.
   - `git tag`: Crear etiquetas para versiones.
   - `git reflog`: Recuperar commits perdidos.

---

#### **11. Resolución de Errores y Conflictos**
   - `git reset`: Deshacer commits.
   - `git checkout`: Restaurar archivos o moverte a un commit específico.
   - `git cherry-pick`: Aplicar un commit específico a otra rama.

---

#### **12. Eliminación y Limpieza**
   - `git branch -d`: Eliminar ramas locales.
   - `git branch -D`: Forzar la eliminación de ramas locales.
   - `git push origin --delete`: Eliminar ramas remotas.
   - `git clean`: Limpiar archivos no rastreados.

---

### Índice: Introducción a GitHub y Comandos Esenciales

1. **Introducción a GitHub**
   - Diferencias entre Git y GitHub.
   - Beneficios de GitHub.

2. **Configuración de SSH**
   - Generar claves SSH: `ssh-keygen`.
   - Añadir la clave pública a GitHub.
   - Verificar la conexión: `ssh -T git@github.com`.

3. **Trabajar con Repositorios**
   - Crear un repositorio en GitHub.
   - Conectar un repositorio local: `git remote add origin`.
   - Subir cambios: `git push`.
   - Clonar un repositorio: `git clone`.

4. **Sincronización**
   - Descargar cambios sin aplicar: `git fetch`.
   - Descargar y fusionar cambios: `git pull`.

5. **Gestión de Ramas**
   - Crear ramas: `git branch`.
   - Subir ramas al remoto: `git push origin nombre_rama`.
   - Cambiar entre ramas: `git checkout`.

6. **Resolución de Problemas**
   - Resolver conflictos con `git status` y `git add`.
   - Revisión de cambios: `git log` y `git diff`. 

Este índice simplifica los pasos y comandos clave para trabajar con GitHub. 🚀