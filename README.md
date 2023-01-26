1. Kita install buat DHCP Server nya dengan perintah :

``
apt-get install isc-dhcp-server -y
``

2. Lalu kita konfigurasi ip nya dengan menetikkan perintah :

``
nano /etc/netplan/00-installer-config.yaml
``

3. Kita restart konfirgurasi kita yang tadi. karna kita belum di user root, maka harus menggunakan
``
sudo
``
:

``
sudo netplan apply
``



![Screenshot (434)](https://user-images.githubusercontent.com/118157585/214761212-953dc95b-e3a8-4299-bce8-6da545e0729b.png)
