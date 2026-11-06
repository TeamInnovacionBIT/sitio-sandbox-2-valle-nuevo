# Valle Nuevo Salones y Eventos — sitio de prueba (sandbox)

> **Estado: dado de baja el 6/11/2026, en su versión 1.0.2.**
> La URL https://plum-moose-404696.hostingersite.com/ está fuera de servicio desde esa fecha. Este repositorio se conserva como registro.

Sitio estático de prueba para observar cómo los rastreadores y los agentes de inteligencia artificial descubren, leen, interpretan y repiten la información publicada en un sitio web. Todo el contenido es ficticio: no existen la empresa Valle Nuevo Salones y Eventos S.R.L., la localidad de Villa San Ernesto, los salones, las direcciones, los teléfonos ni los puestos de trabajo publicados.

## Ficha

| Campo | Valor |
| --- | --- |
| Versión final | 1.0.2 |
| Fecha de baja | 6/11/2026 |
| Alojamiento | Hostinger (dominio gratuito, función Git de hPanel) |
| URL | https://plum-moose-404696.hostingersite.com/ (fuera de servicio) |
| Tipo de sitio | Estático: HTML, CSS y Markdown, sin JavaScript ni paso de compilación |

## Motivo de la baja

El dominio gratuito de Hostinger impidió cumplir con el requisito de que ningún obstáculo técnico distorsione la medición, por dos razones:

1. **Bloqueo de Googlebot.** En los dominios gratuitos, Hostinger prioriza un robots.txt por defecto que niega el acceso al rastreador de Google por encima del `robots.txt` del sitio, que autorizaba de forma explícita a un grupo amplio de rastreadores.
2. **Desconfianza hacia la URL.** Cuando se le pide a un asistente de IA que ingrese a la dirección, su respuesta queda influida por la desconfianza que le genera un subdominio gratuito y desconocido. Además, buscadores como Copilot no ingresaron directamente al sitio.

## Contenido del repositorio

| Archivo | Función |
| --- | --- |
| `index`, `quienes-somos`, `historia`, `salones`, `quincho`, `trabaja-con-nosotros`, `contacto` | Las 7 páginas del sitio, cada una en dos archivos: `.html` y `.md`, con el mismo texto. Solo difieren la sintaxis y el código de referencia visible del pie. |
| `estilos.css` | Hoja de estilos. |
| `llms.txt` | Índice de las versiones Markdown, según la especificación de llmstxt.org. |
| `robots.txt` | Permite el acceso a todos los rastreadores y autoriza por nombre a GPTBot, OAI-SearchBot, ChatGPT-User, ClaudeBot, Claude-SearchBot, anthropic-ai, PerplexityBot, Perplexity-User, Google-Extended, Googlebot y Bingbot. |
| `sitemap.xml` | Las 7 páginas HTML, sin las versiones Markdown. |
| `BingSiteAuth.xml` | Archivo de verificación de Bing Webmaster Tools. Se publicó en la raíz del sitio para registrar la propiedad y habilitar el rastreo e indexación por Bing (versión 1.0.2). |
| `.htaccess` | Sirve los `.md` como `text/markdown; charset=utf-8`, desactiva el listado de directorios, bloquea los archivos ocultos (incluido `.git`) y redirige `/pagina` a `/pagina.html`. |

## Historial de versiones

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 1.0.0 | 6/10/2026 | Primer despliegue: 7 páginas con par HTML/Markdown, `llms.txt`, `robots.txt`, `sitemap.xml` y `.htaccess`. |
| 1.0.1 | 6/10/2026 | Dominio de Hostinger en las URL canónicas, `sitemap.xml`, `robots.txt` y `llms.txt`. |
| 1.0.2 | 7/10/2026 | Archivo `BingSiteAuth.xml` para Bing Webmaster Tools. |

## Uso local

Los enlaces entre páginas son relativos, así que el sitio se navega abriendo `index.html` en el navegador o con un servidor local desde esta carpeta:

```bash
py -m http.server 8000
```

## Mantenimiento

No hay generador ni script de verificación. Cada cambio de contenido se aplica a mano en el `.html` y en el `.md` de la misma página, en el mismo commit. Si se reutiliza el sitio en otro dominio, hay que reemplazar `https://plum-moose-404696.hostingersite.com/` en las URL canónicas, `sitemap.xml`, `robots.txt` y `llms.txt`, y generar un `BingSiteAuth.xml` nuevo para ese dominio.
