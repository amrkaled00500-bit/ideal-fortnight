ا
html_code = '''<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>AMB - المهندس عمرو خالد عمارة</title>
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
:root{--bg:#0b0f17;--card:#111827;--input:#1a2233;--blue:#00a8ff;--blue-glow:rgba(0,168,255,0.15);--green:#25d366;--green-dark:#1da851;--green-glow:rgba(37,211,102,0.2);--text:#ffffff;--text2:#94a3b8;--muted:#64748b;--border:#1e293b;}
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent;}
body{font-family:'Cairo',sans-serif;background:#000;display:flex;justify-content:center;align-items:center;min-height:100vh;padding:0;overflow:hidden;}
.phone{width:100%;max-width:420px;height:100vh;max-height:900px;background:var(--bg);overflow:hidden;position:relative;box-shadow:0 0 60px rgba(0,168,255,0.1),0 20px 60px rgba(0,0,0,0.8);border:1px solid var(--border);}
@media(min-width:440px){.phone{border-radius:40px;height:812px;}}
.status{height:44px;display:flex;align-items:center;justify-content:space-between;padding:0 24px;color:#fff;font-size:14px;font-weight:600;position:relative;z-index:100;}
.status-r{display:flex;gap:6px;align-items:center;}
.page{position:absolute;top:44px;left:0;right:0;bottom:70px;overflow-y:auto;overflow-x:hidden;opacity:0;pointer-events:none;transform:translateX(30px);transition:all .35s cubic-bezier(.4,0,.2,1);padding:0 16px 20px;}
.page::-webkit-scrollbar{display:none;}
.page.active{opacity:1;pointer-events:all;transform:translateX(0);}
.page.exit{opacity:0;transform:translateX(-30px);}
.ph{display:flex;align-items:center;justify-content:center;height:52px;position:relative;margin-bottom:8px;}
.back{position:absolute;right:0;top:50%;transform:translateY(-50%);width:36px;height:36px;display:flex;align-items:center;justify-content:center;color:#fff;font-size:20px;cursor:pointer;border-radius:10px;transition:background .2s;}
.back:hover{background:rgba(255,255,255,.05);}
.pt{font-size:17px;font-weight:700;color:#fff;}
.ps{text-align:center;color:var(--blue);font-size:12px;font-weight:600;margin-bottom:20px;}

/* Home */
.ht{display:flex;align-items:center;justify-content:space-between;padding:8px 4px 16px;}
.hb{background:none;border:none;color:#fff;cursor:pointer;padding:4px;}
.lb{background:linear-gradient(135deg,#0a1628,#0d1f3c);border:2px solid var(--blue);border-radius:14px;padding:10px 28px;box-shadow:0 0 20px rgba(0,168,255,.2),inset 0 1px 0 rgba(255,255,255,.05);}
.lt{font-size:26px;font-weight:900;color:#fff;letter-spacing:2px;text-shadow:0 0 10px rgba(0,168,255,.5);}
.htl{text-align:center;margin-top:12px;}
.htl h1{font-size:18px;font-weight:800;color:#fff;line-height:1.4;}
.htl p{font-size:13px;color:var(--blue);font-weight:600;margin-top:4px;}

/* Cards */
.sc{background:linear-gradient(135deg,#0f1724,#141d2e);border:1px solid var(--border);border-radius:16px;padding:16px;display:flex;align-items:center;justify-content:space-between;margin-bottom:12px;cursor:pointer;transition:all .25s;position:relative;overflow:hidden;}
.sc::before{content:'';position:absolute;top:0;left:0;right:0;height:1px;background:linear-gradient(90deg,transparent,rgba(0,168,255,.3),transparent);}
.sc:hover{border-color:rgba(0,168,255,.3);transform:translateY(-1px);box-shadow:0 8px 30px rgba(0,0,0,.4);}
.sci{flex:1;}
.sc h3{font-size:15px;font-weight:700;color:#fff;margin-bottom:4px;display:flex;align-items:center;gap:6px;}
.dp{width:7px;height:7px;background:var(--blue);border-radius:50%;box-shadow:0 0 8px var(--blue);animation:pulse 2s infinite;}
@keyframes pulse{0%,100%{opacity:1;transform:scale(1);}50%{opacity:.5;transform:scale(.8);}}
.sc p{font-size:11px;color:var(--text2);line-height:1.5;}
.sc img{width:60px;height:60px;border-radius:12px;object-fit:cover;margin-right:12px;border:1px solid rgba(0,168,255,.15);}

.cc{background:linear-gradient(135deg,#0a1628,#0d1f3c);border:1px solid rgba(0,168,255,.15);border-radius:16px;padding:18px;margin-top:8px;margin-bottom:16px;display:flex;align-items:center;gap:14px;cursor:pointer;}
.cci{width:56px;height:56px;border-radius:14px;background:linear-gradient(135deg,rgba(0,168,255,.1),rgba(0,168,255,.05));border:1px solid rgba(0,168,255,.2);display:flex;align-items:center;justify-content:center;flex-shrink:0;}
.cc h3{font-size:15px;font-weight:700;color:#fff;margin-bottom:3px;}
.cc p{font-size:11px;color:var(--text2);}

.wb{width:100%;background:linear-gradient(135deg,var(--green),var(--green-dark));border:none;border-radius:14px;padding:14px 20px;color:#fff;font-family:'Cairo',sans-serif;font-size:14px;font-weight:700;cursor:pointer;display:flex;align-items:center;justify-content:center;gap:10px;box-shadow:0 4px 20px var(--green-glow),0 2px 8px rgba(0,0,0,.3);transition:all .2s;margin-bottom:12px;}
.wb:hover{transform:translateY(-2px);box-shadow:0 6px 28px var(--green-glow),0 4px 12px rgba(0,0,0,.3);}
.wb svg{width:22px;height:22px;}

/* Nav */
.bn{position:absolute;bottom:0;left:0;right:0;height:70px;background:linear-gradient(180deg,transparent 0%,var(--bg) 20%);backdrop-filter:blur(20px);display:flex;justify-content:space-around;align-items:center;border-top:1px solid var(--border);z-index:100;}
.ni{display:flex;flex-direction:column;align-items:center;gap:4px;cursor:pointer;padding:8px 12px;border-radius:12px;transition:all .2s;color:var(--muted);}
.ni.active{color:var(--blue);}
.ni:hover{color:#fff;}
.ni svg{width:22px;height:22px;}
.ni span{font-size:10px;font-weight:600;}

/* Service list */
.sli{background:linear-gradient(135deg,#0f1724,#141d2e);border:1px solid var(--border);border-radius:14px;padding:16px 18px;display:flex;align-items:center;justify-content:space-between;margin-bottom:10px;cursor:pointer;transition:all .2s;}
.sli:hover{border-color:rgba(0,168,255,.2);}
.sli h4{font-size:14px;font-weight:700;color:#fff;}
.sli p{font-size:11px;color:var(--text2);margin-top:2px;}
.slic{width:44px;height:44px;border-radius:10px;background:rgba(0,168,255,.08);border:1px solid rgba(0,168,255,.15);display:flex;align-items:center;justify-content:center;color:var(--blue);}
.slic svg{width:22px;height:22px;}

/* Form */
.fg{margin-bottom:12px;}
.fl{display:flex;align-items:center;gap:8px;margin-bottom:8px;color:var(--text2);font-size:12px;font-weight:600;}
.fl svg{width:16px;height:16px;color:var(--muted);}
.fi,.fs,.ft{width:100%;background:var(--input);border:1px solid var(--border);border-radius:12px;padding:14px 16px;color:#fff;font-family:'Cairo',sans-serif;font-size:13px;outline:none;transition:all .2s;}
.fi:focus,.fs:focus,.ft:focus{border-color:var(--blue);box-shadow:0 0 0 3px var(--blue-glow);}
.fi::placeholder{color:var(--muted);}
.fs{appearance:none;cursor:pointer;}
.fs option{background:var(--bg);color:#fff;}
.ft{min-height:90px;resize:none;}
.sw{position:relative;}
.sw::after{content:'▼';position:absolute;left:16px;top:50%;transform:translateY(-50%);color:var(--muted);font-size:10px;pointer-events:none;}

/* Timeline */
.tl{padding:10px 8px;}
.ti{display:flex;gap:14px;position:relative;padding-bottom:24px;}
.ti:last-child{padding-bottom:0;}
.ti:not(:last-child)::before{content:'';position:absolute;right:15px;top:32px;bottom:0;width:2px;background:linear-gradient(180deg,var(--blue),transparent);opacity:.3;}
.td{width:32px;height:32px;border-radius:50%;display:flex;align-items:center;justify-content:center;flex-shrink:0;z-index:2;position:relative;}
.td.d{background:linear-gradient(135deg,var(--green),var(--green-dark));box-shadow:0 0 12px var(--green-glow);}
.td.a{background:linear-gradient(135deg,var(--blue),#0077cc);box-shadow:0 0 15px rgba(0,168,255,.4);animation:gp 2s infinite;}
@keyframes gp{0%,100%{box-shadow:0 0 15px rgba(0,168,255,.4);}50%{box-shadow:0 0 25px rgba(0,168,255,.7);}}
.td.p{background:var(--input);border:2px solid var(--border);}
.tc h4{font-size:14px;font-weight:700;color:#fff;margin-bottom:3px;}
.tc p{font-size:11px;color:var(--text2);}

/* About */
.al{text-align:center;margin:8px 0 20px;}
.al .lb{display:inline-block;margin-bottom:12px;}
.al h2{font-size:17px;font-weight:800;color:#fff;}
.al p{font-size:12px;color:var(--blue);font-weight:600;margin-top:4px;}
.fc{background:linear-gradient(135deg,#0f1724,#141d2e);border:1px solid var(--border);border-radius:14px;padding:16px;display:flex;align-items:center;gap:14px;margin-bottom:10px;}
.fi2{width:44px;height:44px;border-radius:12px;background:rgba(0,168,255,.08);border:1px solid rgba(0,168,255,.15);display:flex;align-items:center;justify-content:center;color:var(--blue);flex-shrink:0;}
.fi2 svg{width:22px;height:22px;}
.fc p{font-size:13px;font-weight:600;color:#fff;}

/* Terms */
.tr{padding:8px 4px;}
.ti2{display:flex;align-items:flex-start;gap:10px;margin-bottom:16px;padding-right:4px;}
.tb{width:6px;height:6px;background:var(--blue);border-radius:50%;margin-top:8px;flex-shrink:0;box-shadow:0 0 6px var(--blue);}
.ti2 p{font-size:13px;color:var(--text2);line-height:1.7;}
.ti2 p strong{color:#fff;font-weight:700;}
.ab{width:100%;background:linear-gradient(135deg,var(--green),var(--green-dark));border:none;border-radius:14px;padding:14px 20px;color:#fff;font-family:'Cairo',sans-serif;font-size:14px;font-weight:700;cursor:pointer;display:flex;align-items:center;justify-content:center;gap:10px;box-shadow:0 4px 20px var(--green-glow);transition:all .2s;margin-top:8px;}
.ab:hover{transform:translateY(-2px);}

/* Contact */
.ct{text-align:center;padding-top:40px;}
.wbi{width:100px;height:100px;margin:0 auto 24px;background:linear-gradient(135deg,var(--green),var(--green-dark));border-radius:24px;display:flex;align-items:center;justify-content:center;box-shadow:0 0 40px var(--green-glow),0 8px 30px rgba(0,0,0,.3);}
.wbi svg{width:52px;height:52px;}
.ct h3{font-size:16px;font-weight:700;color:#fff;margin-bottom:4px;}
.ct p{font-size:13px;color:var(--text2);margin-bottom:24px;}
.pn{font-size:20px;font-weight:800;color:var(--green);direction:ltr;display:inline-flex;align-items:center;gap:8px;margin-top:8px;}
.pl{font-size:12px;color:var(--muted);margin-top:16px;}

/* Success */
.su{text-align:center;padding-top:60px;}
.sc2{width:100px;height:100px;margin:0 auto 28px;border-radius:50%;background:linear-gradient(135deg,rgba(37,211,102,.1),rgba(37,211,102,.05));border:2px solid var(--green);display:flex;align-items:center;justify-content:center;box-shadow:0 0 40px var(--green-glow);}
.sc2 svg{width:48px;height:48px;color:var(--green);}
.su h2{font-size:20px;font-weight:800;color:#fff;margin-bottom:10px;}
.su p{font-size:13px;color:var(--text2);line-height:1.7;margin-bottom:32px;}
</style>
</head>
<body>
<div class="phone" id="app">
<div class="status"><span>12:30</span><div class="status-r"><svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/></svg><svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M1 9l2 2c4.97-4.97 13.03-4.97 18 0l2-2C16.93 2.93 7.08 2.93 1 9zm8 8l3 3 3-3c-1.65-1.66-4.34-1.66-6 0zm-4-4l2 2c2.76-2.76 7.24-2.76 10 0l2-2C15.14 9.14 8.87 9.14 5 13z"/></svg><svg width="20" height="12" viewBox="0 0 24 12" fill="currentColor"><rect x="2" y="2" width="18" height="8" rx="2" stroke="currentColor" stroke-width="2" fill="none"/><rect x="4" y="4" width="14" height="4" rx="1" fill="currentColor"/></svg></div></div>

<!-- PAGE 1: HOME -->
<div class="page active" id="p-home">
<div class="ht"><button class="hb" onclick="go('terms')"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><line x1="3" y1="6" x2="21" y2="6"/><line x1="3" y1="12" x2="21" y2="12"/><line x1="3" y1="18" x2="21" y2="18"/></svg></button><div class="lb"><span class="lt">AMB</span></div><button class="hb" onclick="go('contact')"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 8A6 6 0 0 0 6 8c0 7-3 9-3 9h18s-3-2-3-9"/><path d="M13.73 21a2 2 0 0 1-3.46 0"/></svg></button></div>
<div class="htl"><h1>المهندس عمرو خالد عمارة</h1><p>لصيانة الثلاجات والغسالات فقط</p></div>
<div style="margin-top:20px;">
<div class="sc" onclick="go('fridge')"><div class="sci"><h3>صيانة ثلاجات <span class="dp"></span></h3><p>ثلاجات نوفروست، ديفروست، سايد باي سايد، عرض</p></div><img src="https://images.unsplash.com/photo-1571175443880-49e1d58b794a?w=120&h=120&fit=crop" alt="ثلاجة"></div>
<div class="sc" onclick="go('washer')"><div class="sci"><h3>صيانة غسالات <span class="dp"></span></h3><p>غسالات أوتوماتيك، فوق أوتوماتيك، أطباق</p></div><img src="https://images.unsplash.com/photo-1626806775351-538068a21838?w=120&h=120&fit=crop" alt="غسالة"></div>
<div class="cc" onclick="go('contact')"><div class="cci"><svg viewBox="0 0 24 24" fill="none" stroke="#00a8ff" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg></div><div><h3>تواصل معنا</h3><p>جميع المعلومات والحجوزات على واتساب</p></div></div>
<button class="wb" onclick="wa()"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>استفسار عبر واتساب</button>
</div></div>

<!-- PAGE 2: FRIDGE -->
<div class="page" id="p-fridge">
<div class="ph"><div class="back" onclick="go('home')">›</div><span class="pt">صيانة الثلاجات</span></div>
<p class="ps">نقدم جميع خدمات صيانة الثلاجات</p>
<div class="sli"><div><h4>ثلاجات نوفروست</h4><p>صيانة جميع الأعطال</p></div><div class="slic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="4" y="2" width="16" height="20" rx="2"/><line x1="4" y1="10" x2="20" y2="10"/></svg></div></div>
<div class="sli"><div><h4>ثلاجات ديفروست</h4><p>صيانة جميع الأعطال</p></div><div class="slic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="4" y="2" width="16" height="20" rx="2"/><circle cx="12" cy="14" r="2"/></svg></div></div>
<div class="sli"><div><h4>ثلاجات سايد باي سايد</h4><p>صيانة جميع الأعطال</p></div><div class="slic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="3" width="9" height="18" rx="1"/><rect x="13" y="3" width="9" height="18" rx="1"/></svg></div></div>
<div class="sli"><div><h4>ثلاجات عرض</h4><p>صيانة جميع الأعطال</p></div><div class="slic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="4" width="18" height="16" rx="1"/><line x1="3" y1="10" x2="21" y2="10"/></svg></div></div>
<button class="wb" style="margin-top:8px;" onclick="wa()"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>احجز الآن عبر واتساب</button>
</div>

<!-- PAGE 3: WASHER -->
<div class="page" id="p-washer">
<div class="ph"><div class="back" onclick="go('home')">›</div><span class="pt">صيانة الغسالات</span></div>
<p class="ps">نقدم جميع خدمات صيانة الغسالات</p>
<div class="sli"><div><h4>غسالات أوتوماتيك</h4><p>صيانة جميع الأعطال</p></div><div class="slic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="3" width="18" height="20" rx="2"/><circle cx="12" cy="13" r="4"/><path d="M12 3v3"/></svg></div></div>
<div class="sli"><div><h4>غسالات فوق أوتوماتيك</h4><p>صيانة جميع الأعطال</p></div><div class="slic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="4" y="6" width="16" height="14" rx="2"/><line x1="4" y1="11" x2="20" y2="11"/></svg></div></div>
<div class="sli"><div><h4>غسالات أطباق</h4><p>صيانة جميع الأعطال</p></div><div class="slic"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="4" width="18" height="16" rx="1"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="7" y1="4" x2="7" y2="9"/><line x1="17" y1="4" x2="17" y2="9"/></svg></div></div>
<button class="wb" style="margin-top:8px;" onclick="wa()"><svg viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>احجز الآن عبر واتساب</button>
</div>

<!-- PAGE 4: REQUEST -->
<div class="page" id="p-request">
<div class="ph"><div class="back" onclick="go('home')">›</div><span cla
