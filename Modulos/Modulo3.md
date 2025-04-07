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




**git merge**


A---B---C topic
     \
      D---E main
           \
            F (merge commit)

Descripción: Se toma la historia de topic y se la une a main con un merge commit (F).

Resultado: La historia queda con una bifurcación (branch) visible.

Ventaja: Se mantiene el historial completo y fiel de cómo se trabajó.

Desventaja: El historial puede verse más "sucio" o con ramas entrecruzadas.

**🎯 **git rebase**

     A---B---C topic (original)
          \
           D---E main

Rebase: mueve la base de `topic` al final de `main`:

              A'--B'--C'
             /
      D---E main

Descripción: Se "reubica" la historia de topic sobre el último commit de main.

Resultado: Historia lineal, como si todo hubiera pasado en una misma secuencia.

Ventaja: El historial es más limpio.

Desventaja: Puede ser peligroso si ya compartiste los commits, porque reescribe la historia.
