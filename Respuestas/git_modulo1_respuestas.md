# ✅ Respuestas - Módulo 1: Introducción a Git

## 🟢 Conceptuales (Teoría)
1. **¿Qué es un sistema de control de versiones y por qué es útil en el desarrollo de software?**  
   Un sistema de control de versiones permite gestionar los cambios en el código fuente, mantener un historial de modificaciones y facilitar la colaboración entre desarrolladores.

2. **Explica la diferencia entre Git y GitHub.**  
   - Git es un software de control de versiones que se usa en local.  
   - GitHub es una plataforma en la nube para almacenar repositorios y facilitar la colaboración.

3. **¿Cuál es la función del área de staging en Git?**  
   Es donde se almacenan los cambios antes de ser confirmados en el repositorio. Permite organizar y seleccionar qué archivos se incluirán en el commit.

## 🔵 Prácticos (Uso de Consola)
4. **Instala Git y configúralo:**  
   ```bash
   git config --global user.name "Tu Nombre"
   git config --global user.email "tuemail@example.com"
   ```

5. **Crea un nuevo repositorio en local:**  
   ```bash
   mkdir mi_proyecto && cd mi_proyecto
   git init
   ```

6. **Añadir y confirmar un archivo `README.md`:**  
   ```bash
   echo "# Mi Proyecto" > README.md
   git add README.md
   git commit -m "Añadir README.md"
   ```

7. **Clonar un repositorio remoto:**  
   ```bash
   git clone https://github.com/example/test-repo.git
   ```

## 🟣 Resolución de Problemas
8. **Agregar un archivo al staging y confirmarlo:**  
   ```bash
   git add archivo.txt
   git commit -m "Agregar cambios en archivo.txt"
   ```

9. **Corregir el mensaje de un commit reciente:**  
   ```bash
   git commit --amend -m "Nuevo mensaje corregido"
   ```

10. **Restaurar un archivo eliminado antes de hacer commit:**  
   ```bash
   git checkout -- archivo_importante.txt
   ```
