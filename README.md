# Pixel Wars

Juego **HTML5 Canvas** estático, empaquetado en un único archivo `index.html` (sin dependencias ni build). Está listo para abrirse localmente y para desplegarse en **Vercel** como proyecto estático.

## Ejecutar localmente

- Opción rápida: hacé doble clic en `index.html` para abrirlo en tu navegador.
- (Opcional) Servidor local simple:
  - **Windows / PowerShell** (si tenés Python):  
    ```powershell
    cd D:\_Repos\pixelwars
    python -m http.server 8080
    ```
    Luego abrí http://localhost:8080 en tu navegador.

## Estructura del repo

```
pixelwars/
├─ index.html
└─ README.md  ← este archivo
```

> Nota: Los sprites PNG están **embebidos** dentro del `index.html`. No hay assets externos ni carpetas adicionales.

## Subir a GitHub (si todavía no está configurado)

En **PowerShell** desde `D:\_Repos\pixelwars`:

```powershell
cd D:\_Repos\pixelwars
git init
git branch -M main
git remote add origin https://github.com/lean1982/pixelwars.git
git add index.html README.md
git commit -m "feat: pixel wars initial commit"
git push -u origin main
```

> Si el remoto ya existe, usá:  
> `git remote set-url origin https://github.com/lean1982/pixelwars.git`

## Desplegar en Vercel (nuevo proyecto)

1. En Vercel, hacé clic en **New Project** → **Import Git Repository** y elegí **lean1982/pixelwars**.  
2. Configuración:
   - **Production Branch**: `main`
   - **Framework Preset**: **Other** (Static)
   - **Root Directory**: `./`
   - **Build Command**: *(vacío)*
   - **Output Directory**: *(vacío)*
3. **Deploy**. Vercel generará una URL pública tipo `https://pixel-wars-xxxxx.vercel.app`.

> Importante: elegí **Create a New Project** para no pisar proyectos ya existentes.

## Actualizar el juego

Cada vez que modifiques `index.html`:

```powershell
cd D:\_Repos\pixelwars
git add index.html
git commit -m "feat: ajustes pixel wars"
git push
```
Vercel va a redeployar automáticamente el proyecto conectado.

## Problemas frecuentes

- **404 o ruta vacía en Vercel**: Asegurate de haber elegido el **Root Directory `./`** y que `index.html` esté en la raíz del repo.
- **Se ve en negro**: Confirmá que subiste la versión correcta de `index.html`. Esta build no requiere assets externos.

## Licencia

Podés agregar la licencia que prefieras (MIT, Apache-2.0, etc.).
