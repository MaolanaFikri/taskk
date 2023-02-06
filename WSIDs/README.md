<b> HOW TO SOLVE WEAK SESSION IDs </b>

Sebelum kita mulai ke studi case, kita harus tau dulu session ids itu apa sih? Session Id adalah sepotong data yang digunakan dalam komunikasi jaringan (sering kali melalui HTTP) untuk mengidentifikasi sesi, serangkaian pertukaran pesan terkait. Pengidentifikasi sesi menjadi penting dalam kasus-kasus di mana infrastruktur komunikasi menggunakan protokol tanpa kewarganegaraan seperti HTTP.

Sekarang bisa kita mulaiiiiiiiiiii

Ini tampilan saat saya klik <b>'Generate'</b>, di inspect elemet terdapat berbagai informasi terkait cookie. itu saya coba ketik <b>Document.cookie</b>.
dan terdapat dvwa session sekaligus security nya.

![Screenshot (480)](https://user-images.githubusercontent.com/118157585/216950245-02499bd6-2267-4e5a-99ee-7dc21e298f44.png)

disini saya menggunakan tool BurpSuite.
so, Setiap kali tombol 'Generate' diklik, cookie 'dvwaSession' akan menerima nilai baru.
dvwaSession yang pertama kali bernilai '1', lalu '2'. Nilai berikutnya adalah '3'. Tidak ada keacakan, nilainya mudah diprediksi. Ini membuka vektor serangan Man-In-The-Middle.

yuk sekarang kita mulai evaluasi keacakan dengan BurpSuite yaitu sequincer.

![Screenshot (478)](https://user-images.githubusercontent.com/118157585/216949505-ee9a7aaa-5f61-48e9-9074-5509204defc2.png)

klik kanan pada IP lalu pilih send to Sequencer

![Screenshot (474)](https://user-images.githubusercontent.com/118157585/216949323-3b6f4270-d027-476f-a9b7-de6164e7f476.png)

after that kita lakukan live capture sampai finish

![Screenshot (477)](https://user-images.githubusercontent.com/118157585/216949447-041eb274-4132-45d5-ba41-e0a3eef3e3c8.png)

nah setelah finish kita klik analyze now

![Screenshot (475)](https://user-images.githubusercontent.com/118157585/216949367-4f6ae076-6557-457d-a8d9-65b759223473.png)

Hasilnya buruk, seperti yang sudah diduga. Tidak ada keacakan dalam nilainya.
