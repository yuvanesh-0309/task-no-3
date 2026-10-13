<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Website Wireframe — Task 3</title>
<style>
:root{--ink:#171717;--paper:#f7f7f5;--white:#fff;--gray:#e9e9e7;--mid:#bcbcb8;--purple:#9877ff;--yellow:#edfa3c}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{margin:0;color:var(--ink);background:var(--paper);font:15px Arial,sans-serif;line-height:1.55}
.container{width:min(1100px,calc(100% - 36px));margin:auto}
.topbar{background:var(--white);border-bottom:1px solid var(--ink)}
.nav{min-height:68px;display:flex;align-items:center;justify-content:space-between;gap:18px}
.logo{font-size:18px;font-weight:800;letter-spacing:-.05em}
.logo span{display:inline-block;padding:4px 8px;background:var(--yellow);border:1px solid var(--ink);margin-right:6px}
.navlinks{display:flex;align-items:center;gap:22px}
.navlinks a{color:inherit;text-decoration:none;font-size:13px;font-weight:700}
.navlinks a:hover{text-decoration:underline}
.navlinks .cta,.button{background:var(--yellow);border:1px solid var(--ink);box-shadow:3px 3px 0 var(--ink);padding:9px 13px}
.menu{display:none;background:var(--white);border:1px solid var(--ink);padding:8px 10px}
.hero{padding:68px 0 56px;border-bottom:1px solid var(--ink)}
.hero-grid{display:grid;grid-template-columns:1.1fr .9fr;gap:44px;align-items:center}
.eyebrow{display:inline-block;background:var(--purple);border:1px solid var(--ink);box-shadow:3px 3px 0 var(--ink);padding:5px 9px;font-size:10px;font-weight:bold;text-transform:uppercase;letter-spacing:.1em}
.hero h1{font-size:clamp(42px,7vw,72px);line-height:.97;letter-spacing:-.06em;margin:20px 0 14px;max-width:620px}
.hero p{max-width:520px;color:#555;margin:0 0 22px}
.button{display:inline-block;color:var(--ink);text-decoration:none;font-weight:bold;font-size:12px;text-transform:uppercase}
.placeholder{background:var(--gray);border:1px solid var(--ink);position:relative;min-height:250px;display:grid;place-items:center;color:#666;font-size:12px;overflow:hidden}
.placeholder:before,.placeholder:after{content:'';position:absolute;width:142%;height:1px;background:var(--mid);transform:rotate(35deg)}
.placeholder:after{transform:rotate(-35deg)}
.placeholder span{position:relative;z-index:1;background:#eee;padding:4px 7px}
.section{padding:56px 0;border-bottom:1px solid var(--ink)}
.section-head{display:flex;justify-content:space-between;align-items:end;gap:22px;margin-bottom:25px}
.kicker{font-size:10px;text-transform:uppercase;letter-spacing:.12em;color:#666}
.section h2{font-size:clamp(28px,4vw,42px);line-height:1.05;letter-spacing:-.05em;margin:6px 0 0}
.section-head p{max-width:390px;color:#555;font-size:13px;margin:0}
.services{display:grid;grid-template-columns:repeat(3,1fr);gap:14px}
.service{background:var(--white);border:1px solid var(--ink);padding:18px}
.service .placeholder{min-height:100px;margin-bottom:15px}
.service h3{font-size:16px;margin:0 0 5px}
.service p{font-size:12px;color:#555;margin:0}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:24px}
.about-grid .placeholder{min-height:260px}
.about-copy p{color:#555;font-size:13px}
.stats{display:flex;gap:10px;margin-top:20px}
.stat{border:1px solid var(--ink);background:var(--white);padding:10px 13px;flex:1}
.stat b{display:block;font-size:20px}
.stat small{font-size:10px;color:#666}
.team{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:28px}
.person{border:1px solid var(--ink);background:var(--white);padding:14px;text-align:center}
.avatar{width:70px;height:70px;border-radius:50%;border:1px solid var(--ink);background:var(--gray);margin:0 auto 9px;position:relative;overflow:hidden}
.avatar:before{content:'';position:absolute;width:30px;height:30px;border:1px solid var(--mid);border-radius:50%;left:19px;top:10px}
.avatar:after{content:'';position:absolute;width:48px;height:30px;border:1px solid var(--mid);border-radius:50% 50% 0 0;left:10px;top:47px}
.person b{font-size:12px}
.person small{display:block;color:#666;font-size:10px}
.contact-grid{display:grid;grid-template-columns:.8fr 1.2fr;gap:34px}
.contact-info p{font-size:13px;color:#555}
.contact-info ul{padding:0;list-style:none;font-size:12px;line-height:2}
.form{display:grid;gap:12px}
.form label{font-size:11px;font-weight:bold}
.form input,.form textarea{width:100%;display:block;margin-top:5px;padding:11px;border:1px solid var(--ink);background:var(--white);font:13px Arial}
.form textarea{min-height:100px;resize:vertical}
.form button{cursor:pointer;font:700 11px Arial;text-transform:uppercase;color:var(--ink);justify-self:start}
.map{margin-top:25px;min-height:160px}
.map:before,.map:after{width:140%}
.footer{padding:20px 0;font-size:10px;color:#666}
.footer .container{display:flex;justify-content:space-between;gap:15px;flex-wrap:wrap}
.notice{position:fixed;bottom:18px;left:50%;transform:translate(-50%,20px);opacity:0;background:var(--ink);color:white;padding:10px 14px;font-size:12px;transition:.2s;pointer-events:none}
.notice.show{opacity:1;transform:translate(-50%,0)}
@media(max-width:700px){
  .container{width:calc(100% - 28px)}
  .menu{display:block}
  .navlinks{display:none;position:absolute;top:68px;left:0;right:0;padding:16px 20px;background:var(--paper);border-bottom:1px solid var(--ink);z-index:3;align-items:flex-start;flex-direction:column}
  .navlinks.open{display:flex}
  .hero{padding:43px 0}
  .hero-grid{grid-template-columns:1fr;gap:24px}
  .hero .placeholder{min-height:190px}
  .section{padding:42px 0}
  .section-head{align-items:flex-start;flex-direction:column}
  .services{grid-template-columns:1fr}
  .service .placeholder{min-height:130px}
  .about-grid,.contact-grid{grid-template-columns:1fr}
  .about-grid .placeholder{min-height:190px}
  .team{gap:8px}
  .person{padding:10px 5px}
  .stats{gap:6px}
  .stat{padding:8px}
  .stat b{font-size:16px}
}
</style>
</head>
<body>
<header class="topbar">
  <nav class="nav container" aria-label="Main navigation">
    <a class="logo" href="#home"><span>W</span> WIREFRAME STUDIO</a>
    <button class="menu" aria-expanded="false" aria-controls="navlinks">MENU</button>
    <div class="navlinks" id="navlinks">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#services">Services</a>
      <a href="#contact">Contact</a>
      <a class="cta" href="#contact">Get in touch ↗</a>
    </div>
  </nav>
</header>

<main>
  <section class="hero" id="home">
    <div class="container hero-grid">
      <div>
        <span class="eyebrow">01 · Home page</span>
        <h1>A clear headline goes right here.</h1>
        <p>Use this space to explain what your business does, who it helps, and why visitors should take the next step.</p>
        <a class="button" href="#services">Explore services →</a>
      </div>
      <div class="placeholder" role="img" aria-label="Hero image placeholder">
        <span>Hero image</span>
      </div>
    </div>
  </section>

  <section class="section" id="services">
    <div class="container">
      <div class="section-head">
        <div><div class="kicker">02 · Services page</div><h2>What we can help with</h2></div>
        <p>A short introduction to the services. Keep the information easy to scan and make each offer distinct.</p>
      </div>
      <div class="services">
        <article class="service">
          <div class="placeholder"><span>Image</span></div>
          <h3>Service title</h3>
          <p>A short description explaining the value of this service.</p>
        </article>
        <article class="service">
          <div class="placeholder"><span>Image</span></div>
          <h3>Service title</h3>
          <p>A short description explaining the value of this service.</p>
        </article>
        <article class="service">
          <div class="placeholder"><span>Image</span></div>
          <h3>Service title</h3>
          <p>A short description explaining the value of this service.</p>
        </article>
      </div>
    </div>
  </section>

  <section class="section" id="about">
    <div class="container">
      <div class="section-head">
        <div><div class="kicker">03 · About page</div><h2>People behind the work</h2></div>
      </div>
      <div class="about-grid">
        <div class="placeholder"><span>Team or studio photo</span></div>
        <div class="about-copy">
          <h3>About our team</h3>
          <p>Introduce the company, its purpose, and what makes its approach useful to customers. Use short paragraphs and clear headings.</p>
          <h3>Our mission</h3>
          <p>Share the principle that guides the work and how it helps customers get a better result.</p>
          <div class="stats">
            <div class="stat"><b>10+</b><small>Years of experience</small></div>
            <div class="stat"><b>80+</b><small>Projects delivered</small></div>
          </div>
        </div>
      </div>
      <div class="team">
        <div class="person"><div class="avatar"></div><b>Team member</b><small>Role / specialty</small></div>
        <div class="person"><div class="avatar"></div><b>Team member</b><small>Role / specialty</small></div>
        <div class="person"><div class="avatar"></div><b>Team member</b><small>Role / specialty</small></div>
      </div>
    </div>
  </section>

  <section class="section" id="contact">
    <div class="container">
      <div class="section-head">
        <div><div class="kicker">04 · Contact page</div><h2>Let’s talk about your project</h2></div>
        <p>Tell visitors how to reach you and what will happen after they send a message.</p>
      </div>
      <div class="contact-grid">
        <div class="contact-info">
          <h3>Contact details</h3>
          <p>Have a question or an idea? Send a note and we’ll get back to you.</p>
          <ul>
            <li>✉ hello@example.com</li>
            <li>☎ (555) 010-1234</li>
            <li>⌖ 123 Main Street, Your City</li>
          </ul>
        </div>
        <form class="form" id="contact-form">
          <label>Your name<input required placeholder="Name"></label>
          <label>Email address<input type="email" required placeholder="you@example.com"></label>
          <label>Your message<textarea required placeholder="How can we help?"></textarea></label>
          <button class="button" type="submit">Send message →</button>
        </form>
      </div>
      <div class="placeholder map"><span>Map / location</span></div>
    </div>
  </section>
</main>

<footer class="footer">
  <div class="container">
    <span>WIREFRAME STUDIO · WEBSITE STRUCTURE</span>
    <span>Home · About · Services · Contact</span>
    <span>© 2026</span>
  </div>
</footer>
<div class="notice" role="status" aria-live="polite">
  Message form preview — connect a form service to receive submissions.
</div>

<script>
const menu = document.querySelector('.menu');
const nav = document.querySelector('.navlinks');

menu.addEventListener('click', () => {
  const open = nav.classList.toggle('open');
  menu.setAttribute('aria-expanded', open);
});

nav.querySelectorAll('a').forEach(link => {
  link.addEventListener('click', () => {
    nav.classList.remove('open');
    menu.setAttribute('aria-expanded', 'false');
  });
});

const form = document.querySelector('#contact-form');
const notice = document.querySelector('.notice');

form.addEventListener('submit', event => {
  event.preventDefault();
  notice.classList.add('show');
  setTimeout(() => notice.classList.remove('show'), 2600);
  form.reset();
});
</script>
</body>
</html>
