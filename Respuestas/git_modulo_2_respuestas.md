# ✅ Respuestas - Módulo 2: Comandos Esenciales de Git

## 🟢 Conceptuales (Teoría)
1. **¿Cuál es la diferencia entre `git init` y `git clone`?**  
   - `git init` crea un repositorio vacío en el directorio actual.
   - `git clone` copia un repositorio remoto a tu máquina local.

2. **Explica la diferencia entre el área de staging y el repositorio en Git.**  
   - El área de staging es donde los cambios se preparan antes de ser confirmados.
   - El repositorio almacena los commits confirmados de manera permanente.

3. **¿Para qué se utiliza el comando `git status`?**  
   - Muestra el estado de los archivos en el repositorio (modificados, en staging, sin seguimiento).

4. **¿Qué significa hacer un `commit` en Git?**  
   - Significa guardar de forma permanente los cambios preparados en el repositorio.

5. **¿Cómo se puede ver un historial de commits en Git?**  
   - Usando `git log` o `git log --oneline --graph` para una vista más compacta.

## 🔵 Prácticos (Uso de Consola)
6. **Crear un nuevo repositorio y verificar la inicialización:**  
   ```bash
   mkdir mi_proyecto && cd mi_proyecto
   git init
   ls -a  # Verifica que existe la carpeta .git
   ```

7. **Crear un archivo, agregarlo al staging y confirmarlo:**  
   ```bash
   touch index.html
   git add index.html
   git commit -m "Añadir archivo index.html"
   ```

8. **Clonar un repositorio público de GitHub:**  
   ```bash
   git clone https://github.com/example/test-repo.git
   ```

9. **Modificar un archivo, verificar su estado y descartar cambios:**  
   ```bash
   echo "Nuevo contenido" >> archivo.txt
   git status
   git checkout -- archivo.txt
   ```

10. **Agregar varios archivos y eliminarlos del staging antes de confirmar:**  
   ```bash
   git add .
   git reset  # Quita todos los archivos del staging
   ```

## 🟣 Resolución de Problemas
11. **Corregir el mensaje de un commit reciente:**  
   ```bash
   git commit --amend -m "Nuevo mensaje correcto"
   ```

12. **Ver detalles de un commit específico:**  
   ```bash
   git show <id-del-commit>
   ```

13. **Ver cambios antes de agregarlos al staging:**  
   ```bash
   git diff
   ```

14. **Quitar un archivo del staging sin eliminarlo del directorio:**  
   ```bash
   git reset <archivo>
   ```

15. **Deshacer el último commit sin perder los cambios:**  
   ```bash
   git reset --soft HEAD~1
   ```


