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
