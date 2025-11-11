# ✅ "Declared" və "Initialized" nədir?

Bunlar JavaScript-in execution prosesində dəyişənin keçdiyi iki fərqli mərhələdir.

---

## ✅ 1. Declared nədir?

**Declared = dəyişənin yaradılması (adı qeyd olunur).**  
JavaScript dəyişənin adını tanıyır, amma dəyər vermir.

**Misal:**

let a;

Burada:
- `a` declared olunub ✅  
- amma hələ dəyəri yoxdur ❌  

---

### ✅ Var/Let/Const declared necə davranır?

| Keyword | Declared olur? | Qeyd |
|--------|----------------|------|
| var    | ✅ bəli        | hoist olunur |
| let    | ✅ bəli        | hoist olunur |
| const  | ✅ bəli        | hoist olunur |

➡️ Hamısı **declared** olunur (hoist zamanı).

---

## ✅ 2. Initialized nədir?

**Initialized = dəyişənə dəyərin verilməsi.**  
Bu andan etibarən dəyişən istifadə oluna bilər.

**Misal:**

let a = 5;

Burada:
- `a` declared ✅  
- `a` initialized ✅ (dəyər aldı → 5)

---

### ✅ Var/Let/Const initialize fərqləri

| Keyword | Initialize zamanı |
|--------|-------------------|
| var    | hoist zamanı → `undefined` |
| let    | yalnız koda çatanda |
| const  | yalnız koda çatanda + dəyər məcburidir |

---

## ✅ Real fərq

### ❌ 1. TDZ (Temporal Dead Zone) nümunəsi

console.log(a); // Error — TDZ  
let a = 10;

Burada:
- `a` declared ✅ (hoist zamanı)
- amma initialized deyil ❌ → TDZ error verir

---

### ✅ 2. var nümunəsi

console.log(b); // undefined  
var b = 10;

Burada:
- `b` declared ✅  
- `b` initialized ✅ (`undefined` ilə, hoist zamanı)

---

## ✅ Çox sadə yadda saxla:

- **Declared** → dəyişənin **adı yaradılır**  
- **Initialized** → dəyişənə **dəyər verilir**  
