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

<code> SELECT DISTINCT replacement_cost FROM film; </code>

2. film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır? (How many different data are there in the replacement_cost column in the movie table?)

<code> SELECT COUNT (DISTINCT replacement_cost) FROM film; </code>

3. film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir? (How many of the movie titles in the movie table start with the character T and at the same time the rating is equal to 'G'?)

<code> SELECT COUNT (title) FROM film
WHERE title LIKE 'T%'
AND rating = 'G'; </code>

4. country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır? (How many of the country names (country) in the country table consist of 5 characters?)

<code> SELECT COUNT (country) FROM country
WHERE country LIKE '_____'; </code>

5. city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter? (How many of the city names in the city table end with the character 'R' or r?)

<code> SELECT COUNT (city) FROM city
WHERE city ILIKE '%r'; </code>

## SQL STUDY 5

## SQL STUDY 6

## SQL STUDY 7

## SQL STUDY 8

## SQL STUDY 9

## SQL STUDY 10

## SQL STUDY 11

## SQL STUDY 12
