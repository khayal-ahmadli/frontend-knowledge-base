# ✅ React layihəsində nə zaman `useState`, nə zaman `variable` istifadə olunur?

React-də ən fundamental qayda:

## 🔥 QAYDA:
### **UI-də görünən və komponenti yenidən render etməli olan dəyər → `useState`**
### **UI-ə təsiri olmayan, sadəcə daxili hesablamalar → `variable`**

---

# ✅ 1. `useState` nə zaman istifadə olunur?

**Komponentin yenidən render olunmasına ehtiyac varsa.**

### ✅ UI-də görünən bütün dəyərlər üçün `useState` lazımdır:
- input dəyəri  
- counter  
- modal open/close  
- dark/light mode  
- API-dən gələn data  
- ekranda göstərilən hər dəyər  

**Misal:**

const [count, setCount] = useState(0);

const increment = () => {
  setCount(count + 1); // UI yenilənir
};

➡️ `count` dəyişəndə komponent yenidən render olur → `useState` vacibdir.

---

# ✅ 2. `variable` (let/const) nə zaman istifadə olunur?

**Dəyərin dəyişməsi UI-ni yeniləməli deyilsə.**  
Sadəcə komponent daxilində aralıq hesablama üçündür.

### ✅ UI-ə təsir etməyən məlumat → variable istifadə et:
- daxili hesablamalar  
- config məlumatları  
- dəyişməyən konstantlar  
- form submit üçün hazırlanan obyekt  
- renderə təsiri olmayan dəyişənlər  

**Misal:**

function Example() {
  const tax = 0.18; // UI dəyişmir
  let total = 100 * tax; // local calculation

  return <div>Total: {total}</div>;
}

➡️ `tax` və `total` dəyişsə də render trigger olunmur → variable kifayət edir.

---

# ✅ 3. `useState` və `variable` arasındakı fərqlər

| Xüsusiyyət | useState | variable |
|-----------|----------|----------|
| Render zamanı saxlanılır | ✅ Bəli | ❌ Xeyr |
| Dəyər dəyişəndə render olur | ✅ Bəli | ❌ Xeyr |
| Component lifecycle ilə işləyir | ✅ Bəli | ❌ Xeyr |
| Asinxron ola bilər | ✅ Bəli | ✅ Xeyr |
| UI-də göstərilir | ✅ Bəli | ✅ Ola bilər, amma dəyişməz |

---