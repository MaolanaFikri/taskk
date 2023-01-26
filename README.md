HOW TO MAKE DHCP SERVER


1. Kita install buat DHCP Server nya dengan perintah :

   ``
   apt-get install isc-dhcp-server -y
   ``

2. Lalu kita konfigurasi ip nya dengan menetikkan perintah :

   ``
   nano /etc/netplan/00-installer-config.yaml
   ``
   lalu ikutin gambar dibawah ini

![Screenshot (434)](https://user-images.githubusercontent.com/118157585/214761212-953dc95b-e3a8-4299-bce8-6da545e0729b.png)


3. Kita restart konfirgurasi kita yang tadi. karna kita belum di user root, maka harus menggunakan
   ``
   sudo
   ``
   :

   ``
   sudo netplan apply
   ``

![Screenshot (435)](https://user-images.githubusercontent.com/118157585/214769683-ca83d201-3baf-4b9c-8105-e292456446fb.png)

4. Langkah berikutnya adalah mengubah host agar kita tahu terhubung kemana nantinya IP DHCP kita pada jaringan lokal.
   lalu ganti nama host server-debian dan ip 127.0.1.1 menjadi ip yang telah kita setting dan domain yang akan digunakan, untuk di gambar ini sudah saya rubah.
   kita dapat mengubah host dengan perintah.
   
   ``
   nano /etc/hosts
   ``
   
   lihat gambar dibawah ini 
   
![Screenshot (436)](https://user-images.githubusercontent.com/118157585/214770250-c970abc8-0da5-4882-94d8-9339ebe52ae9.png)


5. Langkah selanjutnya adalah menentukan nama driver default dhcp servernya agar terhubung ke client dengan mengedit pada bagian isc-dhcp-server dengan mengetikkan perintah :

   `` 
   nano /etc/default/isc-dhcp-server
   ``
   lalu un# pada bacaan DHCPDv4 agar dapat digunakan dan dapat di input pada INTERFACEv4
   lalu INTERFACEv4 di isi dengan nama driver jaringan kita yaitu enp0s3
   
   ![Screenshot (437)](https://user-images.githubusercontent.com/118157585/214771146-eec36e18-0e2e-4169-b8ba-729fa56c176d.png)


6. Sekarang kita masuk kebagian settingan utama DHCP nya
   kita edit file tersebut dengan menggunakan perintah :
   
   ``
   nano /etc/dhcp/dhcpd.conf
   ``
   
   abis itu kita cari kata yang berawalan A Slightly dan hilangakan semua pagar# yang dibawah kata A Slightly
   lalu ip nya sesuai settingan masing masing
   
   ![Screenshot (438)](https://user-images.githubusercontent.com/118157585/214771771-005cedc0-da79-4ce1-9d61-a51d9fd712fc.png)


7. Setelah itu kita restart dengan perintah :
   
   ``
   systemctl restart restart isc-dhcp-server
   ``
   
   
8. Selanjutnya kita cek dulu statusnya
   
   ``
   systemctl status isc-dhcp-server
   ``
   
   sampai status nya berubah menjadi running seperti gambar dibawah ini
   
   ![Screenshot (439)](https://user-images.githubusercontent.com/118157585/214772445-1a99cc52-470e-450f-9374-199f83f3e218.png)

   
