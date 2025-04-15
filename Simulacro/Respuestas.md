# ✅ Respuestas – Evaluación Curso Git

## Parte Teórica

1. c) Es un sistema distribuido de control de versiones.  
2. c) Git es una herramienta local; GitHub es una plataforma de colaboración.  
3. b) `git init`  
4. d) Staging Area  
5. c) `git log`  
6. b) Permite trabajar en funcionalidades sin afectar el código principal.  
7. c) Reescribe la base de una rama sobre otra para obtener una historia lineal.  
8. a) `git pull` descarga y fusiona; `git fetch` solo descarga.  
9. b) Guarda cambios sin confirmarlos para recuperarlos después.  
10. c) `git reflog`

---

## Parte Práctica

### Módulo 1

1. `git --version`  
2.  
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
```  
3. `git init`

---

### Módulo 2

4. `git clone <url>`  
5. `git status`  
6. `git add .`  
7. `git commit -m "Inicialización del proyecto"`  
8. `git log`  
9. `git log --oneline --graph --decorate --all`  
10. `git diff`  
11. `git diff archivo.txt`

---

### Módulo 3

12. `git branch feature-login`  
13. `git checkout feature-login` o `git switch feature-login`  
14.  
```bash
git checkout main
git merge feature-login
```  
15.  
```bash
git checkout feature-login
git rebase main
```  
16.  
**Ventaja**: historial más limpio y lineal.  
**Riesgo**: puede causar conflictos si la rama ya fue compartida.

---

### Módulo 4

17. `git remote add origin <url>`  
18. `git push origin nombre-rama`  
19. `git fetch`  
20.  
```bash
git tag v1.0
git push origin v1.0
```

---

### Módulo 5

21.  
**Pull Request**: permite revisar, comentar y validar cambios antes del merge.  
**Merge directo**: une ramas localmente sin revisión previa.  
22.  
- Resolver manualmente los conflictos en el archivo.  
- Luego:  
```bash
git add archivo.txt
git commit
```

---

### Módulo 6

23. `git cherry-pick <hash>`  
24. `git stash`  
25. `git rebase -i HEAD~3`  
26. `git commit --amend -m "Nuevo mensaje"`  
27. Agregar `.env` al archivo `.gitignore`

---

### Módulo 7

28. `git revert a1b2c3d`  
29. `git restore archivo.txt`  
30.  
```bash
git reflog
git checkout <hash_reflog>
```
