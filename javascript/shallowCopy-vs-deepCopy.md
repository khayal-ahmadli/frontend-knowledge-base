# ✅ Shallow Copy vs Deep Copy — Sadə və Tam İzah

## ✅ Shallow Copy nədir?

**Shallow copy** — obyektin yalnız *üst səviyyəsini* kopyalayır.  
Nested (iç-içə) obyektlər isə **kopyalanmır**, onların referansı eyni qalır.

### ✅ Nəticə:
- Üst səviyyə bağımsızdır  
- İç obyektlər **eyni referansı paylaşır**  
- Birində dəyişiklik → digərinə də təsir edir

### ✅ Misal:
const user1 = { 
  name: "Khayal",
  address: { city: "Baku" }
};

const user2 = { ...user1 }; // shallow copy

user2.address.city = "Ganja";

console.log(user1.address.city); // "Ganja"

---

## ✅ Deep Copy nədir?

**Deep copy** — obyektin bütün səviyyələrini *tam kopyalayır*.  
Nested obyektlər də ayrıca yaradılır → tamamilə bağımsız olur.

### ✅ Nəticə:
- Tam müstəqil obyekt  
- Birində dəyişiklik → digərini təsir etmir

### ✅ Misal:
const user1 = { 
  name: "Khayal",
  address: { city: "Baku" }
};

const user2 = structuredClone(user1); // deep copy

user2.address.city = "Ganja";

console.log(user1.address.city); // "Baku"
console.log(user2.address.city); // "Ganja"

---

## ✅ Ən Sadə Fərq

| Xüsusiyyət | Shallow Copy | Deep Copy |
|-----------|--------------|-----------|
| Kopyalanan səviyyə | 1 səviyyə | Bütün səviyyələr |
| Nested obyekt | Eyni referans | Yeni obyekt |
| Dəyişiklik təsiri | Yayılır | Yayılmır |
| Sürət | Sürətli | Daha yavaş |

---

# “1 səviyyə” və “bütün səviyyələr” nə deməkdir?

## 🔹 Shallow Copy → yalnız **1 səviyyə** kopyalanır
Shallow copy obyektin *yalnız üst qatındakı* dəyərləri kopyalayır.  
Əgər obyektin içində başqa obyekt və ya array varsa → **onların içi kopyalanmır**, referens ötürülür.

### Misal:
    const obj = {
      name: "Ali",
      info: { age: 20 }
    };

    const copy = { ...obj }; // shallow copy
    copy.info.age = 30;

    console.log(obj.info.age); // 30 → dəyişdi

**Səbəb:**  
Shallow copy yalnız 1 səviyyəni kopyalayır.  
`info` adlı nested obyekt isə kopyalanmır → hər iki obyekt eyni `info`-ya baxır.

---

## 🔹 Deep Copy → **bütün səviyyələr** kopyalanır
Deep copy obyektin içində nə qədər nested obyekt varsa → hamısını ayrı-ayrı kopyalayır.  
Yəni **heç bir referens paylaşılmır**, hər şey tam təzədən yaradılır.

### Misal:
    const obj = {
      name: "Ali",
      info: { age: 20 }
    };

    const deep = structuredClone(obj); // deep copy
    deep.info.age = 30;

    console.log(obj.info.age); // 20 → dəyişmədi

**Səbəb:**  
Deep copy nested obyektləri də ayrıca kopyalayır.  
Ona görə də `deep.info` və `obj.info` artıq fərqli obyektlərdir.

---

## ✅ Shallow Copy üsulları
- `{ ...obj }`
- `Object.assign({}, obj)`
- `[ ...arr ]`
- `arr.slice()`

---

## ✅ Deep Copy üsulları
- `structuredClone(obj)` ✅ ən doğru seçim
- `JSON.parse(JSON.stringify(obj))` ⚠️ bəzi dəyərləri itirir
- `_.cloneDeep(obj)` (Lodash)
- Rekursiv funksiya (interview sualı)

---
