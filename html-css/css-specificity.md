# CSS Specificity

## 1. Selector Güc Qaydası

CSS-də selectorların güc prioriteti belədir:

**Inline > ID > Class > Element**

---

## 2. Selectorların Müqayisəsi

Aşağıdakı selectorlar inline, ID, class və element sayına görə müqayisə edilir:

| Selector       | Inline | ID | Class | Element | Güc səviyyəsi               |
|----------------|--------|----|-------|---------|------------------------------|
| .card p        | 0      | 0  | 1     | 1       | Orta                         |
| #card p        | 0      | 1  | 0     | 1       | **2-ci ən güclü (ID var)**       |
| p.card         | 0      | 0  | 1     | 1       | Orta                         |
| div p.card     | 0      | 0  | 1     | 2       | Orta-dan bir az güclü       |
| Inline style   | 1      | 0  | 0     | 0       | **Bunların hamısından güclü** |

### Nəticə

- **Inline style** → ən güclü  
- Normal selectorlar içində isə **#card p** ən güclüdür  

---

## 3. !important və Inline CSS

### 3.1. inline-da !important yoxdursa

`!important` inline style-ı belə üstələyə bilər.

Misal:

CSS: `div { color: blue !important; }`  
HTML: `<div style="color:red"></div>`

**Nəticə:** blue  
(`!important` inline-dan güclüdür)

---

### 4.2. inline-da da !important varsa

Bu, CSS-də mümkün olan **ən güclü kombinasiya**dır:

**Inline + !important**

Misal:

`<div style="color:red !important"></div>`

Bu halda:

- Heç bir stylesheet qaydası bunu keçə bilməz  
- Heç bir class, id, element selectoru bunu üstələyə bilməz  
- Yalnız **başqa inline!important** bunu üstələyə bilər  

---

## 5. Specificity Güc Sırası (Zəifdən Güclüyə)

1. Element selector (Pseudo-elementlər)
2. Class selector  
3. ID selector  
4. Inline style  
5. Class + !important  
6. ID + !important  
7. Inline + !important (**ən güclü**)  

---
