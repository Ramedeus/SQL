# SQL
SQL Examples

Bu repo [Kodluyoruz](Kodluyoruz.org) SQL eğitimi için hazırlamış olduğum repo. İçerisinde bir adet README dosyası barındırıyor.

## ÖDEV 1

### SORU 1
Film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.

### CEVAP 1
```
SELECT title, description FROM film;
```

### SORU 2
Film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.

### CEVAP 2
```
SELECT * FROM film
WHERE length > 60 AND length < 75;
```

### SORU 3
Film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.

### CEVAP 3
```
SELECT * FROM film
WHERE rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99;
```

### SORU 4
Customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

### CEVAP 4
```
SELECT * FROM customer
WHERE first_name = 'Mary' --Smith;
```

### SORU 5
Film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

### CEVAP 5
```
SELECT * FROM film
WHERE length < 50 AND NOT rental_rate = 2.99 OR NOT rental_rate = 4.99;
```

## Contributing
Hatalar, öneriler ve değişiklikler için lütfen bir konu açınız.

## License

[MIT](https://www.google.com/search?q=mit+license&oq=mit+license&aqs=chrome.0.0l4j0i22i30l6.2910j0j7&sourceid=chrome&ie=UTF-8)


![Lorem Picsum](https://picsum.photos/200/300)
