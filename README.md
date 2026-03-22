<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Roots & Rain — South African Gardening</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Nunito:wght@300;400;600;700&family=DM+Serif+Display:ital@0;1&family=Pinyon+Script&family=Great+Vibes&display=swap" rel="stylesheet">
<style>
  :root {
    --soil: #3d2b1f;
    --clay: #7a4028;
    --terracotta: #c2603c;
    --sand: #e8d5b0;
    --cream: #faf5eb;
    --sage: #6b7c5c;
    --fern: #4a6741;
    --moss: #2d4a2a;
    --gold: #c8973a;
    --sky: #8fb4c8;
    --protea: #b8435a;
    --lavender-sa: #9b7fa8;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background-color: var(--cream);
    color: var(--soil);
    font-family: 'Nunito', sans-serif;
    overflow-x: hidden;
  }

  /* ─── NAV ─── */
  nav {
    position: fixed; top: 0; width: 100%; z-index: 100;
    background: rgba(250,245,235,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(61,43,31,0.12);
    padding: 0 2rem;
    display: flex; align-items: center; justify-content: space-between;
    height: 64px;
  }
  .nav-logo {
    font-family: 'Great Vibes', cursive;
    font-size: 2rem;
    letter-spacing: 0.02em;
    line-height: 1;
    display: flex;
    align-items: center;
    gap: 0.3rem;
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
  }
  .nav-logo .floral-icon { font-size: 1.2rem; line-height: 1; }
  .nav-logo .word-roots { color: #2e7d32; }
  .nav-logo .word-amp { color: #1a1a1a; }
  .nav-logo .word-rain { color: #00acc1; }
  .nav-links { display: flex; gap: 2rem; list-style: none; }
  .nav-links a {
    text-decoration: none;
    color: var(--soil);
    font-size: 0.85rem;
    font-weight: 600;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--terracotta); }

  /* ─── HERO ─── */
  .hero {
    min-height: 100vh;
    background: linear-gradient(180deg, #b8dff5 0%, #d6eefc 40%, #e8f7ff 70%, #c8e8b8 100%);
    position: relative;
    display: flex; align-items: center;
    overflow: hidden;
    padding-top: 64px;
  }
  .hero-bg {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse at 70% 10%, rgba(255,255,255,0.5) 0%, transparent 45%),
      radial-gradient(ellipse at 20% 90%, rgba(150,210,120,0.35) 0%, transparent 50%);
  }

  /* Clouds */
  .hero-cloud {
    position: absolute;
    background: white;
    border-radius: 50px;
    opacity: 0.75;
    pointer-events: none;
  }
  .hero-cloud::before, .hero-cloud::after {
    content: '';
    position: absolute;
    background: white;
    border-radius: 50%;
  }
  .cloud1 { width: 120px; height: 38px; top: 12%; left: 8%; animation: cloudDrift 18s linear infinite; }
  .cloud1::before { width: 60px; height: 60px; top: -30px; left: 15px; }
  .cloud1::after  { width: 40px; height: 40px; top: -20px; left: 50px; }
  .cloud2 { width: 90px; height: 28px; top: 22%; left: 55%; animation: cloudDrift 24s linear infinite 4s; }
  .cloud2::before { width: 45px; height: 45px; top: -22px; left: 10px; }
  .cloud2::after  { width: 35px; height: 35px; top: -14px; left: 38px; }
  .cloud3 { width: 70px; height: 22px; top: 8%; left: 75%; animation: cloudDrift 20s linear infinite 9s; }
  .cloud3::before { width: 35px; height: 35px; top: -18px; left: 8px; }
  .cloud3::after  { width: 28px; height: 28px; top: -12px; left: 30px; }

  @keyframes cloudDrift {
    from { transform: translateX(-20px); }
    to   { transform: translateX(30px); }
  }

  /* Animated bees */
  .bee {
    position: absolute; font-size: 1.6rem;
    pointer-events: none; z-index: 3;
    animation: beeFloat linear infinite;
    filter: drop-shadow(0 2px 4px rgba(0,0,0,0.15));
  }
  .bee1 { top: 18%; left: 60%; animation-duration: 6s; animation-delay: 0s; }
  .bee2 { top: 38%; left: 78%; animation-duration: 7.5s; animation-delay: 1.5s; }
  .bee3 { top: 60%; left: 65%; animation-duration: 5.5s; animation-delay: 3s; }
  .bee4 { top: 25%; left: 45%; animation-duration: 8s; animation-delay: 0.8s; }

  @keyframes beeFloat {
    0%   { transform: translate(0,0) rotate(0deg); }
    20%  { transform: translate(14px, -18px) rotate(12deg); }
    40%  { transform: translate(28px, 6px) rotate(-8deg); }
    60%  { transform: translate(10px, 20px) rotate(15deg); }
    80%  { transform: translate(-12px, 8px) rotate(-10deg); }
    100% { transform: translate(0,0) rotate(0deg); }
  }

  /* Flowers scattered right side */
  .hero-flowers {
    position: absolute; right: 0; top: 0; bottom: 0;
    width: 52%; pointer-events: none; z-index: 1;
  }

  /* Ground strip */
  .hero-ground {
    position: absolute; bottom: 0; left: 0; right: 0;
    height: 120px; pointer-events: none; z-index: 1;
    background: linear-gradient(180deg, transparent 0%, rgba(80,140,60,0.3) 60%, rgba(60,110,40,0.55) 100%);
  }

  .hero-content {
    position: relative; z-index: 4;
    padding: 4rem 8% 4rem 8%;
    max-width: 700px;
    animation: fadeUp 1s ease both;
  }
  .hero-eyebrow {
    font-size: 0.75rem; letter-spacing: 0.2em;
    text-transform: uppercase; color: #2a6e1a;
    font-weight: 700; margin-bottom: 1.2rem;
    text-shadow: 0 1px 3px rgba(255,255,255,0.7);
  }
  .hero h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(3rem, 7vw, 6rem);
    font-weight: 900;
    line-height: 1.0;
    color: #1a5c0e;
    margin-bottom: 1.5rem;
    text-shadow: 0 2px 12px rgba(255,255,255,0.6);
  }
  .hero h1 em {
    font-style: italic;
    color: #2e8c18;
    display: block;
  }
  .hero p {
    color: #1e4d12;
    font-size: 1.15rem;
    line-height: 1.75;
    max-width: 500px;
    margin-bottom: 2.5rem;
    text-shadow: 0 1px 6px rgba(255,255,255,0.5);
  }
  .hero-cta {
    display: inline-flex; gap: 1rem; flex-wrap: wrap;
  }
  .btn {
    padding: 0.85rem 2rem;
    border-radius: 50px;
    font-family: 'Nunito', sans-serif;
    font-weight: 700;
    font-size: 0.9rem;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    cursor: pointer;
    border: 2px solid transparent;
    text-decoration: none;
    transition: all 0.25s ease;
    display: inline-block;
  }
  .btn-primary { background: var(--terracotta); color: white; }
  .btn-primary:hover { background: var(--clay); transform: translateY(-2px); }
  .btn-outline { border-color: var(--sand); color: var(--sand); }
  .btn-outline:hover { background: var(--sand); color: var(--soil); transform: translateY(-2px); }

  .hero-stats {
    position: absolute; bottom: 2.5rem; right: 8%;
    display: flex; gap: 3rem;
    animation: fadeUp 1.2s 0.3s ease both;
  }
  .stat { text-align: center; }
  .stat-num {
    font-family: 'Playfair Display', serif;
    font-size: 2.2rem; font-weight: 900;
    color: #1a5c0e; display: block;
    text-shadow: 0 1px 8px rgba(255,255,255,0.6);
  }
  .stat-label {
    font-size: 0.72rem; letter-spacing: 0.12em;
    text-transform: uppercase; color: #2a6e1a;
  }

  /* ─── SECTION COMMON ─── */
  section { padding: 5rem 8%; }
  .section-tag {
    display: inline-block;
    font-size: 0.72rem; letter-spacing: 0.18em;
    text-transform: uppercase; font-weight: 700;
    color: var(--terracotta);
    border-bottom: 2px solid var(--terracotta);
    padding-bottom: 0.2rem;
    margin-bottom: 1rem;
  }
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: clamp(2rem, 4vw, 3rem);
    line-height: 1.15;
    color: var(--moss);
    margin-bottom: 1rem;
  }
  .section-intro {
    color: var(--clay);
    font-size: 1.05rem;
    line-height: 1.75;
    max-width: 650px;
    margin-bottom: 3rem;
  }

  /* ─── INDIGENOUS PLANTS ─── */
  #plants { background: var(--cream); }

  .plants-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1.5rem;
  }
  .plant-card {
    background: white;
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 2px 20px rgba(61,43,31,0.08);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    cursor: pointer;
  }
  .plant-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 40px rgba(61,43,31,0.15);
  }
  .plant-icon {
    height: 200px;
    display: flex; align-items: center; justify-content: center;
    font-size: 4.5rem;
    position: relative;
    overflow: hidden;
    background: #e8f0e0;
  }
  .plant-icon img {
    width: 100%; height: 100%;
    object-fit: cover;
    transition: transform 0.4s ease;
    display: block;
  }
  .plant-card:hover .plant-icon img { transform: scale(1.05); }
  .plant-icon .img-placeholder {
    position: absolute; inset: 0;
    display: flex; flex-direction: column;
    align-items: center; justify-content: center;
    background: linear-gradient(135deg, #e8f0e0, #d5e5c0);
    font-size: 2.5rem;
    gap: 0.5rem;
  }
  .plant-icon .img-placeholder span {
    font-size: 0.7rem;
    color: var(--sage); font-weight: 600;
    letter-spacing: 0.05em;
    text-transform: uppercase;
  }
  .plant-icon::after {
    content: '';
    position: absolute; inset: 0;
    background: linear-gradient(180deg, transparent 55%, rgba(0,0,0,0.18) 100%);
    pointer-events: none;
    z-index: 1;
  }
  .photo-credit {
    position: absolute; bottom: 4px; right: 6px;
    font-size: 0.6rem; color: rgba(255,255,255,0.75);
    z-index: 2; background: rgba(0,0,0,0.3);
    padding: 1px 5px; border-radius: 3px;
  }
  .plant-body { padding: 1.4rem; }
  .plant-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem; font-weight: 700;
    color: var(--moss); margin-bottom: 0.25rem;
  }
  .plant-scientific {
    font-size: 0.78rem; color: var(--sage);
    font-style: italic; margin-bottom: 0.8rem;
  }
  .plant-desc {
    font-size: 0.88rem; color: var(--soil);
    line-height: 1.6; margin-bottom: 1rem;
  }
  .plant-tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
  .tag {
    font-size: 0.72rem; font-weight: 700;
    padding: 0.25rem 0.75rem;
    border-radius: 50px;
    letter-spacing: 0.04em;
  }
  .tag-water { background: #dbeeff; color: #2666a0; }
  .tag-sun { background: #fff3d0; color: #9b6800; }
  .tag-region { background: #e8f0e0; color: var(--moss); }
  .tag-type { background: #fde8e0; color: var(--clay); }

  /* ─── POLLINATORS ─── */
  #pollinators { background: #f5f0e8; }

  .pollinator-layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }
  .pollinator-card {
    background: white;
    border-radius: 20px;
    padding: 2rem;
    display: flex; gap: 1.5rem; align-items: flex-start;
    box-shadow: 0 2px 16px rgba(61,43,31,0.07);
    transition: transform 0.25s;
  }
  .pollinator-card:hover { transform: translateY(-4px); }
  .pollinator-card.featured {
    grid-column: span 2;
    background: var(--moss);
    color: var(--sand);
    flex-direction: row;
    align-items: center;
  }
  .pollinator-card.featured .poll-title { color: var(--gold); }
  .pollinator-card.featured .poll-desc { color: rgba(232,213,176,0.85); }
  .pollinator-card.featured .poll-fact { background: rgba(255,255,255,0.1); color: var(--sand); }
  .poll-emoji {
    font-size: 3.5rem; flex-shrink: 0;
    width: 100px; height: 100px;
    border-radius: 50%;
    overflow: hidden;
    display: flex; align-items: center; justify-content: center;
    background: var(--sand);
    position: relative;
  }
  .poll-emoji img {
    width: 100%; height: 100%;
    object-fit: cover;
    border-radius: 50%;
  }
  .poll-fallback { font-size: 3rem; }
  .pollinator-card.featured .poll-emoji {
    width: 130px; height: 130px; flex-shrink: 0;
  }
  .poll-title {
    font-family: 'Playfair Display', serif;
    font-size: 1.25rem; color: var(--moss);
    margin-bottom: 0.5rem;
  }
  .poll-desc { font-size: 0.9rem; line-height: 1.65; color: var(--soil); margin-bottom: 0.75rem; }
  .poll-fact {
    font-size: 0.8rem; font-weight: 700;
    background: var(--sand); color: var(--clay);
    padding: 0.4rem 0.9rem; border-radius: 50px;
    display: inline-block;
  }

  /* ─── COMPANION PLANTING ─── */
  #companions { background: var(--cream); }

  .companion-intro-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    margin-bottom: 2.5rem;
  }

  .companion-table-wrap {
    overflow-x: auto;
    border-radius: 16px;
    box-shadow: 0 4px 24px rgba(61,43,31,0.1);
  }
  table { width: 100%; border-collapse: collapse; background: white; }
  thead { background: var(--moss); }
  th {
    padding: 1rem 1.2rem;
    font-size: 0.75rem; letter-spacing: 0.12em;
    text-transform: uppercase; font-weight: 700;
    color: var(--sand); text-align: left;
  }
  td { padding: 0.95rem 1.2rem; font-size: 0.9rem; border-bottom: 1px solid rgba(61,43,31,0.07); }
  tr:last-child td { border-bottom: none; }
  tr:hover td { background: #faf5eb; }
  .friend { color: var(--fern); font-weight: 700; }
  .foe { color: var(--protea); font-weight: 700; }
  .benefit-chip {
    font-size: 0.78rem; background: var(--sand);
    padding: 0.2rem 0.7rem; border-radius: 50px;
    color: var(--soil); font-weight: 600;
  }

  .tip-box {
    background: linear-gradient(135deg, var(--fern), var(--moss));
    color: white; border-radius: 16px; padding: 1.8rem 2rem;
  }
  .tip-box h3 {
    font-family: 'Playfair Display', serif;
    font-size: 1.2rem; color: var(--gold); margin-bottom: 0.75rem;
  }
  .tip-box ul { list-style: none; }
  .tip-box li {
    font-size: 0.88rem; line-height: 1.65;
    padding: 0.35rem 0; display: flex; gap: 0.6rem;
    border-bottom: 1px solid rgba(255,255,255,0.12);
  }
  .tip-box li:last-child { border-bottom: none; }

  /* ─── SOIL TYPES ─── */
  #soil { background: #3d2b1f; }
  #soil .section-tag { color: var(--gold); border-color: var(--gold); }
  #soil .section-title { color: var(--sand); }
  #soil .section-intro { color: rgba(232,213,176,0.8); }

  .soil-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 1.2rem;
  }
  .soil-card {
    border-radius: 16px; padding: 1.8rem;
    transition: transform 0.25s;
    position: relative; overflow: hidden;
  }
  .soil-card:hover { transform: translateY(-5px); }
  .soil-card::before {
    content: '';
    position: absolute; top: -30px; right: -30px;
    width: 100px; height: 100px;
    border-radius: 50%;
    background: rgba(255,255,255,0.06);
  }
  .soil-emoji { font-size: 2.5rem; margin-bottom: 1rem; display: block; }
  .soil-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.15rem; font-weight: 700;
    margin-bottom: 0.5rem;
  }
  .soil-desc { font-size: 0.85rem; line-height: 1.6; opacity: 0.85; margin-bottom: 1rem; }
  .soil-props { display: flex; flex-direction: column; gap: 0.4rem; }
  .soil-prop { font-size: 0.8rem; display: flex; align-items: center; gap: 0.5rem; }
  .prop-dot {
    width: 8px; height: 8px; border-radius: 50%;
    flex-shrink: 0;
  }

  /* Soil colors */
  .soil-card.sandy { background: linear-gradient(135deg, #7a6040, #5e4828); color: var(--sand); }
  .soil-card.clay-soil { background: linear-gradient(135deg, #8a3c20, #6b2a12); color: #f5d5c0; }
  .soil-card.loam { background: linear-gradient(135deg, #4a5a30, #334020); color: #d8e8c0; }
  .soil-card.fynbos { background: linear-gradient(135deg, #5a4a70, #3d3050); color: #e0d8f0; }
  .soil-card.compost { background: linear-gradient(135deg, #3a5a2a, #253818); color: #c8e8b0; }

  /* soil improvers */
  .soil-improve-grid {
    display: grid; grid-template-columns: 1fr 1fr 1fr;
    gap: 1rem; margin-top: 2.5rem;
  }
  .improve-card {
    background: rgba(255,255,255,0.06);
    border: 1px solid rgba(232,213,176,0.15);
    border-radius: 12px; padding: 1.4rem;
    color: var(--sand);
  }
  .improve-card h4 {
    font-family: 'Playfair Display', serif;
    font-size: 1rem; color: var(--gold); margin-bottom: 0.5rem;
  }
  .improve-card p { font-size: 0.83rem; line-height: 1.6; opacity: 0.8; }

  /* ─── SEASONS ─── */
  #seasons { background: #f5f0e8; }

  .seasons-grid {
    display: grid; grid-template-columns: repeat(4, 1fr);
    gap: 1rem;
  }
  .season-card {
    border-radius: 20px; overflow: hidden;
    box-shadow: 0 4px 20px rgba(61,43,31,0.1);
  }
  .season-header {
    padding: 1.8rem 1.5rem 1.2rem;
    text-align: center;
  }
  .season-icon { font-size: 3rem; margin-bottom: 0.5rem; display: block; }
  .season-name {
    font-family: 'Playfair Display', serif;
    font-size: 1.5rem; font-weight: 900;
    margin-bottom: 0.15rem;
  }
  .season-months { font-size: 0.75rem; letter-spacing: 0.1em; opacity: 0.75; font-weight: 600; text-transform: uppercase; }
  .season-body { background: white; padding: 1.5rem; }
  .season-section-title {
    font-size: 0.7rem; letter-spacing: 0.12em;
    text-transform: uppercase; font-weight: 700;
    color: var(--terracotta); margin-bottom: 0.6rem; margin-top: 0.8rem;
  }
  .season-section-title:first-child { margin-top: 0; }
  .season-list { list-style: none; }
  .season-list li {
    font-size: 0.85rem; color: var(--soil);
    padding: 0.3rem 0;
    border-bottom: 1px solid rgba(61,43,31,0.06);
    display: flex; align-items: center; gap: 0.5rem;
  }
  .season-list li::before { content: '•'; color: var(--sage); font-weight: 900; }

  /* Season color themes */
  .season-card.summer .season-header { background: linear-gradient(135deg, #c2603c, #e8973a); color: white; }
  .season-card.autumn .season-header { background: linear-gradient(135deg, #8a5030, #6a3818); color: #f5d5b0; }
  .season-card.winter .season-header { background: linear-gradient(135deg, #4a6080, #2d3d58); color: #c8dce8; }
  .season-card.spring .season-header { background: linear-gradient(135deg, #4a6741, #2d4a2a); color: #c8e8b0; }

  /* ─── TIPS BANNER ─── */
  .tip-banner {
    background: var(--terracotta);
    padding: 4rem 8%;
    text-align: center;
  }
  .tip-banner h2 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(1.8rem, 4vw, 2.8rem);
    color: white; margin-bottom: 1rem;
  }
  .tip-banner h2 em { font-style: italic; color: var(--sand); }
  .tip-banner p { color: rgba(255,255,255,0.85); font-size: 1.05rem; max-width: 600px; margin: 0 auto 2rem; line-height: 1.7; }
  .tips-row { display: flex; gap: 2rem; justify-content: center; flex-wrap: wrap; margin-top: 2.5rem; }
  .tip-item {
    background: rgba(255,255,255,0.12);
    backdrop-filter: blur(8px);
    border-radius: 16px; padding: 1.5rem 1.8rem;
    text-align: left; flex: 1; min-width: 200px; max-width: 280px;
    border: 1px solid rgba(255,255,255,0.2);
  }
  .tip-item-icon { font-size: 2rem; margin-bottom: 0.75rem; display: block; }
  .tip-item h4 { font-family: 'Playfair Display', serif; font-size: 1.05rem; color: white; margin-bottom: 0.4rem; }
  .tip-item p { font-size: 0.83rem; color: rgba(255,255,255,0.8); line-height: 1.55; }

  /* ─── FOOTER ─── */
  footer {
    background: var(--soil); color: var(--sand);
    padding: 3rem 8%; text-align: center;
  }
  footer .foot-logo {
    font-family: 'Great Vibes', cursive;
    font-size: 2.8rem;
    color: var(--gold);
    margin-bottom: 0.75rem;
    line-height: 1.2;
  }
  footer p { font-size: 0.85rem; opacity: 0.7; line-height: 1.7; max-width: 550px; margin: 0 auto; }
  footer .foot-links { display: flex; justify-content: center; gap: 2rem; margin-top: 1.5rem; }
  footer a { color: rgba(232,213,176,0.6); text-decoration: none; font-size: 0.8rem; letter-spacing: 0.08em; text-transform: uppercase; transition: color 0.2s; }
  footer a:hover { color: var(--gold); }

  /* ─── ANIMATIONS ─── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .reveal {
    opacity: 0; transform: translateY(24px);
    transition: opacity 0.7s ease, transform 0.7s ease;
  }
  .reveal.visible { opacity: 1; transform: translateY(0); }

  /* ─── RESPONSIVE ─── */
  @media (max-width: 900px) {
    .pollinator-layout { grid-template-columns: 1fr; }
    .pollinator-card.featured { grid-column: span 1; }
    .seasons-grid { grid-template-columns: repeat(2, 1fr); }
    .companion-intro-grid { grid-template-columns: 1fr; }
    .soil-improve-grid { grid-template-columns: 1fr 1fr; }
    .hero-stats { position: static; justify-content: flex-start; padding-top: 2rem; }
    nav .nav-links { display: none; }
  }
  @media (max-width: 600px) {
    section { padding: 3rem 5%; }
    .seasons-grid { grid-template-columns: 1fr; }
    .soil-improve-grid { grid-template-columns: 1fr; }
    .hero-content { padding: 3rem 5% 3rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo"><span class="floral-icon">🌸</span> <span class="word-roots">Roots</span> <span class="word-amp">&amp;</span> <span class="word-rain">Rain</span> <span class="floral-icon">🌿</span></div>
  <ul class="nav-links">
    <li><a href="#plants">Plants</a></li>
    <li><a href="#pollinators">Pollinators</a></li>
    <li><a href="#companions">Companions</a></li>
    <li><a href="#soil">Soil</a></li>
    <li><a href="#seasons">Seasons</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>

  <!-- Clouds -->
  <div class="hero-cloud cloud1"></div>
  <div class="hero-cloud cloud2"></div>
  <div class="hero-cloud cloud3"></div>

  <!-- Animated bees -->
  <div class="bee bee1">🐝</div>
  <div class="bee bee2">🐝</div>
  <div class="bee bee3">🐝</div>
  <div class="bee bee4">🐝</div>

  <!-- Flower garden SVG (right side) -->
  <svg class="hero-flowers" viewBox="0 0 520 900" xmlns="http://www.w3.org/2000/svg">
    <!-- Sky backdrop wash -->
    <defs>
      <radialGradient id="glowY" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stop-color="#ffe066" stop-opacity="0.9"/>
        <stop offset="100%" stop-color="#ffb300" stop-opacity="0"/>
      </radialGradient>
      <radialGradient id="glowP" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stop-color="#ff6b9d" stop-opacity="0.9"/>
        <stop offset="100%" stop-color="#e91e8c" stop-opacity="0"/>
      </radialGradient>
      <radialGradient id="glowO" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stop-color="#ff8c42" stop-opacity="0.95"/>
        <stop offset="100%" stop-color="#e65c00" stop-opacity="0"/>
      </radialGradient>
      <radialGradient id="glowR" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stop-color="#ff4444" stop-opacity="0.9"/>
        <stop offset="100%" stop-color="#cc0000" stop-opacity="0"/>
      </radialGradient>
      <radialGradient id="glowW" cx="50%" cy="50%" r="50%">
        <stop offset="0%" stop-color="white" stop-opacity="1"/>
        <stop offset="100%" stop-color="#e0e0e0" stop-opacity="0"/>
      </radialGradient>
    </defs>

    <!-- Stems -->
    <line x1="120" y1="900" x2="120" y2="560" stroke="#3a7a28" stroke-width="5" stroke-linecap="round"/>
    <line x1="240" y1="900" x2="240" y2="480" stroke="#2d6020" stroke-width="6" stroke-linecap="round"/>
    <line x1="350" y1="900" x2="350" y2="530" stroke="#4a8a30" stroke-width="5" stroke-linecap="round"/>
    <line x1="450" y1="900" x2="450" y2="590" stroke="#3a7a28" stroke-width="4" stroke-linecap="round"/>
    <line x1="60"  y1="900" x2="60"  y2="640" stroke="#2d6020" stroke-width="3" stroke-linecap="round"/>
    <line x1="480" y1="900" x2="480" y2="660" stroke="#4a8a30" stroke-width="3" stroke-linecap="round"/>
    <line x1="180" y1="900" x2="180" y2="620" stroke="#3a7a28" stroke-width="3" stroke-linecap="round"/>
    <line x1="310" y1="900" x2="310" y2="600" stroke="#2d6020" stroke-width="4" stroke-linecap="round"/>

    <!-- Leaves -->
    <ellipse cx="105" cy="700" rx="28" ry="12" fill="#4a8a30" transform="rotate(-40 105 700)" opacity="0.9"/>
    <ellipse cx="135" cy="680" rx="24" ry="10" fill="#3a7020" transform="rotate(35 135 680)" opacity="0.9"/>
    <ellipse cx="225" cy="650" rx="32" ry="13" fill="#4a8a30" transform="rotate(-30 225 650)" opacity="0.9"/>
    <ellipse cx="260" cy="620" rx="28" ry="11" fill="#3a7020" transform="rotate(45 260 620)" opacity="0.9"/>
    <ellipse cx="335" cy="690" rx="26" ry="11" fill="#4a8a30" transform="rotate(-25 335 690)" opacity="0.9"/>
    <ellipse cx="365" cy="720" rx="22" ry="9"  fill="#3a7020" transform="rotate(50 365 720)"  opacity="0.9"/>

    <!-- Big Sunflower (center) -->
    <!-- petals -->
    <g transform="translate(240,480)">
      <ellipse cx="0" cy="-48" rx="14" ry="30" fill="#ffe033" transform="rotate(0)"/>
      <ellipse cx="0" cy="-48" rx="14" ry="30" fill="#ffd020" transform="rotate(45)"/>
      <ellipse cx="0" cy="-48" rx="14" ry="30" fill="#ffe033" transform="rotate(90)"/>
      <ellipse cx="0" cy="-48" rx="14" ry="30" fill="#ffd020" transform="rotate(135)"/>
      <ellipse cx="0" cy="-48" rx="14" ry="30" fill="#ffe033" transform="rotate(180)"/>
      <ellipse cx="0" cy="-48" rx="14" ry="30" fill="#ffd020" transform="rotate(225)"/>
      <ellipse cx="0" cy="-48" rx="14" ry="30" fill="#ffe033" transform="rotate(270)"/>
      <ellipse cx="0" cy="-48" rx="14" ry="30" fill="#ffd020" transform="rotate(315)"/>
      <!-- centre -->
      <circle cx="0" cy="0" r="26" fill="#7b3f00"/>
      <circle cx="0" cy="0" r="18" fill="#5c2d00"/>
    </g>

    <!-- Protea (left) -->
    <g transform="translate(120,555)">
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#d44470" transform="rotate(0)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#c03560" transform="rotate(30)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#d44470" transform="rotate(60)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#c03560" transform="rotate(90)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#d44470" transform="rotate(120)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#c03560" transform="rotate(150)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#d44470" transform="rotate(180)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#c03560" transform="rotate(210)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#d44470" transform="rotate(240)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#c03560" transform="rotate(270)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#d44470" transform="rotate(300)"/>
      <ellipse cx="0" cy="-35" rx="10" ry="38" fill="#c03560" transform="rotate(330)"/>
      <circle cx="0" cy="0" r="22" fill="#ffe4b0"/>
      <circle cx="0" cy="0" r="14" fill="#ffd080"/>
    </g>

    <!-- Orange Cape Honeysuckle trumpet flowers (right) -->
    <g transform="translate(350,525)">
      <ellipse cx="0" cy="-30" rx="12" ry="32" fill="#ff7c2a" transform="rotate(0)"/>
      <ellipse cx="0" cy="-30" rx="12" ry="32" fill="#e86018" transform="rotate(60)"/>
      <ellipse cx="0" cy="-30" rx="12" ry="32" fill="#ff7c2a" transform="rotate(120)"/>
      <ellipse cx="0" cy="-30" rx="12" ry="32" fill="#e86018" transform="rotate(180)"/>
      <ellipse cx="0" cy="-30" rx="12" ry="32" fill="#ff7c2a" transform="rotate(240)"/>
      <ellipse cx="0" cy="-30" rx="12" ry="32" fill="#e86018" transform="rotate(300)"/>
      <circle cx="0" cy="0" r="16" fill="#fff176"/>
    </g>

    <!-- Small daisy (far right) -->
    <g transform="translate(450,585)">
      <ellipse cx="0" cy="-22" rx="8" ry="22" fill="white" transform="rotate(0)"/>
      <ellipse cx="0" cy="-22" rx="8" ry="22" fill="#f0f0f0" transform="rotate(45)"/>
      <ellipse cx="0" cy="-22" rx="8" ry="22" fill="white" transform="rotate(90)"/>
      <ellipse cx="0" cy="-22" rx="8" ry="22" fill="#f0f0f0" transform="rotate(135)"/>
      <ellipse cx="0" cy="-22" rx="8" ry="22" fill="white" transform="rotate(180)"/>
      <ellipse cx="0" cy="-22" rx="8" ry="22" fill="#f0f0f0" transform="rotate(225)"/>
      <ellipse cx="0" cy="-22" rx="8" ry="22" fill="white" transform="rotate(270)"/>
      <ellipse cx="0" cy="-22" rx="8" ry="22" fill="#f0f0f0" transform="rotate(315)"/>
      <circle cx="0" cy="0" r="13" fill="#ffdb00"/>
    </g>

    <!-- Small lavender flower (tiny left) -->
    <g transform="translate(60,635)">
      <ellipse cx="0" cy="-18" rx="7" ry="18" fill="#c8a0e0" transform="rotate(0)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="18" fill="#b080d0" transform="rotate(60)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="18" fill="#c8a0e0" transform="rotate(120)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="18" fill="#b080d0" transform="rotate(180)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="18" fill="#c8a0e0" transform="rotate(240)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="18" fill="#b080d0" transform="rotate(300)"/>
      <circle cx="0" cy="0" r="10" fill="#ffe066"/>
    </g>

    <!-- Small red flower (inner right) -->
    <g transform="translate(480,655)">
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff4455" transform="rotate(0)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#e03040" transform="rotate(72)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff4455" transform="rotate(144)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#e03040" transform="rotate(216)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff4455" transform="rotate(288)"/>
      <circle cx="0" cy="0" r="10" fill="#fff176"/>
    </g>

    <!-- Small pink flower (inner) -->
    <g transform="translate(180,615)">
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff80b0" transform="rotate(0)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff5090" transform="rotate(60)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff80b0" transform="rotate(120)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff5090" transform="rotate(180)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff80b0" transform="rotate(240)"/>
      <ellipse cx="0" cy="-18" rx="7" ry="20" fill="#ff5090" transform="rotate(300)"/>
      <circle cx="0" cy="0" r="10" fill="#ffe066"/>
    </g>

    <!-- Small yellow flower (inner) -->
    <g transform="translate(310,595)">
      <ellipse cx="0" cy="-16" rx="7" ry="18" fill="#ffe033" transform="rotate(0)"/>
      <ellipse cx="0" cy="-16" rx="7" ry="18" fill="#ffc000" transform="rotate(72)"/>
      <ellipse cx="0" cy="-16" rx="7" ry="18" fill="#ffe033" transform="rotate(144)"/>
      <ellipse cx="0" cy="-16" rx="7" ry="18" fill="#ffc000" transform="rotate(216)"/>
      <ellipse cx="0" cy="-16" rx="7" ry="18" fill="#ffe033" transform="rotate(288)"/>
      <circle cx="0" cy="0" r="10" fill="#7b3f00"/>
    </g>

    <!-- Grass / ground cover -->
    <rect x="0" y="840" width="520" height="60" fill="#4a8a30" opacity="0.5" rx="4"/>
    <ellipse cx="100" cy="845" rx="50" ry="20" fill="#3a7020" opacity="0.7"/>
    <ellipse cx="250" cy="848" rx="60" ry="18" fill="#4a8a30" opacity="0.6"/>
    <ellipse cx="400" cy="843" rx="55" ry="22" fill="#3a7020" opacity="0.7"/>
  </svg>

  <!-- Ground strip -->
  <div class="hero-ground"></div>

  <div class="hero-content">
    <p class="hero-eyebrow">South African Gardening Guide</p>
    <h1>Garden with the <em>Land.</em></h1>
    <p>Discover the rich diversity of South Africa's indigenous plants, essential pollinators, seasonal planting wisdom, and the soils that make our gardens thrive — from the Fynbos to the Bushveld.</p>
    <div class="hero-cta">
      <a href="#plants" class="btn btn-primary">Explore Plants</a>
      <a href="#seasons" class="btn btn-outline">Planting Calendar</a>
    </div>
    <div class="hero-stats">
      <div class="stat">
        <span class="stat-num">9</span>
        <span class="stat-label">Biomes</span>
      </div>
      <div class="stat">
        <span class="stat-num">22k+</span>
        <span class="stat-label">Plant Species</span>
      </div>
      <div class="stat">
        <span class="stat-num">860+</span>
        <span class="stat-label">Bird Pollinators</span>
      </div>
    </div>
  </div>
</section>

<!-- INDIGENOUS PLANTS -->
<section id="plants">
  <span class="section-tag">Indigenous Plants</span>
  <h2 class="section-title">Plants that belong<br>to this land</h2>
  <p class="section-intro">South Africa is one of the world's six floral kingdoms. Growing indigenous plants means less water, no fertiliser, and a garden buzzing with life. Here are some essential species to grow.</p>

  <div class="plants-grid">

    <div class="plant-card reveal">
      <div class="plant-icon" data-wiki="Protea_cynaroides">
        <div class="img-placeholder">🌺<span>Loading photo…</span></div>
      </div>
      <div class="plant-body">
        <div class="plant-name">Protea</div>
        <div class="plant-scientific">Protea cynaroides</div>
        <div class="plant-desc">South Africa's national flower and the jewel of the Fynbos. Spectacular blooms attract sunbirds and sugarbirds. Prefers acidic, well-drained soil and full sun.</div>
        <div class="plant-tags">
          <span class="tag tag-water">💧 Low water</span>
          <span class="tag tag-sun">☀️ Full sun</span>
          <span class="tag tag-region">Fynbos</span>
        </div>
      </div>
    </div>

    <div class="plant-card reveal">
      <div class="plant-icon" data-wiki="Osteospermum_ecklonis">
        <div class="img-placeholder">🌼<span>Loading photo…</span></div>
      </div>
      <div class="plant-body">
        <div class="plant-name">African Daisy</div>
        <div class="plant-scientific">Osteospermum ecklonis</div>
        <div class="plant-desc">Bold, cheerful daisies in white, purple, and orange. Incredibly drought-tolerant once established. Excellent ground cover and pollinator magnet throughout the year.</div>
        <div class="plant-tags">
          <span class="tag tag-water">💧 Drought-tolerant</span>
          <span class="tag tag-sun">☀️ Full sun</span>
          <span class="tag tag-region">Nationwide</span>
        </div>
      </div>
    </div>

    <div class="plant-card reveal">
      <div class="plant-icon" data-wiki="Agathosma_betulina">
        <div class="img-placeholder">🌿<span>Loading photo…</span></div>
      </div>
      <div class="plant-body">
        <div class="plant-name">Buchu</div>
        <div class="plant-scientific">Agathosma betulina</div>
        <div class="plant-desc">A fragrant, medicinal shrub beloved in Cape Malay cuisine and herbal remedies. Thrives in rocky, sandy soil. Also a top companion plant that repels certain pests.</div>
        <div class="plant-tags">
          <span class="tag tag-water">💧 Low water</span>
          <span class="tag tag-sun">☀️ Full sun</span>
          <span class="tag tag-region">Western Cape</span>
          <span class="tag tag-type">Medicinal</span>
        </div>
      </div>
    </div>

    <div class="plant-card reveal">
      <div class="plant-icon" data-wiki="Tecoma_capensis">
        <div class="img-placeholder">🧡<span>Loading photo…</span></div>
      </div>
      <div class="plant-body">
        <div class="plant-name">Cape Honeysuckle</div>
        <div class="plant-scientific">Tecoma capensis</div>
        <div class="plant-desc">Vivid orange trumpet flowers that sunbirds absolutely adore. Fast-growing, tough, and perfect for hedges or trellises. Blooms mainly in winter — a lifesaver for pollinators.</div>
        <div class="plant-tags">
          <span class="tag tag-water">💧 Low water</span>
          <span class="tag tag-sun">🌤️ Part–full sun</span>
          <span class="tag tag-region">Nationwide</span>
        </div>
      </div>
    </div>

    <div class="plant-card reveal">
      <div class="plant-icon" data-wiki="Salvia_africana-lutea">
        <div class="img-placeholder">💜<span>Loading photo…</span></div>
      </div>
      <div class="plant-body">
        <div class="plant-name">Wild Sage</div>
        <div class="plant-scientific">Salvia africana-lutea</div>
        <div class="plant-desc">Aromatic silver-grey foliage with rust-orange flowers. Supremely drought-hardy once established. Attracts bees, butterflies, and sunbirds while repelling aphids in the garden.</div>
        <div class="plant-tags">
          <span class="tag tag-water">💧 Very low water</span>
          <span class="tag tag-sun">☀️ Full sun</span>
          <span class="tag tag-region">Coastal & Inland</span>
        </div>
      </div>
    </div>

    <div class="plant-card reveal">
      <div class="plant-icon" data-wiki="Leonotis_leonurus">
        <div class="img-placeholder">🎋<span>Loading photo…</span></div>
      </div>
      <div class="plant-body">
        <div class="plant-name">Wild Dagga</div>
        <div class="plant-scientific">Leonotis leonurus</div>
        <div class="plant-desc">Tall spires of vivid orange flower whorls in autumn and winter. A favourite of sunbirds and bees. Grows in most soil types and handles both drought and seasonal rain.</div>
        <div class="plant-tags">
          <span class="tag tag-water">💧 Low water</span>
          <span class="tag tag-sun">☀️ Full sun</span>
          <span class="tag tag-region">Nationwide</span>
          <span class="tag tag-type">Medicinal</span>
        </div>
      </div>
    </div>

    <div class="plant-card reveal">
      <div class="plant-icon" data-wiki="Agapanthus_africanus">
        <div class="img-placeholder">💙<span>Loading photo…</span></div>
      </div>
      <div class="plant-body">
        <div class="plant-name">Agapanthus</div>
        <div class="plant-scientific">Agapanthus africanus</div>
        <div class="plant-desc">Iconic blue-purple globe flowers on tall stems, beloved in South African gardens. Excellent for borders, pots, and slopes. Very water-wise once established. Bees love it.</div>
        <div class="plant-tags">
          <span class="tag tag-water">💧 Moderate</span>
          <span class="tag tag-sun">🌤️ Full–part sun</span>
          <span class="tag tag-region">Western & E. Cape</span>
        </div>
      </div>
    </div>

    <div class="plant-card reveal">
      <div class="plant-icon" data-wiki="Portulacaria_afra">
        <div class="img-placeholder">🌱<span>Loading photo…</span></div>
      </div>
      <div class="plant-body">
        <div class="plant-name">Spekboom</div>
        <div class="plant-scientific">Portulacaria afra</div>
        <div class="plant-desc">Called the "miracle plant" — sequesters more carbon per hectare than the Amazon rainforest. Edible, succulent leaves. Extremely drought-hardy. A must-have for any SA garden.</div>
        <div class="plant-tags">
          <span class="tag tag-water">💧 Very low water</span>
          <span class="tag tag-sun">☀️ Full sun</span>
          <span class="tag tag-region">Eastern Cape</span>
          <span class="tag tag-type">Edible</span>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- POLLINATORS -->
<section id="pollinators">
  <span class="section-tag">Pollinators</span>
  <h2 class="section-title">Invite the<br>right visitors</h2>
  <p class="section-intro">South Africa's unique pollinator community evolved alongside its indigenous plants. Understanding who pollinates what helps you design a garden that feeds both wildlife and your table.</p>

  <div class="pollinator-layout">

    <div class="pollinator-card featured reveal">
      <div class="poll-emoji" data-wiki="Cape_sugarbird">
        <span class="poll-fallback">🐦</span>
      </div>
      <div>
        <div class="poll-title">Sunbirds — Nature's Helicopter</div>
        <div class="poll-desc">South Africa hosts over 20 sunbird species. These iridescent hoverers are the primary pollinators of proteas, aloes, and tubular flowers. The Cape Sugarbird (Promerops cafer) is uniquely co-evolved with Proteas — its long tail feathers brush pollen while feeding. Plant clusters of orange, red, and tubular flowers to attract them year-round.</div>
        <span class="poll-fact">🌺 Best plant: Cape Honeysuckle, Kniphofia, Aloe ferox</span>
      </div>
    </div>

    <div class="pollinator-card reveal">
      <div class="poll-emoji" data-wiki="Cape_honey_bee">
        <span class="poll-fallback">🐝</span>
      </div>
      <div>
        <div class="poll-title">Cape Honeybee</div>
        <div class="poll-desc">The African honeybee subspecies (Apis mellifera capensis) is found only in the Western Cape. More productive and resilient than European bees. Pollinates almost all flowering plants including vegetables and fruit trees.</div>
        <span class="poll-fact">🍯 Key plant: Lavender, Borage, Fennel</span>
      </div>
    </div>

    <div class="pollinator-card reveal">
      <div class="poll-emoji" data-wiki="Papilio_demodocus">
        <span class="poll-fallback">🦋</span>
      </div>
      <div>
        <div class="poll-title">Butterflies</div>
        <div class="poll-desc">Over 660 butterfly species recorded in SA. They prefer flat, open flowers in purples and yellows. The Citrus Swallowtail and Monarch are garden favourites. Host plant planting is crucial for caterpillar survival.</div>
        <span class="poll-fact">🌻 Key plant: Buddleja, Wild Dagga, Milkweed</span>
      </div>
    </div>

    <div class="pollinator-card reveal">
      <div class="poll-emoji" data-wiki="Episyrphus_balteatus">
        <span class="poll-fallback">🪲</span>
      </div>
      <div>
        <div class="poll-title">Hover Flies & Wasps</div>
        <div class="poll-desc">Often mistaken for bees, hover flies are underrated pollinators that visit shallow, open flowers. Parasitic wasps also pollinate while hunting pest insects — a double benefit for organic gardeners.</div>
        <span class="poll-fact">💐 Key plant: Dill, Coriander, Marigold</span>
      </div>
    </div>

    <div class="pollinator-card reveal">
      <div class="poll-emoji" data-wiki="Flower_chafer">
        <span class="poll-fallback">🐞</span>
      </div>
      <div>
        <div class="poll-title">Beetles</div>
        <div class="poll-desc">Many primitive SA flowers like Babiana and Watsonia evolved to be pollinated by beetles. They're attracted to strong scents and bowl-shaped white or cream flowers. Fascinating ancient relationship.</div>
        <span class="poll-fact">🌼 Key plant: Babiana, Watsonias, Eucomis</span>
      </div>
    </div>

    <div class="pollinator-card reveal">
      <div class="poll-emoji" data-wiki="Trachylepis_capensis">
        <span class="poll-fallback">🦎</span>
      </div>
      <div>
        <div class="poll-title">Lizards & Geckos</div>
        <div class="poll-desc">SA's blue-tailed skinks and several gecko species act as pollinators on rocky outcrops and arid regions, visiting ground-hugging succulents and aloes. A uniquely African pollination strategy.</div>
        <span class="poll-fact">🌵 Key plant: Aloes, Ground Succulents</span>
      </div>
    </div>

  </div>
</section>

<!-- COMPANION PLANTING -->
<section id="companions">
  <span class="section-tag">Companion Planting</span>
  <h2 class="section-title">Plants that grow<br>better together</h2>
  <p class="section-intro">Companion planting is the art of placing plants strategically so they help each other — repelling pests, fixing nitrogen, attracting beneficials, or improving flavour. Here's a South African guide.</p>

  <div class="companion-intro-grid">
    <div>
      <div class="companion-table-wrap">
        <table>
          <thead>
            <tr>
              <th>Plant</th>
              <th>Good Friends ✅</th>
              <th>Bad Neighbours ❌</th>
              <th>Benefit</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>Tomatoes</strong></td>
              <td class="friend">Basil, Marigold, Parsley</td>
              <td class="foe">Fennel, Brassicas</td>
              <td><span class="benefit-chip">Repels aphids & whitefly</span></td>
            </tr>
            <tr>
              <td><strong>Beans</strong></td>
              <td class="friend">Carrot, Squash, Maize</td>
              <td class="foe">Onion, Garlic</td>
              <td><span class="benefit-chip">Fixes nitrogen</span></td>
            </tr>
            <tr>
              <td><strong>Cabbage</strong></td>
              <td class="friend">Dill, Sage, Nasturtium</td>
              <td class="foe">Strawberry, Tomato</td>
              <td><span class="benefit-chip">Deters caterpillars</span></td>
            </tr>
            <tr>
              <td><strong>Carrots</strong></td>
              <td class="friend">Onion, Leek, Rosemary</td>
              <td class="foe">Dill, Anise</td>
              <td><span class="benefit-chip">Confuses carrot fly</span></td>
            </tr>
            <tr>
              <td><strong>Roses</strong></td>
              <td class="friend">Garlic, Lavender, Chives</td>
              <td class="foe">Boxwood</td>
              <td><span class="benefit-chip">Prevents black spot</span></td>
            </tr>
            <tr>
              <td><strong>Maize</strong></td>
              <td class="friend">Beans, Pumpkin, Squash</td>
              <td class="foe">Celery</td>
              <td><span class="benefit-chip">The 3 Sisters method</span></td>
            </tr>
            <tr>
              <td><strong>Spinach</strong></td>
              <td class="friend">Strawberry, Pea, Celery</td>
              <td class="foe">Potato</td>
              <td><span class="benefit-chip">Improves soil moisture</span></td>
            </tr>
            <tr>
              <td><strong>Protea</strong></td>
              <td class="friend">Fynbos grasses, Restios</td>
              <td class="foe">Fertilised lawns</td>
              <td><span class="benefit-chip">Supports mycorrhizae</span></td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

    <div style="display: flex; flex-direction: column; gap: 1rem;">
      <div class="tip-box">
        <h3>🌿 The Three Sisters (SA Style)</h3>
        <ul>
          <li>🌽 <span>Plant <strong>mielies</strong> first — they grow tall and act as a trellis</span></li>
          <li>🫘 <span>Plant <strong>beans</strong> around the mielies — they fix atmospheric nitrogen</span></li>
          <li>🎃 <span>Plant <strong>pumpkins/marrows</strong> between — leaves shade the soil, reducing water loss</span></li>
          <li>💡 <span>This ancient system predates chemical fertilisers and still outperforms them</span></li>
        </ul>
      </div>
      <div class="tip-box" style="background: linear-gradient(135deg, var(--gold), var(--terracotta));">
        <h3>🌸 South African Pest Control</h3>
        <ul>
          <li>🧅 <span><strong>Garlic</strong> planted near roses repels aphids and fungal disease</span></li>
          <li>🌼 <span><strong>Khakibos (Tagetes)</strong> deters nematodes from soil near vegetables</span></li>
          <li>🌿 <span><strong>Buchu</strong> near brassicas repels the diamondback moth</span></li>
          <li>🪻 <span><strong>Lavender</strong> borders confuse and deter whitefly and thrips</span></li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- SOIL TYPES -->
<section id="soil">
  <span class="section-tag">Soil Types</span>
  <h2 class="section-title">Know your ground</h2>
  <p class="section-intro">South Africa's extraordinary geological diversity creates vastly different soil types across the country. Gardening success begins with understanding what's beneath your feet.</p>

  <div class="soil-grid">
    <div class="soil-card sandy reveal">
      <span class="soil-emoji">🏜️</span>
      <div class="soil-name">Sandy / Coastal Soil</div>
      <div class="soil-desc">Found along the coast and dune areas. Fast-draining, low in nutrients, but excellent for indigenous fynbos, proteas, and succulents that hate wet roots.</div>
      <div class="soil-props">
        <div class="soil-prop"><div class="prop-dot" style="background:#ffd700"></div>pH: 5.5–6.5 (slightly acidic)</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#ff9999"></div>Drainage: Excellent</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aaffaa"></div>Best for: Proteas, Restios, Succulents</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aadcff"></div>Improve with: Compost, Bentonite clay</div>
      </div>
    </div>

    <div class="soil-card clay-soil reveal">
      <span class="soil-emoji">🧱</div>
      <div class="soil-name">Clay-Rich Soil</div>
      <div class="soil-desc">Common in Highveld and KwaZulu-Natal. Nutrient-rich but compacts easily. Waterlogged in winter, rock-hard in summer. Needs amendment for most vegetables.</div>
      <div class="soil-props">
        <div class="soil-prop"><div class="prop-dot" style="background:#ffd700"></div>pH: 6.0–7.5 (neutral)</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#ff9999"></div>Drainage: Poor</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aaffaa"></div>Best for: Aloes, Agapanthus, Roses</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aadcff"></div>Improve with: Gypsum, Compost, Sand</div>
      </div>
    </div>

    <div class="soil-card loam reveal">
      <span class="soil-emoji">🌱</span>
      <div class="soil-name">Loam Soil</div>
      <div class="soil-desc">The gardener's dream — a balanced mix of sand, silt, and clay found in Mpumalanga and parts of Limpopo. Retains moisture while draining well. Grows almost anything.</div>
      <div class="soil-props">
        <div class="soil-prop"><div class="prop-dot" style="background:#ffd700"></div>pH: 6.0–7.0 (ideal)</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#ff9999"></div>Drainage: Good</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aaffaa"></div>Best for: Vegetables, Herbs, Fruit trees</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aadcff"></div>Maintain with: Mulch, Annual compost</div>
      </div>
    </div>

    <div class="soil-card fynbos reveal">
      <span class="soil-emoji">🪨</span>
      <div class="soil-name">Fynbos / Acidic Soil</div>
      <div class="soil-desc">Nutrient-poor, highly acidic soils of the Cape Floristic Region. Uniquely suited to proteas, ericas, and restios. Adding fertiliser can kill indigenous plants adapted here.</div>
      <div class="soil-props">
        <div class="soil-prop"><div class="prop-dot" style="background:#ffd700"></div>pH: 4.5–5.5 (very acidic)</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#ff9999"></div>Drainage: Very good</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aaffaa"></div>Best for: Proteas, Ericas, Leucadendrons</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aadcff"></div>Note: DO NOT fertilise!</div>
      </div>
    </div>

    <div class="soil-card compost reveal">
      <span class="soil-emoji">♻️</span>
      <div class="soil-name">Compost-Enriched Soil</div>
      <div class="soil-desc">Any soil transformed with homemade or commercial compost. South Africa's warm climate accelerates decomposition. Even 10% compost by volume dramatically improves structure and biology.</div>
      <div class="soil-props">
        <div class="soil-prop"><div class="prop-dot" style="background:#ffd700"></div>pH: 6.5–7.5 (adjustable)</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#ff9999"></div>Drainage: Improved</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aaffaa"></div>Best for: All food gardens</div>
        <div class="soil-prop"><div class="prop-dot" style="background:#aadcff"></div>Add: Worm castings, Kraal manure</div>
      </div>
    </div>
  </div>

  <div class="soil-improve-grid">
    <div class="improve-card reveal">
      <h4>🐄 Kraal Manure</h4>
      <p>The South African gold standard. Well-composted cattle or horse manure improves clay soils, feeds beneficial microbes, and gently releases nutrients over 6–12 months. Always compost fresh manure first.</p>
    </div>
    <div class="improve-card reveal">
      <h4>🪵 Wood Chip Mulch</h4>
      <p>Apply 10cm of wood chips on top of beds to retain moisture, suppress weeds, and slowly feed soil fungi. Indigenous trees like Acacia chips are ideal and locally available. Never dig it in fresh.</p>
    </div>
    <div class="improve-card reveal">
      <h4>🌊 Biochar & Gypsum</h4>
      <p>Biochar (charcoal) from prunings improves water retention in sandy soils while gypsum breaks up compacted clay without altering pH — perfect for Highveld gardens. Both last years in the soil.</p>
    </div>
  </div>
</section>

<!-- SEASONS -->
<section id="seasons">
  <span class="section-tag">Planting Calendar</span>
  <h2 class="section-title">South Africa's<br>growing seasons</h2>
  <p class="section-intro">South Africa spans multiple climate zones — from winter-rainfall Cape to summer-rainfall Highveld. Use this guide for most of the country; adjust timing 4–6 weeks for the Cape's opposite rainfall pattern.</p>

  <div class="seasons-grid">

    <div class="season-card summer reveal">
      <div class="season-header">
        <span class="season-icon">☀️</span>
        <div class="season-name">Summer</div>
        <div class="season-months">October — February</div>
      </div>
      <div class="season-body">
        <div class="season-section-title">Sow Now</div>
        <ul class="season-list">
          <li>Tomatoes, Peppers</li>
          <li>Butternut, Gem squash</li>
          <li>Sweet basil, Marigold</li>
          <li>Beans, Cucumber</li>
        </ul>
        <div class="season-section-title">Garden Tasks</div>
        <ul class="season-list">
          <li>Mulch heavily to retain moisture</li>
          <li>Water early morning only</li>
          <li>Watch for aphids & whitefly</li>
          <li>Harvest protea flowers</li>
        </ul>
      </div>
    </div>

    <div class="season-card autumn reveal">
      <div class="season-header">
        <span class="season-icon">🍂</span>
        <div class="season-name">Autumn</div>
        <div class="season-months">March — May</div>
      </div>
      <div class="season-body">
        <div class="season-section-title">Sow Now</div>
        <ul class="season-list">
          <li>Spinach, Swiss chard</li>
          <li>Peas, Broad beans</li>
          <li>Carrots, Beetroot</li>
          <li>Indigenous bulbs (Ixia, Watsonia)</li>
        </ul>
        <div class="season-section-title">Garden Tasks</div>
        <ul class="season-list">
          <li>Divide and transplant perennials</li>
          <li>Add compost to beds</li>
          <li>Plant indigenous shrubs</li>
          <li>Collect and save seeds</li>
        </ul>
      </div>
    </div>

    <div class="season-card winter reveal">
      <div class="season-header">
        <span class="season-icon">🌧️</span>
        <div class="season-name">Winter</div>
        <div class="season-months">June — August</div>
      </div>
      <div class="season-body">
        <div class="season-section-title">Sow Now</div>
        <ul class="season-list">
          <li>Cabbage, Kale, Broccoli</li>
          <li>Garlic, Onion, Leek</li>
          <li>Lettuce, Rocket</li>
          <li>Fennel, Parsley</li>
        </ul>
        <div class="season-section-title">Garden Tasks</div>
        <ul class="season-list">
          <li>Prune roses & deciduous trees</li>
          <li>Plant bare-root fruit trees</li>
          <li>Refresh compost heaps</li>
          <li>Plan next season's layout</li>
        </ul>
      </div>
    </div>

    <div class="season-card spring reveal">
      <div class="season-header">
        <span class="season-icon">🌸</span>
        <div class="season-name">Spring</div>
        <div class="season-months">September — October</div>
      </div>
      <div class="season-body">
        <div class="season-section-title">Sow Now</div>
        <ul class="season-list">
          <li>Zucchini, Pumpkin</li>
          <li>Sunflowers, Zinnia</li>
          <li>Sweetcorn (mielies)</li>
          <li>Herbs: Basil, Coriander</li>
        </ul>
        <div class="season-section-title">Garden Tasks</div>
        <ul class="season-list">
          <li>Divide Agapanthus clumps</li>
          <li>Set up drip irrigation</li>
          <li>Feed with liquid seaweed</li>
          <li>Plant out seedlings after frost</li>
        </ul>
      </div>
    </div>

  </div>
</section>

<!-- TIPS BANNER -->
<div class="tip-banner">
  <h2>Water-wise gardening is<br><em>indigenous gardening</em></h2>
  <p>In a water-scarce country, every garden choice matters. Growing indigenous plants and building healthy soil are the most powerful things a South African gardener can do for their environment.</p>
  <div class="tips-row">
    <div class="tip-item">
      <span class="tip-item-icon">🪣</span>
      <h4>Rainwater Harvesting</h4>
      <p>Connect gutters to a tank or barrel. Even 2,000L stored in winter can see a Cape garden through a dry summer month.</p>
    </div>
    <div class="tip-item">
      <span class="tip-item-icon">🌾</span>
      <h4>Sheet Mulching</h4>
      <p>Layer cardboard then compost then wood chips. Suppresses weeds, feeds soil life, and halves water use overnight.</p>
    </div>
    <div class="tip-item">
      <span class="tip-item-icon">🐛</span>
      <h4>Worm Farms</h4>
      <p>A small worm farm converts kitchen scraps into castings more nutrient-dense than any shop fertiliser. Free, sustainable, and odour-free.</p>
    </div>
    <div class="tip-item">
      <span class="tip-item-icon">🌻</span>
      <h4>Grow for Biodiversity</h4>
      <p>A garden with 20 indigenous species supports 10× more animal life than an exotic garden. Every indigenous plant is a habitat.</p>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="foot-logo">🌸 <span style="color:#2e7d32">Roots</span> <span style="color:#1a1a1a">&amp;</span> <span style="color:#00acc1">Rain</span> 🌿</div>
  <p>A guide to thoughtful, water-wise, biodiverse gardening rooted in South Africa's extraordinary natural heritage. Garden with the land, not against it.</p>
  <div class="foot-links">
    <a href="#plants">Indigenous Plants</a>
    <a href="#pollinators">Pollinators</a>
    <a href="#companions">Companions</a>
    <a href="#soil">Soil</a>
    <a href="#seasons">Seasons</a>
  </div>
  <p style="margin-top:1.5rem; font-size:0.75rem; opacity: 0.4;">🌿 Made with love for South African gardens · For the fynbos, the highveld, and everything between</p>
</footer>

<script>
  // ─── Reveal animations ───
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) {
        setTimeout(() => e.target.classList.add('visible'), (e.target.dataset.delay||0)*80);
        observer.unobserve(e.target);
      }
    });
  }, { threshold: 0.1 });
  document.querySelectorAll('.reveal').forEach((el,i) => { el.dataset.delay=i%4; observer.observe(el); });

  // ─── Nav highlight ───
  window.addEventListener('scroll', () => {
    let cur='';
    document.querySelectorAll('section[id]').forEach(s => { if(window.scrollY>=s.offsetTop-100) cur=s.id; });
    document.querySelectorAll('.nav-links a').forEach(a => {
      a.style.color = a.getAttribute('href')==='#'+cur ? 'var(--terracotta)' : '';
    });
  });

  // ─── Wikipedia REST API photo loader ───
  // Uses the Wikipedia Summary API — fully CORS-enabled, free, works directly from the browser.
  // Returns a thumbnail image for each species' Wikipedia article.
  async function loadWikiPhoto(el, articleTitle) {
    try {
      const url = `https://en.wikipedia.org/api/rest_v1/page/summary/${encodeURIComponent(articleTitle)}`;
      const res = await fetch(url);
      if (!res.ok) return;
      const data = await res.json();

      const thumb = data.thumbnail;
      if (!thumb || !thumb.source) return;

      // Build a wider thumbnail (replace width param for better resolution)
      const imgSrc = thumb.source.replace(/\/\d+px-/, '/500px-');

      const img = document.createElement('img');
      img.alt = data.title || articleTitle;
      img.loading = 'lazy';

      // Credit
      const credit = document.createElement('span');
      credit.className = 'photo-credit';
      credit.textContent = '© Wikimedia Commons';

      img.onload = () => {
        el.innerHTML = '';
        el.appendChild(img);
        el.appendChild(credit);
      };
      img.src = imgSrc;
    } catch(e) { /* keep emoji placeholder */ }
  }

  // Load plant photos
  document.querySelectorAll('.plant-icon[data-wiki]').forEach(el => {
    loadWikiPhoto(el, el.dataset.wiki);
  });

  // Load pollinator photos
  document.querySelectorAll('.poll-emoji[data-wiki]').forEach(el => {
    loadWikiPhoto(el, el.dataset.wiki);
  });
</script>
</body>
</html>
