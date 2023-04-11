# SQL ALL STUDIES

## SQL STUDY 1

1. film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız. (Sort the data in the title and description columns in the movie table.)

`SELECT title, description
FROM film;`

2. film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız. (Sort the data in all columns in the movie table with the movie length greater than 60 AND less than 75.)

`SELECT *
FROM film
WHERE length > 60
AND length < 75;`

3. film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız. (Sort the data in all columns in the movie table with rental_rate 0.99 AND replacement_cost 12.99 OR 28.99.)

`SELECT *
FROM film
WHERE rental_rate = 0.99
AND (replacement_cost = 12.99 OR replacement_cost = 28.99);`

4. customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir? (What is the value in the last_name column of the customer whose value is 'Mary' in the first_name column of the customer table?)

`SELECT first_name, last_name
FROM customer
WHERE first_name = 'Mary';`

5. film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız. (Sort the data in the movie table whose length is NOT greater than 50, but whose rental_rate is NOT 2.99 or 4.99.)

`SELECT title, length, rental_rate
FROM film
WHERE length < 50
AND NOT (rental_rate = 2.99 OR rental_rate = 4.99);`

## SQL STUDY 2

1. film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.) (Sort the data in all columns in the movie table provided that the replacement cost value is greater than 12.99, equal and less than 16.99 (use BETWEEN - AND structure).)

`SELECT * FROM film
WHERE replacement_cost BETWEEN 12.00 AND 16.99;`

2. .actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.) (Sort the data in the first_name and last_name columns in the .actor table provided that first_name is 'Penelope' or 'Nick' or 'Ed'. (Use the IN operator.))

`SELECT first_name, last_name FROM actor
WHERE first_name IN ('Penelope', 'Nick', 'Ed');`

3. film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.) (Sort the data in all columns in the movie table with rental_rate 0.99, 2.99, 4.99 AND replacement_cost 12.99, 15.99, 28.99. (Use the IN operator.))

`SELECT * FROM film
WHERE (rental_rate IN (0.99,2.99,4.99)) 
AND (replacement_cost IN (12.99, 15.99, 28.99));`

## SQL STUDY 3

1. country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız. (List the country names in the country column of the country table, starting with the 'A' character and ending with the 'a' character.)

`SELECT country FROM country
WHERE country LIKE 'A%a';`

2. country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız. (List the country names in the country column of the country table, consisting of at least 6 characters and ending with the 'n' character.)

`SELECT country FROM country
WHERE country LIKE '_____%n';`

3. film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız. (In the title column of the movie table, list the movie names containing at least 4 'T' characters, regardless of upper or lower case letters.)

`SELECT title FROM film
WHERE title ILIKE '%t%t%t%t%';`

4. film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız. (From the data in all the columns in the movie table, sort the data that starts with the title 'C' character, has a length greater than 90 and a rental_rate of 2.99.)

`SELECT * FROM film
WHERE title LIKE 'C%'
AND length > 90
AND rental_rate = 2.99;`

## SQL STUDY 4

1. film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız. (Sort the different values in the replacement_cost column in the movie table.)

`SELECT DISTINCT replacement_cost FROM film;`

2. film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır? (How many different data are there in the replacement_cost column in the movie table?)

`SELECT COUNT (DISTINCT replacement_cost) FROM film; </code>`

3. film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir? (How many of the movie titles in the movie table start with the character T and at the same time the rating is equal to 'G'?)

`SELECT COUNT (title) FROM film
WHERE title LIKE 'T%'
AND rating = 'G'; </code>`

4. country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır? (How many of the country names (country) in the country table consist of 5 characters?)

`SELECT COUNT (country) FROM country
WHERE country LIKE '_____'; </code>`

5. city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter? (How many of the city names in the city table end with the character 'R' or r?)

`SELECT COUNT (city) FROM city
WHERE city ILIKE '%r'; </code>`

## SQL STUDY 5

1. film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız. (List the 5 longest (length) movies in the movie table and the movie title (title) ends with the 'n' character.)

`SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5;`

2. film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız. (List the shortest (length) second(6,7,8,9,10) 5 movies(6,7,8,9,10) in the movie table and the movie title ends with the 'n' character.)

`SELECT title, length FROM film
WHERE title LIKE '%n'
ORDER BY length ASC
OFFSET 5
LIMIT 5;`

3. customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız. (Sort the first 4 data, provided that store_id is 1 in the descending order according to the last_name column in the customer table.)

`SELECT first_name, last_name, store_id FROM customer
WHERE store_id = '1'
ORDER BY last_name DESC
LIMIT 4;`

## SQL STUDY 6

1. film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir? (What is the average of the values in the rental_rate column in the movie table?)

`SELECT AVG(rental_rate) FROM film;`

2. film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar? (How many of the movies in the movie table start with the character 'C'?)

`SELECT COUNT(title) FROM film
WHERE title LIKE 'C%';`

3. film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır? (Among the movies in the movie table, how many minutes is the longest (length) movie with a rental_rate equal to 0.99?)

`SELECT MAX(length) FROM film
WHERE rental_rate = 0.99;`

4. film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır? (How many different replacement_cost values are there for the movies longer than 150 minutes in the movie table?)

`SELECT COUNT (DISTINCT replacement_cost) FROM film
WHERE length > 150;`

## SQL STUDY 7

## SQL STUDY 8

## SQL STUDY 9

## SQL STUDY 10

## SQL STUDY 11

## SQL STUDY 12
