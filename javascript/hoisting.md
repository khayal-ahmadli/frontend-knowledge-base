🚀 Hoisting — JavaScript-in gizli mexanizmi

Hoisting = JavaScript-in kodu icra etməzdən əvvəl dəyişənləri və funksiyaları yaddaşa əvvəlcədən yerləşdirməsi. Bu proses Creation Phase zamanı baş verir.

🎯 Hoisting nə edir?

🧪 Misallar ilə Hoisting

---

### 1) var → hoist + undefined

```js
console.log(a); 
var a = 10;
```

Hoisting sonrası JS bunu belə görür:

```js
var a;
console.log(a); // undefined
a = 10;
```

---

### let / const → hoist olunur, amma initialize olunmur

```js
console.log(b);
let b = 20;
```

❌ Error verir, undefined deyil. Çünki TDZ (Temporal Dead Zone) var.

```js
// b hoist olunur, amma initialize olunmur → TDZ
console.log(b); // Error
let b = 20;     // initialize burda olur
```

---

### Function Declaration → tam şəkildə hoist olunur

```js
sayHi(); // işləyəcək

function sayHi() {
  console.log("Hello");
}
```

JS bunu belə görür:

```js
function sayHi() { console.log("Hello"); }
sayHi();
```

---

### Function Expression → hoist olunur, amma var/let kimi davranır

#### var ilə:

```js
sayHi();  
var sayHi = function() {
  console.log("Hello");
};
```

Burda error YOX, amma undefined olacaq:

```js
var sayHi; // undefined
sayHi();   // TypeError: sayHi is not a function
sayHi = function(){};
```

#### let ilə:

```js
sayHi();  
let sayHi = function() {};
```

❌ TDZ → ReferenceError.

---

### 🧠 Hoisting niyə lazımdır?

Çünki JavaScript iki mərhələdə işləyir:

1️⃣ Creation Phase → hoisting burada olur  
2️⃣ Execution Phase → kod sətir-sətir işləyir  

Hoisting yaratma mərhələsinin təbii nəticəsidir.

---

### 🔥 Ən çox edilən səhvlər

❌ “let və const hoist olunmur” — Bu səhvdir.  
✔️ let/const da hoist olunur, ❌ amma initialize olunmur (TDZ).  

❌ “var daha yaxşıdır çünki error vermir” — Bu təhlükəli fikirdir.  
var-ın undefined olması çox bug yaradır. let/const isə bugdan qoruyur.

---

## ❓ Sual

### Variable-lər declaration olanda hoist olunur?

Bəli, bütün variable-lər — var, let, const — hoist olunur.

Amma:

- var hoist olunur və initialize olunur → undefined  
- let & const hoist olunur amma initialize olunmur → TDZ  

📌 Yəni fərq `hoist` olunub-olunmamaqda deyil,  
**fərq `initialize` olunub-olunmamaqdadır.**
