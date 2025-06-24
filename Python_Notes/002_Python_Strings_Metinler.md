# Python - [Strings]

# 🐍 Strings in Python (Metinler)

Bu not, Python'da metinlerle (string) çalışmanın temellerini anlatır. Karakter dizilerini nasıl tanımlarız, işleriz ve analiz ederiz? Gel birlikte öğrenelim!

---

## 📌 String Tanımı (String Definition)

Bir string; `'` veya `"` içinde yazılan karakterler dizisidir.

```python
"hello world"
'Emirhan Çabık'

```

String veriler, ekrana yazdırılabilir:

```python
print("hello python")
# Output: hello python

```

---

## 👨‍💻 Değişkenlerle String Kullanımı

String’leri bir değişkene atayıp kullanabiliriz:

```python
name = "emirhan"

```

Veri tipini görmek için:

```python
type(name)
# Output: <class 'str'>

```

---

## 🧪 String İşlemleri

### 🔢 Uzunluk Bulma (`len()`)

```python
name = "Emirhan Çabık"
len(name) # length
# Output: 13

```

### ➕ String Birleştirme (Concatenation)

```python
first = "emirhan"
last = "çabık"

full_name = first + " " + last
print(full_name)
# Output: emirhan çabık

```

---

### 🕵️ İçerik Kontrolü (`in`)

```python
"han" in name
# Output: True

```

## 🧠 Python String Slicing (Dilimleme) — “emirhan” Üzerinden

Slicing, bir string’in belirli bir bölümünü almak için kullanılır. Yapısı:

```python
metin[başlangıç:durak:atlama]

```

---

### 🔹 Karakter ve İndeks Tablosu

```python
name = "emirhan"

```

| Karakter | e | m | i | r | h | a | n |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Pozitif | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| Negatif | -7 | -6 | -5 | -4 | -3 | -2 | -1 |

---

## 🔸 1. Başlangıç (Starting Index)

Başlayacağı yer. Bu karakter **dahildir**. Boş bırakılırsa baştan başlar (`0`).

```python
print(name[2:])  # 2. indeksten sona kadar
# Output: irhan

```

---

## 🔸 2. Durak (Stopping Index)

Duracağı yer. Bu karakter **dahil edilmez**. Boş bırakılırsa sona kadar gider.

```python
print(name[:4])  # 0’dan başla, 4’e kadar (4 dahil değil)
# Output: emir

print(name[1:4])  # 1’den başla, 4’e kadar
# Output: mir

```

---

## 🔸 3. Atlama (Step Size)

Kaçar kaçar alınacağını belirtir. Varsayılan `1`’dir.

```python
print(name[::2])  # 2’şer atlayarak
# Output: eihn

```

---

## 🔁 Özel: Ters Çevirme

```python
print(name[::-1])  # Metni ters çevir
# Output: nahrime

```

---

## 🔄 Hepsi Birlikte: Başlangıç, Durak, Atlama

```python
print(name[1:6:2])  # 1’den başla, 6’ya kadar, 2’şer atla
# Output: mra

```

📌 Açıklama:

- Alınan karakterler: `m` (1), `r` (3), `a` (5)
- 6. indeks dahil değil.

---

# ✍️ Python String Metotları Kataloğu

Bu not, Python'da bir string değişkeninden sonra nokta koyulduğunda erişilebilen tüm yaygın metotları, kullanım örnekleri ve açıklamalarıyla listeler.

---

## 📌 capitalize()

```python
name = "emirhan çabık"
print(name.capitalize())
# *Output: Emirhan çabık*
```

*Açıklama: Metnin sadece ilk harfini büyük, geri kalanını küçük yapar.*

---

## 📌 casefold()

```python
name = "Emirhan Çabık"
print(name.casefold())
#Output: *emirhan çabık*
```

*Açıklama: Metni, farklı dillerdeki karakterleri de dikkate alarak tamamen küçük harfe çevirir.*

---

## 📌 center()

```python
name = "Emirhan"
print(name.center(21, '-'))
# *Output: -------Emirhan-------*
```

*Açıklama: Metni belirtilen genişliğe ortalar ve boşlukları verilen karakterle doldurur.*

---

## 📌 count()

```python
name = "Emirhan Çabık"
print(name.count("a"))
# *Output: 2*
```

*Output: 2*

*Açıklama: Metin içinde belirtilen karakterin kaç defa geçtiğini sayar.*

---

## 📌 encode()

```python
name = "Emirhan Çabık"
print(name.encode())
#Output : *b'Emirhan \xc3\x87ab\xc4\xb1k'*
```

*Açıklama: Metni, belirtilen standarda (varsayılan: UTF-8) göre byte dizisine çevirir.*

---

## 📌 endswith()

```python
name = "Emirhan Çabık"
print(name.endswith("bık"))
# *Output: True*
```

*Output: True*

*Açıklama: Metin, belirtilen karakter(ler) ile bitiyorsa `True` döndürür.*

---

## 📌 expandtabs()

```python
text = "Emirhan\tÇabık"
print(text.expandtabs())
# *Output: Emirhan    Çabık*
```

*Açıklama: Metin içindeki sekme (`\t`) karakterlerini boşluklara çevirir.*

---

## 📌 find()

```python
name = "Emirhan Çabık"
print(name.find("Ç"))
# Output : 8
```

*Açıklama: Belirtilen karakterin metin içindeki ilk indeksini bulur. Bulamazsa -1 döner.*

---

## 📌 format()

```python
sablon = "Merhaba, benim adım {}."
print(sablon.format("Emirhan"))
# *Output: Merhaba, benim adım Emirhan.*
```

*Açıklama: Metin içindeki `{}` alanlarına sırasıyla belirtilen değerleri yerleştirir.*

---

## 📌 format_map()

```python
bilgiler = {'isim': 'Emirhan', 'sehir': 'Balıkesir'}
sablon = "Kullanıcı: {isim}, Şehir: {sehir}"
print(sablon.format_map(bilgiler))
# *Output: Kullanıcı: Emirhan, Şehir: Balıkesir*
```

*Açıklama: `format()` gibidir ama argüman olarak bir sözlük alır.*

---

## 📌 format_map()

```python
bilgiler = {'isim': 'Emirhan', 'sehir': 'Balıkesir'}
sablon = "Kullanıcı: {isim}, Şehir: {sehir}"
print(sablon.format_map(bilgiler))
# Output: Kullanıcı: Emirhan, Şehir: Balıkesir
```

Açıklama: `format()` gibidir ama argüman olarak bir sözlük (dictionary) alır.

---

## 📌 index()

```python
name = "Emirhan Çabık"
print(name.index("Ç"))
# Output: 8
```

Açıklama: `find()` gibidir ama karakteri bulamazsa hata verir.

---

## 📌 isalnum()

```python
text = "Python3"
print(text.isalnum())
# Output: True
```

Açıklama: Metindeki tüm karakterler harf veya rakam ise `True` döndürür.

---

## 📌 isalpha()

```python
text = "Python"
print(text.isalpha())
# Output: True
```

Açıklama: Metindeki tüm karakterler harf ise `True` döndürür.

---

## 📌 isascii()

```python
name = "Emirhan"
print(name.isascii())
# Output: True
```

Açıklama: Metindeki tüm karakterler ASCII standardında ise `True` döndürür.

---

## 📌 isdigit()

```python
text = "12345"
print(text.isdigit())
# Output: True
```

Açıklama: Metindeki tüm karakterler rakam ise `True` döndürür.

---

## 📌 islower()

```python
text = "emirhan"
print(text.islower())
# Output: True
```

Açıklama: Metindeki tüm harfler küçük ise `True` döndürür.

---

## 📌 isspace()

```python
text = "   "
print(text.isspace())
# Output: True
```

Açıklama: Metin sadece boşluk karakterlerinden oluşuyorsa `True` döndürür.

---

## 📌 istitle()

```python
text = "Emirhan Çabık"
print(text.istitle())
# Output: True
```

Açıklama: Metindeki her kelimenin ilk harfi büyük ise `True` döndürür.

---

## 📌 isupper()

```python
text = "EMİRHAN"
print(text.isupper())
# Output: True
```

### 🔹 `join()`

```python
kelimeler = ["Emirhan", "Çabık"]
ayirici = " "
print(ayirici.join(kelimeler))
# Output: Emirhan Çabık

```

**Açıklama:** Listenin elemanlarını, araya belirtilen karakteri koyarak birleştirir.

---

### 🔹 `ljust()`

```python
name = "Emirhan"
print(name.ljust(20, '-'))
# Output: Emirhan-------------

```

**Açıklama:** Metni sola yaslar, boşlukları belirttiğin karakterle doldurur.

---

### 🔹 `lower()`

```python
name = "Emirhan Çabık"
print(name.lower())
# Output: emirhan çabık

```

**Açıklama:** Tüm harfleri küçük yapar.

---

### 🔹 `lstrip()`

```python
text = "  ---Emirhan"
print(text.lstrip(" -"))
# Output: Emirhan

```

**Açıklama:** Metnin solundaki belirttiğin karakterleri siler.

---

### 🔹 `maketrans()` & `translate()`

```python
metin = "abcde"
ceviri = str.maketrans("ace", "123")
print(metin.translate(ceviri))
# Output: 1b2d3

```

**Açıklama:** `maketrans` ile çeviri tablosu oluşturulur, `translate` ile uygulanır.

---

### 🔹 `removeprefix()`

```python
text = "www.emirhan.com"
print(text.removeprefix("www."))
# Output: emirhan.com

```

**Açıklama:** Belirtilen önek varsa kaldırır.

---

### 🔹 `removesuffix()`

```python
text = "www.emirhan.com"
print(text.removesuffix(".com"))
# Output: www.emirhan

```

**Açıklama:** Belirtilen sonek varsa kaldırır.

---

### 🔹 `replace()`

```python
text = "Balıkesir, Bandırma"
print(text.replace("Bandırma", "Merkez"))
# Output: Balıkesir, Merkez

```

**Açıklama:** Belirttiğin kısmı yenisiyle değiştirir.

---

### 🔹 `rfind()`

```python
text = "emirhan çabık emirhan"
print(text.rfind("emirhan"))
# Output: 14

```

**Açıklama:** `find` gibi ama aramaya sondan başlar.

---

### 🔹 `rindex()`

```python
text = "emirhan çabık emirhan"
print(text.rindex("emirhan"))
# Output: 14

```

**Açıklama:** `index` gibi ama aramaya sondan başlar.

---

### 🔹 `rjust()`

```python
name = "Emirhan"
print(name.rjust(20, '-'))
# Output: -------------Emirhan

```

**Açıklama:** Metni sağa yaslar, sola karakter ekler.

---

### 🔹 `rsplit()`

```python
text = "a-b-c-d"
print(text.rsplit('-', 2))
# Output: ['a-b', 'c', 'd']

```

**Açıklama:** `split` gibi ama sağdan böler.

---

### 🔹 `rstrip()`

```python
text = "Emirhan---  "
print(text.rstrip(" -"))
# Output: Emirhan

```

**Açıklama:** Metnin sağındaki karakterleri siler.

---

### 🔹 `split()`

```python
text = "Emirhan Çabık Balıkesir"
print(text.split())
# Output: ['Emirhan', 'Çabık', 'Balıkesir']

```

**Açıklama:** Boşluklardan bölerek liste oluşturur.

---

### 🔹 `splitlines()`

```python
siir = "Merhaba Dünya\nNasılsın Bugün?"
print(siir.splitlines())
# Output: ['Merhaba Dünya', 'Nasılsın Bugün?']

```

**Açıklama:** Satır sonlarından böler.

---

### 🔹 `startswith()`

```python
name = "Emirhan Çabık"
print(name.startswith("Emir"))
# Output: True

```

**Açıklama:** Metin belirtilen ifade ile başlıyorsa `True` döner.

---

### 🔹 `strip()`

```python
text = "  ---Emirhan---  "
print(text.strip(" -"))
# Output: Emirhan

```

**Açıklama:** Metnin hem başındaki hem sonundaki karakterleri siler.

---

### 🔹 `swapcase()`

```python
name = "EmİrHaN ÇAbıK"
print(name.swapcase())
# Output: eMiRhAn çaBIk

```

**Açıklama:** Küçük harfleri büyük, büyük harfleri küçük yapar.

---

### 🔹 `title()`

```python
name = "emirhan çabık"
print(name.title())
# Output: Emirhan Çabık

```

**Açıklama:** Her kelimenin ilk harfini büyük yapar.

---

### 🔹 `upper()`

```python
name = "Emirhan Çabık"
print(name.upper())
# Output: EMİRHAN ÇABIK

```

**Açıklama:** Tüm harfleri büyük yapar.

---

### 🔹 `zfill()`

```python
numara = "45"
print(numara.zfill(5))
# Output: 00045

```

**Açıklama:** Belirtilen uzunluğa ulaşana kadar başına `0` ekler.

---

# For ENG

---

# 🐍 Strings in Python

This note explains the basics of working with strings in Python. How do we define, process, and analyze character sequences? Let’s learn together!

---

## 📌 String Definition

A string is a sequence of characters enclosed in `'` or `"`.

```python
"hello world"
'Emirhan Çabık'

```

String data can be printed to the screen:

```python
print("hello python")
# Output: hello python

```

---

## 👨‍💻 Using Strings with Variables

We can assign strings to variables and use them:

```python
name = "emirhan"

```

To see the data type:

```python
type(name)
# Output: <class 'str'>

```

---

## 🧪 String Operations

### 🔢 Length (`len()`)

```python
name = "Emirhan Çabık"
len(name)  # length
# Output: 13

```

### ➕ String Concatenation

```python
first = "emirhan"
last = "çabık"

full_name = first + " " + last
print(full_name)
# Output: emirhan çabık

```

---

### 🕵️ Content Check (`in`)

```python
"han" in name
# Output: True

```

### 🔁 Slicing

```python
name[0:3]
# Output: 'emi'
name[-1]
# Output: 'n'

```

---

## 🧠 Python String Slicing — Using “emirhan”

Slicing is used to retrieve a portion of a string. Syntax:

```python
text[start:stop:step]

```

---

### 🔹 Character and Index Table

```python
name = "emirhan"

```

| Character | e | m | i | r | h | a | n |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Positive | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| Negative | -7 | -6 | -5 | -4 | -3 | -2 | -1 |

---

## 🔸 1. Start Index

Where to start. This character **is included**. If omitted, starts from the beginning (`0`).

```python
print(name[2:])  # From index 2 to end
# Output: irhan

```

---

## 🔸 2. Stop Index

Where to stop. This character **is not included**. If omitted, goes to the end.

```python
print(name[:4])  # From 0 to index 4 (excluding 4)
# Output: emir

print(name[1:4])  # From 1 to 4
# Output: mir

```

---

## 🔸 3. Step Size

How many steps to take. Default is `1`.

```python
print(name[::2])  # Take every 2nd character
# Output: eihn

```

---

## 🔁 Special: Reversing

```python
print(name[::-1])  # Reverse the string
# Output: nahrime

```

---

## 🔄 All Together: Start, Stop, Step

```python
print(name[1:6:2])  # From 1 to 6, step by 2
# Output: mra

```

📌 Explanation:

- Selected characters: `m` (1), `r` (3), `a` (5)
- Index 6 is not included.

---

# ✍️ Python String Methods Catalog

This note lists all common string methods in Python that are accessed using dot notation, with examples and explanations.

---

## 📌 capitalize()

```python
name = "emirhan çabık"
print(name.capitalize())
# Output: Emirhan çabık

```

*Explanation: Capitalizes only the first letter, makes the rest lowercase.*

---

## 📌 casefold()

```python
name = "Emirhan Çabık"
print(name.casefold())
# Output: emirhan çabık

```

*Explanation: Converts the text to lowercase considering international characters.*

---

## 📌 center()

```python
name = "Emirhan"
print(name.center(21, '-'))
# Output: -------Emirhan-------

```

*Explanation: Centers the text in the given width and fills the rest with the given character.*

---

## 📌 count()

```python
name = "Emirhan Çabık"
print(name.count("a"))
# Output: 2

```

*Explanation: Counts how many times a character appears in the text.*

---

## 📌 encode()

```python
name = "Emirhan Çabık"
print(name.encode())
# Output: b'Emirhan \xc3\x87ab\xc4\xb1k'

```

*Explanation: Encodes the string to bytes (default: UTF-8).*

---

## 📌 endswith()

```python
name = "Emirhan Çabık"
print(name.endswith("bık"))
# Output: True

```

*Explanation: Returns `True` if the text ends with the given substring.*

---

## 📌 expandtabs()

```python
text = "Emirhan\tÇabık"
print(text.expandtabs())
# Output: Emirhan    Çabık

```

*Explanation: Replaces tab (`\t`) characters with spaces.*

---

## 📌 find()

```python
name = "Emirhan Çabık"
print(name.find("Ç"))
# Output: 8

```

*Explanation: Finds the first index of the character. Returns -1 if not found.*

---

## 📌 format()

```python
template = "Hello, my name is {}."
print(template.format("Emirhan"))
# Output: Hello, my name is Emirhan.

```

*Explanation: Replaces `{}` placeholders with provided values.*

---

## 📌 format_map()

```python
info = {'isim': 'Emirhan', 'sehir': 'Balıkesir'}
template = "User: {isim}, City: {sehir}"
print(template.format_map(info))
# Output: User: Emirhan, City: Balıkesir

```

*Explanation: Like `format()`, but takes a dictionary as argument.*

---

## 📌 index()

```python
name = "Emirhan Çabık"
print(name.index("Ç"))
# Output: 8

```

*Explanation: Like `find()`, but raises an error if not found.*

---

## 📌 isalnum()

```python
text = "Python3"
print(text.isalnum())
# Output: True

```

*Explanation: Returns `True` if all characters are letters or digits.*

---

## 📌 isalpha()

```python
text = "Python"
print(text.isalpha())
# Output: True

```

*Explanation: Returns `True` if all characters are letters.*

---

## 📌 isascii()

```python
name = "Emirhan"
print(name.isascii())
# Output: True

```

*Explanation: Returns `True` if all characters are in ASCII.*

---

## 📌 isdigit()

```python
text = "12345"
print(text.isdigit())
# Output: True

```

*Explanation: Returns `True` if all characters are digits.*

---

## 📌 islower()

```python
text = "emirhan"
print(text.islower())
# Output: True

```

*Explanation: Returns `True` if all letters are lowercase.*

---

## 📌 isspace()

```python
text = "   "
print(text.isspace())
# Output: True

```

*Explanation: Returns `True` if the string contains only whitespace.*

---

## 📌 istitle()

```python
text = "Emirhan Çabık"
print(text.istitle())
# Output: True

```

*Explanation: Returns `True` if each word starts with an uppercase letter.*

---

## 📌 isupper()

```python
text = "EMİRHAN"
print(text.isupper())
# Output: True

```

---

### 🔹 `join()`

```python
words = ["Emirhan", "Çabık"]
separator = " "
print(separator.join(words))
# Output: Emirhan Çabık

```

*Explanation: Joins the list items using the given separator.*

---

### 🔹 `ljust()`

```python
name = "Emirhan"
print(name.ljust(20, '-'))
# Output: Emirhan-------------

```

*Explanation: Left-justifies the text, filling the rest with a character.*

---

### 🔹 `lower()`

```python
name = "Emirhan Çabık"
print(name.lower())
# Output: emirhan çabık

```

*Explanation: Converts all letters to lowercase.*

---

### 🔹 `lstrip()`

```python
text = "  ---Emirhan"
print(text.lstrip(" -"))
# Output: Emirhan

```

*Explanation: Removes specified characters from the left.*

---

### 🔹 `maketrans()` & `translate()`

```python
text = "abcde"
table = str.maketrans("ace", "123")
print(text.translate(table))
# Output: 1b2d3

```

*Explanation: `maketrans` creates a translation map; `translate` applies it.*

---

### 🔹 `removeprefix()`

```python
text = "www.emirhan.com"
print(text.removeprefix("www."))
# Output: emirhan.com

```

*Explanation: Removes the specified prefix if present.*

---

### 🔹 `removesuffix()`

```python
text = "www.emirhan.com"
print(text.removesuffix(".com"))
# Output: www.emirhan

```

*Explanation: Removes the specified suffix if present.*

---

### 🔹 `replace()`

```python
text = "Balıkesir, Bandırma"
print(text.replace("Bandırma", "Merkez"))
# Output: Balıkesir, Merkez

```

*Explanation: Replaces specified text with another.*

---

### 🔹 `rfind()`

```python
text = "emirhan çabık emirhan"
print(text.rfind("emirhan"))
# Output: 14

```

*Explanation: Like `find()`, but searches from the right.*

---

### 🔹 `rindex()`

```python
text = "emirhan çabık emirhan"
print(text.rindex("emirhan"))
# Output: 14

```

*Explanation: Like `index()`, but searches from the right.*

---

### 🔹 `rjust()`

```python
name = "Emirhan"
print(name.rjust(20, '-'))
# Output: -------------Emirhan

```

*Explanation: Right-justifies the text, filling the left side.*

---

### 🔹 `rsplit()`

```python
text = "a-b-c-d"
print(text.rsplit('-', 2))
# Output: ['a-b', 'c', 'd']

```

*Explanation: Like `split()`, but starts splitting from the right.*

---

### 🔹 `rstrip()`

```python
text = "Emirhan---  "
print(text.rstrip(" -"))
# Output: Emirhan

```

*Explanation: Removes specified characters from the right.*

---

### 🔹 `split()`

```python
text = "Emirhan Çabık Balıkesir"
print(text.split())
# Output: ['Emirhan', 'Çabık', 'Balıkesir']

```

*Explanation: Splits the string at spaces.*

---

### 🔹 `splitlines()`

```python
poem = "Hello World\nHow are you?"
print(poem.splitlines())
# Output: ['Hello World', 'How are you?']

```

*Explanation: Splits the string at line breaks.*

---

### 🔹 `startswith()`

```python
name = "Emirhan Çabık"
print(name.startswith("Emir"))
# Output: True

```

*Explanation: Returns `True` if the string starts with the specified text.*

---

### 🔹 `strip()`

```python
text = "  ---Emirhan---  "
print(text.strip(" -"))
# Output: Emirhan

```

*Explanation: Removes specified characters from both ends.*

---

### 🔹 `swapcase()`

```python
name = "EmİrHaN ÇAbıK"
print(name.swapcase())
# Output: eMiRhAn çaBIk

```

*Explanation: Swaps lowercase to uppercase and vice versa.*

---

### 🔹 `title()`

```python
name = "emirhan çabık"
print(name.title())
# Output: Emirhan Çabık

```

*Explanation: Capitalizes the first letter of each word.*

---

### 🔹 `upper()`

```python
name = "Emirhan Çabık"
print(name.upper())
# Output: EMİRHAN ÇABIK

```

*Explanation: Converts all letters to uppercase.*

---

### 🔹 `zfill()`

```python
number = "45"
print(number.zfill(5))
# Output: 00045

```

*Explanation: Pads the string on the left with zeros until it reaches the specified length.*

---