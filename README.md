# Valora Realty — Landing Page

Informe de proyecto para el desarrollo de la landing page de **Valora Realty**. Este documento reúne toda la información de negocio disponible, el branding propuesto y los lineamientos de diseño/funcionalidad que debe cumplir el sitio final.

> **Nota de flujo de trabajo:** este proyecto se construye sobre una plantilla base en HTML. El desarrollador ya cuenta con un prompt inicial para adaptar dicha plantilla. A partir de ahí, **el desarrollador puede (y debe) seguir iterando directamente con Claude**, dándole instrucciones sucesivas hasta lograr el resultado descrito en este documento. No es necesario acertar todo a la primera iteración — se espera un proceso iterativo de ajustes con Claude hasta cumplir cada punto de este brief.

---

## 1. Información del negocio

| Campo | Dato |
|---|---|
| Nombre del negocio | **Valora Realty** |
| Rubro | Bienes raíces / Real estate |
| Tagline | "Todo en Bienes Raíces" |
| Slogan / propuesta de valor | "Tu Patrimonio en Buenas Manos" |
| Contacto / representante | Luis García Sosa |
| Teléfono y WhatsApp | +52 818 994 1554 |
| Ubicación (por lada telefónica) | Área metropolitana de Monterrey, Nuevo León, México |

### ⚠️ Importante — información limitada del cliente

El cliente **no proporcionó** carpeta de imágenes, logo, fotografías de propiedades, ni contenido adicional (textos "quiénes somos", testimonios, listado de servicios detallado, etc.). Solo se cuenta con los datos de la tabla anterior.

Instrucciones para manejar esto:

- **No esperar más información antes de avanzar.** Se debe construir la landing completa priorizando el **diseño, la estructura y la experiencia visual**, que es lo que realmente se va a evaluar en esta primera entrega.
- **Imágenes:** usar fotografías de bancos de imágenes gratuitos y de uso libre (Unsplash, Pexels, Pixabay) buscando términos como *"luxury real estate"*, *"modern house exterior"*, *"real estate agent"*, *"property investment"*, *"skyline Monterrey"*, etc. Evitar tomar imágenes directo de resultados de Google Images por temas de derechos de autor; los bancos gratuitos mencionados son la alternativa segura y visualmente equivalente.
- **Textos/copy:** donde falte contenido real (descripciones de propiedades, testimonios, "nosotros", servicios específicos), usar **contenido placeholder realista y profesional** en español, coherente con una inmobiliaria premium. Debe quedar fácil de identificar y reemplazar rápido cuando el cliente entregue su información real.
- **Logo:** el cliente no envió el logo. Mientras tanto, crear un **logotipo temporal tipo monograma** (por ejemplo, iniciales "VR" o un ícono minimalista de casa/edificio) usando la paleta de marca definida abajo. Debe usarse consistentemente en el header, favicon y pantalla de carga.
  - **Cuando el cliente entregue su logo real:** casi siempre llega con fondo blanco/de color. Es obligatorio quitarle el fondo (dejarlo en PNG transparente) antes de integrarlo al sitio — usar remove.bg, Photoshop o una herramienta equivalente. Un logo con fondo cuadrado se ve poco profesional sobre un header o loader con fondo oscuro/degradado.
- **El objetivo de esta primera versión es que el cliente vea el diseño y la dirección de marca**, y a partir de su feedback se ajustan textos, imágenes reales y contenido específico. No bloquear el desarrollo por falta de información — avanzar con supuestos razonables de la industria inmobiliaria.

---

## 2. Branding y paleta de colores (propuesta)

No se recibió manual de marca, por lo que se propone una paleta acorde a un negocio inmobiliario premium/corporativo, que transmita **confianza, solidez patrimonial y elegancia**:

| Uso | Color | Hex |
|---|---|---|
| Primario (marca / fondos oscuros / header) | Azul marino profundo | `#0B1F3A` |
| Primario alterno (variación / degradados) | Azul noche | `#132A4C` |
| Acento (CTAs, detalles, líneas, hover) | Dorado / champán | `#C9A227` |
| Acento alterno (degradado con el dorado) | Dorado claro | `#E4C874` |
| Neutro base | Blanco | `#FFFFFF` |
| Neutro claro (fondos de sección) | Gris muy claro | `#F5F6F8` |
| Neutro oscuro (texto principal) | Carbón | `#161616` |
| Neutro medio (texto secundario) | Gris | `#5C6470` |

**Lógica de la paleta:** azul marino + dorado es una combinación clásica en el sector de bienes raíces de lujo y banca privada — comunica patrimonio, estabilidad y exclusividad sin caer en colores "genéricos" de agencia inmobiliaria común (evitar el típico azul cielo + naranja).

### Tipografía sugerida

- **Encabezados / Hero:** una sans-serif moderna y elegante con buen peso en bold — ej. *Poppins*, *Sora* o *Manrope*.
- **Texto de cuerpo:** sans-serif limpia y legible — ej. *Inter* o *Manrope* (400/500).
- Evitar fuentes decorativas o script; el estilo debe sentirse **corporativo, no artesanal**.

---

## 3. Dirección de diseño

El sitio debe transmitir un estilo **premium, enterprise y corporativo de marca**, con una sensación **high-tech y elegante**, combinado con un enfoque **minimalista**: espacios en blanco generosos, jerarquía tipográfica clara, pocos elementos por pantalla pero muy cuidados. Referencia de nivel: sitios de fondos de inversión, despachos inmobiliarios de lujo o proptech internacional — no el estilo "agencia inmobiliaria local" tradicional.

Lineamientos concretos:

- Layout limpio, con mucho espacio negativo, grid alineado y consistente.
- Uso de degradados sutiles en azul marino y detalles en dorado como acento (no saturar de color).
- Fotografía a pantalla completa / secciones full-bleed para transmitir escala y solidez.
- Botones y CTAs con bordes definidos, buen contraste, microinteracciones en hover (no efectos genéricos de Bootstrap).
- Todo el sitio debe sentirse **coherente y de una sola marca** — mismos radios de borde, mismas sombras, mismo sistema de espaciado en todas las secciones.

---

## 4. Efectos visuales y animaciones (requeridos)

Estos elementos son **obligatorios** en la entrega, no opcionales:

1. **Pantalla de carga (loading screen)**
   - Debe mostrarse antes de que cargue el sitio.
   - Incluye el logo del negocio centrado junto con un spinner/loader animado.
   - Transición suave (fade out) hacia el contenido una vez que termina de cargar.

2. **Animaciones al hacer scroll**
   - Los elementos de cada sección (títulos, tarjetas, imágenes, bloques de texto) deben aparecer con animación al entrar en el viewport (fade-in + slide-up es un buen default).
   - Puede usarse una librería como AOS (Animate On Scroll), GSAP con ScrollTrigger, o Intersection Observer + CSS transitions.
   - Las animaciones deben ser sutiles y rápidas (no exagerar duración), consistentes con el tono "premium/high-tech".

3. **Efectos en el título de la sección Hero**
   - Efecto tipo **máquina de escribir** (typewriter) sobre el texto principal del hero (por ejemplo, animando el slogan "Tu Patrimonio en Buenas Manos" o alternando frases relacionadas al negocio).
   - Efecto de **letras que cambian de color** en el título (ej. gradiente animado en el texto, o transición de color por letra/palabra), usando los colores de la paleta (azul marino / dorado).
   - Estos efectos deben verse fluidos y no afectar la legibilidad ni el rendimiento de carga inicial.

4. **Botón flotante de WhatsApp**
   - Visible en todo momento (fixed), con el número +52 818 994 1554, para contacto directo — es el canal de conversión principal para este negocio.

---

## 5. Estructura sugerida de secciones

1. **Loading screen** (logo + spinner)
2. **Header/Nav** — logo, menú (Inicio, Nosotros, Servicios, Propiedades, Contacto), botón CTA ("Contáctanos" / WhatsApp)
3. **Hero** — slogan con efectos (typewriter + color), tagline "Todo en Bienes Raíces", CTA principal, imagen/fondo de alto impacto (arquitectura moderna/skyline)
4. **Sobre Valora Realty** — propuesta de valor, presentación de Luis García Sosa como referente del negocio (placeholder si no hay foto/bio real aún)
5. **Servicios** — ej. Compra, Venta, Renta, Asesoría patrimonial/inversión (contenido placeholder, ajustable después)
6. **Propiedades destacadas** — grid/carrusel con propiedades placeholder (imágenes de bancos gratuitos), tarjetas con precio, ubicación, características
7. **¿Por qué elegirnos?** — bloque de diferenciadores (confianza, experiencia, acompañamiento integral, etc.)
8. **Testimonios** — placeholder, estructura lista para reemplazar con testimonios reales
9. **Contacto** — teléfono, WhatsApp, formulario simple, mapa opcional de zona de cobertura
10. **Footer** — datos de contacto, redes sociales (placeholder si no se proporcionaron), aviso de derechos

---

## 6. Flujo de trabajo con Claude (para el desarrollador)

- Partir de la plantilla base HTML + el prompt inicial ya entregado.
- Iterar con Claude en pasos sucesivos: primero estructura y paleta, luego contenido por sección, luego animaciones/efectos, luego responsive y detalles finales.
- No es necesario lograr el resultado en una sola pasada — se puede (y se espera) dar múltiples rondas de instrucciones a Claude hasta que el diseño cumpla con lo descrito en este README.
- Antes de considerar la primera versión lista para mostrar al cliente, verificar que estén implementados: loading screen, animaciones de scroll, efectos del hero, botón de WhatsApp, y que el sitio sea responsive (mobile-first, ya que gran parte del tráfico de WhatsApp vendrá de celular).

### Brief resumido (copiar/pegar como instrucción a Claude)

> Construye/ajusta la landing page de **Valora Realty**, una inmobiliaria ("Todo en Bienes Raíces", slogan "Tu Patrimonio en Buenas Manos", contacto Luis García Sosa, tel/WhatsApp +52 818 994 1554). Estilo: premium, corporativo/enterprise, high-tech, elegante y minimalista. Paleta: azul marino `#0B1F3A` como primario, dorado `#C9A227` como acento, blancos y grises neutros. Tipografía sans-serif moderna (Poppins/Sora/Manrope). Incluye: pantalla de carga con logo + spinner, animaciones on-scroll en todas las secciones, efecto typewriter y de color animado en el título del hero, botón flotante de WhatsApp. Usa imágenes de bancos gratuitos (Unsplash/Pexels) para propiedades y contenido placeholder profesional donde falte información real — el cliente ajustará contenido después de ver el diseño. Si se recibe un logo con fondo, quítale el fondo antes de usarlo.

---

## 7. Checklist de entrega

- [ ] Pantalla de carga con logo + spinner implementada
- [ ] Animaciones de scroll en todas las secciones
- [ ] Efecto typewriter en el hero
- [ ] Efecto de color animado en el título del hero
- [ ] Botón flotante de WhatsApp funcional (+52 818 994 1554)
- [ ] Paleta de colores aplicada de forma consistente
- [ ] Logo (temporal o real) sin fondo, integrado en header/loader/favicon
- [ ] Sitio responsive (mobile, tablet, desktop)
- [ ] Contenido placeholder claramente reemplazable
- [ ] Revisión de velocidad de carga (optimización de imágenes)
