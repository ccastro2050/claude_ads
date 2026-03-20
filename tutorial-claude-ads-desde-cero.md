# Tutorial Completo: Claude Ads desde Cero

## Guía paso a paso en Windows

---

## Tabla de Contenidos

1. [Conceptos básicos](#1-conceptos-básicos)
2. [Instalar Visual Studio Code](#2-instalar-visual-studio-code)
3. [Instalar Node.js](#3-instalar-nodejs)
4. [Instalar Claude Code](#4-instalar-claude-code)
5. [Instalar el skill Claude Ads](#5-instalar-el-skill-claude-ads)
6. [Verificar la instalación](#6-verificar-la-instalación)
7. [Los 12 comandos de Claude Ads](#7-los-12-comandos-de-claude-ads)
8. [Conectar tus cuentas de publicidad](#8-conectar-tus-cuentas-de-publicidad)
9. [Ejemplos prácticos](#9-ejemplos-prácticos)
10. [Caso de uso completo: ecommerce de ropa](#10-caso-de-uso-completo-ecommerce-de-ropa)
11. [Preguntas frecuentes](#11-preguntas-frecuentes)

---

## Flujo general: de cero a tu primera auditoría

```
┌─────────────────────────────────────────────────────────────────────┐
│                    RUTA DE INSTALACIÓN COMPLETA                     │
└─────────────────────────────────────────────────────────────────────┘

  ┌──────────────┐     ┌──────────────┐     ┌──────────────────────┐
  │  1. Instalar │     │  2. Instalar │     │  3. Instalar         │
  │    VSCode    │────>│   Node.js    │────>│    Claude Code       │
  │  (editor)    │     │   (motor)    │     │  (npm install -g ...)│
  └──────────────┘     └──────────────┘     └──────────┬───────────┘
                                                       │
                                                       v
                                            ┌──────────────────────┐
                                            │  4. Iniciar sesión   │
                                            │  en Anthropic        │
                                            │  (claude)            │
                                            └──────────┬───────────┘
                                                       │
                                                       v
                                            ┌──────────────────────┐
                                            │  5. Instalar skill   │
                                            │  Claude Ads          │
                                            │  (irm ... | iex)     │
                                            └──────────┬───────────┘
                                                       │
                                                       v
                                            ┌──────────────────────┐
                                            │  6. Verificar        │
                                            │  /ads audit          │
                                            │  ¡Listo!             │
                                            └──────────────────────┘
```

---

## 1. Conceptos básicos

Antes de instalar nada, es importante que entiendas qué es cada cosa y por qué la necesitas.

### ¿Qué es Visual Studio Code (VSCode)?

**VSCode** es un editor de código gratuito creado por Microsoft. Piensa en él como un "Word para programadores", pero mucho más poderoso. Lo necesitas porque Claude Code funciona dentro de él como una extensión.

- Es gratuito y de código abierto
- Funciona en Windows, Mac y Linux
- Tiene miles de extensiones que le agregan funcionalidades
- Tiene una **terminal integrada** (una pantalla negra donde escribes comandos)

### ¿Qué es una terminal?

La **terminal** (también llamada consola, línea de comandos o shell) es una forma de comunicarte con tu computadora escribiendo texto en vez de hacer clic con el mouse. En vez de abrir carpetas con doble clic, escribes comandos como `cd mi-carpeta`. Parece intimidante al principio, pero solo necesitas unos pocos comandos.

**Ejemplo:** En vez de abrir el explorador de archivos y navegar a una carpeta, en la terminal escribes:

```
cd "C:\Users\tu-usuario\Desktop\mi-proyecto"
```

### ¿Qué es Node.js?

**Node.js** es un programa que permite ejecutar JavaScript fuera del navegador. Claude Code está construido con JavaScript, así que necesitas Node.js instalado para que funcione. Piensa en él como el "motor" que hace que Claude Code pueda correr en tu computadora.

### ¿Qué es npm?

**npm** (Node Package Manager) es el instalador de programas de Node.js. Cuando instalas Node.js, npm se instala automáticamente. Es como la "tienda de apps" del mundo JavaScript. Lo vas a usar para instalar Claude Code con un simple comando.

### Flujo: ¿Cómo se conecta todo?

```
┌─────────────────────────────────────────────────────────────────┐
│                  ¿CÓMO ENCAJA CADA PIEZA?                       │
└─────────────────────────────────────────────────────────────────┘

  ┌─────────┐    contiene    ┌─────────────┐    potencia    ┌───────────┐
  │ VSCode  │───────────────>│ Claude Code  │──────────────>│ Claude    │
  │ (editor)│    extensión   │ (herramienta)│   skill       │   Ads     │
  └─────────┘                └──────┬──────┘               └─────┬─────┘
                                    │                             │
                              necesita para                  analiza datos
                                correr                       que TÚ le das
                                    │                             │
                              ┌─────v──────┐         ┌────────────────────┐
                              │  Node.js   │         │  Tus datos de:     │
                              │  (motor)   │         │  Google, Meta,     │
                              │  + npm     │         │  TikTok, LinkedIn, │
                              └────────────┘         │  YouTube, Microsoft│
                                                     │  (CSVs, métricas,  │
                                                     │   capturas)        │
                                                     └────────────────────┘
```

### ¿Qué es Claude Code?

**Claude Code** es una herramienta oficial de Anthropic (la empresa que creó a Claude, la IA). Es una versión de Claude que vive directamente en tu editor de código (VSCode) y puede:

- Leer y escribir archivos en tu computadora
- Ejecutar comandos en la terminal
- Navegar por internet
- Conectarse a APIs externas

La diferencia con el Claude normal (el que usas en claude.ai) es que Claude Code tiene **acceso a tu computadora local** y puede ejecutar acciones reales, no solo conversar.

### ¿Qué es un Skill?

Un **skill** es como un "pack de habilidades" que le agregas a Claude Code. Por defecto, Claude Code es un asistente de programación generalista. Cuando le instalas un skill, le das conocimiento especializado y comandos nuevos.

Es como la diferencia entre un empleado nuevo (Claude Code base) y ese mismo empleado después de un curso intensivo de publicidad digital (Claude Code + Claude Ads).

### ¿Qué es Claude Ads?

**Claude Ads** es un skill que convierte a Claude Code en un especialista de publicidad digital. Una vez instalado, Claude puede:

- **Auditar** tus campañas de publicidad en 6 plataformas
- **Planificar** campañas nuevas con estrategias por industria
- **Optimizar** presupuestos y creativos
- **Analizar** a tu competencia
- **Evaluar** tus landing pages y creativos

### Las 6 plataformas que cubre

| Plataforma | Qué incluye | Checks |
|---|---|---|
| **Google Ads** | Search, Performance Max, Display, YouTube, Demand Gen | 74 checks |
| **Meta Ads** | Facebook, Instagram, Advantage+ Shopping | Pixel/CAPI, creativos, audiencias |
| **YouTube Ads** | Skippable, Shorts, Demand Gen | Análisis de video y engagement |
| **TikTok Ads** | Smart+, TikTok Shop | Optimizado para contenido nativo |
| **LinkedIn Ads** | B2B, Lead Gen, Targeted Lead Accounts | Campañas enterprise y SaaS |
| **Microsoft Ads** | Bing y red de Microsoft | Importación desde Google |

### Flujo: ¿Qué puede hacer Claude Ads?

```
┌─────────────────────────────────────────────────────────────────┐
│              LAS 5 CAPACIDADES DE CLAUDE ADS                    │
└─────────────────────────────────────────────────────────────────┘

              Tú le das tus datos + escribes un comando
                                  │
                                  v
                    ┌─────────────────────────────┐
                    │        Claude Ads            │
                    └──────────┬──────────────────┘
                               │
            ┌──────────┬───────┴────────┬───────────┬──────────┐
            v          v                v           v          v
     ┌──────────┐ ┌──────────┐  ┌────────────┐ ┌────────┐ ┌────────┐
     │ AUDITAR  │ │PLANIFICAR│  │ OPTIMIZAR  │ │ANALIZAR│ │EVALUAR │
     │campañas  │ │ campañas │  │presupuesto │ │competen│ │landing │
     │existentes│ │  nuevas  │  │y creativos │ │  cia   │ │pages y │
     │          │ │          │  │            │ │        │ │creativos│
     │ /ads     │ │ /ads     │  │ /ads budget│ │ /ads   │ │ /ads   │
     │  audit   │ │  plan    │  │ /ads       │ │competi-│ │landing │
     │          │ │          │  │  creative  │ │  tor   │ │ /ads   │
     │          │ │          │  │            │ │        │ │creative│
     └────┬─────┘ └────┬─────┘  └─────┬──────┘ └───┬────┘ └───┬───┘
          │            │              │             │          │
          v            v              v             v          v
     ┌─────────────────────────────────────────────────────────────┐
     │              Reporte con recomendaciones accionables        │
     └─────────────────────────────────────────────────────────────┘
```

### ¿Qué es el Ads Health Score?

Es una puntuación de **0 a 100** que indica la salud general de tus campañas publicitarias. Claude ejecuta **190+ checks** automáticos (verificaciones) en todas tus plataformas y te da un puntaje:

| Grado | Puntaje | Significado |
|---|---|---|
| A | 90 - 100 | Excelente, campañas muy bien optimizadas |
| B | 80 - 89 | Bien, con algunas mejoras posibles |
| C | 60 - 79 | Regular, hay oportunidades importantes |
| D | 40 - 59 | Mal, necesita atención urgente |
| F | 0 - 39 | Crítico, campañas en problemas serios |

### ¿Qué es una API?

**API** (Application Programming Interface) es la forma en que dos programas se comunican entre sí. Cuando conectas tu cuenta de Google Ads con Claude, Claude usa la API de Google para leer tus campañas. Es como darle a alguien la llave de tu oficina para que pueda entrar y trabajar.

### Flujo: ¿Cómo funciona la auditoría con 6 agentes?

```
┌─────────────────────────────────────────────────────────────────┐
│            FLUJO DE AUDITORÍA COMPLETA (/ads audit)             │
└─────────────────────────────────────────────────────────────────┘

         Tú escribes: /ads audit
                  │
                  v
        ┌─────────────────┐
        │  Claude Ads     │
        │  (coordinador)  │
        └────────┬────────┘
                 │
                 │ Delega en paralelo a 6 sub-agentes
                 │
    ┌────────┬───┴────┬────────┬─────────┬──────────┐
    v        v        v        v         v          v
┌───────┐┌───────┐┌───────┐┌───────┐┌────────┐┌─────────┐
│Google ││ Meta  ││YouTube││TikTok ││LinkedIn││Microsoft│
│ Ads   ││ Ads   ││ Ads   ││ Ads   ││  Ads   ││  Ads    │
│Agent  ││Agent  ││Agent  ││Agent  ││ Agent  ││ Agent   │
│       ││       ││       ││       ││        ││         │
│74     ││checks ││checks ││checks ││ checks ││ checks  │
│checks ││espec. ││espec. ││espec. ││ espec. ││ espec.  │
└───┬───┘└───┬───┘└───┬───┘└───┬───┘└───┬────┘└────┬────┘
    │        │        │        │        │          │
    v        v        v        v        v          v
    └────────┴────────┴───┬────┴────────┴──────────┘
                          │
                          v
               ┌─────────────────────┐
               │   REPORTE FINAL     │
               │                     │
               │ - Ads Health Score  │
               │   (0 a 100)        │
               │ - Problemas por    │
               │   severidad        │
               │ - Quick wins       │
               │ - Recomendaciones  │
               └─────────────────────┘
```

---

## 2. Instalar Visual Studio Code

### Paso 1: Descargar VSCode

1. Abre tu navegador (Chrome, Edge, Firefox, etc.)
2. Ve a: **https://code.visualstudio.com**
3. Haz clic en el botón grande azul que dice **"Download for Windows"**
4. Se descargará un archivo llamado algo como `VSCodeUserSetup-x64-1.xx.x.exe`

### Paso 2: Instalar VSCode

1. Ve a tu carpeta de **Descargas** y haz doble clic en el archivo que descargaste
2. Si Windows te pregunta "¿Quieres permitir que esta aplicación haga cambios?", haz clic en **Sí**
3. Acepta los términos de licencia y haz clic en **Siguiente**
4. **IMPORTANTE:** En la pantalla de "Seleccionar tareas adicionales", marca estas opciones:
   - [x] Agregar la acción "Abrir con Code" al menú contextual de archivos
   - [x] Agregar la acción "Abrir con Code" al menú contextual de directorios
   - [x] Agregar a PATH (esto es muy importante)
5. Haz clic en **Instalar**
6. Cuando termine, haz clic en **Finalizar**

### Paso 3: Abrir VSCode por primera vez

1. Busca "Visual Studio Code" en el menú de inicio de Windows
2. Ábrelo. Verás una pantalla de bienvenida
3. Puedes elegir un tema (oscuro o claro) según tu preferencia
4. Cierra las pestañas de bienvenida

### Paso 4: Conocer la terminal de VSCode

1. En VSCode, ve al menú superior: **Terminal > New Terminal** (o presiona `` Ctrl + ` ``)
2. En la parte inferior se abrirá una ventana negra (o del color de tu tema): esa es la terminal
3. Escribe `echo "Hola Mundo"` y presiona Enter. Si ves "Hola Mundo", la terminal funciona

> **Tip:** La terminal de VSCode es donde vas a escribir todos los comandos de instalación. No necesitas abrir otra ventana.

### Paso 5: Configurar la terminal como Bash (recomendado)

Por defecto, VSCode en Windows puede abrir PowerShell. Para este tutorial usaremos **bash** (que viene con Git):

1. En la terminal, haz clic en la flechita hacia abajo junto al icono `+`
2. Selecciona **"Git Bash"** si aparece como opción
3. Si no aparece, no te preocupes. Instalaremos Git en el siguiente paso

---

## 3. Instalar Node.js

Claude Code necesita Node.js para funcionar. Aquí lo instalamos.

### Paso 1: Descargar Node.js

1. Ve a: **https://nodejs.org**
2. Descarga la versión **LTS** (Long Term Support) - es el botón verde de la izquierda
3. Se descargará un archivo como `node-v22.xx.x-x64.msi`

### Paso 2: Instalar Node.js

1. Haz doble clic en el archivo descargado
2. Haz clic en **Next** en cada pantalla
3. Acepta los términos de licencia
4. Deja la ruta de instalación por defecto
5. **IMPORTANTE:** En la pantalla de "Tools for Native Modules", marca la casilla que dice **"Automatically install the necessary tools"** si aparece
6. Haz clic en **Install**
7. Si te pide permisos de administrador, haz clic en **Sí**
8. Haz clic en **Finish**

### Paso 3: Verificar la instalación

1. **Cierra VSCode completamente** y vuélvelo a abrir (esto es importante para que reconozca Node.js)
2. Abre la terminal en VSCode (`` Ctrl + ` ``)
3. Escribe estos comandos uno por uno:

```bash
node --version
```

Deberías ver algo como `v22.x.x`

```bash
npm --version
```

Deberías ver algo como `10.x.x`

Si ves los números de versión, Node.js está instalado correctamente.

> **Si no funciona:** Cierra TODAS las ventanas de VSCode, reinicia tu computadora, y vuelve a intentar.

---

## 4. Instalar Claude Code

### Paso 1: Instalar Claude Code con npm

1. Abre VSCode
2. Abre la terminal (`` Ctrl + ` ``)
3. Escribe el siguiente comando:

```bash
npm install -g @anthropic-ai/claude-code
```

Espera a que termine. Verás varias líneas de texto. Cuando vuelva a aparecer el cursor parpadeante, la instalación terminó.

### Paso 2: Verificar la instalación

```bash
claude --version
```

Deberías ver un número de versión.

### Paso 3: Iniciar sesión en Claude

La primera vez que uses Claude Code necesitas iniciar sesión con tu cuenta de Anthropic:

1. En la terminal escribe:

```bash
claude
```

2. Claude te pedirá que inicies sesión. Te dará un enlace web
3. Abre ese enlace en tu navegador
4. Inicia sesión con tu cuenta de Anthropic (o crea una en https://console.anthropic.com si no tienes)
5. Autoriza el acceso
6. Vuelve a la terminal. Claude debería estar activo

> **Requisito:** Necesitas una cuenta de Anthropic con un plan activo (Claude Pro, Team o API con crédito). Claude Code no es gratuito.

### Paso 4: Instalar la extensión de Claude Code en VSCode (opcional pero recomendado)

También puedes usar Claude Code directamente como extensión visual de VSCode:

1. En VSCode, haz clic en el icono de **Extensiones** en la barra lateral izquierda (parece 4 cuadritos)
2. En el buscador escribe: **"Claude Code"**
3. Busca la extensión oficial de **Anthropic**
4. Haz clic en **Install**
5. Una vez instalada, verás el icono de Claude en la barra lateral

### Paso 5: Probar que Claude funciona

En la terminal de VSCode, escribe:

```bash
claude "Hola, dime en una frase qué puedes hacer"
```

Si Claude te responde, todo está funcionando.

---

## 5. Instalar el skill Claude Ads

### Flujo: ¿Qué hace el instalador automáticamente?

```
┌─────────────────────────────────────────────────────────────────┐
│     LO QUE PASA CUANDO EJECUTAS EL COMANDO DE INSTALACIÓN      │
└─────────────────────────────────────────────────────────────────┘

  irm ...install.ps1 | iex
          │
          v
  ┌───────────────────┐
  │ 1. Descarga skill │──> Archivos principales de Claude Ads
  └────────┬──────────┘
           v
  ┌───────────────────┐    ┌─────────────────────────────────────┐
  │ 2. Sub-skills     │──> │ google, meta, youtube, tiktok,      │
  └────────┬──────────┘    │ linkedin, microsoft, creative,      │
           │               │ landing, budget, competitor, plan    │
           v               └─────────────────────────────────────┘
  ┌───────────────────┐
  │ 3. Sub-agentes    │──> 6 agentes especializados (uno por plataforma)
  └────────┬──────────┘
           v
  ┌───────────────────┐
  │ 4. Scripts Python │──> Herramientas de análisis y scraping
  └────────┬──────────┘
           v
  ┌───────────────────┐
  │ 5. Dependencias   │──> Librerías de Python necesarias
  └────────┬──────────┘
           v
  ┌───────────────────┐
  │ 6. Chromium       │──> Navegador headless (~170 MB)
  │    (~2-3 min)     │    Para capturas de landing pages y anuncios
  └────────┬──────────┘
           v
      ¡Instalado!
```

Ahora viene lo importante: agregarle a Claude las habilidades de publicidad digital.

### Paso 1: Abrir PowerShell como administrador en VSCode

1. En VSCode, abre la terminal (`` Ctrl + ` ``)
2. Haz clic en la flechita hacia abajo junto al `+` en la terminal
3. Selecciona **"PowerShell"**

### Paso 2: Ejecutar el instalador

Copia y pega este comando en la terminal PowerShell:

```powershell
irm https://raw.githubusercontent.com/AgriciDaniel/claude-ads/main/install.ps1 | iex
```

Presiona **Enter** y espera.

### ¿Qué hace este comando?

- `irm` = Invoke-RestMethod: descarga el contenido de una URL
- La URL apunta al script de instalación oficial en GitHub
- `| iex` = lo ejecuta automáticamente

### ¿Qué instala el script?

El instalador hace todo esto automáticamente:

1. Descarga los archivos del skill de Claude Ads
2. Los coloca en la carpeta correcta (`~/.claude/skills/`)
3. Instala sub-skills especializados (uno por cada plataforma)
4. Instala sub-agentes (los 6 agentes que trabajan en paralelo)
5. Instala scripts de Python necesarios
6. Instala dependencias de Python (librerías)
7. Instala Chromium (un navegador sin interfaz gráfica que Claude usa para tomar capturas de pantalla de landing pages y anuncios)

### ¿Cuánto tarda?

Entre 2 y 5 minutos dependiendo de tu conexión a internet. La parte más pesada es la descarga de Chromium (~170 MB).

### Si el comando falla por política de ejecución

Si ves un error sobre "execution policy", ejecuta esto primero:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Y luego vuelve a ejecutar el comando de instalación.

---

## 6. Verificar la instalación

### Prueba rápida

1. Abre Claude Code (en la terminal escribe `claude` o usa la extensión de VSCode)
2. Escribe:

```
/ads audit
```

3. Si Claude responde pidiendo información de tus campañas, **el skill está instalado correctamente**

### Verificar archivos instalados

También puedes verificar manualmente que los archivos estén en su lugar:

```bash
ls ~/.claude/skills/
```

Deberías ver una carpeta relacionada con `claude-ads` o archivos `.md` del skill.

---

## 7. Los 12 comandos de Claude Ads

### Flujo: ¿Qué comando uso según mi necesidad?

```
┌─────────────────────────────────────────────────────────────────┐
│              ¿QUÉ NECESITAS HACER?                              │
└─────────────────────────────────────────────────────────────────┘

  "Quiero saber cómo          "Quiero crear una         "Quiero mejorar lo
   están mis campañas"          campaña nueva"            que ya tengo"
          │                          │                         │
          v                          v                         v
   ┌─────────────┐           ┌──────────────┐          ┌─────────────┐
   │  AUDITORÍA  │           │PLANIFICACIÓN │          │OPTIMIZACIÓN │
   └──────┬──────┘           └──────┬───────┘          └──────┬──────┘
          │                         │                         │
    ┌─────┴──────┐                  │               ┌────────┼────────┐
    │            │                  │               │        │        │
    v            v                  v               v        v        v
 Todas      Una sola          /ads plan        /ads      /ads     /ads
 a la vez   plataforma         <tipo>        creative  budget  competitor
    │            │                               │        │        │
    v            v                               v        v        v
 /ads        /ads google                     Revisa   Revisa   Espía a
 audit       /ads meta                       tus      tu       tu
 (190+       /ads youtube                    anuncios gasto    competencia
 checks)     /ads tiktok
             /ads linkedin
             /ads microsoft
```

Una vez instalado, tienes estos 12 comandos disponibles:

### Comandos de auditoría

| Comando | Qué hace |
|---|---|
| `/ads audit` | Auditoría completa multi-plataforma con 6 agentes en paralelo. Ejecuta los 190+ checks |
| `/ads google` | Análisis profundo solo de Google Ads (Search, PMax, Display, YouTube, Demand Gen) |
| `/ads meta` | Análisis profundo solo de Meta Ads (Facebook, Instagram, Advantage+) |
| `/ads youtube` | Análisis específico de campañas de YouTube |
| `/ads tiktok` | Análisis específico de campañas de TikTok |
| `/ads linkedin` | Análisis B2B de campañas en LinkedIn |
| `/ads microsoft` | Análisis de campañas en Microsoft/Bing Ads |

### Comandos de optimización

| Comando | Qué hace |
|---|---|
| `/ads creative` | Auditoría de calidad creativa en todas las plataformas |
| `/ads landing` | Evaluación de tus landing pages (páginas de destino) |
| `/ads budget` | Revisión de presupuesto y estrategia de pujas |
| `/ads competitor` | Inteligencia de anuncios de competidores |

### Comando de planificación

| Comando | Qué hace |
|---|---|
| `/ads plan <tipo>` | Planificación estratégica por industria |

Los tipos disponibles para `/ads plan` son:

- `saas` - Software as a Service
- `ecommerce` - Tiendas online
- `local` - Servicios locales (plomeros, dentistas, etc.)
- `b2b` - Business to Business (enterprise)
- `infoproductos` - Cursos, ebooks, membresías
- `apps` - Aplicaciones móviles
- `realestate` - Bienes raíces
- `salud` - Salud y bienestar
- `finanzas` - Servicios financieros
- `agencias` - Agencias de marketing
- `genérico` - Cualquier otro tipo de negocio

---

## 8. Cómo pasarle datos a Claude Ads

### Flujo: ¿Cómo le das tus datos de campañas?

```
┌─────────────────────────────────────────────────────────────────┐
│          ¿CÓMO LE PASAS TUS DATOS A CLAUDE ADS?                │
└─────────────────────────────────────────────────────────────────┘

  Claude Ads NO se conecta directamente a las plataformas.
  Tú le proporcionas los datos y él los analiza como un consultor experto.

                        ┌──────────┐
                        │   TÚ     │
                        └────┬─────┘
                             │
                  ¿De dónde sacas los datos?
                             │
           ┌─────────────────┼─────────────────┐
           │                 │                  │
           v                 v                  v
   ┌──────────────┐  ┌──────────────┐   ┌──────────────┐
   │   OPCIÓN 1   │  │   OPCIÓN 2   │   │   OPCIÓN 3   │
   │              │  │              │   │              │
   │ Exportar CSV │  │ Copiar y     │   │ Capturas de  │
   │ desde tu Ads │  │ pegar las    │   │ pantalla del │
   │ Manager      │  │ métricas     │   │ dashboard    │
   │              │  │ directamente │   │              │
   │ Google Ads > │  │              │   │ Claude puede │
   │ Informes >   │  │ CPC, CTR,    │   │ leer imágenes│
   │ Descargar    │  │ ROAS, gasto, │   │ y extraer    │
   │              │  │ conversiones │   │ los datos    │
   └──────┬───────┘  └──────┬───────┘   └──────┬───────┘
          │                 │                   │
          └─────────────────┼───────────────────┘
                            │
                            v
               ┌─────────────────────┐
               │  Claude Ads analiza │
               │  con 190+ checks y  │
               │  te da un reporte   │
               │  con recomendaciones│
               └─────────────────────┘
```

> **Aclaración importante:** Claude Ads es una herramienta de **análisis y consultoría**. No necesitas credenciales de API ni conectar cuentas. Tú le das los datos (como se los darías a un consultor de marketing) y él los analiza con sus 190+ checks especializados.

### Opción 1: Exportar desde tu plataforma (recomendado)

La forma más completa. Cada plataforma te permite descargar reportes:

| Plataforma | Cómo exportar |
|---|---|
| **Google Ads** | Informes > Campañas > Descargar como CSV |
| **Meta Ads** | Ads Manager > Columnas personalizadas > Exportar |
| **YouTube** | Google Ads filtrado por campañas de Video > Exportar |
| **TikTok Ads** | Ads Manager > Panel > Exportar datos |
| **LinkedIn** | Campaign Manager > Rendimiento > Exportar |
| **Microsoft Ads** | Informes > Rendimiento de campañas > Descargar |

Luego pegas el contenido del CSV en tu conversación con Claude o le indicas la ruta del archivo.

### Opción 2: Copiar y pegar métricas

Si no quieres exportar archivos, simplemente copia las métricas clave:

```
/ads audit

Mis campañas de Meta Ads del último mes:

- Campaña "Prospecting": Gasto $1,200, CPM $14, CTR 1.4%,
  Conversiones 38, CPA $31.58, ROAS 2.1x
- Campaña "Retargeting": Gasto $500, CPM $9, CTR 3.8%,
  Conversiones 24, CPA $20.83, ROAS 4.5x

Industria: ecommerce de muebles
Ticket promedio: $120
País: México
```

### Opción 3: Capturas de pantalla

Claude puede leer imágenes. Toma una captura de tu dashboard y adjúntala en la conversación. Claude extraerá las métricas visibles y las analizará.

### Funciones extras que sí se conectan a internet

Claude Ads incluye herramientas que **sí** usan internet, pero para otras cosas:

| Función | Qué hace | Cuándo se usa |
|---|---|---|
| **Análisis de landing pages** | Abre tu página web con un navegador headless y mide velocidad, diseño, CTAs | `/ads landing` |
| **Capturas de pantalla** | Toma screenshots de páginas web en diferentes tamaños | Parte de `/ads landing` |
| **Generación de imágenes** | Crea imágenes para anuncios con IA (requiere API key de Gemini, OpenAI, etc.) | `/ads creative` o `/ads photoshoot` |
| **Análisis de competencia** | Puede navegar páginas web públicas de competidores | `/ads competitor` |

---

## 9. Ejemplos prácticos

### Ejemplo 1: Tu primera auditoría (sin cuentas conectadas)

Aunque no tengas cuentas conectadas, puedes hacer una auditoría manual:

```
/ads audit

Aquí están los datos de mis campañas de Google Ads del último mes:

- Campaña "Search - Marca": CPC $0.45, CTR 8.2%, Conv. Rate 5.1%, ROAS 4.2x
- Campaña "Search - Genéricas": CPC $1.80, CTR 2.1%, Conv. Rate 1.3%, ROAS 1.1x
- Campaña "PMax - Productos": CPC $0.92, CTR 3.4%, Conv. Rate 2.8%, ROAS 3.5x
- Presupuesto mensual total: $5,000
- Industria: ecommerce de ropa deportiva
```

### Ejemplo 2: Auditoría completa con cuentas conectadas

```
/ads audit

Analiza todas mis campañas activas en todas las plataformas conectadas. Quiero:
1. Mi Ads Health Score general
2. Los 5 problemas más urgentes ordenados por impacto
3. Quick wins que pueda implementar hoy
4. Comparación de rendimiento entre plataformas
```

### Ejemplo 3: Planificar una campaña nueva

```
/ads plan ecommerce

Tipo de negocio: Ecommerce de suplementos deportivos
Producto: Proteína whey premium
Presupuesto mensual: $3,000
Objetivo: Ventas online
Mercado: México y Colombia

Crea un plan de campaña completo con: selección de plataformas, estructura de
campañas, audiencias sugeridas, presupuesto por plataforma y KPIs objetivo.
```

### Ejemplo 4: Analizar a la competencia

```
/ads competitor

Mis competidores principales son: GNC, MyProtein, BSN.
Mi industria es: suplementos deportivos.

Analiza sus anuncios activos, identifica sus estrategias principales y dame
oportunidades donde pueda diferenciarme.
```

### Ejemplo 5: Optimizar presupuesto

```
/ads budget

Mi presupuesto mensual total es: $5,000.
Mis plataformas activas son: Google Ads y Meta Ads.
Mi objetivo principal es: conversiones (ventas online).

Analiza dónde estoy gastando de más, dónde estoy sub-invirtiendo, y recomienda
una redistribución óptima basada en el rendimiento actual.
```

### Ejemplo 6: Revisar un creativo

```
/ads creative

Revisa este anuncio que estoy por lanzar en Meta:

Título: "Proteína Whey Premium - 30% OFF solo hoy"
Texto principal: "La proteína #1 de México ahora con descuento.
25g de proteína por scoop. Envío gratis en compras mayores a $500."
CTA: "Comprar ahora"
Imagen: [descripción de la imagen o adjunta la imagen]

Dime qué mejorar antes de lanzarlo.
```

---

## 10. Caso de uso completo: ecommerce de ropa

Este es un ejemplo realista de cómo usar Claude Ads de principio a fin. Imagina que tienes una tienda online de ropa deportiva llamada **"FitWear"** con $5,000 USD de presupuesto mensual en Google Ads y Meta Ads.

### Flujo: Las 5 fases del caso de uso

```
┌─────────────────────────────────────────────────────────────────┐
│          CASO COMPLETO: FITWEAR - ECOMMERCE DE ROPA             │
└─────────────────────────────────────────────────────────────────┘

  FASE 1          FASE 2          FASE 3          FASE 4          FASE 5
 Auditoría ────> Competencia ──> Presupuesto ──> Creativos ────> Plan nuevo
 ¿Cómo estoy?   ¿Qué hacen     ¿Gasto bien?    ¿Mis anuncios   Campaña de
                 los demás?                      son buenos?     temporada

 /ads audit     /ads competitor  /ads budget     /ads creative   /ads plan
                                                                 ecommerce
      │               │               │               │               │
      v               v               v               v               v
 Health Score    Oportunidades   Redistribución  Mejoras en      Plan completo
 + problemas    vs competencia  óptima          copy e imagen   para nueva
 + quick wins                                                   campaña
```

---

### FASE 1: Auditoría inicial

Lo primero es saber en qué estado están tus campañas. Abres Claude Code y escribes:

```
/ads audit

Soy dueño de FitWear, una tienda online de ropa deportiva.
Presupuesto mensual: $5,000 USD ($3,000 en Google Ads, $2,000 en Meta Ads).

Datos de Google Ads (último mes):
- Campaña "Search - Marca FitWear": CPC $0.38, CTR 9.1%, Conv. Rate 6.2%, ROAS 5.8x, Gasto $400
- Campaña "Search - Ropa deportiva": CPC $1.95, CTR 1.8%, Conv. Rate 0.9%, ROAS 0.7x, Gasto $1,200
- Campaña "PMax - Catálogo": CPC $0.85, CTR 3.2%, Conv. Rate 2.4%, ROAS 3.1x, Gasto $1,400

Datos de Meta Ads (último mes):
- Campaña "Prospecting - Lookalike": CPM $12.50, CTR 1.2%, Conv. Rate 1.8%, ROAS 2.1x, Gasto $1,000
- Campaña "Retargeting - Carrito abandonado": CPM $8.20, CTR 3.5%, Conv. Rate 4.2%, ROAS 6.3x, Gasto $500
- Campaña "Advantage+ Shopping": CPM $11.00, CTR 1.5%, Conv. Rate 1.1%, ROAS 1.4x, Gasto $500

Ticket promedio: $65 USD
Margen bruto: 55%
Público objetivo: hombres y mujeres 25-45, interesados en fitness y running
País: México
```

**Lo que Claude te devuelve:**

- **Ads Health Score: 62/100 (Grado C)** — hay oportunidades importantes
- **Problema #1 (Crítico):** La campaña "Search - Ropa deportiva" tiene ROAS 0.7x, está perdiendo dinero. Gasta $1,200/mes con retorno negativo
- **Problema #2 (Alto):** La campaña "Advantage+ Shopping" tiene ROAS 1.4x, apenas cubre costos con margen del 55%
- **Quick Win #1:** Mover $600 de "Search - Ropa deportiva" a "Retargeting - Carrito abandonado" que tiene ROAS 6.3x
- **Quick Win #2:** Agregar palabras clave negativas en "Search - Ropa deportiva" para filtrar tráfico irrelevante

---

### FASE 2: Análisis de competencia

Ahora quieres saber qué hacen tus competidores:

```
/ads competitor

Mis competidores en México son: Martí, Innvictus, Under Armour México.
Mi industria es: ecommerce de ropa deportiva.
Mi tienda: FitWear (fitwearmx.com)

Analiza sus anuncios activos, identifica sus estrategias principales y dame
oportunidades donde pueda diferenciarme o superar su posicionamiento.
```

**Lo que Claude te devuelve:**

- Martí domina en búsqueda de marca y genéricos con alto presupuesto
- Innvictus apuesta fuerte en Meta con contenido de estilo de vida
- Under Armour tiene video ads muy fuertes en YouTube
- **Oportunidad:** Ninguno está haciendo bien TikTok ni tiene presencia en LinkedIn para venta corporativa (uniformes deportivos para empresas)
- **Oportunidad:** Los keywords long-tail como "leggins para correr mujer talla grande" tienen baja competencia

---

### FASE 3: Optimización de presupuesto

Con los datos de la auditoría y la competencia, optimizas tu gasto:

```
/ads budget

Presupuesto mensual total: $5,000 USD
Plataformas: Google Ads y Meta Ads
Objetivo: maximizar ventas online (ROAS mínimo 2.5x)
Datos de rendimiento: los que ya analizaste en la auditoría

Redistribuye mi presupuesto para maximizar el retorno. Incluye la opción de
abrir TikTok con un presupuesto de prueba si tiene sentido.
```

**Lo que Claude te devuelve:**

| Campaña | Antes | Después | Razón |
|---|---|---|---|
| Search - Marca | $400 | $400 | ROAS excelente, mantener |
| Search - Ropa deportiva | $1,200 | $500 | Reducir y optimizar keywords |
| PMax - Catálogo | $1,400 | $1,600 | ROAS sólido, escalar |
| Prospecting - Lookalike | $1,000 | $800 | Reducir ligeramente, refinar audiencia |
| Retargeting - Carrito | $500 | $900 | ROAS 6.3x, es tu campaña más rentable |
| Advantage+ Shopping | $500 | $300 | ROAS bajo, reducir mientras se optimiza |
| **TikTok - Prueba** | $0 | **$500** | Oportunidad identificada en competencia |
| **Total** | **$5,000** | **$5,000** | |

---

### FASE 4: Revisión de creativos

Antes de hacer los cambios, revisas tus anuncios:

```
/ads creative

Revisa estos anuncios activos de FitWear:

Anuncio Meta (Prospecting):
- Imagen: Mujer corriendo en un parque con leggins negros FitWear
- Título: "Ropa deportiva premium - Envío gratis"
- Texto: "Descubre FitWear. Ropa que se mueve contigo. Compra ahora y recibe
  envío gratis en pedidos mayores a $800."
- CTA: "Comprar ahora"

Anuncio Google (Search - Ropa deportiva):
- Título 1: "Ropa Deportiva | FitWear México"
- Título 2: "Envío Gratis en +$800"
- Título 3: "Hasta 30% de Descuento"
- Descripción: "Compra ropa deportiva de alta calidad. Leggins, tops, shorts
  y más. Envío gratis en compras mayores a $800. Paga a meses sin intereses."

Dime qué mejorar en cada uno.
```

**Lo que Claude te devuelve:**

**Anuncio Meta:**
- El copy es genérico. "Ropa que se mueve contigo" no diferencia de la competencia
- Sugerencia: Usar beneficio específico → "Tela anti-sudor con 4 direcciones de stretch. La usan +5,000 corredoras en México"
- La imagen debería mostrar el producto más de cerca, no solo estilo de vida
- Falta urgencia. Agregar: "Solo esta semana" o "Últimas piezas"

**Anuncio Google:**
- Falta usar los 15 títulos disponibles en RSA (solo tiene 3)
- El título 1 es demasiado genérico, no tiene keyword principal
- Sugerencia: "Leggins para Correr Mujer | FitWear" (más específico)
- Agregar extensiones de precio y extensiones de promoción

---

### FASE 5: Planificar campaña de temporada

Finalmente, planeas una campaña especial para el Buen Fin:

```
/ads plan ecommerce

Negocio: FitWear - ecommerce de ropa deportiva en México
Evento: Buen Fin 2026 (20-23 de noviembre)
Presupuesto especial para el evento: $3,000 USD adicionales
Objetivo: maximizar ventas durante los 4 días + semana previa de calentamiento
Descuento planeado: 30% en toda la tienda + envío gratis sin mínimo
Plataformas disponibles: Google Ads, Meta Ads, TikTok

Crea el plan completo con: fases, estructura de campañas, audiencias,
presupuesto por plataforma y día, creativos sugeridos y KPIs objetivo.
```

**Lo que Claude te devuelve:**

Un plan dividido en 3 fases:

```
┌─────────────────────────────────────────────────────────────────┐
│              PLAN BUEN FIN 2026 - FITWEAR                       │
└─────────────────────────────────────────────────────────────────┘

  FASE 1: Calentamiento       FASE 2: Buen Fin        FASE 3: Extensión
  13-19 nov ($600)             20-23 nov ($2,000)       24-26 nov ($400)
         │                           │                        │
         v                           v                        v
  ┌──────────────┐           ┌──────────────┐          ┌──────────────┐
  │ - Awareness  │           │ - Push fuerte │          │ - Retargeting│
  │ - "Se viene" │           │ - Descuentos  │          │ - "Últimas   │
  │ - Listas de  │           │   activos     │          │   horas"     │
  │   remarketing│           │ - Urgencia    │          │ - Carritos   │
  │ - Lookalikes │           │ - Stock       │          │   abandonados│
  │   calientes  │           │   limitado    │          │              │
  └──────────────┘           └──────────────┘          └──────────────┘

  Distribución por plataforma:
  ┌─────────────┬──────────┬───────────┬───────────┐
  │ Plataforma  │ Calent.  │ Buen Fin  │ Extensión │
  ├─────────────┼──────────┼───────────┼───────────┤
  │ Google Ads  │   $200   │   $800    │   $150    │
  │ Meta Ads    │   $300   │   $900    │   $200    │
  │ TikTok      │   $100   │   $300    │    $50    │
  └─────────────┴──────────┴───────────┴───────────┘
```

Con detalle de:
- Estructura de campañas y ad sets por plataforma
- Audiencias específicas para cada fase
- Textos y conceptos creativos sugeridos para cada fase
- KPIs objetivo: ROAS 3.5x mínimo, CPA máximo $18 USD
- Reglas automáticas: pausar campañas si CPA supera $25

---

### Resumen del caso: qué lograste con Claude Ads

```
┌─────────────────────────────────────────────────────────────────┐
│                RESULTADO FINAL - FITWEAR                        │
└─────────────────────────────────────────────────────────────────┘

  ANTES                              DESPUÉS
  ─────                              ───────
  Health Score: 62/100 (C)           Health Score estimado: 82/100 (B)

  $1,200 en campaña perdiendo  ──>   $500 optimizado + keywords negativas
  dinero (ROAS 0.7x)

  $500 en retargeting          ──>   $900 en tu campaña más rentable
  (sub-invertido)                    (ROAS 6.3x)

  0 presencia en TikTok       ──>   $500 en campaña de prueba
                                     (oportunidad de competencia)

  Creativos genéricos          ──>   Copy específico con social proof
                                     y urgencia

  Sin plan para Buen Fin       ──>   Plan de 3 fases con $3,000
                                     de presupuesto distribuido

  Tiempo invertido: ~30 minutos exportando datos
  de tus plataformas y conversando con Claude
  vs. semanas de trabajo con una agencia tradicional
```

---

## 11. Preguntas frecuentes

### ¿Es gratis?

**Claude Ads (el skill)** es gratuito. **Claude Code** requiere una suscripción de Anthropic (Claude Pro, Team, o créditos de API).

### ¿Necesito saber programar?

**No.** Solo necesitas saber copiar y pegar comandos, y escribir en español lo que quieres que Claude haga. El tutorial de instalación cubre todo lo técnico.

### ¿En qué idioma le hablo a Claude?

En **español** o inglés, los dos funcionan. Claude entiende ambos idiomas perfectamente.

### ¿Necesito conectar mis cuentas de publicidad?

**No.** Claude Ads no se conecta directamente a las APIs de Google, Meta, TikTok, etc. Funciona como un consultor experto: tú le das los datos (exportando CSVs, copiando métricas o compartiendo capturas de pantalla) y él los analiza con 190+ checks especializados. No necesitas credenciales de API ni dar acceso a tus cuentas.

### ¿Puedo usarlo si solo tengo una plataforma?

**Sí.** No necesitas tener las 6 plataformas. Puedes usar solo los comandos de la plataforma que uses (ejemplo: solo `/ads meta` si solo usas Meta Ads).

### ¿Qué pasa si no tengo campañas activas?

Puedes usar `/ads plan` para planificar campañas nuevas desde cero. Claude te genera un plan completo con plataformas recomendadas, estructura, audiencias y presupuesto según tu tipo de negocio. También puedes usar `/ads competitor` para investigar qué hace tu competencia antes de lanzar.

### ¿Cómo actualizo Claude Ads?

Vuelve a ejecutar el comando de instalación. El script detecta la instalación existente y la actualiza:

```powershell
irm https://raw.githubusercontent.com/AgriciDaniel/claude-ads/main/install.ps1 | iex
```

### ¿Dónde encuentro más skills para Claude Code?

Visita el repositorio del creador o busca "Claude Code skills" en GitHub. Claude Ads es parte de una colección más amplia de habilidades para agencias digitales.

---

## Resumen rápido de instalación

Si ya entiendes los conceptos y solo quieres los comandos rápidos:

```
1. Instalar VSCode:        https://code.visualstudio.com (descargar e instalar)
2. Instalar Node.js:       https://nodejs.org (versión LTS)
3. Instalar Claude Code:   npm install -g @anthropic-ai/claude-code
4. Iniciar sesión:         claude (seguir instrucciones en pantalla)
5. Instalar Claude Ads:    irm https://raw.githubusercontent.com/AgriciDaniel/claude-ads/main/install.ps1 | iex
6. Verificar:              /ads audit
```

---

*Tutorial basado en la documentación oficial de Claude Ads disponible en tododeia.com/community/claude-ads*
*Guía paso a paso para Windows con VSCode.*
