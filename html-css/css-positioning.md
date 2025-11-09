# CSS Positioning

## 1. Position nədir?

CSS-də `position` elementin səhifədə necə yerləşəcəyini müəyyən edir.  
5 əsas növü var:

- static  
- relative  
- absolute  
- fixed  
- sticky  

---

## 2. position: static (default)

- Bütün elementlərin default position dəyəridir.  
- `top`, `left`, `right`, `bottom` işləmir.  
- Element səhifənin normal axınına uyğun yerləşir.  
- Heç yerə tərpənmir.

---

## 3. position: relative

- Element normal yerində qalır.  
- Amma vizual olaraq `top`, `left`, `right`, `bottom` ilə öz yerindən tərpədilə bilər.  
- **Absolute** elementlər üçün referans (parent) ola bilər.

**Yəni:**  
Element yerindədir → sadəcə görünüşdə sürüşür.

---

## 4. position: absolute

- Element normal axından çıxır (sanki görünməz olur).  
- Özünü **position verilmiş parentə görə** yerləşdirir.

### Hansı parentə görə?

- Əgər parent-də `position: relative`, `absolute`, `fixed` varsa → **ona görə**  
- Heç bir positioned parent yoxdursa → **body-yə görə**

Bu, müsahibədə ən çox soruşulan sualdır.

---

## 5. position: fixed

- Element **ekrana (viewport)** sabitlənir.  
- Səhifə scroll olsa belə yerindən tərpənmir.  
- Navbar, chat bubble, “back to top” button üçün istifadə olunur.

---

## 6. position: sticky

- `relative` + `fixed` davranışının qarışığıdır.  
- Element normalda `relative` kimidir.  
- Scroll müəyyən bir nöqtəyə çatanda `fixed` olur.

Misal:  
`position: sticky; top: 0;`

**Sticky işləməsi üçün vacib şərt:**  
Parent-də `overflow: hidden;` olmamalıdır.

---

## 7. z-index hansı position-larla işləyir?

`z-index` yalnız **positioned** elementlərdə işləyir:

- relative  
- absolute  
- fixed  
- sticky  

Static elementdə `z-index` işləmir.

---

## 8. Qısa xülasə

| Position | Axından çıxır? | Parentə görə yönlənmə | Scroll davranışı |
|----------|----------------|-------------------------|------------------|
| static   | Xeyr           | Yox                     | Normal           |
| relative | Xeyr           | Yox                     | Normal           |
| absolute | ✅ Bəli        | Positioned parent       | Normal           |
| fixed    | ✅ Bəli        | Viewport                | Sabit qalır      |
| sticky   | Xeyr → Bəli    | Scroll limitinə görə    | Yapışır          |

---
