# Gestión de Credenciales en Git: Tokens y Claves SSH

## 🔐 1. Tokens de Acceso Personal (PATs) – vía HTTPS

Cuando se usa HTTPS para clonar (`https://...`), ya no se acepta contraseña, sino un **token personal**.

### 💡 Cómo usar:
1. Al hacer `git clone`, `git pull`, etc., Git pedirá usuario y contraseña.
2. Usá tu **token** en lugar de la contraseña.

### 💾 Cómo guardar el token localmente:
```bash
# Guarda en texto plano (NO recomendado para producción)
git config --global credential.helper store

# Guarda en caché por tiempo (mejor opción en local)
git config --global credential.helper cache

# macOS - Usa llavero
git config --global credential.helper osxkeychain

# Windows - Usa gestor de credenciales
git config --global credential.helper manager-core

## 🔑 2. Claves SSH (certificados público/privado)

Recomendado si trabajás regularmente con **GitHub**, **GitLab**, **Bitbucket**, etc.

### ✅ Cómo configurar:

#### 1. Generar las claves:

```bash
ssh-keygen -t ed25519 -C "tu_email@example.com"
```

Esto genera:

- `~/.ssh/id_ed25519` → **clave privada**
- `~/.ssh/id_ed25519.pub` → **clave pública**

#### 2. Agregar la clave pública a GitHub / GitLab

Ingresá al panel de tu cuenta → Configuración → SSH Keys → Nueva clave

#### 3. Activar el agente SSH:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

#### 4. Usar SSH para clonar:

```bash
git clone git@github.com:usuario/repositorio.git
```

---

## ⚙️ 3. Múltiples cuentas o claves SSH

Configurá el archivo `~/.ssh/config`:

```ssh
Host github-personal
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_personal

Host github-work
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_work
```

Cloná así:

```bash
git clone git@github-personal:usuario/repositorio.git
```

---

# 🔐 Gestión de Tokens y Certificados SSH en GitHub

## ✅ 1. Uso de Token de Acceso Personal (PAT) con Git (HTTPS)

### 🔧 Cómo generar un token en GitHub:

1. Ir a: [https://github.com/settings/tokens](https://github.com/settings/tokens)
2. Hacer clic en **"Generate new token (classic)"** o "Fine-grained token"
3. Elegir:
   - Expiración
   - Scopes: al menos `repo` y `workflow` si usás CI/CD
4. Guardar el token en lugar seguro. GitHub **no te lo volverá a mostrar**.

### 🧪 Cómo usar el token en Git:

Cuando clones un repositorio por HTTPS:

```bash
git clone https://github.com/usuario/repositorio.git
```

Al pedir usuario y contraseña:
- Usuario: tu nombre de usuario GitHub
- Contraseña: **el token**

### 💾 Guardar el token automáticamente:

```bash
# Almacenar credenciales en texto plano (solo para entornos seguros)
git config --global credential.helper store

# O usar el caché por tiempo limitado
git config --global credential.helper cache

# O gestores específicos:
# macOS
git config --global credential.helper osxkeychain

# Windows
git config --global credential.helper manager-core
```

---

## 🔑 2. Cargar Certificados SSH en GitHub

### 🛠️ Paso 1: Generar clave SSH

```bash
ssh-keygen -t ed25519 -C "tu_email@example.com"
```

Esto generará:
- `~/.ssh/id_ed25519` → clave privada
- `~/.ssh/id_ed25519.pub` → clave pública

### 🛠️ Paso 2: Agregar la clave a tu cuenta GitHub

1. Copiar el contenido de la clave pública:

```bash
cat ~/.ssh/id_ed25519.pub
```

2. Ir a GitHub:  
   [https://github.com/settings/keys](https://github.com/settings/keys)

3. Clic en **"New SSH key"**
   - Pegar la clave pública
   - Darle un nombre (por ejemplo, "Mi laptop")

### 🛠️ Paso 3: Verificar conexión

```bash
ssh -T git@github.com
```

Deberías ver algo como:
Hi usuario! You've successfully authenticated, but GitHub does not provide shell access.



### 🛠️ Paso 4: Clonar usando SSH

```bash
git clone git@github.com:usuario/repositorio.git
```


t