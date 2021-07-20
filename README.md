# SQL
SQL Examples

Bu repo [Kodluyoruz](Kodluyoruz.org) SQL eğitimi için hazırlamış olduğum repo. İçerisinde SQL ödevlerinin soru ve cevaplarını içeren bir adet README dosyası barındırıyor.

Dvdrental Database linki:
```
https://www.postgresqltutorial.com/postgresql-sample-database/
```

| ÖDEVLER      |
| ----------- |
| [ÖDEV 1](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-1) |
| [ÖDEV 2](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-2) |
| [ÖDEV 3](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-3) |
| [ÖDEV 4](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-4) |
| [ÖDEV 5](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-5) |
| [ÖDEV 6](https://github.com/Ramedeus/SQL/blob/main/README.md#open_book-%C3%B6dev-6) |

---

## :open_book: ÖDEV 1	

### SORU 1 :question:
Film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.

### :green_square: CEVAP 1 
```
SELECT title, description FROM film;
```

### SORU 2 :question:
Film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.

### :green_square: CEVAP 2 
```
SELECT * FROM film
WHERE length > 60 AND length < 75;
```

### SORU 3 :question:
Film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.

### :green_square: CEVAP 3 
```
SELECT * FROM film
WHERE rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99;
```

### SORU 4 :question:
Customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

### :green_square: CEVAP 4 
```
SELECT * FROM customer
WHERE first_name = 'Mary' --Smith;
```

### SORU 5 :question:
Film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

### :green_square: CEVAP 5 
```
SELECT * FROM film
WHERE length < 50 AND NOT rental_rate = 2.99 OR NOT rental_rate = 4.99;
```

---

## :open_book: ÖDEV 2 

### SORU 1 :question:
Film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla
sıralayınız ( BETWEEN - AND yapısını kullanınız.)

### :green_square: CEVAP 1 
```
SELECT * FROM film
WHERE replacement_cost BETWEEN 12.99 AND 16.99;
```

### SORU 2 :question:
Actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

### :green_square: CEVAP 2 
```
SELECT first_name, last_name FROM actor
WHERE first_name IN ('Penelope', 'Nick', 'ED');
```

### SORU 3 :question:
Film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. (IN operatörünü kullanınız.)

### :green_square: CEVAP 3 
```
SELECT * FROM film
WHERE rental_rate IN (0.99, 2.99, 4.99) AND replacement_cost IN (12.99, 15.99, 28.99);
```

---

## :open_book: ÖDEV 3 	

### SORU 1 :question:
Country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

### :green_square: CEVAP 1 
```
SELECT country  FROM country 
WHERE country LIKE 'A%a';
```

### SORU 2 :question:
Country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

### :green_square: CEVAP 2 
```
SELECT country  FROM country 
WHERE country LIKE '_____%n';
```

### SORU 3 :question:
Film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

### :green_square: CEVAP 3 
```
SELECT title  FROM film  
WHERE title ILIKE '%t%t%t%t%';
```

### SORU 4 :question:
Film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

### :green_square: CEVAP 4 
```
SELECT *  FROM film  
WHERE title LIKE 'C%' AND length > 90 AND rental_rate IN (2.99);
```

---

## :open_book: ÖDEV 4 	

### SORU 1 :question:
Film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

### :green_square: CEVAP 1 
```
SELECT DISTINCT	replacement_cost FROM film;
```

### SORU 2 :question:
Film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

### :green_square: CEVAP 2 
```
SELECT COUNT (DISTINCT	replacement_cost) FROM film;
```

### SORU 3 :question:
Film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

### :green_square: CEVAP 3 
```
SELECT COUNT (*) FROM film
WHERE title LIKE 'T%' AND rating = 'G';
```

### SORU 4 :question:
Country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

### :green_square: CEVAP 4 
```
SELECT COUNT(*) FROM country
WHERE country LIKE '_____';
```

### SORU 5 :question:
City tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?

### :green_square: CEVAP 5 
```
SELECT COUNT(*) FROM city
WHERE city ILIKE '%r';
```

---

## :open_book: ÖDEV 5 

### SORU 1 :question:
Film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

### :green_square: CEVAP 1 
```
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;
```

### SORU 2 :question:
Film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci 5 filmi sıralayınız.

### :green_square: CEVAP 2 
```
SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5;
```

### SORU 3 :question:
Customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

### :green_square: CEVAP 3 
```
SELECT last_name, store_id FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4;
```

---

## :open_book: ÖDEV 6 	

### SORU 1 :question:
Film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

### :green_square: CEVAP 1 
```
SELECT ROUND(AVG(rental_rate), 2) FROM film;
```

### SORU 2 :question:
Film tablosunda bulunan filmlerden kaçtanesi 'C' karekteri ile başlar?

### :green_square: CEVAP 2 
```
SELECT COUNT(*) FROM film
WHERE title LIKE 'C%';
```

### SORU 3 :question:
Film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

### :green_square: CEVAP 3 
```
SELECT title, rental_rate , length FROM film
WHERE rental_rate = 0.99
ORDER BY length DESC
LIMIT 3;
--3 farklı film mevcut ilgili şartları sağlayan. Ancak cevap değişmiyor.
```

### SORU 4 :question:
Film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

### :green_square: CEVAP 4 
```
SELECT DISTINCT(replacement_cost) FROM film
WHERE length > 150
ORDER BY replacement_cost ASC;
```

---

## Contributing :hammer_and_wrench:	
Hatalar, öneriler ve değişiklikler için lütfen bir konu açınız.

## License :notebook_with_decorative_cover:

[MIT](https://www.google.com/search?q=mit+license&oq=mit+license&aqs=chrome.0.0l4j0i22i30l6.2910j0j7&sourceid=chrome&ie=UTF-8)


![Lorem Picsum](https://picsum.photos/200/300)
