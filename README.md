*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --blue-deep: #0B3D91;
  --blue-mid: #185FA5;
  --blue-bright: #2E86DE;
  --blue-light: #A8D0F5;
  --blue-pale: #E8F3FD;
  --ink: #0D0D0D;
  --ink-soft: #3A3A3A;
  --ink-muted: #767676;
  --white: #FFFFFF;
  --cream: #F7F5F0;
  --accent: #FF5533;
  --font-display: 'Syne', sans-serif;
  --font-body: 'DM Sans', sans-serif;
}

html { scroll-behavior: smooth; }

body {
  font-family: var(--font-body);
  background: var(--ink);
  color: var(--white);
  overflow-x: hidden;
}

/* ── NAV ── */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 100;
  display: flex; align-items: center; justify-content: space-between;
  padding: 20px 40px;
  background: rgba(13,13,13,0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255,255,255,0.06);
  transition: padding 0.3s;
}

nav.scrolled {
  padding: 14px 40px;
  border-bottom-color: rgba(255,255,255,0.1);
}

.nav-logo {
  font-family: var(--font-display);
  font-size: 22px;
  font-weight: 800;
  letter-spacing: -0.5px;
  color: var(--white);
  text-decoration: none;
}
.nav-logo span { color: var(--blue-bright); }

.nav-links { display: flex; gap: 32px; list-style: none; }
.nav-links a {
  font-size: 14px;
  font-weight: 400;
  color: rgba(255,255,255,0.6);
  text-decoration: none;
  transition: color 0.2s;
}
.nav-links a:hover { color: var(--white); }

.nav-cta {
  background: var(--blue-bright);
  color: var(--white);
  font-family: var(--font-body);
  font-size: 14px;
  font-weight: 500;
  padding: 10px 22px;
  border-radius: 100px;
  text-decoration: none;
  transition: background 0.2s, transform 0.15s;
}
.nav-cta:hover { background: var(--blue-mid); transform: translateY(-1px); }

/* ── HERO ── */
.hero {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 120px 40px 80px;
  position: relative;
  overflow: hidden;
}

.hero-bg {
  position: absolute; inset: 0; z-index: 0;
  background:
    radial-gradient(ellipse 60% 50% at 70% 40%, rgba(46,134,222,0.18) 0%, transparent 70%),
    radial-gradient(ellipse 40% 40% at 20% 70%, rgba(11,61,145,0.25) 0%, transparent 60%);
}

.hero-grid {
  position: absolute; inset: 0; z-index: 0;
  background-image:
    linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
  background-size: 60px 60px;
  mask-image: radial-gradient(ellipse 80% 60% at 50% 50%, black 40%, transparent 100%);
}

.hero-content { position: relative; z-index: 1; max-width: 900px; }

.hero-badge {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(46,134,222,0.12);
  border: 1px solid rgba(46,134,222,0.3);
  border-radius: 100px;
  padding: 6px 16px;
  font-size: 13px;
  font-weight: 500;
  color: var(--blue-light);
  margin-bottom: 32px;
  opacity: 0;
  animation: fadeUp 0.6s ease forwards;
}

.hero-badge::before {
  content: '';
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--blue-bright);
  animation: pulse 2s ease-in-out infinite;
}

.hero h1 {
  font-family: var(--font-display);
  font-size: clamp(52px, 7vw, 96px);
  font-weight: 800;
  line-height: 1;
  letter-spacing: -3px;
  color: var(--white);
  margin-bottom: 28px;
  opacity: 0;
  animation: fadeUp 0.6s 0.1s ease forwards;
}

.hero h1 em {
  font-style: normal;
  color: transparent;
  -webkit-text-stroke: 1.5px var(--blue-bright);
}

.hero > .hero-content > p {
  font-size: 18px;
  font-weight: 300;
  line-height: 1.7;
  color: rgba(255,255,255,0.65);
  max-width: 520px;
  margin-bottom: 44px;
  opacity: 0;
  animation: fadeUp 0.6s 0.2s ease forwards;
}

.hero-actions {
  display: flex; align-items: center; gap: 20px;
  opacity: 0;
  animation: fadeUp 0.6s 0.3s ease forwards;
}

.btn-primary {
  display: inline-flex; align-items: center; gap: 8px;
  background: var(--blue-bright);
  color: var(--white);
  font-family: var(--font-body);
  font-size: 15px;
  font-weight: 500;
  padding: 14px 28px;
  border-radius: 100px;
  text-decoration: none;
  transition: background 0.2s, transform 0.15s, box-shadow 0.2s;
  box-shadow: 0 0 30px rgba(46,134,222,0.35);
}
.btn-primary:hover {
  background: #1a77d4;
  transform: translateY(-2px);
  box-shadow: 0 0 40px rgba(46,134,222,0.5);
}

.btn-ghost {
  font-size: 14px;
  font-weight: 400;
  color: rgba(255,255,255,0.55);
  text-decoration: none;
  display: flex; align-items: center; gap: 6px;
  transition: color 0.2s;
}
.btn-ghost:hover { color: var(--white); }

.hero-stats {
  display: flex; gap: 48px;
  margin-top: 72px;
  padding-top: 40px;
  border-top: 1px solid rgba(255,255,255,0.08);
  opacity: 0;
  animation: fadeUp 0.6s 0.4s ease forwards;
}

.stat-num {
  font-family: var(--font-display);
  font-size: 36px;
  font-weight: 800;
  color: var(--white);
  letter-spacing: -1px;
}
.stat-label {
  font-size: 13px;
  color: rgba(255,255,255,0.45);
  margin-top: 2px;
}

/* ── SERVICES ── */
.services {
  padding: 100px 40px;
  background: var(--cream);
  color: var(--ink);
}

.section-label {
  font-size: 12px;
  font-weight: 500;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--blue-mid);
  margin-bottom: 16px;
}

.section-title {
  font-family: var(--font-display);
  font-size: clamp(36px, 4vw, 56px);
  font-weight: 800;
  letter-spacing: -2px;
  line-height: 1.05;
  color: var(--ink);
  max-width: 600px;
  margin-bottom: 60px;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2px;
  background: rgba(0,0,0,0.08);
  border-radius: 16px;
  overflow: hidden;
}

.service-card {
  background: var(--white);
  padding: 40px 36px;
  transition: background 0.25s, transform 0.25s;
  cursor: default;
}
.service-card:hover {
  background: var(--blue-pale);
  transform: translateY(-2px);
}

.service-icon {
  width: 48px; height: 48px;
  border-radius: 12px;
  background: var(--blue-pale);
  display: flex; align-items: center; justify-content: center;
  margin-bottom: 24px;
  font-size: 22px;
}

.service-card h3 {
  font-family: var(--font-display);
  font-size: 20px;
  font-weight: 700;
  color: var(--ink);
  margin-bottom: 12px;
  letter-spacing: -0.5px;
}

.service-card p {
  font-size: 14px;
  line-height: 1.7;
  color: var(--ink-muted);
}

/* ── PRICING ── */
.pricing {
  padding: 100px 40px;
  background: var(--ink);
  position: relative;
  overflow: hidden;
}

.pricing::before {
  content: '';
  position: absolute;
  top: -200px; right: -200px;
  width: 600px; height: 600px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(46,134,222,0.1) 0%, transparent 70%);
  pointer-events: none;
}

.pricing .section-label { color: var(--blue-light); }
.pricing .section-title { color: var(--white); margin-bottom: 16px; }

.pricing-sub {
  font-size: 16px;
  color: rgba(255,255,255,0.5);
  margin-bottom: 60px;
  font-weight: 300;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  position: relative; z-index: 1;
}

.price-card {
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 20px;
  padding: 36px 32px;
  background: rgba(255,255,255,0.03);
  transition: border-color 0.25s, background 0.25s, transform 0.25s;
}
.price-card:hover {
  border-color: rgba(46,134,222,0.4);
  background: rgba(46,134,222,0.06);
  transform: translateY(-4px);
}

.price-card.featured {
  border-color: var(--blue-bright);
  background: rgba(46,134,222,0.1);
  position: relative;
}

.featured-badge {
  position: absolute;
  top: -12px; left: 50%; transform: translateX(-50%);
  background: var(--blue-bright);
  color: var(--white);
  font-size: 11px;
  font-weight: 500;
  padding: 4px 14px;
  border-radius: 100px;
  white-space: nowrap;
  letter-spacing: 0.05em;
}

.price-name {
  font-family: var(--font-display);
  font-size: 18px;
  font-weight: 700;
  color: var(--white);
  margin-bottom: 8px;
  letter-spacing: -0.3px;
}

.price-desc {
  font-size: 13px;
  color: rgba(255,255,255,0.45);
  margin-bottom: 28px;
  line-height: 1.5;
}

.price-amount { margin-bottom: 28px; }

.price-amount .currency {
  font-size: 18px;
  font-weight: 500;
  color: var(--blue-light);
  vertical-align: top;
  margin-top: 8px;
  display: inline-block;
}

.price-amount .number {
  font-family: var(--font-display);
  font-size: 48px;
  font-weight: 800;
  color: var(--white);
  letter-spacing: -2px;
  line-height: 1;
}

.price-amount .period {
  font-size: 13px;
  color: rgba(255,255,255,0.4);
  margin-left: 4px;
}

.price-features {
  list-style: none;
  margin-bottom: 32px;
}

.price-features li {
  font-size: 14px;
  color: rgba(255,255,255,0.65);
  padding: 8px 0;
  border-bottom: 1px solid rgba(255,255,255,0.05);
  display: flex;
  align-items: center;
  gap: 10px;
}
.price-features li::before {
  content: '✓';
  color: var(--blue-bright);
  font-weight: 700;
  font-size: 13px;
  flex-shrink: 0;
}

.price-btn {
  display: block;
  text-align: center;
  padding: 13px;
  border-radius: 100px;
  font-size: 14px;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.2s;
  border: 1px solid rgba(255,255,255,0.15);
  color: rgba(255,255,255,0.7);
  background: transparent;
}
.price-btn:hover {
  border-color: var(--blue-bright);
  color: var(--white);
  background: rgba(46,134,222,0.1);
}

.price-card.featured .price-btn {
  background: var(--blue-bright);
  border-color: var(--blue-bright);
  color: var(--white);
  box-shadow: 0 0 20px rgba(46,134,222,0.4);
}
.price-card.featured .price-btn:hover {
  background: #1a77d4;
  box-shadow: 0 0 30px rgba(46,134,222,0.6);
}

/* ── HOW IT WORKS ── */
.how {
  padding: 100px 40px;
  background: var(--white);
  color: var(--ink);
}

.how .section-title { color: var(--ink); }

.steps {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
  margin-top: 60px;
  position: relative;
}

.steps::before {
  content: '';
  position: absolute;
  top: 28px; left: calc(12.5% + 20px); right: calc(12.5% + 20px);
  height: 1px;
  background: linear-gradient(90deg, var(--blue-pale), var(--blue-light), var(--blue-pale));
}

.step {
  padding: 0 24px;
  text-align: center;
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.5s, transform 0.5s;
}

.step.visible {
  opacity: 1;
  transform: translateY(0);
}

.step-num {
  width: 56px; height: 56px;
  border-radius: 50%;
  background: var(--white);
  border: 2px solid var(--blue-light);
  display: flex; align-items: center; justify-content: center;
  margin: 0 auto 24px;
  font-family: var(--font-display);
  font-size: 20px;
  font-weight: 800;
  color: var(--blue-mid);
  position: relative; z-index: 1;
  transition: background 0.3s, border-color 0.3s;
}

.step:hover .step-num {
  background: var(--blue-pale);
  border-color: var(--blue-bright);
}

.step h4 {
  font-family: var(--font-display);
  font-size: 16px;
  font-weight: 700;
  color: var(--ink);
  margin-bottom: 10px;
  letter-spacing: -0.3px;
}

.step p {
  font-size: 13px;
  line-height: 1.6;
  color: var(--ink-muted);
}

/* ── CTA ── */
.cta-section {
  padding: 100px 40px;
  background: var(--blue-deep);
  text-align: center;
  position: relative;
  overflow: hidden;
}

.cta-section::before {
  content: '';
  position: absolute; inset: 0;
  background: radial-gradient(ellipse 60% 80% at 50% 50%, rgba(46,134,222,0.3) 0%, transparent 70%);
}

.cta-section h2 {
  font-family: var(--font-display);
  font-size: clamp(40px, 5vw, 72px);
  font-weight: 800;
  color: var(--white);
  letter-spacing: -2px;
  line-height: 1.05;
  margin-bottom: 20px;
  position: relative; z-index: 1;
}

.cta-section p {
  font-size: 17px;
  font-weight: 300;
  color: rgba(255,255,255,0.65);
  margin-bottom: 40px;
  position: relative; z-index: 1;
}

.cta-section .btn-primary {
  font-size: 16px;
  padding: 16px 36px;
  position: relative; z-index: 1;
}

/* ── FOOTER ── */
footer {
  padding: 40px;
  background: var(--ink);
  border-top: 1px solid rgba(255,255,255,0.06);
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.footer-logo {
  font-family: var(--font-display);
  font-size: 18px;
  font-weight: 800;
  color: var(--white);
  letter-spacing: -0.5px;
}
.footer-logo span { color: var(--blue-bright); }

footer p {
  font-size: 13px;
  color: rgba(255,255,255,0.3);
}

/* ── ANIMATIONS ── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes pulse {
  0%,100% { opacity: 1; transform: scale(1); }
  50% { opacity: 0.5; transform: scale(0.7); }
}

/* ── RESPONSIVE ── */
@media (max-width: 768px) {
  nav { padding: 16px 20px; }
  .nav-links { display: none; }
  .hero { padding: 100px 20px 60px; }
  .hero h1 { letter-spacing: -2px; }
  .hero-stats { gap: 28px; flex-wrap: wrap; }
  .services { padding: 60px 20px; }
  .services-grid { grid-template-columns: 1fr; }
  .pricing { padding: 60px 20px; }
  .pricing-grid { grid-template-columns: 1fr; }
  .how { padding: 60px 20px; }
  .steps { grid-template-columns: 1fr 1fr; gap: 40px; }
  .steps::before { display: none; }
  .cta-section { padding: 60px 20px; }
  footer { flex-direction: column; gap: 12px; text-align: center; padding: 30px 20px; }
}

- JavaScript vanilla (IntersectionObserver, contadores)
- Google Fonts: Syne + DM Sans

---
Hecho con 💙 por ContentPro
