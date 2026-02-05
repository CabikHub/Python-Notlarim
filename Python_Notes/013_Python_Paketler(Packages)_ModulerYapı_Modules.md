# 📦 Python: Paketler (Packages) ve Modüler Yapı

Bu notlar, Python projelerini klasörler (paketler) halinde düzenlemeyi ve `__name__ == "__main__"` kontrolünün derinlemesine mantığını içerir.

## 1. Paket (Package) Nedir?

Python'da scriptleri (kod dosyalarını) düzenli tutmak için klasörler kullanılır. Bir klasörün Python paketi sayılması için içinde `__init__.py` dosyası olması gerekir.

- **Klasör:** Sıradan dosya saklama alanı.
- **Paket:** İçinde `__init__.py` olan, Python'un tanıdığı kod kütüphanesi.

### Yapı Örneği

```
ProjeKlasörü/
├── main.py                <-- Ana Çalıştırma Dosyası
├── AnimalPackage/         <-- Ana Paket
│   ├── __init__.py        <-- "Ben bir paketim" etiketi
│   ├── info.py            <-- Modül
│   └── CatPackage/        <-- Alt Paket (Sub-package)
│       ├── __init__.py
│       └── Meow.py        <-- Modül
```

## 2. Import İşlemleri

İç içe klasörlerden dosya çağırmak için "nokta" (`.`) operatörü kullanılır.

```python
# AnimalPackage klasöründeki info.py dosyasını çağır
from AnimalPackage import info

# AnimalPackage içindeki CatPackage klasöründeki Meow.py dosyasını çağır
from AnimalPackage.CatPackage import Meow
```

## 3. `if __name__ == "__main__"` ve Import Farkı

Bir Python dosyası iki şekilde çalışabilir:

1. **Doğrudan:** Terminalden `python dosya.py` diyerek.
2. **Import Edilerek:** Başka bir dosyanın içinden `import dosya` diyerek.

Kodun davranışını buna göre değiştirebiliriz:

```python
# Meow.py dosyası

def speak_direct():
    print("Ben direkt çalıştırıldım! (Patron benim)")

def speak_imported():
    print("Ben import edildim! (Misafirim)")

# KONTROL NOKTASI
if __name__ == "__main__":
    # Dosya direkt çalıştırılırsa burası çalışır
    speak_direct()
else:
    # Dosya import edilirse burası çalışır
    speak_imported()
```

---

### 1. Paketleme (Packaging): "Klasörlerle Düzen Sağlamak"

Senin `AnimalPackage` bir klasör. İçine `CatPackage` diye bir klasör daha açmışsın.

- Normalde bilgisayarda klasör açmak sadece dosya düzenidir.
- Ama Python'da bir klasörün içine **`__init__.py`** koyarsan, Python o klasörü artık sıradan bir klasör değil, bir **"Paket" (Package)** olarak görür.
- **Ders:** Kodlarını tek bir dosyaya yığmak yerine, konularına göre (Hayvanlar -> Kediler -> Miyavlama) klasörlere ayırarak yönetmeyi göstermiş.

### 2. Derinlemesine Import (Nested Imports)

`main.py` dosyasındaki şu satıra bak:
`from AnimalPackage.CatPackage import Meow`

- Burada Python'a adres tarif ediyorsun: "AnimalPackage ilçesine git, oradan CatPackage mahallesine gir, oradaki Meow binasını (dosyasını) getir."
- **Ders:** İç içe klasörlerdeki dosyalara nasıl ulaşacağını göstermiş.

### 3. "Kim Çağırdı?" Kontrolü (`if __name__ == "__main__"`)

En kritik yer `Meow.py` içindeki şu kısım:

```python
if __name__ == "__main__":
    speak_direct()  # Dosyayı direkt çalıştırırsan burası
else:
    speak_imported() # Başka yerden çağırırsan (import) burası
```

- Sen `main.py`'yi çalıştırdığında, `Meow` dosyasını **import** ediyorsun (çağırıyorsun).
- Python `Meow.py` dosyasına gidiyor. Bakıyor ki bu dosya "Ana dosya" değil, "Misafir" (import edilmiş).
- O yüzden `else` kısmına düşüyor ve **"meow imported"** yazıyor.
- **Ders:** Bir dosya direkt mi çalıştırıldı, yoksa başka bir dosya tarafından mı çağrıldı? Bunu nasıl ayırt edeceğini göstermiş.