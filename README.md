# Web Marketing Studio

`web-marketing-studio` es un plugin para ChatGPT Work que reúne 14 Skills de estrategia de conversión, dirección de arte, originalidad, calidad visual y animación web accesible.

**Versión actual:** `0.2.0`

## Qué incluye

### Conversión y planificación

- `local-service-leadgen`: páginas para negocios locales orientadas a llamadas, cotizaciones y visitas.
- `design-first-ui-prompting-web`: convierte una idea en una especificación visual e implementable.
- `video-to-superprompt-web`: analiza una referencia en video y produce un prompt de construcción verificable.

### Referencias, originalidad y dirección de arte

- `reference-brand-worlds-web`: transforma referencias múltiples en un sistema visual original.
- `reference-originality-web`: audita similitudes y riesgos de copia.
- `build-awwwards-quality-sites`: crea sitios premium, coherentes y de alto nivel visual sin afirmar premios inexistentes.
- `no-ai-design-slop`: evita decisiones genéricas o incoherentes durante la creación y revisión.
- `audit-ai-design-slop`: realiza una auditoría de diseño basada en evidencia, sin editar el proyecto.

### Movimiento e interacción

- `web-animation-performance`: diagnostica y corrige costos, fugas y trabajo fuera de pantalla.
- `scroll-scrubbed-visual-sequence`: crea secuencias visuales reversibles controladas por scroll.
- `scroll-progress-timeline`: convierte procesos ordenados en líneas de progreso responsivas.
- `scroll-scrubbed-word-reveal`: revela texto por palabras sin romper semántica ni accesibilidad.
- `reveal-hover-effect`: crea revelados de imagen con máscara radial y alternativas para touch y teclado.

### Reutilización

- `web-technique-to-skill`: convierte una técnica web ya probada en una nueva Skill reutilizable.

## Estructura del repositorio

```text
.agents/plugins/marketplace.json
plugins/web-marketing-studio/
  .codex-plugin/plugin.json
  plugin.json
  skills/
  LICENSE
  NOTICE.md
README.md
INSTALL.md
```

La carpeta oculta `.agents` es obligatoria. No la elimines al subir el repositorio.

## Publicación en ChatGPT web

1. Descomprime el ZIP del marketplace.
2. Sube **el contenido extraído**, no el archivo ZIP, a la raíz del mismo repositorio de GitHub usado para la versión anterior.
3. Reemplaza los archivos anteriores y conserva `.agents/` y `plugins/`.
4. El administrador del workspace abre **Admin → Plugins → Add → Import marketplace**.
5. Introduce la URL del repositorio. Deja `Path` vacío si esta estructura está en la raíz.
6. Importa o sincroniza el marketplace y habilita `web-marketing-studio` para los usuarios correspondientes.
7. Instala o actualiza el plugin desde la pestaña del workspace.
8. Abre un chat o sesión de Work nueva para cargar las 14 Skills.

Si no aparece **Admin**, la cuenta no tiene el rol necesario para importar el marketplace. Envía el repositorio al administrador del workspace.

## Actualizaciones

Publica las nuevas versiones en el mismo repositorio. No crees un repositorio por Skill y no instales las Skills individualmente. El número de versión está en `plugins/web-marketing-studio/.codex-plugin/plugin.json`.

El archivo `web-marketing-studio-v0.2.0.zip` es el paquete portable del plugin. Para importar el marketplace del workspace usa `web-marketing-studio-marketplace-v0.2.0.zip`.

## Pruebas rápidas

Después de instalar, abre una sesión nueva y prueba:

- `Usa $local-service-leadgen para planificar una página de servicio local orientada a cotizaciones.`
- `Usa $build-awwwards-quality-sites para definir y construir una dirección visual premium para este sitio.`
- `Usa $audit-ai-design-slop para auditar esta interfaz sin modificarla.`
- `Usa $scroll-scrubbed-visual-sequence para implementar esta secuencia visual reversible.`

## Criterio y fuentes

Cada Skill contiene `references/criteria-and-sources.md`, donde se separan:

- estándares y comportamiento documentado;
- heurísticas de diseño o ingeniería;
- procedencia de la adaptación.

Las fuentes técnicas prioritarias son OpenAI, W3C/WCAG, MDN, web.dev y la documentación oficial de GSAP. Las decisiones estéticas se presentan como heurísticas, no como normas universales.

## Documentación oficial

- [Estructura y empaquetado de plugins](https://developers.openai.com/plugins/build/plugins)
- [Creación de Skills](https://learn.chatgpt.com/docs/build-skills)
- [Uso e instalación de plugins](https://learn.chatgpt.com/docs/plugins?surface=app)
- [Administración del marketplace del workspace](https://learn.chatgpt.com/docs/enterprise/plugin-management)

## Licencia y atribución

Distribuido bajo licencia MIT. Varias Skills son adaptaciones sustanciales de [MengTo/Skills](https://github.com/MengTo/Skills). Consulta `plugins/web-marketing-studio/NOTICE.md` para el detalle de procedencia y cambios.

