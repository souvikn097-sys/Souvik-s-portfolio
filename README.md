<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Souvik Nandi — Software Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400;1,600&family=Outfit:wght@300;400;500;600&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --ink:#0f0f11;--ink2:#1a1a1f;--ink3:#242429;--rule:#2a2a32;
  --gold:#c9a96e;--gold-lt:#e8c98a;--gold-dim:rgba(201,169,110,0.12);
  --fog:#9898a8;--mist:#6c6c7c;
  --txt:#ccccd8;--txt-dim:#8888a0;
  --serif:'Playfair Display',Georgia,serif;
  --sans:'Outfit',sans-serif;--mono:'JetBrains Mono',monospace;
}
html{scroll-behavior:smooth}
body{background:var(--ink);color:var(--txt);font-family:var(--sans);font-weight:400;overflow-x:hidden;line-height:1.6}
::-webkit-scrollbar{width:3px}::-webkit-scrollbar-track{background:var(--ink)}::-webkit-scrollbar-thumb{background:var(--gold)}
::selection{background:rgba(201,169,110,0.22);color:#fff}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:200;display:flex;align-items:center;justify-content:space-between;padding:0 64px;height:64px;background:rgba(15,15,17,0.93);backdrop-filter:blur(20px);border-bottom:1px solid var(--rule)}
.nav-brand{font-family:var(--serif);font-size:1.1rem;font-weight:600;color:#fff;letter-spacing:0.02em}
.nav-brand em{font-style:italic;color:var(--gold)}
.nav-menu{display:flex;align-items:center;gap:36px}
.nav-menu a{font-size:0.76rem;font-weight:500;color:var(--txt-dim);text-decoration:none;letter-spacing:0.1em;text-transform:uppercase;transition:color 0.2s;position:relative}
.nav-menu a::after{content:'';position:absolute;bottom:-4px;left:0;right:0;height:1px;background:var(--gold);transform:scaleX(0);transform-origin:left;transition:transform 0.3s}
.nav-menu a:hover{color:var(--gold)}.nav-menu a:hover::after{transform:scaleX(1)}
.nav-cta{padding:8px 22px;border:1px solid var(--gold);color:var(--gold);font-size:0.74rem;font-weight:500;letter-spacing:0.1em;text-transform:uppercase;text-decoration:none;transition:background 0.2s,color 0.2s}
.nav-cta:hover{background:var(--gold);color:var(--ink)}

/* HERO */
#hero{min-height:100vh;display:grid;grid-template-columns:1fr 420px;align-items:center;gap:80px;padding:100px 64px 80px;position:relative;overflow:hidden}
.hero-vline{position:absolute;top:0;right:484px;bottom:0;width:1px;background:linear-gradient(180deg,transparent,var(--rule) 15%,var(--rule) 85%,transparent)}
.hero-dots{position:absolute;right:0;top:0;bottom:0;width:484px;background-image:radial-gradient(circle,rgba(201,169,110,0.07) 1px,transparent 1px);background-size:30px 30px}
.hero-eyebrow{display:flex;align-items:center;gap:14px;font-family:var(--mono);font-size:0.7rem;color:var(--gold);letter-spacing:0.15em;text-transform:uppercase;margin-bottom:28px;animation:rise 0.8s ease both}
.hero-eyebrow::before{content:'';width:36px;height:1px;background:var(--gold)}
h1.hero-title{font-family:var(--serif);font-size:clamp(3rem,5.5vw,5rem);font-weight:700;line-height:1.05;letter-spacing:-0.02em;color:#fff;animation:rise 0.8s 0.1s ease both}
h1.hero-title em{font-style:italic;color:var(--gold);font-weight:400}
.hero-desc{margin-top:28px;font-size:1rem;color:var(--txt-dim);line-height:1.82;max-width:500px;font-weight:300;animation:rise 0.8s 0.2s ease both}
.hero-actions{margin-top:44px;display:flex;gap:16px;flex-wrap:wrap;animation:rise 0.8s 0.3s ease both}
.btn-gold{display:inline-flex;align-items:center;gap:10px;background:var(--gold);color:var(--ink);padding:13px 28px;font-size:0.8rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;text-decoration:none;transition:background 0.2s,box-shadow 0.3s}
.btn-gold:hover{background:var(--gold-lt);box-shadow:0 8px 32px rgba(201,169,110,0.22)}
.btn-outline{display:inline-flex;align-items:center;gap:10px;background:transparent;color:var(--txt);padding:12px 28px;font-size:0.8rem;font-weight:500;letter-spacing:0.08em;text-transform:uppercase;border:1px solid var(--rule);text-decoration:none;transition:border-color 0.2s,color 0.2s}
.btn-outline:hover{border-color:var(--gold);color:var(--gold)}
.hero-right{position:relative;z-index:1;animation:rise 0.8s 0.2s ease both}
.hero-card{background:var(--ink2);border:1px solid var(--rule);padding:36px 32px}
.hc-label{font-family:var(--mono);font-size:0.63rem;color:var(--gold);letter-spacing:0.2em;text-transform:uppercase;margin-bottom:22px;padding-bottom:14px;border-bottom:1px solid var(--rule)}
.kv{display:flex;justify-content:space-between;align-items:baseline;padding:11px 0;border-bottom:1px solid rgba(42,42,50,0.5)}
.kv:last-child{border-bottom:none}
.kk{font-size:0.7rem;color:var(--mist);letter-spacing:0.06em}
.kv-val{font-size:0.86rem;color:var(--txt);text-align:right}
.kv-val.g{color:var(--gold);font-family:var(--mono);font-size:0.8rem}
.kv-val.on{color:#5dba87}
.metrics{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--rule);margin-top:1px}
.met{background:var(--ink2);padding:22px 18px;text-align:center}
.met-v{font-family:var(--serif);font-size:2rem;font-weight:700;color:var(--gold);line-height:1}
.met-l{font-size:0.65rem;color:var(--mist);text-transform:uppercase;letter-spacing:0.1em;margin-top:5px}
@keyframes rise{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}

/* SECTIONS */
.sec{padding:100px 64px}
.sec-alt{background:var(--ink2)}
.sec-head{margin-bottom:60px}
.sec-no{font-family:var(--mono);font-size:0.63rem;color:var(--mist);letter-spacing:0.2em;margin-bottom:12px;display:flex;align-items:center;gap:10px}
.sec-no::after{content:'';flex:1;max-width:40px;height:1px;background:var(--rule)}
h2.sec-title{font-family:var(--serif);font-size:clamp(1.9rem,3.5vw,2.7rem);font-weight:700;color:#fff;line-height:1.15}
h2.sec-title em{font-style:italic;color:var(--gold);font-weight:400}
.sec-sub{margin-top:14px;font-size:0.94rem;color:var(--txt-dim);max-width:520px;line-height:1.75;font-weight:300}

/* ABOUT */
.about-grid{display:grid;grid-template-columns:3fr 2fr;gap:80px;align-items:start}
.about-body{font-size:0.97rem;color:var(--txt-dim);line-height:1.88;font-weight:300}
.about-body p+p{margin-top:18px}
.about-body strong{color:var(--txt);font-weight:500}
.panel{background:var(--ink);border:1px solid var(--rule);padding:32px 28px}
.panel-lbl{font-family:var(--mono);font-size:0.61rem;color:var(--gold);letter-spacing:0.18em;text-transform:uppercase;margin-bottom:22px;padding-bottom:14px;border-bottom:1px solid var(--rule)}
.irow{display:flex;flex-direction:column;gap:3px;padding:11px 0;border-bottom:1px solid rgba(42,42,50,0.4)}
.irow:last-child{border-bottom:none}
.ik{font-size:0.66rem;color:var(--mist);text-transform:uppercase;letter-spacing:0.1em;font-family:var(--mono)}
.iv{font-size:0.87rem;color:var(--txt)}
.iv a{color:var(--gold);text-decoration:none}.iv a:hover{text-decoration:underline}

/* SKILLS */
.skills-wrap{display:grid;grid-template-columns:repeat(3,1fr);gap:2px;background:var(--rule)}
.sk{background:var(--ink);padding:30px 26px;transition:background 0.3s}
.sk:hover{background:var(--ink2)}
.sk-head{display:flex;align-items:center;gap:12px;margin-bottom:18px;padding-bottom:14px;border-bottom:1px solid var(--rule)}
.sk-ico{width:34px;height:34px;display:grid;place-items:center;background:var(--gold-dim);font-size:1rem;flex-shrink:0}
.sk-name{font-size:0.87rem;font-weight:600;color:#fff;letter-spacing:0.02em}
.chips{display:flex;flex-wrap:wrap;gap:6px}
.chip{font-family:var(--mono);font-size:0.64rem;color:var(--fog);background:var(--ink3);border:1px solid var(--rule);padding:4px 10px;letter-spacing:0.04em;transition:border-color 0.2s,color 0.2s}
.sk:hover .chip{border-color:rgba(201,169,110,0.18);color:var(--txt)}

/* EXPERIENCE */
.exp-wrap{display:flex;flex-direction:column}
.exp-item{display:grid;grid-template-columns:200px 1fr;border-bottom:1px solid var(--rule)}
.exp-item:last-child{border-bottom:none}
.exp-meta{padding:38px 36px 38px 0;border-right:1px solid var(--rule);display:flex;flex-direction:column;gap:7px}
.exp-period{font-family:var(--mono);font-size:0.68rem;color:var(--gold);letter-spacing:0.1em}
.exp-loc{font-size:0.76rem;color:var(--mist)}
.exp-body{padding:38px 0 38px 36px}
.exp-co{font-family:var(--serif);font-size:1.3rem;font-weight:600;color:#fff;margin-bottom:4px}
.exp-role{font-size:0.8rem;color:var(--gold);font-family:var(--mono);letter-spacing:0.08em;margin-bottom:22px}
.exp-pts{list-style:none;display:flex;flex-direction:column;gap:9px}
.exp-pts li{display:flex;gap:12px;font-size:0.91rem;color:var(--txt-dim);line-height:1.68;font-weight:300}
.exp-pts li::before{content:'—';color:var(--gold);flex-shrink:0}

/* PROJECTS */
.proj-wrap{display:grid;grid-template-columns:repeat(2,1fr);gap:2px;background:var(--rule)}
.pc{background:var(--ink);padding:44px 38px;display:flex;flex-direction:column;position:relative;overflow:hidden;transition:background 0.3s}
.pc:hover{background:var(--ink2)}
.pc::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:linear-gradient(90deg,var(--gold),transparent);transform:scaleX(0);transform-origin:left;transition:transform 0.5s}
.pc:hover::before{transform:scaleX(1)}
.pc-idx{font-family:var(--mono);font-size:0.61rem;color:var(--mist);letter-spacing:0.14em;margin-bottom:22px}
.pc-title{font-family:var(--serif);font-size:1.25rem;font-weight:600;color:#fff;line-height:1.3;margin-bottom:14px}
.pc-desc{font-size:0.89rem;color:var(--txt-dim);line-height:1.78;font-weight:300;flex:1;margin-bottom:26px}
.pc-stack{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:26px}
.pt{font-family:var(--mono);font-size:0.63rem;color:var(--gold);border:1px solid rgba(201,169,110,0.22);padding:3px 10px}
.pc-foot{display:flex;gap:20px;padding-top:22px;border-top:1px solid var(--rule)}
.pl{font-family:var(--mono);font-size:0.68rem;color:var(--mist);text-decoration:none;letter-spacing:0.08em;text-transform:uppercase;display:flex;align-items:center;gap:6px;transition:color 0.2s}
.pl:hover{color:var(--gold)}
.pl svg{width:11px;height:11px}

/* CERTS */
.certs-wrap{display:grid;grid-template-columns:repeat(3,1fr);gap:2px;background:var(--rule)}
.ci{background:var(--ink2);padding:30px 26px;display:flex;flex-direction:column;gap:9px;transition:background 0.3s}
.ci:hover{background:var(--ink3)}
.ci-badge{width:30px;height:30px;display:grid;place-items:center;background:var(--gold-dim);font-size:0.85rem;margin-bottom:2px}
.ci-prov{font-family:var(--mono);font-size:0.6rem;color:var(--gold);letter-spacing:0.15em;text-transform:uppercase}
.ci-name{font-size:0.93rem;font-weight:600;color:#fff;line-height:1.35}
.ci-date{font-family:var(--mono);font-size:0.66rem;color:var(--mist)}

/* ACHIEVEMENTS */
.ach-wrap{display:grid;grid-template-columns:repeat(3,1fr);gap:0;background:var(--rule);border:1px solid var(--rule)}
.ai{background:var(--ink);padding:40px 34px;border-right:1px solid var(--rule);transition:background 0.3s}
.ai:last-child{border-right:none}
.ai:hover{background:var(--ink2)}
.ai-num{font-family:var(--serif);font-size:3.2rem;font-weight:700;color:var(--gold);line-height:1;margin-bottom:12px}
.ai-lbl{font-size:0.92rem;font-weight:600;color:#fff;margin-bottom:9px}
.ai-desc{font-size:0.84rem;color:var(--txt-dim);line-height:1.65;font-weight:300}

/* CONTACT */
#contact{padding:100px 64px}
.ct-wrap{display:grid;grid-template-columns:1fr 1fr;gap:2px;background:var(--rule);border:1px solid var(--rule)}
.ct-left{background:var(--ink);padding:62px 54px}
.ct-right{background:var(--ink2);padding:62px 54px}
.ct-over{font-family:var(--mono);font-size:0.62rem;color:var(--gold);letter-spacing:0.2em;text-transform:uppercase;margin-bottom:18px}
h2.ct-head{font-family:var(--serif);font-size:clamp(1.8rem,2.8vw,2.4rem);font-weight:700;color:#fff;line-height:1.15;margin-bottom:18px}
h2.ct-head em{font-style:italic;color:var(--gold);font-weight:400}
.ct-body{font-size:0.95rem;color:var(--txt-dim);line-height:1.82;font-weight:300}
.cl{display:flex;align-items:center;gap:14px;padding:18px 0;border-bottom:1px solid var(--rule);text-decoration:none;transition:padding-left 0.22s}
.cl:last-child{border-bottom:none}
.cl:hover{padding-left:8px}
.cl-ico{width:38px;height:38px;display:grid;place-items:center;background:var(--gold-dim);font-size:0.95rem;flex-shrink:0;transition:background 0.2s}
.cl:hover .cl-ico{background:rgba(201,169,110,0.18)}
.cl-lbl{font-size:0.65rem;color:var(--mist);text-transform:uppercase;letter-spacing:0.1em;font-family:var(--mono)}
.cl-val{font-size:0.9rem;color:var(--txt);transition:color 0.2s}
.cl:hover .cl-val{color:var(--gold)}

/* FOOTER */
footer{background:var(--ink);border-top:1px solid var(--rule);padding:26px 64px;display:flex;justify-content:space-between;align-items:center}
.f-brand{font-family:var(--serif);font-size:0.93rem;color:var(--fog)}
.f-brand em{font-style:italic;color:var(--gold)}
.f-copy{font-family:var(--mono);font-size:0.6rem;color:var(--mist);letter-spacing:0.08em}

/* REVEAL */
.r{opacity:0;transform:translateY(20px);transition:opacity 0.65s ease,transform 0.65s ease}
.r.v{opacity:1;transform:translateY(0)}
.r.d1{transition-delay:.08s}.r.d2{transition-delay:.16s}.r.d3{transition-delay:.24s}

@media(max-width:900px){
  nav{padding:0 20px}.nav-menu{display:none}
  #hero{grid-template-columns:1fr;padding:90px 20px 56px;gap:40px}
  .hero-vline,.hero-dots,.hero-right{display:none}
  .sec,.sec-alt,#contact{padding:64px 20px}
  .about-grid{grid-template-columns:1fr;gap:36px}
  .skills-wrap{grid-template-columns:1fr 1fr}
  .proj-wrap,.certs-wrap,.ct-wrap{grid-template-columns:1fr}
  .ach-wrap{grid-template-columns:1fr}
  .ai{border-right:none;border-bottom:1px solid var(--rule)}
  .ai:last-child{border-bottom:none}
  .exp-item{grid-template-columns:1fr}
  .exp-meta{border-right:none;padding:22px 0 16px;flex-direction:row;gap:20px;border-bottom:1px solid var(--rule)}
  .exp-body{padding:22px 0}
  footer{padding:22px 20px;flex-direction:column;gap:8px;text-align:center}
}
</style>
</head>
<body>

<nav>
  <div class="nav-brand">Souvik <em>Nandi</em></div>
  <div class="nav-menu">
    <a href="#about">About</a>
    <a href="#skills">Skills</a>
    <a href="#experience">Experience</a>
    <a href="#projects">Projects</a>
    <a href="#certifications">Certs</a>
    <a href="#contact" class="nav-cta">Hire Me</a>
  </div>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-vline"></div>
  <div class="hero-dots"></div>
  <div>
    <div class="hero-eyebrow">Software Engineer &amp; AI/ML Student</div>
    <h1 class="hero-title">Building software<br/>that <em>matters.</em></h1>
    <p class="hero-desc">B.Tech CSE (AI &amp; ML) student at IEM Kolkata — crafting full-stack applications, intelligent systems, and embedded solutions with a commitment to clean, scalable engineering.</p>
    <div class="hero-actions">
      <a href="#projects" class="btn-gold">View My Work</a>
      <a href="#contact" class="btn-outline">Get In Touch</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-card">
      <div class="hc-label">// Profile Overview</div>
      <div class="kv"><span class="kk">Role</span><span class="kv-val g">Software Engineer</span></div>
      <div class="kv"><span class="kk">Specialization</span><span class="kv-val">CSE — AI &amp; ML</span></div>
      <div class="kv"><span class="kk">Institution</span><span class="kv-val">IEM, Kolkata</span></div>
      <div class="kv"><span class="kk">Graduation</span><span class="kv-val g">2027</span></div>
      <div class="kv"><span class="kk">Status</span><span class="kv-val on">● Open to Opportunities</span></div>
    </div>
    <div class="metrics">
      <div class="met"><div class="met-v" id="m1">8.54</div><div class="met-l">CGPA</div></div>
      <div class="met"><div class="met-v" id="m2">150+</div><div class="met-l">Problems Solved</div></div>
      <div class="met"><div class="met-v" id="m3">3</div><div class="met-l">Certifications</div></div>
      <div class="met"><div class="met-v">2+</div><div class="met-l">Projects Shipped</div></div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about" class="sec sec-alt">
  <div class="sec-head r">
    <div class="sec-no">01 &nbsp; About</div>
    <h2 class="sec-title">Turning ideas into <em>engineered reality</em></h2>
  </div>
  <div class="about-grid">
    <div class="about-body r">
      <p>I'm <strong>Souvik Nandi</strong>, a motivated software engineering student specializing in <strong>Artificial Intelligence &amp; Machine Learning</strong> at the Institute of Engineering and Management, Kolkata. With a strong academic record and hands-on industry experience, I build software that is purposeful, performant, and production-ready.</p>
      <p>My engineering journey spans <strong>full-stack web development</strong>, <strong>embedded systems &amp; robotics</strong>, and <strong>AI-integrated applications</strong>. I completed a professional internship at IDC Lab and Software Pvt Ltd, contributing to responsive web interfaces and maintainable codebases within a real Agile environment.</p>
      <p>I'm seeking <strong>internships and entry-level engineering roles</strong> where I can contribute meaningfully, learn rapidly, and grow alongside a driven engineering team. I believe in writing code that others can read, understand, and build upon.</p>
    </div>
    <div class="panel r d1">
      <div class="panel-lbl">// Contact Details</div>
      <div class="irow"><span class="ik">Location</span><span class="iv">Krishnagar, West Bengal, IN</span></div>
      <div class="irow"><span class="ik">Phone</span><span class="iv">+91 62943 96389</span></div>
      <div class="irow"><span class="ik">Email</span><span class="iv"><a href="mailto:souviknandi19102005@gmail.com">souviknandi19102005@gmail.com</a></span></div>
      <div class="irow"><span class="ik">LinkedIn</span><span class="iv"><a href="https://linkedin.com" target="_blank">linkedin.com/in/souvik</a></span></div>
      <div class="irow"><span class="ik">GitHub</span><span class="iv"><a href="https://github.com" target="_blank">github.com/souvik</a></span></div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills" class="sec">
  <div class="sec-head r">
    <div class="sec-no">02 &nbsp; Skills</div>
    <h2 class="sec-title">Technical <em>Expertise</em></h2>
    <p class="sec-sub">A curated stack built through academic study, professional internship, and independent project development.</p>
  </div>
  <div class="skills-wrap r">
    <div class="sk"><div class="sk-head"><div class="sk-ico">⌨</div><span class="sk-name">Languages</span></div><div class="chips"><span class="chip">Java</span><span class="chip">Python</span><span class="chip">C</span><span class="chip">C++</span><span class="chip">JavaScript</span></div></div>
    <div class="sk"><div class="sk-head"><div class="sk-ico">🧱</div><span class="sk-name">Frameworks</span></div><div class="chips"><span class="chip">React.js</span><span class="chip">Node.js</span><span class="chip">Express.js</span><span class="chip">Bootstrap</span><span class="chip">HTML5</span><span class="chip">CSS3</span></div></div>
    <div class="sk"><div class="sk-head"><div class="sk-ico">🗄</div><span class="sk-name">Databases</span></div><div class="chips"><span class="chip">MongoDB</span><span class="chip">MySQL</span></div></div>
    <div class="sk"><div class="sk-head"><div class="sk-ico">🛠</div><span class="sk-name">Tools &amp; DevOps</span></div><div class="chips"><span class="chip">Git</span><span class="chip">GitHub</span><span class="chip">ArduinoIDE</span><span class="chip">Agile / Scrum</span></div></div>
    <div class="sk"><div class="sk-head"><div class="sk-ico">🧠</div><span class="sk-name">Core CS</span></div><div class="chips"><span class="chip">DSA</span><span class="chip">OOP</span><span class="chip">DBMS</span><span class="chip">Operating Systems</span><span class="chip">Software Eng.</span></div></div>
    <div class="sk"><div class="sk-head"><div class="sk-ico">🔐</div><span class="sk-name">Security &amp; AI</span></div><div class="chips"><span class="chip">Cryptography</span><span class="chip">Cyber Security</span><span class="chip">LLM Integration</span><span class="chip">Embedded Systems</span></div></div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience" class="sec sec-alt">
  <div class="sec-head r">
    <div class="sec-no">03 &nbsp; Experience</div>
    <h2 class="sec-title">Professional <em>History</em></h2>
  </div>
  <div class="exp-wrap r">
    <div class="exp-item">
      <div class="exp-meta">
        <div class="exp-period">Jul 2025 — Sep 2025</div>
        <div class="exp-loc">Kolkata, India</div>
      </div>
      <div class="exp-body">
        <div class="exp-co">IDC Lab and Software Pvt Ltd</div>
        <div class="exp-role">Web Development Intern</div>
        <ul class="exp-pts">
          <li>Developed responsive, interactive web interfaces using HTML5, CSS3, and JavaScript ensuring cross-browser compatibility and optimal UX.</li>
          <li>Collaborated with the development team via GitHub for version control, participating in code reviews and maintaining clean, well-documented codebases.</li>
          <li>Implemented modern UI/UX principles and CSS frameworks to deliver visually polished, user-friendly web applications.</li>
          <li>Gained real-world exposure to full-stack development workflows and Agile methodologies in a professional environment.</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects" class="sec">
  <div class="sec-head r">
    <div class="sec-no">04 &nbsp; Projects</div>
    <h2 class="sec-title">Selected <em>Work</em></h2>
    <p class="sec-sub">End-to-end projects demonstrating full-stack development, AI integration, and embedded systems engineering.</p>
  </div>
  <div class="proj-wrap r">
    <div class="pc">
      <div class="pc-idx">Project 01 &nbsp;/&nbsp; Fintech + AI</div>
      <h3 class="pc-title">Smart Finance Tracker with LLM-Powered Analysis</h3>
      <p class="pc-desc">A personal finance application integrating Large Language Models to deliver personalized insights, budget optimization, spending trend analysis, and future expense predictions. Features secure REST APIs, dual-database architecture, and AI-driven financial recommendations built for real-world fintech use cases.</p>
      <div class="pc-stack"><span class="pt">Java</span><span class="pt">JavaScript</span><span class="pt">MySQL</span><span class="pt">MongoDB</span><span class="pt">LLM / AI</span><span class="pt">REST APIs</span></div>
      <div class="pc-foot">
        <a href="#" class="pl"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>Live Demo</a>
        <a href="#" class="pl"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>Source Code</a>
      </div>
    </div>
    <div class="pc">
      <div class="pc-idx">Project 02 &nbsp;/&nbsp; Embedded Systems</div>
      <h3 class="pc-title">Arduino Object Tracker &amp; Follower Robot Car</h3>
      <p class="pc-desc">An autonomous robot car engineered to detect, track, and follow a moving object in real time using ultrasonic and IR sensor arrays. Built from hardware assembly through firmware — with C/C++ decision-making logic, sensor calibration, and debugging for reliable autonomous operation in variable environments.</p>
      <div class="pc-stack"><span class="pt">C / C++</span><span class="pt">Arduino</span><span class="pt">Embedded Systems</span><span class="pt">Sensor Integration</span><span class="pt">Robotics</span></div>
      <div class="pc-foot">
        <a href="#" class="pl"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 01-2 2H5a2 2 0 01-2-2V8a2 2 0 012-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>Live Demo</a>
        <a href="#" class="pl"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 00-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0020 4.77 5.07 5.07 0 0019.91 1S18.73.65 16 2.48a13.38 13.38 0 00-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 005 4.77a5.44 5.44 0 00-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 009 18.13V22"/></svg>Source Code</a>
      </div>
    </div>
  </div>
</section>

<!-- CERTIFICATIONS -->
<section id="certifications" class="sec sec-alt">
  <div class="sec-head r">
    <div class="sec-no">05 &nbsp; Certifications</div>
    <h2 class="sec-title">Credentials &amp; <em>Coursework</em></h2>
  </div>
  <div class="certs-wrap r">
    <div class="ci"><div class="ci-badge">🔐</div><div class="ci-prov">Coursera</div><div class="ci-name">Applied Cryptography</div><div class="ci-date">October 2025</div></div>
    <div class="ci"><div class="ci-badge">🛡</div><div class="ci-prov">Coursera</div><div class="ci-name">Cyber Security Fundamentals</div><div class="ci-date">October 2025</div></div>
    <div class="ci"><div class="ci-badge">⚙</div><div class="ci-prov">Coursera</div><div class="ci-name">Advanced System Security Topics</div><div class="ci-date">October 2025</div></div>
  </div>
</section>

<!-- ACHIEVEMENTS -->
<section id="achievements" class="sec">
  <div class="sec-head r">
    <div class="sec-no">06 &nbsp; Achievements</div>
    <h2 class="sec-title">Key <em>Highlights</em></h2>
  </div>
  <div class="ach-wrap r">
    <div class="ai"><div class="ai-num">150+</div><div class="ai-lbl">Coding Problems Solved</div><div class="ai-desc">Demonstrated algorithmic proficiency on LeetCode, HackerRank, and GeeksforGeeks — covering data structures, graph algorithms, and dynamic programming.</div></div>
    <div class="ai"><div class="ai-num">8.54</div><div class="ai-lbl">CGPA at IEM Kolkata</div><div class="ai-desc">Maintaining a strong academic record in the B.Tech CSE program, specializing in Artificial Intelligence and Machine Learning.</div></div>
    <div class="ai"><div class="ai-num">∞</div><div class="ai-lbl">Hackathon Participant</div><div class="ai-desc">Competed in multiple hackathons, collaborating in cross-functional teams to ideate, prototype, and deliver solutions under tight constraints.</div></div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="ct-wrap r">
    <div class="ct-left">
      <div class="ct-over">// Let's Connect</div>
      <h2 class="ct-head">Ready to build something <em>great together?</em></h2>
      <p class="ct-body">I'm actively seeking internship and entry-level opportunities in software engineering, full-stack development, or AI/ML engineering. If my profile aligns with what your team needs, I'd love to connect.</p>
    </div>
    <div class="ct-right">
      <a href="mailto:souviknandi19102005@gmail.com" class="cl"><div class="cl-ico">✉</div><div><div class="cl-lbl">Email</div><div class="cl-val">souviknandi19102005@gmail.com</div></div></a>
      <a href="tel:+916294396389" class="cl"><div class="cl-ico">📞</div><div><div class="cl-lbl">Phone</div><div class="cl-val">+91 62943 96389</div></div></a>
      <a href="https://linkedin.com" target="_blank" class="cl"><div class="cl-ico" style="font-family:serif;font-weight:700;font-size:0.8rem">in</div><div><div class="cl-lbl">LinkedIn</div><div class="cl-val">linkedin.com/in/souvik</div></div></a>
      <a href="https://github.com" target="_blank" class="cl"><div class="cl-ico">⌥</div><div><div class="cl-lbl">GitHub</div><div class="cl-val">github.com/souvik</div></div></a>
    </div>
  </div>
</section>

<footer>
  <div class="f-brand">Souvik <em>Nandi</em> — Software Engineer</div>
  <div class="f-copy">IEM Kolkata &nbsp;·&nbsp; B.Tech CSE AI/ML &nbsp;·&nbsp; Batch 2027</div>
</footer>

<script>
  const obs = new IntersectionObserver(entries => {
    entries.forEach(e => { if(e.isIntersecting) e.target.classList.add('v'); });
  }, { threshold: 0.08 });
  document.querySelectorAll('.r').forEach(el => obs.observe(el));

  function count(el, target, dec=0, suf='') {
    let v=0; const inc=target/55;
    const go=()=>{ v=Math.min(v+inc,target); el.textContent=v.toFixed(dec)+suf; if(v<target)requestAnimationFrame(go); };
    requestAnimationFrame(go);
  }
  setTimeout(()=>{
    count(document.getElementById('m1'),8.54,2);
    let v2=0; const iv=setInterval(()=>{ v2=Math.min(v2+3,150); document.getElementById('m2').textContent=v2+'+'; if(v2>=150)clearInterval(iv); },18);
    count(document.getElementById('m3'),3,0);
  },500);
</script>
</body>
</html>
