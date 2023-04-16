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

1. film tablosunda bulunan filmleri rating değerlerine göre gruplayınız. (Group the movies in the movie table according to their rating values.)

`SELECT rating, COUNT(*) FROM film
GROUP BY rating
ORDER BY rating DESC;`

2. film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız. (When we group the films in the film table according to the replacement_cost column, list the replacement_cost value with more than 50 films and the corresponding number of films.)

`SELECT replacement_cost, COUNT(*) FROM film
GROUP BY replacement_cost
HAVING COUNT(replacement_cost) > 50
ORDER BY replacement_cost;`

3. customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? (What are the customer numbers corresponding to the store_id values in the customer table?)

`SELECT store_id, COUNT(*) FROM customer
GROUP BY store_id;`

4. city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız. (After grouping the city data in the city table according to the country_id column, share the country_id information with the highest number of cities and the number of cities.)

`SELECT country_id, COUNT(*) FROM city
GROUP BY country_id
ORDER BY COUNT(*) DESC
LIMIT 1;`

## SQL STUDY 8

1. test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım. (Let's create a table in your test database with employee name column information id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100).)

`CREATE TABLE employee (
  id SERIAL PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  birthday DATE,
  email VARCHAR(100)
);`

2. Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim. (Let's add 50 pieces of data to the employee table we created using the 'Mockaroo' service.)

`insert into employee (id, name, birthday, email) values (1, 'Rutger', '07/05/2004', 'rchapelhow0@constantcontact.com');`  
`insert into employee (id, name, birthday, email) values (2, 'Martino', '06/13/2020', 'mconnell1@hubpages.com');`  
`insert into employee (id, name, birthday, email) values (3, 'Bruis', '02/29/1980', 'blester2@github.io');`  
`insert into employee (id, name, birthday, email) values (4, 'Claiborne', '02/03/2005', 'cmccaughren3@usgs.gov');`  
`insert into employee (id, name, birthday, email) values (5, 'Alvina', '05/01/1999', 'abowart4@pbs.org');`  
`insert into employee (id, name, birthday, email) values (6, 'Tobey', '06/29/1979', 'tconklin5@yelp.com');`  
`insert into employee (id, name, birthday, email) values (7, 'Walliw', '02/27/1971', 'wmcquorkell6@facebook.com');`  
`insert into employee (id, name, birthday, email) values (8, 'Nikkie', '11/26/2011', 'ndecoursey7@craigslist.org');`  
`insert into employee (id, name, birthday, email) values (9, 'Eric', '08/15/1991', 'efumagalli8@cyberchimps.com');`  
`insert into employee (id, name, birthday, email) values (10, 'Randy', '11/20/1960', 'rmacgarrity9@cbsnews.com');`  
`insert into employee (id, name, birthday, email) values (11, 'Guy', '10/03/1973', 'gdelavaletteparisota@alibaba.com');`  
`insert into employee (id, name, birthday, email) values (12, 'Flossie', '04/04/2000', 'fdraynb@bing.com');`  
`insert into employee (id, name, birthday, email) values (13, 'Nathanil', '08/27/1973', 'nduhamelc@sina.com.cn');`  
`insert into employee (id, name, birthday, email) values (14, 'Sancho', '09/04/2002', 'shodjettsd@thetimes.co.uk');`  
`insert into employee (id, name, birthday, email) values (15, 'Antonio', '11/13/2012', 'agrimselle@e-recht24.de');`  
`insert into employee (id, name, birthday, email) values (16, 'Hasty', '02/11/1980', 'hmattinf@cnet.com');`  
`insert into employee (id, name, birthday, email) values (17, 'Augy', '05/25/1991', 'atilteg@sourceforge.net');`  
`insert into employee (id, name, birthday, email) values (18, 'Phelia', '06/28/1966', 'praithh@prlog.org');`  
`insert into employee (id, name, birthday, email) values (19, 'Walton', '09/30/2022', 'wmcquillani@nymag.com');`  
`insert into employee (id, name, birthday, email) values (20, 'Karlik', '02/26/2007', 'ktorbetj@drupal.org');`  
`insert into employee (id, name, birthday, email) values (21, 'Corbin', '12/10/1968', 'craimank@apache.org');`  
`insert into employee (id, name, birthday, email) values (22, 'Mohammed', '02/06/1963', 'mlangshawl@cocolog-nifty.com');`  
`insert into employee (id, name, birthday, email) values (23, 'Nicol', '10/29/1987', 'nfranciscom@cargocollective.com');`  
`insert into employee (id, name, birthday, email) values (24, 'Elyse', '03/06/1981', 'eakamn@fotki.com');`  
`insert into employee (id, name, birthday, email) values (25, 'Idalina', '04/04/2008', 'igrenshieldso@feedburner.com');`  
`insert into employee (id, name, birthday, email) values (26, 'Kip', '12/07/1994', 'klittlejohnsp@imdb.com');`  
`insert into employee (id, name, birthday, email) values (27, 'Ike', '08/31/1954', 'ifeyerq@ted.com');`  
`insert into employee (id, name, birthday, email) values (28, 'Ruthe', '08/14/1968', 'rbrutyr@oaic.gov.au');`  
`insert into employee (id, name, birthday, email) values (29, 'Parry', '07/29/1958', 'pjershs@joomla.org');`  
`insert into employee (id, name, birthday, email) values (30, 'Cosme', '09/28/2019', 'ckirsopt@nature.com');`  
`insert into employee (id, name, birthday, email) values (31, 'Mychal', '01/11/1981', 'mravenshawu@twitpic.com');`  
`insert into employee (id, name, birthday, email) values (32, 'Emanuel', '11/09/2017', 'epitchersv@usnews.com');`  
`insert into employee (id, name, birthday, email) values (33, 'Fabiano', '07/18/2013', 'fhamsherew@ask.com');`  
`insert into employee (id, name, birthday, email) values (34, 'Henry', '04/20/1950', 'hpaullx@tmall.com');`  
`insert into employee (id, name, birthday, email) values (35, 'Kellen', '12/31/1986', 'ksoaresy@youtube.com');`  
`insert into employee (id, name, birthday, email) values (36, 'Dianemarie', '11/19/1993', 'dcleminshawz@sciencedirect.com');`  
`insert into employee (id, name, birthday, email) values (37, 'Elset', '05/18/1966', 'ebettlestone10@miibeian.gov.cn');`  
`insert into employee (id, name, birthday, email) values (38, 'Ulrika', '08/10/2022', 'uveronique11@unblog.fr');`  
`insert into employee (id, name, birthday, email) values (39, 'Tansy', '02/28/2015', 'tbalmforth12@reference.com');`  
`insert into employee (id, name, birthday, email) values (40, 'Etti', '01/04/1981', 'ecardozo13@nymag.com');`  
`insert into employee (id, name, birthday, email) values (41, 'Katuscha', '12/20/2000', 'kcorbyn14@etsy.com');`  
`insert into employee (id, name, birthday, email) values (42, 'Alane', '05/13/1980', 'aingerith15@ning.com');`  
`insert into employee (id, name, birthday, email) values (43, 'Caitrin', '01/17/1962', 'churdle16@tripod.com');`  
`insert into employee (id, name, birthday, email) values (44, 'Alexio', '07/12/1997', 'ablakeston17@friendfeed.com');`  
`insert into employee (id, name, birthday, email) values (45, 'Eli', '04/26/1957', 'epearse18@hc360.com');`  
`insert into employee (id, name, birthday, email) values (46, 'Karilynn', '01/13/1988', 'kmolan19@paginegialle.it');`  
`insert into employee (id, name, birthday, email) values (47, 'Gabriello', '09/15/1977', 'gconningham1a@mediafire.com');`  
`insert into employee (id, name, birthday, email) values (48, 'Cally', '04/30/1974', 'ceyckel1b@naver.com');`  
`insert into employee (id, name, birthday, email) values (49, 'Jerrie', '02/07/1965', 'jmarcroft1c@dell.com');`  
`insert into employee (id, name, birthday, email) values (50, 'Jesselyn', '03/14/1984', 'jmoorfield1d@guardian.co.uk');`  

3. Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım. (Let's do 5 UPDATE operations that will update the other columns according to each of the columns.)

`UPDATE employee SET email = 'rchapelhow0@gmail.com' WHERE id = 1;`

`UPDATE employee SET birthday = '09/15/1995' WHERE name = 'Martino';`

`UPDATE employee SET name = 'Bryce' WHERE id = 3;`

`UPDATE employee SET email = 'c.mccaughren@hotmail.com' WHERE id = 4;`

`UPDATE employee SET birthday = '12/12/1988', email = 'a.bowart@yahoo.com' WHERE id = 5;`

4. Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım. (Let's do 5 DELETE operations that will delete the relevant row according to each of the columns.)

`DELETE FROM employee WHERE id = 7; --id sütununda 7 olan satırı silecek.`

`DELETE FROM employee WHERE name = 'Tobey'; --name sütununda 'Tobey' olan satırı silecek.`

`DELETE FROM employee WHERE birthday = '11/26/2011'; --birthday sütununda '11/26/2011' olan satırı silecek.`

`DELETE FROM employee WHERE email = 'efumagalli8@cyberchimps.com'; --email sütununda 'efumagalli8@cyberchimps.com' olan satırı silecek.`

`DELETE FROM employee WHERE id = 10 AND name = 'Randy'; --id sütununda 10 ve name sütununda 'Randy' olan satırı silecek.`

## SQL STUDY 9

1. city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız. (Write the INNER JOIN query where we can see the city and country names in the city table and the country table together.)

`SELECT city, country FROM city
INNER JOIN country ON city.country_id = country.country_id`

2. customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız. (Write the INNER JOIN query where we can see the customer table and the payment_id in the payment table and the first_name and last_name names in the customer table together.)

`SELECT payment.payment_id, customer.first_name, customer.last_name
FROM payment
INNER JOIN customer ON payment.customer_id = customer.customer_id;`

3. customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız. (Write the INNER JOIN query where we can see the customer table and the rental_id in the rental table and the first_name and last_name names in the customer table together.)

`SELECT rental.rental_id, customer.first_name, customer.last_name
FROM rental
INNER JOIN customer
ON rental.customer_id = customer.customer_id;`

## SQL STUDY 10

1. city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız. (Write the LEFT JOIN query where we can see the city and country names in the city table and the country table together.)

`SELECT city.city, country.country
FROM city
LEFT JOIN country ON city.country_id = country.country_id;`

2. customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız. (Write the RIGHT JOIN query where we can see the customer table and the payment_id in the payment table and the first_name and last_name names in the customer table together.)

`SELECT payment.payment_id, customer.first_name, customer.last_name
FROM payment
RIGHT JOIN customer ON payment.customer_id = customer.customer_id;`

3. customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız. (Write the FULL JOIN query where we can see the customer table and the rental_id in the rental table and the first_name and last_name names in the customer table together.)

`SELECT rental.rental_id, customer.first_name, customer.last_name
FROM rental
FULL JOIN customer ON rental.customer_id = customer.customer_id;`

## SQL STUDY 11

Yakında geliyor. (Coming soon.)

## SQL STUDY 12

Yakında geliyor. (Coming soon.)
