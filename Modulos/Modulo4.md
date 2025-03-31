
## Módulo 4: Trabajo con Repositorios Remotos

### 1. Diferencia entre Repositorio Local y Remoto
- **Repositorio local:** En tu computadora. Permite trabajar sin conexión.
- **Repositorio remoto:** En la nube (GitHub, GitLab, Bitbucket). Facilita la colaboración y el respaldo.

### 2. Añadir y Eliminar Repositorios Remotos

**Añadir un repositorio remoto:**
```bash
git remote add origin https://url-del-repositorio.git
```

**Ver repositorios remotos:**
```bash
git remote -v
```

**Eliminar un remoto:**
```bash
git remote remove origin
```

### 3. Subir Cambios y Obtener Actualizaciones

**Subir cambios al remoto:**
```bash
git push origin nombre-rama
```

**Obtener cambios remotos y fusionarlos:**
```bash
git pull origin nombre-rama
```

**Obtener cambios sin fusionar:**
```bash
git fetch origin
```

### 4. Trabajo en Equipo con Ramas Remotas

**Listar ramas remotas:**
```bash
git branch -r
```

**Rastrear una rama remota:**
```bash
git checkout --track origin/nombre-rama
```

### 5. Manejo de Tags y Versiones

**Crear un tag:**
```bash
git tag v1.0.0
```

**Ver todos los tags:**
```bash
git tag
```

**Subir tags al repositorio remoto:**
```bash
git push origin --tags
```

**Eliminar un tag local:**
```bash
git tag -d v1.0.0
```

**Eliminar un tag remoto:**
```bash
git push origin :refs/tags/v1.0.0
```

### Conclusión
Estos módulos te permiten trabajar con Git de forma profesional, colaborando en equipo y manejando versiones del código fuente de manera eficiente. Con la práctica, dominarás flujos de trabajo complejos y podrás adaptarte a cualquier entorno de desarrollo moderno.

## Módulo 3: Ramas y Manejo de Versiones

### 1. ¿Qué son las ramas? Beneficios y usos
Una rama en Git es una línea de desarrollo independiente que permite trabajar en nuevas funcionalidades sin afectar la rama principal (usualmente llamada `main` o `master`).

**Beneficios:**
- Permite desarrollo paralelo.
- Facilita la prueba de nuevas ideas sin riesgo.
- Mejora la organización del trabajo en equipo.
- Esencial para la integración continua y despliegues controlados.

### 2. Creación y Gestión de Ramas

**Crear una nueva rama:**
```bash
git branch nombre-rama
```

**Cambiarse a una rama existente:**
```bash
git checkout nombre-rama
```

**Crear y cambiar a una nueva rama (comando moderno):**
```bash
git switch -c nombre-rama
```

**Listar ramas:**
```bash
git branch
```

### 3. Fusión de Ramas y Resolución de Conflictos

**Fusionar una rama a la actual:**
```bash
git merge nombre-rama
```

Si existen cambios incompatibles entre ramas, se generará un **conflicto**, que deberá resolverse manualmente editando los archivos afectados y luego confirmando los cambios:
```bash
git add archivo-afectado
git commit
```

### 4. Rebasing: Cómo Funciona y Cuándo Usarlo
El comando `rebase` reescribe el historial de una rama para aplicarlo sobre otra.

**Usos comunes:**
- Limpiar el historial de commits.
- Evitar merges innecesarios.

**Ejemplo:**
```bash
git checkout feature
# Aplicar los commits de feature sobre main
git rebase main
```

**Precaución:** No usar `rebase` en ramas compartidas si otros ya han trabajado sobre ellas.

### 5. Estrategias de Ramas

**Git Flow:**
Modelo estructurado con ramas dedicadas para desarrollo (`develop`), producción (`main/master`), funcionalidades (`feature/*`), arreglos (`hotfix/*`) y versiones (`release/*`).

**GitHub Flow:**
Ideal para despliegues continuos. Se trabaja con una rama principal (`main`) y ramas cortas por funcionalidad o bug, que se integran mediante Pull Requests.

**Trunk-Based Development:**
Se trabaja directamente sobre la rama principal o "trunk", con integraciones frecuentes y pruebas automáticas.


## Módulo 4: Trabajo con Repositorios Remotos

### 1. Diferencia entre Repositorio Local y Remoto
- **Repositorio local:** En tu computadora. Permite trabajar sin conexión.
- **Repositorio remoto:** En la nube (GitHub, GitLab, Bitbucket). Facilita la colaboración y el respaldo.

### 2. Añadir y Eliminar Repositorios Remotos

**Añadir un repositorio remoto:**
```bash
git remote add origin https://url-del-repositorio.git
```

**Ver repositorios remotos:**
```bash
git remote -v
```

**Eliminar un remoto:**
```bash
git remote remove origin
```

### 3. Subir Cambios y Obtener Actualizaciones

**Subir cambios al remoto:**
```bash
git push origin nombre-rama
```

**Obtener cambios remotos y fusionarlos:**
```bash
git pull origin nombre-rama
```

**Obtener cambios sin fusionar:**
```bash
git fetch origin
```

### 4. Trabajo en Equipo con Ramas Remotas

**Listar ramas remotas:**
```bash
git branch -r
```

**Rastrear una rama remota:**
```bash
git checkout --track origin/nombre-rama
```

### 5. Manejo de Tags y Versiones

**Crear un tag:**
```bash
git tag v1.0.0
```

**Ver todos los tags:**
```bash
git tag
```

**Subir tags al repositorio remoto:**
```bash
git push origin --tags
```

**Eliminar un tag local:**
```bash
git tag -d v1.0.0
```

**Eliminar un tag remoto:**
```bash
git push origin :refs/tags/v1.0.0
```