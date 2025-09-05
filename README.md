<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Green Solutions - Consultoría Agrícola y Ambiental</title>
</head>
<body>

<style>
/* ===== BASE MEJORADO ===== */
* { margin:0; padding:0; box-sizing:border-box; }
html, body { height: 100%; overflow-x: hidden; }
body { 
  font-family:'Inter','Google Sans','Roboto',Arial,sans-serif; 
  line-height:1.6; color:#2c3e50; background: #ffffff;
}
.gs-container { max-width:1400px; margin:0 auto; padding:0 40px; }

/* ===== HEADER FULLSCREEN con animaciones ===== */
.gs-header {
  position: relative;
  color: white;
  text-align: center;
  padding: 0;
  margin: 0;
  overflow: hidden;
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
}

.gs-hero-bg { 
  position: fixed; 
  top: 0; left: 0; 
  width: 100vw; 
  height: 100vh; 
  z-index: 0; 
}

.gs-hero-bg img {
  position: absolute; 
  top: 0; left: 0; 
  width: 100%; 
  height: 100%;
  object-fit: cover; 
  opacity: 0; 
  transition: opacity 1200ms ease, transform 20s ease-in-out; 
  pointer-events: none;
  filter: saturate(1.1) brightness(0.85) contrast(1.1);
  transform: scale(1);
}

.gs-hero-bg img.is-active { 
  opacity: 1; 
  transform: scale(1.05);
}

/* Overlay dinámico mejorado */
.gs-header::before {
  content:'';
  position: fixed; 
  top: 0; left: 0; 
  width: 100vw; 
  height: 100vh; 
  z-index: 1;
  background: 
    radial-gradient(circle at 30% 70%, rgba(27,67,50,0.6) 0%, transparent 50%),
    radial-gradient(circle at 70% 30%, rgba(45,90,61,0.4) 0%, transparent 50%),
    linear-gradient(135deg, rgba(27,67,50,0.7), rgba(45,90,61,0.5), rgba(34,139,34,0.3));
  animation: overlayPulse 8s ease-in-out infinite;
}

@keyframes overlayPulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.8; }
}

.gs-header .gs-container { 
  position: relative; 
  z-index: 10; 
  animation: heroFadeIn 2s ease-out;
  max-width: 900px;
}

@keyframes heroFadeIn {
  0% { opacity: 0; transform: translateY(30px); }
  100% { opacity: 1; transform: translateY(0); }
}

.gs-header h1 {
  font-size: 4.5rem; 
  font-weight: 200; 
  margin-bottom: 2rem;
  letter-spacing: 4px; 
  text-transform: uppercase;
  text-shadow: 2px 2px 8px rgba(0,0,0,0.5);
  animation: titleGlow 3s ease-in-out infinite;
  background: linear-gradient(45deg, #ffffff, #e8f5e8);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

@keyframes titleGlow {
  0%, 100% { text-shadow: 2px 2px 8px rgba(0,0,0,0.5); }
  50% { text-shadow: 2px 2px 20px rgba(255,255,255,0.3), 0 0 30px rgba(255,255,255,0.2); }
}

.gs-header p {
  font-size: 1.4rem; 
  margin-bottom: 3rem; 
  opacity: 0.95; 
  font-weight: 300;
  max-width: 700px; 
  margin-left: auto; 
  margin-right: auto;
  text-shadow: 1px 1px 4px rgba(0,0,0,0.4);
  animation: subtitleSlide 2s ease-out 0.5s both;
}

@keyframes subtitleSlide {
  0% { opacity: 0; transform: translateY(20px); }
  100% { opacity: 0.95; transform: translateY(0); }
}

.gs-cta-button {
  background: transparent; 
  color: white; 
  padding: 18px 45px; 
  border: 2px solid rgba(255,255,255,0.8);
  font-size: 1rem; 
  text-decoration: none; 
  display: inline-block; 
  transition: all 0.4s ease;
  font-weight: 500; 
  letter-spacing: 2px; 
  text-transform: uppercase;
  border-radius: 50px;
  position: relative;
  overflow: hidden;
  animation: buttonPulse 2s ease-out 1s both;
  backdrop-filter: blur(10px);
  background: rgba(255,255,255,0.1);
}

@keyframes buttonPulse {
  0% { opacity: 0; transform: scale(0.8); }
  100% { opacity: 1; transform: scale(1); }
}

.gs-cta-button::before {
  content: '';
  position: absolute;
  top: 0; left: -100%;
  width: 100%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
  transition: left 0.6s ease;
}

.gs-cta-button:hover::before {
  left: 100%;
}

.gs-cta-button:hover { 
  background: rgba(255,255,255,0.95); 
  color: #1b4332; 
  transform: translateY(-3px) scale(1.05);
  box-shadow: 0 15px 40px rgba(0,0,0,0.3);
  border-color: white;
}

/* Indicador de scroll */
.scroll-indicator {
  position: absolute;
  bottom: 30px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 10;
  color: white;
  animation: scrollBounce 2s infinite;
  cursor: pointer;
  transition: opacity 0.3s ease;
}

@keyframes scrollBounce {
  0%, 20%, 50%, 80%, 100% { transform: translateX(-50%) translateY(0); }
  40% { transform: translateX(-50%) translateY(-10px); }
  60% { transform: translateX(-50%) translateY(-5px); }
}

.scroll-indicator:hover {
  opacity: 0.7;
}

/* ===== SECCIONES MEJORADAS ===== */
.gs-section { 
  padding: 120px 0; 
  position: relative;
  background: linear-gradient(180deg, #ffffff 0%, #fafcfa 100%);
}

.gs-section:nth-child(even) {
  background: linear-gradient(180deg, #f8fdf9 0%, #ffffff 100%);
}

.gs-section-title {
  text-align: center; 
  font-size: 3rem; 
  color: #1b4332; 
  margin-bottom: 4rem;
  font-weight: 200; 
  letter-spacing: 3px; 
  text-transform: uppercase; 
  position: relative;
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s ease;
}

.gs-section-title.animate {
  opacity: 1;
  transform: translateY(0);
}

.gs-section-title::after {
  content: ''; 
  width: 80px; 
  height: 4px; 
  background: linear-gradient(90deg, #2d5a3d, #52b788);
  position: absolute; 
  bottom: -30px; 
  left: 50%; 
  transform: translateX(-50%);
  border-radius: 2px;
  animation: lineGrow 1s ease 0.5s both;
}

@keyframes lineGrow {
  0% { width: 0; }
  100% { width: 80px; }
}

/* ===== QUIÉNES SOMOS MEJORADO ===== */
.gs-about { 
  background: linear-gradient(135deg, #f8fdf9 0%, #e8f5e8 100%);
  position: relative;
  overflow: hidden;
}

.gs-about::before {
  content: '';
  position: absolute;
  top: -50%;
  right: -20%;
  width: 60%;
  height: 200%;
  background: radial-gradient(circle, rgba(45,90,61,0.05) 0%, transparent 70%);
  animation: floatPattern 20s linear infinite;
}

@keyframes floatPattern {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.gs-about-grid { 
  display: grid; 
  grid-template-columns: 1fr 1fr; 
  gap: 8rem; 
  align-items: start; 
  margin-top: 3rem; 
  max-width: 1200px; 
  margin-left: auto; 
  margin-right: auto;
  position: relative;
  z-index: 1;
}

.gs-about-text {
  opacity: 0;
  transform: translateX(-30px);
  transition: all 0.8s ease;
}

.gs-about-text.animate {
  opacity: 1;
  transform: translateX(0);
}

.gs-about-text:nth-child(2) {
  transform: translateX(30px);
}

.gs-about-text h3 { 
  color: #1b4332; 
  font-size: 1.8rem; 
  margin-bottom: 2rem; 
  font-weight: 400; 
  letter-spacing: 1px;
  position: relative;
}

.gs-about-text h3::before {
  content: '';
  position: absolute;
  left: -20px;
  top: 50%;
  transform: translateY(-50%);
  width: 4px;
  height: 30px;
  background: linear-gradient(180deg, #2d5a3d, #52b788);
  border-radius: 2px;
}

.gs-about-text p { 
  font-size: 1.1rem; 
  line-height: 1.9; 
  color: #555; 
  font-weight: 300; 
  margin-bottom: 1.5rem;
  text-align: justify;
}

/* ===== EQUIPO CONSULTOR MEJORADO ===== */
.gs-team-description { 
  max-width: 1000px; 
  margin: 0 auto; 
  text-align: center; 
}

.gs-team-description p { 
  font-size: 1.2rem; 
  line-height: 1.9; 
  color: #555; 
  margin-bottom: 2rem; 
  text-align: justify;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.8s ease;
}

.gs-team-description p.animate {
  opacity: 1;
  transform: translateY(0);
}

.gs-team-highlights { 
  display: grid; 
  grid-template-columns: repeat(3, 1fr); 
  gap: 3rem; 
  margin-top: 4rem; 
  justify-items: center;
}

.gs-team-highlights .gs-highlight-item:nth-child(4) {
  grid-column: 2 / 3;
}

.gs-highlight-item { 
  background: white; 
  padding: 3rem; 
  border: 1px solid #e8f2ec; 
  text-align: center; 
  position: relative; 
  transition: all 0.4s ease; 
  border-radius: 15px;
  box-shadow: 0 8px 25px rgba(0,0,0,0.08);
  opacity: 0;
  transform: translateY(30px);
  overflow: hidden;
}

.gs-highlight-item.animate {
  opacity: 1;
  transform: translateY(0);
}

.gs-highlight-item::before { 
  content: ''; 
  position: absolute; 
  top: 0; 
  left: 0; 
  width: 4px; 
  height: 100%; 
  background: linear-gradient(180deg, #2d5a3d, #52b788);
  border-radius: 4px 0 0 4px;
  transition: width 0.4s ease;
}

.gs-highlight-item::after {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(45,90,61,0.03) 0%, transparent 70%);
  transition: all 0.4s ease;
  opacity: 0;
}

.gs-highlight-item:hover::after {
  opacity: 1;
  transform: scale(1.1);
}

.gs-highlight-item:hover { 
  box-shadow: 0 20px 50px rgba(27,67,50,0.2); 
  transform: translateY(-8px) scale(1.02);
}

.gs-highlight-item:hover::before {
  width: 100%;
  opacity: 0.1;
}

.gs-highlight-item h4 { 
  color: #1b4332; 
  font-size: 1.3rem; 
  margin-bottom: 1.5rem; 
  font-weight: 600;
  position: relative;
  z-index: 1;
}

.gs-highlight-item p { 
  color: #666; 
  font-size: 1rem; 
  line-height: 1.6;
  position: relative;
  z-index: 1;
}

/* ===== SERVICIOS MEJORADOS ===== */
.gs-services-columns {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 3rem;
  max-width: 1300px;
  margin: 0 auto;
  align-items: start;
}

.gs-service-col {
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.8s ease;
}

.gs-service-col.animate {
  opacity: 1;
  transform: translateY(0);
}

.gs-service-col h3 {
  color: #1b4332;
  font-size: 1.3rem;
  margin-bottom: 2rem;
  font-weight: 700;
  letter-spacing: 0.5px;
  border-bottom: 3px solid #e8f2ec;
  padding-bottom: 1rem;
  position: relative;
  transition: all 0.3s ease;
}

.gs-service-col h3::after {
  content: '';
  position: absolute;
  bottom: -3px;
  left: 0;
  width: 0;
  height: 3px;
  background: linear-gradient(90deg, #2d5a3d, #52b788);
  transition: width 0.4s ease;
}

.gs-service-col:hover h3::after {
  width: 100%;
}

.gs-service-col ul { list-style: none; }

.gs-service-col li { 
  margin-bottom: 1.5rem; 
  padding: 1.5rem;
  background: white;
  border-radius: 12px;
  border: 1px solid #f0f4f1;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.gs-service-col li::before {
  content: '';
  position: absolute;
  top: 0; left: -100%;
  width: 100%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(45,90,61,0.05), transparent);
  transition: left 0.6s ease;
}

.gs-service-col li:hover::before {
  left: 100%;
}

.gs-service-col li:hover {
  box-shadow: 0 8px 25px rgba(27,67,50,0.15);
  transform: translateY(-3px);
  border-color: #e8f2ec;
}

.gs-service-col li strong { 
  color: #1b4332; 
  display: block; 
  margin-bottom: 0.5rem; 
  font-size: 1rem; 
  font-weight: 600;
  position: relative;
  z-index: 1;
}

.gs-service-col li p { 
  color: #555; 
  font-size: 0.95rem; 
  font-weight: 300; 
  line-height: 1.6;
  position: relative;
  z-index: 1;
}

/* ===== INSUMOS MEJORADOS ===== */
.gs-insumos { 
  background: linear-gradient(135deg, #f8fdf9 0%, #e8f5e8 100%);
  position: relative;
}

.gs-services-grid { 
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); 
  gap: 4rem; 
  margin-top: 5rem; 
  max-width: 1200px; 
  margin-left: auto; 
  margin-right: auto;
}

.gs-service-card { 
  background: white; 
  padding: 3rem; 
  border: 1px solid #e8f2ec; 
  position: relative; 
  border-radius: 20px; 
  transition: all 0.4s ease;
  box-shadow: 0 10px 30px rgba(0,0,0,0.08);
  opacity: 0;
  transform: translateY(30px);
}

.gs-service-card.animate {
  opacity: 1;
  transform: translateY(0);
}

.gs-service-card:hover {
  box-shadow: 0 20px 60px rgba(27,67,50,0.2);
  transform: translateY(-10px);
}

.gs-service-card::before { 
  content: ''; 
  position: absolute; 
  top: 0; 
  left: 0; 
  width: 4px; 
  height: 100%; 
  background: linear-gradient(180deg, #2d5a3d, #52b788);
  border-radius: 4px 0 0 4px;
}

.gs-service-card h3 { 
  color: #1b4332; 
  font-size: 1.4rem; 
  margin-bottom: 2rem; 
  font-weight: 700; 
  letter-spacing: 0.5px; 
}

.gs-service-list { list-style: none; }

.gs-service-list li { 
  margin-bottom: 1.5rem; 
  padding: 1.5rem 0; 
  border-bottom: 1px solid #f0f4f1; 
}

.gs-service-list li:last-child { border-bottom: none; }

.gs-service-list li strong { 
  color: #1b4332; 
  display: block; 
  margin-bottom: 0.5rem; 
  font-size: 1rem; 
  font-weight: 600; 
}

.gs-service-list li p { 
  color: #666; 
  font-size: 0.95rem; 
  font-weight: 300; 
}

/* ===== COBERTURA MEJORADA ===== */
.gs-coverage { 
  background: linear-gradient(135deg, #1b4332 0%, #2d5a3d 50%, #52b788 100%);
  color: white; 
  text-align: center;
  position: relative;
  overflow: hidden;
}

.gs-coverage::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: 
    radial-gradient(circle at 20% 80%, rgba(255,255,255,0.1) 0%, transparent 50%),
    radial-gradient(circle at 80% 20%, rgba(255,255,255,0.05) 0%, transparent 50%);
  animation: coverageFloat 15s ease-in-out infinite;
}

@keyframes coverageFloat {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(2deg); }
}

.gs-coverage .gs-section-title { color: white; }
.gs-coverage .gs-section-title::after { background: linear-gradient(90deg, #ffffff, #e8f5e8); }

.gs-coverage-content { max-width: 700px; margin: 0 auto; }

.gs-coverage h3 { 
  font-size: 1.6rem; 
  margin-bottom: 2rem; 
  font-weight: 300; 
  letter-spacing: 1px; 
}

.gs-coverage p { 
  font-size: 1.1rem; 
  margin-bottom: 2rem; 
  line-height: 1.7; 
  font-weight: 300; 
  opacity: 0.9; 
}

.gs-coverage-features { 
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); 
  gap: 2rem; 
  margin-top: 4rem; 
}

.gs-coverage-feature { 
  background: rgba(255,255,255,0.05); 
  padding: 2rem; 
  border: 1px solid rgba(255,255,255,0.1); 
  transition: 0.3s ease; 
  border-radius: 8px;
}

.gs-coverage-feature:hover { 
  background: rgba(255,255,255,0.1); 
  transform: translateY(-2px);
}

.gs-coverage-feature h4 { 
  font-size: 1rem; 
  margin-bottom: 0.8rem; 
  font-weight: 400; 
  letter-spacing: 0.5px; 
}

.gs-coverage-feature p { 
  font-size: 0.9rem; 
  opacity: 0.8; 
}

/* ===== CONTACTO MEJORADO ===== */
.gs-contact { 
  background: linear-gradient(135deg, #f8fdf9 0%, #ffffff 100%);
  position: relative;
}

.gs-contact-grid { 
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); 
  gap: 4rem; 
  margin-top: 5rem; 
  max-width: 1000px; 
  margin-left: auto; 
  margin-right: auto;
}

.gs-contact-card { 
  background: white; 
  padding: 3rem; 
  text-align: center; 
  border: 1px solid #e8f2ec; 
  transition: all 0.4s ease; 
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.08);
  opacity: 0;
  transform: translateY(30px);
  position: relative;
  overflow: hidden;
}

.gs-contact-card.animate {
  opacity: 1;
  transform: translateY(0);
}

.gs-contact-card::before {
  content: '';
  position: absolute;
  top: -50%; left: -50%;
  width: 200%; height: 200%;
  background: radial-gradient(circle, rgba(45,90,61,0.03) 0%, transparent 70%);
  transition: all 0.6s ease;
  opacity: 0;
}

.gs-contact-card:hover::before {
  opacity: 1;
  transform: scale(1.2);
}

.gs-contact-card:hover { 
  box-shadow: 0 20px 60px rgba(27,67,50,0.2); 
  transform: translateY(-10px);
}

.gs-contact-icon { 
  width: 80px; 
  height: 80px; 
  background: linear-gradient(135deg, #2d5a3d, #52b788); 
  margin: 0 auto 2rem; 
  display: flex; 
  align-items: center; 
  justify-content: center; 
  color: white; 
  font-size: 1.5rem; 
  font-weight: 300; 
  border-radius: 50%;
  position: relative;
  z-index: 1;
  transition: all 0.4s ease;
}

.gs-contact-card:hover .gs-contact-icon {
  transform: scale(1.1) rotateY(360deg);
}

.gs-contact-card h3 { 
  color: #1b4332; 
  margin-bottom: 1rem; 
  font-size: 1.2rem; 
  font-weight: 700; 
  letter-spacing: 0.5px; 
}

.gs-contact-card p { 
  font-weight: 400; 
  color: #555; 
  font-size: 1rem; 
}

.gs-contact-card a { 
  color: #2d5a3d; 
  text-decoration: none; 
  transition: color 0.3s ease; 
}

.gs-contact-card a:hover { 
  color: #1b4332; 
}

.gs-contact-cta { 
  text-align: center; 
  margin-top: 4rem; 
  padding: 3rem; 
  background: white; 
  border: 1px solid #e8f2ec; 
  border-radius: 15px;
}

.gs-contact-cta h3 { 
  color: #1b4332; 
  margin-bottom: 1.5rem; 
  font-weight: 700; 
  font-size: 1.3rem; 
}

.gs-contact-cta p { 
  margin-bottom: 2rem; 
  color: #666; 
  font-weight: 300; 
  line-height: 1.6; 
}

/* ===== FOOTER MEJORADO ===== */
.gs-footer { 
  background: linear-gradient(135deg, #0d2818 0%, #1b4332 100%); 
  color: white; 
  padding: 80px 0 40px; 
  position: relative;
  overflow: hidden;
}

.gs-footer::before {
  content: '';
  position: absolute;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: 
    radial-gradient(circle at 10% 90%, rgba(255,255,255,0.05) 0%, transparent 50%),
    radial-gradient(circle at 90% 10%, rgba(45,90,61,0.1) 0%, transparent 50%);
}

.gs-footer-content { 
  max-width: 1200px; 
  margin: 0 auto; 
  padding: 0 40px;
}

.gs-footer-grid { 
  display: grid; 
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); 
  gap: 3rem; 
  margin-bottom: 3rem; 
}

.gs-footer-section h4 { 
  color: white; 
  margin-bottom: 1.5rem; 
  font-size: 1.1rem; 
  font-weight: 700; 
  letter-spacing: 0.5px; 
}

.gs-footer-section p { 
  color: rgba(255,255,255,0.7); 
  line-height: 1.6; 
  margin-bottom: 0.8rem; 
  font-size: 0.9rem; 
  font-weight: 300; 
}

.gs-footer-section a { 
  color: rgba(255,255,255,0.8); 
  text-decoration: none; 
  transition: color 0.3s ease; 
}

.gs-footer-section a:hover { 
  color: white; 
}

.gs-footer-bottom { 
  border-top: 1px solid rgba(255,255,255,0.1); 
  padding-top: 2rem; 
  text-align: center; 
}

.gs-footer-bottom p { 
  margin-bottom: 0.5rem; 
  color: rgba(255,255,255,0.6); 
  font-size: 0.9rem; 
}

.gs-social-links { 
  margin-top: 1.5rem; 
}

.gs-social-links a { 
  display: inline-block; 
  margin: 0 8px; 
  padding: 8px; 
  background: rgba(255,255,255,0.1); 
  width: 36px; 
  height: 36px; 
  text-align: center; 
  line-height: 20px; 
  transition: 0.3s ease; 
  color: white; 
  text-decoration: none; 
  font-size: 0.9rem; 
  border-radius: 50%;
}

.gs-social-links a:hover { 
  background: #2d5a3d; 
  transform: translateY(-2px);
}

/* ===== RESPONSIVE MEJORADO ===== */
@media (max-width: 1200px) {
  .gs-container { padding: 0 30px; }
  .gs-services-columns { grid-template-columns: repeat(2, 1fr); gap: 2.5rem; }
}

@media (max-width: 768px) {
  .gs-header h1 { font-size: 3rem; letter-spacing: 2px; }
  .gs-header p { font-size: 1.2rem; }
  .gs-section-title { font-size: 2.2rem; letter-spacing: 2px; }
  .gs-about-grid { grid-template-columns: 1fr; gap: 4rem; }
  .gs-services-columns { grid-template-columns: 1fr; }
  .gs-team-highlights { grid-template-columns: 1fr; }
  .gs-team-highlights .gs-highlight-item:nth-child(4) { grid-column: 1; }
  .gs-section { padding: 80px 0; }
  .gs-container { padding: 0 20px; }
}

@media (max-width: 480px) {
  .gs-header h1 { font-size: 2.5rem; }
  .gs-header p { font-size: 1.1rem; }
  .gs-cta-button { padding: 15px 35px; font-size: 0.9rem; }
}

/* ===== ANIMACIONES DE SCROLL ===== */
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
</style>

<!-- ===== HEADER FULLSCREEN ===== -->
<header class="gs-header">
  <div class="gs-hero-bg" aria-hidden="true">
    <img data-drive-id="101-TMmVzQSdmJ-Z9mSQPHP3quFGCNwrp" alt="" />
    <img data-drive-id="1amoLZ92OaAIwXVXmNzdFNS6vlHSYAuHa" alt="" />
    <img data-drive-id="15n6w-kvWBSw9QuyZTRES3Bw8DRcoEh4H" alt="" />
    <img data-drive-id="1eNfbN_X2m9mgvkMQX2HFeAdeDZV2B-af" alt="" />
    <img data-drive-id="1wdBt99BNhPrsJmHnSOtfJGsXOTTGn6UX" alt="" />
    <img data-drive-id="1r8NDZpRjRgoOa1GmfCZyVCAt7pctajvW" alt="" />
    <img data-drive-id="12yTJ47sqK_pTGF93UDTY4IU8n4hcxwBJ" alt="" />
    <img data-drive-id="1wFraSDd7I1o2hl8kw5wf95C0k47ERU2f" alt="" />
  </div>
  <div class="gs-container">
    <h1>Green Solutions</h1>
    <p>Consultoría especializada en agricultura sostenible y gestión ambiental</p>
    <a
      href="mailto:gr3ensolutions@gmail.com?subject=Consulta%20sobre%20servicios%20de%20Green%20Solutions&body=Hola%20Green%20Solutions%2C%0D%0A%0D%0AMe%20gustar%C3%ADa%20recibir%20informaci%C3%B3n%20sobre%3A%20[breve%20descripci%C3%B3n]%0D%0AUbicaci%C3%B3n%3A%20%0D%0ATel%C3%A9fono%3A%20%0D%0A%0D%0AGracias."
      class="gs-cta-button"
      title="Enviar correo a Green Solutions"
    >Contáctanos</a>
  </div>
  <div class="scroll-indicator" onclick="scrollToSection()">
    <div style="font-size: 1.5rem;">↓</div>
    <div style="font-size: 0.8rem; margin-top: 5px;">Descubre más</div>
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

<!-- ===== NUESTROS SERVICIOS ===== -->
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

      <!-- Columna 2 -->
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

      <!-- Columna 3 -->
      <div class="gs-service-col" role="listitem">
        <h3>Certificación Agrícola</h3>
        <ul>
          <li><strong>Certificaciones Internacionales</strong><p>BPA, GlobalG.A.P., Rainforest Alliance, Fairtrade, UTZ Certified.</p></li>
          <li><strong>Inocuidad Alimentaria HACCP</strong><p>Implementación de sistemas HACCP y diseño de plantas empacadoras certificadas.</p></li>
          <li><strong>Trazabilidad Completa</strong><p>Sistemas digitales de rastreo desde campo hasta consumidor final.</p></li>
          <li><strong>Capacitación Sostenible</strong><p>Programas formativos en agricultura regenerativa y prácticas ambientalmente responsables.</p></li>
        </ul>
      </div>

      <!-- Columna 4 -->
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
        </div>
        <div class="gs-coverage-feature">
          <h4>Equipo Móvil</h4>
          <p>Servicios especializados</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ===== CONTACTO ===== -->
<section class="gs-section gs-contact" id="contacto">
  <div class="gs-container">
    <h2 class="gs-section-title">Contáctanos</h2>
    <div class="gs-contact-grid">
      <div class="gs-contact-card">
        <div class="gs-contact-icon">T</div>
        <h3>Teléfono</h3>
        <p><a href="tel:+50235952912">+502 3595-2912</a></p>
      </div>
      <div class="gs-contact-card">
        <div class="gs-contact-icon">@</div>
        <h3>Email</h3>
        <p><a href="mailto:gr3ensolutions@gmail.com">gr3ensolutions@gmail.com</a></p>
      </div>
      <div class="gs-contact-card">
        <div class="gs-contact-icon">◉</div>
        <h3>Ubicación</h3>
        <p>Guatemala - Centroamérica</p>
      </div>
    </div>
    <div class="gs-contact-cta">
      <h3>Impulsa tu proyecto agrícola</h3>
      <p>Contáctanos y descubre cómo podemos transformar tu agricultura con soluciones sostenibles e innovadoras.</p>
      <a href="mailto:gr3ensolutions@gmail.com?subject=Solicitud%20de%20consulta&body=Hola%20Green%20Solutions%2C%0D%0ANecesito%20asesor%C3%ADa%20en%3A%20[tema]%0D%0ATel%C3%A9fono%3A%20%0D%0AUbicaci%C3%B3n%3A%20%0D%0A"
         class="gs-cta-button">Solicita una Consulta</a>
    </div>
  </div>
</section>

<!-- ===== FOOTER ===== -->
<footer class="gs-footer" role="contentinfo">
  <div class="gs-footer-content">
    <div class="gs-footer-grid">
      <div class="gs-footer-section">
        <h4>Green Solutions</h4>
        <p>Consultoría especializada en agricultura sostenible y gestión ambiental en Guatemala.</p>
        <p>Transformando la agricultura hacia modelos más resilientes y productivos.</p>
      </div>
      <div class="gs-footer-section">
        <h4>Servicios</h4>
        <p>Estudios de suelos y agua</p>
        <p>Agricultura de precisión</p>
        <p>Certificaciones agrícolas</p>
        <p>Gestión ambiental</p>
      </div>
      <div class="gs-footer-section">
        <h4>Contacto</h4>
        <p><a href="tel:+50235952912">+502 3595-2912</a></p>
        <p><a href="mailto:gr3ensolutions@gmail.com">gr3ensolutions@gmail.com</a></p>
        <p>Guatemala, Centroamérica</p>
      </div>
    </div>
    <div class="gs-footer-bottom">
      <p>&copy; 2025 Green Solutions. Todos los derechos reservados.</p>
      <p>Consultoría Agrícola y Ambiental - Guatemala</p>
      <div class="gs-social-links">
        <a href="https://wa.me/50235952912" target="_blank" title="WhatsApp">W</a>
        <a href="tel:+50235952912" title="Teléfono">T</a>
        <a href="#contacto" title="Ver contacto">@</a>
        <a href="https://www.linkedin.com/company/green-solutions-guatemala" target="_blank" title="LinkedIn">in</a>
      </div>
    </div>
  </div>
</footer>

<!-- ===== SCRIPTS MEJORADOS ===== -->
<script>
/* ===== CARRUSEL DE FONDO MEJORADO ===== */
(function(){
  const hero = document.querySelector('.gs-hero-bg');
  if(!hero) return;

  const buildSrcs = (id) => ([
    `https://drive.google.com/uc?export=view&id=${id}`,
    `https://drive.google.com/thumbnail?id=${id}&sz=w2000`,
    `https://drive.google.com/uc?export=download&id=${id}`,
    `https://lh3.googleusercontent.com/d/${id}=w2000`
  ]);

  const imgs = Array.from(hero.querySelectorAll('img[data-drive-id]'));
  let loadedCount = 0;
  
  imgs.forEach((img, i) => {
    const id = img.getAttribute('data-drive-id');
    const candidates = buildSrcs(id);
    let pos = 0;
    
    const tryNext = () => { 
      if (pos < candidates.length) {
        img.src = candidates[pos++];
      } else {
        loadedCount++;
        checkStart();
      }
    };
    
    img.addEventListener('error', tryNext);
    img.addEventListener('load', () => {
      loadedCount++;
      checkStart();
    });
    
    if(i === 0){ 
      img.setAttribute('decoding','async'); 
      img.setAttribute('fetchpriority','high'); 
    }
    
    tryNext();
  });

  function checkStart() {
    if (loadedCount >= Math.min(3, imgs.length)) {
      startCarousel();
    }
  }

  function startCarousel() {
    let index = 0;
    const total = imgs.length;
    const intervalMs = 6000;

    function show(i){
      imgs.forEach((el,k) => el.classList.toggle('is-active', k === i));
    }
    
    show(0);
    
    if (total > 1) {
      setInterval(() => { 
        index = (index + 1) % total; 
        show(index); 
      }, intervalMs);
    }
  }

  if (window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
    imgs.forEach(el => el.style.transition = 'none');
  }
})();

/* ===== ANIMACIONES DE SCROLL ===== */
function setupScrollAnimations() {
  const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
  };

  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate');
      }
    });
  }, observerOptions);

  // Observar elementos animables
  const animateElements = document.querySelectorAll(
    '.gs-section-title, .gs-about-text, .gs-team-description p, .gs-highlight-item, .gs-service-col, .gs-service-card, .gs-contact-card'
  );

  animateElements.forEach(el => observer.observe(el));
}

/* ===== SCROLL SUAVE ===== */
function scrollToSection() {
  const firstSection = document.querySelector('.gs-about');
  if (firstSection) {
    firstSection.scrollIntoView({ behavior: 'smooth' });
  }
}

// Navegación suave para enlaces internos
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
  anchor.addEventListener('click', function (e) {
    e.preventDefault();
    const target = document.querySelector(this.getAttribute('href'));
    if (target) {
      target.scrollIntoView({ behavior: 'smooth', block: 'start' });
    }
  });
});

/* ===== PARALLAX SUTIL ===== */
function setupParallax() {
  let ticking = false;
  
  function updateParallax() {
    const scrolled = window.pageYOffset;
    const rate = scrolled * -0.5;
    
    const hero = document.querySelector('.gs-hero-bg');
    if (hero && scrolled < window.innerHeight) {
      hero.style.transform = `translateY(${rate}px)`;
    }
    
    ticking = false;
  }
  
  function requestTick() {
    if (!ticking) {
      requestAnimationFrame(updateParallax);
      ticking = true;
    }
  }
  
  window.addEventListener('scroll', requestTick);
}

/* ===== INICIALIZACIÓN ===== */
document.addEventListener('DOMContentLoaded', function() {
  setupScrollAnimations();
  setupParallax();
  
  // Ocultar indicador de scroll al hacer scroll
  let scrollTimeout;
  window.addEventListener('scroll', function() {
    const indicator = document.querySelector('.scroll-indicator');
    if (indicator && window.pageYOffset > 100) {
      indicator.style.opacity = '0';
    }
    
    clearTimeout(scrollTimeout);
    scrollTimeout = setTimeout(() => {
      if (indicator && window.pageYOffset <= 100) {
        indicator.style.opacity = '1';
      }
    }, 150);
  });
});

/* ===== PRELOADER OPCIONAL ===== */
window.addEventListener('load', function() {
  document.body.classList.add('loaded');
});
</script>

</body>
</html>
