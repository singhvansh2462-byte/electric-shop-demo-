<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="description" content="NYTRIXX Electricity Shop — premium electrical products & services" />
  <title>NYTRIXX Electricity Shop</title>

  <style>
    :root{
      --bg: #fbfbf8;
      --panel: rgba(255,255,255,.75);
      --panel-strong: rgba(255,255,255,.92);
      --text: #0f172a;
      --muted: rgba(15,23,42,.72);
      --border: rgba(15,23,42,.12);
      --shadow: 0 20px 50px rgba(2, 6, 23, .12);
      --shadow-soft: 0 12px 32px rgba(2, 6, 23, .10);

      --blue: #2a4dff; /* royal */
      --cyan: #00d4ff;
      --gold: #f6c453;

      --glow-blue: rgba(42, 77, 255, .45);
      --glow-cyan: rgba(0, 212, 255, .40);
      --glow-gold: rgba(246, 196, 83, .40);

      --radius: 18px;
      --radius-sm: 12px;

      --ring: 0 0 0 4px rgba(0,212,255,.18);
      --ease: cubic-bezier(.2,.8,.2,1);

      --hero-grad:
        radial-gradient(900px 500px at 15% 15%, rgba(0,212,255,.18), transparent 60%),
        radial-gradient(700px 420px at 75% 15%, rgba(42,77,255,.14), transparent 62%),
        radial-gradient(600px 420px at 50% 80%, rgba(246,196,83,.10), transparent 60%),
        linear-gradient(180deg, rgba(255,255,255,0.2), rgba(255,255,255,0.6));
    }

    [data-theme="dark"]{
      --bg: #070b18;
      --panel: rgba(13, 20, 50, .55);
      --panel-strong: rgba(13, 20, 50, .82);
      --text: #eaf2ff;
      --muted: rgba(234,242,255,.70);
      --border: rgba(234,242,255,.14);
      --shadow: 0 24px 70px rgba(0, 0, 0, .45);
      --shadow-soft: 0 14px 40px rgba(0, 0, 0, .35);

      --glow-blue: rgba(42, 77, 255, .55);
      --glow-cyan: rgba(0, 212, 255, .50);
      --glow-gold: rgba(246, 196, 83, .44);

      --hero-grad:
        radial-gradient(900px 500px at 15% 15%, rgba(0,212,255,.25), transparent 60%),
        radial-gradient(700px 420px at 75% 15%, rgba(42,77,255,.22), transparent 62%),
        radial-gradient(600px 420px at 50% 80%, rgba(246,196,83,.16), transparent 60%),
        linear-gradient(180deg, rgba(7,11,24,0.3), rgba(7,11,24,0.9));
    }

    *{ box-sizing: border-box; }
    html{ scroll-behavior: smooth; }

    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji","Segoe UI Emoji";
      background: var(--bg);
      color: var(--text);
      overflow-x: hidden;
    }

    :focus-visible{ outline: none; box-shadow: var(--ring); border-radius: 10px; }
    a{ color: inherit; text-decoration: none; }

    .container{ width: min(1140px, 92vw); margin: 0 auto; }

    header{
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(12px);
      background: color-mix(in oklab, var(--bg) 70%, transparent);
      border-bottom: 1px solid var(--border);
    }

    .nav{ display:flex; align-items:center; justify-content: space-between; padding: 14px 0; gap: 14px; }

    .brand{ display:flex; align-items:center; gap: 12px; min-width: 220px; }

    .logoMark{
      width: 40px; height: 40px; border-radius: 14px;
      background: linear-gradient(135deg, rgba(42,77,255,.18), rgba(0,212,255,.25));
      border: 1px solid rgba(0,212,255,.22);
      box-shadow: 0 0 0 1px rgba(255,255,255,.04) inset, 0 12px 26px rgba(0, 212, 255, .18);
      position: relative; overflow:hidden;
    }
    .logoMark:before{
      content:"";
      position:absolute; inset:-40%;
      background: conic-gradient(from 180deg, rgba(0,212,255,.0), rgba(0,212,255,.55), rgba(42,77,255,.35), rgba(246,196,83,.35), rgba(0,212,255,.0));
      animation: spin 6s linear infinite;
      opacity:.9;
    }
    .logoMark:after{
      content:"";
      position:absolute; inset: 10px;
      border-radius: 12px;
      background:
        radial-gradient(circle at 30% 30%, rgba(255,255,255,.35), transparent 60%),
        linear-gradient(180deg, rgba(42,77,255,.12), rgba(0,212,255,.08));
      border: 1px solid rgba(255,255,255,.22);
      box-shadow: 0 0 30px rgba(0,212,255,.25);
    }
    @keyframes spin{ to{ transform: rotate(360deg); } }

    .brandText{ display:flex; flex-direction:column; line-height:1.05; }
    .brandText strong{
      font-weight: 950; letter-spacing: .2px;
      background: linear-gradient(90deg, var(--blue), var(--cyan), var(--gold));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      filter: drop-shadow(0 10px 25px rgba(0,212,255,.25));
      text-shadow: 0 0 18px rgba(42,77,255,.18);
      font-size: 14px;
    }
    .brandText span{ font-size: 12.5px; color: var(--muted); font-weight: 700; }

    nav ul{ list-style:none; display:flex; gap: 18px; padding:0; margin:0; align-items:center; }
    nav a{
      text-decoration:none; color: var(--muted);
      font-weight: 850; font-size: 13.5px;
      padding: 10px 12px; border-radius: 999px;
      transition: background .2s var(--ease), color .2s var(--ease), transform .2s var(--ease);
      white-space: nowrap;
    }
    nav a:hover{ color: var(--text); background: rgba(0,212,255,.08); transform: translateY(-1px); }

    .navRight{ display:flex; align-items:center; gap: 12px; }

    .togglePill{
      width: 58px; height: 34px; border-radius: 999px;
      border: 1px solid var(--border);
      background: var(--panel);
      box-shadow: 0 10px 22px rgba(0,0,0,.06);
      position: relative;
      cursor: pointer;
      display:flex; align-items:center; padding: 0 6px;
      transition: transform .2s var(--ease);
      user-select:none;
    }
    .togglePill:hover{ transform: translateY(-1px); }
    .toggleKnob{
      width: 26px; height: 26px; border-radius: 999px;
      background: linear-gradient(180deg, rgba(255,255,255,.9), rgba(255,255,255,.55));
      border: 1px solid rgba(0,212,255,.25);
      display:grid; place-items:center;
      position:absolute; top: 50%; transform: translateY(-50%);
      left: 6px;
      transition: left .35s var(--ease), background .35s var(--ease);
      box-shadow: 0 14px 30px rgba(0,212,255,.22);
    }
    [data-theme="dark"] .toggleKnob{ left: 26px; background: linear-gradient(180deg, rgba(40,60,140,.8), rgba(0,212,255,.12)); }

    .toggleIcon{ width: 14px; height: 14px; opacity: .95; filter: drop-shadow(0 8px 20px rgba(0,212,255,.25)); }

    .burger{ display:none; border: 1px solid var(--border); background: var(--panel); border-radius: 12px; padding: 10px 12px; cursor:pointer; }
    .burger span{ display:block; width: 18px; height: 2px; background: var(--text); margin: 3px 0; opacity:.75; }

    section{ padding: 72px 0; }

    .sectionHead{ display:flex; align-items:flex-end; justify-content: space-between; gap: 18px; margin-bottom: 24px; }
    .kicker{ font-weight: 950; letter-spacing: .14em; text-transform: uppercase; font-size: 12px; color: color-mix(in oklab, var(--muted) 80%, var(--cyan)); }
    h2{ margin: 6px 0 0; font-size: clamp(22px, 2.4vw, 30px); letter-spacing: -0.02em; }
    .sub{ margin: 10px 0 0; color: var(--muted); font-weight: 740; line-height: 1.55; max-width: 60ch; }

    .card{ background: var(--panel); border: 1px solid var(--border); border-radius: var(--radius); box-shadow: 0 0 0 1px rgba(255,255,255,.05) inset; }

    /* Hero */
    .hero{ position: relative; padding: 54px 0 32px; overflow:hidden; }
    .heroBg{ position:absolute; inset: -30% -10% -20%; background: var(--hero-grad); pointer-events:none; }

    .sparks{ position:absolute; inset: 0; pointer-events:none; opacity: .95; }

    .heroGrid{ display:grid; grid-template-columns: 1.1fr .9fr; gap: 24px; align-items:center; position: relative; }
    .heroLeft{ padding: 26px 0; }

    .glowTitle{
      font-size: clamp(34px, 4.2vw, 56px);
      line-height: 1.02;
      margin: 10px 0;
      font-weight: 1000;
      letter-spacing: -0.045em;
      background: linear-gradient(90deg, var(--blue), var(--cyan), var(--gold));
      -webkit-background-clip:text;
      background-clip:text;
      color: transparent;
      filter: drop-shadow(0 18px 40px rgba(0,212,255,.22));
      text-shadow: 0 0 25px rgba(42,77,255,.22);
    }

    .heroTag{ color: var(--muted); font-weight: 820; font-size: clamp(14px, 1.5vw, 18px); line-height: 1.6; }

    .ctaRow{ display:flex; align-items:center; gap: 14px; flex-wrap: wrap; margin-top: 18px; }

    .btn{
      cursor:pointer; border: 1px solid var(--border);
      background: var(--panel-strong);
      color: var(--text);
      padding: 12px 16px;
      border-radius: 14px;
      font-weight: 950;
      letter-spacing: .01em;
      transition: transform .2s var(--ease), box-shadow .2s var(--ease), border-color .2s var(--ease), background .2s var(--ease);
      box-shadow: 0 14px 32px rgba(2,6,23,.08);
      display:inline-flex; align-items:center; gap: 10px;
      user-select:none;
    }
    .btn:hover{ transform: translateY(-2px); box-shadow: 0 20px 44px rgba(2,6,23,.12); border-color: rgba(0,212,255,.35); }

    .btnPrimary{
      border-color: rgba(0,212,255,.35);
      background: linear-gradient(135deg, rgba(42,77,255,.18), rgba(0,212,255,.12));
      box-shadow: 0 18px 44px rgba(0,212,255,.20);
    }

    .btnIcon{ width: 26px; height: 26px; border-radius: 10px; display:grid; place-items:center; background: linear-gradient(180deg, rgba(0,212,255,.18), rgba(42,77,255,.12)); border: 1px solid rgba(0,212,255,.25); }

    .heroRight{ position: relative; }
    .heroPanel{
      padding: 16px;
      border-radius: var(--radius);
      background: linear-gradient(180deg, rgba(255,255,255,.72), rgba(255,255,255,.44));
      border: 1px solid rgba(0,212,255,.20);
      box-shadow: var(--shadow-soft);
      overflow:hidden;
      transform: translateZ(0);
    }
    [data-theme="dark"] .heroPanel{ background: linear-gradient(180deg, rgba(13,20,50,.70), rgba(13,20,50,.35)); }

    .heroStats{ display:grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-top: 12px; }
    .stat{ padding: 14px; border-radius: 16px; background: rgba(255,255,255,.58); border: 1px solid rgba(0,212,255,.16); }
    [data-theme="dark"] .stat{ background: rgba(13,20,50,.58); }
    .stat strong{ font-size: 20px; display:block; }
    .stat span{ color: var(--muted); font-weight: 800; font-size: 13px; line-height: 1.3; }

    .reveal{ opacity: 0; transform: translateY(18px); transition: opacity .7s var(--ease), transform .7s var(--ease); }
    .reveal.in{ opacity: 1; transform: translateY(0); }

    /* Products */
    .filters{ display:flex; gap: 10px; flex-wrap: wrap; align-items:center; }
    .chip{
      border-radius: 999px;
      padding: 10px 12px;
      border: 1px solid var(--border);
      background: var(--panel);
      color: var(--muted);
      font-weight: 950;
      cursor:pointer;
      transition: transform .2s var(--ease), box-shadow .2s var(--ease), background .2s var(--ease), color .2s var(--ease), border-color .2s var(--ease);
      user-select:none;
      font-size: 13px;
    }
    .chip:hover{ transform: translateY(-2px); border-color: rgba(0,212,255,.3); color: var(--text); }
    .chip.active{ color: var(--text); border-color: rgba(0,212,255,.35); background: linear-gradient(135deg, rgba(0,212,255,.16), rgba(42,77,255,.10)); box-shadow: 0 16px 40px rgba(0,212,255,.14); }

    .productGrid{ display:grid; grid-template-columns: repeat(3, 1fr); gap: 16px; margin-top: 18px; }

    .productCard{ padding: 14px; position: relative; overflow:hidden; transition: transform .25s var(--ease), box-shadow .25s var(--ease), border-color .25s var(--ease); }
    .productCard:hover{ transform: translateY(-6px); border-color: rgba(0,212,255,.35); box-shadow: 0 22px 60px rgba(0,212,255,.14); }
    .productCard:before{
      content:"";
      position:absolute; inset:-2px;
      background:
        radial-gradient(300px 120px at 20% 0%, rgba(0,212,255,.20), transparent 60%),
        radial-gradient(260px 120px at 90% 0%, rgba(42,77,255,.18), transparent 58%),
        radial-gradient(260px 140px at 40% 120%, rgba(246,196,83,.14), transparent 60%);
      opacity: 0;
      transition: opacity .25s var(--ease);
      pointer-events:none;
    }
    .productCard:hover:before{ opacity: 1; }

    .productTop{ display:flex; align-items:flex-start; justify-content:space-between; gap: 12px; position:relative; z-index:1; }
    .productImg{
      width: 62px; height: 62px; border-radius: 18px;
      background: linear-gradient(180deg, rgba(0,212,255,.16), rgba(42,77,255,.08));
      border: 1px solid rgba(0,212,255,.22);
      box-shadow: 0 18px 40px rgba(0,212,255,.12);
      display:grid; place-items:center;
      flex: 0 0 auto;
      position:relative; overflow:hidden;
    }
    .productImg svg{ width: 36px; height: 36px; }

    .productBody{ margin-top: 12px; position:relative; z-index:1; }
    .productName{ font-weight: 1000; letter-spacing:-.01em; font-size: 15px; }
    .price{ margin-top: 8px; font-weight: 1000; font-size: 16px; color: color-mix(in oklab, var(--blue) 55%, var(--text)); }
    .productMeta{ margin-top: 6px; color: var(--muted); font-weight: 850; font-size: 12.5px; line-height: 1.35; }

    .addRow{ display:flex; gap: 10px; align-items:center; justify-content:space-between; margin-top: 12px; position:relative; z-index:1; }

    .qtyPill{ display:flex; align-items:center; gap: 8px; border: 1px solid var(--border); border-radius: 999px; padding: 8px 10px; background: rgba(255,255,255,.45); }
    [data-theme="dark"] .qtyPill{ background: rgba(13,20,50,.45); }
    .qtyPill button{ width: 28px; height: 28px; border-radius: 10px; border: 1px solid var(--border); background: var(--panel); cursor:pointer; font-weight: 1000; color: var(--text); transition: transform .2s var(--ease), border-color .2s var(--ease); }
    .qtyPill button:hover{ transform: translateY(-1px); border-color: rgba(0,212,255,.3); }
    .qtyPill span{ min-width: 18px; text-align:center; font-weight: 1000; }

    /* Services */
    .servicesGrid{ display:grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
    .serviceCard{ padding: 18px; position:relative; overflow:hidden; transition: transform .25s var(--ease), box-shadow .25s var(--ease), border-color .25s var(--ease); }
    .serviceCard:hover{ transform: translateY(-6px); border-color: rgba(0,212,255,.35); box-shadow: 0 26px 70px rgba(42,77,255,.15); }

    .serviceIconWrap{
      width: 54px; height: 54px; border-radius: 18px;
      display:grid; place-items:center;
      border: 1px solid rgba(0,212,255,.22);
      background: linear-gradient(180deg, rgba(0,212,255,.18), rgba(42,77,255,.10));
      box-shadow: 0 20px 50px rgba(0,212,255,.16);
      transform: translateZ(0);
      transition: transform .35s var(--ease), filter .35s var(--ease);
    }
    .serviceCard:hover .serviceIconWrap{ transform: rotateX(18deg) rotateY(-18deg) translateY(-3px); filter: saturate(1.25) drop-shadow(0 18px 26px rgba(0,212,255,.18)); }
    .serviceIconWrap svg{ width: 26px; height: 26px; }

    .serviceTitle{ margin-top: 14px; font-weight: 1000; letter-spacing: -.01em; }
    .serviceText{ margin-top: 8px; color: var(--muted); font-weight: 830; line-height: 1.55; font-size: 13.5px; }

    /* About */
    .aboutGrid{ display:grid; grid-template-columns: 1fr 1fr; gap: 16px; }
    .aboutCard{ padding: 18px; }
    .trustedPill{ display:inline-flex; align-items:center; gap: 10px; padding: 12px 14px; border-radius: 999px; border: 1px solid rgba(0,212,255,.25); background: linear-gradient(135deg, rgba(0,212,255,.14), rgba(42,77,255,.08)); box-shadow: 0 18px 44px rgba(0,212,255,.14); font-weight: 1000; margin-top: 14px; }

    /* Testimonials */
    .slider{ position:relative; overflow:hidden; }
    .slides{ display:flex; transition: transform .6s var(--ease); will-change: transform; }
    .slide{ min-width: 100%; padding: 12px; }
    .testimonialCard{ padding: 20px; height: 100%; }
    .quote{ font-size: 16px; line-height: 1.7; font-weight: 850; color: var(--muted); }
    .person{ margin-top: 14px; display:flex; align-items:center; gap: 12px; }
    .avatar{ width: 40px; height: 40px; border-radius: 14px; background: linear-gradient(135deg, rgba(0,212,255,.20), rgba(246,196,83,.10)); border: 1px solid rgba(0,212,255,.22); display:grid; place-items:center; font-weight: 1000; }
    .person strong{ font-weight: 1000; }
    .person span{ color: var(--muted); font-weight: 850; font-size: 12.5px; }

    .dots{ display:flex; gap: 10px; justify-content:center; margin-top: 14px; }
    .dot{ width: 10px; height: 10px; border-radius: 999px; border: 1px solid var(--border); background: transparent; cursor:pointer; transition: transform .2s var(--ease), background .2s var(--ease), border-color .2s var(--ease); }
    .dot.active{ background: linear-gradient(135deg, rgba(42,77,255,.55), rgba(0,212,255,.40)); border-color: rgba(0,212,255,.45); transform: scale(1.2); }

    /* FAQ */
    .faq{ display:grid; grid-template-columns: 1fr; gap: 12px; }
    details.faqItem{ border: 1px solid var(--border); background: var(--panel); border-radius: var(--radius-sm); overflow:hidden; }
    details.faqItem summary{
      cursor:pointer;
      list-style:none;
      padding: 16px 16px;
      font-weight: 1000;
      display:flex;
      align-items:center;
      justify-content: space-between;
      gap: 12px;
    }
    details.faqItem summary::-webkit-details-marker{ display:none; }
    .faqIcon{ width: 28px; height: 28px; border-radius: 12px; border: 1px solid rgba(0,212,255,.22); background: rgba(0,212,255,.10); display:grid; place-items:center; transition: transform .25s var(--ease); }
    details[open] .faqIcon{ transform: rotate(45deg); }
    .faqBody{ padding: 0 16px 16px; color: var(--muted); font-weight: 850; line-height: 1.65; }

    /* Contact */
    .contactGrid{ display:grid; grid-template-columns: 1fr 1fr; gap: 16px; }
    .contactCard{ padding: 18px; }
    .contactList{ display:grid; gap: 12px; margin-top: 14px; }
    .contactRow{ display:flex; align-items:flex-start; gap: 12px; }
    .contactRow svg{ width: 18px; height: 18px; margin-top: 2px; }
    .contactRow strong{ font-weight: 1000; display:block; }
    .contactRow span{ color: var(--muted); font-weight: 850; line-height: 1.4; }

    form{ display:grid; gap: 12px; }
    .field{ display:grid; gap: 8px; }
    label{ font-weight: 1000; }
    input, textarea{
      width:100%;
      border-radius: 14px;
      border: 1px solid var(--border);
      background: rgba(255,255,255,.45);
      color: var(--text);
      padding: 12px 12px;
      font-weight: 850;
      transition: border-color .2s var(--ease), box-shadow .2s var(--ease), background .2s var(--ease);
    }
    [data-theme="dark"] input, [data-theme="dark"] textarea{ background: rgba(13,20,50,.45); }
    input:focus, textarea:focus{ border-color: rgba(0,212,255,.45); box-shadow: 0 0 0 4px rgba(0,212,255,.14); outline:none; }
    textarea{ min-height: 120px; resize: vertical; }

    .formHint{ color: var(--muted); font-weight: 850; font-size: 12.5px; line-height: 1.45; }
    .toast{
      position: fixed;
      right: 18px;
      bottom: 18px;
      z-index: 100;
      background: linear-gradient(135deg, rgba(42,77,255,.22), rgba(0,212,255,.12));
      border: 1px solid rgba(0,212,255,.35);
      color: var(--text);
      box-shadow: 0 20px 60px rgba(0,212,255,.15);
      border-radius: 16px;
      padding: 12px 14px;
      font-weight: 950;
      transform: translateY(20px);
      opacity: 0;
      transition: transform .25s var(--ease), opacity .25s var(--ease);
      pointer-events:none;
      max-width: min(360px, 80vw);
    }
    .toast.show{ transform: translateY(0); opacity: 1; }

    /* Footer */
    footer{ padding: 28px 0 40px; border-top: 1px solid var(--border); }
    .footerGrid{ display:flex; align-items:center; justify-content: space-between; gap: 16px; flex-wrap: wrap; }
    .footerLeft{ font-weight: 900; color: var(--muted); }
    .social{ display:flex; gap: 10px; }
    .social a{ width: 40px; height: 40px; border-radius: 16px; border: 1px solid var(--border); background: var(--panel); display:grid; place-items:center; transition: transform .2s var(--ease), box-shadow .2s var(--ease), border-color .2s var(--ease); }
    .social a:hover{ transform: translateY(-2px); border-color: rgba(0,212,255,.35); box-shadow: 0 22px 60px rgba(0,212,255,.14); }
    .social svg{ width: 18px; height: 18px; }

    /* Floating Cart */
    .cartFab{
      position: fixed;
      right: 18px;
      bottom: 18px;
      z-index: 80;
      display:flex;
      align-items:center;
      gap: 10px;
      padding: 12px 14px;
      border-radius: 999px;
      border: 1px solid rgba(0,212,255,.35);
      background: linear-gradient(135deg, rgba(42,77,255,.18), rgba(0,212,255,.12));
      box-shadow: 0 22px 70px rgba(0,212,255,.18);
      cursor:pointer;
      user-select:none;
      transform: translateY(0);
      transition: transform .2s var(--ease), box-shadow .2s var(--ease);
    }
    .cartFab:hover{ transform: translateY(-3px); box-shadow: 0 28px 90px rgba(0,212,255,.24); }
    .cartFab .badge{ width: 26px; height: 26px; border-radius: 999px; background: rgba(0,212,255,.18); border: 1px solid rgba(0,212,255,.35); display:grid; place-items:center; font-weight: 1000; }

    /* Responsive */
    @media (max-width: 980px){
      .heroGrid{ grid-template-columns: 1fr; }
      .productGrid{ grid-template-columns: repeat(2, 1fr); }
      .servicesGrid{ grid-template-columns: repeat(2, 1fr); }
      .aboutGrid{ grid-template-columns: 1fr; }
      .contactGrid{ grid-template-columns: 1fr; }
      nav ul{ display:none; }
      .burger{ display:block; }
    }

    @media (max-width: 640px){
      section{ padding: 60px 0; }
      .productGrid{ grid-template-columns: 1fr; }
      .servicesGrid{ grid-template-columns: 1fr; }
    }

    /* Mobile menu */
    .mobileMenu{
      display:none;
      padding: 12px 0 18px;
      border-top: 1px solid var(--border);
    }
    .mobileMenu.open{ display:block; }
    .mobileMenu a{ display:block; padding: 10px 12px; border-radius: 14px; color: var(--muted); font-weight: 950; background: rgba(255,255,255,.25); margin-top: 8px; border: 1px solid rgba(255,255,255,.0); }
    [data-theme="dark"] .mobileMenu a{ background: rgba(13,20,50,.35); }

  </style>
</head>
<body data-theme="light">
  <header>
    <div class="container nav">
      <a class="brand" href="#top" aria-label="NYTRIXX Electricity Shop">
        <div class="logoMark" aria-hidden="true"></div>
        <div class="brandText">
          <strong>NYTRIXX</strong>
          <span>Electricity Shop</span>
        </div>
      </a>

      <nav aria-label="Primary">
        <ul>
          <li><a href="#products">Products</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a href="#faq">FAQ</a></li>
        </ul>
      </nav>

      <div class="navRight">
        <button class="burger" id="burger" aria-label="Open menu" type="button">
          <span></span><span></span><span></span>
        </button>

        <div class="togglePill" id="themeToggle" role="switch" aria-checked="false" tabindex="0" aria-label="Toggle dark mode">
          <div class="toggleKnob" id="themeKnob">
            <svg class="toggleIcon" id="themeIcon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M12 18a6 6 0 0 1 0-12c.5 0 .99.06 1.45.18A7.5 7.5 0 0 0 20.82 11.5c-.12.46-.18.95-.18 1.45a6 6 0 0 1-8.64 5.05Z" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
        </div>
      </div>
    </div>

    <div class="container mobileMenu" id="mobileMenu">
      <a href="#products">Products</a>
      <a href="#services">Services</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
      <a href="#faq">FAQ</a>
    </div>
  </header>

  <main id="top">
    <!-- HERO -->
    <section class="hero">
      <div class="heroBg" aria-hidden="true"></div>
      <div class="sparks" aria-hidden="true">
        <svg id="sparksSvg" width="100%" height="100%" viewBox="0 0 1200 520" preserveAspectRatio="none" style="opacity:.9"></svg>
      </div>

      <div class="container heroGrid">
        <div class="heroLeft reveal" data-reveal>
          <div class="kicker">Premium Electrical Shop</div>
          <div class="glowTitle">Powering Your World</div>
          <div class="heroTag">Wires, switches, solar panels, inverters & expert electrical services—crafted for reliability and glow-up performance.</div>
          <div class="ctaRow">
            <a class="btn btnPrimary" href="#products">
              <span class="btnIcon" aria-hidden="true">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M13 2 3 14h9l-1 8 10-12h-9l1-8Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </span>
              Shop Now
            </a>
            <a class="btn" href="#contact">
              <span class="btnIcon" aria-hidden="true">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.8 19.8 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6A19.8 19.8 0 0 1 2.08 4.18 2 2 0 0 1 4.06 2h3a2 2 0 0 1 2 1.72c.12.86.3 1.7.57 2.5a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.58-1.09a2 2 0 0 1 2.11-.45c.8.27 1.64.45 2.5.57A2 2 0 0 1 22 16.92Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </span>
              Get Support
            </a>
          </div>
        </div>

        <div class="heroRight reveal" data-reveal>
          <div class="heroPanel">
            <div class="kicker">Fast, Safe & Clean Work</div>
            <div style="font-weight:1000;font-size:22px;margin-top:8px;letter-spacing:-.02em;">
              Trusted solutions for homes & businesses
            </div>
            <div class="heroStats">
              <div class="stat">
                <strong>100% Quality</strong>
                <span>Premium brands & verified stock</span>
              </div>
              <div class="stat">
                <strong>Quick Response</strong>
                <span>Installation & repairs when needed</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- PRODUCTS -->
    <section id="products" class="reveal" data-reveal>
      <div class="container">
        <div class="sectionHead">
          <div>
            <div class="kicker">Shop Categories</div>
            <h2>Products built for modern power</h2>
            <div class="sub">Select a category and add items to your cart. Hover glow, smooth UI, and premium cards included.</div>
          </div>
        </div>

        <div class="filters" id="productFilters" role="tablist" aria-label="Product categories">
          <button class="chip active" type="button" data-filter="All">All</button>
          <button class="chip" type="button" data-filter="Wires">Wires</button>
          <button class="chip" type="button" data-filter="Switches">Switches</button>
          <button class="chip" type="button" data-filter="Bulbs">Bulbs</button>
          <button class="chip" type="button" data-filter="Fans">Fans</button>
          <button class="chip" type="button" data-filter="Inverters">Inverters</button>
          <button class="chip" type="button" data-filter="Solar Panels">Solar Panels</button>
        </div>

        <div class="productGrid" id="productGrid" aria-live="polite"></div>
      </div>
    </section>

    <!-- SERVICES -->
    <section id="services" class="reveal" data-reveal>
      <div class="container">
        <div class="sectionHead">
          <div>
            <div class="kicker">Service Center</div>
            <h2>Installation • Repair • Maintenance</h2>
            <div class="sub">3D hover icons and bright feedback—because your electrical system deserves it.</div>
          </div>
        </div>

        <div class="servicesGrid">
          <div class="card serviceCard">
            <div class="serviceIconWrap" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8l-6-6Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M14 2v6h6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M9 13h6" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
              </svg>
            </div>
            <div class="serviceTitle">Installation</div>
            <div class="serviceText">Clean wiring, safe load balancing, and properly installed accessories.</div>
          </div>

          <div class="card serviceCard">
            <div class="serviceIconWrap" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M10 13a5 5 0 0 1 7.07 0l1.41 1.41a5 5 0 0 1-7.07 7.07L10 20" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M14 11a5 5 0 0 1-7.07 0L5.52 9.59a5 5 0 0 1 7.07-7.07L14 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>
            <div class="serviceTitle">Repair</div>
            <div class="serviceText">Fault diagnosis, quick fixes, and tested outcomes for stable power.</div>
          </div>

          <div class="card serviceCard">
            <div class="serviceIconWrap" aria-hidden="true">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-14.6 1.8A8.38 8.38 0 0 1 3 11.5" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
                <path d="M12 7v5l3 2" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M22 12h-2" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
                <path d="M4 12H2" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
              </svg>
            </div>
            <div class="serviceTitle">Maintenance</div>
            <div class="serviceText">Periodic checkups, safety upgrades, and better efficiency over time.</div>
          </div>
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about" class="reveal" data-reveal>
      <div class="container">
        <div class="sectionHead">
          <div>
            <div class="kicker">Our Story</div>
            <h2>Premium power for everyday life</h2>
            <div class="sub">We started as a small electrical shop and grew into a trusted one-stop solution for quality products and dependable service.</div>
          </div>
        </div>

        <div class="aboutGrid">
          <div class="card aboutCard">
            <div style="font-weight:1000;font-size:18px;">A legacy of reliable electricity</div>
            <div class="sub" style="margin-top:10px;max-width:unset;">NYTRIXX Electricity Shop has helped homes and businesses stay powered with safe installs, correct parts, and responsive service. From switches to solar panels, our focus stays the same: quality, safety, and performance.</div>
            <div class="trustedPill">Trusted since <span id="trustedYear">2014</span></div>
          </div>

          <div class="card aboutCard">
            <div style="font-weight:1000;font-size:18px;">What you get</div>
            <div class="contactList" style="margin-top:12px;">
              <div class="contactRow">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M20 6 9 17l-5-5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg>
                <div><strong>Verified Products</strong><span>Quality stock curated for performance</span></div>
              </div>
              <div class="contactRow">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 2v20" stroke="currentColor" stroke-width="2" stroke-linecap="round"/><path d="M2 12h20" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg>
                <div><strong>Safe Work</strong><span>Proper checks and clean finishing</span></div>
              </div>
              <div class="contactRow">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M20 21V7" stroke="currentColor" stroke-width="2" stroke-linecap="round"/><path d="M4 17V3" stroke="currentColor" stroke-width="2" stroke-linecap="round"/><path d="M14 21V10" stroke="currentColor" stroke-width="2" stroke-linecap="round"/><path d="M10 3v14" stroke="currentColor" stroke-width="2" stroke-linecap="round"/></svg>
                <div><strong>Modern Options</strong><span>Solar + inverter solutions for efficiency</span></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- TESTIMONIALS -->
    <section class="reveal" data-reveal>
      <div class="container">
        <div class="sectionHead">
          <div>
            <div class="kicker">Loved By Customers</div>
            <h2>Testimonials</h2>
            <div class="sub">Real feedback with premium service experiences.</div>
          </div>
        </div>

        <div class="slider" aria-label="Testimonials slider">
          <div class="slides" id="testimonialSlides">
            <div class="slide">
              <div class="card testimonialCard">
                <div class="quote">“They installed my inverter and wiring safely. Everything looks clean, works perfectly, and the team explained usage clearly.”</div>
                <div class="person"><div class="avatar">A</div><div><strong>Ananya</strong><span>Home Installation</span></div></div>
              </div>
            </div>
            <div class="slide">
              <div class="card testimonialCard">
                <div class="quote">“Quick repair for my fan and switch issues. Transparent charges and high-quality replacements.”</div>
                <div class="person"><div class="avatar">R</div><div><strong>Rahul</strong><span>Repair & Maintenance</span></div></div>
              </div>
            </div>
            <div class="slide">
              <div class="card testimonialCard">
                <div class="quote">“Great solar panel guidance and honest recommendations. Received exactly what I needed.”</div>
                <div class="person"><div class="avatar">S</div><div><strong>Shreya</strong><span>Solar Consultation</span></div></div>
              </div>
            </div>
          </div>
          <div class="dots" id="testimonialDots" aria-label="Slide navigation"></div>
        </div>
      </div>
    </section>

    <!-- FAQ -->
    <section id="faq" class="reveal" data-reveal>
      <div class="container">
        <div class="sectionHead">
          <div>
            <div class="kicker">FAQ</div>
            <h2>Questions, answered</h2>
            <div class="sub">Quick explanations about products, installation, and service.</div>
          </div>
        </div>

        <div class="faq">
          <details class="faqItem" open>
            <summary>
              <span>Do you provide installation for all products?</span>
              <span class="faqIcon" aria-hidden="true">+</span>
            </summary>
            <div class="faqBody">Yes. Our team supports installation for wiring, switches, lighting, fans, inverters, and solar panels (availability may vary by requirement).</div>
          </details>
          <details class="faqItem">
            <summary>
              <span>How do I choose the right inverter or solar panel?</span>
              <span class="faqIcon" aria-hidden="true">+</span>
            </summary>
            <div class="faqBody">Share your usage (devices/wattage and backup needs). We recommend a suitable inverter/solar setup based on your requirement.</div>
          </details>
          <details class="faqItem">
            <summary>
              <span>Can you repair old wiring or switches?</span>
              <span class="faqIcon" aria-hidden="true">+</span>
            </summary>
            <div class="faqBody">We can diagnose and repair faults safely. If replacement is needed, we suggest the best quality options for your setup.</div>
          </details>
          <details class="faqItem">
            <summary>
              <span>Do you sell wires and switches in different brands?</span>
              <span class="faqIcon" aria-hidden="true">+</span>
            </summary>
            <div class="faqBody">Yes. We keep curated options across quality tiers so you can choose based on performance and budget.</div>
          </details>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact" class="reveal" data-reveal>
      <div class="container">
        <div class="sectionHead">
          <div>
            <div class="kicker">Contact Us</div>
            <h2>Let’s power your project</h2>
            <div class="sub">Call, email, follow on Instagram, or send a message using the form.</div>
          </div>
        </div>

        <div class="contactGrid">
          <div class="card contactCard">
            <div style="font-weight:1000;font-size:18px;">Direct Contact</div>
            <div class="contactList">
              <div class="contactRow">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.8 19.8 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6A19.8 19.8 0 0 1 2.08 4.18 2 2 0 0 1 4.06 2h3a2 2 0 0 1 2 1.72c.12.86.3 1.7.57 2.5a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.58-1.09a2 2 0 0 1 2.11-.45c.8.27 1.64.45 2.5.57A2 2 0 0 1 22 16.92Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg>
                <div><strong>Phone</strong><span>+91 9456853697</span></div>
              </div>
              <div class="contactRow">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M4 4h16v16H4V4Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/><path d="m4 7 8 6 8-6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/></svg>
                <div><strong>Email</strong><span>nytrixxofficial@gmail.com</span></div>
              </div>
              <div class="contactRow">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5Z" stroke="currentColor" stroke-width="2"/><path d="M12 11.5a2.5 2.5 0 1 0 0-5 2.5 2.5 0 0 0 0 5Z" stroke="currentColor" stroke-width="2"/><path d="M17.5 6.5h.01" stroke="currentColor" stroke-width="3" stroke-linecap="round"/></svg>
                <div><strong>Instagram</strong><span>@nytrixxofficial</span></div>
              </div>
              <div class="contactRow">
                <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 22s8-4 8-10a8 8 0 1 0-16 0c0 6 8 10 8 10Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/><path d="M12 12a2 2 0 1 0 0-4 2 2 0 0 0 0 4Z" stroke="currentColor" stroke-width="2"/></svg>
                <div><strong>Location</strong><span>India</span></div>
              </div>
            </div>
          </div>

          <div class="card contactCard">
            <div style="font-weight:1000;font-size:18px;">Send a Message</div>
            <form id="contactForm" novalidate>
              <div class="field">
                <label for="name">Name</label>
                <input id="name" name="name" type="text" placeholder="Your name" required minlength="2" />
              </div>
              <div class="field">
                <label for="email">Email</label>
                <input id="email" name="email" type="email" placeholder="you@example.com" required />
              </div>
              <div class="field">
                <label for="message">Message</label>
                <textarea id="message" name="message" placeholder="Tell us what you need..." required minlength="10"></textarea>
              </div>
              <div class="formHint">This demo form shows a success toast (no backend connected).</div>
              <button class="btn btnPrimary" type="submit">
                <span class="btnIcon" aria-hidden="true">
                  <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M22 2 11 13" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    <path d="M22 2 15 22 11 13 2 9 22 2Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                  </svg>
                </span>
                Submit
              </button>
            </form>
          </div>
        </div>
      </div>
    </section>

    <footer>
      <div class="container footerGrid">
        <div class="footerLeft">Copyright © 2026 NYTRIXX Electricity Shop</div>
        <div class="social" aria-label="Social links">
          <a href="#" title="Instagram" aria-label="Instagram">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M7 2h10a5 5 0 0 1 5 5v10a5 5 0 0 1-5 5H7a5 5 0 0 1-5-5V7a5 5 0 0 1 5-5Z" stroke="currentColor" stroke-width="2"/>
              <path d="M12 11.5a2.5 2.5 0 1 0 0-5 2.5 2.5 0 0 0 0 5Z" stroke="currentColor" stroke-width="2"/>
              <path d="M17.5 6.5h.01" stroke="currentColor" stroke-width="3" stroke-linecap="round"/>
            </svg>
          </a>
          <a href="#" title="Facebook" aria-label="Facebook">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3V2Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </a>
          <a href="#" title="Twitter" aria-label="Twitter">
            <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M22 4s-1 0-3 1c-1-1-2-1-3-1-2 0-4 2-4 4v1C7 9 4 7 2 5c0 2 1 4 3 5-1 0-2 0-3-1 0 3 2 5 5 6-1 1-3 1-5 1 3 2 6 3 9 3 8 0 13-7 13-14 0-1 0-1 0-1 1-1 2-2 2-2Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </a>
        </div>
      </div>
    </footer>
  </main>

  <button class="cartFab" id="cartFab" type="button" aria-label="Cart">
    <span class="btnIcon" aria-hidden="true" style="border-radius:999px;width:34px;height:34px;">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M6 6h15l-1.5 9h-12L6 6Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M6 6 5 3H2" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M9 20a1 1 0 1 0 0-2 1 1 0 0 0 0 2Z" fill="currentColor"/>
        <path d="M18 20a1 1 0 1 0 0-2 1 1 0 0 0 0 2Z" fill="currentColor"/>
      </svg>
    </span>
    <span style="font-weight:1000;">Cart</span>
    <span class="badge" id="cartCount">0</span>
  </button>

  <div class="toast" id="toast" role="status" aria-live="polite">Added to cart.</div>

  <script>
    // ---------- Electricity sparks (SVG) ----------
    const sparksSvg = document.getElementById('sparksSvg');
    function makeSparkPath() {
      const x1 = Math.random() * 1200;
      const y1 = Math.random() * 520;
      const len = 40 + Math.random() * 130;
      const segs = 3 + Math.floor(Math.random() * 4);
      let d = `M ${x1.toFixed(1)} ${y1.toFixed(1)}`;
      let x = x1;
      let y = y1;
      for (let i=0;i<segs;i++) {
        x += (Math.random() - 0.5) * 120;
        y += (Math.random() - 0.5) * 90;
        d += ` L ${x.toFixed(1)} ${y.toFixed(1)}`;
      }
      return { d, len, x1, y1 };
    }

    // Build lightweight spark lines
    (function buildSparks(){
      if (!sparksSvg) return;
      const colors = [
        'rgba(0,212,255,.55)',
        'rgba(42,77,255,.42)',
        'rgba(246,196,83,.35)'
      ];
      sparksSvg.innerHTML = '';
      const n = 36;
      for (let i=0;i<n;i++){
        const { d } = makeSparkPath();
        const p = document.createElementNS('http://www.w3.org/2000/svg','path');
        p.setAttribute('d', d);
        p.setAttribute('fill','none');
        p.setAttribute('stroke', colors[Math.floor(Math.random()*colors.length)]);
        p.setAttribute('stroke-width', (1.2 + Math.random()*1.8).toFixed(2));
        p.setAttribute('stroke-linecap','round');
        p.style.filter = 'drop-shadow(0 0 10px rgba(0,212,255,.18))';
        const dur = (0.9 + Math.random()*1.9).toFixed(2);
        const delay = (Math.random()*1.4).toFixed(2);
        p.style.opacity = (0.18 + Math.random()*0.55).toFixed(2);
        p.style.animation = `sparkFlicker ${dur}s var(--ease, cubic-bezier(.2,.8,.2,1)) ${delay}s infinite alternate`;
        sparksSvg.appendChild(p);
      }

      const style = document.createElement('style');
      style.textContent = `@keyframes sparkFlicker{ from{ opacity: .18; } to{ opacity: .9; } }`;
      document.head.appendChild(style);
    })();

    // ---------- Reveal on scroll ----------
    const revealEls = document.querySelectorAll('[data-reveal]');
    const io = new IntersectionObserver((entries)=>{
      for (const e of entries){
        if (e.isIntersecting) e.target.classList.add('in');
      }
    }, { threshold: 0.12 });
    revealEls.forEach(el=>io.observe(el));

    // ---------- Theme toggle ----------
    const themeToggle = document.getElementById('themeToggle');
    const themeIcon = document.getElementById('themeIcon');

    function setTheme(theme){
      document.body.setAttribute('data-theme', theme);
      const isDark = theme === 'dark';
      themeToggle.setAttribute('aria-checked', String(isDark));

      // swap icon (sun/moon)
      if (isDark){
        themeIcon.innerHTML = '<path d="M12 18a6 6 0 0 1 0-12c.5 0 .99.06 1.45.18A7.5 7.5 0 0 0 20.82 11.5c-.12.46-.18.95-.18 1.45a6 6 0 0 1-8.64 5.05Z" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>';
      } else {
        themeIcon.innerHTML = '<path d="M12 18a6 6 0 1 0 0-12 6 6 0 0 0 0 12Z" stroke="currentColor" stroke-width="1.8"/><path d="M12 2v2" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/><path d="M12 20v2" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/><path d="M4.93 4.93l1.41 1.41" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/><path d="M17.66 17.66l1.41 1.41" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/><path d="M2 12h2" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/><path d="M20 12h2" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/><path d="M4.93 19.07l1.41-1.41" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/><path d="M17.66 6.34l1.41-1.41" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>';
      }

      localStorage.setItem('theme', theme);
    }

    const savedTheme = localStorage.getItem('theme');
    if (savedTheme === 'dark' || savedTheme === 'light') setTheme(savedTheme);
    else setTheme('light');

    themeToggle.addEventListener('click', ()=>{
      const cur = document.body.getAttribute('data-theme') === 'dark' ? 'dark' : 'light';
      setTheme(cur === 'dark' ? 'light' : 'dark');
    });
    themeToggle.addEventListener('keydown', (e)=>{
      if (e.key === 'Enter' || e.key === ' ') { e.preventDefault(); themeToggle.click(); }
    });

    // ---------- Mobile menu ----------
    const burger = document.getElementById('burger');
    const mobileMenu = document.getElementById('mobileMenu');
    burger?.addEventListener('click', ()=> mobileMenu.classList.toggle('open'));

    // ---------- Products + Cart ----------
    const products = [
      { id: 'wire-1', category: 'Wires', name: 'Copper Wire 2.5mm', price: 499, meta: 'Heat-resistant • Premium copper', icon: 'wire' },
      { id: 'wire-2', category: 'Wires', name: 'Copper Wire 1.5mm', price: 349, meta: 'Flexible • Reliable conductivity', icon: 'wire2' },
      { id: 'switch-1', category: 'Switches', name: 'Premium Modular Switch', price: 129, meta: 'Smooth touch • Long life', icon: 'switch' },
      { id: 'switch-2', category: 'Switches', name: 'Fan Regulator (LED)', price: 229, meta: 'Stable speed control', icon: 'regulator' },
      { id: 'bulb-1', category: 'Bulbs', name: 'LED Bulb 9W (Cool White)', price: 89, meta: 'Low power • Bright output', icon: 'bulb' },
      { id: 'bulb-2', category: 'Bulbs', name: 'LED Bulb 12W (Warm)', price: 109, meta: 'Warm comfort • Eco', icon: 'bulb2' },
      { id: 'fan-1', category: 'Fans', name: 'BLDC Ceiling Fan 52"', price: 5899, meta: 'Energy saver • Silent', icon: 'fan' },
      { id: 'fan-2', category: 'Fans', name: 'High-Speed Exhaust Fan', price: 1799, meta: 'Powerful airflow', icon: 'fan2' },
      { id: 'inv-1', category: 'Inverters', name: 'Inverter 1100VA', price: 11999, meta: 'Stable backup • Smart protection', icon: 'inverter' },
      { id: 'inv-2', category: 'Inverters', name: 'Inverter 850VA', price: 8999, meta: 'Efficient • Clean power', icon: 'inverter2' },
      { id: 'solar-1', category: 'Solar Panels', name: 'Solar Panel 550W', price: 18999, meta: 'High efficiency • Durable frame', icon: 'solar' },
      { id: 'solar-2', category: 'Solar Panels', name: 'Solar Panel 300W', price: 10999, meta: 'Cost-effective • Great output', icon: 'solar2' },
    ];

    const grid = document.getElementById('productGrid');
    const filters = document.getElementById('productFilters');
    const cartCountEl = document.getElementById('cartCount');
    const toastEl = document.getElementById('toast');

    const cart = new Map(); // id -> qty

    function fmtINR(n){
      try{ return new Intl.NumberFormat('en-IN',{ style:'currency', currency:'INR', maximumFractionDigits:0 }).format(n); }
      catch{ return '₹' + Math.round(n); }
    }

    function iconSVG(kind){
      const common = 'stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"';
      switch(kind){
        case 'wire':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M4 17 17 4" ${common}/><path d="M7 20 20 7" ${common}/><path d="M4 7h5" ${common}/><path d="M12 3v5" ${common}/></svg>`;
        case 'wire2':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6 18 18 6" ${common}/><path d="M9 21l12-12" ${common}/><path d="M3 10h6" ${common}/><path d="M12 3v6" ${common}/></svg>`;
        case 'switch':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M8 7a4 4 0 1 1 8 0v10a4 4 0 1 1-8 0V7Z" ${common}/><path d="M9.5 12h5" ${common}/></svg>`;
        case 'regulator':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M4 12a8 8 0 1 0 16 0" ${common}/><path d="M12 12l4-3" ${common}/><path d="M4 12h2" ${common}/></svg>`;
        case 'bulb':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M9 18h6" ${common}/><path d="M10 22h4" ${common}/><path d="M8 14c-1.5-1.3-2-3-2-5a6 6 0 1 1 12 0c0 2-.5 3.7-2 5l-1 2H9l-1-2Z" ${common}/></svg>`;
        case 'bulb2':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 2a7 7 0 0 0-4 12c1 1 1 2 1 2h6s0-1 1-2a7 7 0 0 0-4-12Z" ${common}/><path d="M9 22h6" ${common}/><path d="M10 19h4" ${common}/></svg>`;
        case 'fan':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M12 12m7-3-7 3 7 3-7-3" ${common}/><path d="M12 12 5 9" ${common}/><path d="M12 12 5 15" ${common}/><circle cx="12" cy="12" r="2" ${common}/></svg>`;
        case 'fan2':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><circle cx="12" cy="12" r="3" ${common}/><path d="M12 12c4 0 7-2 8-5" ${common}/><path d="M12 12c-4 0-7-2-8-5" ${common}/><path d="M12 12c4 0 7 2 8 5" ${common}/><path d="M12 12c-4 0-7 2-8 5" ${common}/></svg>`;
        case 'inverter':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M4 7h16v14H4V7Z" ${common}/><path d="M8 7V3h8v4" ${common}/><path d="M9 13h6" ${common}/><path d="M12 10v6" ${common}/></svg>`;
        case 'inverter2':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6 18h12" ${common}/><path d="M4 7h16v11H4V7Z" ${common}/><path d="M9 11h6" ${common}/></svg>`;
        case 'solar':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M4 10h16v10H4V10Z" ${common}/><path d="M8 6l-4 4" ${common}/><path d="M16 6l4 4" ${common}/><path d="M10 4l2 6" ${common}/></svg>`;
        case 'solar2':
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6 12h12v8H6v-8Z" ${common}/><path d="M4 10l8-6 8 6" ${common}/><path d="M12 6v14" ${common}/></svg>`;
        default:
          return `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M13 2 3 14h9l-1 8 10-12h-9l1-8Z" ${common}/></svg>`;
      }
    }

    function renderProducts(filter){
      const items = filter === 'All' ? products : products.filter(p => p.category === filter);
      grid.innerHTML = items.map(p => {
        return `
          <div class="card productCard" data-category="${p.category}" data-id="${p.id}">
            <div class="productTop">
              <div class="productImg" aria-hidden="true">${iconSVG(p.icon)}</div>
              <div style="flex:1; text-align:right;">
                <div class="productMeta" style="margin-top:0;">${p.category}</div>
              </div>
            </div>

            <div class="productBody">
              <div class="productName">${p.name}</div>
              <div class="price">${fmtINR(p.price)}</div>
              <div class="productMeta">${p.meta}</div>

              <div class="addRow">
                <div class="qtyPill" aria-label="Quantity">
                  <button type="button" class="qtyMinus" aria-label="Decrease">−</button>
                  <span class="qty" aria-live="off">1</span>
                  <button type="button" class="qtyPlus" aria-label="Increase">+</button>
                </div>
                <button class="btn btnPrimary" type="button" data-add="${p.id}" style="padding:10px 12px;border-radius:14px;">
                  <span class="btnIcon" aria-hidden="true" style="width:24px;height:24px;border-radius:10px;">
                    <svg width="14" height="14" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                      <path d="M6 6h15l-1.5 9h-12L6 6Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                      <path d="M6 6 5 3H2" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    </svg>
                  </span>
                  Add to Cart
                </button>
              </div>
            </div>
          </div>
        `;
      }).join('');

      // qty handling per card
      grid.querySelectorAll('.productCard').forEach(card => {
        const qtyEl = card.querySelector('.qty');
        const minus = card.querySelector('.qtyMinus');
        const plus = card.querySelector('.qtyPlus');

        let qty = 1;
        const clamp = (v) => Math.max(1, Math.min(99, v));

        const setQty = (v) => { qty = clamp(v); qtyEl.textContent = String(qty); };
        minus.addEventListener('click', ()=> setQty(qty - 1));
        plus.addEventListener('click', ()=> setQty(qty + 1));

        const addBtn = card.querySelector('[data-add]');
        addBtn.addEventListener('click', ()=>{
          const id = addBtn.getAttribute('data-add');
          cart.set(id, (cart.get(id) || 0) + qty);
          updateCartCount();
          showToast('Added to cart.');
        });
      });
    }

    function updateCartCount(){
      let total = 0;
      for (const q of cart.values()) total += q;
      cartCountEl.textContent = String(total);
    }

    function showToast(msg){
      toastEl.textContent = msg;
      toastEl.classList.add('show');
      clearTimeout(showToast._t);
      showToast._t = setTimeout(()=> toastEl.classList.remove('show'), 2000);
    }

    filters?.addEventListener('click', (e)=>{
      const btn = e.target.closest('button[data-filter]');
      if (!btn) return;
      filters.querySelectorAll('.chip').forEach(c => c.classList.remove('active'));
      btn.classList.add('active');
      renderProducts(btn.getAttribute('data-filter'));
    });

    // init
    renderProducts('All');
    updateCartCount();

    // cart click
    document.getElementById('cartFab').addEventListener('click', ()=>{
      const total = Number(cartCountEl.textContent);
      if (total <= 0) { showToast('Cart is empty.'); return; }
      const firstFew = Array.from(cart.entries()).slice(0, 3);
      const lines = firstFew.map(([id,q]) => {
        const p = products.find(x=>x.id===id);
        return p ? `${p.name} × ${q}` : `${id} × ${q}`;
      }).join('\n');
      alert(`Cart items:\n${lines}\n\nTotal items: ${total}`);
    });

    // ---------- Testimonials slider ----------
    const slidesWrap = document.getElementById('testimonialSlides');
    const dotsWrap = document.getElementById('testimonialDots');
    const slides = Array.from(slidesWrap?.children || []);
    let idx = 0;
    let timer = null;

    function renderDots(){
      if (!dotsWrap) return;
      dotsWrap.innerHTML = '';
      slides.forEach((_, i)=>{
        const b = document.createElement('button');
        b.type = 'button';
        b.className = 'dot' + (i===0 ? ' active' : '');
        b.setAttribute('aria-label', `Go to testimonial ${i+1}`);
        b.addEventListener('click', ()=>{ go(i, true); });
        dotsWrap.appendChild(b);
      });
    }

    function go(i, manual=false){
      idx = i;
      slidesWrap.style.transform = `translateX(${-i*100}%)`;
      Array.from(dotsWrap.children).forEach((d,di)=> d.classList.toggle('active', di===i));
      if (manual) restartTimer();
    }

    function restartTimer(){
      if (timer) clearInterval(timer);
      timer = setInterval(()=>{
        const next = (idx + 1) % slides.length;
        go(next, false);
      }, 3800);
    }

    renderDots();
    if (slides.length) {
      slidesWrap.style.transform = 'translateX(0%)';
      restartTimer();
    }

    // ---------- Contact form validation (demo) ----------
    const form = document.getElementById('contactForm');
    const toast = document.getElementById('toast');

    form?.addEventListener('submit', (e)=>{
      e.preventDefault();
      const name = document.getElementById('name');
      const email = document.getElementById('email');
      const message = document.getElementById('message');

      const okName = name.value.trim().length >= 2;
      const okEmail = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email.value.trim());
      const okMsg = message.value.trim().length >= 10;

      if (!okName){ name.focus(); showToast('Please enter your name (min 2 chars).'); return; }
      if (!okEmail){ email.focus(); showToast('Please enter a valid email address.'); return; }
      if (!okMsg){ message.focus(); showToast('Message should be at least 10 characters.'); return; }

      showToast('Message sent! We will contact you soon.');
      form.reset();
    });

    // ---------- Trusted year (editable) ----------
    // Set to current decade default if you want: keep as static for requirement.
    document.getElementById('trustedYear').textContent = '2014';

    // Ensure initial reveal for users who scroll fast
    window.addEventListener('load', ()=>{
      revealEls.forEach(el=>{
        if (el.getBoundingClientRect().top < window.innerHeight * 0.9) el.classList.add('in');
      });
    });
  </script>
</body>
</html>
