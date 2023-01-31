<b> HOW TO SOLVE CSRF LOW </b>

Nah di jenis attack ini cara kerja nya yaitu dengan mencoba attack sistem dengan menggunakan kelemahan end-user yang authentik.
sekarang kita coba liat gambar tersebut setelah saya masukan password baru <b>"fikri"</b>

![Screenshot (453)](https://user-images.githubusercontent.com/118157585/215658192-5e0724b8-f30c-4350-ade8-9ea9d342f4a2.png)

lihat gambar diatas ? apa yang berubah setelah dimasukan new password ?

Lihat url nya, dia berubah menjadi

```
http://192.168.18.115/DVWA/vulnerabilities/csrf/?password_new=fikri&password_conf=fikri&Change=Change#
```

Jadi, coba bayangkan seorang penyerang yang akan mengirimi Anda alamat berbahaya seperti url diatas dan si attacker menemukan cara untuk anda mengklik link tersebut, maka nnti password kita akan berubah seperti yang di url tersebut.

dan untuk kasus ini yaitu akun dvwa kita akan berubah yang sebelumnya passwordnya <b> password </b> menjadi <b> fikri </b>
