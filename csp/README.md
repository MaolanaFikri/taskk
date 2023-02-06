<b> HOW TO SOLVE CSP </b>

apa itu sih CSP? Content Security Policy adalah standar keamanan komputer yang diperkenalkan untuk mencegah skrip lintas situs, clickjacking, dan serangan injeksi kode lainnya yang dihasilkan dari eksekusi konten berbahaya dalam konteks halaman web tepercaya.

nah sekarang kita akan mulai dokumentasi cara pengerjaannya.

ini saya tampilkan DVWA/csp

![Screenshot (462)](https://user-images.githubusercontent.com/118157585/216886506-9e3c4598-5e5f-4b29-8a3c-955e602bd988.png)

nah setlah itu kita lihat di inspect element DVWA/csp itu, lalu masuk ke network dan klik yang /DVWA/vulnerabilities. hasilnya seperti digambar,
yang mana web browser tersebut termasuk yang ter whitelist oleh DVWA/csp ( di izinkan )

![Screenshot (463)](https://user-images.githubusercontent.com/118157585/216886572-408aa0ec-47ad-4496-8344-64ada3d09f25.png)
