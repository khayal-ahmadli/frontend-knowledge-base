✅ Scope

Scope — dəyişənin harada əlçatan olduğunu göstərən sahədir.

JavaScript-də əsas üç scope tipi var:
✅ Global Scope
✅ Function Scope
✅ Block Scope

Var, let, const bu scope-larda fərqli davranır.

---

✅ 1. Global Scope

Əgər dəyişən hər hansı function və ya block xaricində yaradılıbsa → global olur.

var a = 10;
let b = 20;
const c = 30;
console.log(a, b, c); // hər yerdə görünür

Fərq burada deyil — fərq block və function-da başlayır.

---

✅ 2. Function Scope (yalnız var-da işləyir)

function test() {
  var x = 5;
  let y = 6;
  const z = 7;
}
console.log(x); // ❌ Error
console.log(y); // ❌ Error
console.log(z); // ❌ Error

let və const function scope deyil — onlar block scope-dur.
Amma function da bir block sayıldığı üçün — function daxilində onlar da kənara çıxmır.

---

✅ 3. Block Scope {}

Block → {} ilə yaradılan hər yer:
if  
for  
while  
switch  
try/catch  
sadəcə {} belə  

✅ let və const block scope-dur  
❌ var block scope deyil  

Misal:

if (true) {
  var a = 1;
  let b = 2;
  const c = 3;
}

console.log(a); // ✅ 1  
console.log(b); // ❌ Error (block scope)  
console.log(c); // ❌ Error (block scope)

Yadda saxla:
✅ let və const → blokdan çölə çıxmır  
❌ var → blokdan çölə çıxır  

---