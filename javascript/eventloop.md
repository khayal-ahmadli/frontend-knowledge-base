# JavaScript Asynchronous Behaviour, Event Loop, Microtask, Macrotask, Callback, Call Stack

## 1. Sinxron və Asinxron Nədir?

### ✔ Sinxron (Synchronous)
Kod **sətir-sətir**, ardıcıl şəkildə icra olunur.  
Növbəti əməliyyat əvvəlkini gözləyir.

```js
console.log(1);
console.log(2);
console.log(3);
```

---

### ✔ Asinxron (Asynchronous)
Kod gözləmədən davam edir.  
Uzunmüddətli əməliyyatlar (timer, API, event) background-da işləyir.

```js
console.log(1);

setTimeout(() => console.log(2), 1000);

console.log(3);
```

Nəticə:
```
1
3
2
```

---

## 2. Call Stack

JavaScript funksiyaları **Call Stack**də icra edir.  
Bu, JS-in əsas sinxron icra yeridir.

```js
function a() { b(); }
function b() { console.log("Hello"); }
a();
```

Call Stack:
```
a()
b()
console.log
```

---

## 3. Web APIs (Asinxron Mexanizmlər)

Browser JS-ə asinxron imkanlar verir:

- setTimeout
- setInterval
- fetch
- DOM Events
- FileReader

Asinxron funksiyalar Call Stack-dən çıxır və Web API-də işləyirlər.

---

## 4. Microtask və Macrotask Queue

Asinxron kod nəticələri iki növbədən birinə gedir:

### ✔ Microtask Queue
**Promiselər üçün** xüsusi yüksək prioritetli növbə.

Buraya daxildir:
- Promise.then
- Promise.catch
- Promise.finally
- queueMicrotask
- MutationObserver

### ✔ Macrotask Queue (Task Queue / Callback Queue)
Buraya daxildir:
- setTimeout
- setInterval
- DOM events
- MessageChannel
- I/O callbacks

### ❗ Microtask Queue → daima Macrotask Queue-dan əvvəl icra olunur.

---

## 5. Event Loop — Sistemin Beyni

Event Loop-un işi sadədir:

```
Call Stack boşdur?
  Bəli → Microtask Queue-dakı callback-ləri Call Stack-ə göndər
         Microtask tam boşalana qədər
         Sonra Macrotask Queue-dakı callback-ləri Call Stack-ə göndər
  Xeyr → Gözlə
```

### ❗ Microtask ≠ Macrotask  
### ❗ Microtask Queue ≠ Task Queue  
### ✔ Macrotask Queue = Task Queue (Task Queue = Callback Queue -> Macrotask-ların toplandığı növbəyə verilən addır)
### ✔ Hər ikisi Event Loop tərəfindən idarə olunur.

---

## 6. Nümunə

```js
console.log(1);

setTimeout(() => console.log(2), 0);

Promise.resolve().then(() => console.log(3));

console.log(4);
```

İcra sırası:
```
1
4
3  ← microtask
2  ← macrotask
```

---

## 7. Niyə Macrotask Queue-dan “callback” deyirik?

Çünki Queue-da saxlanan şey **həmişə FUNKSIYADIR**, yəni sonradan çağırılacaq “callback”.

- setTimeout → callback function
- click event → callback function
- fetch → callback function

Task Queue-da “task” yox, **callback function** saxlanılır.

---

## 8. Yekun Axın Diagramı

```
                 ┌─────────────┐
                 │  Call Stack │
                 └──────▲──────┘
                        │
           ┌────────────┴────────────┐
           │        Event Loop       │
           └────────────┬────────────┘
                        │
        ┌───────────────▼────────────────┐
        │         Microtask Queue        │
        │   (Promise.then, catch, ...)   │
        └───────────────┬────────────────┘
                        │
        ┌───────────────▼────────────────┐
        │        Macrotask Queue         │
        │ (setTimeout, events, I/O ...)  │
        └────────────────────────────────┘
```

---

## 9. Bir cümləlik xülasə

**Sinxron kod Call Stack-də işləyir.  
Asinxron kod Web API-lərdə işləyib Microtask və Macrotask Queue-lara düşür.  
Event Loop Call Stack boşalanda əvvəl Microtask Queue-ni, sonra Macrotask Queue-ni Call Stack-ə ötürür.  
Bütün callback-lər sonda Call Stack-də icra olunur.**
