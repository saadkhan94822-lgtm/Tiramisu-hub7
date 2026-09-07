# Tiramisu-hub7
We are selling tiramisu in local area dont let the tiramisu get out of stock order it now 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tiramisu Hub — Fresh, Creamy Tiramisu in Motihari</title>
<meta name="description" content="Tiramisu Hub — Motihari's premium tiramisu destination. Freshly crafted, rich & creamy tiramisu made with love. Order online or get home delivery.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700;800&family=Jost:wght@400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.css">
<style>
  :root{
    --bg-dark:#1c0d06;
    --bg-coffee:#2c1710;
    --bg-coffee-2:#3a2016;
    --cream:#faf3e6;
    --cream-2:#f1e4c9;
    --gold:#c9a227;
    --gold-light:#e8c874;
    --ink:#2c1710;
    --ink-soft:#5b4230;
    --on-dark:#f3e9d2;
    --shadow:0 12px 30px -12px rgba(28,13,6,.45);
    --radius:18px;
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;font-family:'Jost',sans-serif;color:var(--ink);background:var(--cream);
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3,.logo-word{font-family:'Playfair Display',serif;}
  a{color:inherit;text-decoration:none;}
  img,svg{max-width:100%;display:block;}
  ul{list-style:none;margin:0;padding:0;}
  section{padding:88px 24px;}
  .wrap{max-width:1180px;margin:0 auto;}
  .eyebrow{font-size:12.5px;letter-spacing:3px;color:var(--gold);opacity:.85;margin:0 0 10px;}
  .section-title{font-size:clamp(28px,4vw,40px);font-weight:700;margin:0 0 14px;line-height:1.15;}
  .section-lede{max-width:560px;color:var(--ink-soft);font-size:16px;line-height:1.7;margin:0 0 40px;}
  .on-dark .section-lede{color:rgba(243,233,210,.75);}
  .btn{
    display:inline-flex;align-items:center;gap:8px;padding:14px 28px;border-radius:999px;
    font-size:14.5px;font-weight:600;letter-spacing:.3px;cursor:pointer;border:1px solid transparent;
    transition:transform .18s ease, box-shadow .18s ease, background .18s ease;
  }
  .btn:active{transform:scale(.97);}
  .btn-gold{background:var(--gold);color:var(--bg-dark);}
  .btn-gold:hover{background:var(--gold-light);box-shadow:0 8px 20px -6px rgba(201,162,39,.55);}
  .btn-outline{border-color:var(--gold);color:var(--gold-light);background:transparent;}
  .btn-outline:hover{background:rgba(201,162,39,.12);}
  .btn-outline-dark{border-color:var(--ink);color:var(--ink);background:transparent;}
  .btn-outline-dark:hover{background:rgba(44,23,16,.06);}
  .btn-sm{padding:9px 18px;font-size:13px;}
  @media (prefers-reduced-motion: reduce){ *{animation:none !important; transition:none !important;} }

  /* ---------- Nav ---------- */
  #nav{
    position:fixed;top:0;left:0;right:0;z-index:100;
    background:rgba(28,13,6,.72);backdrop-filter:blur(10px);
    border-bottom:1px solid rgba(201,162,39,.18);
    transition:background .3s ease;
  }
  #nav .wrap{display:flex;align-items:center;justify-content:space-between;padding:14px 24px;max-width:1180px;}
  .brand{display:flex;align-items:center;gap:10px;color:var(--on-dark);}
  .brand .mark{
    width:38px;height:38px;border-radius:50%;border:1.5px solid var(--gold);
    display:flex;align-items:center;justify-content:center;font-weight:700;color:var(--gold-light);font-size:14px;
  }
  .brand .word{font-size:19px;letter-spacing:.5px;font-weight:700;}
  #nav-links{display:flex;align-items:center;gap:26px;}
  #nav-links a{color:rgba(243,233,210,.82);font-size:14px;font-weight:500;}
  #nav-links a:hover{color:var(--gold-light);}
  #nav-actions{display:flex;align-items:center;gap:14px;}
  #cart-toggle{
    position:relative;background:none;border:1px solid rgba(201,162,39,.5);color:var(--on-dark);
    width:40px;height:40px;border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;
  }
  #cart-toggle svg{width:18px;height:18px;stroke:var(--gold-light);}
  #cart-count{
    position:absolute;top:-6px;right:-6px;background:var(--gold);color:var(--bg-dark);
    font-size:11px;font-weight:700;border-radius:50%;width:18px;height:18px;display:flex;align-items:center;justify-content:center;
  }
  #nav-burger{display:none;background:none;border:none;color:var(--on-dark);font-size:22px;cursor:pointer;}
  @media (max-width:860px){
    #nav-links{position:fixed;top:64px;left:0;right:0;background:var(--bg-coffee);flex-direction:column;
      padding:18px 24px;gap:16px;transform:translateY(-8px);opacity:0;pointer-events:none;transition:.22s ease;
      border-bottom:1px solid rgba(201,162,39,.18);}
    #nav-links.open{transform:translateY(0);opacity:1;pointer-events:auto;}
    #nav-burger{display:block;}
  }

  /* ---------- Hero ---------- */
  #hero{
    position:relative;padding:170px 24px 100px;background:
      radial-gradient(circle at 20% 15%, rgba(232,200,116,.10), transparent 35%),
      radial-gradient(circle at 85% 10%, rgba(232,200,116,.08), transparent 32%),
      linear-gradient(180deg,var(--bg-dark) 0%, var(--bg-coffee) 60%, var(--bg-coffee-2) 100%);
    color:var(--on-dark);overflow:hidden;
  }
  #hero .wrap{display:grid;grid-template-columns:1.05fr .95fr;gap:56px;align-items:center;}
  @media (max-width:900px){ #hero .wrap{grid-template-columns:1fr;} #hero{padding-top:140px;} }
  #hero .tag-hi{font-size:15px;color:var(--gold-light);letter-spacing:.4px;margin-bottom:14px;font-style:italic;}
  #hero h1{font-size:clamp(42px,6.4vw,72px);line-height:1.02;margin:0 0 18px;letter-spacing:1px;}
  #hero p.desc{color:rgba(243,233,210,.78);font-size:17px;max-width:440px;line-height:1.7;margin:0 0 32px;}
  #hero .cta-row{display:flex;gap:16px;flex-wrap:wrap;}
  .hero-art{position:relative;}
  .hero-art svg{width:100%;height:auto;}

  /* ---------- Featured Flavors ---------- */
  #flavors{background:var(--cream);}
  .flavor-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:28px;}
  @media (max-width:720px){.flavor-grid{grid-template-columns:1fr;}}
  .p-card{
    background:#fff;border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);
    border:1px solid rgba(44,23,16,.06);
    opacity:0;transform:translateY(18px);transition:opacity .6s ease, transform .6s ease;
  }
  .p-card.in{opacity:1;transform:translateY(0);}
  .p-card .art{aspect-ratio:4/3;background:linear-gradient(160deg,#efe2c9,#e4d2a8);display:flex;align-items:center;justify-content:center;padding:20px;}
  .p-card .art svg{width:78%;}
  .p-card .body{padding:22px 24px 26px;}
  .p-card h3{font-size:21px;margin:0 0 6px;}
  .p-card p{color:var(--ink-soft);font-size:14.5px;line-height:1.6;margin:0 0 16px;}
  .p-card .row{display:flex;align-items:center;justify-content:space-between;}
  .p-card .price{font-weight:700;color:var(--ink);font-size:18px;}
  .add-btn{
    background:var(--bg-dark);color:var(--gold-light);border:none;border-radius:999px;
    padding:10px 18px;font-size:13px;font-weight:600;cursor:pointer;transition:.2s ease;
  }
  .add-btn:hover{background:var(--gold);color:var(--bg-dark);}

  /* ---------- Why us ---------- */
  #why{background:linear-gradient(180deg,var(--bg-coffee-2),var(--bg-dark));color:var(--on-dark);}
  .why-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:22px;}
  @media (max-width:900px){.why-grid{grid-template-columns:repeat(2,1fr);}}
  @media (max-width:520px){.why-grid{grid-template-columns:1fr;}}
  .why-card{
    border:1px solid rgba(201,162,39,.22);border-radius:16px;padding:26px 22px;
    background:rgba(255,255,255,.02);
    opacity:0;transform:translateY(18px);transition:opacity .6s ease, transform .6s ease;
  }
  .why-card.in{opacity:1;transform:translateY(0);}
  .why-card .ic{width:40px;height:40px;margin-bottom:16px;stroke:var(--gold-light);fill:none;stroke-width:1.6;}
  .why-card h3{font-family:'Jost',sans-serif;font-size:16px;font-weight:600;margin:0 0 8px;color:var(--on-dark);}
  .why-card p{font-size:13.5px;color:rgba(243,233,210,.68);line-height:1.6;margin:0;}

  /* ---------- About ---------- */
  #about{background:var(--cream-2);}
  .about-grid{display:grid;grid-template-columns:.9fr 1.1fr;gap:56px;align-items:center;}
  @media (max-width:860px){.about-grid{grid-template-columns:1fr;}}
  #about p{color:var(--ink-soft);font-size:16px;line-height:1.8;margin:0 0 16px;}
  .about-art{border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);background:linear-gradient(160deg,#2c1710,#1c0d06);padding:36px;}

  /* ---------- Menu ---------- */
  #menu{background:var(--cream);}
  .menu-tools{display:flex;flex-wrap:wrap;gap:14px;align-items:center;justify-content:space-between;margin-bottom:34px;}
  .filters{display:flex;gap:10px;flex-wrap:wrap;}
  .filter-chip{
    border:1px solid rgba(44,23,16,.18);background:#fff;color:var(--ink);
    padding:9px 18px;border-radius:999px;font-size:13.5px;cursor:pointer;transition:.2s ease;
  }
  .filter-chip.active{background:var(--bg-dark);color:var(--gold-light);border-color:var(--bg-dark);}
  #menu-search{
    border:1px solid rgba(44,23,16,.18);border-radius:999px;padding:10px 18px;font-size:14px;
    font-family:'Jost',sans-serif;min-width:220px;background:#fff;
  }
  #menu-search:focus{outline:2px solid var(--gold);outline-offset:1px;}
  #menu-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;}
  @media (max-width:900px){#menu-grid{grid-template-columns:repeat(2,1fr);}}
  @media (max-width:600px){#menu-grid{grid-template-columns:1fr;}}
  #menu-empty{display:none;text-align:center;padding:50px 20px;color:var(--ink-soft);border:1px dashed rgba(44,23,16,.25);border-radius:16px;}
  #menu-empty h3{margin:0 0 8px;font-size:19px;color:var(--ink);}

  /* ---------- How to order ---------- */
  #how{background:linear-gradient(180deg,var(--bg-dark),var(--bg-coffee));color:var(--on-dark);}
  .steps{display:grid;grid-template-columns:repeat(3,1fr);gap:30px;counter-reset:step;}
  @media (max-width:800px){.steps{grid-template-columns:1fr;}}
  .step{position:relative;padding:30px 24px 24px;border:1px solid rgba(201,162,39,.22);border-radius:16px;}
  .step .num{
    font-family:'Playfair Display',serif;font-size:34px;color:var(--gold-light);opacity:.55;margin-bottom:10px;
  }
  .step h3{font-size:18px;margin:0 0 8px;}
  .step p{font-size:14px;color:rgba(243,233,210,.7);line-height:1.6;margin:0;}

  /* ---------- Location ---------- */
  #location{background:var(--cream-2);}
  .loc-grid{display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:stretch;}
  @media (max-width:900px){.loc-grid{grid-template-columns:1fr;}}
  .loc-info{display:flex;flex-direction:column;justify-content:center;gap:18px;}
  .loc-info .addr{font-size:18px;font-weight:600;line-height:1.5;}
  .loc-info .sub{color:var(--ink-soft);font-size:14.5px;}
  .banner{
    display:inline-flex;align-items:center;gap:10px;background:rgba(201,162,39,.14);
    border:1px solid rgba(201,162,39,.35);color:var(--ink);padding:10px 16px;border-radius:12px;
    font-size:13.5px;font-weight:600;width:fit-content;
  }
  .delivery-rates{
    border:1px solid rgba(44,23,16,.15);border-radius:14px;padding:16px 18px;
    background:rgba(255,255,255,.55);max-width:320px;
  }
  .delivery-rates h4{margin:0 0 10px;font-size:12.5px;letter-spacing:1.4px;text-transform:uppercase;color:var(--ink-soft);font-weight:600;}
  .delivery-rates ul li{display:flex;justify-content:space-between;gap:12px;font-size:14px;padding:7px 0;border-bottom:1px dashed rgba(44,23,16,.15);}
  .delivery-rates ul li:last-child{border-bottom:none;}
  .delivery-rates ul li span:last-child{font-weight:700;color:var(--ink);}
  .map-frame{border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);min-height:320px;border:1px solid rgba(44,23,16,.08);}
  .map-frame iframe{width:100%;height:100%;min-height:320px;border:0;display:block;}

  /* ---------- Contact ---------- */
  #contact{background:linear-gradient(180deg,var(--bg-coffee),var(--bg-dark));color:var(--on-dark);}
  .contact-grid{display:grid;grid-template-columns:.9fr 1.1fr;gap:48px;}
  @media (max-width:860px){.contact-grid{grid-template-columns:1fr;}}
  .contact-actions{display:flex;flex-direction:column;gap:14px;margin-top:22px;}
  .contact-actions a{
    display:flex;align-items:center;gap:12px;border:1px solid rgba(201,162,39,.3);border-radius:12px;
    padding:14px 16px;font-size:14.5px;color:var(--on-dark);
  }
  .contact-actions a:hover{background:rgba(201,162,39,.08);}
  .contact-actions svg{width:18px;height:18px;stroke:var(--gold-light);fill:none;stroke-width:1.6;flex-shrink:0;}
  form#contact-form{display:flex;flex-direction:column;gap:14px;}
  form#contact-form input, form#contact-form textarea{
    background:rgba(255,255,255,.04);border:1px solid rgba(201,162,39,.28);border-radius:10px;
    padding:13px 14px;color:var(--on-dark);font-family:'Jost',sans-serif;font-size:14.5px;
  }
  form#contact-form input::placeholder, form#contact-form textarea::placeholder{color:rgba(243,233,210,.45);}
  form#contact-form input:focus, form#contact-form textarea:focus{outline:2px solid var(--gold);outline-offset:1px;}
  #form-status{font-size:13.5px;color:var(--gold-light);min-height:18px;}

  /* ---------- Footer ---------- */
  footer{background:var(--bg-dark);color:rgba(243,233,210,.65);padding:56px 24px 26px;}
  .foot-grid{display:grid;grid-template-columns:1.3fr 1fr 1fr;gap:36px;margin-bottom:36px;}
  @media (max-width:700px){.foot-grid{grid-template-columns:1fr;}}
  footer h4{color:var(--on-dark);font-size:14px;letter-spacing:1px;margin:0 0 14px;font-family:'Jost',sans-serif;font-weight:600;}
  footer ul li{margin-bottom:9px;font-size:14px;}
  footer ul li a:hover{color:var(--gold-light);}
  .foot-bottom{border-top:1px solid rgba(201,162,39,.15);padding-top:20px;font-size:12.5px;display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;}

  /* ---------- Cart drawer ---------- */
  #cart-overlay{position:fixed;inset:0;background:rgba(28,13,6,.5);z-index:199;opacity:0;pointer-events:none;transition:opacity .25s ease;}
  #cart-overlay.open{opacity:1;pointer-events:auto;}
  #cart-drawer{
    position:fixed;top:0;right:0;height:100%;width:min(400px,92vw);background:var(--cream);z-index:200;
    box-shadow:-14px 0 40px rgba(0,0,0,.25);transform:translateX(100%);transition:transform .3s ease;
    display:flex;flex-direction:column;
  }
  #cart-drawer.open{transform:translateX(0);}
  .cart-head{display:flex;justify-content:space-between;align-items:center;padding:20px 22px;border-bottom:1px solid rgba(44,23,16,.1);}
  .cart-head h3{margin:0;font-size:19px;}
  #cart-close{background:none;border:none;font-size:22px;cursor:pointer;color:var(--ink);}
  #cart-items{flex:1;overflow-y:auto;padding:16px 22px;}
  .cart-item{display:flex;gap:12px;align-items:center;padding:14px 0;border-bottom:1px solid rgba(44,23,16,.08);}
  .cart-item .ci-name{flex:1;font-size:14.5px;font-weight:600;}
  .cart-item .ci-price{font-size:13px;color:var(--ink-soft);}
  .qty{display:flex;align-items:center;gap:8px;}
  .qty button{width:26px;height:26px;border-radius:50%;border:1px solid rgba(44,23,16,.25);background:#fff;cursor:pointer;font-size:14px;line-height:1;}
  .qty span{min-width:16px;text-align:center;font-size:14px;}
  .ci-remove{background:none;border:none;color:#a9432b;font-size:12px;cursor:pointer;margin-left:8px;}
  #cart-empty{color:var(--ink-soft);font-size:14px;padding:30px 0;text-align:center;}
  .cart-foot{padding:18px 22px 24px;border-top:1px solid rgba(44,23,16,.1);}
  .cart-total-row{display:flex;justify-content:space-between;font-size:15px;font-weight:700;margin-bottom:8px;}
  .cart-total-row.cart-total-sub{font-size:13.5px;font-weight:500;color:var(--ink-soft);}
  .cart-total-row.cart-grand{border-top:1px dashed rgba(44,23,16,.2);padding-top:10px;margin-top:2px;margin-bottom:16px;}
  .cart-foot .btn{width:100%;justify-content:center;}
  .cart-customer{display:flex;flex-direction:column;gap:10px;margin-bottom:16px;}
  .cart-customer input{
    border:1px solid rgba(44,23,16,.2);border-radius:10px;padding:11px 14px;font-size:14px;
    font-family:'Jost',sans-serif;background:#fff;color:var(--ink);
  }
  .cart-customer input:focus{outline:2px solid var(--gold);outline-offset:1px;}
  .cart-customer input.invalid{border-color:#a9432b;}
  #cust-error{color:#a9432b;font-size:12.5px;min-height:16px;}
  #map-hint{font-size:11.5px;color:var(--ink-soft);}
  #delivery-map{height:170px;border-radius:10px;overflow:hidden;border:1px solid rgba(44,23,16,.2);}
  #delivery-summary{font-size:13px;font-weight:600;color:var(--ink);}
  #delivery-summary.out-of-range{color:#a9432b;}
  .stall-pin{background:var(--gold);border:2px solid var(--bg-dark);border-radius:50%;width:14px;height:14px;}
  .cust-pin{background:#a9432b;border:2px solid #fff;border-radius:50%;width:14px;height:14px;}

  .reveal{opacity:0;transform:translateY(18px);transition:opacity .6s ease, transform .6s ease;}
  .reveal.in{opacity:1;transform:translateY(0);}
  .sr-only{position:absolute;width:1px;height:1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;}
  :focus-visible{outline:2px solid var(--gold);outline-offset:2px;}
</style>
</head>
<body>

<!-- ================= NAV ================= -->
<nav id="nav">
  <div class="wrap">
    <a href="#hero" class="brand">
      <span class="mark">TH</span>
      <span class="word">Tiramisu Hub</span>
    </a>
    <ul id="nav-links">
      <li><a href="#flavors">Flavors</a></li>
      <li><a href="#why">Why Us</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#menu">Menu</a></li>
      <li><a href="#how">How to Order</a></li>
      <li><a href="#location">Location</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div id="nav-actions">
      <button id="cart-toggle" aria-label="Open cart">
        <svg viewBox="0 0 24 24" fill="none" stroke-linecap="round" stroke-linejoin="round"><path d="M3 4h2l2.6 12.4a2 2 0 0 0 2 1.6h7.7a2 2 0 0 0 2-1.6L21 8H6"/><circle cx="10" cy="21" r="1"/><circle cx="18" cy="21" r="1"/></svg>
        <span id="cart-count">0</span>
      </button>
      <button id="nav-burger" aria-label="Toggle menu" aria-expanded="false">&#9776;</button>
    </div>
  </div>
</nav>

<!-- ================= HERO ================= -->
<header id="hero">
  <div class="wrap">
    <div>
      <div class="tag-hi">Har Layer Mein Swaad, Har Bite Mein Khushiyan.</div>
      <h1>TIRAMISU<br>HUB</h1>
      <p class="desc">Freshly crafted, rich &amp; creamy tiramisu made with love — served straight from our kitchen in Motihari.</p>
      <div class="cta-row">
        <a href="#menu" class="btn btn-gold">Order Now</a>
        <a href="#flavors" class="btn btn-outline">Explore Flavors</a>
      </div>
    </div>
    <div class="hero-art">
      <svg viewBox="0 0 420 360" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="gCup" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="#f6ecd9"/>
            <stop offset="100%" stop-color="#d8b98a"/>
          </linearGradient>
          <linearGradient id="gLayer" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="#8a5a34"/>
            <stop offset="100%" stop-color="#5c3a20"/>
          </linearGradient>
        </defs>
        <ellipse cx="210" cy="322" rx="150" ry="18" fill="#000" opacity=".18"/>
        <path d="M110 120 L140 300 Q210 320 280 300 L310 120 Z" fill="url(#gCup)"/>
        <path d="M118 150 L302 150 L296 190 L124 190 Z" fill="url(#gLayer)" opacity=".92"/>
        <path d="M124 210 L296 210 L290 250 L130 250 Z" fill="url(#gLayer)" opacity=".8"/>
        <path d="M116 120 Q210 100 304 120 L296 150 L124 150 Z" fill="#efe2c9"/>
        <g fill="#4a2f1c" opacity=".65">
          <circle cx="150" cy="112" r="2.4"/><circle cx="172" cy="106" r="2.4"/><circle cx="196" cy="114" r="2.4"/>
          <circle cx="220" cy="105" r="2.4"/><circle cx="244" cy="113" r="2.4"/><circle cx="268" cy="107" r=<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tiramisu Hub — Fresh, Creamy Tiramisu in Motihari</title>
<meta name="description" content="Tiramisu Hub — Motihari's premium tiramisu destination. Freshly crafted, rich & creamy tiramisu made with love. Order online or get home delivery.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700;800&family=Jost:wght@400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.9.4/leaflet.min.css">
<style>
  :root{
    --bg-dark:#1c0d06;
    --bg-coffee:#2c1710;
    --bg-coffee-2:#3a2016;
    --cream:#faf3e6;
    --cream-2:#f1e4c9;
    --gold:#c9a227;
    --gold-light:#e8c874;
    --ink:#2c1710;
    --ink-soft:#5b4230;
    --on-dark:#f3e9d2;
    --shadow:0 12px 30px -12px rgba(28,13,6,.45);
    --radius:18px;
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;font-family:'Jost',sans-serif;color:var(--ink);background:var(--cream);
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3,.logo-word{font-family:'Playfair Display',serif;}
  a{color:inherit;text-decoration:none;}
  img,svg{max-width:100%;display:block;}
  ul{list-style:none;margin:0;padding:0;}
  section{padding:88px 24px;}
  .wrap{max-width:1180px;margin:0 auto;}
  .eyebrow{font-size:12.5px;letter-spacing:3px;color:var(--gold);opacity:.85;margin:0 0 10px;}
  .section-title{font-size:clamp(28px,4vw,40px);font-weight:700;margin:0 0 14px;line-height:1.15;}
  .section-lede{max-width:560px;color:var(--ink-soft);font-size:16px;line-height:1.7;margin:0 0 40px;}
  .on-dark .section-lede{color:rgba(243,233,210,.75);}
  .btn{
    display:inline-flex;align-items:center;gap:8px;padding:14px 28px;border-radius:999px;
    font-size:14.5px;font-weight:600;letter-spacing:.3px;cursor:pointer;border:1px solid transparent;
    transition:transform .18s ease, box-shadow .18s ease, background .18s ease;
  }
  .btn:active{transform:scale(.97);}
  .btn-gold{background:var(--gold);color:var(--bg-dark);}
  .btn-gold:hover{background:var(--gold-light);box-shadow:0 8px 20px -6px rgba(201,162,39,.55);}
  .btn-outline{border-color:var(--gold);color:var(--gold-light);background:transparent;}
  .btn-outline:hover{background:rgba(201,162,39,.12);}
  .btn-outline-dark{border-color:var(--ink);color:var(--ink);background:transparent;}
  .btn-outline-dark:hover{background:rgba(44,23,16,.06);}
  .btn-sm{padding:9px 18px;font-size:13px;}
  @media (prefers-reduced-motion: reduce){ *{animation:none !important; transition:none !important;} }

  /* ---------- Nav ---------- */
  #nav{
    position:fixed;top:0;left:0;right:0;z-index:100;
    background:rgba(28,13,6,.72);backdrop-filter:blur(10px);
    border-bottom:1px solid rgba(201,162,39,.18);
    transition:background .3s ease;
  }
  #nav .wrap{display:flex;align-items:center;justify-content:space-between;padding:14px 24px;max-width:1180px;}
  .brand{display:flex;align-items:center;gap:10px;color:var(--on-dark);}
  .brand .mark{
    width:38px;height:38px;border-radius:50%;border:1.5px solid var(--gold);
    display:flex;align-items:center;justify-content:center;font-weight:700;color:var(--gold-light);font-size:14px;
  }
  .brand .word{font-size:19px;letter-spacing:.5px;font-weight:700;}
  #nav-links{display:flex;align-items:center;gap:26px;}
  #nav-links a{color:rgba(243,233,210,.82);font-size:14px;font-weight:500;}
  #nav-links a:hover{color:var(--gold-light);}
  #nav-actions{display:flex;align-items:center;gap:14px;}
  #cart-toggle{
    position:relative;background:none;border:1px solid rgba(201,162,39,.5);color:var(--on-dark);
    width:40px;height:40px;border-radius:50%;display:flex;align-items:center;justify-content:center;cursor:pointer;
  }
  #cart-toggle svg{width:18px;height:18px;stroke:var(--gold-light);}
  #cart-count{
    position:absolute;top:-6px;right:-6px;background:var(--gold);color:var(--bg-dark);
    font-size:11px;font-weight:700;border-radius:50%;width:18px;height:18px;display:flex;align-items:center;justify-content:center;
  }
  #nav-burger{display:none;background:none;border:none;color:var(--on-dark);font-size:22px;cursor:pointer;}
  @media (max-width:860px){
    #nav-links{position:fixed;top:64px;left:0;right:0;background:var(--bg-coffee);flex-direction:column;
      padding:18px 24px;gap:16px;transform:translateY(-8px);opacity:0;pointer-events:none;transition:.22s ease;
      border-bottom:1px solid rgba(201,162,39,.18);}
    #nav-links.open{transform:translateY(0);opacity:1;pointer-events:auto;}
    #nav-burger{display:block;}
  }

  /* ---------- Hero ---------- */
  #hero{
    position:relative;padding:170px 24px 100px;background:
      radial-gradient(circle at 20% 15%, rgba(232,200,116,.10), transparent 35%),
      radial-gradient(circle at 85% 10%, rgba(232,200,116,.08), transparent 32%),
      linear-gradient(180deg,var(--bg-dark) 0%, var(--bg-coffee) 60%, var(--bg-coffee-2) 100%);
    color:var(--on-dark);overflow:hidden;
  }
  #hero .wrap{display:grid;grid-template-columns:1.05fr .95fr;gap:56px;align-items:center;}
  @media (max-width:900px){ #hero .wrap{grid-template-columns:1fr;} #hero{padding-top:140px;} }
  #hero .tag-hi{font-size:15px;color:var(--gold-light);letter-spacing:.4px;margin-bottom:14px;font-style:italic;}
  #hero h1{font-size:clamp(42px,6.4vw,72px);line-height:1.02;margin:0 0 18px;letter-spacing:1px;}
  #hero p.desc{color:rgba(243,233,210,.78);font-size:17px;max-width:440px;line-height:1.7;margin:0 0 32px;}
  #hero .cta-row{display:flex;gap:16px;flex-wrap:wrap;}
  .hero-art{position:relative;}
  .hero-art svg{width:100%;height:auto;}

  /* ---------- Featured Flavors ---------- */
  #flavors{background:var(--cream);}
  .flavor-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:28px;}
  @media (max-width:720px){.flavor-grid{grid-template-columns:1fr;}}
  .p-card{
    background:#fff;border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);
    border:1px solid rgba(44,23,16,.06);
    opacity:0;transform:translateY(18px);transition:opacity .6s ease, transform .6s ease;
  }
  .p-card.in{opacity:1;transform:translateY(0);}
  .p-card .art{aspect-ratio:4/3;background:linear-gradient(160deg,#efe2c9,#e4d2a8);display:flex;align-items:center;justify-content:center;padding:20px;}
  .p-card .art svg{width:78%;}
  .p-card .body{padding:22px 24px 26px;}
  .p-card h3{font-size:21px;margin:0 0 6px;}
  .p-card p{color:var(--ink-soft);font-size:14.5px;line-height:1.6;margin:0 0 16px;}
  .p-card .row{display:flex;align-items:center;justify-content:space-between;}
  .p-card .price{font-weight:700;color:var(--ink);font-size:18px;}
  .add-btn{
    background:var(--bg-dark);color:var(--gold-light);border:none;border-radius:999px;
    padding:10px 18px;font-size:13px;font-weight:600;cursor:pointer;transition:.2s ease;
  }
  .add-btn:hover{background:var(--gold);color:var(--bg-dark);}

  /* ---------- Why us ---------- */
  #why{background:linear-gradient(180deg,var(--bg-coffee-2),var(--bg-dark));color:var(--on-dark);}
  .why-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:22px;}
  @media (max-width:900px){.why-grid{grid-template-columns:repeat(2,1fr);}}
  @media (max-width:520px){.why-grid{grid-template-columns:1fr;}}
  .why-card{
    border:1px solid rgba(201,162,39,.22);border-radius:16px;padding:26px 22px;
    background:rgba(255,255,255,.02);
    opacity:0;transform:translateY(18px);transition:opacity .6s ease, transform .6s ease;
  }
  .why-card.in{opacity:1;transform:translateY(0);}
  .why-card .ic{width:40px;height:40px;margin-bottom:16px;stroke:var(--gold-light);fill:none;stroke-width:1.6;}
  .why-card h3{font-family:'Jost',sans-serif;font-size:16px;font-weight:600;margin:0 0 8px;color:var(--on-dark);}
  .why-card p{font-size:13.5px;color:rgba(243,233,210,.68);line-height:1.6;margin:0;}

  /* ---------- About ---------- */
  #about{background:var(--cream-2);}
  .about-grid{display:grid;grid-template-columns:.9fr 1.1fr;gap:56px;align-items:center;}
  @media (max-width:860px){.about-grid{grid-template-columns:1fr;}}
  #about p{color:var(--ink-soft);font-size:16px;line-height:1.8;margin:0 0 16px;}
  .about-art{border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);background:linear-gradient(160deg,#2c1710,#1c0d06);padding:36px;}

  /* ---------- Menu ---------- */
  #menu{background:var(--cream);}
  .menu-tools{display:flex;flex-wrap:wrap;gap:14px;align-items:center;justify-content:space-between;margin-bottom:34px;}
  .filters{display:flex;gap:10px;flex-wrap:wrap;}
  .filter-chip{
    border:1px solid rgba(44,23,16,.18);background:#fff;color:var(--ink);
    padding:9px 18px;border-radius:999px;font-size:13.5px;cursor:pointer;transition:.2s ease;
  }
  .filter-chip.active{background:var(--bg-dark);color:var(--gold-light);border-color:var(--bg-dark);}
  #menu-search{
    border:1px solid rgba(44,23,16,.18);border-radius:999px;padding:10px 18px;font-size:14px;
    font-family:'Jost',sans-serif;min-width:220px;background:#fff;
  }
  #menu-search:focus{outline:2px solid var(--gold);outline-offset:1px;}
  #menu-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:24px;}
  @media (max-width:900px){#menu-grid{grid-template-columns:repeat(2,1fr);}}
  @media (max-width:600px){#menu-grid{grid-template-columns:1fr;}}
  #menu-empty{display:none;text-align:center;padding:50px 20px;color:var(--ink-soft);border:1px dashed rgba(44,23,16,.25);border-radius:16px;}
  #menu-empty h3{margin:0 0 8px;font-size:19px;color:var(--ink);}

  /* ---------- How to order ---------- */
  #how{background:linear-gradient(180deg,var(--bg-dark),var(--bg-coffee));color:var(--on-dark);}
  .steps{display:grid;grid-template-columns:repeat(3,1fr);gap:30px;counter-reset:step;}
  @media (max-width:800px){.steps{grid-template-columns:1fr;}}
  .step{position:relative;padding:30px 24px 24px;border:1px solid rgba(201,162,39,.22);border-radius:16px;}
  .step .num{
    font-family:'Playfair Display',serif;font-size:34px;color:var(--gold-light);opacity:.55;margin-bottom:10px;
  }
  .step h3{font-size:18px;margin:0 0 8px;}
  .step p{font-size:14px;color:rgba(243,233,210,.7);line-height:1.6;margin:0;}

  /* ---------- Location ---------- */
  #location{background:var(--cream-2);}
  .loc-grid{display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:stretch;}
  @media (max-width:900px){.loc-grid{grid-template-columns:1fr;}}
  .loc-info{display:flex;flex-direction:column;justify-content:center;gap:18px;}
  .loc-info .addr{font-size:18px;font-weight:600;line-height:1.5;}
  .loc-info .sub{color:var(--ink-soft);font-size:14.5px;}
  .banner{
    display:inline-flex;align-items:center;gap:10px;background:rgba(201,162,39,.14);
    border:1px solid rgba(201,162,39,.35);color:var(--ink);padding:10px 16px;border-radius:12px;
    font-size:13.5px;font-weight:600;width:fit-content;
  }
  .delivery-rates{
    border:1px solid rgba(44,23,16,.15);border-radius:14px;padding:16px 18px;
    background:rgba(255,255,255,.55);max-width:320px;
  }
  .delivery-rates h4{margin:0 0 10px;font-size:12.5px;letter-spacing:1.4px;text-transform:uppercase;color:var(--ink-soft);font-weight:600;}
  .delivery-rates ul li{display:flex;justify-content:space-between;gap:12px;font-size:14px;padding:7px 0;border-bottom:1px dashed rgba(44,23,16,.15);}
  .delivery-rates ul li:last-child{border-bottom:none;}
  .delivery-rates ul li span:last-child{font-weight:700;color:var(--ink);}
  .map-frame{border-radius:var(--radius);overflow:hidden;box-shadow:var(--shadow);min-height:320px;border:1px solid rgba(44,23,16,.08);}
  .map-frame iframe{width:100%;height:100%;min-height:320px;border:0;display:block;}

  /* ---------- Contact ---------- */
  #contact{background:linear-gradient(180deg,var(--bg-coffee),var(--bg-dark));color:var(--on-dark);}
  .contact-grid{display:grid;grid-template-columns:.9fr 1.1fr;gap:48px;}
  @media (max-width:860px){.contact-grid{grid-template-columns:1fr;}}
  .contact-actions{display:flex;flex-direction:column;gap:14px;margin-top:22px;}
  .contact-actions a{
    display:flex;align-items:center;gap:12px;border:1px solid rgba(201,162,39,.3);border-radius:12px;
    padding:14px 16px;font-size:14.5px;color:var(--on-dark);
  }
  .contact-actions a:hover{background:rgba(201,162,39,.08);}
  .contact-actions svg{width:18px;height:18px;stroke:var(--gold-light);fill:none;stroke-width:1.6;flex-shrink:0;}
  form#contact-form{display:flex;flex-direction:column;gap:14px;}
  form#contact-form input, form#contact-form textarea{
    background:rgba(255,255,255,.04);border:1px solid rgba(201,162,39,.28);border-radius:10px;
    padding:13px 14px;color:var(--on-dark);font-family:'Jost',sans-serif;font-size:14.5px;
  }
  form#contact-form input::placeholder, form#contact-form textarea::placeholder{color:rgba(243,233,210,.45);}
  form#contact-form input:focus, form#contact-form textarea:focus{outline:2px solid var(--gold);outline-offset:1px;}
  #form-status{font-size:13.5px;color:var(--gold-light);min-height:18px;}

  /* ---------- Footer ---------- */
  footer{background:var(--bg-dark);color:rgba(243,233,210,.65);padding:56px 24px 26px;}
  .foot-grid{display:grid;grid-template-columns:1.3fr 1fr 1fr;gap:36px;margin-bottom:36px;}
  @media (max-width:700px){.foot-grid{grid-template-columns:1fr;}}
  footer h4{color:var(--on-dark);font-size:14px;letter-spacing:1px;margin:0 0 14px;font-family:'Jost',sans-serif;font-weight:600;}
  footer ul li{margin-bottom:9px;font-size:14px;}
  footer ul li a:hover{color:var(--gold-light);}
  .foot-bottom{border-top:1px solid rgba(201,162,39,.15);padding-top:20px;font-size:12.5px;display:flex;justify-content:space-between;flex-wrap:wrap;gap:10px;}

  /* ---------- Cart drawer ---------- */
  #cart-overlay{position:fixed;inset:0;background:rgba(28,13,6,.5);z-index:199;opacity:0;pointer-events:none;transition:opacity .25s ease;}
  #cart-overlay.open{opacity:1;pointer-events:auto;}
  #cart-drawer{
    position:fixed;top:0;right:0;height:100%;width:min(400px,92vw);background:var(--cream);z-index:200;
    box-shadow:-14px 0 40px rgba(0,0,0,.25);transform:translateX(100%);transition:transform .3s ease;
    display:flex;flex-direction:column;
  }
  #cart-drawer.open{transform:translateX(0);}
  .cart-head{display:flex;justify-content:space-between;align-items:center;padding:20px 22px;border-bottom:1px solid rgba(44,23,16,.1);}
  .cart-head h3{margin:0;font-size:19px;}
  #cart-close{background:none;border:none;font-size:22px;cursor:pointer;color:var(--ink);}
  #cart-items{flex:1;overflow-y:auto;padding:16px 22px;}
  .cart-item{display:flex;gap:12px;align-items:center;padding:14px 0;border-bottom:1px solid rgba(44,23,16,.08);}
  .cart-item .ci-name{flex:1;font-size:14.5px;font-weight:600;}
  .cart-item .ci-price{font-size:13px;color:var(--ink-soft);}
  .qty{display:flex;align-items:center;gap:8px;}
  .qty button{width:26px;height:26px;border-radius:50%;border:1px solid rgba(44,23,16,.25);background:#fff;cursor:pointer;font-size:14px;line-height:1;}
  .qty span{min-width:16px;text-align:center;font-size:14px;}
  .ci-remove{background:none;border:none;color:#a9432b;font-size:12px;cursor:pointer;margin-left:8px;}
  #cart-empty{color:var(--ink-soft);font-size:14px;padding:30px 0;text-align:center;}
  .cart-foot{padding:18px 22px 24px;border-top:1px solid rgba(44,23,16,.1);}
  .cart-total-row{display:flex;justify-content:space-between;font-size:15px;font-weight:700;margin-bottom:8px;}
  .cart-total-row.cart-total-sub{font-size:13.5px;font-weight:500;color:var(--ink-soft);}
  .cart-total-row.cart-grand{border-top:1px dashed rgba(44,23,16,.2);padding-top:10px;margin-top:2px;margin-bottom:16px;}
  .cart-foot .btn{width:100%;justify-content:center;}
  .cart-customer{display:flex;flex-direction:column;gap:10px;margin-bottom:16px;}
  .cart-customer input{
    border:1px solid rgba(44,23,16,.2);border-radius:10px;padding:11px 14px;font-size:14px;
    font-family:'Jost',sans-serif;background:#fff;color:var(--ink);
  }
  .cart-customer input:focus{outline:2px solid var(--gold);outline-offset:1px;}
  .cart-customer input.invalid{border-color:#a9432b;}
  #cust-error{color:#a9432b;font-size:12.5px;min-height:16px;}
  #map-hint{font-size:11.5px;color:var(--ink-soft);}
  #delivery-map{height:170px;border-radius:10px;overflow:hidden;border:1px solid rgba(44,23,16,.2);}
  #delivery-summary{font-size:13px;font-weight:600;color:var(--ink);}
  #delivery-summary.out-of-range{color:#a9432b;}
  .stall-pin{background:var(--gold);border:2px solid var(--bg-dark);border-radius:50%;width:14px;height:14px;}
  .cust-pin{background:#a9432b;border:2px solid #fff;border-radius:50%;width:14px;height:14px;}

  .reveal{opacity:0;transform:translateY(18px);transition:opacity .6s ease, transform .6s ease;}
  .reveal.in{opacity:1;transform:translateY(0);}
  .sr-only{position:absolute;width:1px;height:1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;}
  :focus-visible{outline:2px solid var(--gold);outline-offset:2px;}
</style>
</head>
<body>

<!-- ================= NAV ================= -->
<nav id="nav">
  <div class="wrap">
    <a href="#hero" class="brand">
      <span class="mark">TH</span>
      <span class="word">Tiramisu Hub</span>
    </a>
    <ul id="nav-links">
      <li><a href="#flavors">Flavors</a></li>
      <li><a href="#why">Why Us</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#menu">Menu</a></li>
      <li><a href="#how">How to Order</a></li>
      <li><a href="#location">Location</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div id="nav-actions">
      <button id="cart-toggle" aria-label="Open cart">
        <svg viewBox="0 0 24 24" fill="none" stroke-linecap="round" stroke-linejoin="round"><path d="M3 4h2l2.6 12.4a2 2 0 0 0 2 1.6h7.7a2 2 0 0 0 2-1.6L21 8H6"/><circle cx="10" cy="21" r="1"/><circle cx="18" cy="21" r="1"/></svg>
        <span id="cart-count">0</span>
      </button>
      <button id="nav-burger" aria-label="Toggle menu" aria-expanded="false">&#9776;</button>
    </div>
  </div>
</nav>

<!-- ================= HERO ================= -->
<header id="hero">
  <div class="wrap">
    <div>
      <div class="tag-hi">Har Layer Mein Swaad, Har Bite Mein Khushiyan.</div>
      <h1>TIRAMISU<br>HUB</h1>
      <p class="desc">Freshly crafted, rich &amp; creamy tiramisu made with love — served straight from our kitchen in Motihari.</p>
      <div class="cta-row">
        <a href="#menu" class="btn btn-gold">Order Now</a>
        <a href="#flavors" class="btn btn-outline">Explore Flavors</a>
      </div>
    </div>
    <div class="hero-art">
      <svg viewBox="0 0 420 360" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <linearGradient id="gCup" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="#f6ecd9"/>
            <stop offset="100%" stop-color="#d8b98a"/>
          </linearGradient>
          <linearGradient id="gLayer" x1="0" y1="0" x2="0" y2="1">
            <stop offset="0%" stop-color="#8a5a34"/>
            <stop offset="100%" stop-color="#5c3a20"/>
          </linearGradient>
        </defs>
        <ellipse cx="210" cy="322" rx="150" ry="18" fill="#000" opacity=".18"/>
        <path d="M110 120 L140 300 Q210 320 280 300 L310 120 Z" fill="url(#gCup)"/>
        <path d="M118 150 L302 150 L296 190 L124 190 Z" fill="url(#gLayer)" opacity=".92"/>
        <path d="M124 210 L296 210 L290 250 L130 250 Z" fill="url(#gLayer)" opacity=".8"/>
        <path d="M116 120 Q210 100 304 120 L296 150 L124 150 Z" fill="#efe2c9"/>
        <g fill="#4a2f1c" opacity=".65">
          <circle cx="150" cy="112" r="2.4"/><circle cx="172" cy="106" r="2.4"/><circle cx="196" cy="114" r="2.4"/>
          <circle cx="220" cy="105" r="2.4"/><circle cx="244" cy="113" r="2.4"/><circle cx="268" cy="107" r=
