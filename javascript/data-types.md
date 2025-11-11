# ✅ JavaScript Data Types — Primitive vs Reference

JavaScript-də data type-lar 2 böyük kateqoriyaya bölünür:

---

## ✅ 1. Primitive Types (Dəyər ilə saxlanır)

Primitive = **sadə dəyərlər**.  
Bu tip dəyişənlərin özündə dəyər olur (stack-də saxlanır).

### ✅ Primitive tiplər:
1. string  
2. number  
3. boolean  
4. null  
5. undefined  
6. symbol  
7. bigint  

### ✅ Xüsusiyyətləri:
- Dəyər **kopyalanır**, referans ötürülmür.  
- Immutable-dır (dəyişdirilə bilməz — əslində yeni dəyər yazılır).  

### ✅ Misal:
let a = 10;
let b = a;  // b=10 olur
a = 20;

console.log(a); // 20
console.log(b); // 10 (dəyişmir)

➡️ Primitive-lərdə kopyalama real kopyadır. Bir-birinə təsir etmir.

---

## ✅ 2. Reference Types (Referans ilə saxlanır)

Reference = **obyekt yönümlü dəyərlər**.  
Dəyərin özü deyil, **adres (referans)** saxlanır (heap-də yerləşir).

### ✅ Reference tiplər:
- object  
- array  
- function  
- Map, Set, WeakMap, WeakSet  

### ✅ Xüsusiyyətləri:
- Dəyərin özü yox **adres kopyalanır**.  
- Eyni obyektə baxan iki dəyişəndə dəyişiklik → hər ikisinə təsir edir.  

### ✅ Misal:
const user1 = { name: "Khayal" };
const user2 = user1;

user1.name = "Ahmad";

console.log(user1.name); // "Ahmad"
console.log(user2.name); // "Ahmad"

➡️ Çünki user1 və user2 eyni obyektin adresini paylaşır.

---