# Security-Awareness
For Enterprises

DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cybersecurity Grundlagen – ESG Elektro Gesellschaft</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;1,9..40,400&family=DM+Mono:wght@400;500&display=swap');

  :root {
    --navy:    #0D1B2A;
    --blue:    #1A3A5C;
    --electric:#00A8E8;
    --yellow:  #F5C518;
    --light:   #F0F4F8;
    --mid:     #C8D8E8;
    --text:    #1A2535;
    --muted:   #5A7A9A;
    --white:   #ffffff;
    --border:  #DDE8F0;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'DM Sans', sans-serif;
    background: var(--light);
    color: var(--text);
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  /* ── HEADER ── */
  header {
    background: var(--navy);
    border-bottom: 3px solid var(--electric);
    position: sticky; top: 0; z-index: 100;
  }
  .header-inner {
    max-width: 860px; margin: 0 auto;
    padding: 14px 24px;
    display: flex; align-items: center; justify-content: space-between;
  }
  .logo { display: flex; align-items: center; gap: 12px; }
  .logo-icon {
    width: 34px; height: 34px; background: var(--electric);
    border-radius: 7px; display: flex; align-items: center;
    justify-content: center; font-size: 17px; flex-shrink: 0;
  }
  .logo-name  { color: #fff; font-size: 14px; font-weight: 600; line-height: 1.2; }
  .logo-sub   { color: var(--mid); font-size: 10px; font-weight: 300; letter-spacing: .08em; text-transform: uppercase; }
  .badge {
    background: var(--yellow); color: var(--navy);
    font-size: 10px; font-weight: 700; padding: 3px 10px;
    border-radius: 20px; letter-spacing: .06em; text-transform: uppercase;
  }

  /* ── HERO ── */
  .hero {
    background: linear-gradient(135deg, var(--navy) 0%, var(--blue) 100%);
    padding: 60px 24px 52px; text-align: center; position: relative; overflow: hidden;
  }
  .hero::after {
    content: ''; position: absolute; top: -80px; right: -80px;
    width: 340px; height: 340px; border-radius: 50%;
    background: radial-gradient(circle, rgba(0,168,232,.13) 0%, transparent 70%);
    pointer-events: none;
  }
  .hero-eyebrow {
    font-family: 'DM Mono', monospace; color: var(--electric);
    font-size: 11px; letter-spacing: .18em; text-transform: uppercase; margin-bottom: 14px;
  }
  .hero h1 {
    color: #fff; font-size: clamp(26px, 5vw, 42px);
    font-weight: 600; line-height: 1.2; margin-bottom: 14px;
  }
  .hero h1 span { color: var(--electric); }
  .hero-sub {
    color: var(--mid); font-size: 15px; font-weight: 300;
    max-width: 460px; margin: 0 auto 36px;
  }
  .hero-stats { display: flex; justify-content: center; gap: 48px; flex-wrap: wrap; }
  .stat-num {
    font-family: 'DM Mono', monospace; font-size: 26px;
    color: var(--yellow); font-weight: 500; display: block;
  }
  .stat-lbl { color: var(--mid); font-size: 11px; }

  /* ── SECTION LABEL ── */
  .section-wrap { max-width: 860px; margin: 0 auto; padding: 52px 24px 0; }
  .section-eyebrow {
    font-family: 'DM Mono', monospace; font-size: 10px;
    letter-spacing: .18em; text-transform: uppercase;
    color: var(--electric); margin-bottom: 6px;
  }
  .section-title { font-size: 22px; font-weight: 600; color: var(--navy); margin-bottom: 24px; }

  /* ── MODULE CARDS ── */
  .module-list { display: flex; flex-direction: column; gap: 14px; padding-bottom: 52px; }

  .module {
    background: var(--white); border: 1px solid var(--border);
    border-radius: 12px; overflow: hidden;
    box-shadow: 0 1px 4px rgba(13,27,42,.05);
    transition: box-shadow .2s;
  }
  .module:hover { box-shadow: 0 4px 20px rgba(13,27,42,.09); }

  .module-trigger {
    display: flex; align-items: center; gap: 14px;
    padding: 18px 20px; width: 100%; background: none;
    border: none; cursor: pointer; text-align: left;
  }
  .mod-num {
    font-family: 'DM Mono', monospace; font-size: 10px;
    color: var(--muted); min-width: 20px;
  }
  .mod-icon {
    width: 42px; height: 42px; border-radius: 10px;
    display: flex; align-items: center; justify-content: center;
    font-size: 19px; flex-shrink: 0;
  }
  .ic-blue   { background: #E8F4FD; }
  .ic-yellow { background: #FFF8E1; }
  .ic-green  { background: #E8F5E9; }
  .ic-red    { background: #FCE4EC; }

  .mod-meta { flex: 1; min-width: 0; }
  .mod-title { font-size: 15px; font-weight: 600; color: var(--navy); }
  .mod-desc  { font-size: 12px; color: var(--muted); margin-top: 1px; }
  .mod-time  { font-family: 'DM Mono', monospace; font-size: 11px; color: var(--muted); white-space: nowrap; }
  .chevron   { color: var(--muted); font-size: 12px; margin-left: 6px; transition: transform .22s ease; flex-shrink: 0; }
  .module.open .chevron { transform: rotate(180deg); }

  .module-body {
    display: none; border-top: 1px solid var(--border);
    padding: 0 20px 20px 76px;
  }
  .module.open .module-body { display: block; }

  .lesson-list { list-style: none; margin-top: 16px; display: flex; flex-direction: column; gap: 10px; }
  .lesson {
    display: flex; gap: 12px; padding: 13px 15px;
    background: var(--light); border-radius: 8px;
    border-left: 3px solid var(--electric);
  }
  .lesson-icon { font-size: 15px; flex-shrink: 0; margin-top: 1px; }
  .lesson h4   { font-size: 13px; font-weight: 600; color: var(--navy); margin-bottom: 3px; }
  .lesson p    { font-size: 12px; color: var(--muted); line-height: 1.55; }

  /* ── DEMO SECTION ── */
  .demo-band {
    background: var(--navy); padding: 52px 24px; margin-top: 52px;
  }
  .demo-inner { max-width: 860px; margin: 0 auto; }
  .demo-eyebrow {
    font-family: 'DM Mono', monospace; font-size: 10px;
    letter-spacing: .18em; text-transform: uppercase;
    color: var(--yellow); margin-bottom: 6px;
  }
  .demo-title { font-size: 22px; font-weight: 600; color: #fff; margin-bottom: 6px; }
  .demo-sub   { font-size: 13px; color: var(--mid); margin-bottom: 28px; }

  .email-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
  @media(max-width:580px){ .email-grid { grid-template-columns: 1fr; } }

  .email-card { border-radius: 10px; overflow: hidden; font-size: 13px; border: 1px solid rgba(255,255,255,.1); }
  .email-label {
    padding: 9px 14px; font-size: 11px; font-weight: 700;
    letter-spacing: .05em; text-transform: uppercase;
  }
  .email-label.ok   { background: #1B4332; color: #6FCF97; }
  .email-label.bad  { background: #4A1215; color: #F87171; }
  .email-fields {
    background: #fff; padding: 12px 14px;
    border-bottom: 1px solid #eee;
  }
  .email-field { font-size: 12px; color: #333; line-height: 1.7; }
  .email-field strong { color: #111; }
  .tag {
    display: inline-block; font-size: 10px; font-weight: 700;
    padding: 1px 6px; border-radius: 4px; margin-left: 4px; vertical-align: middle;
  }
  .tag-ok  { background: #D1FAE5; color: #065F46; }
  .tag-bad { background: #FEF3C7; color: #92400E; }
  .email-body-text {
    background: #fff; padding: 12px 14px;
    font-size: 12px; color: #333; line-height: 1.65;
  }
  .email-danger { color: #DC2626; font-weight: 600; }

  /* ── CHECKLIST ── */
  .checklist-wrap { max-width: 860px; margin: 0 auto; padding: 52px 24px 60px; }
  .progress-row { display: flex; align-items: center; gap: 12px; margin-bottom: 20px; }
  .progress-track {
    flex: 1; height: 6px; background: var(--border);
    border-radius: 3px; overflow: hidden;
  }
  .progress-fill {
    height: 100%; width: 0%; background: var(--electric);
    border-radius: 3px; transition: width .3s ease;
  }
  .progress-label {
    font-family: 'DM Mono', monospace; font-size: 11px;
    color: var(--muted); white-space: nowrap;
  }

  .checklist {
    background: var(--white); border: 1px solid var(--border);
    border-radius: 12px; overflow: hidden;
  }
  .check-item {
    display: flex; align-items: center; gap: 14px;
    padding: 15px 18px; border-bottom: 1px solid var(--border);
    cursor: pointer; transition: background .15s; user-select: none;
  }
  .check-item:last-child { border-bottom: none; }
  .check-item:hover { background: #f5f9fd; }
  .check-box {
    width: 20px; height: 20px; border: 2px solid var(--border);
    border-radius: 5px; flex-shrink: 0; display: flex;
    align-items: center; justify-content: center;
    font-size: 11px; color: transparent; transition: all .15s;
  }
  .check-item.done .check-box {
    background: var(--electric); border-color: var(--electric); color: #fff;
  }
  .check-text h4 { font-size: 13px; font-weight: 600; color: var(--navy); }
  .check-text p  { font-size: 11px; color: var(--muted); margin-top: 1px; }
  .check-item.done .check-text h4 { color: var(--muted); text-decoration: line-through; }

  /* ── FOOTER ── */
  footer {
    background: var(--navy); border-top: 1px solid rgba(255,255,255,.07);
    padding: 30px 24px; text-align: center;
  }
  .footer-name { font-size: 13px; font-weight: 600; color: #fff; margin-bottom: 4px; }
  .footer-sub  { font-size: 11px; color: var(--muted); }
  .footer-rule {
    width: 36px; height: 2px; background: var(--electric);
    border-radius: 2px; margin: 14px auto;
  }
  .footer-note { font-size: 11px; color: var(--muted); line-height: 1.6; }

  @media(max-width:600px){
    .hero-stats { gap: 28px; }
    .module-body { padding-left: 20px; }
    .section-wrap { padding-top: 36px; }
  }

  @media(prefers-reduced-motion: reduce){
    .chevron, .progress-fill, .check-box { transition: none; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header>
  <div class="header-inner">
    <div class="logo">
      <div class="logo-icon">⚡</div>
      <div>
        <div class="logo-name">ESG Elektro Gesellschaft</div>
        <div class="logo-sub">Cybersecurity Schulung</div>
      </div>
    </div>
    <span class="badge">Kostenlos</span>
  </div>
</header>

<!-- HERO -->
<div class="hero">
  <div class="hero-eyebrow">Mitarbeiter-Schulung · 2026</div>
  <h1>Sicher im digitalen <span>Arbeitsalltag</span></h1>
  <p class="hero-sub">Praktische Grundlagen für alle Mitarbeiter – kein IT-Vorwissen nötig. In 30 Minuten sicherer unterwegs.</p>
  <div class="hero-stats">
    <div class="stat">
      <span class="stat-num">91%</span>
      <span class="stat-lbl">aller Angriffe starten per E-Mail</span>
    </div>
    <div class="stat">
      <span class="stat-num">3 Min.</span>
      <span class="stat-lbl">bis ein Angriff entdeckt wird</span>
    </div>
    <div class="stat">
      <span class="stat-num">4 Module</span>
      <span class="stat-lbl">je 5–8 Minuten</span>
    </div>
  </div>
</div>

<!-- MODULES -->
<div class="section-wrap">
  <div class="section-eyebrow">Lerninhalt</div>
  <div class="section-title">Was Sie heute lernen</div>
  <div class="module-list">

    <!-- 01 -->
    <div class="module open" id="m1">
      <button class="module-trigger" onclick="toggle('m1')" aria-expanded="true">
        <span class="mod-num">01</span>
        <div class="mod-icon ic-blue">🎣</div>
        <div class="mod-meta">
          <div class="mod-title">Phishing erkennen</div>
          <div class="mod-desc">Gefälschte E-Mails sicher identifizieren</div>
        </div>
        <span class="mod-time">~7 Min.</span>
        <span class="chevron">▼</span>
      </button>
      <div class="module-body">
        <ul class="lesson-list">
          <li class="lesson">
            <span class="lesson-icon">📧</span>
            <div>
              <h4>Was ist Phishing?</h4>
              <p>Betrüger geben sich per E-Mail als Kollegen, Banken oder Behörden aus, um Passwörter oder Geld zu stehlen. Das Wort kommt von „fishing" – sie werfen einen Köder aus und warten, wer beißt.</p>
            </div>
          </li>
          <li class="lesson">
            <span class="lesson-icon">🔍</span>
            <div>
              <h4>Die 4 Warnsignale</h4>
              <p><strong>1. Absenderadresse prüfen</strong> – nicht nur den Namen, sondern die echte Adresse dahinter<br>
              <strong>2. Dringlichkeit</strong> – „Sofort handeln!" ist fast immer ein Trick<br>
              <strong>3. Links nicht anklicken</strong> – mit der Maus drüberfahren und die Ziel-URL prüfen<br>
              <strong>4. Anhänge</strong> – keine unerwarteten .zip, .exe oder Office-Dateien öffnen</p>
            </div>
          </li>
          <li class="lesson">
            <span class="lesson-icon">✅</span>
            <div>
              <h4>Im Zweifel: Anrufen</h4>
              <p>Wenn eine E-Mail merkwürdig wirkt – auch von einem bekannten Absender – einfach kurz anrufen und nachfragen. Ein 30-Sekunden-Anruf spart im Ernstfall Tausende Euro.</p>
            </div>
          </li>
        </ul>
      </div>
    </div>

    <!-- 02 -->
    <div class="module" id="m2">
      <button class="module-trigger" onclick="toggle('m2')" aria-expanded="false">
        <span class="mod-num">02</span>
        <div class="mod-icon ic-yellow">🔐</div>
        <div class="mod-meta">
          <div class="mod-title">Sichere Passwörter</div>
          <div class="mod-desc">Passwörter, die wirklich schützen</div>
        </div>
        <span class="mod-time">~6 Min.</span>
        <span class="chevron">▼</span>
      </button>
      <div class="module-body">
        <ul class="lesson-list">
          <li class="lesson">
            <span class="lesson-icon">❌</span>
            <div>
              <h4>Die häufigsten Fehler</h4>
              <p>„123456", „Passwort1", der eigene Name oder das Geburtsdatum – das sind die ersten Kombinationen, die Angreifer ausprobieren. Auch „esg2026!" ist unsicher, weil Firmenname + Jahr ein bekanntes Muster ist.</p>
            </div>
          </li>
          <li class="lesson">
            <span class="lesson-icon">💡</span>
            <div>
              <h4>Die Passphrase-Methode</h4>
              <p>Drei zufällige Wörter zusammen sind sicherer als ein kompliziertes Passwort: <strong>„Hammer-Wolke-Fußball7"</strong> ist leicht zu merken und extrem schwer zu knacken. Je länger, desto besser.</p>
            </div>
          </li>
          <li class="lesson">
            <span class="lesson-icon">🔁</span>
            <div>
              <h4>Niemals wiederverwenden</h4>
              <p>Jedes Konto braucht ein eigenes Passwort. Wenn ein Dienst gehackt wird, werden gestohlene Passwörter sofort bei anderen Seiten ausprobiert. Ein Passwort-Manager (z.B. Bitwarden – kostenlos) löst dieses Problem.</p>
            </div>
          </li>
        </ul>
      </div>
    </div>

    <!-- 03 -->
    <div class="module" id="m3">
      <button class="module-trigger" onclick="toggle('m3')" aria-expanded="false">
        <span class="mod-num">03</span>
        <div class="mod-icon ic-green">📱</div>
        <div class="mod-meta">
          <div class="mod-title">Geräte &amp; Zugang</div>
          <div class="mod-desc">Laptop, Handy und Homeoffice absichern</div>
        </div>
        <span class="mod-time">~6 Min.</span>
        <span class="chevron">▼</span>
      </button>
      <div class="module-body">
        <ul class="lesson-list">
          <li class="lesson">
            <span class="lesson-icon">💻</span>
            <div>
              <h4>Bildschirm sperren</h4>
              <p>Beim Verlassen des Arbeitsplatzes – auch kurz – immer den Bildschirm sperren (<strong>Windows: Win+L</strong>, <strong>Mac: Ctrl+Cmd+Q</strong>). In 30 Sekunden kann jemand Schaden anrichten.</p>
            </div>
          </li>
          <li class="lesson">
            <span class="lesson-icon">📶</span>
            <div>
              <h4>Öffentliches WLAN meiden</h4>
              <p>Im Café oder auf der Baustelle: Kein öffentliches WLAN für Firmendaten nutzen. Lieber den Hotspot vom Handy verwenden. Wenn WLAN nötig ist: VPN einschalten.</p>
            </div>
          </li>
          <li class="lesson">
            <span class="lesson-icon">🔄</span>
            <div>
              <h4>Updates nicht ignorieren</h4>
              <p>„Später erinnern" ist eine Einladung für Angreifer. Updates schließen bekannte Sicherheitslücken. Faustregel: Updates immer am selben Tag einspielen, spätestens am Abend.</p>
            </div>
          </li>
        </ul>
      </div>
    </div>

    <!-- 04 -->
    <div class="module" id="m4">
      <button class="module-trigger" onclick="toggle('m4')" aria-expanded="false">
        <span class="mod-num">04</span>
        <div class="mod-icon ic-red">🚨</div>
        <div class="mod-meta">
          <div class="mod-title">Was tun im Ernstfall?</div>
          <div class="mod-desc">Richtig reagieren, wenn etwas passiert</div>
        </div>
        <span class="mod-time">~5 Min.</span>
        <span class="chevron">▼</span>
      </button>
      <div class="module-body">
        <ul class="lesson-list">
          <li class="lesson">
            <span class="lesson-icon">🛑</span>
            <div>
              <h4>Sofort: Netzwerk trennen</h4>
              <p>Bei Verdacht auf einen Angriff: Kabel raus, WLAN aus. Das stoppt die weitere Ausbreitung. Danach sofort die Vorgesetzte oder IT informieren – keine Zeit verlieren.</p>
            </div>
          </li>
          <li class="lesson">
            <span class="lesson-icon">📢</span>
            <div>
              <h4>Melden, nicht verheimlichen</h4>
              <p>Wer aus Scham einen Vorfall verschweigt, macht es schlimmer. Frühzeitiges Melden begrenzt den Schaden erheblich. Kein Mitarbeiter wird bestraft, der ehrlich einen Fehler meldet.</p>
            </div>
          </li>
          <li class="lesson">
            <span class="lesson-icon">📸</span>
            <div>
              <h4>Screenshot machen</h4>
              <p>Bevor man etwas schließt: Screenshot der verdächtigen Nachricht oder des Fehlers. Das hilft der IT später bei der Analyse und der Anzeige bei den Behörden.</p>
            </div>
          </li>
        </ul>
      </div>
    </div>

  </div>
</div>

<!-- PHISHING DEMO -->
<div class="demo-band">
  <div class="demo-inner">
    <div class="demo-eyebrow">Praxis-Beispiel</div>
    <div class="demo-title">Echte E-Mail oder Falle?</div>
    <p class="demo-sub">Beide E-Mails sehen auf den ersten Blick ähnlich aus. Finden Sie die Unterschiede.</p>

    <div class="email-grid">
      <!-- ECHTE -->
      <div class="email-card">
        <div class="email-label ok">✅ Echte E-Mail</div>
        <div class="email-fields">
          <div class="email-field"><strong>Von:</strong> buchhaltung@esg-elektro.de <span class="tag tag-ok">✓ Korrekte Domain</span></div>
          <div class="email-field"><strong>Betreff:</strong> Gehaltsabrechnung März 2026</div>
        </div>
        <div class="email-body-text">
          Guten Tag,<br><br>
          Ihre Gehaltsabrechnung für März steht im Mitarbeiterportal bereit. Loggen Sie sich wie gewohnt ein.<br><br>
          Mit freundlichen Grüßen<br>
          <strong>Sabine Meier, Buchhaltung</strong>
        </div>
      </div>

      <!-- PHISHING -->
      <div class="email-card">
        <div class="email-label bad">🚨 Phishing-Versuch</div>
        <div class="email-fields">
          <div class="email-field"><strong>Von:</strong> buchhaltung@esg-e|ektro.de <span class="tag tag-bad">⚠ Falsches „l"</span></div>
          <div class="email-field"><strong>Betreff:</strong> ‼ DRINGLICH: Gehaltsabrechnung fehlerhaft</div>
        </div>
        <div class="email-body-text">
          Sehr geehrter Mitarbeiter,<br><br>
          Ihre Bankdaten sind veraltet. Bitte aktualisieren Sie diese <strong>sofort</strong>, sonst verzögert sich Ihre Zahlung!<br><br>
          <span class="email-danger">→ esg-elektr0-portal.ru</span> <span class="tag tag-bad">⚠ .ru Domain!</span>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- CHECKLIST -->
<div class="checklist-wrap">
  <div class="section-eyebrow">Meine Sicherheit</div>
  <div class="section-title">Persönliche Checkliste</div>

  <div class="progress-row">
    <div class="progress-track"><div class="progress-fill" id="bar"></div></div>
    <span class="progress-label" id="prog-label">0 von 6 erledigt</span>
  </div>

  <div class="checklist">
    <div class="check-item" onclick="tick(this)">
      <div class="check-box">✓</div>
      <div class="check-text">
        <h4>Ich prüfe bei jeder E-Mail die Absenderadresse</h4>
        <p>Nicht nur den Anzeigenamen, sondern die echte E-Mail-Adresse</p>
      </div>
    </div>
    <div class="check-item" onclick="tick(this)">
      <div class="check-box">✓</div>
      <div class="check-text">
        <h4>Ich nutze für jedes Konto ein eigenes Passwort</h4>
        <p>Am besten mit einem Passwort-Manager wie Bitwarden (kostenlos)</p>
      </div>
    </div>
    <div class="check-item" onclick="tick(this)">
      <div class="check-box">✓</div>
      <div class="check-text">
        <h4>Ich sperre meinen Bildschirm beim Verlassen des Arbeitsplatzes</h4>
        <p>Windows: Win+L · Mac: Ctrl+Cmd+Q</p>
      </div>
    </div>
    <div class="check-item" onclick="tick(this)">
      <div class="check-box">✓</div>
      <div class="check-text">
        <h4>Ich spiele Updates zeitnah ein</h4>
        <p>Spätestens am selben Abend – nicht auf „Später" klicken</p>
      </div>
    </div>
    <div class="check-item" onclick="tick(this)">
      <div class="check-box">✓</div>
      <div class="check-text">
        <h4>Ich nutze kein öffentliches WLAN für Firmendaten</h4>
        <p>Im Zweifel Handy-Hotspot oder VPN verwenden</p>
      </div>
    </div>
    <div class="check-item" onclick="tick(this)">
      <div class="check-box">✓</div>
      <div class="check-text">
        <h4>Ich melde Vorfälle sofort an Vorgesetzte / IT</h4>
        <p>Frühzeitiges Melden begrenzt den Schaden erheblich</p>
      </div>
    </div>
  </div>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-name">⚡ ESG Elektro Gesellschaft</div>
  <div class="footer-sub">Cybersecurity Mitarbeiterschulung 2026</div>
  <div class="footer-rule"></div>
  <div class="footer-note">Diese Schulung wurde kostenlos für Ihr Team erstellt.<br>Bei Fragen wenden Sie sich an Ihre IT-Verantwortlichen.</div>
</footer>

<script>
  function toggle(id) {
    const el = document.getElementById(id);
    const btn = el.querySelector('.module-trigger');
    const isOpen = el.classList.contains('open');
    el.classList.toggle('open', !isOpen);
    btn.setAttribute('aria-expanded', String(!isOpen));
  }

  function tick(el) {
    el.classList.toggle('done');
    updateProgress();
  }

  function updateProgress() {
    const total = document.querySelectorAll('.check-item').length;
    const done  = document.querySelectorAll('.check-item.done').length;
    const pct   = Math.round((done / total) * 100);
    document.getElementById('bar').style.width = pct + '%';
    document.getElementById('prog-label').textContent = done + ' von ' + total + ' erledigt';
  }
</script>
</body>
</html>
