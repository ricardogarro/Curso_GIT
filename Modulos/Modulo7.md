# 🔴 Módulo 7: Recuperación de Errores y Depuración
 
## 1. Revertir Commits (`git revert`)

`git revert` crea un nuevo commit que deshace los cambios de un commit anterior, sin alterar el historial. Es la forma recomendada de deshacer cambios en producción.

### Ejemplo:

```bash
git revert a1b2c3d4
```

Esto generará un nuevo commit que revierte los efectos del commit con hash `a1b2c3d4`.

> Ideal cuando necesitás revertir algo en una rama compartida sin reescribir el historial.

---

## 2. Restaurar Versiones Anteriores

### a) Recuperar un archivo a un estado anterior:

```bash
git checkout hash_commit -- archivo.txt
```

Esto restaura el archivo `archivo.txt` desde un commit específico, sin cambiar el resto del proyecto.

### b) Volver todo el proyecto a un commit anterior (peligroso):

```bash
git reset --hard hash_commit
```

Este comando mueve el puntero actual (`HEAD`) a un commit anterior **y descarta todos los cambios posteriores**.

> ⚠️ Precaución: puede borrar trabajo si no hacés backup o push previo.

---

## 3. Recuperar Commits Eliminados con `git reflog`

`git reflog` permite ver el historial de referencias del `HEAD`, incluyendo commits que fueron descartados o sobrescritos con `reset`, `rebase`, etc.

### Ver el historial de movimientos:

```bash
git reflog
```

### Recuperar un commit perdido:

```bash
git checkout hash_reflog
```

Incluso si borraste una rama entera por accidente, `reflog` puede ayudarte a recuperarla.

---

## 4. Manejo de Archivos Eliminados Accidentalmente

### a) Archivo borrado antes del commit:

Si eliminaste un archivo por error y aún no hiciste commit:

```bash
git restore archivo.txt
```

### b) Archivo borrado después de un commit anterior:

```bash
git checkout hash_commit -- archivo.txt
```

Esto recupera la versión del archivo desde un commit anterior específico.

---

Usá `git status` y `git log` frecuentemente para monitorear el estado de tus cambios y evitar sobrescribir trabajo por accidente.
