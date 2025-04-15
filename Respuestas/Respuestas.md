# ✅ Respuestas – Curso de Git (Módulos 1 al 8)

---

## 🟢 Módulo 1: Introducción a Git

### ✅ Conceptuales
1. Un sistema de control de versiones permite gestionar y registrar los cambios en archivos a lo largo del tiempo. Es útil para colaborar, recuperar versiones anteriores y evitar la pérdida de trabajo.
2. Git es una herramienta local de control de versiones. GitHub es una plataforma en la nube para alojar y compartir repositorios Git.
3. El área de staging es donde se colocan los archivos que van a ser incluidos en el próximo commit.

### 💻 Prácticos
4.  
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```

5.  
```bash
mkdir mi_proyecto && cd mi_proyecto
git init
```

6.  
```bash
echo "# Mi Proyecto" > README.md
git add README.md
git commit -m "Agregar README"
```

7.  
```bash
git clone https://github.com/example/test-repo.git
```

### 🛠️ Resolución de Problemas
8.  
```bash
git add archivo.txt
git commit -m "Actualizar archivo"
```

9.  
```bash
git commit --amend -m "Mensaje corregido"
```

10.  
```bash
git restore archivo.txt
```

---

## 🟡 Módulo 2: Comandos Esenciales

### ✅ Conceptuales
1. Muestra el estado actual del repositorio: archivos modificados, sin seguimiento o en staging.
2. \`git add archivo\` agrega un archivo específico. \`git add .\` agrega todos los archivos modificados.
3. Permite ver el historial de commits del repositorio.

### 💻 Prácticos
4.  
```bash
git status
```

5.  
```bash
git add archivo.txt
```

6.  
```bash
git commit -m "primer commit"
```

7.  
```bash
git log --oneline --graph --decorate
```

8.  
```bash
git diff archivo.txt
```

### 🛠️ Resolución de Problemas
9.  
```bash
git restore archivo.txt
```

10.  
```bash
git reset archivo.txt
```

---

## 🔵 Módulo 3: Ramas y Manejo de Versiones

### ✅ Conceptuales
1. Una rama es una línea independiente de desarrollo que permite trabajar en paralelo sin afectar la rama principal.
2. \`git merge\` une el historial de otra rama creando un commit de fusión; \`git rebase\` reescribe el historial para crear una línea lineal.
3. Git Flow es una estrategia de ramas estructurada para organizar el desarrollo de software.

### 💻 Prácticos
4.  
```bash
git branch feature/header
```

5.  
```bash
git checkout feature/header
```

6.  
```bash
touch header.txt
git add header.txt
git commit -m "Agregar header"
git checkout main
```

7.  
```bash
git merge feature/header
```

### 🛠️ Resolución de Problemas
8. Git mostrará los archivos en conflicto. Se resuelven manualmente, luego:  
```bash
git add archivo.conflictivo
git commit
```

9. Podrías sobrescribir cambios si otra persona ya trabajó sobre esa rama.

10.  
```bash
git revert -m 1 <hash_del_merge>
```

---
---

## 🟠 Módulo 4: Repositorios Remotos

### ✅ Conceptuales
1. El repositorio local está en tu máquina; el remoto se aloja en una plataforma como GitHub, GitLab o Bitbucket.
2. \`origin\` es el nombre por defecto que Git asigna al repositorio remoto cuando se clona o se añade por primera vez.
3. \`git fetch\` descarga los cambios remotos sin fusionarlos. \`git pull\` descarga y fusiona automáticamente.

### 💻 Prácticos
4.  
```bash
git remote add origin https://url-ficticia.git
```

5.  
```bash
echo "Nuevo archivo" > nuevo.txt
git add nuevo.txt
git commit -m "Agregar nuevo archivo"
git push origin main
```

6.  
```bash
git branch -r
```

7.  
```bash
git tag v1.0
git push origin v1.0
```

### 🛠️ Resolución de Problemas
8.  
```bash
git pull --rebase
```
(o resolver conflictos y luego \`git push\`)

9.  
```bash
git fetch --tags
```

10.  
```bash
git remote set-url origin https://nueva-url.git
```

---

## 🟣 Módulo 5: Pull Requests y Colaboración

### ✅ Conceptuales
1. Un Pull Request es una solicitud de revisión para integrar una rama a otra, generalmente a \`main\`. Se hace desde la plataforma remota.
2. Permite revisar, comentar y aprobar código antes de integrarlo, evitando errores.
3. \`Squash\` fusiona todos los commits en uno; \`Merge\` conserva el historial completo de commits de la rama.

### 💻 Prácticos
4.  
```bash
git checkout -b hotfix/footer
echo "fix" > fix.txt
git add fix.txt
git commit -m "Corrección footer"
```

5.  
```bash
git push origin hotfix/footer
```

6. Desde la interfaz de GitHub: seleccionar \`Compare & pull request\`, agregar título, descripción y crear PR.

7. En GitHub: seleccionar "Squash and merge".

### 🛠️ Resolución de Problemas
8. Resolver el conflicto en la interfaz o localmente, luego:
```bash
git add archivo.conflictivo
git commit
git push
```

9. Puede sobrescribir el historial del PR. Solo debe usarse si sabés lo que hacés y no afecta a otros.

10.  
```bash
git branch -d hotfix/footer
git push origin --delete hotfix/footer
```

---

## 🟢 Módulo 6: Técnicas Avanzadas

### ✅ Conceptuales
1. \`git cherry-pick\` aplica un commit específico de otra rama sobre la actual.
2. \`git stash\` guarda temporalmente los cambios no confirmados para poder cambiarnos de rama o limpiar el working directory.
3. \`git commit --amend\` modifica el último commit; \`git rebase -i\` permite reordenar, editar o eliminar commits múltiples.

### 💻 Prácticos
4.  
```bash
git cherry-pick <hash>
```

5.  
```bash
git stash
git checkout otra-rama
git stash pop
```

6.  
```bash
git rebase -i HEAD~3
```

7.  
```bash
git commit --amend -m "Nuevo mensaje"
```

8. En \`.gitignore`, agregar:
```
.env
```

### 🛠️ Resolución de Problemas
9.  
```bash
git add archivo_olvidado
git commit --amend --no-edit
```

10.  
```bash
git stash list
git stash apply stash@{1}
```

---

## 🔴 Módulo 7: Recuperación de Errores

### ✅ Conceptuales
1. \`git revert\` crea un nuevo commit que deshace uno anterior; \`git reset --hard\` borra commits de forma destructiva.
2. \`git reflog\` permite ver los movimientos recientes de HEAD, incluso commits perdidos por reset o rebase.
3. \`git restore\` se usa para deshacer cambios en archivos individuales, sin afectar otros.

### 💻 Prácticos
4.  
```bash
git revert abc1234
```

5.  
```bash
git restore archivo.txt
```

6.  
```bash
git reflog
git checkout <hash>
```

7.  
```bash
git reset --hard <hash>
```

### 🛠️ Resolución de Problemas
8. Usar \`git reflog\` para encontrar el commit anterior al reset y hacer:
```bash
git checkout <hash>
```

9.  
```bash
git reflog
git checkout -b rama_recuperada <hash>
```

10.  
```bash
git checkout HEAD@{3}
```

---

## 🟣 Módulo 8: Integración con Herramientas

### ✅ Conceptuales
1. Permite ver los cambios, hacer commit, resolver conflictos y navegar historial visualmente.
2. Un hook es un script que Git ejecuta automáticamente en eventos como \`pre-commit\`, \`pre-push\`, etc.
3. Sirve para verificar la autoría de los commits con una clave criptográfica (GPG), aumentando la seguridad del historial.

### 💻 Prácticos
4. Usar la pestaña "Source Control" en VS Code y hacer click en \`✓ Commit\`.

5.  
```bash
echo '#!/bin/sh\nnpm run lint || exit 1' > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit
```

6.  
```bash
ssh-keygen -t ed25519 -C "tu@email.com"
```
Luego agregar la clave pública a GitHub en Settings > SSH and GPG keys.

7.  
```bash
git blame archivo.txt
```

### 🛠️ Resolución de Problemas
8. Verificar que el archivo esté en \`.git/hooks/\`, sea ejecutable y tenga el shebang correcto.

9. Usar SSH para evitar pedir contraseña:
```bash
git remote set-url origin git@github.com:usuario/repo.git
```

10.  
```bash
git bisect start
git bisect bad
git bisect good <hash_bueno>
# Seguir instrucciones para encontrar el commit problemático
```

