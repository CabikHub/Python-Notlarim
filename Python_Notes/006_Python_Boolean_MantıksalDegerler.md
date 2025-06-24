# Python - [Boolean]

---

# 🚦 Python'da Boolean Mantığı (True/False)

Boolean, programlamanın temel taşlarından biridir ve sadece iki değere sahip bir veri tipidir: `True` (Doğru) veya `False` (Yanlış). Bir durumun geçerli olup olmadığını kontrol etmek için kullanılır.

---

### ✅ ❌ Boolean Değerleri

Python'da bu iki değer büyük harfle başlar:

- `True`
- `False`

<!-- end list -->

```python
myBoolean = True
type(myBoolean)
# Çıktı: bool

```

---

### 🔍 Boolean'lar Nasıl Oluşur? Karşılaştırma Operatörleri

Boolean değerleri en çok **karşılaştırma** işlemleri sonucunda ortaya çıkar.

| Operatör | Anlamı | Örnek | Sonuç |
| --- | --- | --- | --- |
| `==` | Eşit mi? | `5 == 5` | `True` |
| `!=` | Eşit değil mi? | `5 != 4` | `True` |
| `>` | Büyük mü? | `5 > 3` | `True` |
| `<` | Küçük mü? | `2 < 1` | `False` |
| `>=` | Büyük veya eşit mi? | `5 >= 5` | `True` |
| `<=` | Küçük veya eşit mi? | `5 <= 4` | `False` |

---

### 💡 Pratik Kullanım Örneği: Yaş Kontrolü

Boolean'ların gücü, programın akışını kontrol etme yeteneklerinde yatar.

**Amaç:** Kullanıcının yaşının 18'den büyük olup olmadığını kontrol etmek.

**Adım 1: Kullanıcıdan Veri Almak**`input()` ile kullanıcıdan yaşını alırız. Ancak unutma, `input()` ile gelen veri her zaman metindir (`string`).

```python
age = input("Yaşınızı Giriniz: ")
# Kullanıcı 35 girerse, age değişkeni '35' olur.
print(age)
# Çıktı: '35'

```

**Adım 2: Sayısal Karşılaştırma için Veri Tipi Dönüşümü**
Metin olan `'35'` ile sayı olan `18`'i karşılaştıramayız. Bu yüzden `int()` fonksiyonu ile metni sayıya çeviririz.

**Adım 3: Karşılaştırma ve Sonuç**
Artık sayıya çevirdiğimiz yaşı 18 ile karşılaştırabiliriz. Bu işlemin sonucu bize `True` veya `False` olarak dönecektir.

```python
# 'age' değişkeni kullanıcıdan '35' olarak alınmıştı.
is_over_18 = int(age) > 18
print(is_over_18)
# Çıktı: True

```

---

# 🚦 Boolean Logic in Python (True/False)

Booleans are a cornerstone of programming and a data type that has only two possible values: `True` or `False`. They are used to check if a condition is valid.

---

### ✅ ❌ Boolean Values

In Python, these two values start with a capital letter:

- `True`
- `False`

<!-- end list -->

```python
myBoolean = True
type(myBoolean)
# Output: bool

```

---

### 🔍 How Are Booleans Created? Comparison Operators

Boolean values most often arise as a result of **comparison** operations.

| Operator | Meaning | Example | Result |
| --- | --- | --- | --- |
| `==` | Equal to? | `5 == 5` | `True` |
| `!=` | Not equal to? | `5 != 4` | `True` |
| `>` | Greater than? | `5 > 3` | `True` |
| `<` | Less than? | `2 < 1` | `False` |
| `>=` | Greater than or equal to? | `5 >= 5` | `True` |
| `<=` | Less than or equal to? | `5 <= 4` | `False` |

---

### 💡 Practical Use Case: Age Check

The power of Booleans lies in their ability to control the flow of a program. 

**Goal:** To check if the user's age is greater than 18.

**Step 1: Getting Data from the User**
We get the user's age with `input()`. But remember, data from `input()` is always a string.

```python
age = input("Enter your age: ")
# If the user enters 35, the age variable becomes '35'.
print(age)
# Output: '35'

```

**Step 2: Type Conversion for Numerical Comparison**
We cannot compare the string `'35'` with the number `18`. Therefore, we convert the string to a number using the `int()` function.

**Step 3: Comparison and Result**
Now we can compare the age, which we converted to a number, with 18. The result of this operation will return to us as `True` or `False`.

```python
# The 'age' variable was taken from the user as '35'.
is_over_18 = int(age) > 18
print(is_over_18)
# Output: True

```