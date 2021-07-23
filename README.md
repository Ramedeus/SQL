# SQL (PostgreSQL / pgAdmin4)
SQL Örnekleri

Bu repo [Kodluyoruz](Kodluyoruz.org) SQL eğitimi için hazırlamış olduğum repo. İçerisinde SQL ödevlerinin soru ve cevaplarını içeren bir adet README dosyası barındırıyor.

Dvdrental Database linki:
```
https://www.postgresqltutorial.com/postgresql-sample-database/
```
Database Üretmek için link:
```
https://www.mockaroo.com/
```

| ÖDEVLER | 
| ----------- | 
| [ÖDEV 1](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-1) |
| [ÖDEV 2](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-2) |
| [ÖDEV 3](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-3) |
| [ÖDEV 4](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-4) |
| [ÖDEV 5](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-5) |
| [ÖDEV 6](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-6) |
| [ÖDEV 7](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-7) |
| [ÖDEV 8](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-8) |
| [ÖDEV 9](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-9) |

---

## :open_book: ÖDEV 1	

### SORU 1 :question:
Film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.

### :green_square: CEVAP 1

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```javascript
SELECT title, description FROM film;
```
</details>

### SORU 2 :question:
Film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.

### :green_square: CEVAP 2 

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT * FROM film
WHERE length > 60 AND length < 75;
```
</details>

### SORU 3 :question:
Film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.

### :green_square: CEVAP 3 

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT * FROM film
WHERE rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99;
```
</details>

### SORU 4 :question:
Customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

### :green_square: CEVAP 4 

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT * FROM customer
WHERE first_name = 'Mary' --Smith;
```
</details>

### SORU 5 :question:
Film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

### :green_square: CEVAP 5
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT * FROM film
WHERE length < 50 AND NOT rental_rate = 2.99 OR NOT rental_rate = 4.99;
```
</details>  

---

## :open_book: ÖDEV 2 

### SORU 1 :question:
Film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla
sıralayınız ( BETWEEN - AND yapısını kullanınız.)

### :green_square: CEVAP 1 
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT * FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.99;
```
</details> 

### SORU 2 :question:
Actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

### :green_square: CEVAP 2
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT first_name, last_name FROM actor
WHERE first_name IN ('Penelope', 'Nick', 'ED');
```
</details>   

### SORU 3 :question:
Film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. (IN operatörünü kullanınız.)

### :green_square: CEVAP 3 
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT * FROM film
WHERE rental_rate IN (0.99, 2.99, 4.99) AND replacement_cost IN (12.99, 15.99, 28.99);
```
</details>   

---

## :open_book: ÖDEV 3 	

### SORU 1 :question:
Country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

### :green_square: CEVAP 1
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT country  FROM country 
WHERE country LIKE 'A%a';
```
</details>  
  
### SORU 2 :question:
Country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

### :green_square: CEVAP 2 

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT country  FROM country 
WHERE country LIKE '_____%n';
```
</details>  

### SORU 3 :question:
Film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

### :green_square: CEVAP 3

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT title  FROM film  
WHERE title ILIKE '%t%t%t%t%';
```
</details>    

### SORU 4 :question:
Film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

### :green_square: CEVAP 4
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT *  FROM film  
WHERE title LIKE 'C%' AND length > 90 AND rental_rate IN (2.99);
```
</details> 
  
---

## :open_book: ÖDEV 4 	

### SORU 1 :question:
Film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

### :green_square: CEVAP 1 
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT DISTINCT	replacement_cost FROM film;
```
</details>
  
### SORU 2 :question:
Film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

### :green_square: CEVAP 2
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT COUNT (DISTINCT	replacement_cost) FROM film;
```
</details>
  
### SORU 3 :question:
Film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

### :green_square: CEVAP 3
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT COUNT (*) FROM film
WHERE title LIKE 'T%' AND rating = 'G';
```
</details>
  
### SORU 4 :question:
Country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

### :green_square: CEVAP 4

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT COUNT(*) FROM country
WHERE country LIKE '_____';
```
</details>
  
### SORU 5 :question:
City tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?

### :green_square: CEVAP 5

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT COUNT(*) FROM city
WHERE city ILIKE '%r';
```
</details>
  
---

## :open_book: ÖDEV 5 

### SORU 1 :question:
Film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

### :green_square: CEVAP 1 
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;
```
</details>
  
### SORU 2 :question:
Film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci 5 filmi sıralayınız.

### :green_square: CEVAP 2
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5;
```
</details>
  
### SORU 3 :question:
Customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

### :green_square: CEVAP 3
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT last_name, store_id FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4;
```
</details>
  
---

## :open_book: ÖDEV 6 	

### SORU 1 :question:
Film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

### :green_square: CEVAP 1

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT ROUND(AVG(rental_rate), 2) FROM film;
```
</details>
  
### SORU 2 :question:
Film tablosunda bulunan filmlerden kaçtanesi 'C' karekteri ile başlar?

### :green_square: CEVAP 2
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT COUNT(*) FROM film
WHERE title LIKE 'C%';
```
</details>
  
### SORU 3 :question:
Film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

### :green_square: CEVAP 3
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT title, rental_rate , length FROM film
WHERE rental_rate = 0.99
ORDER BY length DESC
LIMIT 3;
--3 farklı film mevcut ilgili şartları sağlayan. Ancak cevap değişmiyor.
```
</details>  
  
### SORU 4 :question:
Film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

### :green_square: CEVAP 4

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT DISTINCT(replacement_cost) FROM film
WHERE length > 150
ORDER BY replacement_cost ASC;
```
</details>  
  
---

## :open_book: ÖDEV 7 	

### SORU 1 :question:
Film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.

### :green_square: CEVAP 1
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT rating, COUNT(*) FROM film
GROUP BY rating;
```
</details> 
  
### SORU 2 :question:
Film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.
### :green_square: CEVAP 2 

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT replacement_cost, COUNT(*) FROM film
GROUP BY replacement_cost
HAVING COUNT(*) > 50;
```
</details>   

### SORU 3 :question:
Customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?

### :green_square: CEVAP 3
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT store_id, COUNT(*) FROM customer
GROUP BY store_id;
```
</details>

### SORU 4 :question:
City tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

### :green_square: CEVAP 4
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT country_id, COUNT(*) FROM city
GROUP BY country_id
ORDER BY COUNT(*) DESC
LIMIT 1;
```
</details>
 
  
## :open_book: ÖDEV 8 	

### SORU 1 :question:
Test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
  
### :green_square: CEVAP 1
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
CREATE TABLE employee (
	id INTEGER,
	name VARCHAR(50),
	birthday DATE,
	email VARCHAR(100)
);
```
</details> 
  
### SORU 2 :question:
Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
  
### :green_square: CEVAP 2 
[MOCKAROO](https://www.mockaroo.com/) kullanılarak elde edilen tablo verileri.
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
insert into employee (id, name, birthday, email) values (1, 'Rubetta Bewsey', '2019-03-27', 'rbewsey0@drupal.org');
insert into employee (id, name, birthday, email) values (2, 'Agnesse McNeill', '2006-12-29', 'amcneill1@toplist.cz');
insert into employee (id, name, birthday, email) values (3, 'Taylor Mew', '2006-10-18', 'tmew2@disqus.com');
insert into employee (id, name, birthday, email) values (4, 'Devina Walhedd', '1992-03-15', 'dwalhedd3@bluehost.com');
insert into employee (id, name, birthday, email) values (5, 'Kiel Goodrich', '2000-05-09', 'kgoodrich4@illinois.edu');
insert into employee (id, name, birthday, email) values (6, 'Karlis Capon', '1995-10-17', 'kcapon5@blogger.com');
insert into employee (id, name, birthday, email) values (7, 'Iver McGenis', '2012-08-29', 'imcgenis6@smugmug.com');
insert into employee (id, name, birthday, email) values (8, 'Ralf Bragg', '2002-07-20', 'rbragg7@reference.com');
insert into employee (id, name, birthday, email) values (9, 'Ninnetta Sparhawk', '2018-01-05', 'nsparhawk8@statcounter.com');
insert into employee (id, name, birthday, email) values (10, 'Mitchell McSherry', '2015-04-30', 'mmcsherry9@bloglovin.com');
insert into employee (id, name, birthday, email) values (11, 'Cathee Abys', '1991-12-19', 'cabysa@furl.net');
insert into employee (id, name, birthday, email) values (12, 'Monique Cantle', '2006-06-23', 'mcantleb@redcross.org');
insert into employee (id, name, birthday, email) values (13, 'Tyrus Haig', '2017-12-28', 'thaigc@nba.com');
insert into employee (id, name, birthday, email) values (14, 'Erma Bannerman', '1993-08-23', 'ebannermand@ning.com');
insert into employee (id, name, birthday, email) values (15, 'Saundra Almeida', '2003-04-23', 'salmeidae@bing.com');
insert into employee (id, name, birthday, email) values (16, 'Dallon Havick', '2003-06-18', 'dhavickf@earthlink.net');
insert into employee (id, name, birthday, email) values (17, 'Dulcie Polo', '2003-12-01', 'dpolog@ebay.com');
insert into employee (id, name, birthday, email) values (18, 'Loralyn Waber', '1992-01-19', 'lwaberh@ucoz.ru');
insert into employee (id, name, birthday, email) values (19, 'Luci Burghall', '1990-07-26', 'lburghalli@usa.gov');
insert into employee (id, name, birthday, email) values (20, 'Keefer Gilley', '2019-10-07', 'kgilleyj@rambler.ru');
insert into employee (id, name, birthday, email) values (21, 'Keenan Caswall', '2000-10-01', 'kcaswallk@yellowbook.com');
insert into employee (id, name, birthday, email) values (22, 'Cherri Haslewood', '2002-06-03', 'chaslewoodl@deliciousdays.com');
insert into employee (id, name, birthday, email) values (23, 'Clark Tiley', '2000-09-19', 'ctileym@huffingtonpost.com');
insert into employee (id, name, birthday, email) values (24, 'Mallory Damrell', '2019-03-08', 'mdamrelln@cdbaby.com');
insert into employee (id, name, birthday, email) values (25, 'Winnah Radcliffe', '2019-09-25', 'wradcliffeo@prnewswire.com');
insert into employee (id, name, birthday, email) values (26, 'Asia Balle', '1992-01-03', 'aballep@cafepress.com');
insert into employee (id, name, birthday, email) values (27, 'Joan Daulby', '2020-08-10', 'jdaulbyq@phoca.cz');
insert into employee (id, name, birthday, email) values (28, 'Estrellita Dally', '2017-02-11', 'edallyr@timesonline.co.uk');
insert into employee (id, name, birthday, email) values (29, 'Shayne Garralts', '2018-07-24', 'sgarraltss@gizmodo.com');
insert into employee (id, name, birthday, email) values (30, 'Erskine Hanssmann', '2019-04-11', 'ehanssmannt@mayoclinic.com');
insert into employee (id, name, birthday, email) values (31, 'Clare Lampbrecht', '1999-03-05', 'clampbrechtu@mayoclinic.com');
insert into employee (id, name, birthday, email) values (32, 'Shelbi Eouzan', '2002-02-13', 'seouzanv@ameblo.jp');
insert into employee (id, name, birthday, email) values (33, 'Reed Hartopp', '2007-02-14', 'rhartoppw@elegantthemes.com');
insert into employee (id, name, birthday, email) values (34, 'Vinnie Heelis', '2013-12-26', 'vheelisx@mashable.com');
insert into employee (id, name, birthday, email) values (35, 'Janel Dillway', '2019-05-24', 'jdillwayy@i2i.jp');
insert into employee (id, name, birthday, email) values (36, 'Kippie Blonfield', '2001-12-04', 'kblonfieldz@freewebs.com');
insert into employee (id, name, birthday, email) values (37, 'Marylou Oliver', '2009-09-21', 'moliver10@linkedin.com');
insert into employee (id, name, birthday, email) values (38, 'Dani Gasgarth', '2000-09-05', 'dgasgarth11@mediafire.com');
insert into employee (id, name, birthday, email) values (39, 'Maurie Grishenkov', '2016-04-03', 'mgrishenkov12@edublogs.org');
insert into employee (id, name, birthday, email) values (40, 'Egon Janata', '2019-04-12', 'ejanata13@etsy.com');
insert into employee (id, name, birthday, email) values (41, 'Christal Cohen', '2018-03-27', 'ccohen14@so-net.ne.jp');
insert into employee (id, name, birthday, email) values (42, 'Gnni Wickey', '1992-09-09', 'gwickey15@yellowbook.com');
insert into employee (id, name, birthday, email) values (43, 'Cameron Nazaret', '1992-11-27', 'cnazaret16@artisteer.com');
insert into employee (id, name, birthday, email) values (44, 'Adele Ovett', '2003-01-05', 'aovett17@wufoo.com');
insert into employee (id, name, birthday, email) values (45, 'Georgy Kersey', '2007-10-23', 'gkersey18@gnu.org');
insert into employee (id, name, birthday, email) values (46, 'Dari Jephson', '2013-04-08', 'djephson19@qq.com');
insert into employee (id, name, birthday, email) values (47, 'Madalyn Simmins', '2006-07-30', 'msimmins1a@hibu.com');
insert into employee (id, name, birthday, email) values (48, 'Robinia Segar', '2007-08-17', 'rsegar1b@ted.com');
insert into employee (id, name, birthday, email) values (49, 'Gav Crickmore', '2000-05-08', 'gcrickmore1c@ft.com');
insert into employee (id, name, birthday, email) values (50, 'Audy Mauro', '2004-01-30', 'amauro1d@nymag.com');

```
</details>   

### SORU 3 :question:
Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
  
### :green_square: CEVAP 3
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
--1. Örnek
UPDATE employee
SET name = 'XXXX YYYY' 
WHERE id = 1
RETURNING *;

--2. Örnek
UPDATE employee
SET birthday = '1111-11-11' 
WHERE name LIKE 'A%'
RETURNING *;

--3. Örnek  
UPDATE employee
SET email = 'null' 
WHERE name = 'Taylor Mew'
RETURNING *;

--4. Örnek
UPDATE employee
SET name = 'Devina Walhedd',
	birthday = '2000-02-02',
	email = 'devj@walhedd.com'
WHERE name = 'Devina J. Walhedd'
RETURNING *;

--5. Örnek  
UPDATE employee
SET name = 'DELETED',
	birthday = '0001-01-01',
	email = 'null'
WHERE id between 5 and 7
RETURNING *;
```
</details>

### SORU 4 :question:
Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

### :green_square: CEVAP 4
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
--1. Örnek
DELETE FROM employee
WHERE id = 8
RETURNING *;

--2. Örnek
DELETE FROM employee
WHERE name LIKE '%k'
RETURNING *;

--3. Örnek
DELETE FROM employee
WHERE birthday > '2019-01-01'
RETURNING *;

--4. Örnek
DELETE FROM employee
WHERE email = 'null' OR name = 'DELETED'
RETURNING *;

--5. Örnek
DELETE FROM employee
WHERE name = 'Devina J. Walhedd' AND birthday = '2000-02-02' AND email = 'devj@walhedd.com'
RETURNING *;

--6. Örnek (Bir tane fazla olmuş :) )
DELETE FROM employee
WHERE birthday = '1111-11-11'
RETURNING *;
```
</details>  

## :open_book: ÖDEV 9 	

### SORU 1 :question:
City tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
	
### :green_square: CEVAP 1
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT city, country FROM city
INNER JOIN country ON city.city_id = country.country_id;
```
</details> 
  
### SORU 2 :question:
Customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

### :green_square: CEVAP 2 

<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT payment_id, first_name, last_name FROM customer 
INNER JOIN payment ON payment.customer_id = customer.customer_id;
```
</details>   

### SORU 3 :question:
customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

### :green_square: CEVAP 3
  
<details>
<summary>Kodu görmek için tıklayınız.</summary>
  
```java
SELECT rental_id, first_name, last_name FROM customer 
INNER JOIN rental ON rental.customer_id = customer.customer_id;
```
</details>
  
---

## Contributing :hammer_and_wrench:	
Hatalar, öneriler ve değişiklikler için lütfen bir konu açınız.

## License :notebook_with_decorative_cover:

[MIT](https://www.google.com/search?q=mit+license&oq=mit+license&aqs=chrome.0.0l4j0i22i30l6.2910j0j7&sourceid=chrome&ie=UTF-8)


![Lorem Picsum](https://picsum.photos/200/300)
