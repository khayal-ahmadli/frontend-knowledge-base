🚀 JavaScript Execution Process

JavaScript kodu iki əsas mərhələdə icra olunur:

✅ 1. Creation Phase (Yaradılma mərhələsi)  
✅ 2. Execution Phase (İcra mərhələsi)

Bu iki mərhələ Execution Context daxilində baş verir.

🎯 İlk əvvəl Execution Context nədir?

Execution Context = JS-in bir kod parçasını işlətməsi üçün yaratdığı “mühit”.

3 növ Execution Context var:

1️⃣ Global Execution Context (GEC)  
2️⃣ Function Execution Context (FEC)  
3️⃣ Eval Execution Context  

Biz əsasən GEC və FEC-i öyrənirik.

Hər dəfə funksiya çağrılanda → yeni execution context yaradılır.  
Bütün execution context-lər → call stack-ə əlavə olunur.

🔥 İndi keçək iki əsas mərhələyə:

## ✅ 1. Creation Phase (Yaradılma mərhələsi)

Bu mərhələdə JavaScript kodunuzu işləmir, sadəcə hazırlıq görür.

Bu mərhələdə JS aşağıdakıları edir:

🔹 1) Scope və dəyişənlərin siyahısını çıxarır  
🔹 2) var dəyişənlərini hoist edib → undefined edir  
🔹 3) let və const-u hoist edir → ama initialize etmir (TDZ olur)  
🔹 4) Function Declaration-ları tam şəkildə yuxarı qaldırır  
🔹 5) Lexical Environment yaradır  

**Yadda saxla:**

- var → hoist + undefined  
- let/const → hoist + TDZ  
- function declaration → tam hoist  

🧠 TDZ (Temporal Dead Zone) nədir?

let və const creation phase zamanı hoist olunur, amma dəyər verilmədiyi üçün **“ölü zona”**da olur.

Bu səbəbdən:

console.log(a);
let a = 10;

❌ Error verir. Çünki a declared olunub, amma hələ initialize edilməyib.

## ✅ 2. Execution Phase (Icra mərhələsi)

Bu mərhələdə JS artıq sətir-sətir kodu işlədir. Bu zaman:

- Dəyişənlər initialize olunur (dəyər alır)  
- Funksiyalar icra olunur  
- Hesablamalar baş verir  
- console.log, API çağırışları və s. edilir  

🔄 Execution Context Flow necə işləyir?

Aşağıdakı kodu götürək:

var a = 5;

function test() {
let b = 10;
return a + b;
}

test();

### Creation Phase:

- var a → hoist + undefined  
- function test → tam şəkildə hoist  
- test-in içində let b → hoist + TDZ  

**İndi memory-də belə görünür:**

- a → undefined  
- test → function() {...}  
- b → TDZ (function icra olunana qədər)

### Execution Phase:

- a = 5  
- test() çağrılır → yeni Function Execution Context yaranır  
- FEC-in creation phase-i baş verir  
- b hoist olunur → TDZ  
- b initialize olunur → 10  
- return a + b hesablanır  

🧾 Qısa olaraq:

### Creation Phase

- Hoisting olur  
- var → undefined  
- let/const → TDZ  
- Function declarations → tam hazırdır  
- Scope və environment yaradılır  

### Execution Phase

- Kodu sətir-sətir icra edir  
- Dəyərlər təyin olunur  
- Funksiyalar işləyir  

