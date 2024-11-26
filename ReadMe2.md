### **Capítulo: Introducción a GitHub, primeros pasos y autenticación SSH**

---

### **¿Qué es GitHub y cómo se relaciona con Git?**

GitHub es una plataforma basada en la nube que utiliza Git como sistema de control de versiones. Permite a los desarrolladores:
- Subir y gestionar proyectos de código de forma remota.
- Trabajar en colaboración con otros desarrolladores.
- Guardar el historial de cambios de un proyecto de manera segura.

**Diferencias clave entre Git y GitHub:**
- **Git:** Herramienta local para gestionar versiones de un proyecto.
- **GitHub:** Plataforma en la nube para alojar repositorios y colaborar en proyectos utilizando Git.

---

### **Primeros pasos en GitHub**

1. **Crear una cuenta en GitHub:**
   - Regístrate en [github.com](https://github.com).
   - Proporciona un nombre de usuario, correo electrónico y contraseña.
   - Personaliza tu perfil añadiendo una foto y una descripción.

2. **Conceptos básicos:**
   - **Repositorio:** Carpeta en GitHub donde se almacena tu proyecto.
   - **README:** Archivo de texto que sirve como introducción o documentación del proyecto.
   - **Público vs Privado:** Los repositorios públicos son visibles para todos, mientras que los privados son accesibles solo para ti y los colaboradores que invites.

3. **Crear un repositorio:**
   - Haz clic en el botón **"New"** en la pestaña de repositorios.
   - Proporciona un nombre, descripción y configuración inicial, como añadir un archivo `README` o `.gitignore`.

---

### **Sincronización entre Git local y GitHub**

GitHub actúa como un punto central para que múltiples desarrolladores colaboren en un proyecto. Este flujo incluye:
1. Trabajar en local utilizando Git para gestionar el proyecto.
2. Subir los cambios a GitHub para que otros puedan acceder y colaborar.
3. Descargar cambios de otros colaboradores desde GitHub.

---

### **Configuración de SSH en GitHub para Windows**

La configuración de SSH en Windows permite conectar tu ordenador local a GitHub de manera segura y sin necesidad de introducir tu usuario y contraseña cada vez que interactúes con un repositorio. Aquí te explicamos el proceso paso a paso para Windows.

---

### **1. Instalar Git y Git Bash**

Antes de comenzar, asegúrate de tener Git instalado en tu ordenador:
1. Descarga e instala Git desde [git-scm.com](https://git-scm.com/).
2. Durante la instalación, selecciona Git Bash como terminal predeterminada para trabajar con Git.

Para verificar la instalación, abre Git Bash y escribe:
```bash
git --version
```
Debería mostrar la versión de Git instalada.

---

### **2. Generar claves SSH**

Para establecer una conexión segura con GitHub, necesitas generar un par de claves SSH: una pública y una privada.

1. **Abre Git Bash** en tu ordenador.
2. Ejecuta el siguiente comando para generar una nueva clave SSH:
   ```bash
   ssh-keygen -t ed25519 -C "tu_email@ejemplo.com"
   ```
   - Sustituye `"tu_email@ejemplo.com"` por el correo electrónico asociado a tu cuenta de GitHub.
   - Si tu sistema no soporta `ed25519`, usa RSA:
     ```bash
     ssh-keygen -t rsa -b 4096 -C "tu_email@ejemplo.com"
     ```

3. **Guarda la clave SSH:**
   - Cuando se te pida una ubicación para guardar el archivo, presiona `Enter` para aceptar la ubicación predeterminada:
     ```
     /c/Users/TuUsuario/.ssh/id_ed25519
     ```
   - Opcionalmente, puedes añadir una contraseña para mayor seguridad. Si no deseas una, simplemente presiona `Enter`.

4. Una vez completado, las claves se almacenarán en:
   ```
   C:\Users\TuUsuario\.ssh\
   ```

---

### **3. Añadir la clave SSH al agente SSH**

El agente SSH administra las claves SSH para ti, asegurando que las conexiones se establezcan correctamente.

1. Inicia el agente SSH ejecutando:
   ```bash
   eval "$(ssh-agent -s)"
   ```
   Esto debería devolver algo como:
   ```
   Agent pid 1234
   ```

2. Añade tu clave privada al agente SSH:
   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```
   Si usaste RSA, reemplaza `id_ed25519` por `id_rsa`.

---

### **4. Añadir la clave pública a GitHub**

Ahora debes informar a GitHub sobre tu clave pública para que pueda autenticar tu ordenador.

1. Copia tu clave pública:
   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```
   Esto mostrará algo como:
   ```
   ssh-ed25519 AAAAB3...TuClavePublica...Z username@ejemplo.com
   ```
   Copia todo el contenido.

2. Ve a tu perfil de GitHub:
   - Inicia sesión en [github.com](https://github.com).
   - Haz clic en tu avatar en la esquina superior derecha y selecciona **"Settings"**.
   - Ve a la sección **"SSH and GPG keys"** en el menú lateral izquierdo.
   - Haz clic en **"New SSH key"**.
   - Pega la clave pública en el campo correspondiente y dale un título descriptivo, como "Mi ordenador personal".
   - Haz clic en **"Add SSH key"**.

---

### **5. Verificar la conexión SSH**

Para asegurarte de que todo está configurado correctamente, prueba la conexión SSH con GitHub:
```bash
ssh -T git@github.com
```

Si todo está bien, verás un mensaje como:
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

Esto significa que la conexión SSH está configurada correctamente y puedes trabajar con GitHub.

---

### **6. Configurar tu repositorio para usar SSH**

1. Si tienes un repositorio local que deseas conectar a GitHub, cambia el remoto a SSH:
   ```bash
   git remote set-url origin git@github.com:usuario/nombre-repositorio.git
   ```

2. Si estás clonando un repositorio por primera vez, usa el enlace SSH proporcionado por GitHub:
   ```bash
   git clone git@github.com:usuario/nombre-repositorio.git
   ```

---

### **Ventajas de usar SSH en GitHub**

- **Seguridad:** Autenticación cifrada sin necesidad de contraseñas.
- **Eficiencia:** No necesitas ingresar credenciales cada vez que interactúas con un repositorio.
- **Escalabilidad:** Puedes configurar múltiples claves para diferentes dispositivos.

Con esta configuración, estás listo para trabajar con repositorios de GitHub de manera segura y eficiente desde Windows. 🚀

### **Trabajar con un repositorio remoto en GitHub**

#### **Subir un repositorio local a GitHub**
1. Crea un repositorio en GitHub sin inicializar archivos (`README`, `.gitignore`, etc.).
2. Conecta tu repositorio local con el remoto:
   ```bash
   git remote add origin git@github.com:username/repo-name.git
   ```
3. Sube los cambios:
   ```bash
   git push -u origin main
   ```

#### **Clonar un repositorio de GitHub**
Si deseas trabajar en un repositorio existente en GitHub:
```bash
git clone git@github.com:username/repo-name.git
```

---

### **Beneficios de usar GitHub**

- **Colaboración:** Facilita el trabajo en equipo mediante herramientas como pull requests y code reviews.
- **Seguridad:** Los proyectos están respaldados en la nube, protegiéndolos de pérdidas locales.
- **Documentación:** Añadir un archivo `README` ayuda a otros a entender el propósito y las instrucciones del proyecto.
- **Open Source:** GitHub es el hogar de miles de proyectos de código abierto.

---

### **Git Fetch y Git Pull**

En este capítulo, explicaremos los comandos `git fetch` y `git pull`, esenciales para sincronizar tu repositorio local con un repositorio remoto en Git. Ambos son herramientas clave para mantener tu trabajo actualizado y garantizar que estás trabajando con la versión más reciente del código.

---

### **1. ¿Qué son `git fetch` y `git pull`?**

#### **Git Fetch**
El comando `git fetch` descarga las actualizaciones del repositorio remoto (commits, ramas y etiquetas), pero no las integra automáticamente en tu repositorio local. Esto significa que actualiza tu copia local de la información remota, pero no modifica tu área de trabajo ni tus ramas locales.

#### **Git Pull**
El comando `git pull` realiza dos operaciones en una:
1. **`git fetch`:** Descarga las actualizaciones del repositorio remoto.
2. **`git merge`:** Fusiona automáticamente los cambios del repositorio remoto con tu rama actual.

En resumen:
- **`git fetch`:** Solo descarga cambios sin aplicarlos.
- **`git pull`:** Descarga y fusiona los cambios automáticamente.

---

### **2. Uso de `git fetch`**

#### **Sintaxis básica**
```bash
git fetch [remote]
```
- **`[remote]`:** Es el nombre del repositorio remoto. Por defecto, suele ser `origin`.

#### **Ejemplo práctico**
1. Para descargar actualizaciones del repositorio remoto sin fusionarlas:
   ```bash
   git fetch origin
   ```
2. Para ver los cambios descargados:
   ```bash
   git log origin/main
   ```
   Esto muestra los commits recientes en la rama remota `main`.

#### **¿Cuándo usar `git fetch`?**
- Si quieres revisar los cambios antes de aplicarlos.
- Cuando estás trabajando en tu rama local y no quieres mezclar cambios automáticamente.
- Para sincronizar información sobre nuevas ramas o etiquetas en el remoto.

---

### **3. Uso de `git pull`**

#### **Sintaxis básica**
```bash
git pull [remote] [branch]
```
- **`[remote]`:** Nombre del repositorio remoto (por defecto, `origin`).
- **`[branch]`:** Rama remota que deseas fusionar con tu rama actual (por defecto, la rama actual vinculada).

#### **Ejemplo práctico**
1. Para descargar y fusionar los cambios de la rama `main` del remoto:
   ```bash
   git pull origin main
   ```
2. Si solo escribes `git pull`, Git intentará hacer un pull de la rama predeterminada vinculada al remoto:
   ```bash
   git pull
   ```

#### **¿Cuándo usar `git pull`?**
- Cuando deseas obtener las últimas actualizaciones y fusionarlas rápidamente en tu rama actual.
- En equipos donde los cambios se integran con frecuencia en el remoto.

---

### **4. Diferencias clave entre `git fetch` y `git pull`**

| **Comando** | **¿Qué hace?**                               | **¿Cuándo usarlo?**                                                                                                                                 |
|-------------|---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| `git fetch` | Descarga actualizaciones pero no las aplica | Para revisar cambios remotos antes de fusionarlos, o si no deseas alterar tu área de trabajo inmediatamente.                                       |
| `git pull`  | Descarga y fusiona los cambios              | Para integrar rápidamente las actualizaciones del remoto en tu rama actual, especialmente si estás sincronizado y listo para fusionar los cambios. |

---

### **5. Consideraciones al usar `git pull`**

- **Conflictos de fusión:** Si hay cambios en tu rama local que no coinciden con los del remoto, puede ocurrir un conflicto de fusión. En ese caso, deberás resolver los conflictos manualmente.
- **Evitar errores inesperados:** Si no estás seguro de los cambios en el remoto, usa `git fetch` primero y revisa los cambios antes de ejecutar `git pull`.

---

### **6. Ejemplo completo: `git fetch` y `git pull`**

Supongamos que trabajas en la rama `main` y tu compañero ha subido cambios al remoto.

1. **Revisar los cambios sin aplicarlos (`git fetch`):**
   ```bash
   git fetch origin
   git log origin/main
   ```
   Esto muestra los commits que están en el remoto pero no en tu rama local.

2. **Aplicar los cambios (`git pull`):**
   Si decides integrar los cambios, usa:
   ```bash
   git pull origin main
   ```

3. **Resolver conflictos (si ocurren):**
   Si hay conflictos, Git los señalará. Edita los archivos afectados, resuelve los conflictos y finaliza el proceso:
   ```bash
   git add archivo_conflictivo
   git commit
   ```

---

### **7. Buenas prácticas**

- Usa `git fetch` regularmente para mantenerte informado sobre los cambios en el remoto.
- Antes de usar `git pull`, asegúrate de haber comprometido tus cambios locales para evitar conflictos innecesarios.
- En equipos grandes, comunicarte con tus compañeros antes de hacer `git pull` puede evitar problemas.

Con estos comandos, puedes mantener tu trabajo sincronizado con el remoto y colaborar eficientemente con tu equipo. 🚀