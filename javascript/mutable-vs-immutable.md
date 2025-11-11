# ✅ JavaScript-də Mutable vs Immutable — Sadə və Tam İzah

JavaScript-də data type-lar iki kateqoriyaya bölünür:

✅ **Immutable (dəyişdirilə bilməz)**  
✅ **Mutable (dəyişdirilə bilən)**

Bu anlayış **dəyərin dəyişdirilməsi** ilə bağlıdır, **dəyişənin yox**.

---

# ✅ 1. Immutable Types — Dəyər dəyişmir

**Primitive type-lar immutable-dır:**
- string  
- number  
- boolean  
- null  
- undefined  
- symbol  
- bigint  

### ✅ İzah:
Primitive dəyəri dəyişdiyini düşündüyün vaxt əslində **yeni dəyər yaranır**, köhnə dəyər dəyişmir.

### ✅ Misal:
let a = "Ali";
a = "Veli";

➡️ Burada “Ali” dəyəri dəyişmir, sadəcə `a` başqa dəyərə işarə edir.  
➡️ Primitive-lər **immutable**-dır.

---

# ✅ 2. Mutable Types — Dəyər dəyişir

**Reference type-lar mutable-dır:**
- object  
- array  
- function  
- map, set  

### ✅ İzah:
Bu dəyərlərin **içini dəyişmək olur**, çünki referans eyni qalır.

### ✅ Misal:
const user = { name: "Ali" };
user.name = "Veli"; // ✅ icazəli

➡️ Obyektin içi dəyişir → çünki reference type **mutable**-dır.

---

# ✅ Mutable / Immutable Qısa Təsvir

| Tip | Mutable? | Misallar |
|-----|----------|----------|
| Primitive | ❌ Immutable | number, string, boolean |
| Reference | ✅ Mutable | object, array, function |

---

# ✅ Niyə Vacibdir?

### ✅ 1. Bug-ların qarşısını alır
Mutable obyektlər paylaşılarsa → bir yerdə dəyişiklik başqa yerdə də görünür.

### ✅ 2. React-də State idarəsi
React state **immutable olmalıdır**.

❌ Səhv:
state.user.name = "Ali";

✅ Düzgün:
setState({ ...state, user: { ...state.user, name: "Ali" }});

### ✅ 3. Pure functions
Functional programming → immutable data üstünlük verir.

---

# ✅ Ən Sadə Yadda Saxlama Qaydası

- **Primitive** → daş kimidir → forması dəyişməz  
- **Object** → plastilin kimidir → içi dəyişdirilə bilər  
