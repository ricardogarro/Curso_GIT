# 🟢 Módulo 6: Técnicas Avanzadas y Buenas Prácticas

## 1. Cherry-picking: Aplicar Commits Específicos

El comando `git cherry-pick` permite tomar uno o varios commits puntuales de otra rama y aplicarlos en la rama actual, sin necesidad de hacer merge de toda la rama.

Esto es útil, por ejemplo, cuando querés llevar una corrección puntual desde una rama de desarrollo (`develop`) a producción (`main`) sin incorporar otros cambios que todavía no están listos.

### Ejemplo:

```bash
git checkout main
git cherry-pick a1b2c3d4
```

Este comando aplica el commit con hash `a1b2c3d4` en la rama `main`.

También podés cherry-pick múltiple:

```bash
git cherry-pick hash1 hash2 hash3
```

>  Importante: si hay conflictos, deberás resolverlos manualmente y luego continuar con:
>
> ```bash
> git cherry-pick --continue
> ```

---

## 2. Stashing: Guardar Cambios sin Commit

Cuando estás trabajando en algo pero necesitás cambiar de rama sin hacer commit, podés "guardar" temporalmente tus cambios usando `git stash`.

### Guardar los cambios:

```bash
git stash
```

### Volver a aplicarlos luego:

```bash
git stash apply
```

### Ver lista de stashes:

```bash
git stash list
```

Podés aplicar un stash específico con:

```bash
git stash apply stash@{0}
```

---

## 3. Squash y Edición de Commits

### Squash: Fusionar Commits

Permite combinar varios commits en uno solo. Ideal para limpiar el historial antes de fusionar una rama.

```bash
git rebase -i HEAD~3
```

Aparecerá una lista de commits. Reemplazá `pick` por `squash` en los que quieras unir.

### Editar el último commit:

```bash
git commit --amend
```

Permite modificar el mensaje o incluir nuevos cambios al commit más reciente (no recomendado si ya fue compartido).

---

## 4. Uso de `.gitignore` y Archivos de Configuración

El archivo `.gitignore` le dice a Git qué archivos o carpetas debe ignorar (no versionar).

Ejemplo típico en un proyecto web:

```
/node_modules
/vendor
.env
/storage/*.key
```

Otros archivos útiles:

- `.gitattributes`: define cómo manejar archivos al cambiar de sistema operativo.
- Hooks personalizados: scripts en `.git/hooks/` que pueden ejecutar validaciones antes de commits o pushes.

---

## 5. Buenas Prácticas en Git

### Commits atómicos

Cada commit debe representar un cambio único, funcional y comprensible. No mezcles cambios sin relación en el mismo commit.

### Mensajes Claros y Estructurados

Formato recomendado:

```
tipo: descripción corta

Descripción opcional más extensa.
```

Ejemplos de tipos comunes:

- `feat`: nueva funcionalidad
- `fix`: corrección de bug
- `docs`: cambios en documentación
- `refactor`: refactorización sin cambio de funcionalidad

Ejemplo:

```
fix: corregir cálculo de porcentaje en resumen mensual
```

### Estrategias de Branching

- **GitHub Flow**: ramas cortas por funcionalidad, integradas mediante PR.
- **Git Flow**: estructura con `main`, `develop`, `feature/*`, `release/*`, `hotfix/*`.
- **Trunk-Based Development**: trabajo continuo en `main`, con tests automáticos.

