<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Munawar Abbas — Full-Stack Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;500;600;700;800&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --c-teal:#00FFD1;--c-purple:#7B61FF;--c-red:#FF3B6B;--c-amber:#FF9500;--c-blue:#00B4FF;
  --bg:#060810;--bg2:#0C1020;--bg3:#111828;--bg4:#0f1520;
  --text:#E8EAF0;--muted:#6B7394;--subtle:#3A4060;
  --border:rgba(123,97,255,0.18);--border2:rgba(0,255,209,0.15);
  --glow-purple:rgba(123,97,255,0.15);--glow-teal:rgba(0,255,209,0.1);
}
html{scroll-behavior:smooth}
body{
  font-family:'Syne',sans-serif;
  background:var(--bg);
  color:var(--text);
  overflow-x:hidden;
  cursor:none;
}

/* CURSOR */
#cursor{position:fixed;width:10px;height:10px;background:var(--c-teal);border-radius:50%;pointer-events:none;z-index:9999;transition:transform 0.1s;mix-blend-mode:difference}
#cursor-ring{position:fixed;width:36px;height:36px;border:1px solid rgba(0,255,209,0.4);border-radius:50%;pointer-events:none;z-index:9998;transition:all 0.15s ease}

/* SCROLLBAR */
::-webkit-scrollbar{width:4px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--c-purple);border-radius:2px}

/* NAV */
nav{
  position:fixed;top:0;left:0;right:0;z-index:100;
  display:flex;align-items:center;justify-content:space-between;
  padding:16px 48px;
  background:rgba(6,8,16,0.85);
  backdrop-filter:blur(20px);
  border-bottom:1px solid var(--border);
}
.nav-logo{
  font-family:'Space Mono',monospace;
  font-size:13px;color:var(--c-teal);
  letter-spacing:0.1em;
  display:flex;align-items:center;gap:8px;
}
.nav-logo::before{content:'◈';font-size:16px}
.nav-links{display:flex;gap:32px}
.nav-links a{
  font-family:'Space Mono',monospace;font-size:11px;
  color:var(--muted);text-decoration:none;letter-spacing:0.08em;
  text-transform:uppercase;transition:color 0.2s;
}
.nav-links a:hover{color:var(--c-teal)}
.nav-cta{
  font-family:'Space Mono',monospace;font-size:11px;
  color:var(--c-teal);border:1px solid rgba(0,255,209,0.35);
  padding:8px 18px;border-radius:6px;text-decoration:none;
  transition:background 0.2s;letter-spacing:0.08em;
}
.nav-cta:hover{background:rgba(0,255,209,0.1)}

/* GRID BG */
.grid-bg{
  position:fixed;top:0;left:0;right:0;bottom:0;
  background-image:
    linear-gradient(rgba(123,97,255,0.035) 1px,transparent 1px),
    linear-gradient(90deg,rgba(123,97,255,0.035) 1px,transparent 1px);
  background-size:44px 44px;
  pointer-events:none;z-index:0;
}

/* SECTIONS */
section{position:relative;z-index:1}

/* ═══════════ HERO ═══════════ */
#hero{
  min-height:100vh;
  display:flex;align-items:center;
  padding:120px 48px 80px;
  position:relative;overflow:hidden;
}
.hero-orb{
  position:absolute;border-radius:50%;pointer-events:none;
  filter:blur(120px);
}
.orb-a{width:600px;height:600px;background:rgba(123,97,255,0.1);top:-200px;right:-200px}
.orb-b{width:400px;height:400px;background:rgba(0,255,209,0.07);bottom:-100px;left:-100px}
.orb-c{width:300px;height:300px;background:rgba(255,59,107,0.05);top:50%;left:40%}

.hero-left{flex:1;max-width:680px}
.hero-right{flex:0 0 280px;display:flex;flex-direction:column;align-items:center;gap:20px}

.status-badge{
  display:inline-flex;align-items:center;gap:8px;
  background:rgba(0,255,209,0.06);
  border:1px solid rgba(0,255,209,0.2);
  border-radius:100px;padding:6px 16px;
  font-family:'Space Mono',monospace;font-size:11px;
  color:var(--c-teal);letter-spacing:0.08em;margin-bottom:28px;
}
.pulse{
  width:7px;height:7px;background:var(--c-teal);
  border-radius:50%;animation:pulseAnim 2s ease-in-out infinite;
}
@keyframes pulseAnim{0%,100%{opacity:1;box-shadow:0 0 0 0 rgba(0,255,209,0.4)}50%{opacity:0.5;box-shadow:0 0 0 6px rgba(0,255,209,0)}}

.hero-name{
  font-size:80px;font-weight:800;line-height:0.95;
  letter-spacing:-0.04em;margin-bottom:16px;
}
.name-white{color:var(--text)}
.name-grad{
  background:linear-gradient(135deg,var(--c-purple) 0%,var(--c-teal) 60%,var(--c-blue) 100%);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
}
.hero-role{
  font-family:'Space Mono',monospace;font-size:14px;
  color:var(--muted);letter-spacing:0.05em;margin-bottom:28px;
  min-height:22px;
}
.hero-role span{color:var(--c-teal)}
.tw-cursor{
  display:inline-block;width:2px;height:15px;
  background:var(--c-teal);margin-left:2px;
  vertical-align:middle;animation:blink 1s step-end infinite;
}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0}}

.hero-desc{
  font-size:17px;color:#8A95B8;line-height:1.75;
  max-width:560px;margin-bottom:40px;
}
.hero-desc strong{color:var(--text);font-weight:600}

.hero-btns{display:flex;gap:14px;flex-wrap:wrap}
.btn-primary{
  padding:14px 32px;background:linear-gradient(135deg,var(--c-purple),var(--c-teal));
  border:none;border-radius:8px;font-family:'Space Mono',monospace;
  font-size:12px;color:#060810;letter-spacing:0.08em;cursor:pointer;
  text-decoration:none;transition:transform 0.2s,box-shadow 0.2s;font-weight:700;
}
.btn-primary:hover{transform:translateY(-2px);box-shadow:0 10px 40px rgba(123,97,255,0.3)}
.btn-outline{
  padding:14px 32px;background:transparent;
  border:1px solid var(--border);border-radius:8px;
  font-family:'Space Mono',monospace;font-size:12px;
  color:var(--text);letter-spacing:0.08em;cursor:pointer;
  text-decoration:none;transition:all 0.2s;
}
.btn-outline:hover{border-color:var(--c-teal);color:var(--c-teal)}

/* HERO STATS CARD */
.hero-stats-card{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:16px;padding:28px 24px;width:100%;
  position:relative;overflow:hidden;
}
.hero-stats-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,var(--c-purple),var(--c-teal));
}
.hero-stat{margin-bottom:20px}
.hero-stat:last-child{margin-bottom:0}
.hero-stat-val{font-size:32px;font-weight:800;letter-spacing:-0.04em;line-height:1}
.hero-stat-val.teal{background:linear-gradient(90deg,var(--c-teal),var(--c-blue));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.hero-stat-val.purple{background:linear-gradient(90deg,var(--c-purple),var(--c-red));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.hero-stat-val.amber{background:linear-gradient(90deg,var(--c-amber),var(--c-red));-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text}
.hero-stat-label{font-family:'Space Mono',monospace;font-size:10px;color:var(--muted);letter-spacing:0.1em;text-transform:uppercase;margin-top:4px}
.hero-stat-divider{height:1px;background:var(--border);margin:16px 0}

.location-tag{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:10px;padding:12px 16px;width:100%;
  font-family:'Space Mono',monospace;font-size:11px;
  color:var(--muted);display:flex;align-items:center;gap:8px;
}
.location-tag::before{content:'📍';font-size:14px}

/* ═══════════ SECTION DIVIDER ═══════════ */
.sec-divider{
  display:flex;align-items:center;gap:16px;
  padding:0 48px;margin-bottom:48px;
}
.sec-divider-line{
  flex:1;height:1px;
  background:linear-gradient(90deg,rgba(123,97,255,0.4),transparent);
}
.sec-divider-line.rev{background:linear-gradient(90deg,transparent,rgba(123,97,255,0.4))}
.sec-num{font-family:'Space Mono',monospace;font-size:11px;color:var(--muted)}
.sec-title{font-family:'Space Mono',monospace;font-size:11px;color:var(--c-purple);letter-spacing:0.15em;text-transform:uppercase}

/* ═══════════ ABOUT ═══════════ */
#about{padding:100px 48px}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:48px;align-items:start}
.about-text h2{font-size:44px;font-weight:800;letter-spacing:-0.03em;line-height:1.1;margin-bottom:24px}
.about-text h2 span{color:var(--c-teal)}
.about-text p{font-size:16px;color:#8A95B8;line-height:1.8;margin-bottom:16px}
.about-code{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:14px;overflow:hidden;
}
.code-header{
  background:var(--bg3);padding:12px 20px;
  display:flex;align-items:center;gap:8px;
  border-bottom:1px solid var(--border);
}
.code-dot{width:10px;height:10px;border-radius:50%}
.code-dot.red{background:#FF5F57}.code-dot.yellow{background:#FFBD2E}.code-dot.green{background:#28C840}
.code-filename{font-family:'Space Mono',monospace;font-size:11px;color:var(--muted);margin-left:8px}
.code-body{padding:24px;font-family:'Space Mono',monospace;font-size:13px;line-height:2}
.code-key{color:#7B61FF}
.code-str{color:#00FFD1}
.code-num{color:#FF9500}
.code-comment{color:#3A4060}
.code-fn{color:#FF3B6B}
.code-obj{color:#00B4FF}
.code-indent{display:block;padding-left:20px}

/* ═══════════ ROLES ═══════════ */
#roles{padding:60px 48px 100px}
.roles-heading{font-size:48px;font-weight:800;letter-spacing:-0.03em;margin-bottom:16px}
.roles-heading span{color:var(--c-purple)}
.roles-sub{font-family:'Space Mono',monospace;font-size:12px;color:var(--muted);letter-spacing:0.06em;margin-bottom:56px}
.roles-grid{display:grid;grid-template-columns:1fr 1fr;gap:20px}

.role-card{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:16px;padding:32px;position:relative;
  overflow:hidden;transition:transform 0.3s,border-color 0.3s,box-shadow 0.3s;
  cursor:default;
}
.role-card:hover{transform:translateY(-6px);box-shadow:0 24px 60px rgba(0,0,0,0.4)}
.role-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:3px;border-radius:16px 16px 0 0;
}
.role-card.rc1::before{background:linear-gradient(90deg,#7B61FF,#00FFD1)}
.role-card.rc2::before{background:linear-gradient(90deg,#FF3B6B,#7B61FF)}
.role-card.rc3::before{background:linear-gradient(90deg,#00FFD1,#00B4FF)}
.role-card.rc4::before{background:linear-gradient(90deg,#FF9500,#FF3B6B)}
.role-card:hover.rc1{border-color:rgba(123,97,255,0.5)}
.role-card:hover.rc2{border-color:rgba(255,59,107,0.4)}
.role-card:hover.rc3{border-color:rgba(0,255,209,0.4)}
.role-card:hover.rc4{border-color:rgba(255,149,0,0.4)}

.rc-glow{
  position:absolute;width:200px;height:200px;border-radius:50%;
  filter:blur(60px);pointer-events:none;top:-60px;right:-60px;opacity:0;
  transition:opacity 0.4s;
}
.role-card:hover .rc-glow{opacity:1}
.rc1 .rc-glow{background:rgba(123,97,255,0.12)}
.rc2 .rc-glow{background:rgba(255,59,107,0.1)}
.rc3 .rc-glow{background:rgba(0,255,209,0.1)}
.rc4 .rc-glow{background:rgba(255,149,0,0.1)}

.rc-icon{
  font-size:36px;margin-bottom:20px;display:block;line-height:1;
}
.rc-number{
  font-family:'Space Mono',monospace;font-size:10px;
  color:var(--muted);letter-spacing:0.15em;margin-bottom:10px;
}
.rc-title{font-size:26px;font-weight:800;letter-spacing:-0.02em;margin-bottom:12px}
.rc-desc{font-size:14px;color:#7A85A8;line-height:1.7;margin-bottom:24px}

.rc-tags{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:28px}
.rc-tag{
  padding:5px 12px;border-radius:6px;
  font-family:'Space Mono',monospace;font-size:10px;letter-spacing:0.04em;
}
.rc1 .rc-tag{background:rgba(123,97,255,0.12);color:#A89CFF;border:1px solid rgba(123,97,255,0.25)}
.rc2 .rc-tag{background:rgba(255,59,107,0.1);color:#FF7A9A;border:1px solid rgba(255,59,107,0.25)}
.rc3 .rc-tag{background:rgba(0,255,209,0.08);color:#60F0D8;border:1px solid rgba(0,255,209,0.22)}
.rc4 .rc-tag{background:rgba(255,149,0,0.08);color:#FFBE6A;border:1px solid rgba(255,149,0,0.22)}

.rc-skills{
  border-top:1px solid var(--border);padding-top:24px;
}
.rc-skills-label{
  font-family:'Space Mono',monospace;font-size:10px;
  color:var(--muted);letter-spacing:0.1em;margin-bottom:16px;
  text-transform:uppercase;
}
.rc-skill-row{display:flex;justify-content:space-between;align-items:center;margin-bottom:10px}
.rc-skill-name{font-size:13px;color:#9AA3C0;font-family:'Space Mono',monospace}
.rc-skill-bar-wrap{width:120px;height:3px;background:var(--subtle);border-radius:2px;overflow:hidden}
.rc-skill-bar{height:100%;border-radius:2px;transition:width 1s ease}
.rc1 .rc-skill-bar{background:linear-gradient(90deg,#7B61FF,#A89CFF)}
.rc2 .rc-skill-bar{background:linear-gradient(90deg,#FF3B6B,#FF7A9A)}
.rc3 .rc-skill-bar{background:linear-gradient(90deg,#00FFD1,#60F0D8)}
.rc4 .rc-skill-bar{background:linear-gradient(90deg,#FF9500,#FFBE6A)}

/* ═══════════ PROJECTS ═══════════ */
#projects{padding:60px 48px 100px}
.projects-heading{font-size:48px;font-weight:800;letter-spacing:-0.03em;margin-bottom:16px}
.projects-heading span{color:var(--c-teal)}
.projects-sub{font-family:'Space Mono',monospace;font-size:12px;color:var(--muted);letter-spacing:0.06em;margin-bottom:56px}
.projects-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px}

.proj-card{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:14px;padding:24px;
  transition:transform 0.25s,border-color 0.25s;
  position:relative;overflow:hidden;
  cursor:pointer;text-decoration:none;color:inherit;display:block;
}
.proj-card:hover{transform:translateY(-4px);border-color:rgba(0,255,209,0.3)}
.proj-card::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(0,255,209,0.03),transparent);
  opacity:0;transition:opacity 0.3s;
}
.proj-card:hover::after{opacity:1}
.proj-lang{
  display:inline-flex;align-items:center;gap:6px;
  font-family:'Space Mono',monospace;font-size:10px;
  color:var(--muted);margin-bottom:12px;letter-spacing:0.05em;
}
.lang-dot{width:8px;height:8px;border-radius:50%}
.proj-title{font-size:16px;font-weight:700;letter-spacing:-0.01em;margin-bottom:8px;color:var(--text)}
.proj-desc{font-size:13px;color:#6B7394;line-height:1.6;margin-bottom:16px}
.proj-footer{display:flex;align-items:center;justify-content:space-between}
.proj-stars{font-family:'Space Mono',monospace;font-size:11px;color:var(--muted);display:flex;align-items:center;gap:5px}
.proj-arrow{color:var(--c-teal);font-size:16px;transition:transform 0.2s}
.proj-card:hover .proj-arrow{transform:translate(3px,-3px)}

/* ═══════════ STACK ═══════════ */
#stack{padding:60px 48px 100px}
.stack-heading{font-size:48px;font-weight:800;letter-spacing:-0.03em;margin-bottom:16px}
.stack-heading span{color:var(--c-red)}
.stack-sub{font-family:'Space Mono',monospace;font-size:12px;color:var(--muted);letter-spacing:0.06em;margin-bottom:56px}

.stack-section{margin-bottom:48px}
.stack-section-label{
  font-family:'Space Mono',monospace;font-size:10px;
  color:var(--muted);letter-spacing:0.14em;text-transform:uppercase;
  margin-bottom:16px;display:flex;align-items:center;gap:12px;
}
.stack-section-label::after{content:'';flex:1;height:1px;background:rgba(255,255,255,0.04)}
.stack-chips{display:flex;flex-wrap:wrap;gap:10px}

.chip{
  display:flex;align-items:center;gap:8px;
  padding:10px 16px;border-radius:8px;
  font-family:'Space Mono',monospace;font-size:12px;
  border:1px solid;letter-spacing:0.03em;
  transition:transform 0.15s,box-shadow 0.15s;cursor:default;
}
.chip:hover{transform:translateY(-2px)}
.chip.c-purple{background:rgba(123,97,255,0.1);border-color:rgba(123,97,255,0.3);color:#A89CFF}
.chip.c-teal{background:rgba(0,255,209,0.07);border-color:rgba(0,255,209,0.25);color:#60F0D8}
.chip.c-red{background:rgba(255,59,107,0.08);border-color:rgba(255,59,107,0.25);color:#FF7A9A}
.chip.c-amber{background:rgba(255,149,0,0.08);border-color:rgba(255,149,0,0.25);color:#FFBE6A}
.chip.c-blue{background:rgba(0,180,255,0.08);border-color:rgba(0,180,255,0.25);color:#60CEFF}
.chip.c-gray{background:rgba(255,255,255,0.04);border-color:rgba(255,255,255,0.1);color:#9AA3C0}

.chip-icon{font-size:15px}

/* ═══════════ STATS ═══════════ */
#stats{padding:60px 48px 100px;background:var(--bg4)}
.stats-heading{font-size:48px;font-weight:800;letter-spacing:-0.03em;margin-bottom:16px}
.stats-heading span{color:var(--c-amber)}
.stats-sub{font-family:'Space Mono',monospace;font-size:12px;color:var(--muted);letter-spacing:0.06em;margin-bottom:56px}
.stats-big-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:16px;margin-bottom:48px}
.big-stat{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:14px;padding:28px 20px;text-align:center;
  position:relative;overflow:hidden;
}
.big-stat::after{
  content:'';position:absolute;bottom:0;left:50%;
  transform:translateX(-50%);width:50%;height:2px;
  background:linear-gradient(90deg,transparent,var(--c-purple),transparent);
}
.big-stat-val{
  font-size:42px;font-weight:800;letter-spacing:-0.05em;
  background:linear-gradient(135deg,var(--c-teal),var(--c-purple));
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;
  margin-bottom:8px;line-height:1;
}
.big-stat-label{font-family:'Space Mono',monospace;font-size:10px;color:var(--muted);letter-spacing:0.1em;text-transform:uppercase}

.github-imgs{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.github-img-wrap{
  background:var(--bg2);border:1px solid var(--border);
  border-radius:14px;overflow:hidden;padding:4px;
}
.github-img-wrap img{width:100%;border-radius:10px;display:block}

/* ═══════════ CONTACT ═══════════ */
#contact{padding:100px 48px 80px;text-align:center;position:relative;overflow:hidden}
.contact-orb{
  position:absolute;width:500px;height:500px;
  background:rgba(123,97,255,0.08);border-radius:50%;
  filter:blur(100px);top:50%;left:50%;
  transform:translate(-50%,-50%);pointer-events:none;
}
.contact-heading{font-size:56px;font-weight:800;letter-spacing:-0.04em;margin-bottom:16px;line-height:1.1}
.contact-heading span{color:var(--c-purple)}
.contact-desc{font-size:17px;color:#7A85A8;max-width:520px;margin:0 auto 48px;line-height:1.75}
.contact-links{display:flex;justify-content:center;gap:16px;flex-wrap:wrap;margin-bottom:64px}

.contact-link{
  display:flex;align-items:center;gap:10px;
  padding:14px 28px;border-radius:10px;
  font-family:'Space Mono',monospace;font-size:12px;
  text-decoration:none;letter-spacing:0.05em;
  transition:transform 0.2s,box-shadow 0.2s;border:1px solid;
}
.contact-link:hover{transform:translateY(-3px)}
.contact-link.linkedin{background:rgba(0,119,181,0.1);border-color:rgba(0,119,181,0.35);color:#4BA3E3}
.contact-link.linkedin:hover{box-shadow:0 12px 40px rgba(0,119,181,0.2)}
.contact-link.facebook{background:rgba(24,119,242,0.1);border-color:rgba(24,119,242,0.3);color:#6BA8F0}
.contact-link.facebook:hover{box-shadow:0 12px 40px rgba(24,119,242,0.2)}
.contact-link.github{background:rgba(255,255,255,0.04);border-color:rgba(255,255,255,0.15);color:#C0C6D8}
.contact-link.github:hover{box-shadow:0 12px 40px rgba(255,255,255,0.05)}
.contact-link.email{background:rgba(255,59,107,0.08);border-color:rgba(255,59,107,0.3);color:#FF7A9A}
.contact-link.email:hover{box-shadow:0 12px 40px rgba(255,59,107,0.15)}
.contact-link.portfolio{background:rgba(0,255,209,0.06);border-color:rgba(0,255,209,0.25);color:var(--c-teal)}
.contact-link.portfolio:hover{box-shadow:0 12px 40px rgba(0,255,209,0.12)}

.contact-note{
  font-family:'Space Mono',monospace;font-size:12px;
  color:var(--muted);letter-spacing:0.06em;
}
.contact-note span{color:var(--c-teal)}

/* FOOTER */
footer{
  border-top:1px solid var(--border);
  padding:28px 48px;
  display:flex;align-items:center;justify-content:space-between;
  position:relative;z-index:1;
}
.footer-left{font-family:'Space Mono',monospace;font-size:11px;color:var(--muted);letter-spacing:0.06em}
.footer-right{font-family:'Space Mono',monospace;font-size:11px;color:var(--c-teal);letter-spacing:0.08em}
.footer-mid{
  display:flex;gap:24px;
}
.footer-mid a{font-family:'Space Mono',monospace;font-size:11px;color:var(--muted);text-decoration:none;letter-spacing:0.06em;transition:color 0.2s}
.footer-mid a:hover{color:var(--c-teal)}

/* SCROLL INDICATOR */
.scroll-indicator{
  position:fixed;top:0;left:0;height:2px;
  background:linear-gradient(90deg,var(--c-purple),var(--c-teal));
  z-index:200;transition:width 0.1s;
}

/* ANIMATIONS */
.fade-up{opacity:0;transform:translateY(30px);transition:opacity 0.7s ease,transform 0.7s ease}
.fade-up.visible{opacity:1;transform:translateY(0)}

@media(max-width:900px){
  nav{padding:14px 24px}
  .nav-links{display:none} /* FIX: Hide desktop links on small screens to prevent overflow */
  #hero{padding:100px 24px 60px;flex-direction:column}
  .hero-right{flex:none;width:100%}
  #about,.about-grid{grid-template-columns:1fr}
  .roles-grid,.projects-grid{grid-template-columns:1fr}
  .stats-big-grid{grid-template-columns:repeat(2,1fr)}
  .github-imgs{grid-template-columns:1fr}
  #roles,#projects,#stack,#stats,#contact,#about{padding-left:24px;padding-right:24px}
  footer{flex-direction:column;gap:16px;text-align:center}
  .hero-name{font-size:52px}
  .sec-divider{padding:0 24px}
}
</style>
</head>
<body>

<!-- CURSOR -->
<div id="cursor"></div>
<div id="cursor-ring"></div>

<!-- SCROLL PROGRESS -->
<div class="scroll-indicator" id="scroll-bar"></div>

<!-- GRID BG -->
<div class="grid-bg"></div>

<!-- NAV -->
<nav>
  <div class="nav-logo">munawar.dev</div>
  <div class="nav-links">
    <a href="#about">About</a>
    <a href="#roles">Roles</a>
    <a href="#projects">Projects</a>
    <a href="#stack">Stack</a>
    <a href="#contact">Contact</a>
  </div>
  <a href="#contact" class="nav-cta">Hire Me ↗</a>
</nav>

<!-- ═══════════ HERO ═══════════ -->
<section id="hero">
  <div class="hero-orb orb-a"></div>
  <div class="hero-orb orb-b"></div>
  <div class="hero-orb orb-c"></div>

  <div class="hero-left">
    <div class="status-badge">
      <div class="pulse"></div>
      Available for new projects
    </div>
    <h1 class="hero-name">
      <span class="name-white">Munawar</span><br>
      <span class="name-grad">Abbas</span>
    </h1>
    <div class="hero-role" id="tw-target"><span id="tw-text"></span><span class="tw-cursor"></span></div>
    <p class="hero-desc">
      Engineering <strong>intelligent, scalable systems</strong> at the intersection of full-stack development, AI automation, and growth-driven SEO. Based in Pakistan — building for the world.
    </p>
    <div class="hero-btns">
      <a href="#projects" class="btn-primary">View Projects</a>
      <a href="#contact" class="btn-outline">Let's Connect →</a>
    </div>
  </div>

  <div class="hero-right">
    <div class="hero-stats-card">
      <div class="hero-stat">
        <div class="hero-stat-val teal">4+</div>
        <div class="hero-stat-label">Years of Experience</div>
      </div>
      <div class="hero-stat-divider"></div>
      <div class="hero-stat">
        <div class="hero-stat-val purple">69</div>
        <div class="hero-stat-label">GitHub Repositories</div>
      </div>
      <div class="hero-stat-divider"></div>
      <div class="hero-stat">
        <div class="hero-stat-val amber">50+</div>
        <div class="hero-stat-label">Projects Delivered</div>
      </div>
    </div>
    <div class="location-tag">Pakistan · UTC+05:00</div>
  </div>
</section>

<!-- DIVIDER -->
<div class="sec-divider fade-up">
  <span class="sec-num">01</span>
  <div class="sec-divider-line"></div>
  <span class="sec-title">About</span>
  <div class="sec-divider-line rev"></div>
</div>

<!-- ═══════════ ABOUT ═══════════ -->
<section id="about">
  <div class="about-grid">
    <div class="about-text fade-up">
      <h2>Crafting digital<br><span>experiences</span><br>that matter.</h2>
      <p>I'm a passionate Full-Stack Developer and AI Engineer from Pakistan, dedicated to building software that is not only functional but genuinely impactful. With deep expertise across the entire web stack, AI integrations, and automation pipelines, I turn complex ideas into elegant solutions.</p>
      <p>My work spans from pixel-perfect React interfaces to intelligent chatbot systems, from high-performance APIs to technical SEO strategies that drive measurable growth for businesses worldwide.</p>
      <p>Currently focused on building next-generation AI-powered applications with LangChain, OpenAI, and modern automation tooling.</p>
    </div>
    <div class="about-code fade-up">
      <div class="code-header">
        <div class="code-dot red"></div>
        <div class="code-dot yellow"></div>
        <div class="code-dot green"></div>
        <span class="code-filename">munawar.config.ts</span>
      </div>
      <div class="code-body">
        <span class="code-key">const</span> <span class="code-obj">developer</span> = {<br>
        <span class="code-indent"><span class="code-key">name</span>: <span class="code-str">"Munawar Abbas"</span>,</span>
        <span class="code-indent"><span class="code-key">handle</span>: <span class="code-str">"@MunawarAbbas313"</span>,</span>
        <span class="code-indent"><span class="code-key">location</span>: <span class="code-str">"Pakistan 🇵🇰"</span>,</span>
        <span class="code-indent"><span class="code-key">roles</span>: [</span>
        <span class="code-indent" style="padding-left:40px"><span class="code-str">"Full-Stack Developer"</span>,</span>
        <span class="code-indent" style="padding-left:40px"><span class="code-str">"Chatbot Architect"</span>,</span>
        <span class="code-indent" style="padding-left:40px"><span class="code-str">"SEO Expert"</span>,</span>
        <span class="code-indent" style="padding-left:40px"><span class="code-str">"Automation Engineer"</span>,</span>
        <span class="code-indent">],</span>
        <span class="code-indent"><span class="code-key">status</span>: <span class="code-str">"available"</span> <span class="code-comment">// hire me!</span></span>
        <span class="code-indent"><span class="code-fn">build</span>: () => <span class="code-str">"something legendary"</span></span>
        }
      </div>
    </div>
  </div>
</section>

<!-- DIVIDER -->
<div class="sec-divider fade-up">
  <span class="sec-num">02</span>
  <div class="sec-divider-line"></div>
  <span class="sec-title">What I Do</span>
  <div class="sec-divider-line rev"></div>
</div>

<!-- ═══════════ ROLES ═══════════ -->
<section id="roles">
  <h2 class="roles-heading fade-up">My <span>Expertise</span></h2>
  <p class="roles-sub fade-up">// four domains — one unified vision</p>
  <div class="roles-grid">

    <div class="role-card rc1 fade-up">
      <div class="rc-glow"></div>
      <span class="rc-icon">⬡</span>
      <div class="rc-number">01 / FULL-STACK DEVELOPMENT</div>
      <h3 class="rc-title">Full-Stack Developer</h3>
      <p class="rc-desc">End-to-end web applications — from blazing-fast React frontends to robust, scalable backend APIs. I architect complete systems that perform, scale, and delight users.</p>
      <div class="rc-tags">
        <span class="rc-tag">React</span>
        <span class="rc-tag">Next.js</span>
        <span class="rc-tag">Node.js</span>
        <span class="rc-tag">FastAPI</span>
        <span class="rc-tag">NestJS</span>
        <span class="rc-tag">TypeScript</span>
        <span class="rc-tag">Tailwind</span>
        <span class="rc-tag">Firebase</span>
      </div>
      <div class="rc-skills">
        <div class="rc-skills-label">Proficiency</div>
        <div class="rc-skill-row"><span class="rc-skill-name">React / Next.js</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="95" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">Node.js / APIs</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="90" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">TypeScript</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="88" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">Python / FastAPI</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="82" style="width:0%"></div></div></div>
      </div>
    </div>

    <div class="role-card rc2 fade-up">
      <div class="rc-glow"></div>
      <span class="rc-icon">◈</span>
      <div class="rc-number">02 / AI & CHATBOT DEVELOPMENT</div>
      <h3 class="rc-title">Chatbot Architect</h3>
      <p class="rc-desc">Building intelligent conversational AI — from simple FAQ bots to advanced agentic systems with memory, RAG pipelines, and multi-step reasoning capabilities.</p>
      <div class="rc-tags">
        <span class="rc-tag">OpenAI API</span>
        <span class="rc-tag">LangChain</span>
        <span class="rc-tag">RAG</span>
        <span class="rc-tag">Agents</span>
        <span class="rc-tag">Telegram Bot</span>
        <span class="rc-tag">WhatsApp Bot</span>
        <span class="rc-tag">Vector DBs</span>
        <span class="rc-tag">Fine-tuning</span>
      </div>
      <div class="rc-skills">
        <div class="rc-skills-label">Proficiency</div>
        <div class="rc-skill-row"><span class="rc-skill-name">OpenAI / GPT</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="93" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">LangChain</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="87" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">RAG Pipelines</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="85" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">Bot APIs</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="91" style="width:0%"></div></div></div>
      </div>
    </div>

    <div class="role-card rc3 fade-up">
      <div class="rc-glow"></div>
      <span class="rc-icon">◎</span>
      <div class="rc-number">03 / SEO & DIGITAL MARKETING</div>
      <h3 class="rc-title">SEO Expert</h3>
      <p class="rc-desc">Data-driven SEO strategies that move the needle — technical audits, on-page optimization, schema markup, Core Web Vitals, and content strategies that rank and convert.</p>
      <div class="rc-tags">
        <span class="rc-tag">Technical SEO</span>
        <span class="rc-tag">On-Page SEO</span>
        <span class="rc-tag">Schema Markup</span>
        <span class="rc-tag">Core Web Vitals</span>
        <span class="rc-tag">Google Analytics</span>
        <span class="rc-tag">Search Console</span>
        <span class="rc-tag">Keyword Research</span>
        <span class="rc-tag">Link Building</span>
      </div>
      <div class="rc-skills">
        <div class="rc-skills-label">Proficiency</div>
        <div class="rc-skill-row"><span class="rc-skill-name">Technical SEO</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="90" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">Analytics</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="88" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">Content Strategy</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="84" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">Link Building</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="80" style="width:0%"></div></div></div>
      </div>
    </div>

    <div class="role-card rc4 fade-up">
      <div class="rc-glow"></div>
      <span class="rc-icon">⟁</span>
      <div class="rc-number">04 / AUTOMATION ENGINEERING</div>
      <h3 class="rc-title">Automation Engineer</h3>
      <p class="rc-desc">Connecting tools, eliminating repetitive work, and building autonomous workflows — from simple Zapier flows to complex multi-step automation pipelines that run 24/7.</p>
      <div class="rc-tags">
        <span class="rc-tag">n8n</span>
        <span class="rc-tag">Make</span>
        <span class="rc-tag">Zapier</span>
        <span class="rc-tag">Python Scripts</span>
        <span class="rc-tag">REST APIs</span>
        <span class="rc-tag">Webhooks</span>
        <span class="rc-tag">Cron Jobs</span>
        <span class="rc-tag">CI/CD</span>
      </div>
      <div class="rc-skills">
        <div class="rc-skills-label">Proficiency</div>
        <div class="rc-skill-row"><span class="rc-skill-name">n8n / Make</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="92" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">Python Scripting</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="88" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">API Integration</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="93" style="width:0%"></div></div></div>
        <div class="rc-skill-row"><span class="rc-skill-name">Workflow Design</span><div class="rc-skill-bar-wrap"><div class="rc-skill-bar" data-w="89" style="width:0%"></div></div></div>
      </div>
    </div>

  </div>
</section>

<!-- DIVIDER -->
<div class="sec-divider fade-up">
  <span class="sec-num">03</span>
  <div class="sec-divider-line"></div>
  <span class="sec-title">Projects</span>
  <div class="sec-divider-line rev"></div>
</div>

<!-- ═══════════ PROJECTS ═══════════ -->
<section id="projects">
  <h2 class="projects-heading fade-up">Featured <span>Repos</span></h2>
  <p class="projects-sub fade-up">// selected work from github.com/MunawarAbbas313</p>
  <div class="projects-grid">

    <a href="https://github.com/MunawarAbbas313/Hiresense-Ai" target="_blank" class="proj-card fade-up">
      <div class="proj-lang"><span class="lang-dot" style="background:#F7DF1E"></span>JavaScript</div>
      <div class="proj-title">Hiresense AI</div>
      <div class="proj-desc">AI-powered hiring platform — intelligent resume screening, candidate matching, and automated outreach workflows.</div>
      <div class="proj-footer"><span class="proj-stars">★ 1</span><span class="proj-arrow">↗</span></div>
    </a>

    <a href="https://github.com/MunawarAbbas313/Smart-Inventory-Mangemnt-system" target="_blank" class="proj-card fade-up">
      <div class="proj-lang"><span class="lang-dot" style="background:#F7DF1E"></span>JavaScript</div>
      <div class="proj-title">Smart Inventory System</div>
      <div class="proj-desc">Real-time inventory management with automated restocking alerts, analytics dashboard, and Firebase sync.</div>
      <div class="proj-footer"><span class="proj-stars">★ 1</span><span class="proj-arrow">↗</span></div>
    </a>

    <a href="https://github.com/MunawarAbbas313/JavaScript-projects-for-begineers" target="_blank" class="proj-card fade-up">
      <div class="proj-lang"><span class="lang-dot" style="background:#F7DF1E"></span>JavaScript</div>
      <div class="proj-title">JS Projects for Beginners</div>
      <div class="proj-desc">Curated collection of hands-on JavaScript projects — helping new developers build real skills through practice.</div>
      <div class="proj-footer"><span class="proj-stars">★ 1</span><span class="proj-arrow">↗</span></div>
    </a>

    <a href="https://github.com/MunawarAbbas313/JAVASCRIPT-ANIMATTED-WEBSITE-PROJECTS" target="_blank" class="proj-card fade-up">
      <div class="proj-lang"><span class="lang-dot" style="background:#E34C26"></span>HTML</div>
      <div class="proj-title">Animated Web Projects</div>
      <div class="proj-desc">A showcase of visually stunning animated website projects with advanced CSS and JavaScript interactions.</div>
      <div class="proj-footer"><span class="proj-stars">★ 1</span><span class="proj-arrow">↗</span></div>
    </a>

    <a href="https://github.com/MunawarAbbas313/DSA-CPP" target="_blank" class="proj-card fade-up">
      <div class="proj-lang"><span class="lang-dot" style="background:#f34b7d"></span>C++</div>
      <div class="proj-title">DSA in C++</div>
      <div class="proj-desc">Complete DSA material with clear code and explanations — from arrays to advanced trees, graphs and dynamic programming.</div>
      <div class="proj-footer"><span class="proj-stars">★ 1</span><span class="proj-arrow">↗</span></div>
    </a>

    <a href="https://munawarabbas313.github.io/munawarportfoliooffical/" target="_blank" class="proj-card fade-up">
      <div class="proj-lang"><span class="lang-dot" style="background:#00FFD1"></span>Portfolio</div>
      <div class="proj-title">Personal Portfolio</div>
      <div class="proj-desc">Official portfolio website — showcasing projects, skills, and professional background with a sleek modern design.</div>
      <div class="proj-footer"><span class="proj-stars">Live ↗</span><span class="proj-arrow">↗</span></div>
    </a>

  </div>
</section>

<!-- DIVIDER -->
<div class="sec-divider fade-up">
  <span class="sec-num">04</span>
  <div class="sec-divider-line"></div>
  <span class="sec-title">Tech Stack</span>
  <div class="sec-divider-line rev"></div>
</div>

<!-- ═══════════ STACK ═══════════ -->
<section id="stack">
  <h2 class="stack-heading fade-up">The <span>Arsenal</span></h2>
  <p class="stack-sub fade-up">// tools i use to build, ship, and scale</p>

  <div class="stack-section fade-up">
    <div class="stack-section-label">Frontend & UI</div>
    <div class="stack-chips">
      <div class="chip c-purple"><span class="chip-icon">⚛</span>React</div>
      <div class="chip c-purple"><span class="chip-icon">▲</span>Next.js</div>
      <div class="chip c-purple"><span class="chip-icon">TS</span>TypeScript</div>
      <div class="chip c-purple"><span class="chip-icon">JS</span>JavaScript</div>
      <div class="chip c-purple"><span class="chip-icon">🎨</span>Tailwind CSS</div>
      <div class="chip c-gray"><span class="chip-icon">📐</span>Figma</div>
      <div class="chip c-gray"><span class="chip-icon">🅱</span>Bootstrap</div>
      <div class="chip c-gray"><span class="chip-icon">📦</span>Redux Toolkit</div>
    </div>
  </div>

  <div class="stack-section fade-up">
    <div class="stack-section-label">Backend & APIs</div>
    <div class="stack-chips">
      <div class="chip c-teal"><span class="chip-icon">🟢</span>Node.js</div>
      <div class="chip c-teal"><span class="chip-icon">⚡</span>FastAPI</div>
      <div class="chip c-teal"><span class="chip-icon">🐍</span>Python</div>
      <div class="chip c-teal"><span class="chip-icon">🐦</span>NestJS</div>
      <div class="chip c-teal"><span class="chip-icon">🌶</span>Flask</div>
      <div class="chip c-teal"><span class="chip-icon">🚂</span>Express.js</div>
      <div class="chip c-teal"><span class="chip-icon">🔌</span>REST APIs</div>
      <div class="chip c-teal"><span class="chip-icon">🔗</span>WebSockets</div>
    </div>
  </div>

  <div class="stack-section fade-up">
    <div class="stack-section-label">AI & Chatbots</div>
    <div class="stack-chips">
      <div class="chip c-red"><span class="chip-icon">🤖</span>OpenAI API</div>
      <div class="chip c-red"><span class="chip-icon">⛓</span>LangChain</div>
      <div class="chip c-red"><span class="chip-icon">🧠</span>RAG Pipelines</div>
      <div class="chip c-red"><span class="chip-icon">✈</span>Telegram Bot</div>
      <div class="chip c-red"><span class="chip-icon">💬</span>WhatsApp Bot</div>
      <div class="chip c-red"><span class="chip-icon">📊</span>ML / scikit-learn</div>
      <div class="chip c-red"><span class="chip-icon">🔍</span>Vector DBs</div>
    </div>
  </div>

  <div class="stack-section fade-up">
    <div class="stack-section-label">Automation</div>
    <div class="stack-chips">
      <div class="chip c-amber"><span class="chip-icon">🔄</span>n8n</div>
      <div class="chip c-amber"><span class="chip-icon">⚙</span>Make</div>
      <div class="chip c-amber"><span class="chip-icon">⚡</span>Zapier</div>
      <div class="chip c-amber"><span class="chip-icon">🔔</span>Webhooks</div>
      <div class="chip c-amber"><span class="chip-icon">🐍</span>Python Scripts</div>
      <div class="chip c-amber"><span class="chip-icon">⏱</span>Cron Jobs</div>
    </div>
  </div>

  <div class="stack-section fade-up">
    <div class="stack-section-label">Database & Cloud</div>
    <div class="stack-chips">
      <div class="chip c-blue"><span class="chip-icon">🔥</span>Firebase</div>
      <div class="chip c-blue"><span class="chip-icon">🟩</span>Supabase</div>
      <div class="chip c-blue"><span class="chip-icon">🐘</span>PostgreSQL</div>
      <div class="chip c-blue"><span class="chip-icon">🍃</span>MongoDB</div>
      <div class="chip c-blue"><span class="chip-icon">☁</span>Vercel</div>
      <div class="chip c-blue"><span class="chip-icon">🌊</span>Netlify</div>
    </div>
  </div>
</section>

<!-- DIVIDER -->
<div class="sec-divider fade-up">
  <span class="sec-num">05</span>
  <div class="sec-divider-line"></div>
  <span class="sec-title">GitHub Stats</span>
  <div class="sec-divider-line rev"></div>
</div>

<!-- ═══════════ STATS ═══════════ -->
<section id="stats">
  <h2 class="stats-heading fade-up">By the <span>Numbers</span></h2>
  <p class="stats-sub fade-up">// activity, reach, and contributions</p>

  <div class="stats-big-grid fade-up">
    <div class="big-stat"><div class="big-stat-val">69</div><div class="big-stat-label">Repositories</div></div>
    <div class="big-stat"><div class="big-stat-val">4+</div><div class="big-stat-label">Years Coding</div></div>
    <div class="big-stat"><div class="big-stat-val">50+</div><div class="big-stat-label">Projects Done</div></div>
    <div class="big-stat"><div class="big-stat-val">∞</div><div class="big-stat-label">Ideas Left</div></div>
  </div>

  <div class="github-imgs fade-up">
    <div class="github-img-wrap">
      <img src="https://github-readme-stats.vercel.app/api?username=MunawarAbbas313&show_icons=true&theme=merko&hide_border=true&bg_color=0C1020&title_color=7B61FF&icon_color=00FFD1&text_color=9AA3C0&count_private=true" alt="GitHub Stats" loading="lazy"/>
    </div>
    <div class="github-img-wrap">
      <img src="https://github-readme-streak-stats.herokuapp.com/?user=MunawarAbbas313&theme=merko&hide_border=true&background=0C1020&stroke=7B61FF&ring=00FFD1&fire=FF3B6B&currStreakLabel=7B61FF&sideLabels=9AA3C0&dates=9AA3C0" alt="Streak Stats" loading="lazy"/>
    </div>
    <div class="github-img-wrap" style="grid-column:1/-1">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=MunawarAbbas313&bg_color=0C1020&color=7B61FF&line=00FFD1&point=FF3B6B&area=true&hide_border=true" alt="Activity Graph" loading="lazy"/>
    </div>
  </div>
</section>

<!-- DIVIDER -->
<div class="sec-divider fade-up">
  <span class="sec-num">06</span>
  <div class="sec-divider-line"></div>
  <span class="sec-title">Contact</span>
  <div class="sec-divider-line rev"></div>
</div>

<!-- ═══════════ CONTACT ═══════════ -->
<section id="contact">
  <div class="contact-orb"></div>
  <h2 class="contact-heading fade-up">Let's Build<br><span>Something</span><br>Legendary.</h2>
  <p class="contact-desc fade-up">Open to freelance projects, full-time roles, and interesting collaborations. If you have an idea — let's talk.</p>

  <div class="contact-links fade-up">
    <a href="https://www.linkedin.com/in/munawar-abbas-5a2b8a273" target="_blank" class="contact-link linkedin">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
      LinkedIn
    </a>
    <a href="https://github.com/MunawarAbbas313" target="_blank" class="contact-link github">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0C5.374 0 0 5.373 0 12c0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23A11.509 11.509 0 0112 5.803c1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576C20.566 21.797 24 17.3 24 12c0-6.627-5.373-12-12-12z"/></svg>
      GitHub
    </a>
    <a href="https://munawarabbas313.github.io/munawarportfoliooffical/" target="_blank" class="contact-link portfolio">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"/><path d="M2 12h20M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"/></svg>
      Portfolio
    </a>
    <a href="https://www.facebook.com/munawar.abbasmir.7" target="_blank" class="contact-link facebook">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
      Facebook
    </a>
    <a href="mailto:your_email@gmail.com" class="contact-link email">
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      Email
    </a>
  </div>

  <p class="contact-note fade-up">Based in Pakistan · Available globally · <span>Let's build something legendary →</span></p>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-left">© 2024 Munawar Abbas · MunawarAbbas313</div>
  <div class="footer-mid">
    <a href="https://github.com/MunawarAbbas313" target="_blank">GitHub</a>
    <a href="https://www.linkedin.com/in/munawar-abbas-5a2b8a273" target="_blank">LinkedIn</a>
    <a href="https://munawarabbas313.github.io/munawarportfoliooffical/" target="_blank">Portfolio</a>
  </div>
  <div class="footer-right">made with ◈ passion</div>
</footer>

<script>
// CURSOR
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursor-ring');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{
  mx=e.clientX;my=e.clientY;
  cursor.style.left=(mx-5)+'px';cursor.style.top=(my-5)+'px';
});
function animRing(){
  rx+=(mx-rx)*0.12;ry+=(my-ry)*0.12;
  ring.style.left=(rx-18)+'px';ring.style.top=(ry-18)+'px';
  requestAnimationFrame(animRing);
}animRing();
document.querySelectorAll('a,button,.role-card,.proj-card,.chip').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cursor.style.transform='scale(2)';ring.style.transform='scale(1.5)';ring.style.borderColor='rgba(0,255,209,0.7)'});
  el.addEventListener('mouseleave',()=>{cursor.style.transform='scale(1)';ring.style.transform='scale(1)';ring.style.borderColor='rgba(0,255,209,0.4)'});
});

// SCROLL BAR
const bar=document.getElementById('scroll-bar');
window.addEventListener('scroll',()=>{
  const pct=window.scrollY/(document.body.scrollHeight-window.innerHeight)*100;
  bar.style.width=pct+'%';
});

// TYPEWRITER
const phrases=['Full-Stack Developer','AI & Chatbot Architect','SEO Strategist','Automation Engineer'];
let pi=0,ci=0,del=false;
const twEl=document.getElementById('tw-text');
function tick(){
  const p=phrases[pi];
  if(!del){ci++;twEl.textContent=p.slice(0,ci);if(ci===p.length){del=true;setTimeout(tick,1800);return;}setTimeout(tick,70);}
  else{ci--;twEl.textContent=p.slice(0,ci);if(ci===0){del=false;pi=(pi+1)%phrases.length;setTimeout(tick,400);return;}setTimeout(tick,35);}
}tick();

// FADE UP ON SCROLL - FIXED STAGGER
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('visible');obs.unobserve(e.target);}});
},{threshold:0.1,rootMargin:'0px 0px -40px 0px'});
document.querySelectorAll('.fade-up').forEach((el)=>{
  // Removing the global index transition delay prevents scroll glitching
  obs.observe(el);
});

// SKILL BARS ANIMATE
const barObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.querySelectorAll('.rc-skill-bar').forEach(b=>{b.style.width=b.dataset.w+'%';});
      barObs.unobserve(e.target);
    }
  });
},{threshold:0.3});
document.querySelectorAll('.role-card').forEach(c=>barObs.observe(c));

// SMOOTH NAV
document.querySelectorAll('a[href^="#"]').forEach(a=>{
  a.addEventListener('click',e=>{
    e.preventDefault();
    document.querySelector(a.getAttribute('href'))?.scrollIntoView({behavior:'smooth'});
  });
});
</script>
</body>
</html>
