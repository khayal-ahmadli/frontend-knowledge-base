# ✅ CSS Flexbox — Sadə və Tam İzah

**Flexbox = 1 ölçülü layout sistemi**  
(ya yatay — row, ya da şaquli — column istiqamətində düzülüş üçün).

Flexbox parent elementə `display: flex` tətbiq olunur və içindəki bütün children-lər flex item olur.

---

## ✅ 1. Flex istiqaməti (flex-direction)

**flex-direction:**
- row  *(default)*
- column
- row-reverse
- column-reverse

**row** → elementlər soldan sağa  
**column** → yuxarıdan aşağı

---

## ✅ 2. Horizontal hizalama (justify-content)

**justify-content:**
- center
- space-between
- space-around
- space-evenly

Row → soldan-sağa hizalayır  
Column → yuxarıdan-aşağı hizalayır

---

## ✅ 3. Vertical hizalama (align-items)

**align-items:**
- center
- flex-start
- flex-end
- stretch *(default)*

Row → yuxarı / aşağı hizalayır.

---

## ✅ 4. Sətirləmə (flex-wrap)

Default olaraq bütün flex elementləri **bir sətirə** yığılır.

**flex-wrap:**
- wrap
- nowrap

✅ *wrap* → elementlər yer çatmayanda aşağı keçir.

---

## ✅ 5. Item səviyyəsində idarəetmə

**flex-grow:** boş yeri paylaşır  
**flex-shrink:** sıxıldıqda büzülür  
**flex-basis:** ilkin ölçünü təyin edir

**Shorthand nümunələri:**
- flex: 1
- flex: 1 0 200px

---

## ✅ Flexbox nə üçün idealdır?

- Navbar
- Menü
- Card-lar
- Sadə layout-lar
- Row/column düzülüşləri
- Bir ölçü üzrə hizalama problemləri
- Mobil adaptasiya (responsive)

---

## ✅ Flexbox-un məhdudiyyəti

Flex yalnız **1 ölçünü** idarə edir:
- ya yatay
- ya şaquli

Mürəkkəb **2D layout** üçün **CSS Grid** daha uyğundur.
