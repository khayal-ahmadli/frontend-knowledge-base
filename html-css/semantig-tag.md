# Semantic HTML — Fundamental Explanation

## 1. Semantic tag-lər nədir?

**Semantic tag** — adı ilə funksiyasını izah edən HTML elementidir.

**Nümunələr:**
- `<nav>` → naviqasiya üçün  
- `<footer>` → alt hissə üçün  
- `<section>` → məzmun bölməsi üçün  

### ✅ Semantic tag-lər:
`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`

### ❌ Semantic olmayanlar:
`<div>`, `<span>`, `<p>`  
(*P sadəcə paragraph elementidir, semantic məlumat daşımır.*)

---

## 2. SEO cəhətdən niyə üstündür?

Semantic tag-lər Google və digər search engine-lərə səhifənin strukturunu daha dəqiq başa düşməyə kömək edir.

### ✅ SEO faydaları:
- Google `<nav>` görüncə → menyu olduğunu anlayır  
- `<article>` → əsas məzmun hissəsi kimi qəbul olunur  
- `<section>` → məzmunun lojiq bölmələrini göstərir  
- `<header>` və `<footer>` → səhifənin başlıq və alt hissəsini bildirir  

Bu, səhifənin daha düzgün indekslənməsinə və nəticədə **ranking-in yaxşılaşmasına** səbəb olur.

---

## 3. Accessibility (a11y) üçün üstünlüklər

Ekran oxuyucular semantic tag-ləri avtomatik tanıyır və istifadəçiyə düzgün şəkildə təqdim edir.

**Misallar:**
- `<nav>` → “Navigation region”  
- `<main>` → “Main content”  
- `<footer>` → “Content info region”  

Bu, görmə məhdudiyyətli istifadəçilərin saytın strukturunu daha asan və tez başa düşməsinə imkan yaradır.

---

## 4. Browser semantic tag-ləri necə render edir?

Brauzer semantic tag-ləri vizual olaraq **div kimi** render edir, lakin onların **struktur mənasını** qoruyur.

### Yəni:
- ✅ Görünüşdə fərq yoxdur  
- ✅ Anlamsal olaraq böyük fərq var  

CSS baxımından semantic elementlər **block-level** elementlər kimi davranır.

---
