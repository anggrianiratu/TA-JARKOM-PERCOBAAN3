## Percobaan 3 : Configure VLANs and Trunking


### Link Youtube
https://youtu.be/rp_gPyOND5Y?si=vHUGn_5m1BPObDu_

### Tujuan Percobaan
* Membangun jaringan dasar menggunakan dua switch dan beberapa PC sesuai topologi yang diberikan.
* Mempelajari cara membuat dan mengonfigurasi VLAN (Virtual Local Area Network) pada switch.
* Menetapkan port switch ke VLAN tertentu untuk memisahkan lalu lintas jaringan.
* Mengetahui cara mengelola database VLAN dan melakukan perubahan atau penghapusan VLAN.
* Mengonfigurasi trunking (802.1Q) agar VLAN dapat ditransmisikan antar-switch melalui satu link.
* Menguji konektivitas antarperangkat dalam VLAN yang sama dan memahami batas komunikasi antar-VLAN.

### Topology
<img width="1146" height="580" alt="image" src="https://github.com/user-attachments/assets/37d40e51-abe4-4994-9068-5550e59a3d47" />

**IP Address** 
* PC-A: 192.168.10.3
* PC-B: 192.168.10.4
* PC-C: 192.168.10.5
* SW-1: 192.168.1.11
* SW-2: 192.168.1.12
  
#### Ping PC-B, PC-C, SW-1 melalui command prompt di PC-A
<img width="1382" height="1398" alt="image" src="https://github.com/user-attachments/assets/4ba918dd-b775-4f1d-9bce-a2e815faa57c" />

#### Ping SW-2, PC-A melalui command prompt di SW-1
<img width="1383" height="555" alt="image" src="https://github.com/user-attachments/assets/7d68449b-f8c8-4e72-b3d9-63cbc6792999" />

#### Penjelasan

**PC ke PC berhasil:**
<p align="justify">
PC-A, PC-B, dan PC-C berada pada VLAN yang sama, yaitu VLAN 10. Trunk pada port F0/1 mengangkut VLAN 10 antar-switch, sehingga ketiga PC dapat saling berkomunikasi meskipun terhubung ke switch yang berbeda. </p>

**Switch ke Switch berhasil:**
<p align="justify">
Kedua switch (S1 dan S2) menggunakan VLAN 99 untuk manajemen, dan trunk juga membawa VLAN 99. Karena itu, komunikasi antar-switch dapat berjalan dengan baik melalui jalur trunk tersebut. </p>

**PC ke Switch atau sebaliknya tidak berhasil:**
<p align="justify">
PC berada di VLAN 10, sedangkan switch berada di VLAN 99. Karena tidak ada perangkat Layer 3 yang melakukan routing antar-VLAN, komunikasi antara PC dan switch tidak dapat dilakukan. </p>


