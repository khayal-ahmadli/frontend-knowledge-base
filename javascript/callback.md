# Callback

**Callback = bir funksiyanın başqa funksiyaya parametr kimi ötürülməsi və sonra çağrılmasıdır.**

---

## 🎯 Sadə Callback Misalı

```js
function greet(name) {
  console.log("Hello " + name);
}

function processUser(callback) {
  callback("Khayal");
}

processUser(greet);
```

Burada `greet` funksiyası callback olur, çünki başqa funksiyaya ötürülür və sonra işlədilir.

---

## 🧠 Callback Niyə Lazımdır?

Callback iki əsas vəziyyətdə istifadə olunur:

### 1️⃣ Başqa funksiyanın içində funksiyanın işləməsi lazım olanda  
Məsələn, məlumat gəldikdən sonra konsola yazmaq.

### 2️⃣ Hadisələrdə (events)  
Klik, hover, form submit və s.

---

## ⏳ Callback-in Ən Məşhur Nümunəsi: setTimeout

```js
setTimeout(() => {
  console.log("Done");
}, 1000);
```

Buradakı arrow function → callback-dir.  
setTimeout işini bitirəndən sonra bu funksiyanı çağırır.

---

## 🔥 Real Həyat Misalı — API Simulyasiyası

```js
function getUser(callback) {
  setTimeout(() => {
    callback({ name: "Khayal", age: 22 });
  }, 1000);
}

getUser((user) => {
  console.log(user);
});
```

- getUser 1 saniyə gözləyir  
- sonra callback-i çağırır  
- user obyektini callback-ə ötürür  

Bu asynchronous davranışdır.

---

## 🤯 Callback Hell Nədir?

Callback-lər iç-içə olanda kod belə olur:

```js
getData((data) => {
  getUser(data.id, (user) => {
    getPosts(user, (posts) => {
      console.log(posts);
    });
  });
});
```

Bu struktur çox qarışıqdır — buna **callback hell** deyilir.  
Promise və async/await bunu həll edir.

---

## 🔗 Callback + Closure

Callback-lər çox vaxt üst scope-dakı dəyişənləri istifadə edir:

```js
function outer() {
  let name = "Khayal";

  setTimeout(() => {
    console.log(name); // callback + closure
  }, 1000);
}

outer();
```

Daxili funksiya həm callback-dir, həm də closure yaradır.

---

## 📌 Qısa Tərif

**Callback — başqa funksiyaya ötürülən və həmin funksiyanın içində sonradan çağırılan funksiyadır.**

---