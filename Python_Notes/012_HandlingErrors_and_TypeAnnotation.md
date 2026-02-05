# Hata Yönetici ve Tip Belirleme

# 1. Hata Yönetimi (Error Handling) 🛡️

**Dosya:** HandlingErrors.ipynb

Yazdığın kod kusursuz olabilir ama kullanıcı saçma sapan bir şey girebilir (örneğin yaş yerine "Emirhan" yazmak gibi). Bu durumda programın "güm" diye patlamaması için try-except yapısını kullanıyoruz. Buna "Güvenlik Ağı" diyebilirsin.

## Temel Yapı ve Anlamları:

**try:** (Dene Bakalım):

"Riskli" kodları buraya yazarız. Hata çıkma ihtimali olan yerdir (örn: int(input())).

**except:** (Hata Olursa Yakala):

Eğer try bloğunda hata çıkarsa program çökmez, buraya atlar. Kullanıcıya "Sayı girmeliydin!" gibi nazik bir mesaj verirsin.

**Not:** except ValueError: diyerek sadece spesifik hataları (veri tipi hatası) yakalamışsın, bu doğru kullanım.

**else:** (Hata Yoksa Buraya):

Sadece try kısmı sorunsuz çalışırsa burası devreye girer. (Senin örnekte döngüyü break ile kırmak için kullanılmış).

**finally:** (Ne Olursa Olsun):

Hata olsa da olmasa da, yer yerinden oynasa da mutlaka çalışır. Genelde "dosyayı kapat", "bağlantıyı kes" gibi temizlik işleri için kullanılır.

## Senin Kodundaki Senaryo:

```python
while True:
    try:
        myAge = int(input("yas gir: "))  # Riskli hareket
    except ValueError:
        print("Sayı gir dedik sana!")    # Hata varsa burası
    else:
        print("Tamamdır, yaşın:", myAge) # Hata yoksa burası
        break
    finally:
        print("İşlem bitti.")            # Her türlü çalışır

```

---

# 2. Tip Belirleme (Type Annotation / Hinting) 🏷️

**Dosya:** TypeAnnotation.ipynb

Python normalde "Ne verirsen kabulümdür" diyen esnek bir dildir. Ama projeler büyüyünce "Bu değişkene sayı mı gelecekti, yazı mı?" diye kafalar karışır. Type Annotation, değişkenlerin üzerine etiket yapıştırmaktır.

## Önemli Uyarı:

Python bu etiketleri zorunlu tutmaz.

Örnek: Dosyanda surname: str = 20 yazmışsın ve Python hata vermemiş. Yani etikete "Yazı" dedin ama içine "Sayı" koydun. Python bunu çalıştırır ama PyCharm gibi editörler sana "Hopp, yanlış yapıyorsun" diye sarı uyarı verir.

## Kullanılan Etiketler:

### Değişken Etiketleme:

```python
name: str = "Emirhan"  # Bu bir metindir
age: int = 22          # Bu bir tam sayıdır
is_student: bool = True # Bu True/False alır

```

### Fonksiyon Etiketleme (Çok Önemli):

Fonksiyonun ne alıp ne vereceğini baştan söylersin.

```python
# a ve b tam sayı olmalı, sonuç da tam sayı dönecek (-> int)
def add_numbers(a: int, b: int) -> int:
    return a + b

```

### Birden Fazla Tip (Union):

"Ya sayı gelsin ya da yazı, ikisi de olur" demek için | işareti kullanılır.

```python
def islem_yap(deger: int | str):
    # Hem int hem str kabul eder

```

### Liste Etiketleme:

Listenin içindeki elemanların türünü belirtmek için List kullanılır.

```python
from typing import List

# Sadece sayılardan oluşan bir liste
numbers: List[int] = [1, 2, 3, 4]

```

---

# For ENG

---

# 1. Error Handling 🛡️

**File:** HandlingErrors.ipynb

The code you write may be perfect, but the user can enter something completely nonsense (for example, typing "Emirhan" instead of an age). To prevent the program from crashing with a big "boom", we use the try-except structure. You can call this a "Safety Net".

## Basic Structure and Meanings:

**try:** (Give It a Try):

We write "risky" code here. This is the place where an error might occur (e.g., int(input())).

**except:** (Catch the Error):

If an error occurs in the try block, the program does not crash and jumps here. You give the user a polite message like "You should have entered a number!".

**Note:** Using except ValueError: to catch only specific errors (data type errors) is the correct usage.

**else:** (If No Error):

This part runs only if the try block works without any problems. (In your example, it is used to break the loop).

**finally:** (No Matter What):

Whether an error occurs or not, even if the world collapses, this block always runs. It is generally used for cleanup tasks such as "close the file" or "disconnect the connection".

## The Scenario in Your Code:

```python
while True:
    try:
        myAge = int(input("enter age: "))  # Risky action
    except ValueError:
        print("We told you to enter a number!")    # If there is an error
    else:
        print("Alright, your age is:", myAge) # If there is no error
        break
    finally:
        print("Process finished.")            # Runs no matter what

```

---

# 2. Type Annotation / Hinting 🏷️

**File:** TypeAnnotation.ipynb

Python is normally a flexible language that says "I accept whatever you give me". But as projects grow, confusion arises like "Was this variable supposed to be a number or a string?". Type Annotation is the act of attaching labels to variables.

## Important Warning:

Python does not enforce these labels.

Example: In your file, you wrote surname: str = 20 and Python did not throw an error. So you labeled it as "String" but assigned a "Number" to it. Python runs this, but editors like PyCharm give you a yellow warning saying "Hey, you’re doing something wrong".

## Used Annotations:

### Variable Annotation:

```python
name: str = "Emirhan"  # This is a string
age: int = 22          # This is an integer
is_student: bool = True # This takes True/False

```

### Function Annotation (Very Important):

You define what the function takes and what it returns beforehand.

```python
# a and b must be integers, and the result will return an integer (-> int)
def add_numbers(a: int, b: int) -> int:
    return a + b

```

### Multiple Types (Union):

To say "Either a number or a string can come, both are okay", the | symbol is used.

```python
def islem_yap(deger: int | str):
    # Accepts both int and str

```

### List Annotation:

To specify the type of elements inside a list, List is used.

```python
from typing import List

# A list consisting only of numbers
numbers: List[int] = [1, 2, 3, 4]

```

---
