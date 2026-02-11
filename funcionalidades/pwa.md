<h1 style="color: #4DD0E1;">📱 Superprompt: Convertir a PWA</h1>

Este superprompt solicita los pasos y el código necesarios para convertir una aplicación web existente en una Progressive Web App (PWA), permitiendo su instalación en dispositivos y funcionalidad offline.

> **Abrir este superprompt:**
> ```bash
> code superprompts/funcionalidades/pwa.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/funcionalidades/pwa.md`
> - **Linux:** `xclip -selection clipboard < superprompts/funcionalidades/pwa.md`
> - **Windows:** `clip < superprompts/funcionalidades/pwa.md`

---

## pwa

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Desarrollador Frontend Experto**</span>, especializado en Progressive Web Apps (PWA) y Service Workers.

**[CONTEXTO]**
- **Framework/Bundler:** <span style="color: #FF9800;">`{{framework_bundler}}`</span> (Ej: "Create React App", "Next.js", "Vite", "Angular CLI").
- **Objetivo Offline:** ¿Qué nivel de funcionalidad offline se necesita?
  <span style="color: #FF9800;">`{{objetivo_offline}}`</span> (Ej: "Mostrar una página de 'Estás desconectado' personalizada", "Permitir al usuario navegar por las páginas que ya ha visitado (cache-first)", "Permitir la lectura de artículos offline").

**[FORMATO DE SALIDA]**
Quiero una guía paso a paso y el código necesario para convertir mi aplicación en una PWA instalable y con capacidades offline.
1.  **Archivos de Manifiesto (Manifest):**
    - **`manifest.json`:** Genera el código completo para este archivo. Incluye `name`, `short_name`, `start_url`, `display`, `background_color`, `theme_color`, y una lista de `icons` de varios tamaños.
    - **Iconos:** Especifica los tamaños de icono recomendados que necesito crear (ej: 192x192, 512x512).
    - **Integración HTML:** Muestra cómo enlazar el manifiesto en el `index.html`.
2.  **Service Worker:**
    - **Estrategia de Caching:** Recomienda una estrategia de caching para los diferentes tipos de assets (ej: `Cache-First` para assets estáticos como CSS/JS, `Network-First` para llamadas a API, `Stale-While-Revalidate` para el shell de la aplicación).
    - **Generación del Service Worker:**
        - Muestra cómo generar y configurar el service worker, preferiblemente usando una librería que simplifique el proceso (ej: `workbox` de Google).
        - Proporciona el código de configuración para el bundler (ej: `vite.config.js` o `webpack.config.js`) para usar el plugin de Workbox.
    - **Registro del Service Worker:** Proporciona el script del lado del cliente para registrar el service worker de forma segura.
3.  **Experiencia de Usuario (UX):**
    - **Instalación:** ¿Cómo puedo promover la instalación de la PWA? Sugiere un patrón, como mostrar un botón de "Instalar App" cuando el evento `beforeinstallprompt` se dispare.
    - **Actualizaciones:** ¿Cómo manejar las actualizaciones de la PWA cuando hay un nuevo service worker? Sugiere un patrón para notificar al usuario y pedirle que recargue la página.

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Desarrollador Frontend Experto, especializado en Progressive Web Apps y Service Workers.[0m

[1m[CONTEXTO][0m
- [1mFramework/Bundler:[0m [1;33m`{{framework_bundler}}`[0m (Ej: "Vite").
- [1mObjetivo Offline:[0m [1;33m`{{objetivo_offline}}`[0m (Ej: "Permitir al usuario navegar por las páginas que ya ha visitado").

[1m[FORMATO DE SALIDA][0m
Quiero una guía paso a paso para convertir mi app en una PWA.
1.  [1mArchivos de Manifiesto:[0m
    - Código para `manifest.json`.
    - Tamaños de icono recomendados.
    - Cómo enlazarlo en el HTML.
2.  [1mService Worker:[0m
    - Recomendación de estrategia de caching.
    - Código de configuración para `workbox` en mi bundler.
    - Script para registrar el service worker.
3.  [1mExperiencia de Usuario (UX):[0m
    - Patrón para promover la instalación (botón de "Instalar App").
    - Patrón para manejar actualizaciones de la PWA.
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-pwa="pbcopy < ~/superprompts/funcionalidades/pwa.md && echo 'Copiado: Prompt Convertir a PWA'"
# Para Linux
# alias sp-pwa="xclip -selection clipboard < ~/superprompts/funcionalidades/pwa.md && echo 'Copiado: Prompt Convertir a PWA'"
```

### Instalar Workbox para Vite
Workbox es la herramienta estándar para facilitar la creación de Service Workers.

```bash
function install-workbox-vite() {
    if [ -f "vite.config.js" ] || [ -f "vite.config.ts" ]; then
        npm install workbox-precaching workbox-routing workbox-strategies --save-dev
        # Para generación automática, es mejor usar un plugin
        npm install vite-plugin-pwa --save-dev
        echo "vite-plugin-pwa instalado."
        echo "Ahora, importa y configura el plugin en tu vite.config.js"
    else
        echo "No se encontró un archivo de configuración de Vite."
    fi
}
```
