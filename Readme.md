# Data Manipülasyon Komutları

**SELECT** : Veritabanındaki tablolardan kayıtları seçmek için kullanılır.

**UPDATE** : Veritabanındaki tablolardaki kayıtları güncellemek için kullanılır.

**DELETE** : Veritabanındaki tablolardaki kayıtları silmek için kullanılır.

**INSERT** : Veritabanındaki tablolara yeni kayıt eklemek için kullanılır.

**TRUNCATE** : Veritabanındaki tablonun içini boşaltmak için kullanılır.

# Veritabanı Manipülasyon Komutları

**CREATE** : Veritabanı oluşturmak için kullanılır.

**ALTER** : Veritabanındaki özelliği değiştirmek için kullanılır.

**DROP** : Veritabanını silmek için kullanılır.

**CREATE DATABASE** : Yeni veritabanı oluşturmak için kullanılır.

**ALTER DATABASE** : Veritabanındaki özelliği değiştirmek için kullanılır.

**CREATE TABLE** : Yeni tablo oluşturmak için kullanılır.

**ALTER TABLE** : Tablodaki özelliği değiştirmek için kullanılır.

**DROP TABLE** : Tabloyu silmek için kullanılır.

**CREATE INDEX** : Tablodaki kolonlara indeks oluşturmak için kullanılır.

**DROP INDEX** : Tablodaki indeksi silmek için kullanılır.

---

### SELECT

Verileri seçmek için kullanılır. SELECT komutu ile veritabanındaki tablolardan kayıtları seçebiliriz. 

#### Syntax

```sql
SELECT KOLON1, KOLON2, KOLON3 FROM TABLO_ADI WHERE KOŞUL

SELECT * FROM TABLO_ADI WHERE KOŞUL
```

### INSERT

Verileri eklemek için kullanılır. INSERT komutu ile veritabanındaki tablolara yeni kayıt ekleyebiliriz.

#### Syntax

```sql
INSERT INTO TABLO_ADI (KOLON1, KOLON2, KOLON3) VALUES (DEĞER1, DEĞER2, DEĞER3)
```

### UPDATE

Verileri güncellemek için kullanılır. UPDATE komutu ile veritabanındaki tablolardaki kayıtları güncelleyebiliriz.

#### Syntax

```sql
UPDATE TABLO_ADI SET KOLON1 = DEĞER1, KOLON2 = DEĞER2 WHERE KOŞUL
```

### DELETE

Verileri silmek için kullanılır. DELETE komutu ile veritabanındaki tablolardaki kayıtları silebiliriz.

#### Syntax

```sql
DELETE FROM TABLO_ADI WHERE KOŞUL
```

### TRUNCATE

Verileri silmek için kullanılır. TRUNCATE komutu ile veritabanındaki tablonun içini boşaltabiliriz.

#### Syntax

```sql
TRUNCATE TABLE TABLO_ADI
```

### WHERE

Verileri filtrelemek için kullanılır. WHERE komutu ile veritabanındaki tablolardaki kayıtları filtreleyebiliriz.

#### Syntax

```sql
SELECT * FROM TABLO_ADI WHERE KOŞUL
SELECT KOLON1, KOLON2, KOLON3 FROM TABLO_ADI WHERE KOŞUL
```
#### Örnekler

```sql
SELECT * FROM Customers WHERE Country='Germany'
```

= : Eşittir
  
```sql
SELECT * FROM Customers WHERE CustomerID=1
```
<> : Eşit değildir

```sql
SELECT * FROM Customers WHERE CustomerID<>1
```

> : Büyüktür

```sql
SELECT * FROM Customers WHERE CustomerID>1
```

< : Küçüktür

```sql
SELECT * FROM Customers WHERE CustomerID<1
```

>= : Büyük eşittir

```sql
SELECT * FROM Customers WHERE CustomerID>=1
```

<= : Küçük eşittir

```sql
SELECT * FROM Customers WHERE CustomerID<=1
```

BETWEEN : Arasındadır

```sql
SELECT * FROM Customers WHERE CustomerID BETWEEN 1 AND 5
```

LIKE : İle başlar, ile bitirir, içerir

```sql
SELECT * FROM Customers WHERE CustomerName LIKE 'ahmet%'
```

IN : Bir değerden bir veya daha fazla değer içerir

```sql
SELECT * FROM Customers WHERE Country IN ('Germany', 'France', 'UK')
```

NOT LIKE : İle başlamaz, ile bitmez, içermez

```sql
SELECT * FROM Customers WHERE CustomerName NOT LIKE 'ahmet%'
```

NOT IN : Bir değerden bir veya daha fazla değer içermez

```sql
SELECT * FROM Customers WHERE Country NOT IN ('Germany', 'France', 'UK')
```

AND : Ve

```sql
SELECT * FROM Customers WHERE Country='Germany' AND City='Berlin'
```

OR : Veya

```sql
SELECT * FROM Customers WHERE Country='Germany' OR Country='France'
```

### DISTINCT

Verileri filtrelemek için kullanılır. DISTINCT komutu ile veritabanındaki tablolardaki kayıtları filtreleyebiliriz.
Birden fazla aynı değeri içeren kayıtları tek bir kayıt olarak gösterir.

#### Syntax

```sql
SELECT DISTINCT KOLON1, KOLON2, KOLON3 FROM TABLO_ADI WHERE KOŞUL
```

#### Örnekler

```sql
SELECT DISTINCT Country FROM Customers
// Aynı ülke birden fazla kez yazılmışsa sadece bir kez yazdırır.
```

### ORDER BY

Verileri sıralamak için kullanılır. ORDER BY komutu ile veritabanındaki tablolardaki kayıtları sıralayabiliriz.

#### Syntax

```sql
SELECT * FROM TABLO_ADI ORDER BY KOLON1, KOLON2, KOLON3

SELECT KOLON1, KOLON2, KOLON3 FROM TABLO_ADI ORDER BY KOLON1, KOLON2, KOLON3

SELECT KOLON1, KOLON2, KOLON3 FROM TABLO_ADI WHERE KOŞUL ORDER BY KOLON1, KOLON2, KOLON3
```

ASC : A-Z Küçükten büyüğe göre sıralar. (Varsayılan olarak kullanılır.)

```sql
SELECT * FROM Customers ORDER BY Country ASC
```

DESC : Z-A Büyükten küçüğe göre sıralar.

```sql
SELECT * FROM Customers ORDER BY Country DESC
```

### TOP

Verileri belli bir sayıda sıralamak için kullanılır. TOP komutu ile veritabanındaki tablolardaki kayıtları sıralayabiliriz.

#### Syntax

```sql
SELECT TOP N KOLON1, KOLON2, KOLON3 FROM TABLO_ADI WHERE KOŞUL 
```

N : Sıralanacak kayıt sayısı

#### Örnekler

```sql
SELECT TOP 3 * FROM Customers
// Üç kayıt sıralar.
```

```sql
SELECT TOP 50 PERCENT * FROM Customers WHERE Country='Germany'
// Almanya'dan gelenlerin yüzde 50'sini sıralar.
```

### AGGREGATE FUNCTIONS

Verileri toplamak, ortalama almak, en büyük, en küçük değerleri bulmak için kullanılır. AGGREGATE FUNCTIONS komutu ile veritabanındaki tablolardaki kayıtları toplayabiliriz.

#### Syntax

```sql
SELECT SUM(KOLON1), AVG(KOLON2), MAX(KOLON3), MIN(KOLON4) FROM TABLO_ADI 
```

#### Örnekler

```sql
SELECT SUM(Quantity) FROM OrderDetails
// Quantity toplamını sıralar.
```

```sql
SELECT AVG(Quantity) FROM OrderDetails
// Quantity ortalamasını sıralar.
```

```sql
SELECT MAX(Quantity) FROM OrderDetails
// Quantity en büyük değerini sıralar.
```

```sql
SELECT MIN(Quantity) FROM OrderDetails
// Quantity en küçük değerini sıralar.
```

```sql
SELECT COUNT(*) FROM Customers
// Müşteri sayısını sıralar.
```

### GROUP BY

Verileri gruplamak için kullanılır. GROUP BY komutu ile veritabanındaki tablolardaki kayıtları gruplayabiliriz.

#### Syntax

```sql
SELECT KOLON1, KOLON2 SUM(KOLON3) FROM TABLO_ADI GROUP BY KOLON1, KOLON2
```

#### Örnekler

```sql
SELECT Country, COUNT(*) FROM Customers GROUP BY Country
// Ülkelere göre müşteri sayısını sıralar.
```

```sql
SELECT Country, SUM(TotalPrice) FROM Orders GROUP BY Country ORDER BY SUM(TotalPrice) DESC

// Ülkelere göre toplam satış miktarını azalan sırada sıralar.
```

```sql
SELECT TOP 10 Country, SUM(TotalPrice) FROM Orders GROUP BY Country ORDER BY SUM(TotalPrice) DESC

// Ülkelere göre toplam satış miktarını azalan sırada sıralar. Sadece ilk 10 kaydı gösterir.
```

Bir şehrin günlere göre toplam satışları ;

```sql
SELECT City, OrderDate, SUM(TotalPrice) FROM Orders WHERE City ="Berlin" GROUP BY City, OrderDate

// Berlin'deki günlere göre toplam satış miktarını sıralar.
```

Ör: Bir günün şehir bazlı satış rakamlarını göstermek istiyorsak ;

```sql
SELECT City, OrderDate, SUM(TotalPrice) FROM Orders WHERE OrderDate = "2012-07-04" GROUP BY City, OrderDate

// 2012-07-04 tarihindeki şehirlere göre toplam satış miktarını sıralar.
```

Ör: Şehirlerin aylara göre toplam satış rakamlarını göstermek istiyorsak ;

```sql
SELECT City, MONTH(OrderDate) AS Month, SUM(TotalPrice) FROM Orders GROUP BY City, MONTH(OrderDate)

// Şehirlerin aylara göre toplam satış miktarını sıralar.
```

Ör: Ürün kategorilerine göre satış rakamlarını getirmek istiyorsak ;

```sql
SELECT CategoryName, SUM(TotalPrice) AS Total FROM Orders GROUP BY CategoryName ORDER BY Total DESC

// Ürün kategorilerine göre toplam satış miktarını azalan sırada sıralar.
```

Ör: Şehirlerin müşteri sayılarını getirmek istiyorsak ;

```sql
SELECT City, COUNT(*) AS Total FROM Customers GROUP BY City ORDER BY Total DESC

// Şehirlere göre müşteri sayısını azalan sırada sıralar.
```

Ör: Belirli bir cironu üzerinde satış yapan şehirleri getirmek istiyorsak ;

```sql
SELECT City, SUM(TotalPrice) AS Total FROM Orders GROUP BY City HAVING SUM(TotalPrice) > 100000

// 100.000 TL üzerinde satış yapan şehirleri sıralar.
```

## Veri Tipleri

### bigint

Tamsayı veri tipidir. 8 byte yer kaplar. -2^63 ile 2^63-1 arasında değer alır.

### int

Tamsayı veri tipidir. 4 byte yer kaplar. -2^31 ile 2^31-1 arasında değer alır.

### smallint

Tamsayı veri tipidir. 2 byte yer kaplar. -2^15 ile 2^15-1 arasında değer alır.

### tinyint

Tamsayı veri tipidir. 1 byte yer kaplar. 0 ile 255 arasında değer alır.

### bit

0 ve 1 değerlerini alır. 1 byte yer kaplar.

### decimal / numeric

Ondalıklı sayı veri tipidir. 1 byte yer kaplar. -10^38 ile 10^38 arasında değer alır.

### money

Ondalıklı sayı veri tipidir. 8 byte yer kaplar. -922337203685477.5808 ile 922337203685477.5807 arasında değer alır.

### smallmoney

Ondalıklı sayı veri tipidir. 4 byte yer kaplar. -214748.3648 ile 214748.3647 arasında değer alır.

### float

Ondalıklı sayı veri tipidir. 8 byte yer kaplar. -1.79E + 308 ile 1.79E + 308 arasında değer alır.

### real

Ondalıklı sayı veri tipidir. 4 byte yer kaplar. -3.40E + 38 ile 3.40E + 38 arasında değer alır.

### varchar

Değişken uzunluklu karakter veri tipidir.

### char

Sabit uzunluklu karakter veri tipidir. 

### date 

Tarih veri tipidir. 4 byte yer kaplar.

### smalldate

Tarih veri tipidir. 3 byte yer kaplar.

### datetime

Tarih ve zaman veri tipidir. 8 byte yer kaplar.

### datetime2

Tarih ve zaman veri tipidir. 8 byte yer kaplar.

### datetimeoffset

Tarih ve zaman veri tipidir. 10 byte yer kaplar.

### time

Zaman veri tipidir. 5 byte yer kaplar.

## İlişkisel Veri Tabanı

İlişkisel veri tabanı, verileri tablolar arasında ilişkiler oluşturarak tutan veri tabanıdır. Tablolar arasında ilişkiler oluşturmak için tablolar arasında ilişki kurulacak alanları belirlemek gerekir. Bu alanlara anahtar alan denir. 

Örnek Kullanıcı Tablosu;

|    ID     | Name | Surname |   AddressID   |
|-----------|------|---------|---------------|
|    1      | Joe  | Doe     |       1       |
|    2      | John | Doe     |       2       |

Adres tablosu;

|    ID     | Address |   City   |
|-----------|---------|----------|
|    1      | 123     | New York |
|    2      | 456     | New York |

AddressID alanı kullanıcı tablosunda adres tablosunun ID alanı ile ilişkilendirilmiştir. 

**Primary Key (Anahtar Alan)** : Tabloda benzersiz değer tutan alanlara denir.

**Foreign Key (Yabancı Anahtar)** : İlişkili tabloların anahtar alanlarına denir.

AddressID alanı kullanıcı tablosunda _foreign key (yabancı anahtar)_ olarak kullanılmıştır.

### Script ile Tablo Oluşturma

CREATE TABLE _tablo_adi_ (
  _kolon_adi_ _veri_tipi_,
  _kolon_adi_ _veri_tipi_, 
  ...
);

```sql
CREATE TABLE Customers (
    ID int IDENTITY(1,1) PRIMARY KEY,
    Name varchar(50) NOT NULL,
    Surname varchar(50) NOT NULL,
    AddressID int FOREIGN KEY REFERENCES Addresses(ID)
)
```

Çıktı;

|    ID     | Name | Surname |   AddressID   |
|-----------|------|---------|---------------|
|    1      | Joe  | Doe     |       1       |
|    2      | John | Doe     |       2       |


### Alias Kullanımı

Tabloların kolonlarını kullanırken kolon adı yerine alias kullanılabilir. Alias, kolonun takma adıdır. Alias kullanmak için kolon adının yanına AS anahtar kelimesi ile takma adı yazılır.

```sql
SELECT U.Name, U.Surname, A.Cities FROM Users AS U, Addresses AS A WHERE U.ID = A.UserID AND U.Name = 'Joe'

// 'Joe' isimli kullanıcının adı, soyadı ve adresi sıralanır.
```

**İlişkisel Tablolardan Veri Sorgulama ;**

```sql
SELECT
A.KOLON1, A.KOLON2, B.KOLON3, B.KOLON4 ...
FROM TABLO1 AS A
JOIN TABLO2 AS B ON A.PRIMARY_KEY = B.FOREIGN_KEY
```

Örnek;

```sql
SELECT
U.Name, U.Surname, A.Address, A.City
FROM Users U
JOIN Addresses A ON U.ID = A.UserID
```

#### INNER JOIN

İki tablodaki ilişkili alanlara göre verileri birleştirir.

```sql
SELECT
A.KOLON1, A.KOLON2, B.KOLON3, B.KOLON4 ...
FROM TABLO1 AS A
INNER JOIN TABLO2 AS B ON A.PRIMARY_KEY = B.FOREIGN_KEY
```

#### LEFT JOIN

İki tablodaki ilişkili alanlara göre verileri birleştirir. Sol tablodaki tüm verileri getirir.

```sql
SELECT
A.KOLON1, A.KOLON2, B.KOLON3, B.KOLON4 ...
FROM TABLO1 AS A
LEFT JOIN TABLO2 AS B ON A.PRIMARY_KEY = B.FOREIGN_KEY

// A tablosundaki tüm verileri getirir.
```

#### RIGHT JOIN

İki tablodaki ilişkili alanlara göre verileri birleştirir. Sağ tablodaki tüm verileri getirir.

```sql
SELECT
A.KOLON1, A.KOLON2, B.KOLON3, B.KOLON4 ...
FROM TABLO1 AS A
RIGHT JOIN TABLO2 AS B ON A.PRIMARY_KEY = B.FOREIGN_KEY

// B tablosundaki tüm verileri getirir.
```

#### FULL JOIN

İki tablodaki ilişkili alanlara göre verileri birleştirir. İki tablodaki tüm verileri getirir.

```sql
SELECT
A.KOLON1, A.KOLON2, B.KOLON3, B.KOLON4 ...
FROM TABLO1 AS A
FULL JOIN TABLO2 AS B ON A.PRIMARY_KEY = B.FOREIGN_KEY

// A ve B tablosundaki tüm verileri getirir.
```

### String Fonksiyonları

#### ASCII

Verilen karakterin ASCII değerini döndürür.

```sql
SELECT ASCII('A')

// 65
```

#### CHAR

Verilen ASCII değerine karşılık gelen karakteri döndürür.

```sql
SELECT CHAR(65)

// A
```

#### SUBSTRING

Verilen karakter dizisinden belirtilen karakter aralığını döndürür.

```sql
SELECT SUBSTRING('Hello World', 1, 5)

// Hello
```

#### LEN

Verilen karakter dizisinin uzunluğunu döndürür.

```sql
SELECT LEN('Hello World')

// 11
```

#### CHARINDEX

Verilen karakter dizisinde aranan karakterin ilk bulunduğu indeksi döndürür.

```sql
SELECT CHARINDEX('o', 'Hello World')

// 5
```

#### CONCAT

Verilen karakter dizilerini birleştirir.

```sql
SELECT CONCAT('Hello', 'World')

// HelloWorld
```

#### FORMAT

Verilen sayıyı belirtilen formata göre döndürür.

```sql
SELECT FORMAT(123456.789, 'C')

// $123,456.79
```

#### LEFT, RIGHT

Verilen karakter dizisinden belirtilen karakter sayısını döndürür.

```sql
SELECT LEFT('Hello World', 5)

// Hello

SELECT RIGHT('Hello World', 5)

// World
```

#### REPLACE

Verilen karakter dizisinde aranan karakteri değiştirir.

```sql
SELECT REPLACE('Hello World', ' ', '-')

// Hello-World
``` 
