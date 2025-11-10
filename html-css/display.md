# ✅ CSS Display — Ən Sadə və Tam İzah

CSS-də `display` elementi səhifədə necə davrandığını müəyyən edən ən fundamental xüsusiyyətdir.

Əsas display tipləri:

- inline  
- block  
- inline-block  
- none  
- flex  
- grid  

---

## ✅ 1. display: block

- Yeni sətirdən başlayır  
- `width` default olaraq 100% olur  
- `height`, `margin`, `padding` tam işləyir  
- Ətrafındakı elementləri aşağı salır  

**Nümunələr:**  
`div`, `p`, `section`, `article`, `ul`, `ol`, `li`, `h1-h6`

---

## ✅ 2. display: inline

- Yeni sətir açmır  
- Eyni sətirdə qalır  
- `width` və `height` işləmir  
- `margin-top` və `margin-bottom` işləmir  
- Amma padding (həm üfüqi, həm də şaquli) işləyir  
- Mətn tərkibi kimi davranır  

**Nümunələr:**  
`span`, `a`, `b`, `i`, `strong`, `em`

---

## ✅ 3. display: inline-block

- Inline kimi yan-yana durur  
- Block kimi `width` və `height` qəbul edir  
- `margin-top` və `margin-bottom` işləyir  
- UI komponentləri üçün ən çox istifadə olunan display-dir  

**Misal:**  
`button`, `input`, `img` (default inline-block davranır)

---

## ✅ 4. display: none

- Element DOM-da mövcuddur  
- Amma ekranda **tamamilə görünmür**  
- Yer tutmur  

---

## ✅ 5. display: flex

Modern layout sistemidir.

Əsas xüsusiyyətlər:

- Uşaqları (children) axın yönünə görə düzür  
- Default olaraq horizontal (row) düzür  
- `justify-content` → horizontal hizalama  
- `align-items` → vertical hizalama  
- `gap` → elementlər arasında boşluq  
- `flex-wrap`, `flex-direction` və s.

Flexbox **1 ölçülü layout** üçündür (ya sıraya görə, ya sütuna görə).

---

## ✅ 6. display: grid

Grid → **2 ölçülü layout sistemidir**.

Əsas xüsusiyyətlər:

- Sətir və sütunları eyni anda idarə edir  
- `grid-template-columns`, `grid-template-rows`  
- `fr` ölçü vahidi  
- `auto-fit`, `auto-fill`  
- Kompleks layout-lar üçün ən ideal həll  

---

