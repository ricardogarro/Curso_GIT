### Módulo 4: Trabajo con Repositorios Remotos

### 1. Diferencia entre Repositorio Local y Remoto

Repositorio local: En tu computadora. Permite trabajar sin conexión.

Repositorio remoto: En la nube (GitHub, GitLab, Bitbucket). Facilita la colaboración y el respaldo.

### 2. Añadir y Eliminar Repositorios Remotos

Añadir un repositorio remoto:

git remote add origin https://url-del-repositorio.git

Ver repositorios remotos:
```bash
git remote -v
```

Eliminar un remoto:
```bash
git remote remove origin
```
### 3. Subir Cambios y Obtener Actualizaciones

Subir cambios al remoto:
```bash
git push origin nombre-rama
```
Obtener cambios remotos y fusionarlos:
```bash
git pull origin nombre-rama
```
Obtener cambios sin fusionar:
```bash
git fetch origin
```
### 4. Trabajo en Equipo con Ramas Remotas

Listar ramas remotas:
```bash
git branch -r
```
Rastrear una rama remota:
```bash
git checkout --track origin/nombre-rama
```
### 5. Manejo de Tags y Versiones

Crear un tag:
```bash
git tag v1.0.0
```
Ver todos los tags:
```bash
git tag
```
Subir tags al repositorio remoto:
```bash
git push origin --tags
```
Eliminar un tag local:
```bash
git tag -d v1.0.0
```
Eliminar un tag remoto:
```bash
git push origin :refs/tags/v1.0.0
```

