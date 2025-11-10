# ✅ Critical Rendering Path — Sadə və Tam İzah

**Critical Rendering Path (CRP)** — brauzerin HTML, CSS və JavaScript fayllarını oxuyub **DOM ağacından ekranda görünən piksel görüntüsü yaratmaq** üçün keçdiyi bütün mərhələlərdir.

CRP nə qədər qısa və optimallaşdırılmış olarsa, səhifə o qədər tez görünür (FCP, LCP, TTI yaxşılaşır).

---

## ✅ 1. CRP hansı addımlardan ibarətdir?

1. **HTML parse edilir → DOM qurulur**  
2. **CSS yüklənir + parse edilir → CSSOM qurulur**  
3. **DOM + CSSOM birləşir → Render Tree yaradılır**  
4. **Layout (Reflow)** → elementlərin ölçü və mövqeləri hesablanır  
5. **Paint** → piksellər ekrana çəkilir  

**Qısa formul:**  
**DOM + CSSOM → Render Tree → Layout → Paint**

---

## ✅ 2. Niyə CRP vacibdir?

Çünki CRP nə qədər gec baş verərsə:

- First Paint gecikar  
- First Contentful Paint (FCP) yüksələr  
- Largest Contentful Paint (LCP) yavaşlayar  
- Sayt yüklənmə hissi zəifləyər  
- Google PageSpeed reytinqi düşər

---

## ✅ 3. CSS CRP-a necə təsir edir?

- Browser ekrana çəkmək üçün **DOM + CSSOM** lazımdır.  
- CSSOM external CSS yüklənmədən yaranmır.  
- CSSOM YOXDUR → Render Tree YOXDUR → Paint YOXDUR.  

Yəni:

**CSS gələnə qədər browser ekrana heç nə çəkə bilmir.**

---

## ✅ Inline CSS — Niyə render-blocking deyil?

✅ Inline CSS HTML ilə **birlikdə** gəlir.  
✅ Ayrı request lazım deyil.  
✅ CSSOM-un bu hissəsi dərhal hazır olur.  
✅ Browser Render Tree-ni yaratmağa mane olmur.

**Qısa:**  
**Inline CSS = render-blocking deyil.**

---

## ❌ External CSS — Niyə render-blockingdir?

👎 External CSS ayrıca **network request** tələb edir:  
1. Serverə sorğu göndərilir  
2. CSS faylı yüklənir  
3. CSS parse olunur  
4. CSSOM yaranır  

Bu vaxt boyunca:

❌ Browser Render Tree qura bilmir  
❌ Render Tree olmadıqda səhifə ekrana çəkilə bilmir  
❌ Nəticə: **Ağ ekran / gec görünmə**

**Qısa:**  
**External CSS = render-blocking resource**

---

## ✅ 4. JavaScript CRP-ə necə təsir edir?

JS həm HTML parsing-i, həm də CSS parsing-i bloklaya bilər:

- `<script>` (defer/async olmadan) → HTML parsing dayanır  
- JS CSSOM hazır olmadan işləyə bilməz → render bloklanır  

**Optimallaşdırma → async və defer.**

---

## ✅ 5. CRP optimizasiya yolları

### ✅ 1. CSS-i minify edin  
### ✅ 2. Critical CSS-i inline edin (above-the-fold content)  
### ✅ 3. JS fayllarına `async` və `defer` əlavə edin  
### ✅ 4. Render-blocking resursları azaldın  
### ✅ 5. Unused CSS və JS-i silin  
### ✅ 6. Fontları `preload` edin  
### ✅ 7. CDN və caching istifadə edin  

Bunlar CRP-i ciddi şəkildə qısaldır.

---