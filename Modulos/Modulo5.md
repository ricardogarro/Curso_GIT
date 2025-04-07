## Módulo 5: Pull Requests y Colaboración en GitHub/GitLab

### . ¿Qué es un Pull Request (PR)? ¿En qué se diferencia de un Merge?

Un **Pull Request (PR)** es una solicitud para incorporar cambios desde una rama (por ejemplo, `feature/nueva-funcionalidad`) hacia otra (por lo general, `main` o `develop`).

- Un **merge** es la acción de integrar cambios entre ramas.
- Un **PR** es un proceso colaborativo: permite revisar, comentar y aprobar los cambios **antes** de hacer el merge.

---

### . Creación y revisión de PRs en GitHub/GitLab

#### ✅ Crear un Pull Request

1. Hacer `push` de tu rama al repositorio remoto:
```bash
git push origin feature/nueva-funcionalidad
```

2. Ir a GitHub o GitLab y crear un PR desde esa rama hacia `main`.

#### Revisar un Pull Request

- Asignar revisores
- Dejar comentarios
- Aprobar o solicitar cambios
- Hacer "merge" cuando todo esté aprobado

---

### Estrategias para aprobar cambios en equipo

- ✅ **Revisión por pares (peer review)**
- ✅ Reglas como: mínimo 2 aprobaciones antes de merge
- ❌ No permitir merges directos a `main`
- ✅ Usar etiquetas como `WIP` (Work In Progress)
- ✅ Automatizar checks (lint, tests, builds)

---

### Resolución de conflictos en PRs

Si hay conflictos, Git mostrará mensajes como:

```bash
CONFLICT (content): Merge conflict in archivo.js
```

#### Pasos para resolver:

1. Editar manualmente los archivos y dejar solo el código correcto
2. Marcar como resuelto:
```bash
git add archivo.js
```

3. Hacer commit:
```bash
git commit -m "Resuelto conflicto en archivo.js"
```

4. Si estás en PR con `rebase`, podés continuar con:
```bash
git rebase --continue
```

---

### Integración continua con GitHub Actions o GitLab CI

#### 🚀 GitHub Actions

- Archivo `.github/workflows/ci.yml`
- Ejemplo simple:

```yaml
name: CI

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Instalar dependencias
        run: npm install
      - name: Ejecutar tests
        run: npm test
```

#### 🚀 GitLab CI

- Archivo `.gitlab-ci.yml`
- Ejemplo:

```yaml
stages:
  - test

test-job:
  stage: test
  script:
    - npm install
    - npm test
```

---

💡 **Consejo final**: Usar PRs bien estructurados mejora la calidad del código, facilita la colaboración y mantiene el historial limpio y trazable.
