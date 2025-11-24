# Lexical Environment

Lexical Environment = hər bir scope-un saxladığı dəyişənlər + outer environment-a olan referans.

Bu o deməkdir ki, JavaScript-də hər bir scope iki hissədən ibarətdir:

1) Local Memory  
   - Həmin scope daxilində elan olunan bütün dəyişənlər (`var`, `let`, `const`, funksiyalar)

2) Outer Environment Reference  
   - Scope-un üst səviyyədə yerləşən xarici scope-a olan bağlantısı

Bu iki hissə birlikdə Lexical Environment yaradır və scope chain-in formalaşmasına səbəb olur.

---

## Misal

```js
let a = 10;

function outer() {
  let b = 20;

  function inner() {
    let c = 30;
    console.log(a, b, c);
  }

  inner();
}

outer();
```

### Global Lexical Environment
- Local: a = 10, outer = function
- Outer: yoxdur (ən üst səviyyə)

### outer() Lexical Environment
- Local: b = 20, inner = function
- Outer: global environment

### inner() Lexical Environment
- Local: c = 30
- Outer: outer() environment

Bu səbəbdən inner() funksiyası `a`, `b`, `c` dəyişənlərini görə bilir.

---

## Qısa Yekun

**Lexical Environment = scope-un özündə olan dəyişənlər + üst scope-a olan bağlantı.**
