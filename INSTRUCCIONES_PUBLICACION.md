# GUÍA DE PUBLICACIÓN — Avanch Technology
## GitHub Pages + Google Domains

---

## PARTE A — GitHub Pages (5 minutos)

### 1. Crear repositorio
1. Ve a https://github.com y crea una cuenta si no tienes
2. Clic en "New repository"
3. Nombre: `avanchtechnology-web`
4. Visibilidad: Public
5. Clic en "Create repository"

### 2. Subir los archivos
1. En el repositorio nuevo, clic en "uploading an existing file"
2. Arrastra estos 3 archivos:
   - `index.html`          ← landing page principal
   - `form-suscripcion.html` ← formulario de suscripción
3. Clic en "Commit changes"

### 3. Activar GitHub Pages
1. Ve a Settings (⚙️) → Pages (menú izquierdo)
2. Source: "Deploy from a branch"
3. Branch: main → / (root) → Save
4. Espera ~2 minutos → aparecerá tu URL temporal:
   `https://tu-usuario.github.io/avanchtechnology-web`

### 4. Conectar dominio personalizado
1. En Settings → Pages → Custom domain
2. Escribe: `www.avanchtechnology.com`
3. Clic en Save
4. Activa ✓ "Enforce HTTPS"

---

## PARTE B — Google Domains (3 minutos)

1. Ve a https://domains.google.com
2. Selecciona `avanchtechnology.com`
3. Menú izquierdo → DNS
4. Scroll hasta "Custom records"
5. Agrega estos registros:

### Registro CNAME (para www):
```
Host:  www
Type:  CNAME
TTL:   3600
Data:  tu-usuario.github.io
```

### Registros A (para dominio raíz sin www):
```
Host:  @
Type:  A
TTL:   3600
Data:  185.199.108.153
```
```
Host:  @
Type:  A
TTL:   3600
Data:  185.199.109.153
```
```
Host:  @
Type:  A
TTL:   3600
Data:  185.199.110.153
```
```
Host:  @
Type:  A
TTL:   3600
Data:  185.199.111.153
```

### Registro para redirigir dominio raíz a www (opcional):
En Google Domains → Website → Forwarding:
```
Redirigir: avanchtechnology.com → www.avanchtechnology.com
```

---

## RESULTADO FINAL

Después de 1-24h de propagación DNS:

| URL | Destino |
|-----|---------|
| www.avanchtechnology.com | index.html (landing) |
| www.avanchtechnology.com/form-suscripcion.html | Formulario público |

---

## NOTAS IMPORTANTES

- Google Sites seguirá activo mientras no lo elimines — puedes dejarlo
  como respaldo o eliminarlo desde sites.google.com
- El HTTPS es automático con GitHub Pages (certificado Let's Encrypt)
- Los cambios futuros: solo reemplaza el archivo en GitHub y listo
- Costo adicional: $0 (GitHub Pages es gratis para sitios estáticos)

