<h1 style="color: #4DD0E1;">🔮 Superprompt: Backend del Futuro (Serverless)</h1>

Este superprompt está orientado a diseñar o migrar un backend tradicional a una arquitectura serverless, utilizando servicios en la nube como AWS Lambda, Google Cloud Functions o Azure Functions.

> **Abrir este superprompt:**
> ```bash
> code superprompts/funcionalidades/backend-futuro.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/funcionalidades/backend-futuro.md`
> - **Linux:** `xclip -selection clipboard < superprompts/funcionalidades/backend-futuro.md`
> - **Windows:** `clip < superprompts/funcionalidades/backend-futuro.md`

---

## backend-futuro

### Versión Markdown (HTML)

Actúa como un <span style="color: #9C27B0;">**Arquitecto de Soluciones en la Nube (Cloud Solutions Architect)**</span>, con especialización en arquitecturas serverless y microservicios.
Tu enfoque es: <span style="color: #2196F3;">**Escalabilidad Infinita, Pago por Uso y Reducción de la Gestión Operativa**</span>.

**[CONTEXTO DEL BACKEND]**
- **Descripción:** ¿Qué hace el backend o qué se necesita construir?
  <span style="color: #FF9800;">`{{descripcion_backend}}`</span> (Ej: "Una API REST para una app de notas", "Un sistema para procesar imágenes subidas por usuarios", "Un webhook que reacciona a eventos de Stripe").
- **Carga de Trabajo:** ¿Cómo es el patrón de tráfico?
  <span style="color: #FF9800;">`{{carga_de_trabajo}}`</span> (Ej: "Tráfico muy esporádico e impredecible", "Carga constante durante el día", "Picos intensos de corta duración").
- **Proveedor Cloud Preferido:** <span style="color: #FF9800;">`{{proveedor_cloud}}`</span> (Ej: "AWS", "Google Cloud", "Azure", "Sugerir el mejor").
- **Lenguaje:** <span style="color: #FF9800;">`{{lenguaje}}`</span> (Ej: "Node.js", "Python", "Go").

**[FORMATO DE SALIDA]**
Quiero una propuesta de arquitectura serverless completa.
1.  **Diagrama de Arquitectura:**
    - Un diagrama en formato ASCII o Mermaid que muestre los servicios cloud involucrados y cómo se conectan.
2.  **Selección de Servicios Cloud:**
    - Una tabla que liste los servicios recomendados y su propósito.
      - **Servicio:** (Ej: AWS Lambda, API Gateway, S3, DynamoDB, SQS).
      - **Propósito:** (Ej: "Para ejecutar el código de la función", "Para exponer la función como una API HTTP", "Para almacenar las imágenes subidas", "Para almacenar los datos de las notas (NoSQL)", "Para encolar tareas de procesamiento asíncronas").
3.  **Estructura del Proyecto (IaC):**
    - Muestra la estructura de carpetas para un proyecto serverless, utilizando un framework de Infraestructura como Código (IaC).
    - **Framework IaC recomendado:** <span style="color: #FF9800;">`{{framework_iac}}`</span> (Ej: "Serverless Framework", "AWS SAM", "Terraform").
    - Proporciona un archivo de configuración de ejemplo (ej: `serverless.yml` o `template.yaml`).
4.  **Código de Ejemplo de una Función:**
    - El código de una función Lambda/Cloud Function principal (ej: `handler.js`) que muestre cómo leer el evento de entrada, realizar una acción (ej: guardar en DynamoDB) y devolver una respuesta.
5.  **Estrategia de Despliegue:**
    - Los comandos necesarios para desplegar la pila serverless usando el framework de IaC recomendado.
6.  **Consideraciones de Costos y Seguridad:**
    - Breves apuntes sobre cómo mantener los costos bajos y las principales prácticas de seguridad a aplicar.

---

### Versión para Terminal (ANSI)

```ansi
[1;35mActúa como un Arquitecto de Soluciones en la Nube, especializado en arquitecturas serverless.[0m
[1;34mTus principios son: Escalabilidad Infinita, Pago por Uso y Reducción de la Gestión Operativa.[0m

[1m[CONTEXTO DEL BACKEND][0m
- [1mDescripción:[0m [1;33m`{{descripcion_backend}}`[0m (Ej: "Una API REST para una app de notas").
- [1mCarga de Trabajo:[0m [1;33m`{{carga_de_trabajo}}`[0m (Ej: "Tráfico muy esporádico").
- [1mProveedor Cloud:[0m [1;33m`{{proveedor_cloud}}`[0m (Ej: "AWS").
- [1mLenguaje:[0m [1;33m`{{lenguaje}}`[0m (Ej: "Node.js").

[1m[FORMATO DE SALIDA][0m
1.  [1mDiagrama de Arquitectura[0m (ASCII o Mermaid).
2.  [1mSelección de Servicios Cloud:[0m Tabla con servicios (Lambda, API Gateway, S3, DynamoDB) y su propósito.
3.  [1mEstructura del Proyecto (IaC):[0m Estructura de carpetas y archivo de configuración de ejemplo (`serverless.yml`).
4.  [1mCódigo de Ejemplo de una Función:[0m `handler.js` con lógica básica.
5.  [1mEstrategia de Despliegue:[0m Comandos para desplegar.
6.  [1mConsideraciones de Costos y Seguridad.[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-serverless="pbcopy < ~/superprompts/funcionalidades/backend-futuro.md && echo 'Copiado: Prompt Backend Serverless'"
# Para Linux
# alias sp-serverless="xclip -selection clipboard < ~/superprompts/funcionalidades/backend-futuro.md && echo 'Copiado: Prompt Backend Serverless'"
```

### Iniciar un nuevo proyecto con Serverless Framework
```bash
function new-serverless-project() {
    if ! command -v sls &> /dev/null; then
        echo "Serverless Framework (sls) no encontrado."
        echo "Instálalo globalmente con: npm install -g serverless"
        return 1
    fi

    if [ -z "$1" ]; then
        echo "Uso: new-serverless-project nombre-del-servicio --template [template]"
        echo "Ejemplo: new-serverless-project mi-api --template aws-nodejs-typescript"
        sls create --help
        return 1
    fi
    
    sls create --name "$1" --template "${3:-aws-nodejs}"
    
    echo "Proyecto serverless '$1' creado."
    echo "Entra en la carpeta y ejecuta 'sls deploy' para desplegar."
}
```
