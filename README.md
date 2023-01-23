# patika_blog
Patika_Blog
Patika örnek blog:


Üçgenlerle aranız nasıl? Muhtemelen hepiniz geometri,trigonometri vb. çoğu konuda üçgenlerle karşılaşmışsınızdır. Bu blog yazısında ise birçoğumuzun bildiği konu olan üçgen kenar kurallarına biraz değinelim ve SQL ile de pekiştirelim.
 

Hackerrank sitesinden bir örnek alırsak (Type of Triangle);

Üç kenar uzunluğunu kullanarak ÜÇGENLER tablosundaki her bir kaydın türünü tanımlayan bir sorgu yazın. Tablodaki her kayıt için aşağıdaki ifadelerden birini çıkarın:

Eşkenar: Kenar uzunlukları eşit olan üçgendir.('Equilateral')
İkizkenar: 2 kenarı eşit uzunlukta olan üçgendir.('Isosceles')
Çeşitkenar: Kenar uzunlukları farklı olan üçgendir.('Scalene')
Üçgen Değil: Verilen A, B ve C değerleri bir üçgen oluşturmaz.('Not A Triangle')


SELECT CASE             
            WHEN A + B > C AND B + C > A AND A + C > B THEN
                CASE 
                    WHEN A = B AND B = C THEN 'Equilateral'
                    WHEN A = B OR B = C OR A = C THEN 'Isosceles'
                    ELSE 'Scalene'
                END
            ELSE 'Not A Triangle'
        END
FROM TRIANGLES;


Bu sorgu Microsoft SQL Server veri tabanı yönetim sistemi programında verilerden eşkenar üçgen olanlar, ikizkenar üçgen olanlar, çeşitkenar üçgen olanlar ve üçgen olma şartını sağlayamayanları gösterir.

Eşkenar üçgen olması için üç kenar verisinin birbirine eşit olması gerektiğinden a=b=c şeklinde belirtebiliriz.

İkizkenar üçgen olması için iki kenarı eşit bir kenarı farklı olmalı,ancak aynı zamanda üçgen şartını sağlaması için herhangi iki kenarın toplamı üçüncü kenardan küçük olmamalı ki bunu da unutmamamız gerekiyor.

Çeşitkenar üçgenin üç kenarı da farklıdır ve üçgen olma şartını karşılamalıdır.

Peki neden "A + B > C AND B + C > A AND A + C > B" kısmını başa yazdık? Çünkü önce üçgen olup olmadığını çözmeye çalıştık ve daha sonra çeşitkenar,ikizkenar vb. olduğunun sorgusunu yaptık.
