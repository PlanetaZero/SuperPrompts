<h1 style="color: #F44336;">📊 Superprompt: Diseño de Dashboard</h1>

Este prompt se enfoca en el diseño de un dashboard complejo, rico en datos. El objetivo es organizar la información de manera efectiva y crear visualizaciones útiles.

> **Abrir este superprompt:**
> ```bash
> code superprompts/ui-ux/diseño-dashboard.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/ui-ux/diseño-dashboard.md`
> - **Linux:** `xclip -selection clipboard < superprompts/ui-ux/diseño-dashboard.md`
> - **Windows:** `clip < superprompts/ui-ux/diseño-dashboard.md`

---

## diseño-dashboard

### Versión Markdown (HTML)

Actúa como un <span style="color: #E91E63;">**Especialista en UI/UX**</span> con experiencia en visualización de datos y diseño de dashboards de business intelligence.
Tus metas son: <span style="color: #2196F3;">**Claridad de un vistazo, Jerarquía de la Información y Accionabilidad**</span>.

**[PLATAFORMA Y TECNOLOGÍA]**
- **Plataforma:** <span style="color: #FF9800;">`{{plataforma}}`</span> (Ej: "Aplicación web responsive").
- **Stack de Frontend:** <span style="color: #FF9800;">`{{stack_frontend}}`</span> (Ej: "React, TypeScript").
- **Librería de Gráficos:** <span style="color: #FF9800;">`{{libreria_graficos}}`</span> (Ej: "Recharts", "D3.js", "Chart.js").

**[OBJETIVO DEL DASHBOARD Y PERFIL DE USUARIO]**
- **Objetivo:** ¿Qué pregunta principal debe responder el dashboard?
  <span style="color: #FF9800;">`{{objetivo_dashboard}}`</span> (Ej: "Mostrar la salud financiera de la empresa en el último trimestre").
- **Usuario:** ¿Quién usará este dashboard y qué es lo más importante para él?
  <span style="color: #FF9800;">`{{perfil_usuario}}`</span> (Ej: "Un C-level que necesita ver KPIs de alto nivel", "Un analista de marketing que necesita explorar datos de campañas").

**[MÉTRICAS Y DATOS DISPONIBLES]**
Enumera los KPIs y los datos que se deben mostrar.
- **KPIs Principales:** <span style="color: #FF9800;">`Ingresos Totales (MRR), Número de Clientes Activos, Tasa de Churn`</span>.
- **Datos Secundarios:** <span style="color: #FF9800;">`Ingresos por plan, Nuevos clientes por día, Tasa de conversión de la web`</span>.
- **Datos para Tablas:** <span style="color: #FF9800;">`Lista de últimos 10 clientes, Facturas pendientes de pago`</span>.

**[FORMATO DE SALIDA]**
Quiero una propuesta completa de diseño e implementación:
1.  **Jerarquía de la Información:** Describe qué información es más importante y debería ser más prominente.
2.  **Layout del Dashboard (Wireframe):** Un esquema de la disposición de los elementos en la pantalla. Puedes usar un bloque de código con ASCII art o una descripción por secciones (ej: "Fila 1: KPIs principales. Fila 2: Gráfico de evolución de MRR a la izquierda, gráfico de donut de ingresos por plan a la derecha...").
3.  **Selección de Gráficos:** Para cada métrica o conjunto de datos, recomienda el tipo de gráfico más adecuado (líneas, barras, donut, etc.) y justifica tu elección.
4.  **Propuesta de Interacción:** Describe las funcionalidades interactivas (ej: "Filtro de fecha global que afecta a todos los gráficos", "Tooltips en los gráficos con datos detallados", "Click en una sección del gráfico de donut para filtrar la tabla de clientes").
5.  **Código de Implementación:**
    - El código JSX/TSX para la estructura del layout del dashboard (usando CSS Grid o Flexbox).
    - El código de ejemplo para al menos dos de los gráficos propuestos, utilizando la librería especificada.

---

### Versión para Terminal (ANSI)

```ansi
[1;35mActúa como un Especialista en UI/UX con experiencia en visualización de datos y dashboards.[0m
[1;34mTus metas son: Claridad de un vistazo, Jerarquía de la Información y Accionabilidad.[0m

[1m[PLATAFORMA Y TECNOLOGÍA][0m
- [1mPlataforma:[0m [1;33m`{{plataforma}}`[0m
- [1mStack de Frontend:[0m [1;33m`{{stack_frontend}}`[0m
- [1mLibrería de Gráficos:[0m [1;33m`{{libreria_graficos}}`[0m

[1m[OBJETIVO DEL DASHBOARD Y PERFIL DE USUARIO][0m
- [1mObjetivo:[0m [1;33m`{{objetivo_dashboard}}`[0m
- [1mUsuario:[0m [1;33m`{{perfil_usuario}}`[0m

[1m[MÉTRICAS Y DATOS DISPONIBLES][0m
- [1mKPIs Principales:[0m [1;33m`Ingresos Totales, Clientes Activos, Churn`[0m
- [1mDatos Secundarios:[0m [1;33m`Ingresos por plan, Nuevos clientes`[0m
- ...

[1m[FORMATO DE SALIDA][0m
1.  [1mJerarquía de la Información:[0m Qué es lo más importante.
2.  [1mLayout del Dashboard (Wireframe):[0m Esquema de la disposición.
3.  [1mSelección de Gráficos:[0m Recomienda el tipo de gráfico para cada métrica.
4.  [1mPropuesta de Interacción:[0m Funcionalidades interactivas (filtros, tooltips).
5.  [1mCódigo de Implementación:[0m Código JSX/TSX para el layout y ejemplos de gráficos.
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-dash="pbcopy < ~/superprompts/ui-ux/diseño-dashboard.md && echo 'Copiado: Prompt Diseño de Dashboard'"
# Para Linux
# alias sp-dash="xclip -selection clipboard < ~/superprompts/ui-ux/diseño-dashboard.md && echo 'Copiado: Prompt Diseño de Dashboard'"
```

### Crear un nuevo componente de gráfico
```bash
function new-chart-component() {
  if [ -z "$1" ]; then
    echo "Uso: new-chart-component NombreDelGrafico"
    return 1
  fi
  
  COMP_NAME=$1
  # Puedes adaptar esta ruta
  DIR_PATH="src/components/charts/$COMP_NAME"
  mkdir -p "$DIR_PATH"
  
  # Archivo del componente
  echo "import React from 'react';
// Importa aquí tu librería de gráficos, ej:
// import { LineChart, Line, XAxis, YAxis, Tooltip } from 'recharts';

const ${COMP_NAME} = ({ data }) => {
  return (
    <div>
      {/* Tu gráfico aquí */}
      <p>Gráfico: ${COMP_NAME}</p>
    </div>
  );
};

export default ${COMP_NAME};" > "$DIR_PATH/${COMP_NAME}.tsx"

  # Archivo de índice
  echo "export { default as ${COMP_NAME} } from './${COMP_NAME}';" > "$DIR_PATH/index.ts"

  echo "Componente de gráfico $COMP_NAME creado en $DIR_PATH"
}
```
