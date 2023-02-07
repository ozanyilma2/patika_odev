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
