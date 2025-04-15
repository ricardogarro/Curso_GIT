# 🟣 Módulo 8: Integración con Otras Herramientas

## 1. Uso de Git en Visual Studio Code

Visual Studio Code (VS Code) ofrece integración nativa con Git. Permite:

- Ver cambios (`Source Control` panel).
- Hacer `commit`, `push`, `pull` y `merge` sin usar la terminal.
- Visualizar diferencias (`diff`) entre versiones de archivos.
- Resolver conflictos de forma visual.

También podés instalar extensiones como:

- GitLens: para ver historial, autores y `blame` enriquecido.
- Git Graph: para visualizar ramas y commits de forma gráfica.

---

## 2. Integración con Docker y CI/CD

### Git + Docker:

- Guardar archivos de configuración como `Dockerfile` y `.dockerignore` en el repositorio.
- Versionar imágenes y automatizar despliegues.

### Git + CI/CD:

- Con GitHub Actions o GitLab CI podés ejecutar tests, linters, builds o despliegues automáticos en cada `push` o PR.

Ejemplo básico (GitHub Actions):

```yaml
name: CI Pipeline
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: docker build -t mi-app .
```

---

## 3. Uso de Submódulos en Git (`git submodule`)

Permite incluir un repositorio dentro de otro (útil si dependés de una librería o proyecto externo que se actualiza por separado).

### Agregar un submódulo:

```bash
git submodule add https://github.com/usuario/proyecto-libreria external/lib
```

### Clonar un repositorio con submódulos:

```bash
git clone --recurse-submodules https://github.com/mi-proyecto.git
```

### Actualizar submódulos:

```bash
git submodule update --remote
```

 Requiere cuidado para evitar desincronización entre versiones del submódulo y el proyecto principal.

---

## 4. Configuración de Hooks (`.git/hooks/`) para Automatización

Los **Git Hooks** son scripts que se ejecutan automáticamente en determinados eventos (antes de commit, push, merge, etc.).

Ejemplo: prevenir commits con errores de sintaxis.

### Ubicación:

```
.git/hooks/pre-commit
```

### Ejemplo de hook `pre-commit` en Bash:

```bash
#!/bin/sh
npm run lint
if [ $? -ne 0 ]; then
  echo "❌ Errores de lint. Commit cancelado."
  exit 1
fi
```

>  Se pueden usar herramientas como [Husky](https://github.com/typicode/husky) para gestionar hooks de forma más profesional.

---

## 5. Seguridad en Git: Claves SSH y Firmas GPG

### Autenticación por SSH:

Evita ingresar usuario y contraseña al hacer `push`.

```bash
ssh-keygen -t ed25519 -C "tu@email.com"
```

Agregá la clave pública a GitHub/GitLab en tu perfil.

### Firmar commits con GPG:

Verifica que los commits provienen realmente de vos.

```bash
git config --global user.signingkey <tu-clave-gpg>
git commit -S -m "Commit firmado"
```

>Mejora la trazabilidad y seguridad de tu historial de commits.

---

## 6. Auditoría y Análisis de Cambios

### `git blame`:

Muestra quién modificó cada línea de un archivo.

```bash
git blame archivo.txt
```

### `git bisect`:

Ayuda a encontrar en qué commit se introdujo un bug.

```bash
git bisect start
git bisect bad
git bisect good hash
