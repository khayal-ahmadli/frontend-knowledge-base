# ✅ CSS Grid — Sadə və Tam İzah

**Grid = 2 ölçülü layout sistemi**  
(sətir + sütun birlikdə idarə olunur).

---

## ✅ 1. Grid sahəsinin yaradılması

Grid yaratmaq üçün parent elementə `display: grid` verilir.

**Nümunə:**
- grid-template-columns: 200px 200px 200px  
- grid-template-rows: 100px 100px

və ya nisbətlə:

- grid-template-columns: 1fr 1fr 1fr

`fr` = fractional unit → pay bölməsi

---

## ✅ 2. repeat()

**repeat(3, 1fr)** → `1fr 1fr 1fr` ilə eynidir.

Bu, kodu daha qısa və oxunaqlı edir.

---

## ✅ 3. auto-fit və auto-fill

Responsive grid düzülüşlər üçün ən mükəmməl yanaşmadır.

**Nümunə:**

grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))

- Boş yer qalırsa avtomatik əlavə sütun əlavə edir  
- Elementlər öz ölçüsünü sərbəst tənzimləyir  
- Card grid-ləri üçün ən ideal həlldir

---

## ✅ 4. Gap

Grid elementləri arasında boşluq yaratmaq üçün istifadə olunur.

- grid-gap: 20px  
- gap: 20px

Flex-dəki `gap` ilə eyni işləyir.

---
