# Python [OOP]

---

# ✨ Python'da Nesne Yönelimli Programlama (OOP)

Bu not, Python'da kodun daha düzenli, güvenli ve sürdürülebilir olmasını sağlayan Sınıf (Class) yapılarını ve OOP prensiplerini (Kalıtım, Çok Biçimlilik, Kapsülleme, Soyutlama) ele almaktadır.

---

### 1️⃣ Sınıf (Class) ve Nesne (Object) Kavramı

Sınıf bir **mimari plandır** (kalıp), nesne ise o plandan üretilen **evdir** (örnek). `class` anahtar kelimesiyle tanımlanır.

### ✅ Kolay Örnek: Boş Sınıf ve Nesne Üretimi

En temel haliyle bir sınıf tanımlayıp ondan nesne üretmek.

Python

```python
class Person():
    pass  # Şimdilik işlem yapma, boş geç

# Nesne oluşturma (Instance)
emirhan = Person()
print(type(emirhan))
# Çıktı: <class '__main__.Person'>

```

### 🟡 Orta Örnek: `__init__` ve `self`

`__init__`, nesne oluşturulduğu an çalışan kurucu metottur. `self`, o an oluşturulan nesnenin kendisini temsil eder.

Python

```python
class Dog():
    year = 7 # Sınıf özelliği (Her köpek için sabit çarpan)

    def __init__(self, age):
        self.age = age # Nesne özelliği (Her köpeğin yaşı farklıdır)

    def humanAge(self):
        return self.age * self.year

my_dog = Dog(3)
print(f"Köpek yaşı: {my_dog.age}, İnsan yaşı: {my_dog.humanAge()}")
# Çıktı: Köpek yaşı: 3, İnsan yaşı: 21

```

### 🔴 Zor Örnek: Metot İçinde Nesne Özelliklerini Değiştirme

Sınıf içinde tanımlanan metotlar, nesnenin özelliklerini (`self.job` gibi) sonradan değiştirebilir.

Python

```python
class Person():
    job = "İşsiz" # Varsayılan değer

    def __init__(self, name):
        self.name = name

    def setJob(self, new_job):
        self.job = new_job

person1 = Person("Ahmet")
person1.setJob("Developer")
print(f"{person1.name} şu an {person1.job}")
# Çıktı: Ahmet şu an Developer

```

---

### 2️⃣ Inheritance (Kalıtım / Miras)

Bir sınıfın özelliklerini tekrar yazmak yerine, başka bir sınıftan (Parent) miras almasıdır. "Hazıra konmak" demektir.

### ✅ Kolay Örnek: Temel Miras Alma

Çocuk sınıf, ebeveyn sınıfın tüm özelliklerine sahip olur.

Python

```python
class Musician():
    def __init__(self, name):
        self.name = name
        print("Müzisyen oluşturuldu")

class Pianist(Musician): # Musician'dan miras al
    pass

p = Pianist("Fazıl")
print(p.name)
# Çıktı:
# Müzisyen oluşturuldu
# Fazıl

```

### 🟡 Orta Örnek: Metot Ekleme (Extending)

Miras alınan sınıfa yeni özellikler eklemek.

Python

```python
class MusicianPlus(Musician):
    def __init__(self, name):
        Musician.__init__(self, name) # Baba sınıfın init'ini çalıştır
        print("MusicianPlus aktif")

    def hosgoru(self):
        print("Bu kişi hoşgörülüdür.")

mp = MusicianPlus("Emirhan")
mp.hosgoru()
# Çıktı:
# Müzisyen oluşturuldu
# MusicianPlus aktif
# Bu kişi hoşgörülüdür.

```

### 🔴 Zor Örnek: Hata Yönetimi (AttributeError)

Ebeveyn sınıf, çocuk sınıfa eklenen **yeni** özellikleri kullanamaz.

Python

```python
normal_musician = Musician("Ali")
# normal_musician.hosgoru()
# HATA: 'Musician' object has no attribute 'hosgoru'
# Çünkü 'hosgoru' özelliği sadece çocukta (MusicianPlus) var.

```

---

### 3️⃣ Polymorphism (Çok Biçimlilik)

Farklı sınıfların aynı isimli metoda (`infos` gibi) sahip olması ve çağrıldığında her birinin kendi işini yapmasıdır.

### ✅ Kolay Örnek: Aynı İsimli Metotlar

Python

```python
class Banana():
    def infos(self):
        return "Muz: 100 Kalori"

class Apple():
    def infos(self):
        return "Elma: 150 Kalori"

```

### 🟡 Orta Örnek: Döngü ile Polymorphism

Liste içindeki nesnelerin türü farklı olsa da aynı komutu anlayabilirler.

Python

```python
muz = Banana()
elma = Apple()
meyve_listesi = [muz, elma]

for meyve in meyve_listesi:
    print(meyve.infos())
# Çıktı:
# Muz: 100 Kalori
# Elma: 150 Kalori

```

---

### 4️⃣ Encapsulation (Kapsülleme)

Veriyi dışarıdan gizlemek ve sadece izin verilen yollarla değiştirilmesini sağlamaktır. Değişkenin başına `__` (iki alt çizgi) koyarak yapılır.

### ✅ Kolay Örnek: Private (Gizli) Değişken Tanımlama

Python

```python
class Phone():
    def __init__(self, price):
        self.__price = price # Gizli değişken

tel = Phone(500)
# print(tel.__price)
# HATA: AttributeError (Dışarıdan doğrudan erişilemez)

```

### 🟡 Orta Örnek: Getter ve Setter Metotları

Gizli değişkene ulaşmak veya değiştirmek için aracı fonksiyonlar kullanırız.

Python

```python
class Phone():
    def __init__(self, name, price):
        self.name = name
        self.__price = price # Private

    def info(self): # Getter (Okuma)
        print(f"{self.name} fiyatı: {self.__price}")

    def changePrice(self, new_price): # Setter (Yazma)
        self.__price = new_price

iphone = Phone("iPhone 14", 500)
iphone.changePrice(300) # Fiyatı güvenli yoldan değiştirdik
iphone.info()
# Çıktı: iPhone 14 fiyatı: 300

```

---

### 5️⃣ Abstraction (Soyutlama)

Detayları gizleyip sadece bir şablon sunmaktır. Soyut sınıflardan nesne üretilmez, onlar sadece çocuklarına kural koyar.

### ✅ Kolay Örnek: Şablon Oluşturma

`ABC` (Abstract Base Class) ve `@abstractmethod` kullanılır.

Python

```python
from abc import ABC, abstractmethod

class Car(ABC): # Soyut Sınıf
    @abstractmethod
    def maxSpeed(self):
        pass # İçini doldurma, sadece kural koy

```

### 🔴 Zor Örnek: Kurala Uyma Zorunluluğu

Soyut sınıftan miras alan her sınıf, `@abstractmethod` olan fonksiyonu doldurmak **ZORUNDADIR**.

Python

```python
class Tesla(Car):
    def maxSpeed(self):
        print("Hız: 200km/h")

class Mercedes(Car):
    def maxSpeed(self):
        print("Hız: 250km/h")

t = Tesla()
t.maxSpeed()
# Çıktı: Hız: 200km/h

```

---

### 6️⃣ Özel Metotlar (Magic Methods)

Python'un yerleşik fonksiyonlarına (`len`, `print`, `indexing`) kendi sınıflarımızı entegre etmemizi sağlar.

### ✅ Kolay Örnek: `__str__` (Yazdırma)

Bir nesneyi `print()` içine koyduğumuzda ne yazacağını belirler.

Python

```python
class Fruit():
    def __init__(self, name, calories):
        self.name = name
        self.calories = calories

    def __str__(self):
        return f"{self.name}: {self.calories} kalori"

muz = Fruit("Muz", 150)
print(muz)
# Çıktı: Muz: 150 kalori

```

### 🟡 Orta Örnek: `__len__` (Uzunluk)

`len()` fonksiyonunun sınıfımızda nasıl davranacağını belirler.

Python

```python
class Fruit():
    def __init__(self, calories):
        self.calories = calories
    def __len__(self):
        return self.calories

muz = Fruit(150)
print(len(muz))
# Çıktı: 150

```

### 🔴 Zor Örnek: `__getitem__` (İndeksleme)

Sınıfın bir liste gibi davranmasını ve `obj["anahtar"]` şeklinde veri çağırmayı sağlar.

Python

```python
class Train():
    def __init__(self, name):
        self.name = name

    def __getitem__(self, key):
        if key == "a":
            return self.name
        else:
            return "Not Found"

t = Train("Hızlı Tren")
print(t["a"])
print(t["b"])
# Çıktı:
# Hızlı Tren
# Not Found

```

---

# For ENG

---

## ✨ Object Oriented Programming (OOP) in Python

This note covers Class structures and OOP principles (Inheritance, Polymorphism, Encapsulation, Abstraction) that make code more organized, secure, and maintainable in Python.

---

### 1️⃣ Class and Object Concept

A Class is a blueprint, and an object is the house built from that blueprint. Defined with the class keyword.

---

### ✅ Easy Example: Empty Class and Object Creation

Defining a basic class and creating an object from it.

```python
class Person():
    pass

# Creating an Instance
emirhan = Person()
print(type(emirhan))
# Output: <class '__main__.Person'>

```

---

### 🟡 Medium Example: **init** and self

**init** is the constructor method that runs when an object is created. self represents the object itself being created.

```python
class Dog():
    year = 7 # Class attribute

    def __init__(self, age):
        self.age = age # Object attribute

    def humanAge(self):
        return self.age * self.year

my_dog = Dog(3)
print(f"Dog Age: {my_dog.age}, Human Age: {my_dog.humanAge()}")
# Output: Dog Age: 3, Human Age: 21

```

---

### 🔴 Hard Example: Changing Attributes via Methods

Methods defined inside the class can modify the object's attributes later.

```python
class Person():
    job = "Unemployed" # Default value

    def __init__(self, name):
        self.name = name

    def setJob(self, new_job):
        self.job = new_job

person1 = Person("John")
person1.setJob("Developer")
print(f"{person1.name} is now a {person1.job}")
# Output: John is now a Developer

```

---

### 2️⃣ Inheritance

Instead of rewriting code, a class inherits properties from another class (Parent).

---

### ✅ Easy Example: Basic Inheritance

The child class possesses all attributes of the parent class.

```python
class Musician():
    def __init__(self, name):
        self.name = name
        print("Musician created")

class Pianist(Musician): # Inherits from Musician
    pass

p = Pianist("Mozart")
print(p.name)
# Output:
# Musician created
# Mozart

```

---

### 🟡 Medium Example: Extending Methods

Adding new features to the inherited class.

```python
class MusicianPlus(Musician):
    def __init__(self, name):
        Musician.__init__(self, name) # Run parent's init
        print("MusicianPlus active")

    def tolerance(self):
        print("This person is tolerant.")

mp = MusicianPlus("Emirhan")
mp.tolerance()
# Output:
# Musician created
# MusicianPlus active
# This person is tolerant.

```

---

### 3️⃣ Polymorphism

Different classes having methods with the same name (infos), doing their own specific tasks when called.

---

### ✅ Easy Example: Methods with Same Names

```python
class Banana():
    def infos(self):
        return "Banana: 100 Calories"

class Apple():
    def infos(self):
        return "Apple: 150 Calories"

```

---

### 🟡 Medium Example: Polymorphism with Loops

Objects in a list can understand the same command even if they are of different types.

```python
banana = Banana()
apple = Apple()
fruit_list = [banana, apple]

for fruit in fruit_list:
    print(fruit.infos())
# Output:
# Banana: 100 Calories
# Apple: 150 Calories

```

---

### 4️⃣ Encapsulation

Hiding data from the outside and allowing modification only through permitted ways. Done by adding __ (double underscore) before the variable.

---

### ✅ Easy Example: Defining Private Variables

```python
class Phone():
    def __init__(self, price):
        self.__price = price # Private variable

tel = Phone(500)
# print(tel.__price)
# ERROR: AttributeError (Cannot access directly from outside)

```

---

### 🟡 Medium Example: Getter and Setter Methods

Using intermediary functions to access or change the private variable.

```python
class Phone():
    def __init__(self, name, price):
        self.name = name
        self.__price = price # Private

    def info(self): # Getter
        print(f"{self.name} price: {self.__price}")

    def changePrice(self, new_price): # Setter
        self.__price = new_price

iphone = Phone("iPhone 14", 500)
iphone.changePrice(300) # Changed price safely
iphone.info()
# Output: iPhone 14 price: 300

```

---

### 5️⃣ Abstraction

Hiding details and providing only a template. Abstract classes cannot be instantiated; they only set rules for their children.

---

### ✅ Easy Example: Creating a Template

Using ABC (Abstract Base Class) and @abstractmethod.

```python
from abc import ABC, abstractmethod

class Car(ABC): # Abstract Class
    @abstractmethod
    def maxSpeed(self):
        pass # Do not fill, just set the rule

```

---

### 🔴 Hard Example: Mandatory Implementation

Any class inheriting from an abstract class MUST implement the @abstractmethod.

```python
class Tesla(Car):
    def maxSpeed(self):
        print("Speed: 200km/h")

class Mercedes(Car):
    def maxSpeed(self):
        print("Speed: 250km/h")

t = Tesla()
t.maxSpeed()
# Output: Speed: 200km/h

```

---

### 6️⃣ Special Methods (Magic Methods)

Allows integrating our classes with Python's built-in functions (len, print, indexing).

---

### ✅ Easy Example: **str** (Printing)

Determines what to display when an object is put into print().

```python
class Fruit():
    def __init__(self, name, calories):
        self.name = name
        self.calories = calories

    def __str__(self):
        return f"{self.name}: {self.calories} calories"

banana = Fruit("Banana", 150)
print(banana)
# Output: Banana: 150 calories

```

---

### 🟡 Medium Example: **len** (Length)

Determines how len() behaves with our class.

```python
class Fruit():
    def __init__(self, calories):
        self.calories = calories
    def __len__(self):
        return self.calories

banana = Fruit(150)
print(len(banana))
# Output: 150

```

---

### 🔴 Hard Example: **getitem** (Indexing)

Allows the class to behave like a list/dictionary and fetch data using obj["key"].

```python
class Train():
    def __init__(self, name):
        self.name = name

    def __getitem__(self, key):
        if key == "a":
            return self.name
        else:
            return "Not Found"

t = Train("Maglev")
print(t["a"])
print(t["b"])
# Output:
# Maglev
# Not Found

```

---
