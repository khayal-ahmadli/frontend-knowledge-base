# ✅ LocalStorage, SessionStorage, Cookies

---

## ✅ 1. localStorage nədir?

- Brauzerdə məlumat saxlamaq üçündür.  
- Məlumat **brauzer bağlansa belə silinmir**.  
- Yalnız **eyni domain** daxilində əlçatan olur.  

**Storage limiti:** ~5–10 MB  

**İstifadə nümunələri:**
- Tema seçimi (dark/light)
- User settings
- Cart məlumatları
- Language seçimi

---

## ✅ 2. sessionStorage nədir?

- localStorage kimidir, amma **oturum (session) bitən kimi silinir**.  
- Tab bağlananda məlumat silinir.  
- Tablar arasında paylaşılmır.  

**Storage limiti:** ~5 MB  

**İstifadə nümunələri:**
- Form doldurarkən müvəqqəti məlumat
- Step-by-step wizard state
- Yeniləməyə davam edən, amma tab bağlananda yox olmalı data

---

## ✅ 3. Cookies nədir?

- Məlumat brauzerdə saxlanır və **hər request ilə serverə göndərilir** ✅  
- Expire vaxtı var (1 gün, 1 ay, 1 il və s.)  
- Security flag-ları mövcuddur:

**Security xüsusiyyətləri:**
- **HttpOnly** — JS oxuya bilmir (XSS-dən qoruyur)
- **Secure** — yalnız HTTPS-də işləyir
- **SameSite** — CSRF-dən qorunma

**Storage limiti:** ~4 KB (çox az)

**İstifadə nümunələri:**
- Authentication token (HttpOnly cookie)
- User tracking (analytics)
- “Remember me”
- Server-side session idarəsi

---

# ✅ Əsas fərqlər — Yadda Saxlamaq üçün Tabloda

| Xüsusiyyət | localStorage | sessionStorage | Cookies |
|-----------|--------------|----------------|---------|
| Saxlanma müddəti | Sonsuz (silənə kimi) | Tab bağlanan kimi silinir | Expire tarixinə bağlı |
| Storage limiti | ~5–10 MB | ~5 MB | ~4 KB |
| Hər request ilə serverə gedir? | ❌ Yox | ❌ Yox | ✅ Bəli |
| Domain-ə bağlılıq | ✅ Bəli | ✅ Bəli | ✅ Bəli |
| Təhlükəsizlik | Orta | Orta | Çox (HttpOnly + Secure) |
| Əsas istifadə | UI məlumatları | Session məlumatı | Auth, tracking |

---
