# ✅ Temporal Dead Zone (TDZ)

**Temporal Dead Zone (TDZ)** — JavaScript-də `let` və `const` dəyişənlərinin **declared (yaradıldığı)** sətrə çatana qədər **istifadə edilə bilmədiyi zaman aralığıdır**.

Bu dövrə “temporal” (zamansal) deyilir, çünki kodun müəyyən bir məqamına qədər dəyişən mövcud olsa da, əlçatan deyil.

---

## ✅ TDZ nə deməkdir?

console.log(a); // ❌ Error — TDZ
let a = 10;

Burada:
- `a` hoist olunub ✅  
- amma initialize edilməyib ❌  
- initialize sətirinə qədər olan müddət → **TDZ**

---

## ✅ Var-da niyə TDZ yoxdur?

Çünki `var` hoist olunduqda **undefined ilə initialize olunur**.

console.log(a); // ✅ undefined
var a = 10;

✅ Buna görə `var` üçün TDZ YOXDUR.

---

## ✅ Let və const niyə TDZ-də olur?

Çünki:
- `let` və `const` hoist olunur ✅  
- amma **undefined ilə initialize edilmir** ❌  
- initialize sətirinə qədər akses → **ReferenceError**

---

## ✅ TDZ necə işləyir? (addım-addım)

console.log(x); // ❌ TDZ
let x = 5;

1. JS kodu scan edir → `let x` var  
2. Hoist olunur (amma initialize edilmir)  
3. İlk sətirdə `console.log(x)`  
4. Nəticə → **ReferenceError: Cannot access 'x' before initialization**

Bu dövrə → **Temporal Dead Zone**

---

## ✅ TDZ yalnız let/const üçün deyil

Function parametrlərində də TDZ olur:

function test(a = b, b = 10) {
  console.log(a, b);
}

test(); // ❌ ReferenceError

Çünki `a = b` olduğu anda `b` hələ initialize edilməyib.

---

## ✅ Müsahibəlik ən sadə cavab:

**TDZ = dəyişən hoist olsa da, initialize olunana qədər əlçatan olmadığı zaman aralığıdır.**

---

## ✅ TDZ nə üçün lazımdır?

- Təhlükəsiz code üçün  
- Undefined səhvlərini azaltmaq üçün  
- let/const-un block scoped davranışını təmin edir  
- const-un mütləq initialize tələb etməsi üçün  

---

## ✅ 10 saniyəyə TDZ yadda saxlamaq:

- ✅ `var` → hoist + undefined → **TDZ YOX**  
- ✅ `let` → hoist + no init → **TDZ VAR**  
- ✅ `const` → hoist + no init → **TDZ VAR + init məcburidir**  
