# ✅ CSS Pseudo-Elementlər

**Pseudo-elementlər** CSS-də elementin müəyyən bir hissəsinə xüsusi stil vermək üçün istifadə olunur.

Məsələn:
- Mətnin ilk hərfini, ilk sətrini, seçilmiş hissəsini və ya elementdən əvvəl/sonra yaradılan virtual content-i idarə etmək üçün.

---

## ✅ 1. Əsas Pseudo-Elementlər

| Pseudo-element | İzah |
|----------------|------|
| `::before` | Elementin **içindən, əvvəlində** virtual content yaradır |
| `::after` | Elementin **içindən, sonunda** virtual content yaradır |
| `::first-letter` | Mətnin yalnız **ilk hərfini** hədəfləyir |
| `::first-line` | Mətnin yalnız **ilk sətrini** hədəfləyir |
| `::selection` | İstifadəçi mətni **seçəndə** (highlight edəndə) stil tətbiq edir |
| `::placeholder` | Input-un **placeholder** mətninə stil verir |
| `::marker` | List elementlərinin (ul, ol) **marker** hissəsini (bullet, number) stil edir |
| `::backdrop` | Modal, fullscreen və ya dialog arxasındakı **fonu** hədəfləyir |

---

## ✅ 2. `::before` və `::after` — Ən çox istifadə olunanlar

Bu pseudo-elementlər **content** xüsusiyyətinə əsaslanır.

```css
.card::before {
  content: "🔥 ";
  color: red;
}

.card::after {
  content: " ✅";
  color: green;
}
