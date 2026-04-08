# Golden-k

<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Golden K Resort · Kribi · 5 Etoiles</title>
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400&family=Jost:wght@300;400;500;600&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#080806;--dark:#0E0E0A;--dark2:#141410;--dark3:#1C1C14;
  --gold:#C8A84B;--gold2:#DDB96A;--gold3:#EDD9A0;--cream:#F3EDD8;
  --dim:#A89880;   /* WAS #6E6858 — maintenant lisible sur fond noir */
  --fd:'Cormorant Garamond',serif;--fs:'Jost',sans-serif;
  --pad:clamp(1.2rem,5vw,5rem);
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--cream);font-family:var(--fd);overflow-x:hidden}
::-webkit-scrollbar{width:2px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--gold)}

/* LOADER */
#loader{position:fixed;inset:0;background:var(--bg);z-index:9999;display:flex;flex-direction:column;align-items:center;justify-content:center;transition:opacity 1s ease .5s}
#loader.out{opacity:0;pointer-events:none}
.ld-logo{font-family:var(--fd);font-size:clamp(2rem,8vw,4rem);font-weight:300;letter-spacing:.5em;color:var(--gold);animation:pulse 2s ease-in-out infinite}
.ld-sub{font-family:var(--fs);font-size:.52rem;letter-spacing:.4em;text-transform:uppercase;color:var(--dim);margin-top:.6rem}
.ld-bar{width:0;height:1px;background:var(--gold);margin-top:2rem;animation:grow 2.5s ease forwards}
@keyframes pulse{0%,100%{opacity:.2}50%{opacity:1}}
@keyframes grow{to{width:min(160px,50vw)}}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:800;display:flex;align-items:center;justify-content:space-between;padding:1.4rem var(--pad);transition:all .4s ease}
nav.scrolled{background:rgba(8,8,6,.97);backdrop-filter:blur(18px);border-bottom:1px solid rgba(200,168,75,.2)}
.nlogo{font-family:var(--fd);font-size:clamp(1.1rem,3.5vw,1.5rem);font-weight:600;letter-spacing:.28em;color:var(--gold);text-decoration:none;text-transform:uppercase}
.nlogo em{font-style:normal;font-weight:300;color:var(--cream)}
.nlinks{display:flex;gap:clamp(1rem,2vw,2.2rem);list-style:none}
.nlinks a{font-family:var(--fs);font-size:clamp(.72rem,.8vw,.85rem);font-weight:500;letter-spacing:.2em;text-transform:uppercase;color:var(--cream);text-decoration:none;position:relative;transition:color .3s;white-space:nowrap}
.nlinks a::after{content:'';position:absolute;bottom:-3px;left:0;width:0;height:1px;background:var(--gold);transition:width .3s}
.nlinks a:hover{color:var(--gold)}.nlinks a:hover::after{width:100%}
.nbtn{font-family:var(--fs);font-size:clamp(.7rem,.75vw,.8rem);font-weight:600;letter-spacing:.2em;text-transform:uppercase;color:var(--bg);background:var(--gold);padding:.6rem 1.4rem;text-decoration:none;transition:background .3s;white-space:nowrap}
.nbtn:hover{background:var(--gold2)}
.hamburger{display:none;flex-direction:column;gap:5px;background:none;border:none;cursor:pointer;padding:.3rem;z-index:810}
.hbar{width:24px;height:1.5px;background:var(--gold);transition:all .35s ease;display:block}
.hamburger.open .hbar:nth-child(1){transform:translateY(6.5px) rotate(45deg)}
.hamburger.open .hbar:nth-child(2){opacity:0}
.hamburger.open .hbar:nth-child(3){transform:translateY(-6.5px) rotate(-45deg)}
.mobile-menu{position:fixed;top:0;left:0;right:0;bottom:0;background:rgba(8,8,6,.98);z-index:805;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:2.2rem;transform:translateX(100%);transition:transform .45s cubic-bezier(.25,.46,.45,.94)}
.mobile-menu.open{transform:translateX(0)}
.mobile-menu a{font-family:var(--fd);font-size:clamp(1.6rem,5vw,2.2rem);font-weight:300;letter-spacing:.15em;color:var(--cream);text-decoration:none;transition:color .3s}
.mobile-menu a:hover{color:var(--gold)}
.mobile-menu .m-res{color:var(--gold);border:1px solid var(--gold);padding:.7rem 2.2rem;font-family:var(--fs);font-size:.65rem;font-weight:600;letter-spacing:.2em}
.mobile-menu .m-stars{font-family:var(--fs);font-size:.6rem;letter-spacing:.4em;color:var(--gold);margin-top:.5rem}

/* HERO */
#hero{position:relative;height:100svh;min-height:600px;overflow:hidden;display:flex;align-items:flex-end;padding:0 var(--pad) clamp(4rem,10vh,9rem)}
#hbg{position:absolute;inset:0;background-size:cover;background-position:center;transform:scale(1.1);will-change:transform;animation:hzoom 22s ease-in-out infinite alternate}
@keyframes hzoom{0%{transform:scale(1.1)}100%{transform:scale(1.2) translateY(-2%)}}
.hgrad{position:absolute;inset:0;background:linear-gradient(to top,rgba(8,8,6,.96) 0%,rgba(8,8,6,.4) 55%,rgba(8,8,6,.12) 100%)}
.hcnt{position:relative;z-index:2;max-width:860px;width:100%}
.hlbl{font-family:var(--fs);font-size:clamp(.65rem,.8vw,.75rem);letter-spacing:.35em;text-transform:uppercase;color:var(--gold);display:flex;align-items:center;gap:.8rem;margin-bottom:clamp(1rem,2vh,2rem);opacity:0;animation:fu .9s ease .6s forwards}
.hlbl::before{content:'';width:clamp(16px,3vw,32px);height:1px;background:var(--gold)}
.htitle{font-family:var(--fd);font-size:clamp(2.8rem,8vw,8rem);font-weight:300;line-height:1.05;color:#FFFFFF;opacity:0;animation:fu .9s ease .9s forwards}
.htitle em{font-style:italic;color:var(--gold2)}
.hsub{font-family:var(--fs);font-size:clamp(.82rem,.95vw,.9rem);letter-spacing:.05em;color:#E8DEC8;line-height:1.9;max-width:500px;margin-top:clamp(1rem,2vh,2rem);opacity:0;animation:fu .9s ease 1.2s forwards}
.hbtns{display:flex;flex-wrap:wrap;align-items:center;gap:clamp(1rem,3vw,2.5rem);margin-top:clamp(1.5rem,3vh,3rem);opacity:0;animation:fu .9s ease 1.5s forwards}
.btn-prim{font-family:var(--fs);font-size:clamp(.56rem,.65vw,.62rem);font-weight:600;letter-spacing:.24em;text-transform:uppercase;color:var(--bg);background:var(--gold);padding:clamp(.75rem,.9vw,1rem) clamp(1.5rem,2.5vw,2.6rem);text-decoration:none;position:relative;overflow:hidden;transition:.3s}
.btn-prim::before{content:'';position:absolute;inset:0;background:var(--gold2);transform:translateX(-101%);transition:transform .35s}
.btn-prim:hover::before{transform:translateX(0)}
.btn-prim span{position:relative;z-index:1}
.btn-ghost{font-family:var(--fs);font-size:clamp(.56rem,.65vw,.62rem);letter-spacing:.18em;text-transform:uppercase;color:var(--cream);text-decoration:none;display:flex;align-items:center;gap:.5rem;transition:color .3s}
.btn-ghost .arr{display:inline-block;transition:transform .3s}
.btn-ghost:hover{color:var(--gold)}.btn-ghost:hover .arr{transform:translateX(5px)}
.hscroll{position:absolute;right:var(--pad);bottom:clamp(1.5rem,3vh,3rem);display:flex;flex-direction:column;align-items:center;gap:.6rem;opacity:0;animation:fi .8s ease 2.2s forwards}
.hscroll span{font-family:var(--fs);font-size:.48rem;letter-spacing:.3em;text-transform:uppercase;color:var(--dim);writing-mode:vertical-rl}
.sbar{width:1px;height:44px;overflow:hidden;background:rgba(200,168,75,.18)}
.sbar::after{content:'';display:block;width:100%;height:100%;background:var(--gold);animation:sb 2.2s ease-in-out infinite;transform:translateY(-100%)}
@keyframes fu{from{opacity:0;transform:translateY(26px)}to{opacity:1;transform:translateY(0)}}
@keyframes fi{to{opacity:1}}
@keyframes sb{0%{transform:translateY(-100%)}50%{transform:translateY(0)}100%{transform:translateY(100%)}}

/* MARQUEE */
.mband{overflow:hidden;padding:.8rem 0}
.mband-g{background:var(--gold)}
.mband-d{background:var(--dark3);border-top:1px solid rgba(200,168,75,.1);border-bottom:1px solid rgba(200,168,75,.1)}
.mtrack{display:flex;white-space:nowrap;animation:mq 28s linear infinite}
.mtrack.slow{animation-duration:42s}.mtrack.rev{animation-direction:reverse}
.mitem{font-family:var(--fs);font-size:clamp(.65rem,.75vw,.72rem);font-weight:600;letter-spacing:.3em;text-transform:uppercase;padding:0 1.8rem;display:inline-flex;align-items:center;gap:1.8rem}
.mitem::after{content:'*';font-size:.5rem}
.mband-g .mitem{color:var(--bg)}.mband-d .mitem{color:var(--gold)}
@keyframes mq{from{transform:translateX(0)}to{transform:translateX(-50%)}}

/* COMMON */
.sec{padding:clamp(4rem,8vw,8rem) var(--pad)}
.slbl{font-family:var(--fs);font-size:clamp(.62rem,.7vw,.68rem);letter-spacing:.38em;text-transform:uppercase;color:var(--gold);display:flex;align-items:center;gap:.8rem;margin-bottom:1.4rem}
.slbl::before{content:'';width:22px;height:1px;background:var(--gold)}
.stitle{font-family:var(--fd);font-size:clamp(2.2rem,5vw,4rem);font-weight:400;line-height:1.14;color:#FFFFFF}
.stitle em{font-style:italic;color:var(--gold2)}

/* ABOUT */
#about{background:var(--dark)}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:clamp(2rem,6vw,8rem);align-items:center}
.aimg-wrap{position:relative}
.aimg-wrap img{width:100%;height:clamp(300px,50vw,580px);object-fit:cover;display:block}
.aimg-deco{position:absolute;bottom:-18px;right:-18px;width:clamp(80px,12vw,160px);height:clamp(80px,12vw,160px);border:1px solid var(--gold);pointer-events:none}
.abadge{position:absolute;top:clamp(1rem,2vw,2.5rem);left:clamp(-1.5rem,-3vw,-2rem);background:var(--gold);color:var(--bg);padding:clamp(.8rem,1.5vw,1.5rem) clamp(1rem,2vw,1.8rem);text-align:center;z-index:2}
.abadge .bn{font-family:var(--fd);font-size:clamp(1.6rem,3vw,2.6rem);font-weight:700;display:block;line-height:1}
.abadge .bl{font-family:var(--fs);font-size:.44rem;letter-spacing:.2em;text-transform:uppercase;display:block;margin-top:.25rem}
.atxt p{font-family:var(--fd);font-size:clamp(1.05rem,1.4vw,1.2rem);font-weight:300;line-height:2;color:#D4C4A0;margin-top:1.4rem}
.astats{display:grid;grid-template-columns:repeat(3,1fr);gap:1.2rem;margin-top:2.5rem;padding-top:2.5rem;border-top:1px solid rgba(200,168,75,.25)}
.astat .n{font-family:var(--fd);font-size:clamp(2rem,3vw,2.8rem);font-weight:600;color:var(--gold);display:block;line-height:1}
.astat .l{font-family:var(--fs);font-size:clamp(.62rem,.7vw,.68rem);letter-spacing:.15em;text-transform:uppercase;color:#C0B090;display:block;margin-top:.35rem}

/* ROOMS */
#rooms{background:var(--bg)}
.rhead{display:flex;flex-wrap:wrap;justify-content:space-between;align-items:flex-end;gap:1rem;margin-bottom:clamp(2rem,4vw,4rem)}
.rcards{display:grid;grid-template-columns:1fr 1fr;gap:3px}
.rcards .rcard:first-child{grid-column:span 2}
.rcard{display:flex;flex-direction:column;background:var(--dark2);transition:transform .4s,box-shadow .4s}
.rcard:hover{transform:translateY(-6px);box-shadow:0 20px 50px rgba(0,0,0,.5)}
.rcard-img{overflow:hidden;flex-shrink:0}
.rcard.feat .rcard-img{height:clamp(220px,30vw,420px)}
.rcard:not(.feat) .rcard-img{height:clamp(180px,22vw,300px)}
.rcard-img img{width:100%;height:100%;object-fit:cover;display:block;transition:transform .8s cubic-bezier(.25,.46,.45,.94)}
.rcard:hover .rcard-img img{transform:scale(1.06)}
.rcard-info{padding:clamp(1.2rem,2vw,1.8rem) clamp(1.2rem,2vw,2rem) clamp(1.4rem,2.5vw,2.2rem);flex:1;display:flex;flex-direction:column;border-top:2px solid transparent;transition:border-color .4s}
.rcard:hover .rcard-info{border-top-color:var(--gold)}
.rnum{font-family:var(--fs);font-size:clamp(.6rem,.65vw,.65rem);letter-spacing:.35em;text-transform:uppercase;color:var(--gold);margin-bottom:.5rem}
.rname{font-family:var(--fd);font-size:clamp(1.35rem,2.2vw,1.7rem);font-weight:500;color:#FFFFFF;line-height:1.2}
.rdesc{font-family:var(--fs);font-size:clamp(.72rem,.8vw,.76rem);line-height:1.9;color:#C0B090;margin-top:.7rem;flex:1}
.rprice-row{display:flex;flex-wrap:wrap;align-items:baseline;justify-content:space-between;gap:.8rem;margin-top:1.3rem;padding-top:1.2rem;border-top:1px solid rgba(200,168,75,.2)}
.rprice{font-family:var(--fd);font-size:clamp(1.2rem,1.8vw,1.5rem);font-weight:500;color:var(--gold);line-height:1}
.rprice small{font-family:var(--fs);font-size:clamp(.6rem,.65vw,.62rem);color:#A89880;display:block;margin-top:.18rem}
.rresv{font-family:var(--fs);font-size:clamp(.62rem,.68vw,.65rem);font-weight:600;letter-spacing:.18em;text-transform:uppercase;color:var(--gold);text-decoration:none;display:flex;align-items:center;gap:.4rem;transition:color .3s}
.rresv .arr{transition:transform .3s}
.rresv:hover{color:var(--gold2)}.rresv:hover .arr{transform:translateX(4px)}

/* SERVICES */
#services{background:var(--dark)}
.svc-intro{text-align:center;max-width:560px;margin:0 auto clamp(2.5rem,5vw,5rem)}
.svc-intro p{font-family:var(--fd);font-size:clamp(.95rem,1.3vw,1.1rem);font-weight:300;color:var(--gold3);line-height:1.95;margin-top:1.2rem}
.sgrid{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:rgba(200,168,75,.08)}
.scard{background:var(--dark);padding:clamp(1.5rem,2.5vw,2.8rem) clamp(1rem,1.5vw,1.8rem);text-align:center;position:relative;overflow:hidden;transition:background .3s}
.scard::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px;background:var(--gold);transform:scaleX(0);transform-origin:left;transition:transform .4s}
.scard:hover::after{transform:scaleX(1)}.scard:hover{background:var(--dark2)}
.sicon{font-size:clamp(1.4rem,2.5vw,2rem);margin-bottom:1.2rem;display:block}
.sname{font-family:var(--fd);font-size:clamp(1.1rem,1.5vw,1.3rem);font-weight:500;color:#FFFFFF;margin-bottom:.6rem}
.sdesc{font-family:var(--fs);font-size:clamp(.7rem,.78vw,.72rem);line-height:1.9;color:#C0B090}

/* GALLERY */
#gallery{background:var(--bg)}
.ghead{display:flex;flex-wrap:wrap;justify-content:space-between;align-items:flex-end;gap:1rem;margin-bottom:clamp(1.5rem,3vw,3rem)}
.gcarousel{display:flex;gap:3px;overflow:hidden}
.gslide{flex-shrink:0;width:calc(33.333% - 2px);transition:width .55s cubic-bezier(.25,.46,.45,.94)}
.gslide.active{width:calc(50% - 1.5px)}
.gslide-img{overflow:hidden}
.gslide-img img{width:100%;height:clamp(200px,35vw,480px);object-fit:cover;display:block;transition:transform .7s cubic-bezier(.25,.46,.45,.94)}
.gslide:hover .gslide-img img{transform:scale(1.04)}
.gcap{background:var(--dark2);padding:clamp(.6rem,1vw,.9rem) clamp(.8rem,1.2vw,1.4rem);display:flex;justify-content:space-between;align-items:center;min-height:clamp(44px,5vw,54px);border-top:1px solid rgba(200,168,75,.2)}
.gcap-name{font-family:var(--fd);font-size:clamp(.9rem,1.2vw,1.05rem);font-weight:400;color:#FFFFFF;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.gcap-num{font-family:var(--fs);font-size:clamp(.58rem,.65vw,.62rem);letter-spacing:.28em;color:var(--gold);flex-shrink:0;margin-left:.8rem}
.garrows{display:flex;gap:.6rem}
.garr{width:clamp(36px,4vw,46px);height:clamp(36px,4vw,46px);border:1px solid rgba(200,168,75,.28);background:transparent;color:var(--gold);cursor:pointer;transition:all .3s;display:flex;align-items:center;justify-content:center;font-family:var(--fs);font-size:.9rem}
.garr:hover{background:var(--gold);color:var(--bg)}
.gdots{display:flex;gap:.5rem;margin-top:1rem;justify-content:center}
.gdot{width:5px;height:5px;border-radius:50%;background:var(--dim);transition:all .3s;cursor:pointer}
.gdot.active{background:var(--gold);width:18px;border-radius:3px}

/* PROMOTIONS */
#promotions{background:var(--dark)}
.promo-grid{display:grid;grid-template-columns:1fr 1.1fr;gap:clamp(2rem,5vw,5rem);margin-top:clamp(2rem,4vw,4rem);align-items:start}
.cal-wrap{background:var(--dark2);border:1px solid rgba(200,168,75,.14);padding:clamp(1.2rem,2vw,2rem)}
.cal-header{display:flex;align-items:center;justify-content:space-between;margin-bottom:1.6rem}
.cal-nav{background:none;border:1px solid rgba(200,168,75,.25);color:var(--gold);width:34px;height:34px;cursor:pointer;font-size:.9rem;transition:all .3s;display:flex;align-items:center;justify-content:center;font-family:var(--fs)}
.cal-nav:hover{background:var(--gold);color:var(--bg)}
.cal-title{font-family:var(--fd);font-size:clamp(1.1rem,1.6vw,1.35rem);color:var(--cream)}
.cal-days{display:grid;grid-template-columns:repeat(7,1fr);gap:2px;margin-bottom:5px}
.cal-day-hdr{font-family:var(--fs);font-size:clamp(.58rem,.65vw,.62rem);letter-spacing:.12em;text-transform:uppercase;color:#C0B090;text-align:center;padding:.35rem 0}
.cal-dates{display:grid;grid-template-columns:repeat(7,1fr);gap:2px}
.cdate{font-family:var(--fs);font-size:clamp(.7rem,.82vw,.76rem);color:#C0B090;text-align:center;padding:clamp(.4rem,.6vw,.52rem) 0;transition:all .25s;border-radius:2px}
.cdate.today{color:var(--gold);font-weight:600}
.cdate.promo{background:rgba(200,168,75,.15);color:var(--cream)}
.cdate.promo-start{background:var(--gold);color:var(--bg);font-weight:600;border-radius:2px 0 0 2px}
.cdate.promo-end{background:var(--gold);color:var(--bg);font-weight:600;border-radius:0 2px 2px 0}
.cdate.other-month{opacity:.2}
.cal-legend{margin-top:1.3rem;display:flex;align-items:center;gap:.7rem}
.leg-dot{width:10px;height:10px;background:var(--gold);border-radius:1px;flex-shrink:0}
.leg-txt{font-family:var(--fs);font-size:clamp(.62rem,.7vw,.66rem);color:#C0B090}
.promos-list{display:flex;flex-direction:column;gap:1.2rem}
.promo-card{background:var(--dark2);border:1px solid rgba(200,168,75,.18);padding:clamp(1.2rem,1.8vw,1.8rem) clamp(1.2rem,1.8vw,2rem);position:relative;transition:border-color .3s}
.promo-card.live-card{border-color:var(--gold)}
.pbadge{position:absolute;top:1.2rem;right:3rem;font-family:var(--fs);font-size:clamp(.58rem,.62vw,.62rem);letter-spacing:.18em;text-transform:uppercase;padding:.28rem .8rem;border-radius:2px}
.pbadge.live{background:rgba(200,168,75,.2);color:var(--gold)}
.pbadge.upcoming{background:rgba(200,168,75,.1);color:#C8A84B}
.pbadge.past{background:transparent;color:#A89880;opacity:.7}
.pname{font-family:var(--fd);font-size:clamp(1.2rem,1.6vw,1.4rem);font-weight:500;color:#FFFFFF;margin-bottom:.4rem}
.pdates{font-family:var(--fs);font-size:clamp(.65rem,.72vw,.68rem);letter-spacing:.1em;color:var(--gold);margin-bottom:.6rem}
.pdesc{font-family:var(--fs);font-size:clamp(.7rem,.78vw,.72rem);line-height:1.85;color:#C0B090}
.pdiscount{font-family:var(--fd);font-size:clamp(1.7rem,2.5vw,2.2rem);font-weight:400;color:var(--gold);margin-top:.5rem}
.pdiscount small{font-family:var(--fs);font-size:clamp(.62rem,.7vw,.65rem);color:#C0B090}
.promo-del{position:absolute;bottom:1.2rem;right:1.2rem;background:none;border:1px solid rgba(200,168,75,.2);color:#A89880;width:26px;height:26px;cursor:pointer;font-size:.68rem;transition:all .3s;display:flex;align-items:center;justify-content:center}
.promo-del:hover{border-color:#c0392b;color:#c0392b}
.no-promo{font-family:var(--fd);font-size:clamp(1rem,1.3vw,1.15rem);font-style:italic;color:#C0B090;text-align:center;padding:2.5rem;border:1px dashed rgba(200,168,75,.2)}

/* PRICING */
#pricing{background:var(--bg)}
.pheader{text-align:center;max-width:540px;margin:0 auto clamp(2.5rem,5vw,5rem)}
.pgrid{display:grid;grid-template-columns:repeat(3,1fr);gap:clamp(.8rem,1.5vw,1.4rem)}
.pcard{border:1px solid rgba(200,168,75,.12);padding:clamp(1.5rem,2.5vw,3rem) clamp(1.2rem,2vw,2.4rem);background:var(--dark2);position:relative;transition:all .4s}
.pcard:hover{border-color:var(--gold);transform:translateY(-8px)}
.pcard.featured{border-color:var(--gold);background:linear-gradient(155deg,#181810,#222211)}
.pfeat-lbl{position:absolute;top:-1px;left:50%;transform:translateX(-50%);background:var(--gold);color:var(--bg);font-family:var(--fs);font-size:clamp(.58rem,.62vw,.62rem);font-weight:700;letter-spacing:.22em;text-transform:uppercase;padding:.35rem 1.2rem;white-space:nowrap}
.ptier{font-family:var(--fs);font-size:clamp(.62rem,.68vw,.66rem);letter-spacing:.28em;text-transform:uppercase;color:var(--gold);margin-bottom:.8rem}
.proom-name{font-family:var(--fd);font-size:clamp(1.3rem,1.8vw,1.8rem);font-weight:500;color:#FFFFFF;padding-bottom:1.4rem;border-bottom:1px solid rgba(200,168,75,.2);margin-bottom:1.4rem}
.pamt{font-family:var(--fd);font-size:clamp(2rem,3vw,3rem);font-weight:400;color:var(--gold);line-height:1}
.pcur{font-family:var(--fs);font-size:clamp(.64rem,.7vw,.66rem);color:#C0B090;letter-spacing:.08em;margin-top:.4rem}
.plist{list-style:none;margin:1.6rem 0}
.plist li{font-family:var(--fs);font-size:clamp(.7rem,.78vw,.74rem);color:#D4C4A0;padding:.6rem 0;border-bottom:1px solid rgba(200,168,75,.1);display:flex;align-items:flex-start;gap:.7rem;line-height:1.6}
.plist li::before{content:'*';color:var(--gold);font-size:.6rem;margin-top:.25rem;flex-shrink:0}
.btn-book{display:block;text-align:center;font-family:var(--fs);font-size:clamp(.64rem,.7vw,.68rem);font-weight:600;letter-spacing:.2em;text-transform:uppercase;padding:.88rem;text-decoration:none;border:1px solid var(--gold);color:var(--gold);background:transparent;cursor:pointer;transition:all .3s;margin-top:1.2rem}
.btn-book:hover,.pcard.featured .btn-book{background:var(--gold);color:var(--bg)}

/* RESERVATION */
#reservation{background:var(--dark)}
.res-grid{display:grid;grid-template-columns:1fr 1fr;gap:clamp(2rem,6vw,8rem);align-items:start}
.res-info{position:sticky;top:6rem}
.res-info p{font-family:var(--fd);font-size:clamp(1.05rem,1.3vw,1.15rem);font-weight:300;color:#D4C4A0;line-height:2;margin-top:1.4rem}
.contacts{margin-top:2.5rem;display:flex;flex-direction:column;gap:1.4rem}
.citem{display:flex;align-items:flex-start;gap:1.1rem;padding-bottom:1.4rem;border-bottom:1px solid rgba(200,168,75,.18)}
.cion{width:40px;height:40px;border:1px solid var(--gold);display:flex;align-items:center;justify-content:center;color:var(--gold);font-size:.95rem;flex-shrink:0}
.clbl{font-family:var(--fs);font-size:clamp(.6rem,.65vw,.62rem);letter-spacing:.22em;text-transform:uppercase;color:#C0B090;display:block;margin-bottom:.3rem}
.cval{font-family:var(--fd);font-size:clamp(1rem,1.2vw,1.1rem);color:#FFFFFF}
.cval a{color:#FFFFFF;text-decoration:none;transition:color .3s}
.cval a:hover{color:var(--gold)}

/* FORM */
.rform{display:flex;flex-direction:column;gap:1.1rem}
.frow{display:grid;grid-template-columns:1fr 1fr;gap:.9rem}
.fg{display:flex;flex-direction:column;gap:.4rem}
.fg label{font-family:var(--fs);font-size:clamp(.64rem,.7vw,.68rem);letter-spacing:.2em;text-transform:uppercase;color:#C0B090}
.fg input,.fg select,.fg textarea{background:var(--dark3);border:1px solid rgba(200,168,75,.2);color:#FFFFFF;padding:clamp(.7rem,.9vw,.9rem) clamp(.8rem,1vw,1.1rem);font-family:var(--fd);font-size:clamp(1rem,1.1vw,1.05rem);outline:none;transition:border-color .3s;width:100%;-webkit-appearance:none;appearance:none}
.fg input::placeholder,.fg textarea::placeholder{color:#7A6E58;font-style:italic}
.fg input:focus,.fg select:focus,.fg textarea:focus{border-color:var(--gold)}
.fg select{background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='8' viewBox='0 0 12 8'%3E%3Cpath d='M1 1l5 5 5-5' stroke='%23C8A84B' stroke-width='1.5' fill='none'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 1rem center;background-color:var(--dark3);padding-right:2.5rem}
.fg select option{background:var(--dark3);color:var(--cream)}
.fg textarea{resize:vertical;min-height:90px}

/* SEND BUTTONS */
.send-btns{display:grid;grid-template-columns:1fr 1fr;gap:.9rem;margin-top:.5rem}
.btn-wa{display:flex;align-items:center;justify-content:center;gap:.6rem;font-family:var(--fs);font-size:clamp(.54rem,.68vw,.62rem);font-weight:600;letter-spacing:.14em;text-transform:uppercase;border:none;padding:clamp(.85rem,1.2vw,1.1rem) 1rem;cursor:pointer;background:#25D366;color:#fff;transition:all .3s;width:100%}
.btn-wa:hover{background:#1ebe5a;transform:translateY(-2px);box-shadow:0 8px 24px rgba(37,211,102,.3)}
.btn-mail{display:flex;align-items:center;justify-content:center;gap:.6rem;font-family:var(--fs);font-size:clamp(.54rem,.68vw,.62rem);font-weight:600;letter-spacing:.14em;text-transform:uppercase;border:1px solid var(--gold);padding:clamp(.85rem,1.2vw,1.1rem) 1rem;cursor:pointer;background:transparent;color:var(--gold);transition:all .3s;width:100%}
.btn-mail:hover{background:var(--gold);color:var(--bg);transform:translateY(-2px);box-shadow:0 8px 24px rgba(200,168,75,.25)}
.btn-wa svg,.btn-mail svg{flex-shrink:0}
.form-msg{display:none;font-family:var(--fs);font-size:clamp(.6rem,.75vw,.66rem);text-align:center;padding:.9rem;margin-top:.5rem;line-height:1.7;border:1px solid;transition:all .3s}
.form-msg.ok{color:var(--gold);border-color:rgba(200,168,75,.28)}
.form-msg.err{color:#e74c3c;border-color:rgba(231,76,60,.28)}

/* FOOTER */
footer{background:var(--dark2);padding:clamp(3rem,6vw,5rem) var(--pad) clamp(1.5rem,3vw,3rem);border-top:1px solid rgba(200,168,75,.12)}
.ftop{display:grid;grid-template-columns:2fr 1fr 1fr 1fr;gap:clamp(1.5rem,3vw,4rem);padding-bottom:clamp(2rem,4vw,4rem);border-bottom:1px solid rgba(200,168,75,.08)}
.flogo{font-family:var(--fd);font-size:clamp(1.4rem,2.5vw,1.9rem);font-weight:600;letter-spacing:.22em;color:var(--gold);text-transform:uppercase;display:block;margin-bottom:1.2rem}
.fabout{font-family:var(--fs);font-size:clamp(.7rem,.8vw,.74rem);line-height:1.95;color:#C0B090}
.fsoc{display:flex;gap:.6rem;margin-top:1.6rem}
.fsocl{width:34px;height:34px;border:1px solid rgba(200,168,75,.3);display:flex;align-items:center;justify-content:center;color:#C0B090;font-family:var(--fs);font-size:.68rem;text-decoration:none;transition:all .3s}
.fsocl:hover{border-color:var(--gold);color:var(--gold)}
.fcol h4{font-family:var(--fs);font-size:clamp(.6rem,.68vw,.64rem);letter-spacing:.25em;text-transform:uppercase;color:var(--gold);margin-bottom:1.3rem}
.flinks{list-style:none;display:flex;flex-direction:column;gap:.7rem}
.flinks a{font-family:var(--fs);font-size:clamp(.7rem,.78vw,.74rem);color:#C0B090;text-decoration:none;transition:color .3s}
.flinks a:hover{color:var(--gold)}
.fbot{display:flex;flex-wrap:wrap;justify-content:space-between;align-items:center;gap:.8rem;padding-top:2rem}
.fcopy{font-family:var(--fs);font-size:clamp(.62rem,.7vw,.65rem);color:#C0B090;letter-spacing:.06em}
.f5{font-family:var(--fs);font-size:clamp(.6rem,.65vw,.62rem);letter-spacing:.25em;text-transform:uppercase;color:var(--gold);border:1px solid rgba(200,168,75,.3);padding:.4rem 1rem}

/* BACK TO TOP */
#btt{position:fixed;bottom:5rem;right:1rem;width:42px;height:42px;background:var(--gold);border:none;color:var(--bg);font-size:.85rem;cursor:pointer;opacity:0;pointer-events:none;transform:translateY(12px);transition:all .35s;z-index:500}
#btt.show{opacity:1;pointer-events:auto;transform:translateY(0)}
#btt:hover{background:var(--gold2)}

/* DASHBOARD BTN */
#dbbtn{position:fixed;bottom:1rem;right:1rem;background:var(--dark3);border:1px solid rgba(200,168,75,.35);color:var(--gold);font-family:var(--fs);font-size:clamp(.5rem,.62vw,.54rem);letter-spacing:.16em;text-transform:uppercase;padding:.6rem 1.1rem;cursor:pointer;z-index:801;transition:all .3s}
#dbbtn:hover{background:var(--gold);color:var(--bg)}

/* DASHBOARD PANEL */
#db{position:fixed;top:0;right:-105%;width:min(480px,100vw);height:100vh;background:var(--dark2);border-left:1px solid rgba(200,168,75,.2);z-index:900;overflow-y:auto;transition:right .45s cubic-bezier(.25,.46,.45,.94)}
#db.open{right:0}
.dbh{position:sticky;top:0;background:var(--dark2);z-index:10;display:flex;justify-content:space-between;align-items:center;padding:1.4rem 1.8rem;border-bottom:1px solid rgba(200,168,75,.18)}
.dbh-ttl{font-family:var(--fd);font-size:1.35rem;color:var(--gold)}
.dbclose{background:none;border:1px solid rgba(200,168,75,.25);color:var(--gold);width:32px;height:32px;cursor:pointer;font-size:.85rem;transition:all .3s}
.dbclose:hover{background:var(--gold);color:var(--bg)}
.dbbody{padding:1.4rem 1.8rem 5rem}
.dbsec{margin-bottom:1.4rem;border:1px solid rgba(200,168,75,.1);background:var(--dark3)}
.dbsec-hdr{font-family:var(--fs);font-size:.5rem;letter-spacing:.26em;text-transform:uppercase;color:var(--gold);padding:.8rem 1.2rem;background:rgba(200,168,75,.07);border-bottom:1px solid rgba(200,168,75,.1);cursor:pointer;display:flex;justify-content:space-between;align-items:center;user-select:none;transition:background .25s}
.dbsec-hdr:hover{background:rgba(200,168,75,.12)}
.ticon{transition:transform .3s;font-size:.65rem}
.dbsec-body{padding:1.2rem;display:flex;flex-direction:column;gap:.8rem}
.dbsec-body.collapsed{display:none}
.dbf{display:flex;flex-direction:column;gap:.35rem}
.dbf label{font-family:var(--fs);font-size:.46rem;letter-spacing:.2em;text-transform:uppercase;color:var(--dim)}
.dbf input,.dbf textarea{width:100%;background:var(--dark);border:1px solid rgba(200,168,75,.12);color:var(--cream);padding:.55rem .85rem;font-family:var(--fs);font-size:.72rem;outline:none;transition:border-color .3s}
.dbf input:focus,.dbf textarea:focus{border-color:var(--gold)}
.dbf textarea{resize:vertical;min-height:62px}
.dbsave{width:100%;background:var(--gold);border:none;color:var(--bg);font-family:var(--fs);font-size:.56rem;font-weight:700;letter-spacing:.2em;text-transform:uppercase;padding:.85rem;cursor:pointer;transition:all .3s}
.dbsave:hover{background:var(--gold2)}
.dbnote{font-family:var(--fs);font-size:.55rem;color:var(--dim);text-align:center;margin-top:.6rem;line-height:1.7}
.dbf-row{display:grid;grid-template-columns:1fr 1fr;gap:.6rem}
.dbsep{height:1px;background:rgba(200,168,75,.1);margin:.2rem 0}
.dbadd{width:100%;background:transparent;border:1px solid var(--gold);color:var(--gold);font-family:var(--fs);font-size:.54rem;font-weight:600;letter-spacing:.18em;text-transform:uppercase;padding:.68rem;cursor:pointer;transition:all .3s}
.dbadd:hover{background:var(--gold);color:var(--bg)}

/* REVEAL */
.rv{opacity:0;transform:translateY(28px);transition:opacity .8s ease,transform .8s ease}
.rv.vis{opacity:1;transform:translateY(0)}
.rv1{transition-delay:.12s}.rv2{transition-delay:.24s}.rv3{transition-delay:.36s}.rv4{transition-delay:.48s}

/* RESPONSIVE TABLETTE */
@media(max-width:900px){
  .nlinks,.nbtn{display:none}
  .hamburger{display:flex}
  .about-grid{grid-template-columns:1fr}
  .aimg-deco{display:none}
  .rcards{grid-template-columns:1fr}
  .rcards .rcard:first-child{grid-column:span 1}
  .rcard.feat .rcard-img,.rcard:not(.feat) .rcard-img{height:clamp(220px,50vw,360px)}
  .sgrid{grid-template-columns:repeat(2,1fr)}
  .gslide{width:calc(50% - 1.5px)}
  .gslide.active{width:calc(65% - 1px)}
  .promo-grid{grid-template-columns:1fr}
  .pgrid{grid-template-columns:1fr;max-width:440px;margin:0 auto}
  .res-grid{grid-template-columns:1fr}
  .res-info{position:static}
  .ftop{grid-template-columns:1fr 1fr;gap:2rem}
}

/* RESPONSIVE MOBILE */
@media(max-width:560px){
  :root{--pad:1.2rem}
  .hscroll{display:none}
  .hbtns{flex-direction:column;align-items:flex-start;gap:1rem}
  .btn-prim{width:100%;text-align:center;padding:.9rem 1.2rem}
  .rhead{flex-direction:column;align-items:flex-start}
  .gslide{width:calc(80% - 1.5px)}
  .gslide.active{width:calc(88% - 1px)}
  .gslide-img img{height:220px}
  .frow{grid-template-columns:1fr}
  .send-btns{grid-template-columns:1fr}
  .ftop{grid-template-columns:1fr}
  .promo-grid{gap:1.8rem}
}
</style>
</head>
<body>

<div id="loader">
  <div class="ld-logo">GOLDEN K</div>
  <div class="ld-sub">Resort - Kribi - Cameroun - 5 Etoiles</div>
  <div class="ld-bar"></div>
</div>

<nav id="nav">
  <a href="#" class="nlogo">Golden <em>K</em></a>
  <ul class="nlinks">
    <li><a href="#about">L'Hotel</a></li>
    <li><a href="#rooms">Suites</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#gallery">Galerie</a></li>
    <li><a href="#promotions">Promotions</a></li>
    <li><a href="#pricing">Tarifs</a></li>
    <li><a href="#reservation">Contact</a></li>
  </ul>
  <a href="#reservation" class="nbtn">Reserver</a>
  <button class="hamburger" id="ham" onclick="toggleMenu()" aria-label="Menu">
    <span class="hbar"></span><span class="hbar"></span><span class="hbar"></span>
  </button>
</nav>

<div class="mobile-menu" id="mmenu">
  <a href="#about" onclick="closeMenu()">L'Hotel</a>
  <a href="#rooms" onclick="closeMenu()">Suites</a>
  <a href="#services" onclick="closeMenu()">Services</a>
  <a href="#gallery" onclick="closeMenu()">Galerie</a>
  <a href="#promotions" onclick="closeMenu()">Promotions</a>
  <a href="#pricing" onclick="closeMenu()">Tarifs</a>
  <a href="#reservation" onclick="closeMenu()">Contact</a>
  <a href="#reservation" onclick="closeMenu()" class="m-res">Reserver</a>
  <div class="m-stars">5 Etoiles - Kribi - Cameroun</div>
</div>

<section id="hero">
  <div id="hbg"></div>
  <div class="hgrad"></div>
  <div class="hcnt">
    <div class="hlbl"><span>5 Etoiles</span><span>Kribi - Cameroun - Hotel de Luxe</span></div>
    <h1 class="htitle" id="htitle1">L'Art de Vivre<br><em id="htitle2">au Bord de l'Atlantique</em></h1>
    <p class="hsub" id="hsubtxt">La ou le raffinement africain rencontre l'elegance mondiale. Une experience d'exception au coeur de la perle du Cameroun.</p>
    <div class="hbtns">
      <a href="#reservation" class="btn-prim"><span>Reserver votre sejour</span></a>
      <a href="#rooms" class="btn-ghost">Decouvrir nos suites <span class="arr">&#8594;</span></a>
    </div>
  </div>
  <div class="hscroll"><div class="sbar"></div><span>Defiler</span></div>
</section>

<div class="mband mband-g"><div class="mtrack">
  <span class="mitem">Luxe Absolu</span><span class="mitem">Kribi</span><span class="mitem">5 Etoiles</span><span class="mitem">Atlantique</span><span class="mitem">Golden K Resort</span><span class="mitem">Excellence</span><span class="mitem">Cameroun</span><span class="mitem">Prestige</span>
  <span class="mitem">Luxe Absolu</span><span class="mitem">Kribi</span><span class="mitem">5 Etoiles</span><span class="mitem">Atlantique</span><span class="mitem">Golden K Resort</span><span class="mitem">Excellence</span><span class="mitem">Cameroun</span><span class="mitem">Prestige</span>
</div></div>

<section id="about" class="sec">
  <div class="about-grid">
    <div class="aimg-wrap rv">
      <img id="about-img" src="https://images.unsplash.com/photo-1571896349842-33c89424de2d?w=900&q=80" alt="Golden K Resort">
      <div class="aimg-deco"></div>
      <div class="abadge"><span class="bn">5</span><span class="bl">Etoiles</span></div>
    </div>
    <div class="atxt">
      <div class="slbl rv">Notre Histoire</div>
      <h2 class="stitle rv rv1" id="atitle">Un Sanctuaire<br><em>de Prestige</em></h2>
      <p class="rv rv2" id="ap1">Niche sur les rives de l'Atlantique, le Golden K Resort incarne une vision audacieuse du luxe africain contemporain. Chaque detail temoigne d'un engagement indefectible envers l'excellence.</p>
      <p class="rv rv3" id="ap2">Kribi, joyau du littoral camerounais, vous offre plages de sable blanc, forets tropicales et chutes majestueuses de la Lobe — a decouvrir dans un confort souverain.</p>
      <div class="astats rv rv4">
        <div class="astat"><span class="n" id="as1n">48</span><span class="l" id="as1l">Suites</span></div>
        <div class="astat"><span class="n" id="as2n">3</span><span class="l" id="as2l">Restaurants</span></div>
        <div class="astat"><span class="n" id="as3n">&#8734;</span><span class="l" id="as3l">Souvenirs</span></div>
      </div>
    </div>
  </div>
</section>

<section id="rooms" class="sec">
  <div class="rhead">
    <div>
      <div class="slbl rv">Hebergements</div>
      <h2 class="stitle rv rv1">Nos <em>Suites</em> &amp; Chambres</h2>
    </div>
    <a href="#pricing" class="btn-ghost rv rv2">Voir les tarifs <span class="arr">&#8594;</span></a>
  </div>
  <div class="rcards rv">
    <div class="rcard feat">
      <div class="rcard-img"><img id="room1-img" src="https://images.unsplash.com/photo-1631049307264-da0ec9d70304?w=1200&q=80" alt="Suite Presidentielle"></div>
      <div class="rcard-info">
        <div class="rnum">Suite - 01</div>
        <div class="rname" id="room1-name">Suite Presidentielle</div>
        <div class="rdesc" id="room1-desc">Vue panoramique sur l'Atlantique. 180 m² de pur raffinement avec terrasse privee, jacuzzi et service 24h/24.</div>
        <div class="rprice-row">
          <div class="rprice"><span id="price1-amt">500 000</span> XAF<small>par nuit - taxes incluses</small></div>
          <a href="#reservation" class="rresv">Reserver <span class="arr">&#8594;</span></a>
        </div>
      </div>
    </div>
    <div class="rcard">
      <div class="rcard-img"><img id="room2-img" src="https://images.unsplash.com/photo-1578683010236-d716f9a3f461?w=800&q=80" alt="Suite Deluxe"></div>
      <div class="rcard-info">
        <div class="rnum">Suite - 02</div>
        <div class="rname" id="room2-name">Suite Deluxe Ocean</div>
        <div class="rdesc" id="room2-desc">Vue mer directe, baignoire ilot et acces spa inclus.</div>
        <div class="rprice-row">
          <div class="rprice"><span id="price2-amt">280 000</span> XAF<small>par nuit</small></div>
          <a href="#reservation" class="rresv">Reserver <span class="arr">&#8594;</span></a>
        </div>
      </div>
    </div>
    <div class="rcard">
      <div class="rcard-img"><img id="room3-img" src="https://images.unsplash.com/photo-1540518614846-7eded433c457?w=800&q=80" alt="Chambre Superieure"></div>
      <div class="rcard-info">
        <div class="rnum">Chambre - 03</div>
        <div class="rname" id="room3-name">Chambre Superieure</div>
        <div class="rdesc" id="room3-desc">Confort cinq etoiles — vue jardin ou piscine, equipements complets inclus.</div>
        <div class="rprice-row">
          <div class="rprice"><span id="price3-amt">150 000</span> XAF<small>par nuit</small></div>
          <a href="#reservation" class="rresv">Reserver <span class="arr">&#8594;</span></a>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="mband mband-d"><div class="mtrack slow rev">
  <span class="mitem">Spa Imperial</span><span class="mitem">Gastronomie Africaine</span><span class="mitem">Piscine Infinity</span><span class="mitem">Plage Privee</span><span class="mitem">Excursions</span><span class="mitem">Room Service 24/7</span><span class="mitem">Transferts VIP</span><span class="mitem">Bar Lounge</span>
  <span class="mitem">Spa Imperial</span><span class="mitem">Gastronomie Africaine</span><span class="mitem">Piscine Infinity</span><span class="mitem">Plage Privee</span><span class="mitem">Excursions</span><span class="mitem">Room Service 24/7</span><span class="mitem">Transferts VIP</span><span class="mitem">Bar Lounge</span>
</div></div>

<section id="services" class="sec">
  <div class="svc-intro">
    <div class="slbl rv" style="justify-content:center">Nos Prestations</div>
    <h2 class="stitle rv rv1" style="text-align:center">Un Univers de <em>Privileges</em></h2>
    <p class="rv rv2">Au Golden K Resort, chaque service est concu pour transcender vos attentes et faire de votre sejour une experience absolument memorable.</p>
  </div>
  <div class="sgrid rv">
    <div class="scard"><span class="sicon">&#127754;</span><div class="sname">Piscine Infinity</div><div class="sdesc">A debordement sur l'Atlantique, notre piscine panoramique redefinie l'horizon.</div></div>
    <div class="scard"><span class="sicon">&#10022;</span><div class="sname">Spa Imperial</div><div class="sdesc">Soins alliant traditions africaines et techniques modernes de bien-etre.</div></div>
    <div class="scard"><span class="sicon">&#127869;</span><div class="sname">Gastronomie</div><div class="sdesc">Trois restaurants d'exception : saveurs camerounaises et cuisine internationale.</div></div>
    <div class="scard"><span class="sicon">&#127958;</span><div class="sname">Plage Privee</div><div class="sdesc">Acces exclusif a notre plage de sable fin avec service personnalise.</div></div>
    <div class="scard"><span class="sicon">&#128664;</span><div class="sname">Transferts VIP</div><div class="sdesc">Accueil en vehicule de prestige. Chauffeur disponible a toute heure.</div></div>
    <div class="scard"><span class="sicon">&#128188;</span><div class="sname">Business Centre</div><div class="sdesc">Salles de conference high-tech pour vos evenements professionnels.</div></div>
    <div class="scard"><span class="sicon">&#127807;</span><div class="sname">Excursions Nature</div><div class="sdesc">Chutes de la Lobe, foret tropicale et faune marine de Kribi.</div></div>
    <div class="scard"><span class="sicon">&#128718;</span><div class="sname">Concierge 24/7</div><div class="sdesc">Une equipe dediee pour repondre a vos moindres desirs.</div></div>
  </div>
</section>

<section id="gallery" class="sec">
  <div class="ghead">
    <div>
      <div class="slbl rv">Galerie</div>
      <h2 class="stitle rv rv1">Laissez-vous <em>Inspirer</em></h2>
    </div>
    <div class="garrows rv rv2">
      <button class="garr" onclick="galPrev()">&#8592;</button>
      <button class="garr" onclick="galNext()">&#8594;</button>
    </div>
  </div>
  <div class="rv">
    <div class="gcarousel" id="gcar"></div>
    <div class="gdots" id="gdots"></div>
  </div>
</section>

<section id="promotions" class="sec">
  <div class="slbl rv">Offres Speciales</div>
  <h2 class="stitle rv rv1">Nos <em>Promotions</em></h2>
  <div class="promo-grid">
    <div class="cal-wrap rv rv2">
      <div class="cal-header">
        <button class="cal-nav" onclick="calPrev()">&#8592;</button>
        <div class="cal-title" id="cal-title">-</div>
        <button class="cal-nav" onclick="calNext()">&#8594;</button>
      </div>
      <div class="cal-days" id="cal-days"></div>
      <div class="cal-dates" id="cal-dates"></div>
      <div class="cal-legend"><div class="leg-dot"></div><span class="leg-txt">Periode promotionnelle active</span></div>
    </div>
    <div id="promos-list" class="promos-list rv rv3"></div>
  </div>
</section>

<section id="pricing" class="sec">
  <div class="pheader">
    <div class="slbl rv" style="justify-content:center">Tarifs</div>
    <h2 class="stitle rv rv1" style="text-align:center">Le Luxe a <em>Votre Mesure</em></h2>
  </div>
  <div class="pgrid">
    <div class="pcard rv">
      <div class="ptier">Sejour Essentiel</div>
      <div class="proom-name" id="pname1">Chambre Superieure</div>
      <div class="pamt" id="pamt1">150 000</div>
      <div class="pcur">XAF par nuit - Taxes incluses</div>
      <ul class="plist">
        <li>Vue jardin ou piscine</li>
        <li>Petit-dejeuner continental inclus</li>
        <li>Acces piscine &amp; plage privee</li>
        <li>Wi-Fi haut debit</li>
        <li>Climatisation &amp; minibar garni</li>
      </ul>
      <a href="#reservation" class="btn-book">Reserver</a>
    </div>
    <div class="pcard featured rv rv1">
      <div class="pfeat-lbl">Le Plus Populaire</div>
      <div class="ptier">Suite Prestige</div>
      <div class="proom-name" id="pname2">Suite Deluxe Ocean</div>
      <div class="pamt" id="pamt2">280 000</div>
      <div class="pcur">XAF par nuit - Taxes incluses</div>
      <ul class="plist">
        <li>Vue directe sur l'Atlantique</li>
        <li>Petit-dejeuner &amp; diner inclus</li>
        <li>Acces spa &amp; salle de sport</li>
        <li>Baignoire ilot &amp; douche italienne</li>
        <li>Concierge personnelle</li>
        <li>Transfert aeroport inclus</li>
      </ul>
      <a href="#reservation" class="btn-book">Reserver</a>
    </div>
    <div class="pcard rv rv2">
      <div class="ptier">L'Ultime Experience</div>
      <div class="proom-name" id="pname3">Suite Presidentielle</div>
      <div class="pamt" id="pamt3">500 000</div>
      <div class="pcur">XAF par nuit - Taxes incluses</div>
      <ul class="plist">
        <li>180 m2 de pure elegance</li>
        <li>Pension complete &amp; room service 24h</li>
        <li>Jacuzzi prive &amp; terrasse panoramique</li>
        <li>Majordome personnel attitree</li>
        <li>Soin spa quotidien offert</li>
        <li>Tout inclus sur demande</li>
      </ul>
      <a href="#reservation" class="btn-book">Reserver</a>
    </div>
  </div>
</section>

<section id="reservation" class="sec">
  <div class="res-grid">
    <div class="res-info">
      <div class="slbl rv">Contact &amp; Reservation</div>
      <h2 class="stitle rv rv1">Planifiez votre<br><em>Sejour de Reve</em></h2>
      <p class="rv rv2">Notre equipe est disponible 24h/24 pour organiser chaque detail de votre experience au Golden K Resort.</p>
      <div class="contacts">
        <div class="citem rv">
          <div class="cion">&#128222;</div>
          <div><span class="clbl">Telephone</span><div class="cval"><a id="ctlph" href="tel:+237600000000">+237 600 000 000</a></div></div>
        </div>
        <div class="citem rv rv1">
          <div class="cion">&#128172;</div>
          <div><span class="clbl">WhatsApp</span><div class="cval"><a id="ctwa" href="https://wa.me/237600000000">+237 600 000 000</a></div></div>
        </div>
        <div class="citem rv rv2">
          <div class="cion">&#9993;</div>
          <div><span class="clbl">Email</span><div class="cval"><a id="ctmail" href="/cdn-cgi/l/email-protection#04676b6a7065677044636b6860616a6f7661776b76702a6769"><span class="__cf_email__" data-cfemail="86e5e9e8f2e7e5f2c6e1e9eae2e3e8edf4e3f5e9f4f2a8e5eb">[email&#160;protected]</span></a></div></div>
        </div>
        <div class="citem rv rv3">
          <div class="cion">&#128205;</div>
          <div><span class="clbl">Adresse</span><div class="cval" id="ctaddr">Boulevard de l'Atlantique, Kribi, Cameroun</div></div>
        </div>
      </div>
    </div>
    <div class="rv">
      <div class="rform">
        <div class="frow">
          <div class="fg"><label>Prenom</label><input id="fn" type="text" placeholder="Votre prenom"></div>
          <div class="fg"><label>Nom</label><input id="ln" type="text" placeholder="Votre nom"></div>
        </div>
        <div class="frow">
          <div class="fg"><label>Email</label><input id="em" type="email" placeholder="vous@exemple.com"></div>
          <div class="fg"><label>Telephone / WhatsApp</label><input id="ph" type="tel" placeholder="+237 6XX XXX XXX"></div>
        </div>
        <div class="frow">
          <div class="fg"><label>Arrivee</label><input id="ci" type="date"></div>
          <div class="fg"><label>Depart</label><input id="co" type="date"></div>
        </div>
        <div class="frow">
          <div class="fg">
            <label>Hebergement</label>
            <select id="rt">
              <option value="">Selectionnez votre hebergement</option>
              <option value="Chambre Superieure - 150 000 XAF / nuit">Chambre Superieure - 150 000 XAF / nuit</option>
              <option value="Suite Deluxe Ocean - 280 000 XAF / nuit">Suite Deluxe Ocean - 280 000 XAF / nuit</option>
              <option value="Suite Presidentielle - 500 000 XAF / nuit">Suite Presidentielle - 500 000 XAF / nuit</option>
            </select>
          </div>
          <div class="fg"><label>Nombre de Personnes</label><input id="res-pers" type="number" min="1" max="20" placeholder="ex. 2"></div>
        </div>
        <div class="fg"><label>Demandes Speciales</label><textarea id="msg" placeholder="Occasions speciales, preferences, services additionnels..."></textarea></div>
        <div class="send-btns">
          <button class="btn-wa" id="btn-whatsapp" type="button">
            <svg viewBox="0 0 24 24" fill="currentColor" width="17" height="17" style="flex-shrink:0"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.136.565 4.14 1.545 5.878L.057 23.5l5.765-1.512A11.94 11.94 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.8 9.8 0 01-5.036-1.388l-.361-.214-3.418.896.912-3.328-.235-.38A9.818 9.818 0 012.182 12C2.182 6.57 6.57 2.182 12 2.182S21.818 6.57 21.818 12 17.43 21.818 12 21.818z"/></svg>
            WhatsApp
          </button>
          <button class="btn-mail" id="btn-email" type="button">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" width="17" height="17" style="flex-shrink:0"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="M2 7l10 7 10-7"/></svg>
            Email
          </button>
        </div>
        <div class="form-msg" id="form-ok">Message prepare ! Verifiez l'application qui vient de s'ouvrir.</div>
        <div class="form-msg" id="form-err">Veuillez remplir tous les champs obligatoires.</div>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="ftop">
    <div>
      <span class="flogo">Golden K</span>
      <p class="fabout">Le Golden K Resort est le symbole du luxe a Kribi, une adresse de reference sur le continent africain.</p>
      <div class="fsoc">
        <a href="#" class="fsocl">f</a>
        <a href="#" class="fsocl">in</a>
        <a href="#" class="fsocl">ig</a>
        <a href="#" class="fsocl">&#9654;</a>
      </div>
    </div>
    <div class="fcol">
      <h4>L'Hotel</h4>
      <ul class="flinks">
        <li><a href="#about">Histoire</a></li>
        <li><a href="#rooms">Suites</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#gallery">Galerie</a></li>
      </ul>
    </div>
    <div class="fcol">
      <h4>Sejour</h4>
      <ul class="flinks">
        <li><a href="#pricing">Tarifs</a></li>
        <li><a href="#promotions">Promotions</a></li>
        <li><a href="#reservation">Reserver</a></li>
      </ul>
    </div>
    <div class="fcol">
      <h4>Contact</h4>
      <ul class="flinks">
        <li><a href="tel:+237600000000">+237 600 000 000</a></li>
        <li><a href="/cdn-cgi/l/email-protection#a0c3cfced4c1c3d4e0c7cfccc4c5cecbd2c5d3cfd2d48ec3cd"><span class="__cf_email__" data-cfemail="d3b0bcbda7b2b0a793b4bcbfb7b6bdb8a1b6a0bca1a7fdb0be">[email&#160;protected]</span></a></li>
        <li>Kribi, Cameroun</li>
      </ul>
    </div>
  </div>
  <div class="fbot">
    <p class="fcopy">2025 Golden K Resort - Kribi, Cameroun</p>
    <div class="f5">5 Etoiles - Hotel de Luxe</div>
  </div>
</footer>

<button id="btt" onclick="scrollTo({top:0,behavior:'smooth'})">&#8593;</button>
<button id="dbbtn" onclick="toggleDB()">Tableau de bord</button>

<div id="db">
  <div class="dbh"><div class="dbh-ttl">Tableau de Bord</div><button class="dbclose" onclick="toggleDB()">X</button></div>
  <div class="dbbody">

    <div class="dbsec">
      <div class="dbsec-hdr" onclick="toggleSec(this)">Hero <span class="ticon">v</span></div>
      <div class="dbsec-body">
        <div class="dbf"><label>Titre ligne 1</label><input id="d-t1" type="text" placeholder="L'Art de Vivre"></div>
        <div class="dbf"><label>Titre ligne 2 (italique)</label><input id="d-t2" type="text" placeholder="au Bord de l'Atlantique"></div>
        <div class="dbf"><label>Sous-titre</label><textarea id="d-sub" rows="2"></textarea></div>
        <div class="dbf"><label>Image Hero (URL)</label><input id="d-ih" type="url" placeholder="https://..."></div>
        <button class="dbsave" onclick="applyHero()">Appliquer</button>
      </div>
    </div>

    <div class="dbsec">
      <div class="dbsec-hdr" onclick="toggleSec(this)">Section Histoire <span class="ticon">v</span></div>
      <div class="dbsec-body">
        <div class="dbf"><label>Titre ligne 1</label><input id="d-at1" type="text"></div>
        <div class="dbf"><label>Titre ligne 2</label><input id="d-at2" type="text"></div>
        <div class="dbf"><label>Paragraphe 1</label><textarea id="d-ap1" rows="3"></textarea></div>
        <div class="dbf"><label>Paragraphe 2</label><textarea id="d-ap2" rows="3"></textarea></div>
        <div class="dbf-row">
          <div class="dbf"><label>Stat 1 Chiffre</label><input id="d-s1n" type="text"></div>
          <div class="dbf"><label>Stat 1 Libelle</label><input id="d-s1l" type="text"></div>
        </div>
        <div class="dbf-row">
          <div class="dbf"><label>Stat 2 Chiffre</label><input id="d-s2n" type="text"></div>
          <div class="dbf"><label>Stat 2 Libelle</label><input id="d-s2l" type="text"></div>
        </div>
        <div class="dbf-row">
          <div class="dbf"><label>Stat 3 Chiffre</label><input id="d-s3n" type="text"></div>
          <div class="dbf"><label>Stat 3 Libelle</label><input id="d-s3l" type="text"></div>
        </div>
        <div class="dbf"><label>Image (URL)</label><input id="d-ia" type="url"></div>
        <button class="dbsave" onclick="applyAbout()">Appliquer</button>
      </div>
    </div>

    <div class="dbsec">
      <div class="dbsec-hdr" onclick="toggleSec(this)">Chambres et Suites <span class="ticon">v</span></div>
      <div class="dbsec-body">
        <div class="dbf"><label>Suite 01 Nom</label><input id="d-rn1" type="text"></div>
        <div class="dbf"><label>Suite 01 Description</label><textarea id="d-rd1" rows="2"></textarea></div>
        <div class="dbf-row">
          <div class="dbf"><label>Prix XAF</label><input id="d-rp1" type="text"></div>
          <div class="dbf"><label>Image URL</label><input id="d-ri1" type="url"></div>
        </div>
        <div class="dbsep"></div>
        <div class="dbf"><label>Suite 02 Nom</label><input id="d-rn2" type="text"></div>
        <div class="dbf"><label>Suite 02 Description</label><textarea id="d-rd2" rows="2"></textarea></div>
        <div class="dbf-row">
          <div class="dbf"><label>Prix XAF</label><input id="d-rp2" type="text"></div>
          <div class="dbf"><label>Image URL</label><input id="d-ri2" type="url"></div>
        </div>
        <div class="dbsep"></div>
        <div class="dbf"><label>Chambre 03 Nom</label><input id="d-rn3" type="text"></div>
        <div class="dbf"><label>Chambre 03 Description</label><textarea id="d-rd3" rows="2"></textarea></div>
        <div class="dbf-row">
          <div class="dbf"><label>Prix XAF</label><input id="d-rp3" type="text"></div>
          <div class="dbf"><label>Image URL</label><input id="d-ri3" type="url"></div>
        </div>
        <button class="dbsave" onclick="applyRooms()">Appliquer</button>
      </div>
    </div>

    <div class="dbsec">
      <div class="dbsec-hdr" onclick="toggleSec(this)">Galerie Photos <span class="ticon">v</span></div>
      <div class="dbsec-body" id="db-gal-body"></div>
    </div>

    <div class="dbsec">
      <div class="dbsec-hdr" onclick="toggleSec(this)">Contacts <span class="ticon">v</span></div>
      <div class="dbsec-body">
        <div class="dbf"><label>Telephone</label><input id="d-ct" type="tel"></div>
        <div class="dbf"><label>WhatsApp (numero sans +)</label><input id="d-cw" type="tel"></div>
        <div class="dbf"><label>Email</label><input id="d-ce" type="email"></div>
        <div class="dbf"><label>Adresse</label><input id="d-ca" type="text"></div>
        <button class="dbsave" onclick="applyContacts()">Appliquer</button>
      </div>
    </div>

    <div class="dbsec">
      <div class="dbsec-hdr" onclick="toggleSec(this)">Ajouter une Promotion <span class="ticon">v</span></div>
      <div class="dbsec-body">
        <div class="dbf"><label>Nom de la promotion</label><input id="p-name" type="text" placeholder="ex. Offre Noel Atlantique"></div>
        <div class="dbf"><label>Description</label><textarea id="p-desc" rows="2" placeholder="ex. Reduction sur toutes les suites..."></textarea></div>
        <div class="dbf-row">
          <div class="dbf"><label>Debut</label><input id="p-start" type="date"></div>
          <div class="dbf"><label>Fin</label><input id="p-end" type="date"></div>
        </div>
        <div class="dbf"><label>Reduction (ex. 20%)</label><input id="p-disc" type="text" placeholder="20%"></div>
        <button class="dbadd" onclick="addPromo()">+ Ajouter cette promotion</button>
        <p class="dbnote">La promotion apparaitra sur le calendrier et dans la section Offres Speciales.</p>
      </div>
    </div>

  </div>
</div>

<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
"use strict";

/* ====================================================
   CONFIG — MODIFIER CES VALEURS AVANT MISE EN LIGNE
==================================================== */
var WA_NUM    = "237600000000";           // ton vrai numero sans + ni espaces
var HTL_MAIL  = "contact@goldenkresort.cm"; // ton vrai email
var HTL_NOM   = "Golden K Resort";

/* ====================================================
   STORE — sauvegarde locale
==================================================== */
var SK = "gkr_v6";
var D = {
  hero:    { t1:"", t2:"", sub:"", img:"" },
  about:   { t1:"", t2:"", p1:"", p2:"", s1n:"", s1l:"", s2n:"", s2l:"", s3n:"", s3l:"", img:"" },
  rooms:   [ {name:"",desc:"",price:"",img:""}, {name:"",desc:"",price:"",img:""}, {name:"",desc:"",price:"",img:""} ],
  gallery: [
    { url:"https://images.unsplash.com/photo-1566073771259-6a8506099945?w=900&q=80", cap:"Piscine Infinity" },
    { url:"https://images.unsplash.com/photo-1520250497591-112f2f40a3f4?w=900&q=80", cap:"Vue Atlantique" },
    { url:"https://images.unsplash.com/photo-1544161515-4ab6ce6db874?w=900&q=80",    cap:"Spa Imperial" },
    { url:"https://images.unsplash.com/photo-1414235077428-338989a2e8c0?w=900&q=80", cap:"Restaurant" },
    { url:"https://images.unsplash.com/photo-1507525428034-b723cf961d3e?w=900&q=80", cap:"Plage Privee" },
    { url:"https://images.unsplash.com/photo-1571003123894-1f0594d2b5d9?w=900&q=80", cap:"Suite de Luxe" }
  ],
  contacts: { tel:"", wa:"", email:"", addr:"" },
  promos:   []
};

function storeSave() {
  try { localStorage.setItem(SK, JSON.stringify(D)); } catch(e) {}
}
function storeLoad() {
  try {
    var raw = localStorage.getItem(SK);
    if (raw) {
      var parsed = JSON.parse(raw);
      if (parsed.hero)     Object.assign(D.hero,    parsed.hero);
      if (parsed.about)    Object.assign(D.about,   parsed.about);
      if (parsed.rooms)    D.rooms    = parsed.rooms;
      if (parsed.gallery)  D.gallery  = parsed.gallery;
      if (parsed.contacts) Object.assign(D.contacts, parsed.contacts);
      if (parsed.promos)   D.promos   = parsed.promos;
    }
  } catch(e) {}
}

/* ====================================================
   LOADER
==================================================== */
window.addEventListener("load", function() {
  setTimeout(function() {
    var el = document.getElementById("loader");
    if (el) el.classList.add("out");
  }, 2000);
});

/* ====================================================
   HERO BG + PARALLAX
==================================================== */
var hbgEl = document.getElementById("hbg");
function setHeroBg(url) {
  var src = url || "https://images.unsplash.com/photo-1582268611958-ebfd161ef9cf?w=1900&q=80";
  hbgEl.style.backgroundImage = "url('" + src + "')";
}
setHeroBg("");
window.addEventListener("scroll", function() {
  hbgEl.style.transform = "scale(1.1) translateY(" + (window.scrollY * 0.14) + "px)";
}, { passive: true });

/* ====================================================
   NAV / BTT
==================================================== */
var navEl = document.getElementById("nav");
var bttEl = document.getElementById("btt");
window.addEventListener("scroll", function() {
  if (window.scrollY > 60)  navEl.classList.add("scrolled"); else navEl.classList.remove("scrolled");
  if (window.scrollY > 600) bttEl.classList.add("show");    else bttEl.classList.remove("show");
}, { passive: true });

/* ====================================================
   MOBILE MENU
==================================================== */
function toggleMenu() {
  document.getElementById("ham").classList.toggle("open");
  document.getElementById("mmenu").classList.toggle("open");
  document.body.style.overflow = document.getElementById("mmenu").classList.contains("open") ? "hidden" : "";
}
function closeMenu() {
  document.getElementById("ham").classList.remove("open");
  document.getElementById("mmenu").classList.remove("open");
  document.body.style.overflow = "";
}

/* ====================================================
   REVEAL ON SCROLL
==================================================== */
var revealObs = new IntersectionObserver(function(entries) {
  entries.forEach(function(e) { if (e.isIntersecting) e.target.classList.add("vis"); });
}, { threshold: 0.07 });
document.querySelectorAll(".rv").forEach(function(el) { revealObs.observe(el); });

/* ====================================================
   GALLERY CAROUSEL
==================================================== */
var galIdx = 0;

function buildGallery() {
  var car  = document.getElementById("gcar");
  var dots = document.getElementById("gdots");
  if (!car || !dots) return;
  car.innerHTML  = "";
  dots.innerHTML = "";

  D.gallery.forEach(function(item, i) {
    var slide = document.createElement("div");
    slide.className = "gslide" + (i === galIdx ? " active" : "");
    slide.innerHTML =
      '<div class="gslide-img"><img src="' + item.url + '" alt="' + item.cap + '" loading="lazy"></div>' +
      '<div class="gcap">' +
        '<span class="gcap-name">' + item.cap + '</span>' +
        '<span class="gcap-num">' + String(i + 1).padStart(2, "0") + " / " + String(D.gallery.length).padStart(2, "0") + '</span>' +
      '</div>';
    slide.addEventListener("click", (function(idx) {
      return function() { galIdx = idx; updateGallery(); };
    })(i));
    car.appendChild(slide);

    var dot = document.createElement("div");
    dot.className = "gdot" + (i === galIdx ? " active" : "");
    dot.addEventListener("click", (function(idx) {
      return function() { galIdx = idx; updateGallery(); };
    })(i));
    dots.appendChild(dot);
  });
}

function updateGallery() {
  document.querySelectorAll(".gslide").forEach(function(s, i) {
    s.classList.toggle("active", i === galIdx);
  });
  document.querySelectorAll(".gdot").forEach(function(d, i) {
    d.classList.toggle("active", i === galIdx);
  });
}
function galNext() { galIdx = (galIdx + 1) % D.gallery.length; updateGallery(); }
function galPrev() { galIdx = (galIdx - 1 + D.gallery.length) % D.gallery.length; updateGallery(); }

/* ====================================================
   CALENDAR
==================================================== */
var calY, calM;
var MOIS = ["Janvier","Fevrier","Mars","Avril","Mai","Juin","Juillet","Aout","Septembre","Octobre","Novembre","Decembre"];
var JOURS = ["Lu","Ma","Me","Je","Ve","Sa","Di"];

function initCal() {
  var now = new Date();
  calY = now.getFullYear();
  calM = now.getMonth();
  renderCal();
}
function calPrev() { calM--; if (calM < 0) { calM = 11; calY--; } renderCal(); }
function calNext() { calM++; if (calM > 11) { calM = 0;  calY++; } renderCal(); }

function dateInPromo(y, m, d) {
  var dt = new Date(y, m, d);
  return D.promos.some(function(p) {
    if (!p.start || !p.end) return false;
    return dt >= new Date(p.start) && dt <= new Date(p.end);
  });
}
function isPromoStart(y, m, d) {
  var dt = new Date(y, m, d);
  return D.promos.some(function(p) {
    return p.start && new Date(p.start).toDateString() === dt.toDateString();
  });
}
function isPromoEnd(y, m, d) {
  var dt = new Date(y, m, d);
  return D.promos.some(function(p) {
    return p.end && new Date(p.end).toDateString() === dt.toDateString();
  });
}

function renderCal() {
  var titleEl = document.getElementById("cal-title");
  var daysEl  = document.getElementById("cal-days");
  var datesEl = document.getElementById("cal-dates");
  if (!titleEl || !daysEl || !datesEl) return;

  titleEl.textContent = MOIS[calM] + " " + calY;
  daysEl.innerHTML = JOURS.map(function(j) { return '<div class="cal-day-hdr">' + j + '</div>'; }).join("");

  var firstDay = new Date(calY, calM, 1).getDay();
  var offset   = firstDay === 0 ? 6 : firstDay - 1;
  var daysInMonth = new Date(calY, calM + 1, 0).getDate();
  var daysInPrev  = new Date(calY, calM, 0).getDate();
  var today = new Date();
  var html  = "";

  for (var i = 0; i < offset; i++) {
    html += '<div class="cdate other-month">' + (daysInPrev - offset + 1 + i) + '</div>';
  }
  for (var d = 1; d <= daysInMonth; d++) {
    var cls = "cdate";
    if (today.getFullYear() === calY && today.getMonth() === calM && today.getDate() === d) cls += " today";
    if      (isPromoStart(calY, calM, d))  cls += " promo-start";
    else if (isPromoEnd(calY, calM, d))    cls += " promo-end";
    else if (dateInPromo(calY, calM, d))   cls += " promo";
    html += '<div class="' + cls + '">' + d + '</div>';
  }
  var total   = offset + daysInMonth;
  var fillEnd = total % 7 === 0 ? 0 : 7 - (total % 7);
  for (var k = 1; k <= fillEnd; k++) {
    html += '<div class="cdate other-month">' + k + '</div>';
  }
  datesEl.innerHTML = html;
}

/* ====================================================
   PROMOTIONS
==================================================== */
function addPromo() {
  var nm    = (document.getElementById("p-name")?.value || "").trim();
  var st    = document.getElementById("p-start")?.value || "";
  var en    = document.getElementById("p-end")?.value   || "";
  var desc  = (document.getElementById("p-desc")?.value || "").trim();
  var disc  = (document.getElementById("p-disc")?.value || "").trim();

  if (!nm || !st || !en) { alert("Veuillez saisir le nom, la date de debut et la date de fin."); return; }
  if (new Date(st) > new Date(en)) { alert("La date de debut doit etre avant la date de fin."); return; }

  D.promos.push({ id: Date.now(), name: nm, desc: desc, start: st, end: en, disc: disc });
  storeSave();
  renderPromos();
  renderCal();
  ["p-name","p-desc","p-start","p-end","p-disc"].forEach(function(id) {
    var el = document.getElementById(id); if (el) el.value = "";
  });
}

function delPromo(id) {
  D.promos = D.promos.filter(function(p) { return p.id !== id; });
  storeSave(); renderPromos(); renderCal();
}

function promoStatus(p) {
  var now = new Date(), s = new Date(p.start), e = new Date(p.end);
  e.setHours(23, 59, 59);
  if (now >= s && now <= e) return "live";
  if (now < s)              return "upcoming";
  return "past";
}

function formatDate(ds) {
  if (!ds) return "-";
  var parts = ds.split("-");
  return parts[2] + "/" + parts[1] + "/" + parts[0];
}

function renderPromos() {
  var el = document.getElementById("promos-list");
  if (!el) return;
  if (!D.promos.length) {
    el.innerHTML = '<div class="no-promo">Aucune promotion en cours.<br>Creez-en une depuis le tableau de bord.</div>';
    return;
  }
  var sorted = D.promos.slice().sort(function(a, b) { return new Date(a.start) - new Date(b.start); });
  var labels = { live: "En cours", upcoming: "A venir", past: "Terminee" };
  el.innerHTML = sorted.map(function(p) {
    var st = promoStatus(p);
    return '<div class="promo-card ' + (st === "live" ? "live-card" : "") + '">' +
      '<div class="pbadge ' + st + '">' + labels[st] + '</div>' +
      '<div class="pname">' + p.name + '</div>' +
      '<div class="pdates">' + formatDate(p.start) + ' &rarr; ' + formatDate(p.end) + '</div>' +
      (p.desc ? '<div class="pdesc">' + p.desc + '</div>' : '') +
      (p.disc ? '<div class="pdiscount">' + p.disc + ' <small>de reduction</small></div>' : '') +
      '<button class="promo-del" onclick="delPromo(' + p.id + ')">X</button>' +
      '</div>';
  }).join("");
}

/* ====================================================
   WHATSAPP + EMAIL — RESERVATION
==================================================== */
function getFormData() {
  var prenom  = (document.getElementById("fn")?.value  || "").trim();
  var nom     = (document.getElementById("ln")?.value  || "").trim();
  var email   = (document.getElementById("em")?.value  || "").trim();
  var tel     = (document.getElementById("ph")?.value  || "").trim();
  var arrivee = (document.getElementById("ci")?.value  || "");
  var depart  = (document.getElementById("co")?.value  || "");
  var chambre = (document.getElementById("rt")?.value  || "").trim();
  var pers    = (document.getElementById("res-pers")?.value || "").trim();
  var message = (document.getElementById("msg")?.value || "").trim();

  if (!prenom || !nom || !chambre || !arrivee || !depart) {
    showMsg("err");
    return null;
  }
  if (new Date(arrivee) >= new Date(depart)) {
    alert("La date de depart doit etre apres la date d'arrivee.");
    return null;
  }
  return { prenom:prenom, nom:nom, email:email, tel:tel,
           arrivee:arrivee, depart:depart, chambre:chambre,
           pers:pers, message:message };
}

function showMsg(type) {
  var ok  = document.getElementById("form-ok");
  var err = document.getElementById("form-err");
  if (!ok || !err) return;
  ok.style.display  = "none";
  err.style.display = "none";
  if (type === "ok") {
    ok.classList.add("ok"); ok.style.display = "block";
    setTimeout(function() { ok.style.display = "none"; }, 7000);
  } else {
    err.classList.add("err"); err.style.display = "block";
    setTimeout(function() { err.style.display = "none"; }, 5000);
  }
}

document.getElementById("btn-whatsapp").addEventListener("click", function() {
  var f = getFormData();
  if (!f) return;

  var waNum = (D.contacts.wa && D.contacts.wa.trim()) ? D.contacts.wa.replace(/[^0-9]/g,"") : WA_NUM;

  var texte = "Bonjour " + HTL_NOM + " !\n\n" +
    "Je souhaite effectuer une reservation :\n\n" +
    "Nom : " + f.prenom + " " + f.nom + "\n" +
    "Hebergement : " + f.chambre + "\n" +
    "Arrivee : " + formatDate(f.arrivee) + "\n" +
    "Depart : " + formatDate(f.depart) + "\n" +
    "Personnes : " + (f.pers || "Non precise") + "\n" +
    (f.tel     ? "Mon telephone : " + f.tel + "\n"     : "") +
    (f.email   ? "Mon email : " + f.email + "\n"       : "") +
    (f.message ? "\nDemande speciale : " + f.message + "\n" : "") +
    "\nMerci de confirmer la disponibilite.";

  var url = "https://wa.me/" + waNum + "?text=" + encodeURIComponent(texte);
  window.open(url, "_blank");
  showMsg("ok");
});

document.getElementById("btn-email").addEventListener("click", function() {
  var f = getFormData();
  if (!f) return;

  var dest  = (D.contacts.email && D.contacts.email.trim()) ? D.contacts.email.trim() : HTL_MAIL;
  var sujet = "Demande de reservation - " + HTL_NOM;
  var corps =
    "Bonjour,\n\n" +
    "Je souhaite effectuer une reservation au " + HTL_NOM + ".\n\n" +
    "Nom complet  : " + f.prenom + " " + f.nom + "\n" +
    "Hebergement  : " + f.chambre + "\n" +
    "Date arrivee : " + formatDate(f.arrivee) + "\n" +
    "Date depart  : " + formatDate(f.depart)  + "\n" +
    "Nb personnes : " + (f.pers || "Non precise") + "\n" +
    (f.email   ? "Email client : " + f.email + "\n"     : "") +
    (f.tel     ? "Telephone    : " + f.tel   + "\n"     : "") +
    (f.message ? "\nDemande speciale :\n" + f.message + "\n" : "") +
    "\nDans l'attente de votre confirmation.\n\nCordialement,\n" + f.prenom + " " + f.nom;

  window.location.href =
    "mailto:" + dest +
    "?subject=" + encodeURIComponent(sujet) +
    "&body="    + encodeURIComponent(corps);
  showMsg("ok");
});

/* ====================================================
   DASHBOARD
==================================================== */
function toggleDB() { document.getElementById("db").classList.toggle("open"); }

function toggleSec(hdr) {
  var body = hdr.nextElementSibling;
  var icon = hdr.querySelector(".ticon");
  body.classList.toggle("collapsed");
  if (icon) icon.textContent = body.classList.contains("collapsed") ? ">" : "v";
}

function dbVal(id) { return (document.getElementById(id)?.value || "").trim(); }

function dbFlash(btn) {
  if (!btn) return;
  var orig = btn.textContent;
  btn.textContent = "Applique !";
  btn.style.background = "#2a6e2a";
  setTimeout(function() { btn.textContent = orig; btn.style.background = ""; }, 2600);
}

function buildGalDash() {
  var el = document.getElementById("db-gal-body");
  if (!el) return;
  var html = "";
  D.gallery.forEach(function(g, i) {
    html +=
      '<div class="dbf"><label>Photo ' + (i+1) + ' - Legende</label>' +
      '<input id="dg-c-' + i + '" type="text" value="' + (g.cap || "") + '"></div>' +
      '<div class="dbf"><label>Photo ' + (i+1) + ' - URL</label>' +
      '<input id="dg-u-' + i + '" type="url" value="' + (g.url || "") + '"></div>';
    if (i < D.gallery.length - 1) html += '<div class="dbsep"></div>';
  });
  html +=
    '<div class="dbsep"></div>' +
    '<div class="dbf"><label>Nouvelle photo URL</label><input id="dg-nu" type="url" placeholder="https://..."></div>' +
    '<div class="dbf"><label>Nouvelle photo Legende</label><input id="dg-nc" type="text" placeholder="Description..."></div>' +
    '<button class="dbsave" onclick="applyGallery()">Appliquer la galerie</button>';
  el.innerHTML = html;
}

function applyHero() {
  var t1  = dbVal("d-t1"), t2 = dbVal("d-t2"), sub = dbVal("d-sub"), img = dbVal("d-ih");
  if (t1) { var h1 = document.getElementById("htitle1"); if (h1 && h1.childNodes[0]) h1.childNodes[0].textContent = t1; }
  if (t2) { var h2 = document.getElementById("htitle2"); if (h2) h2.textContent = t2; }
  if (sub) { var hs = document.getElementById("hsubtxt"); if (hs) hs.textContent = sub; }
  if (img) { setHeroBg(img); D.hero.img = img; }
  Object.assign(D.hero, { t1:t1, t2:t2, sub:sub });
  storeSave();
  dbFlash(document.querySelector("#db .dbsec:nth-child(1) .dbsave"));
}

function applyAbout() {
  var t1  = dbVal("d-at1"), t2 = dbVal("d-at2");
  var p1  = dbVal("d-ap1"), p2 = dbVal("d-ap2");
  var s1n = dbVal("d-s1n"), s1l = dbVal("d-s1l");
  var s2n = dbVal("d-s2n"), s2l = dbVal("d-s2l");
  var s3n = dbVal("d-s3n"), s3l = dbVal("d-s3l");
  var img = dbVal("d-ia");

  if (t1 || t2) {
    var at = document.getElementById("atitle");
    if (at) at.innerHTML = (t1 || "Un Sanctuaire") + "<br><em>" + (t2 || "de Prestige") + "</em>";
  }
  if (p1) { var ap1 = document.getElementById("ap1"); if (ap1) ap1.textContent = p1; }
  if (p2) { var ap2 = document.getElementById("ap2"); if (ap2) ap2.textContent = p2; }
  var statMap = [["as1n",s1n],["as1l",s1l],["as2n",s2n],["as2l",s2l],["as3n",s3n],["as3l",s3l]];
  statMap.forEach(function(pair) { if (pair[1]) { var e=document.getElementById(pair[0]); if(e) e.textContent=pair[1]; } });
  if (img) { var ai = document.getElementById("about-img"); if (ai) ai.src = img; }

  Object.assign(D.about, {t1:t1,t2:t2,p1:p1,p2:p2,s1n:s1n,s1l:s1l,s2n:s2n,s2l:s2l,s3n:s3n,s3l:s3l,img:img});
  storeSave();
  dbFlash(document.querySelector("#db .dbsec:nth-child(2) .dbsave"));
}

function applyRooms() {
  [1, 2, 3].forEach(function(i) {
    var n   = dbVal("d-rn" + i);
    var d   = dbVal("d-rd" + i);
    var p   = dbVal("d-rp" + i);
    var img = dbVal("d-ri" + i);
    if (n)   { var rn = document.getElementById("room" + i + "-name"); if (rn) rn.textContent = n; }
    if (d)   { var rd = document.getElementById("room" + i + "-desc"); if (rd) rd.textContent = d; }
    if (p)   {
      var pa = document.getElementById("price" + i + "-amt"); if (pa) pa.textContent = p;
      var pb = document.getElementById("pamt" + i);            if (pb) pb.textContent = p;
    }
    if (img) { var ri = document.getElementById("room" + i + "-img"); if (ri) ri.src = img; }
    Object.assign(D.rooms[i - 1], { name:n, desc:d, price:p, img:img });
  });
  storeSave();
  dbFlash(document.querySelector("#db .dbsec:nth-child(3) .dbsave"));
}

function applyGallery() {
  D.gallery.forEach(function(g, i) {
    var u = (document.getElementById("dg-u-" + i)?.value || "").trim();
    var c = (document.getElementById("dg-c-" + i)?.value || "").trim();
    if (u) g.url = u;
    if (c) g.cap = c;
  });
  var nu = (document.getElementById("dg-nu")?.value || "").trim();
  var nc = (document.getElementById("dg-nc")?.value || "").trim();
  if (nu) D.gallery.push({ url: nu, cap: nc || ("Photo " + (D.gallery.length + 1)) });
  storeSave();
  buildGallery();
  buildGalDash();
  dbFlash(document.querySelector("#db .dbsec:nth-child(4) .dbsave"));
}

function applyContacts() {
  var tel   = dbVal("d-ct");
  var wa    = dbVal("d-cw");
  var email = dbVal("d-ce");
  var addr  = dbVal("d-ca");

  if (tel) {
    var lt = document.getElementById("ctlph");
    if (lt) { lt.textContent = tel; lt.href = "tel:" + tel.replace(/\s/g, ""); }
  }
  if (wa) {
    var lw = document.getElementById("ctwa");
    if (lw) { lw.textContent = wa; lw.href = "https://wa.me/" + wa.replace(/[^0-9]/g, ""); }
    WA_NUM = wa.replace(/[^0-9]/g, "");
  }
  if (email) {
    var le = document.getElementById("ctmail");
    if (le) { le.textContent = email; le.href = "mailto:" + email; }
    HTL_MAIL = email;
  }
  if (addr) { var la = document.getElementById("ctaddr"); if (la) la.textContent = addr; }

  Object.assign(D.contacts, { tel:tel, wa:wa, email:email, addr:addr });
  storeSave();
  dbFlash(document.querySelector("#db .dbsec:nth-child(5) .dbsave"));
}

/* ====================================================
   RESTORE SAVED STATE
==================================================== */
function restoreState() {
  var h = D.hero;
  if (h.t1) {
    var h1 = document.getElementById("htitle1");
    if (h1 && h1.childNodes[0]) h1.childNodes[0].textContent = h.t1;
    var f1 = document.getElementById("d-t1"); if (f1) f1.value = h.t1;
  }
  if (h.t2) {
    var h2 = document.getElementById("htitle2"); if (h2) h2.textContent = h.t2;
    var f2 = document.getElementById("d-t2"); if (f2) f2.value = h.t2;
  }
  if (h.sub) {
    var hs = document.getElementById("hsubtxt"); if (hs) hs.textContent = h.sub;
    var fs = document.getElementById("d-sub"); if (fs) fs.value = h.sub;
  }
  if (h.img) setHeroBg(h.img);

  var ab = D.about;
  if (ab.t1 || ab.t2) {
    var at = document.getElementById("atitle");
    if (at) at.innerHTML = (ab.t1 || "Un Sanctuaire") + "<br><em>" + (ab.t2 || "de Prestige") + "</em>";
  }
  if (ab.p1) { var ap1 = document.getElementById("ap1"); if (ap1) ap1.textContent = ab.p1; }
  if (ab.p2) { var ap2 = document.getElementById("ap2"); if (ap2) ap2.textContent = ab.p2; }

  var statMap2 = [["as1n",ab.s1n],["as1l",ab.s1l],["as2n",ab.s2n],["as2l",ab.s2l],["as3n",ab.s3n],["as3l",ab.s3l]];
  statMap2.forEach(function(pair) { if (pair[1]) { var e=document.getElementById(pair[0]); if(e) e.textContent=pair[1]; } });
  if (ab.img) { var ai = document.getElementById("about-img"); if (ai) ai.src = ab.img; }

  D.rooms.forEach(function(r, i) {
    var j = i + 1;
    if (r.name) { var rn = document.getElementById("room" + j + "-name"); if (rn) rn.textContent = r.name; }
    if (r.desc) { var rd = document.getElementById("room" + j + "-desc"); if (rd) rd.textContent = r.desc; }
    if (r.price) {
      var pa = document.getElementById("price" + j + "-amt"); if (pa) pa.textContent = r.price;
      var pb = document.getElementById("pamt" + j);            if (pb) pb.textContent = r.price;
    }
    if (r.img) { var ri = document.getElementById("room" + j + "-img"); if (ri) ri.src = r.img; }
  });

  var ct = D.contacts;
  if (ct.tel) {
    var lt = document.getElementById("ctlph");
    if (lt) { lt.textContent = ct.tel; lt.href = "tel:" + ct.tel.replace(/\s/g,""); }
  }
  if (ct.wa) {
    var lw = document.getElementById("ctwa");
    if (lw) { lw.textContent = ct.wa; lw.href = "https://wa.me/" + ct.wa.replace(/[^0-9]/g,""); }
    WA_NUM = ct.wa.replace(/[^0-9]/g,"");
  }
  if (ct.email) {
    var le = document.getElementById("ctmail");
    if (le) { le.textContent = ct.email; le.href = "mailto:" + ct.email; }
    HTL_MAIL = ct.email;
  }
  