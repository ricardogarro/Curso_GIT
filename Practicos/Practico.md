# 📝 Ejercicios – Curso de Git (Módulos 1 al 8)

---

## 🟢 Módulo 1: Introducción a Git

### ✅ Conceptuales
1. ¿Qué es un sistema de control de versiones y por qué es útil en el desarrollo de software?
2. Explica la diferencia entre Git y GitHub.
3. ¿Cuál es la función del área de staging en Git?

### 💻 Prácticos
4. Instala Git en tu sistema y configura tu nombre y correo globalmente.
5. Crea un nuevo repositorio en tu máquina local llamado \`mi_proyecto\` e inicialízalo con Git.
6. Agrega un archivo \`README.md\` con una breve descripción y confírmalo.
7. Clona el repositorio \`https://github.com/example/test-repo.git\`.

### 🛠️ Resolución de Problemas
8. Ejecutaste \`git status\` y un archivo está "modificado" pero no en staging. ¿Qué hacés?
9. Hiciste un commit con mensaje incorrecto. ¿Cómo lo corregís?
10. Eliminaste un archivo y aún no hiciste commit. ¿Cómo lo recuperás?

---

## 🟡 Módulo 2: Comandos Esenciales de Git

### ✅ Conceptuales
1. ¿Qué hace el comando \`git status\`?
2. ¿Qué diferencia hay entre \`git add <archivo>\` y \`git add .\`?
3. ¿Para qué se usa \`git log\`?

### 💻 Prácticos
4. Ver el estado del repositorio.
5. Agregar un archivo específico al área de staging.
6. Confirmar los cambios con el mensaje "primer commit".
7. Ver el historial de commits en formato resumido.
8. Mostrar los cambios no confirmados de un archivo.

### 🛠️ Resolución de Problemas
9. ¿Cómo restaurar un archivo al último commit?
10. ¿Cómo eliminar un archivo del área de staging sin borrarlo?

---

## 🔵 Módulo 3: Ramas y Manejo de Versiones

### ✅ Conceptuales
1. ¿Qué es una rama en Git y para qué sirve?
2. Diferencia entre \`git merge\` y \`git rebase\`.
3. ¿Qué es Git Flow?

### 💻 Prácticos
4. Crear una nueva rama llamada \`feature/header\`.
5. Cambiarse a esa rama.
6. Hacer un commit simulado y volver a \`main\`.
7. Unir las ramas con \`merge\`.

### 🛠️ Resolución de Problemas
8. ¿Qué hacer ante un conflicto de merge?
9. ¿Qué problema puede generar el rebase en una rama compartida?
10. ¿Cómo volver atrás un merge mal hecho?

---

## 🟠 Módulo 4: Repositorios Remotos

### ✅ Conceptuales
1. ¿Qué diferencia hay entre repositorio local y remoto?
2. ¿Qué representa \`origin\`?
3. ¿Cuándo usar \`git fetch\` en lugar de \`git pull\`?

### 💻 Prácticos
4. Agregar un repositorio remoto con una URL ficticia.
5. Subir un archivo nuevo al repositorio remoto.
6. Listar ramas remotas.
7. Crear un tag y subirlo al remoto.

### 🛠️ Resolución de Problemas
8. ¿Qué hacer si \`git push\` devuelve un error de actualización no adelantada?
9. ¿Cómo sincronizar los tags remotos?
10. Cambiar la URL de un remoto existente.

---

## 🟣 Módulo 5: Pull Requests y Colaboración

### ✅ Conceptuales
1. ¿Qué es un Pull Request (PR)?
2. ¿Por qué es importante revisar los PR antes de hacer merge?
3. ¿Qué diferencia hay entre un PR con squash y uno con merge?

### 💻 Prácticos
4. Crear la rama \`hotfix/footer\` y hacer un commit.
5. Subir la rama al remoto.
6. Explicar cómo abrir un PR desde GitHub.
7. Simular la fusión de un PR con squash.

### 🛠️ Resolución de Problemas
8. Resolver un conflicto en un PR abierto.
9. ¿Qué implica hacer \`git push --force\` después de editar un PR?
10. ¿Cómo eliminar la rama de un PR fusionado?

---

## 🟢 Módulo 6: Técnicas Avanzadas

### ✅ Conceptuales
1. ¿Qué es \`git cherry-pick\`?
2. ¿Qué hace \`git stash\`?
3. ¿Diferencias entre \`git commit --amend\` y \`git rebase -i\`?

### 💻 Prácticos
4. Aplicar un commit específico desde otra rama.
5. Stashear cambios, cambiar de rama, y restaurarlos.
6. Reescribir los últimos 3 commits como uno solo.
7. Corregir el último mensaje de commit.
8. Agregar una regla a \`.gitignore\` para ignorar \`.env\`.

### 🛠️ Resolución de Problemas
9. Incorporar un archivo olvidado al último commit sin crear uno nuevo.
10. Ver la lista de stashes y aplicar uno específico.

---

## 🔴 Módulo 7: Recuperación de Errores

### ✅ Conceptuales
1. ¿Qué diferencia hay entre \`git revert\` y \`git reset --hard\`?
2. ¿Qué es \`git reflog\`?
3. ¿Cuándo usarías \`git restore\`?

### 💻 Prácticos
4. Revertir un commit.
5. Recuperar un archivo eliminado antes del commit.
6. Recuperar un commit eliminado usando \`git reflog\`.
7. Volver al estado de un commit anterior con \`git reset --hard\`.

### 🛠️ Resolución de Problemas
8. Te equivocaste con un reset destructivo. ¿Cómo recuperar tu trabajo?
9. Borraste una rama local. ¿Podés traerla de vuelta?
10. Volver al estado exacto que tenías 3 pasos atrás.

---

## 🟣 Módulo 8: Integración con Herramientas

### ✅ Conceptuales
1. ¿Qué ventajas ofrece usar Git desde VS Code?
2. ¿Qué es un hook en Git?
3. ¿Para qué sirve firmar commits con GPG?

### 💻 Prácticos
4. Usar Git desde Visual Studio Code para hacer commit.
5. Agregar un hook \`pre-commit\` que impida hacer commit si hay errores de lint.
6. Crear una clave SSH y agregarla a GitHub.
7. Ver qué usuario hizo cada línea de un archivo con \`git blame\`.

### 🛠️ Resolución de Problemas
8. El hook pre-commit no se ejecuta. ¿Qué revisás?
9. El repositorio clonado pide contraseña cada vez. ¿Cómo evitás esto con SSH?
10. ¿Cómo detectar en qué commit se introdujo un bug usando \`git bisect\`?

