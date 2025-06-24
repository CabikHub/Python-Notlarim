# Python -  [Dictionary]

# 🔑 Python'da Sözlükler (Dictionary) ve Metotları

Sözlükler, verileri bir `anahtar:değer` (key:value) çifti olarak saklayan, sırasız (Python 3.7+ sürümlerinde sıralı) ve **değiştirilebilir (mutable)** koleksiyonlardır. Listelerdeki gibi sayısal indeksler yerine, anlamlı anahtarlar (genellikle metin) kullanarak verilere erişim sağlarlar.

---

### 1. Sözlük Nasıl Oluşturulur?

Sözlükler, süslü parantezler `{}` içine `anahtar:değer` çiftleri yazılarak oluşturulur.

```python
# Anahtarlar metin (string), değerler sayı (integer)
fitness_dictionary = {"banana": 100, "apple": 150}
print(fitness_dictionary)
# Çıktı: {'banana': 100, 'apple': 150}
```

```python
my_dictionary = {"key1":"value1","key2":"value2","key3":"value3"}
my_dictionary["key1"]
# Output : 'value1'

last_dictionary = {"k1":10,"k2":[10,20,30,40,50],"k3":"string","k4":{"a":100,"b":200}}
last_dictionary["k2"][2]
# Output : 30

```

Anahtarlar ve değerler farklı veri tiplerinde olabilir:

```python
ornek_sozluk = {100: "a", 200: "b", 300: "c"}
print(ornek_sozluk[100])
# Çıktı: a

```

---

## 📌 2. Temel Sözlük İşlemleri

### 🔹 Değere Erişim

```python
print(fitness_sozlugu["elma"])
# Çıktı: 150

```

### 🔹 Değer Güncelleme & Yeni Eleman Ekleme

```python
fitness_sozlugu["muz"] = 200  # Güncelleme
fitness_sozlugu["karpuz"] = 300  # Yeni ekleme
print(fitness_sozlugu)
# Çıktı: {'muz': 200, 'elma': 150, 'karpuz': 300}

```

---

## 🧩 İç İçe Sözlükler (Nested Dictionary)

Bir sözlüğün değeri başka bir liste veya sözlük olabilir.

```python
karma_sozluk = {
    "k1": 10,
    "k2": [10, 20, 30],
    "k3": "metin",
    "k4": {"a": 100, "b": 200}
}

print(karma_sozluk["k2"][1])  # Çıktı: 20
print(karma_sozluk["k4"]["b"])  # Çıktı: 200

```

---

## 🧰 Sözlük Metotları

### 📌 `.keys()`

Tüm anahtarları döndürür.

```python
fitness_sozlugu = {"muz": 200, "elma" : 150, "karpuz" : 300 }
print(fitness_sozlugu.keys())
# Çıktı: dict_keys(['muz', 'elma', 'karpuz'])

```

---

### 📌 `.values()`

Tüm değerleri döndürür.

```python
print(fitness_sozlugu.values())
# Çıktı: dict_values([200, 150, 300])

```

---

### 📌 `.items()`

Tüm anahtar-değer çiftlerini (tuple) döndürür.

```python
print(fitness_sozlugu.items())
# Çıktı: dict_items([('muz', 200), ('elma', 150), ('karpuz', 300)])

```

---

### 📌 `.get()`

Anahtar varsa değerini döndürür, yoksa `None` ya da belirtilen varsayılan değeri döndürür.

```python
print(fitness_sozlugu.get("elma", 0))     # Çıktı: 150
print(fitness_sozlugu.get("portakal", 0)) # Çıktı: 0

```

---

### 📌 `.pop()`

Belirtilen anahtarı siler ve değerini döndürür.

```python
deger = fitness_sozlugu.pop("muz")
print(f"Kaldırılan değer: {deger}")  # Çıktı: 200
print(fitness_sozlugu)  # {'elma': 150, 'karpuz': 300}

```

---

### 📌 `.popitem()`

Son eklenen öğeyi siler ve döndürür (Python 3.7+).

```python
son = fitness_sozlugu.popitem()
print(f"Kaldırılan: {son}")  # ('karpuz', 300)
print(fitness_sozlugu)       # {'elma': 150}

```

---

### 📌 `.update()`

Bir sözlüğü başka bir sözlükle birleştirir. Var olan anahtarlar güncellenir, yeniler eklenir.

```python
sozluk1 = {"a": 1, "b": 2}
sozluk2 = {"b": 3, "c": 4}
sozluk1.update(sozluk2)
print(sozluk1)
# Çıktı: {'a': 1, 'b': 3, 'c': 4}

```

---

### 📌 `.clear()`

Tüm anahtar-değer çiftlerini siler.

```python
fitness_sozlugu.clear()
print(fitness_sozlugu)
# Çıktı: {}

```

# For ENG

# 🔑 Python Dictionaries and Their Methods

Dictionaries are collections that store data as `key:value` pairs. They are unordered (ordered in Python 3.7+), and **mutable**. Unlike lists which use numerical indexes, dictionaries access values using meaningful keys (usually strings).

---

### 1. How to Create a Dictionary?

Dictionaries are created using curly braces `{}` with key:value pairs.

```python
# Keys are strings, values are integers
fitness_dictionary = {"banana": 100, "apple": 150}
print(fitness_dictionary)
# Output: {'banana': 100, 'apple': 150}

```

```python
my_dictionary = {"key1":"value1","key2":"value2","key3":"value3"}
my_dictionary["key1"]
# Output : 'value1'

last_dictionary = {"k1":10,"k2":[10,20,30,40,50],"k3":"string","k4":{"a":100,"b":200}}
last_dictionary["k2"][2]
# Output : 30

```

Keys and values can have different data types:

```python
ornek_sozluk = {100: "a", 200: "b", 300: "c"}
print(ornek_sozluk[100])
# Output: a

```

---

## 📌 2. Basic Dictionary Operations

### 🔹 Accessing a Value

```python
print(fitness_sozlugu["elma"])
# Output: 150

```

### 🔹 Updating a Value & Adding a New Entry

```python
fitness_sozlugu["muz"] = 200  # Update
fitness_sozlugu["karpuz"] = 300  # Add new
print(fitness_sozlugu)
# Output: {'muz': 200, 'elma': 150, 'karpuz': 300}

```

---

## 🧩 Nested Dictionaries

A dictionary's value can be another list or dictionary.

```python
karma_sozluk = {
    "k1": 10,
    "k2": [10, 20, 30],
    "k3": "text",
    "k4": {"a": 100, "b": 200}
}

print(karma_sozluk["k2"][1])  # Output: 20
print(karma_sozluk["k4"]["b"])  # Output: 200

```

---

## 🧰 Dictionary Methods

### 📌 `.keys()`

Returns all keys.

```python
fitness_sozlugu = {"muz": 200, "elma" : 150, "karpuz" : 300 }
print(fitness_sozlugu.keys())
# Output: dict_keys(['muz', 'elma', 'karpuz'])

```

---

### 📌 `.values()`

Returns all values.

```python
print(fitness_sozlugu.values())
# Output: dict_values([200, 150, 300])

```

---

### 📌 `.items()`

Returns all key-value pairs as tuples.

```python
print(fitness_sozlugu.items())
# Output: dict_items([('muz', 200), ('elma', 150), ('karpuz', 300)])

```

---

### 📌 `.get()`

Returns the value for the specified key if it exists; otherwise returns `None` or the default value.

```python
print(fitness_sozlugu.get("elma", 0))     # Output: 150
print(fitness_sozlugu.get("portakal", 0)) # Output: 0

```

---

### 📌 `.pop()`

Removes the specified key and returns its value.

```python
deger = fitness_sozlugu.pop("muz")
print(f"Removed value: {deger}")  # Output: 200
print(fitness_sozlugu)  # {'elma': 150, 'karpuz': 300}

```

---

### 📌 `.popitem()`

Removes and returns the last inserted item (Python 3.7+).

```python
son = fitness_sozlugu.popitem()
print(f"Removed: {son}")  # ('karpuz', 300)
print(fitness_sozlugu)    # {'elma': 150}

```

---

### 📌 `.update()`

Merges another dictionary into the current one. Existing keys are updated; new ones are added.

```python
sozluk1 = {"a": 1, "b": 2}
sozluk2 = {"b": 3, "c": 4}
sozluk1.update(sozluk2)
print(sozluk1)
# Output: {'a': 1, 'b': 3, 'c': 4}

```

---

### 📌 `.clear()`

Removes all items from the dictionary.

```python
fitness_sozlugu.clear()
print(fitness_sozlugu)
# Output: {}

```