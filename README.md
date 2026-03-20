# Claude Ads

Claude Ads es un **skill para Claude Code** que lo convierte en un especialista de publicidad digital. Permite auditar, planificar y optimizar campanas publicitarias en 6 plataformas con mas de 190 checks automaticos.

## Plataformas soportadas

| Plataforma | Cobertura |
|---|---|
| **Google Ads** | Search, Performance Max, Display, YouTube, Demand Gen (74 checks) |
| **Meta Ads** | Facebook, Instagram, Advantage+ Shopping |
| **YouTube Ads** | Skippable, Shorts, Demand Gen |
| **TikTok Ads** | Smart+, TikTok Shop |
| **LinkedIn Ads** | B2B, Lead Gen, Targeted Lead Accounts |
| **Microsoft Ads** | Bing, red de Microsoft, Copilot |

## Que puede hacer

- **Auditar** campanas existentes con un Ads Health Score (0-100)
- **Planificar** campanas nuevas con estrategias por industria
- **Optimizar** presupuestos y creativos
- **Analizar** anuncios de la competencia
- **Evaluar** landing pages y calidad creativa
- **Generar** imagenes para anuncios con IA

## Requisitos

- [Visual Studio Code](https://code.visualstudio.com)
- [Node.js](https://nodejs.org) (version LTS)
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) con suscripcion activa de Anthropic

## Instalacion rapida

```bash
# 1. Instalar Claude Code
npm install -g @anthropic-ai/claude-code

# 2. Iniciar sesion
claude

# 3. Instalar el skill Claude Ads (PowerShell)
irm https://raw.githubusercontent.com/AgriciDaniel/claude-ads/main/install.ps1 | iex
```

## Comandos disponibles

### Auditoria

| Comando | Descripcion |
|---|---|
| `/ads audit` | Auditoria completa multi-plataforma (190+ checks) |
| `/ads google` | Analisis profundo de Google Ads |
| `/ads meta` | Analisis profundo de Meta Ads |
| `/ads youtube` | Analisis de campanas de YouTube |
| `/ads tiktok` | Analisis de campanas de TikTok |
| `/ads linkedin` | Analisis B2B de LinkedIn |
| `/ads microsoft` | Analisis de Microsoft/Bing Ads |

### Optimizacion

| Comando | Descripcion |
|---|---|
| `/ads creative` | Auditoria de calidad creativa |
| `/ads landing` | Evaluacion de landing pages |
| `/ads budget` | Revision de presupuesto y pujas |
| `/ads competitor` | Inteligencia de competidores |

### Planificacion

| Comando | Descripcion |
|---|---|
| `/ads plan <tipo>` | Plan estrategico por industria (saas, ecommerce, local, b2b, infoproductos, apps, realestate, salud, finanzas, agencias) |

## Como funciona

Claude Ads **no se conecta directamente** a las plataformas de publicidad. Funciona como un consultor experto: tu le proporcionas los datos (exportando CSVs, copiando metricas o compartiendo capturas de pantalla) y el los analiza con sus checks especializados.

```
Tu datos (CSV, metricas, capturas) --> Claude Ads (190+ checks) --> Reporte con recomendaciones
```

## Ejemplo de uso

```
/ads audit

Mis campanas de Google Ads del ultimo mes:
- Campana "Search - Marca": CPC $0.45, CTR 8.2%, ROAS 4.2x, Gasto $400
- Campana "PMax - Catalogo": CPC $0.85, CTR 3.2%, ROAS 3.1x, Gasto $1,400

Industria: ecommerce de ropa deportiva
Presupuesto mensual: $5,000
Pais: Mexico
```

## Tutorial completo

Consulta [tutorial-claude-ads-desde-cero.md](tutorial-claude-ads-desde-cero.md) para una guia paso a paso desde la instalacion hasta tu primera auditoria.

## Ads Health Score

| Grado | Puntaje | Significado |
|---|---|---|
| A | 90 - 100 | Excelente |
| B | 80 - 89 | Bien, con mejoras posibles |
| C | 60 - 79 | Regular, oportunidades importantes |
| D | 40 - 59 | Necesita atencion urgente |
| F | 0 - 39 | Critico |

---

*Basado en la documentacion de [Claude Ads](https://tododeia.com/community/claude-ads)*
