# 🟡 Módulo 2: Comandos Esenciales de Git

## 6. Creación y clonación de repositorios

### Crear un repositorio local

\`\`\`bash
git init
\`\`\`

Crea un nuevo repositorio vacío en el directorio actual.

### Clonar un repositorio remoto

\`\`\`bash
git clone <url-del-repositorio>
\`\`\`

Ejemplo:

\`\`\`bash
git clone https://github.com/user/proyecto.git
\`\`\`

Esto descarga el historial completo del proyecto a tu máquina.

---

## 7. Seguimiento de cambios en archivos

### Ver el estado del repositorio

\`\`\`bash
git status
\`\`\`

Muestra los archivos modificados, eliminados o sin seguimiento.

### Agregar archivos al staging

\`\`\`bash
git add archivo.txt
git add .  # Agrega todos los archivos modificados
\`\`\`

### Confirmar los cambios (commit)

\`\`\`bash
git commit -m "Mensaje descriptivo del cambio"
\`\`\`

Guarda una nueva versión en el historial del repositorio.

---

## 8. Inspección del historial de cambios

### Ver historial de commits

\`\`\`bash
git log
\`\`\`

Para una vista más compacta y visual:

\`\`\`bash
git log --oneline --graph --decorate --all
\`\`\`

### Ver detalles de un commit

\`\`\`bash
git show <id-del-commit>
\`\`\`

---

## 9. Diferencias entre versiones

### Ver cambios no confirmados

\`\`\`bash
git diff
\`\`\`

Comparar contra el último commit:

\`\`\`bash
git diff HEAD
\`\`\`

Comparar un archivo específico:

\`\`\`bash
git diff archivo.txt
\`\`\`

---

## 10. Deshacer cambios

### Restaurar un archivo al último commit

\`\`\`bash
git restore archivo.txt
\`\`\`

### Quitar archivos del staging

\`\`\`bash
git reset archivo.txt
\`\`\`

### Volver un archivo a su estado anterior

\`\`\`bash
git checkout -- archivo.txt
\`\`\`

> ⚠️ `git checkout` en este contexto es equivalente a `restore`, pero su uso está siendo reemplazado por comandos más explícitos como `git switch` y `git restore`.

---

> 🎯 Estos comandos forman la base para gestionar versiones, colaborar con otros y mantener un control riguroso del código fuente.
