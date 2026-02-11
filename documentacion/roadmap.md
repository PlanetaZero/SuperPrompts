<h1 style="color: #FF5722;">🗺️ Superprompt: Crear Roadmap de Producto</h1>

Este superprompt está diseñado para generar un roadmap de producto o técnico, ayudando a planificar el futuro de un proyecto en trimestres (Quarters) o sprints.

> **Abrir este superprompt:**
> ```bash
> code superprompts/documentacion/roadmap.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/documentacion/roadmap.md`
> - **Linux:** `xclip -selection clipboard < superprompts/documentacion/roadmap.md`
> - **Windows:** `clip < superprompts/documentacion/roadmap.md`

---

## roadmap

### Versión Markdown (HTML)

Actúa como un <span style="color: #E91E63;">**Product Manager**</span> experimentado y un <span style="color: #9C27B0;">**Líder Técnico**</span>. Tu misión es traducir una visión y una lista de funcionalidades deseadas en un roadmap estratégico y accionable.

**[VISIÓN DEL PRODUCTO]**
Describe la visión a largo plazo del producto. ¿Qué se aspira a conseguir en 1-2 años?
<span style="color: #FF9800;">`{{vision_del_producto}}`</span>
(Ej: "Convertir nuestra plataforma en el estándar de la industria para la gestión de proyectos creativos, enfocándonos en la colaboración en tiempo real y la integración con herramientas de IA.").

**[ESTADO ACTUAL]**
Resume brevemente el estado actual del producto. ¿Qué se ha lanzado ya? ¿En qué se está trabajando ahora?
<span style="color: #FF9800;">`{{estado_actual}}`</span>
(Ej: "Actualmente tenemos un MVP con gestión de tareas y tableros kanban. Estamos terminando la funcionalidad de comentarios en las tareas.").

**[LISTA DE FUNCIONALIDADES (BACKLOG)]**
Enumera las principales funcionalidades o "epics" que se quieren construir, sin un orden particular.
- <span style="color: #FF9800;">`Funcionalidad A: Edición de documentos en tiempo real (como Google Docs)`</span>
- <span style="color: #FF9800;">`Funcionalidad B: Integración con un modelo de IA para generar ideas`</span>
- <span style="color: #FF9800;">`Funcionalidad C: Sistema de notificaciones mejorado (Email y Push)`</span>
- <span style="color: #FF9800;">`Funcionalidad D: Refactorización del backend a microservicios`</span>
- <span style="color: #FF9800;">`Funcionalidad E: App móvil nativa (iOS y Android)`</span>
- <span style="color: #FF9800;">`... (añade tantas como necesites)`</span>

**[FORMATO DE SALIDA]**
Quiero un roadmap de producto en formato Markdown, organizado por trimestres (Quarters) para los próximos 12 meses. Para cada trimestre, incluye:
1.  **Tema Principal:** Un nombre que resuma el enfoque del trimestre (Ej: "Fundaciones y Rendimiento", "Expansión a Móvil", "Inteligencia Artificial").
2.  **Objetivos Clave (OKRs):** 2-3 objetivos medibles para el trimestre.
3.  **Epics/Funcionalidades Principales:** Las funcionalidades del backlog que se abordarán en ese trimestre.
4.  **Justificación:** Por qué se han elegido esas funcionalidades para este trimestre (valor de negocio, dependencia técnica, etc.).

**Ejemplo de un Trimestre:**
### **Q1 2024: Fundaciones y Rendimiento**
- **Objetivos:** Reducir la latencia de la API en un 30%, Aumentar la retención de usuarios en un 10%.
- **Epics:**
    - `[Técnico]` Refactorización del backend a microservicios.
    - `[Producto]` Sistema de notificaciones mejorado.
- **Justificación:** La refactorización es crucial para escalar y soportar futuras funcionalidades. Las notificaciones mejorarán el engagement y la retención.

---

### Versión para Terminal (ANSI)

```ansi
[1;35mActúa como un Product Manager experimentado[0m y un [1;35mLíder Técnico[0m. Tu misión es crear un roadmap estratégico.

[1m[VISIÓN DEL PRODUCTO][0m
Describe la visión a largo plazo.
[1;33m`{{vision_del_producto}}`[0m

[1m[ESTADO ACTUAL][0m
Resume el estado actual del producto.
[1;33m`{{estado_actual}}`[0m

[1m[LISTA DE FUNCIONALIDADES (BACKLOG)][0m
Enumera las funcionalidades deseadas.
- [1;33m`Funcionalidad A: Edición de documentos en tiempo real`[0m
- [1;33m`Funcionalidad B: Integración con IA`[0m
- ...

[1m[FORMATO DE SALIDA][0m
Quiero un roadmap en Markdown organizado por trimestres (Quarters) para los próximos 12 meses.
Para cada trimestre:
1.  [1mTema Principal:[0m (Ej: "Fundaciones y Rendimiento").
2.  [1mObjetivos Clave (OKRs):[0m 2-3 objetivos medibles.
3.  [1mEpics/Funcionalidades Principales:[0m Qué se abordará.
4.  [1mJustificación:[0m Por qué se han elegido.
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-roadmap="pbcopy < ~/superprompts/documentacion/roadmap.md && echo 'Copiado: Prompt Crear Roadmap'"
# Para Linux
# alias sp-roadmap="xclip -selection clipboard < ~/superprompts/documentacion/roadmap.md && echo 'Copiado: Prompt Crear Roadmap'"
```

### Crear un nuevo archivo de roadmap
```bash
function new-roadmap() {
  DOCS_DIR="docs/product"
  mkdir -p "$DOCS_DIR"
  
  FILE_PATH="${DOCS_DIR}/ROADMAP-$(date +%Y).md"
  
  if [ -f "$FILE_PATH" ]; then
    echo "El archivo de roadmap para este año ya existe: $FILE_PATH"
  else
    touch "$FILE_PATH"
    echo "Archivo de roadmap creado en: $FILE_PATH"
  fi
  
  # Abre el archivo para que el usuario pegue la salida de la IA
  # code "$FILE_PATH"
}
```
