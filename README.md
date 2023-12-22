# Homework1

<div>
  Soru 1: Film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.

  Cevap 1: SELECT title, description FROM film;
</div>

<div>
  Soru 2: film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.

  Cevap 2: SELECT * FROM film WHERE length > 60 AND length < 75;
</div>

<div>
  Soru 3: film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.

  Cevap 3: SELECT * FROM film WHERE rental_rate = 0.99 AND replacement_cost = 12.99 OR replacement_cost = 28.99;
</div>

<div>
  Soru 4: customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

  Cevap 4: Smith
</div>

<div>
  Soru 5: film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

  Cevap 5: SELECT * FROM film WHERE NOT length > 50 AND NOT(rental_rate = 2.99 OR rental_rate = 4.99);
</div>

# Homework2

<div>
  Soru 1: film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

  Cevap 1: SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99;
</div>

<div>
  Soru 2: actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

  Cevap 2: SELECT first_name, last_name FROM actor WHERE first_name IN ('Penelope', 'Nick', 'Ed');
</div>

<div>
  Soru 3: film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

  Cevap 3: SELECT * FROM film WHERE rental_rate IN (0.99, 2.99, 4.99) AND replacement_cost IN (12.99, 15.99, 28.99);
</div>

# Homework3
<div>
  Soru 1: country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

  Cevap 1: SELECT * FROM country WHERE country LIKE 'A%a';
</div>

<div>
  Soru 2: country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

  Cevap 2: SELECT * FROM country WHERE country LIKE '%_____n'; 
</div>

<div>
  Soru 3: film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

  Cevap 3:SELECT * FROM film WHERE title ILIKE '%t%t%t%';
</div>

<div>
  Soru 4: film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

  Cevap 4: SELECT * FROM film WHERE title LIKE 'C%' AND length > 90 AND rental_rate = 2.99;
</div>

# Homework4
<div>
  Soru 1: film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

  Cevap 1: SELECT DISTINCT replacement_cost FROM film;
</div>

<div>
  Soru 2: film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

  Cevap 2: SELECT COUNT(DISTINCT replacement_cost) FROM film;
</div>

<div>
  Soru 3: film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

  Cevap 3: SELECT COUNT(title) FROM film WHERE title LIKE 'T%' AND rating = 'G';
</div>

<div>
  Soru 4: country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

  Cevap 4: SELECT COUNT(country) FROM country WHERE country LIKE '_____';
</div>

<div>
  Soru 5: city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

  Cevap 5: SELECT COUNT(city) FROM city WHERE city LIKE '%R' OR city LIKE '%r';
</div>

# Homework5
<div>
  Soru 1: film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

  Cevap 1: SELECT * FROM film WHERE title LIKE '%n' ORDER BY length DESC LIMIT 5;
</div>

<div>
  Soru 2: film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) 5 filmi sıralayınız.

  Cevap 2: SELECT * FROM film WHERE title LIKE '%n' ORDER BY length LIMIT 5;
</div>

<div>
  Soru 3: customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

  Cevap 3: SELECT * FROM customer WHERE store_id = 1 ORDER BY last_name DESC LIMIT 4;
</div>

# Homework6
<div>
  Soru 1: film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

  Cevap 1: SELECT AVG(rental_rate) FROM film;
</div>

<div>
  Soru 2: film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

  Cevap 2: SELECT COUNT(title) FROM film WHERE title LIKE 'C%';
</div>

<div>
  Soru 3: film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

  Cevap 3: SELECT MAX(length) FROM film WHERE rental_rate = 0.99;
</div>

<div>
  Soru 4: film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

  Cevap 4: SELECT COUNT(DISTINCT replacement_cost) FROM film WHERE length > 150;
</div>

# Homework7

<div>
  Soru 1: film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.

  Cevap 1: SELECT rating FROM film GROUP BY rating;
</div>

<div>
  Soru 2: film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı, 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

  Cevap 2: SELECT replacement_cost, COUNT(*) FROM film GROUP BY replacement_cost HAVING COUNT(*) > 50;
</div>

<div>
  Soru 3: customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? 4. city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

  Cevap 3: SELECT store_id, COUNT(*) FROM customer GROUP BY store_id; SELECT country_id, COUNT(*) FROM city GROUP BY country_id ORDER BY COUNT(*) DESC LIMIT 1;
</div>

# Homework8

<div>
  Soru 1: test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

  Cevap 1:CREATE TABLE test ( id SERIAL PRIMARY KEY, name VARCHAR(50) NOT NULL, birthday DATE, email VARCHAR(100) );
</div>

<div>
  Soru 2: Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

  Cevap 2: 👍
</div>

<div>
  Soru 3: Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

  Cevap 3: 
            
            UPDATE test
            SET name = 'Elon'
            WHERE id = 49;

            UPDATE test
            SET email = 'elonmusk@x.com'
            WHERE id = 49;

            UPDATE test
            SET 
              name = 'Reserved',
              email = 'reserved@reserved.com'
            WHERE id BETWEEN 1 AND 10;

            UPDATE test
            SET
              name = 'Jeff',
              email = 'jeffbezos@amazon.com'
            WHERE id = 50;

            UPDATE test
            SET
              name = 'Bill',
              email = 'billgates@microsoft.com'
            WHERE id = 48;
</div>

<div>
  Soru 4: Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

  Cevap 4:  
            
            DELETE FROM test
            WHERE id = 13;

            DELETE FROM test
            WHERE id = 17;

            DELETE FROM test
            WHERE id = 33;

            DELETE FROM test
            WHERE id = 23;

            DELETE FROM test
            WHERE id BETWEEN 20 AND 30;
</div>

# Homework9

<div>
  Soru 1: city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

  Cevap 1: SELECT city, country FROM city JOIN country ON country.country_id = city.country_id;
</div>

<div>
  Soru 2: customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

  Cevap 2: SELECT payment_id, first_name, last_name FROM customer JOIN payment ON customer.customer_id = payment.customer_id;
</div>

<div>
  Soru 3: customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

  Cevap 3: SELECT rental_id, first_name, last_name FROM customer JOIN rental ON customer.customer_id = rental.customer_id;
</div>

# Homework10

<div>
  Soru 1: city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.

  Cevap 1: SELECT city, country FROM city LEFT JOIN country ON city.country_id = country.country_id;
</div>

<div>
  Soru 2: customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.

  Cevap 2: SELECT payment_id, first_name, last_name FROM customer RIGHT JOIN payment ON customer.customer_id = payment.customer_id;
</div>

<div>
  Soru 3: customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

  Cevap 3: SELECT rental_id, first_name, last_name FROM customer FULL JOIN rental ON customer.customer_id = rental.customer_id;
</div>

# Homework11

<div>
  Soru 1: actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.

  Cevap 1: (SELECT first_name FROM sakila.actor) UNION (SELECT first_name FROM sakila.customer);
</div>

<div>
  Soru 2: actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.

  Cevap 2: (SELECT first_name FROM sakila.actor) INTERSECT (SELECT first_name FROM sakila.customer);
</div>

<div>
  Soru 3: actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.

  Cevap 3: (SELECT first_name FROM sakila.actor) EXCEPT (SELECT first_name FROM sakila.customer);
</div>
