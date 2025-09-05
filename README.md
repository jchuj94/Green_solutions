<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <meta name="color-scheme" content="light dark" />
  <title>Green Solutions - Consultoría Agrícola y Ambiental</title>

  <!-- Mejora tipográfica: Inter + Roboto (no cambia textos ni estructura) -->
  <link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
</head>
<body>

<style>
/* =========================
   VARIABLES & BASE
   ========================= */
:root{
  --gs-bg:#ffffff;
  --gs-text:#27323a;
  --gs-muted:#586873;
  --gs-green-900:#0d2818;
  --gs-green-800:#12331f;
  --gs-green-700:#1b4332;
  --gs-green-600:#22543d;
  --gs-green-500:#2d5a3d;
  --gs-green-300:#9cc4ad;
  --gs-accent:#42b883;
  --gs-border: #e6efe9;
  --gs-card: #ffffff;
  --gs-radius: 16px;
  --gs-shadow: 0 10px 30px rgba(17, 29, 24, .09);
  --gs-shadow-soft: 0 6px 20px rgba(17, 29, 24, .07);
}

/* Soporte dark mode sin cambiar estructura */
@media (prefers-color-scheme: dark){
  :root{
    --gs-bg:#0f1714;
    --gs-text:#e5ece8;
    --gs-muted:#c9d6cf;
    --gs-green-900:#08140d;
    --gs-green-800:#0f2017;
    --gs-green-700:#153725;
    --gs-green-600:#1d4932;
    --gs-green-500:#2a5f41;
    --gs-green-300:#8fbea7;
    --gs-border:#1e2b24;
    --gs-card:#111b17;
  }
}

/* ===== BASE ===== */
* { margin:0; padding:0; box-sizing:border-box; }
html, body { height:100%; }
body {
  font-family:'Inter','Roboto',Arial,sans-serif;
  background:var(--gs-bg);
  color:var(--gs-text);
  line-height:1.7;
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smoothing:grayscale;
}
img { max-width:100%; display:block; }
a { color:inherit; }

/* Contenedor */
.gs-container { max-width:1200px; margin:0 auto; padding:0 20px; }

/* Enfoque accesible sin cambiar HTML */
:focus-visible{
  outline: 3px solid var(--gs-green-300);
  outline-offset: 2px;
  border-radius: 8px;
}

/* ===== HEADER con fondo-carrusel ===== */
.gs-header {
  position: relative;
  color: white;
  text-align: center;
  padding: 110px 20px 100px;
  margin: -20px -20px 0 -20px;
  overflow: hidden;
  isolation:isolate;
}
.gs-hero-bg { position:absolute; inset:0; z-index:-1; }
.gs-hero-bg img {
  position:absolute; inset:0; width:100%; height:100%;
  object-fit:cover; opacity:0; transition:opacity 900ms ease;
  filter: saturate(1.05) contrast(1.05) brightness(.95);
}
.gs-hero-bg img.is-active { opacity:1; }

/* Overlay verde translúcido mejorado (gradiente + sutil blur) */
.gs-header::before {
  content:'';
  position:absolute; inset:0; z-index:-1;
  background:
    linear-gradient(180deg, rgba(16,36,28,.55) 0%, rgba(16,36,28,.35) 45%, rgba(16,36,28,.55) 100%),
    radial-gradient(1200px 600px at 50% 0%, rgba(66,184,131,.25), transparent 60%);
  backdrop-filter: blur(2px);
}

/* Tipografía del hero */
.gs-header .gs-container { position:relative; }
.gs-header h1 {
  font-size:clamp(2.2rem, 5vw, 3.4rem);
  font-weight:300; margin-bottom:1.1rem;
  letter-spacing:3px; text-transform:uppercase;
  text-shadow: 0 2px 18px rgba(0,0,0,.25);
}
.gs-header p {
  font-size:1.1rem; margin-bottom:2.2rem; opacity:.98; font-weight:300;
  max-width:680px; margin-left:auto; margin-right:auto;
  text-shadow: 0 1px 12px rgba(0,0,0,.20);
}

/* Botón CTA con mejoras de accesibilidad */
.gs-cta-button {
  background:rgba(255,255,255,.06);
  color:white; padding:12px 28px; border:1.8px solid rgba(255,255,255,.85);
  font-size:.95rem; text-decoration:none; display:inline-block; transition:.3s ease;
  font-weight:500; letter-spacing:.8px; text-transform:uppercase;
  border-radius:999px; box-shadow: 0 8px 20px rgba(0,0,0,.15);
  backdrop-filter: blur(2px);
}
.gs-cta-button:hover { background:white; color:var(--gs-green-700); transform: translateY(-1px); }
.gs-cta-button:active{ transform: translateY(0); }

/* ===== SECCIONES ===== */
.gs-section { padding:88px 20px; margin:0 -20px; }
.gs-section-title {
  text-align:center; font-size:clamp(1.8rem, 3.8vw, 2.4rem); color:var(--gs-green-700); margin-bottom:3.4rem;
  font-weight:300; letter-spacing:2px; text-transform:uppercase; position:relative;
}
.gs-section-title::after {
  content:''; width:72px; height:2px; background:var(--gs-green-500);
  position:absolute; bottom:-18px; left:50%; transform:translateX(-50%);
  box-shadow:0 2px 0 rgba(0,0,0,.04);
}

/* ===== QUIÉNES SOMOS ===== */
.gs-about { background:linear-gradient(180deg, rgba(45,90,61,.04), rgba(45,90,61,0) 30%), var(--gs-bg); }
.gs-about-grid {
  display:grid; grid-template-columns:1fr 1fr; gap:4.5rem; align-items:start;
  margin-top:3rem; max-width:1000px; margin-left:auto; margin-right:auto;
}
.gs-about-text{
  background:var(--gs-card);
  border:1px solid var(--gs-border);
  padding:2rem 2.2rem;
  border-radius: var(--gs-radius);
  box-shadow: var(--gs-shadow-soft);
}
.gs-about-text h3 { color:var(--gs-green-700); font-size:1.35rem; margin-bottom:1rem; font-weight:500; letter-spacing:.5px; }
.gs-about-text p { font-size:1.02rem; line-height:1.85; color:var(--gs-muted); font-weight:300; }

/* ===== EQUIPO CONSULTOR ===== */
.gs-team-description { max-width:900px; margin:0 auto; text-align:center; }
.gs-team-description p {
  font-size:1.06rem; line-height:1.9; color:var(--gs-muted);
  margin-bottom:2rem; text-align:justify;
}
.gs-team-highlights { 
  display:grid; grid-template-columns:repeat(3,1fr); gap:2rem; margin-top:2.2rem; justify-items:center;
}
.gs-team-highlights .gs-highlight-item:nth-child(4) { grid-column: 2 / 3; }
.gs-highlight-item {
  background:var(--gs-card); padding:1.8rem; border:1px solid var(--gs-border);
  text-align:center; position:relative; transition:transform .25s ease, box-shadow .25s ease, border-color .25s ease;
  border-radius: calc(var(--gs-radius) - 6px);
  box-shadow: var(--gs-shadow-soft);
}
.gs-highlight-item:hover {
  box-shadow: var(--gs-shadow);
  transform:translateY(-3px);
  border-color: color-mix(in srgb, var(--gs-green-300) 35%, var(--gs-border));
}
.gs-highlight-item::before {
  content:''; position:absolute; top:0; left:0; width:4px; height:100%; background:var(--gs-green-500); border-radius:4px 0 0 4px;
}
.gs-highlight-item h4 { color:var(--gs-green-700); font-size:1.08rem; margin-bottom:.6rem; font-weight:700; letter-spacing:.3px; }
.gs-highlight-item p { color:var(--gs-muted); font-size:.95rem; line-height:1.55; }

/* ===== SERVICIOS (LISTADO HORIZONTAL POR TÍTULOS) ===== */
.gs-services-columns {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 2rem 2.2rem;
  max-width: 1100px;
  margin: 0 auto;
  align-items: start;
}
.gs-service-col{
  background:var(--gs-card);
  border:1px solid var(--gs-border);
  border-radius: var(--gs-radius);
  padding:1.4rem 1.6rem;
  box-shadow: var(--gs-shadow-soft);
}
.gs-service-col h3 {
  color:var(--gs-green-700);
  font-size:1.12rem;
  margin-bottom:.9rem;
  font-weight:800; /* negrita asegurada */
  letter-spacing:.4px;
  border-bottom: 2px solid var(--gs-border);
  padding-bottom:.6rem;
}
.gs-service-col ul { list-style: none; }
.gs-service-col li { margin-bottom:.9rem; }
.gs-service-col li strong {
  color:var(--gs-green-700); display:block; margin-bottom:.2rem;
  font-size:.97rem; font-weight:700;
}
.gs-service-col li p { color:var(--gs-muted); font-size:.92rem; font-weight:300; line-height:1.55; }

/* ===== INSUMOS ===== */
.gs-insumos { background:linear-gradient(180deg, rgba(45,90,61,.04), rgba(45,90,61,0) 30%), var(--gs-bg); }
.gs-services-grid {
  display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
  gap:2.2rem; margin-top:3rem; max-width:1000px; margin-left:auto; margin-right:auto;
}
.gs-service-card {
  background:var(--gs-card); padding:2.1rem; border:1px solid var(--gs-border); position:relative;
  border-radius: var(--gs-radius);
  box-shadow: var(--gs-shadow-soft);
  transition: transform .25s ease, box-shadow .25s ease, border-color .25s ease;
}
.gs-service-card:hover{
  transform: translateY(-3px);
  box-shadow: var(--gs-shadow);
  border-color: color-mix(in srgb, var(--gs-green-300) 35%, var(--gs-border));
}
.gs-service-card::before {
  content:''; position:absolute; top:0; left:0; width:4px; height:100%; background:var(--gs-green-500);
  border-radius: 4px 0 0 4px;
}
.gs-service-card h3 {
  color:var(--gs-green-700); font-size:1.15rem; margin-bottom:1.2rem; font-weight:800; letter-spacing:.5px;
}
.gs-service-list { list-style:none; }
.gs-service-list li { margin-bottom:1.1rem; padding:1rem 0; border-bottom:1px solid var(--gs-border); }
.gs-service-list li:last-child { border-bottom:none; }
.gs-service-list li strong { color:var(--gs-green-700); display:block; margin-bottom:.35rem; font-size:.96rem; font-weight:700; }
.gs-service-list li p { color:var(--gs-muted); font-size:.92rem; font-weight:300; }

/* ===== COBERTURA ===== */
.gs-coverage { background:var(--gs-green-700); color:white; text-align:center; }
.gs-coverage .gs-section-title { color:white; }
.gs-coverage .gs-section-title::after { background:white; }
.gs-coverage-content { max-width:700px; margin:0 auto; }
.gs-coverage h3 { font-size:1.35rem; margin-bottom:1.2rem; font-weight:300; letter-spacing:1px; }
.gs-coverage p { font-size:1rem; margin-bottom:1.2rem; line-height:1.75; font-weight:300; opacity:.94; }
.gs-coverage-features {
  display:grid; grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); gap:1.4rem; margin-top:2.2rem;
}
.gs-coverage-feature {
  background:rgba(255,255,255,.06);
  padding:1.4rem; border:1px solid rgba(255,255,255,.12);
  transition:.25s ease; border-radius: calc(var(--gs-radius) - 8px);
}
.gs-coverage-feature:hover { background:rgba(255,255,255,.12); }

/* ===== CONTACTO ===== */
.gs-contact { background:linear-gradient(180deg, rgba(45,90,61,.04), rgba(45,90,61,0) 30%), var(--gs-bg); }
.gs-contact-grid {
  display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:2rem; margin-top:2.4rem; max-width:900px; margin-left:auto; margin-right:auto;
}
.gs-contact-card {
  background:var(--gs-card); padding:2rem; text-align:center; border:1px solid var(--gs-border);
  transition:.25s ease; border-radius: var(--gs-radius); box-shadow: var(--gs-shadow-soft);
}
.gs-contact-card:hover { box-shadow:var(--gs-shadow); transform: translateY(-2px); }
.gs-contact-icon {
  width:54px; height:54px; background:var(--gs-green-500); margin:0 auto 1rem; display:flex; align-items:center; justify-content:center;
  color:white; font-size:1.1rem; font-weight:600; border-radius:14px;
  box-shadow: 0 6px 16px rgba(0,0,0,.12);
}
.gs-contact-card h3 { color:var(--gs-green-700); margin-bottom:.6rem; font-size:1.06rem; font-weight:800; letter-spacing:.5px; }
.gs-contact-card p { font-weight:400; color:var(--gs-muted); font-size:1rem; }
.gs-contact-card a { color:var(--gs-green-600); text-decoration:none; transition:color .25s ease; }
.gs-contact-card a:hover { color:#ffffff; background:var(--gs-green-600); padding:.2rem .4rem; border-radius:.5rem; }
.gs-contact-cta {
  text-align:center; margin-top:2.6rem; padding:2.2rem; background:var(--gs-card); border:1px solid var(--gs-border);
  border-radius: var(--gs-radius); box-shadow: var(--gs-shadow-soft);
}
.gs-contact-cta h3 { color:var(--gs-green-700); margin-bottom:1rem; font-weight:800; font-size:1.22rem; }
.gs-contact-cta p { margin-bottom:1.4rem; color:var(--gs-muted); font-weight:300; line-height:1.7; }

/* ===== FOOTER ===== */
.gs-footer {
  background:var(--gs-green-900); color:white; padding:60px 20px 40px; margin:0 -20px -20px -20px;
  border-top: 1px solid rgba(255,255,255,.06);
}
.gs-footer-content { max-width:1200px; margin:0 auto; }
.gs-footer-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:2.2rem; margin-bottom:2rem; }
.gs-footer-section h4 { color:white; margin-bottom:1rem; font-size:1.08rem; font-weight:800; letter-spacing:.5px; }
.gs-footer-section p { color:rgba(255,255,255,.78); line-height:1.65; margin-bottom:.55rem; font-size:.95rem; font-weight:300; }
.gs-footer-section a { color:rgba(255,255,255,.86); text-decoration:none; transition:color .25s ease, background .25s ease; border-radius:.5rem; padding:.05rem .2rem; }
.gs-footer-section a:hover { color:#111; background:#fff; }
.gs-footer-bottom { border-top:1px solid rgba(255,255,255,.12); padding-top:1.4rem; text-align:center; }
.gs-footer-bottom p { margin-bottom:.35rem; color:rgba(255,255,255,.68); font-size:.92rem; }
.gs-social-links { margin-top:1rem; }
.gs-social-links a {
  display:inline-block; margin:0 6px; padding:8px; background:rgba(255,255,255,.10);
  width:36px; height:36px; text-align:center; line-height:20px; transition:.25s ease; color:white; text-decoration:none; font-size:.92rem; border-radius: 12px;
  box-shadow: 0 6px 16px rgba(0,0,0,.15);
}
.gs-social-links a:hover { background:var(--gs-green-500); transform: translateY(-2px); }

/* ===== RESPONSIVE ===== */
@media (max-width: 1200px){
  .gs-services-columns { gap: 1.6rem; }
}
@media (max-width: 1024px){
  .gs-services-columns { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 820px){
  .gs-team-highlights { grid-template-columns:repeat(2,1fr); }
  .gs-team-highlights .gs-highlight-item:nth-child(4) { grid-column:auto; }
}
@media (max-width: 640px){
  .gs-services-columns { grid-template-columns: 1fr; }
  .gs-header h1 { font-size: 2.15rem; letter-spacing: 2px; }
  .gs-section-title { font-size: 1.7rem; letter-spacing: 1px; }
  .gs-about-grid { grid-template-columns: 1fr; gap: 2rem; }
  .gs-footer-grid { grid-template-columns: 1fr; text-align: center; }
  .gs-section { padding: 64px 20px; }
  .gs-header { padding: 90px 20px 84px; }
}
@media (prefers-reduced-motion: reduce){
  .gs-hero-bg img { transition: none !important; }
  .gs-highlight-item, .gs-service-card, .gs-contact-card, .gs-cta-button { transition: none !important; }
}
</style>

<!-- ===== HEADER (con fondo de carrusel) ===== -->
<header class="gs-header">
  <div class="gs-hero-bg" aria-hidden="true">
    <img data-drive-id="101-TMmVzQSdmJ-Z9mSQPHP3quFGCNwrp" alt="" loading="lazy" />
    <img data-drive-id="1amoLZ92OaAIwXVXmNzdFNS6vlHSYAuHa" alt="" loading="lazy" />
    <img data-drive-id="15n6w-kvWBSw9QuyZTRES3Bw8DRcoEh4H" alt="" loading="lazy" />
    <img data-drive-id="1eNfbN_X2m9mgvkMQX2HFeAdeDZV2B-af" alt="" loading="lazy" />
    <img data-drive-id="1wdBt99BNhPrsJmHnSOtfJGsXOTTGn6UX" alt="" loading="lazy" />
    <img data-drive-id="1r8NDZpRjRgoOa1GmfCZyVCAt7pctajvW" alt="" loading="lazy" />
    <img data-drive-id="12yTJ47sqK_pTGF93UDTY4IU8n4hcxwBJ" alt="" loading="lazy" />
    <img data-drive-id="1wFraSDd7I1o2hl8kw5wf95C0k47ERU2f" alt="" loading="lazy" />
  </div>
  <div class="gs-container">
    <h1>Green Solutions</h1>
    <p>Consultoría especializada en agricultura sostenible y gestión ambiental</p>
    <!-- Botón correo -->
    <a
      href="mailto:gr3ensolutions@gmail.com?subject=Consulta%20sobre%20servicios%20de%20Green%20Solutions&body=Hola%20Green%20Solutions%2C%0D%0A%0D%0AMe%20gustar%C3%ADa%20recibir%20informaci%C3%B3n%20sobre%3A%20[breve%20descripci%C3%B3n]%0D%0AUbicaci%C3%B3n%3A%20%0D%0ATel%C3%A9fono%3A%20%0D%0A%0D%0AGracias."
      class="gs-cta-button"
      title="Enviar correo a Green Solutions"
    >Contáctanos</a>
  </div>
</header>

<!-- ===== QUIÉNES SOMOS ===== -->
<section class="gs-section gs-about">
  <div class="gs-container">
    <h2 class="gs-section-title">Quiénes Somos</h2>
    <div class="gs-about-grid">
      <div class="gs-about-text">
        <h3>Nuestra Misión</h3>
        <p>En Green Solutions impulsamos la sostenibilidad y productividad del sector agrícola y ambiental a través de soluciones integrales en nutrición vegetal, manejo de suelos, gestión eficiente del agua, inocuidad alimentaria y tecnologías de precisión.</p>
        <p>Nuestra misión es acompañar a productores y empresas con asesoría técnica de alto nivel, promoviendo una agricultura responsable, rentable y adaptada a los desafíos actuales.</p>
      </div>
      <div class="gs-about-text">
        <h3>Nuestra Visión</h3>
        <p>Aspiramos a liderar la transformación sostenible de la agricultura en América Latina, reconocida por nuestra innovación, excelencia técnica y liderazgo en agricultura de precisión.</p>
        <p>Contribuimos a transformar los sistemas productivos hacia modelos más resilientes, eficientes y ambientalmente responsables.</p>
      </div>
    </div>
  </div>
</section>

<!-- ===== NUESTRO EQUIPO CONSULTOR ===== -->
<section class="gs-section">
  <div class="gs-container">
    <h2 class="gs-section-title">Nuestro Equipo Consultor</h2>
    <div class="gs-team-description">
      <p>Green Solutions es un equipo multidisciplinario integrado por profesionales con maestrías y especializaciones en áreas de vanguardia del sector agrícola y ambiental. Nuestras competencias técnicas están respaldadas por formación continua en las últimas tendencias y tecnologías del sector, desarrollando soluciones adaptadas a las necesidades reales del sector productivo actual.</p>

      <div class="gs-team-highlights">
        <div class="gs-highlight-item">
          <h4>Formación Especializada</h4>
          <p>Maestrías y especializaciones en áreas de vanguardia del sector agrícola</p>
        </div>
        <div class="gs-highlight-item">
          <h4>Equipo Multidisciplinario</h4>
          <p>Profesionales de diversas especialidades trabajando de forma integrada</p>
        </div>
        <div class="gs-highlight-item">
          <h4>Actualización Constante</h4>
          <p>Formación continua en las últimas tendencias y tecnologías del sector</p>
        </div>
        <div class="gs-highlight-item">
          <h4>Orientación al Mercado</h4>
          <p>Soluciones adaptadas a las necesidades reales del sector productivo</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== NUESTROS SERVICIOS (HORIZONTAL POR TÍTULOS) - MEJORADO ===== -->
<section class="gs-section">
  <div class="gs-container">
    <h2 class="gs-section-title">Nuestros Servicios</h2>

    <div class="gs-services-columns" role="list">
      <!-- Columna 1 -->
      <div class="gs-service-col" role="listitem">
        <h3>Estudios Técnicos Especializados</h3>
        <ul>
          <li><strong>Estudios Hidrogeológicos</strong><p>Disponibilidad y dinámica del agua subterránea para proyectos agrícolas, industriales o comunitarios.</p></li>
          <li><strong>Calidad de Agua</strong><p>Análisis físico-químico y microbiológico para riego o consumo.</p></li>
          <li><strong>Estudios de Suelos</strong><p>Diagnóstico de propiedades físicas, químicas y biológicas.</p></li>
          <li><strong>Fertilidad de Suelos</strong><p>Uso sostenible y productivo del suelo.</p></li>
        </ul>
      </div>

      <!-- Columna 2 - AMPLIADA -->
      <div class="gs-service-col" role="listitem">
        <h3>Agricultura de Precisión</h3>
        <ul>
          <li><strong>Planes de Fertilización Avanzada</strong><p>Curvas de absorción de nutrientes por etapa fenológica y fertirriego automatizado.</p></li>
          <li><strong>Agricultura Controlada</strong><p>Monitoreo en tiempo real de variables ambientales y sistemas de control automatizado.</p></li>
          <li><strong>Fotogrametría y Teledetección</strong><p>Drones para mapeo NDVI, análisis multitemporales y detección de estrés hídrico.</p></li>
          <li><strong>SIG Especializado</strong><p>Modelos digitales de alta precisión y cartografía de variabilidad espacial.</p></li>
          <li><strong>Agricultura Regenerativa</strong><p>Capacitaciones en salud del suelo, secuestro de carbono y prácticas sostenibles.</p></li>
        </ul>
      </div>

      <!-- Columna 3 - AMPLIADA -->
      <div class="gs-service-col" role="listitem">
        <h3>Certificación Agrícola</h3>
        <ul>
          <li><strong>Certificaciones Internacionales</strong><p>BPA, GlobalG.A.P., Rainforest Alliance, Fairtrade, UTZ Certified.</p></li>
          <li><strong>Inocuidad Alimentaria HACCP</strong><p>Implementación de sistemas HACCP y diseño de plantas empacadoras certificadas.</p></li>
          <li><strong>Trazabilidad Completa</strong><p>Sistemas digitales de rastreo desde campo hasta consumidor final.</p></li>
          <li><strong>Capacitación Sostenible</strong><p>Programas formativos en agricultura regenerativa y prácticas ambientalmente responsables.</p></li>
        </ul>
      </div>

      <!-- Columna 4 - AMPLIADA -->
      <div class="gs-service-col" role="listitem">
        <h3>Gestión Ambiental</h3>
        <ul>
          <li><strong>Estudios de Impacto Ambiental</strong><p>EIA especializados con análisis de vulnerabilidad y planes de mitigación.</p></li>
          <li><strong>Manejo Integral de Cuencas</strong><p>Planes hidrográficos, conservación hídrica y gestión de ecosistemas.</p></li>
          <li><strong>Cambio Climático</strong><p>Estudios de adaptación climática, vulnerabilidad y análisis de escenarios futuros.</p></li>
          <li><strong>Análisis Multitemporales</strong><p>Evaluación de cambios de uso de suelo y monitoreo de cobertura vegetal.</p></li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- ===== INSUMOS AGRÍCOLAS ===== -->
<section class="gs-section gs-about gs-insumos" id="insumos">
  <div class="gs-container">
    <h2 class="gs-section-title">Insumos Agrícolas</h2>
    <div class="gs-services-grid">
      <article class="gs-service-card">
        <h3>Fertilizantes</h3>
        <ul class="gs-service-list">
          <li><strong>Fórmulas NPK</strong><p>Formulaciones balanceadas por etapa fenológica y meta de rendimiento.</p></li>
          <li><strong>Fosfatos y Potásicos</strong><p>Fuentes de liberación rápida o controlada.</p></li>
          <li><strong>Enmiendas (Cal/Yeso)</strong><p>Corrección de acidez, mejora de CICE y estructura del suelo.</p></li>
        </ul>
      </article>
      <article class="gs-service-card">
        <h3>Bioestimulantes</h3>
        <ul class="gs-service-list">
          <li><strong>Extractos de algas y aminoácidos</strong><p>Enraizamiento, cuaje y tolerancia a estrés.</p></li>
          <li><strong>Ácidos húmicos y fúlvicos</strong><p>Disponibilidad de nutrientes y actividad microbiana.</p></li>
          <li><strong>Quelatos y micronutrientes</strong><p>Corrección precisa de deficiencias.</p></li>
        </ul>
      </article>
      <article class="gs-service-card">
        <h3>Microorganismos mejoradores del suelo</h3>
        <ul class="gs-service-list">
          <li><strong>Micorrizas y Trichoderma</strong><p>Absorción de P y resiliencia ante patógenos.</p></li>
          <li><strong>Rizobacterias (PGPR)</strong><p>Fijación biológica de N, solubilización de P.</p></li>
          <li><strong>Consorcios personalizados</strong><p>Ajustados a cultivo, suelo y objetivos de producción.</p></li>
        </ul>
      </article>
    </div>
  </div>
</section>

<!-- ===== COBERTURA ===== -->
<section class="gs-section gs-coverage" aria-labelledby="cov-title">
  <div class="gs-container">
    <h2 id="cov-title" class="gs-section-title">Cobertura Geográfica</h2>
    <div class="gs-coverage-content">
      <h3>Área de Operaciones</h3>
      <p>Operamos en toda la región central y altiplano del país, con proyección regional en Centroamérica.</p>
      <p>Nuestro equipo está preparado para brindar servicios de consultoría especializada en agricultura y medio ambiente en las principales zonas productivas de Guatemala y la región centroamericana.</p>
      <div class="gs-coverage-features">
        <div class="gs-coverage-feature">
          <h4>Región Central</h4>
          <p>Altiplano guatemalteco</p>
        </div>
        <div class="gs-coverage-feature">
          <h4>Centroamérica</h4>
          <p>Proyección regional</p>
