# patika_odev


ODEV1

S1-film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.
  C1-select title , description from film;
  
S2-film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.
  C2-select * from film WHERE length between 60 and 75;
  
S3-film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.
  C3-select * from film WHERE rental_rate between 0.99 and 12.99;
  
S4-customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
  c4-select last_name from CUSTOMER WHERE first_name ='Mary';
  
S5-film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.
  C5-select length , rental_rate from film WHERE length < 50 and not (rental_rate=2.99 or rental_rate=4.99);
  
 
ODEV2
  
S1-film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)
  C1-select * from  film where replacement_cost BETWEEN 12.99 and 16.99;
  
S2-actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)
  C2-select  first_name,last_name from ACTOR WHERE first_name in ('Penelope' ,'Nick','Ed');
  
S3-film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)
  C3-select  * FROM film where rental_rate in ( 0.99, 2.99, 4.99)  and  replacement_cost in (12.99, 15.99, 28.99);
  
  
  ODEV3
  
S1- country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.
  c1-
select COUNTRY FROM COUNTRY 
WHERE COUNTRY LIKE 'A%a';

S2- country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.
c2-
select COUNTRY FROM COUNTRY 
WHERE COUNTRY LIKE '%%%%%%a';

S3- film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.
C3-
select TITLE ,FILM FROM FILM 
WHERE TITLE ILIKE '%%%%T';

S4- film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri 
sıralayınız.
 
 C4-
 select * FROM FILM 
WHERE TITLE LIKE 'C%' AND length>90 AND rental_rate=2.99 ;

ODEV4

1-film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

select DISTINCT(replacement_cost) FROM FILM ;

2-film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

select COUNT( DISTINCT replacement_cost ) FROM FILM ; --count sayıyı verir distinc ise benzersiz değerleri getirir

3-film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

select COUNT( DISTINCT TITLE ) FROM FILM
WHERE TITLE LIKE 'T%' AND RATING ='G';


4-country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

SELECT COUNT(DISTINCT COUNTRY ) FROM COUNTRY 
WHERE COUNTRY LIKE '_____';

5-city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

SELECT COUNT(DISTINCT CITY ) FROM CITY
WHERE CITY ILIKE '%R';

  
ODEV5

1-film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

SELECT * FROM film
WHERE title like '%n'
order by length desc
limit 5;

2-film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.

SELECT * FROM film
WHERE title like '%n'
order by length asc --sıralama (asc-->küçükten büyüğe desc--> büyükten küçüğe)
limit 5 --limit koyar
offset 5; --atlama yapar


3-customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

SELECT * FROM customer
WHERE store_id=1
order by last_name desc
limit 4;


ODEV6

1-film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

SELECT AVG(rental_rate) FROM film;--ortalama verir
SELECT round (AVG(rental_rate) ,2 ) FROM film; --yuvarlama yapar round ile

2-film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?

SELECT count(film) FROM film
WHERE title like'C%';

3-film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

SELECT max(length) FROM film
WHERE rental_rate = 0.99;

4-film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?

SELECT count(distinct replacement_cost) FROM film
WHERE length >150;


ODEV7

1-film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.

SELECT rating FROM film
GROUP BY rating;

2-film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

SELECT replacement_cost , COUNT(*) FROM film
GROUP BY replacement_cost -- group by : gruplama yapar
HAVING count(*) >50; --having : gruba koşul koyar

3-customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? 

SELECT store_id , COUNT(*) FROM customer
group by store_id;

4. city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.

SELECT country_id , COUNT(*) FROM city
group by country_id
ORDER BY COUNT(*) DESC
LIMIT 1;


ODEV8


1-test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

create table employee(
	id integer,
	name VARCHAR(50),
	birthday DATE,
	email VARCHAR(100)
	
);

2-Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

select * from employee;

3-Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

update employee 
set name ='ali'
where name ilike 'L%'

4-Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

delete from employee 
where name ilike 'a%';

ODEV9

1-city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

SELECT * from city
join country on country.country_id = city.country_id;

2-customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

SELECT payment_id , first_name , last_name from customer
join payment  on customer.customer_id = payment.customer_id;


3-customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.

SELECT rental_id , first_name , last_name from customer
join rental on customer.customer_id = rental.customer_id;

ODEV10

1-city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.

SELECT * FROM city
left join country on city.country_id=country.country_id;

2-customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu 
yazınız.

SELECT payment_id , first_name , last_name FROM customer
right join payment on payment.customer_id=customer.customer_id;

3-customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.

SELECT rental_id , first_name , last_name FROM customer
full join rental on rental.customer_id=customer.customer_id;

ODEV11

1-actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.

select first_name from actor
union all 
select first_name from customer;

2-actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.

select first_name from actor
intersect 
select first_name from customer;

3-actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.

select first_name from actor
except 
select first_name from customer;

4-İlk 3 sorguyu tekrar eden veriler için de yapalım.
