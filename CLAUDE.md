# Centro El Alba — Contexto del Proyecto

## Qué es esto
Sitio web completo para **Centro El Alba**, centro de salud multidisciplinario en Maipú, Chile.
Archivo único: `index.html` — HTML/CSS/JS puro, sin frameworks.

## Información real del centro
- **Dirección:** Hernán Olguín 136, Maipú, Chile
- **Teléfono/WhatsApp:** +56 9 7234 2849
- **Link directo WhatsApp:** https://wa.me/message/HCYWC2VJFMPQI1
- **Email:** contacto.centroelalba@gmail.com
- **Horario:** Lunes a viernes 9:00–18:30 / Sábados 9:00–14:00
- **Instagram:** https://www.instagram.com/centroelalba/
- **Facebook:** https://www.facebook.com/Centrodedesarrollointegralelalba
- **TikTok:** https://www.tiktok.com/@centroelalba1
- **Google Maps review link:** https://share.google/BYiN7My2xE7Db0pCG

## Especialidades
- Psicología
- Fonoaudiología
- Terapia Ocupacional
- Nutrición

## Archivos de recursos
```
Recursos/
  LOGO CENTRO/
    foto sin fondo.png        ← Logo PNG con fondo transparente (usar siempre este)
  Fotos espacio fisico/         ← Galería completa de #galeria (7 fotos)
    Sala 1.jpeg
    Sala 2.jpeg
    Sala 2.1.jpeg
    Sala3.jpeg
    Sala4.jpeg
    Sala Psicologia.jpeg
    Sala Psicologia2.jpeg
  Trabajadores/                ← Fotos de los profesionales (usadas en #profesionales)
    Marta Ibarra Psicologa, Dueña.jpeg
    Alejandro Gonzales.jpeg
    Yulissa Díaz.jpeg
    Camilo Reyes.jpeg
    Jacinta Nutrcionista.jpeg
    Maria Victoria.jpeg
    Pamela Aguilera.jpeg
```
Siempre URL-encodear espacios: `%20` (ej: `Recursos/LOGO%20CENTRO/foto%20sin%20fondo.png`)

## Paleta de colores (CSS custom properties)
```css
--alba-dawn:  #F4A261   /* naranja claro */
--alba-warm:  #E76F51   /* naranja oscuro / CTA principal */
--alba-light: #FFF8F0   /* fondo principal */
--alba-sand:  #F2E9D8   /* fondo secciones alternas */
--alba-teal:  #457B9D   /* azul acento */
--alba-dark:  #264653   /* texto oscuro / headings */
--alba-text:  #3D3D3D   /* texto cuerpo */
```

## Estructura de secciones (en orden)
1. `nav` — navegación fija con logo y hamburger
2. `#hero` — split layout (texto izq / imagen der), logo en hero, badge flotante familias
3. `#quienes` — Quiénes Somos
4. `#especialidades` — accordion de especialidades
5. `#profesionales` — grid filtrable por especialidad y días
6. `#evaluaciones` — tests y evaluaciones por especialidad
7. `#aranceles` — FONASA, ISAPREs, formas de pago, valores por especialidad
8. `#galeria` — fotos del espacio
9. `#politicas` — políticas de atención (6 tarjetas)
10. `#agenda` — sección para reservar hora (apunta a Reservo)
11. `#redes` — redes sociales
12. `#contacto` — formulario de contacto
13. `#ubicacion` — mapa Google Maps embed
14. `#reviews` — reseñas (link a Google)
15. `footer` — info de cierre

## Sistema de reservas
- Plataforma: **Reservo**
- Placeholder actual en el código: `[RESERVO_LINK]`
- Cuando tengas el link, reemplazar TODOS los `[RESERVO_LINK]` del HTML

## Tarjeta de profesional (estructura HTML)
```html
<div class="pro-card" data-especialidad="psicologia" data-dias="lun mar mie jue vie">
  <div class="pro-card-img">👤<!-- RELLENAR: <img src="..."> --></div>
  <div class="pro-card-body">
    <p class="pro-card-role">Psicología</p>
    <h3 class="pro-card-name">[RELLENAR: Nombre completo]</h3>
    <p class="pro-card-desc">[RELLENAR: Descripción breve]</p>
    <p class="pro-avail-label">Disponibilidad</p>
    <div class="availability-days">
      <span class="day-badge">Lun</span>
      <!-- ... -->
    </div>
    <a href="[RESERVO_LINK]" class="btn btn-primary btn-sm">Reservar Hora</a>
  </div>
</div>
```
Valores válidos para `data-especialidad`: `psicologia` | `fonoaudiologia` | `terapia-ocupacional` | `nutricion`
Valores válidos para `data-dias`: combinación de `lun mar mie jue vie sab`

## Pendientes (de mayor a menor urgencia)

### 🔗 Reservo
- [ ] Reemplazar todos los `[RESERVO_LINK]` con el link real de Reservo

### 👥 Profesionales (7 en total)
Equipo confirmado en `index.html` (sección `#profesionales`):
- **Psicología (2):** Marta Ibarra, Alejandro González (Director del centro)
- **Terapia Ocupacional (2):** Yulissa Díaz, Camilo Reyes
- **Nutrición (1):** Jacinta Legarreta
- **Fonoaudiología (2):** María Victoria Motta, Pamela Aguilera

Pendiente por profesional:
- [ ] Días de atención de los 7 (actualmente todos muestran "Consultar disponibilidad", `data-dias=""`)
- Fotos: ya cargadas para los 7, desde `Recursos/Trabajadores/` (URL-encodeadas por espacios/acentos/coma en el `src`)

### 🏥 Convenios
- **ISAPREs:** el centro trabaja con TODAS las ISAPREs (no hay lista acotada) — sección `#aranceles` muestra badges de las principales (Banmédica, Colmena, Consalud, Cruz Blanca, Vida Tres, Nueva Masvida, Esencial) + "Y todas las demás"
- **Seguros complementarios:** se mencionan de forma genérica (sin listar aseguradoras específicas), decisión del usuario
- **FONASA:** Libre Elección, **tarifas preferenciales y sin venta de bonos** (confirmado por el usuario). No se muestran montos de reembolso por tramo — se deriva a que el paciente consulte con su tramo

### 💰 Precios
- Se decidió **no mostrar precios en el sitio**: ni valores de sesión por especialidad (bloque eliminado de `#aranceles`) ni valores de evaluaciones (`eval-price` eliminado de las 6 tarjetas de `#evaluaciones`) — se deriva a WhatsApp para consultar precios

### 🖼 Imágenes
- [ ] Foto para el hero (equipo o fachada del centro) — hay `Recursos/Portada del centro.jpeg` sin usar aún, evaluar si va ahí
- Fotos de profesionales: completas (ver sección Profesionales arriba)
- Galería del espacio: completa, 7 fotos reales en `#galeria`
- [ ] Badge de hero: `+[RELLENAR]` familias → poner número real

### 📋 Políticas de atención
- Tolerancia por llegada tarde: **15 minutos** (ya en el sitio)
- Anticipación mínima para cancelar: **12 horas** (ya en el sitio). Decisión: no se cobra por inasistencia/cancelación tardía — solo se pide avisar y reagendar por Reservo o WhatsApp
- Formas de pago (ya en el sitio, sección `#aranceles`): efectivo, transferencia bancaria, débito y crédito, más pago online vía Reservo al agendar

## Decisiones de diseño tomadas
- Inspiración estructura: centrointegralvibra.cl/profesionales.html
- Especialidades: acordeón (no tabs) para ahorrar espacio
- Profesionales: grid filtrable con data-attributes + JS vanilla
- Hero: split grid 1fr/1fr, colapsa a 1 col en mobile (imagen se oculta)
- Formulario de contacto: JS confirmation message (sin backend)
- WhatsApp: usar link directo `wa.me/message/HCYWC2VJFMPQI1`, no número directo
