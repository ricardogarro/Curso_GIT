# 🟢 Módulo 1: Introducción a Git y Control de Versiones

## 1. ¿Qué es Git? Historia y conceptos clave

### Introducción a los sistemas de control de versiones

Un sistema de control de versiones permite gestionar los cambios realizados en archivos a lo largo del tiempo. Es fundamental para equipos de desarrollo, ya que facilita la colaboración, el seguimiento de errores y la recuperación de versiones anteriores.

### Historia de Git

Git fue creado por Linus Torvalds en 2005 para gestionar el desarrollo del kernel de Linux. Entre sus principales características se destacan:

- **Distribuido**: cada copia del repositorio tiene todo el historial.
- **Seguro**: utiliza hashes SHA-1 para garantizar la integridad.
- **Eficiente**: maneja grandes proyectos con agilidad.

### Ventajas de Git

- Permite trabajar sin conexión.
- Facilita el trabajo colaborativo.
- Brinda herramientas para control detallado de versiones.

---

## 2. Diferencia entre Git y GitHub/GitLab/Bitbucket

### Git

- Es una herramienta local de control de versiones.
- Se utiliza desde la línea de comandos.
- No requiere conexión a internet para la mayoría de sus operaciones.

### GitHub, GitLab y Bitbucket

- Son plataformas que alojan repositorios Git en la nube.
- Proveen funcionalidades adicionales como:
  - Pull Requests / Merge Requests
  - Integración continua (CI/CD)
  - Issues, wiki, gestión de proyectos

| Característica       | Git                          | GitHub/GitLab/Bitbucket              |
|----------------------|------------------------------|--------------------------------------|
| Naturaleza           | Herramienta local             | Servicio en la nube                  |
| Interfaz             | Línea de comandos             | Web y CLI                            |
| Colaboración         | Manual (por archivos)         | Automatizada (PRs, revisiones, etc.)|

---

## 3. Instalación y configuración inicial de Git

### Instalación

#### Windows

1. Descargar desde [git-scm.com](https://git-scm.com/download/win)
2. Instalar seleccionando `Git Bash` como terminal recomendada.

#### macOS

```bash
brew install git
```

#### Linux (Debian/Ubuntu)

```bash
sudo apt update && sudo apt install git
```

### Configuración básica

```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tuemail@example.com"
git config --global core.editor "nano"
git config --list
```

---

## 4. Comandos básicos

### Verificar la versión de Git instalada

```bash
git --version
```

### Inicializar un repositorio

```bash
git init
```

Crea un repositorio vacío en el directorio actual.

### Configurar el usuario (si no se hizo antes)

```bash
git config --global user.name "Nombre"
git config --global user.email "correo@example.com"
```

---

## 5. Flujo de trabajo en Git

Git se basa en tres áreas clave:

1. **Working Directory**: donde se editan los archivos.
2. **Staging Area**: donde se preparan los cambios a confirmar.
3. **Repository**: donde se almacena el historial de cambios.

### Flujo básico:

1. Modificar archivos.
2. Agregarlos al staging con `git add`.
3. Confirmarlos con `git commit`.
4. Subirlos (más adelante) con `git push`.

> Este flujo permite registrar los cambios de forma ordenada y segura.
