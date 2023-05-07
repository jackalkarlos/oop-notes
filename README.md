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

<h2>Python için Kullanışlı bir Class ve Instance oluşturma</h2>

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

<h2> Class Methodları </h2>

```py
class calisan:
	def __init__(self,name,surname,age):
		self.name = name
		self.surname = surname
		self.age = age
	def show_info(self):
		print(f"Ad: {self.name}, Soyad: {self.surname}, Yaş: {self.age}")

worker1=calisan("Ali","Veli",20)

worker1.show_info() //Instance üzerinden show_info method çağrısı çağırılıyor.

calisan.show_info(worker1) //Class methodu çağırılıyor ve calisan1 değeri gönderiliyor,	
```

Sondaki her 2 komutta aynı çıktıyı verecektir. Amaç, bir class içerisinde fonksiyon tanımlayarak bunu self değerine göre çağırmaktır.

Değerlerimizden biri girilmezse, veya default bir değere sahip olmasını istersekte aşağıdaki gibi bir yaklaşım sergileyebiliriz.

```py
class calisan:
	def __init__(self,name,surname="soyisim girilmedi",age=0):
		self.name = name
		self.surname = surname
		self.age = age
	def show_info(self):
		print(f"Ad: {self.name}, Soyad: {self.surname}, Yaş: {self.age}")

worker1=calisan("Ali")

worker1.show_info()
```

Output:

```
Ad: Ali, Soyad: soyisim girilmedi, Yaş: 0
```


<h3> Method Input Sırası </h3>

Normalde inputları sıraya göre veririz ancak soyadı kısmını atlamak istiyorsak aşağıdaki gibi bir kullanım sergileyebiliriz.

```py
worker1=calisan("Ali",age=20)
```

<h2> Instance Variables </h2>

Nesnelerin değişkeni demektir.

`self.name` bir instance variable'dir.

Instance variable'leri bir sözlük halinde görüntülemek için:

```
print(calisan1.__dict__)
```
