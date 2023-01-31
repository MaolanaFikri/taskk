<b> HOW TO SOLVE FILE UPLOAD ON DVWA </b>

File Upload itu sering kita jumpai saat berada di internet, so mencegah terjadinya file malicious itu penting.

nah sekarang kita akan belajar case untuk menjadi seorang attacker menggunakan web dvwa

1. Sekarang kita akan coba mensusupkan file malicious, yang mana sebenernya file tersebut adalah .html dan kita tiban dengan .jpg
   kita bikin file tersebut dulu, skrg kita buka notepad, dan ketikkan perintah seperti dibawah ini, dan rubah ekstensi nya menjadi .jpg agar terlihat seperti image
   
![Screenshot (454)](https://user-images.githubusercontent.com/118157585/215696065-54f6e867-b3da-41d9-8623-bdd96db65497.png)

![Screenshot (455)](https://user-images.githubusercontent.com/118157585/215696086-3746e17a-e447-439a-be65-1e690a877a1d.png)

2. nah sekarang kit upload file yang .jpg kita buat tadi ke DVWA, setelah upload nnti akan ada notif seperti gambar dibawah ini

![Screenshot (456)](https://user-images.githubusercontent.com/118157585/215696092-4aba3bec-3f3a-400f-b194-c1397a72e54f.png)

3. nah kita cek di folder menggunakan cli, dan ternyata terdapat file malicious tersebut.

![Screenshot (457)](https://user-images.githubusercontent.com/118157585/215696095-97f5f4e5-86f0-433a-8b4c-8176bd76a564.png)

4. lalu sekarang kita copy folder seperti gambar diatas, lalu salin di url DVWA

   ```
   http://192.168.18.115/DVWA/hackable/uploads/hacked.html
   ```

5. taraaaa, sekarang file udah berhasil di tanam di web tersebut.

