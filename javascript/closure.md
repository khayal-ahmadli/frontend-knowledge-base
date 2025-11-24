# Closure — JavaScript İzahı

Nested funksiyalarda alt funksiyanın üst scope-un dəyişənlərindən istifadə etməsi closure yaradır.

---

**Closure = daxili funksiyanın, özünü yaradan üst scope-dakı dəyişənləri yadda saxlaması və sonradan istifadə etməsi.**

Closure yalnız bu halda yaranır:
1. Bir funksiyanın içində başqa funksiya var
2. Alt funksiya üst scope-dakı dəyişənə toxunur
3. Üst funksiya bitdikdən sonra da həmin dəyişən “ölmür”

---

## Sadə Misal

```js
function outer() {
  let count = 0;

  function inner() {
    count++;
    console.log(count);
  }

  return inner;
}

const fn = outer();
fn(); // 1
fn(); // 2
fn(); // 3
```

---

## Closure Necə İşləyir?

- outer() çağrılır → count = 0 yaranır
- inner() return olunur
- outer() bitir → normalda count ölməli idi
- Amma inner() count-u yadda saxlayır (closure)
- fn() hər çağırışda count artır

---

## Closure + Global variable → Closure DEYİL

```js
let x = 10;

function test() {
  console.log(x);
}
```

Burada closure yoxdur. Global scope heç vaxt ölmür.

---

## Closure + var / let / const fərqi

| Növ | Scope | Davranış |
|-----|--------|----------|
| var | Function scope | Loop-da closure bug yaradır (3,3,3 problemi) |
| let | Block scope | Hər iterasiya üçün ayrı i saxlayır |
| const | Block scope | Dəyər sabitdir, closure tərəfindən yadda saxlanır |

---

## Closure + Loop (var)

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

Nəticə:
```
3
3
3
```

Səbəb:
- var block scope deyil → tək i var
- loop bitəndə i = 3 olur
- callback-lər gecikir → closure eyni i-nin son dəyərini görür

---

## Closure + Loop (let)

```js
for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

Nəticə:
```
0
1
2
```

Səbəb:
- let block scope-dur
- hər iterasiya üçün ayrı i yaranır
- closure hər iterasiyanın öz dəyərini saxlayır

---

## Closure + Loop (const)

```js
for (const i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

Nəticə:
```
TypeError: Assignment to constant variable.
```

Səbəb:
- const dəyərin dəyişdirilməsinə icazə vermir

---

## Qısa Yekun

Closure = Funksiya yaranan anda öz lexical environment-ını yadda saxlayır.

Nested funksiyalarda alt funksiyanın üst scope-un dəyişənlərindən istifadə etməsi closure yaradır.
