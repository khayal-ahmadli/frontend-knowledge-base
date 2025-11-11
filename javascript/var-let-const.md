✅ var, let, const

JavaScript-də dəyişən yaratmağın 3 yolu var: **var, let, const**

Aralarındakı fərqlər 5 əsas mövzuda özünü göstərir:

---

## ✅ 1. Scope

- var → ✅ function scope
- let → ✅ block scope {}
- const → ✅ block scope {}

### ✅ var — function scope
if (true) {
  var a = 10;
}
console.log(a); // 10

Blokdan çölə çıxır.

### ✅ let/const — block scope
if (true) {
  let b = 20;
  const c = 30;
}
console.log(b); // Error
console.log(c); // Error

Blokdan çölə çıxmır.

---

## ✅ 2. Hoisting fərqi

Hamısı hoist olunur, amma davranış fərqlidir:

**Keyword — Hoist olunur? — Dəyəri nə olur?**
- var → ✅ Bəli → undefined
- let → ✅ Bəli → TDZ (Temporal Dead Zone)
- const → ✅ Bəli → TDZ

✅ **var = hoist + undefined** → istifadə edilə bilər  
❌ **let/const = hoist olsa da TDZ-dədir** → istifadə edilə bilməz

Misal:

console.log(a); // undefined
var a = 5;

console.log(b); // Error
let b = 10;

---

## ✅ 3. Yenidən dəyər mənimsətmə (reassign)

**Keyword — Reassign etmək olur?**
- var → ✅ Bəli
- let → ✅ Bəli
- const → ❌ Xeyr (primitive-lərdə)

let x = 5;
x = 10; // ✅

const y = 5;
y = 10; // ❌ Error

---

## ✅ 4. Yenidən deklarasiya (təkrar eyni adda dəyişən yaratmaq)

**Keyword — Redeclare?**
- var → ✅ Bəli
- let → ❌ Xeyr
- const → ❌ Xeyr

var a = 1;
var a = 2;  // ✅ allowed

let b = 1;
let b = 2;  // ❌ Error

---

## ✅ 5. const obyektləri dəyişmək olurmu?

✅ **Bəli**, const yalnız *referensi* dəyişməyə icazə vermir, amma obyektin içini dəyişmək olar:

const user = { name: "Ali" };
user.name = "Veli"; // ✅ icazəlidir

user = {}; // ❌ Error
