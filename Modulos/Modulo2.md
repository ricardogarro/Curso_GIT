# Módulo 2: Comandos Esenciales de Git

## 📌 Introducción
En este módulo aprenderemos los comandos fundamentales de Git para gestionar repositorios, rastrear cambios y mantener un historial de versiones. Estos comandos permiten trabajar con el código de manera eficiente y segura.

---

## 🟢 1. Creación y Clonación de Repositorios

### 🔹 Crear un Nuevo Repositorio Local
Para comenzar a utilizar Git en un proyecto, primero debemos inicializar un repositorio:

```bash
git init
```
- Este comando crea un nuevo repositorio en el directorio actual.
- Se genera un directorio oculto `.git` donde Git almacena toda la información del historial del proyecto.

### 🔹 Clonar un Repositorio Remoto
Si queremos obtener una copia de un repositorio alojado en una plataforma como GitHub, usamos:

```bash
git clone <url-del-repositorio>
```
Ejemplo:

```bash
git clone https://github.com/user/proyecto.git
```
- Descarga todo el historial del repositorio y crea una copia local.
- La carpeta creada tendrá la misma estructura del repositorio original.

---

## 🟡 2. Seguimiento de Cambios en Archivos

### 🔹 Ver el Estado del Repositorio
Para conocer qué archivos han cambiado en el repositorio, usamos:

```bash
git status
```
- Indica los archivos modificados, nuevos o eliminados.
- Muestra si hay cambios preparados para commit.

### 🔹 Agregar Archivos al Área de Staging
Antes de confirmar cambios en Git, primero los agregamos al área de staging:

```bash
git add <archivo>
```
O para agregar todos los archivos modificados:

```bash
git add .
```

### 🔹 Confirmar Cambios en el Repositorio
Para guardar los cambios en el historial de Git:

```bash
git commit -m "Descripción de los cambios"
```

Ejemplo:

```bash
git commit -m "Añadir función de autenticación"
```

- Cada commit representa un punto en la historia del proyecto.
- Se recomienda escribir mensajes de commit descriptivos y concisos.

---

## 🔵 3. Inspección del Historial de Cambios

### 🔹 Ver el Historial de Commits
Para visualizar los commits realizados en el repositorio:

```bash
git log
```

Si queremos un historial más resumido:

```bash
git log --oneline --graph --decorate --all
```

- Muestra el historial de commits en una vista compacta y visual.

### 🔹 Ver Detalles de un Commit Específico
Si necesitamos inspeccionar los cambios de un commit:

```bash
git show <id-del-commit>
```

Ejemplo:

```bash
git show 3f8b2d1
```

- Muestra las diferencias introducidas por un commit específico.

---

## 🟣 4. Comparación de Versiones

### 🔹 Ver Cambios No Confirmados
Para ver qué cambios se han realizado antes de hacer un commit:

```bash
git diff
```

Si queremos comparar un archivo específico:

```bash
git diff <archivo>
```

### 🔹 Comparar con el Último Commit
Si queremos ver la diferencia entre la versión actual y el último commit:

```bash
git diff HEAD
```

- Útil para verificar qué cambios se han hecho antes de confirmarlos.

---

## 🟠 5. Deshacer y Modificar Commits

### 🔹 Restaurar un Archivo al Último Estado Confirmado
Si hicimos cambios en un archivo pero queremos volver a la última versión confirmada:

```bash
git checkout -- <archivo>
```

### 🔹 Eliminar Archivos del Staging sin Perderlos
Si agregamos un archivo al staging pero queremos sacarlo antes del commit:

```bash
git reset <archivo>
```

Para eliminar todos los archivos del staging:

```bash
git reset
```

### 🔹 Revertir un Commit
Si ya hicimos un commit pero queremos deshacerlo:

```bash
git revert <id-del-commit>
```

Ejemplo:

```bash
git revert 2a7b3c9
```

- Crea un nuevo commit que revierte los cambios anteriores.
- No elimina el historial, sino que agrega un nuevo punto que anula el commit seleccionado.

### 🔹 Modificar el Último Commit (`git commit --amend`)
A veces cometemos errores en un commit, como un mensaje incorrecto o archivos que olvidamos agregar. Podemos corregir el último commit con:

```bash
git commit --amend -m "Nuevo mensaje del commit"
```

- Esto reemplaza el mensaje del último commit sin crear uno nuevo.
- Si olvidamos agregar un archivo antes del commit, podemos hacer:

```bash
git add archivo_nuevo.txt
git commit --amend --no-edit
```

- Esto agrega el archivo al commit sin cambiar el mensaje.

⚠ **Nota**: `--amend` solo debe usarse en commits que aún no han sido enviados a un repositorio remoto con `git push`. Si ya subiste el commit, tendrás que hacer un `git push --force`.

---

## 🟤 Conclusión
Este módulo cubre los comandos esenciales para trabajar con Git en un entorno profesional. Comprender estos comandos es fundamental antes de avanzar a temas más avanzados como ramas, trabajo en equipo y manejo de repositorios remotos.

---

📌 **Recomendación:** Practica cada comando en un entorno seguro antes de aplicarlo en proyectos reales.
