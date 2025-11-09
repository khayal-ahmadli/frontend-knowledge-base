1. Semantic tag-lər nədir?
Semantic tag — adı ilə funksiyasını izah edən HTML elementidir.
Məsələn:
•	<nav> → naviqasiya üçün
•	<footer> → alt hissə üçün
•	<section> → məzmun bölməsi üçün
✅ Semantic tag-lər:
<header>, <nav>, <main>, <section>, <article>, <aside>, <footer>
❌ Semantic olmayanlar:
<div>, <span>, <p> (p sadəcə paragraph tag-dır, semantic deyil)


2. SEO cəhətdən niyə üstündür?
Semantic tag-lər Google-a və digər search engine-lərə səhifənin strukturunu daha yaxşı başa düşməyə kömək edir.
SEO faydası:
•	Google <nav> görüncə bilir ki burası menyudur
•	<article> məzmunun əsas hissəsi kimi qəbul olunur
•	<section> səhifənin lojiq bölmələrini göstərir
•	<header> və <footer> səhifənin global və lokal başlıq hissələrini göstərir
Bu, Google-ın səhifəni daha düzgün indeksləməsinə, nəticədə isə ranking-in yaxşılaşmasına səbəb olur.

3. Accessibility (a11y) üçün üstünlüklər
Ekran oxuyucular semantic tag-ləri avtomatik tanıyır. Məsələn:
•	<nav> → “Navigation region” deyir
•	<main> → “Main content” deyir
•	<footer> → “Content info region” deyir
Bu, görmə məhdudiyyətli insanların saytın strukturunu daha tez anlamasına kömək edir.

4. Browser semantic tag-ləri necə render edir?
Browser semantic tag-ləri div kimi render edir, amma əlavə olaraq struktur anlamını saxlayır.
Yəni:
•	Görünüşdə fərq yoxdur
•	Anlamsal olaraq fərq böyükdür
CSS baxımından da semantic tag-lər sadəcə blok-level elementlər kimidir.
