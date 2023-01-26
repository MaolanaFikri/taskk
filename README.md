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
