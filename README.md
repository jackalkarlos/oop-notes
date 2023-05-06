Kaynak: https://www.youtube.com/watch?v=7XF4lnUHzc4&ab_channel=Python%27aGiri%C5%9F

# oop-notes

<h2>Class:</h2> 

Classlar, ortak özellikleri olan nesneleri kategorilere ayırdığımız bir kavramdır. Classlar form şablonu gibi düşünülebilir.

Örneğin <u>Kırmızı</u> Class'ı için:

Kırmızı elma,
Kırmızı kalem,

örneği verilebilir.

Örneğin <u>Turuncu</u> Class'ı için:

Turuncu portakal,
Turuncu elma,

örneği verilebilir.

<h2>Instance:</h2>

Class'tan üretilmiş nesnelere Instance adı verilir. "Turuncu" class'ından üretilen "Turuncu Portakal" nesnesi bir Instance'dir.

Örnek Class Şablonu ve Instance'leri

Müşteri Class'ı
```
	Müşteri
------------------
	Adı
	Soyadı
	Yaşı
	Mail
```

Müşteri Class'ı için Instance'ler

```
	Müşteri
------------------
	Ali
	Veli
	30
	benbir@instanceyim.com
```

Python için Boş Class ve Instance Oluşturma

```py
class calisan: //boş bir class
	pass

calisan1=calisan() //bir instance
```

Python için Kullanışlı bir Class ve Instance oluşturma

Bu kodda "calisan" adında bir class'ımız var. Classlar çağırıldığında otomatik olarak ilk devreye giren fonksiyon  `__init__` fonksiyonudur. 

`__init__` fonksiyonu bu aşamada bizden 4 adet bilgi bekliyor. "self","name","surname","age". 

"self": Instance'mizin adıdır. Otomatik olarak gönderilir. Class içerisindeki fonksiyonu kullanırken ekstradan göndermeye gerek yoktur.

Bu durumda fonksiyonla birlikte `"Ali","Veli", 20` bilgisini gönderip ilgili class'da tanımlamamız mümkündür.

Kod'un çalışması class içerisinde şu hale gelmekte: 
`calisan1.name = "fonksiyonla birlikte gönderdiğimiz isim"` 

```py
class calisan:
  def __init__(self,name,surname,age): //self parametresi instance'nin kendisidir.
		print("__init__ çalışıyor.")
		self.name = name
		self.surname = surname
		self.age = age
		
calisan1=calisan("Ali","Veli",20)
```

Farkı daha iyi ayırt edebilmeniz için:

```py
class calisan:
  def __init__(self,a,b,c): //self parametresi instance'nin kendisidir.
		print("__init__ çalışıyor.")
		self.name = a
		self.surname = b
		self.age = c
		
calisan1=calisan("Ali","Veli",20)
```

<h2>Attribute</h2>

Attribute nitelik anlamı taşır.

"name" bir attribute'dir, isim niteliğidir.
"surname" bir attribute'dir, soyisim niteliğidir.
"age" bir attribute'dir, yaş niteliğidir.

```py
class calisan:
  def __init__(self,name,surname,age):
		print("__init__ çalışıyor.")
		self.name = name
		self.surname = surname
		self.age = age
		
calisan1=calisan("Ali","Veli",20)
```
