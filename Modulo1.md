# Módulo 1: Introducción a Git y Control de Versiones

## 1. ¿Qué es Git? Historia y Conceptos Clave
### Introducción a los sistemas de control de versiones
Un sistema de control de versiones permite gestionar los cambios en archivos a lo largo del tiempo, facilitando la colaboración entre desarrolladores y la recuperación de versiones anteriores en caso de errores.

### Historia de Git
Git fue creado por Linus Torvalds en 2005 para gestionar el desarrollo del kernel de Linux. Sus principales características incluyen:
- **Distribuido**: Cada copia del repositorio es un historial completo.
- **Seguro**: Usa SHA-1 para verificar la integridad de los datos.
- **Eficiente**: Maneja grandes proyectos con rapidez.

### Ventajas de Git
- Permite trabajar sin conexión y sincronizar cambios después.
- Gestión eficiente de ramas y versiones.
- Facilita la colaboración en equipos de desarrollo.

---

## 2. Diferencia entre Git y GitHub/GitLab/Bitbucket
### Git: Sistema de control de versiones
Git es una herramienta de línea de comandos que permite gestionar versiones localmente sin necesidad de conexión a internet.

### GitHub, GitLab y Bitbucket: Servicios de alojamiento de repositorios
Son plataformas en la nube que proporcionan herramientas para compartir repositorios, colaborar en proyectos y gestionar el flujo de trabajo.
- **GitHub**: Enfocado en código abierto y colaboración.
- **GitLab**: Ofrece integración continua y DevOps.
- **Bitbucket**: Integrado con Atlassian y Jira.

Diferencias clave:

| Característica | Git | GitHub/GitLab/Bitbucket |
|--------------|-----|------------------------|
| Uso | Control de versiones local | Repositorios remotos y colaboración |
| Interfaz | Línea de comandos | Web y CLI |
| Colaboración | Manual (compartir archivos) | PRs, issues, revisiones |

---

## 3. Instalación y Configuración Inicial de Git
### Instalación en Diferentes Sistemas Operativos
#### Windows:
1. Descargar e instalar [Git for Windows](https://git-scm.com/download/win).
2. Durante la instalación, seleccionar "Git Bash" como terminal predeterminada.

#### macOS:
```bash
brew install git
```

#### Linux (Debian/Ubuntu):
```bash
sudo apt update && sudo apt install git
```

### Configuración Básica de Git
Una vez instalado, configurar el usuario y correo:
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tuemail@example.com"
git config --global core.editor "nano"  # O cualquier otro editor de preferencia
git config --list  # Verificar la configuración
```

---

## 4. Comandos Básicos de Git
### Inicializar un Repositorio
```bash
git init
```
Crea un nuevo repositorio en el directorio actual.

### Clonar un Repositorio
```bash
git clone <url-del-repositorio>
```
Descarga un repositorio remoto a la máquina local.

### Estado del Repositorio
```bash
git status
```
Muestra los archivos modificados y los cambios pendientes.

### Agregar Cambios al Área de Staging
```bash
git add <archivo>
git add .  # Agrega todos los archivos modificados
```

### Confirmar Cambios en el Repositorio
```bash
git commit -m "Mensaje descriptivo del cambio"
```
Cada commit crea una nueva versión en el historial del repositorio.

### Ver el Historial de Commits
```bash
git log
```
Lista los commits realizados en el repositorio.

---

## 5. Flujo de Trabajo en Git
### Tres Áreas Principales
1. **Working Directory (Directorio de trabajo)**: Donde se editan los archivos.
2. **Staging Area (Área de preparación)**: Archivos listos para ser confirmados.
3. **Repository (Repositorio local)**: Donde se almacenan los commits.

### Flujo de Trabajo Típico
1. **Modificar archivos** en el directorio de trabajo.
2. **Agregar cambios** al staging con `git add`.
3. **Confirmar los cambios** con `git commit`.
4. **Subir cambios** a un repositorio remoto con `git push` (ver en módulos posteriores).

---

## Conclusión
Este módulo ha cubierto los conceptos fundamentales de Git, desde su instalación hasta el flujo de trabajo básico. A medida que avancemos en el curso, exploraremos comandos más avanzados y estrategias para trabajar en equipo de manera eficiente con Git.
