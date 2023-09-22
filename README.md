# Jarkom-Modul-1-E20
Nama Anggota :
1. Ahmad Hafiz Mahardika   (5025201196)
2. Moch. Taslam Gustino P  (5025211011)

# Lapres

## Soal 1
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/2aaa00d3-82a2-4d7c-ac64-01af1f7e0a39)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/6a70e588-a0c9-4c7b-a192-f53e6779cc42)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/ede8feaf-67d6-4d08-9f48-6382569ba6aa)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/b8db161d-fd19-4f10-a1d1-f28666dd7a51)

Untuk filter packet yang melakukan upload FTP maka perlu mencari protocol FTP yang mengandung string STOR didalam packetnya. Lalu diklik packet yang bersangkutan untuk melihat sequence number (raw) dan acknowledge number (raw). Untuk mengetahui responsenya maka melihat packet selanjutnya yang dikirim dari IP yang sama setelah melakukan STOR. Terlihat untuk upload file (STOR) terdapat di packet no 147 dan packet selanjutnya yaitu pada packet no 149. Didalam packet no 149 terdapat sequence number (raw) dan acknowledge number (raw) didalamnya.
FLAG : Jarkom2023{y0u_r_g00d_4t_4dr3ssing_JoKvIxJ06293367}

## Soal 2
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/95972129/c868791b-2792-40d6-8636-a61b74362cbd)

Filter hasil capture dengan `ip.addr == 10.21.78.111 && tcp.port == 8000`(Adress website praktikum). Selanjutnya pilih salah satu packet dan follow tcp/http stream. Setetlah itu akan muncul window berikut.

![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/95972129/33ebb1a6-35e0-4054-a847-699e73053b70)

Pada window tersebut dapat deketahui bahwa webserver yang digunakan adalah gunicorn.
FLAG : Jarkom2023{9unic0rn_1s_L5LYalo38S9u2h6_c00l}

## Soal 3
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/f0249de0-d078-4073-93aa-890b6c449cc7)

a. Untuk melihat packet yang tercapture pada ip source dan destination address 239.255.255.250 dengan port 3702 adalah dengan filter (ip.dst == 239.255.255.250 || ip.src == 239.255.255.250) && udp.port == 3702. Banyak packet langsung dapat dihitung semua yang muncul dari filter tersebut.
b. Untuk protocol yang digunakan pada packet dapat dilihat dari kolom Protocol pada wireshark
FLAG : Jarkom2023{4nalyz3_is_7033_DwNmNhNkBtC_gr3at}

## Soal 4
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/95972129/be3fcb88-ebba-44d6-962f-f4ba98cb858b)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/95972129/293e4bd3-283b-4190-8eef-4e5f9d7173f2)

Untuk mendapatkan nilai cheksum pada paket nomor 130, filter hasil capture dengan `frame.number == 130`. Klik hasil paket yang difilter, kemudian pada bagian User Datagram Protocol, dapat diketahui cheksum dari paket nomor 130 adalah 0x18e5.
FLAG : Jarkom2023{ch3cksum_is_u5eful_0x1l6j}

## Soal 5
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/608d09bb-c539-4b8b-b255-376f96778200)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/7b3c955d-1dac-4885-a2c9-e593bef4283d)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/369b1a6b-6848-4237-9cd5-c13b77f85f92)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/71e52835-a4d0-4d33-a228-f51a8eb13fc4)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/2f15bfe3-62f0-472c-947d-3666d71c3e00)

Untuk mendapatkan flag maka diperlukan netcat yang sudah disediakan menurut soalnya. Karena netcat belum diberikan maka perlu dicari menggunakan filtering di dalam wireshark file pcap-nya. Filtering dengan mencari protocol SMTP dan mencari packet yang bertuliskan "Pass ...". Kemudian didalam packet tersebut terdapat password untuk membuka file zip yang dikunci. Password didecode terlebih dahulu menggunakan base64 sesuai perintah yang ada didalam packet. Kemudian buka file zip untuk mendapatkan netcat-nya.

a. Untuk mengetahui banyak packet dari file pcap yaitu scroll sampai packet yang paling akhir dan ada nomor urut packet terakhir. Disitulah jumlah packetnya.
b. Untuk melihat port yang digunakan untuk service SMTP yaitu klik packet yang berasal dari IP source yang sama saat IP kita menggunakan service SMTP. Kemudian di dalamnya terdapat port-nya.
c. IP public yaitu IP yang tersebar luas di internet, maka dari itu untuk melihat IP tersebut yaitu dilihat IP source dari response saat kita mengirimkan packet
FLAG : Jarkom2023{k0w4lski_0932_BgFlBRgkCNy_4nalys1s}

## Soal 6
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/da8d1c0c-1123-4923-8f6f-490c2a16e42b)

Untuk mencari source address 7812 yaitu membuka packet dengan nomor urut 7812. Di soal deberikan petunjuk yang bertuliskan "hasil pencarian hanya menampilkan a1 e5 u21" dimana itu adalah petunjuk untuk decode sesuatu. Cara mendecode yaitu dengan merubah angka 1 menjadi 'a', 2 menjadi 'b' dan seterusnya sampai 'z'. Karena packet tadi berada pada nomor urut 7812 maka mencari kode yang dapat di decode. Kode tersebut yaitu berupa IP source-nya yaitu 104.18.14.101. Untuk melakukan decode yaitu memisahkan angka tersebut menjadi 10 = J, 4 = D, 18 = R, 14 = N, 10 = J, 1 = A. Kode error yang dimaksud yaitu 'JDRNJA'
FLAG : Jarkom2023{h3h3_ctf_d1k1t_a07BL4ZV17L39SQ94Kkx}

## Soal 7
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/93267604/d33e8a8f-805c-449a-bba2-285f61b91efe)

Untuk mencari jumlah packet yang memiliki ip destination sesuai soal maka menggunakan filter ip.dst == "Alamat IP". Dalam kasus ini maka filternya yaitu ip.dst == 184.87.193.88. Kemudian hitung jumlah packet yang ditampilkan tersebut.
FLAG : Jarkom2023{N6wNd795RYDU30XZfl_4n0th3r_f1lt3ring}

## Soal 8
Untuk memfilter capture semua protokol paket yang menuju port 80 menggunakan `tcp.dstport == 80 || udp.dstport == 80`. Karena, pada soal terdapat kata kunci 'menuju' dan 'semua protokol' sehinggan menggunakan kueri `dstport` dan `tcp || udp`.
FLAG : Jarkom2023{qu3ryyyyying_573630_NlFvFjFtCwE_15_fun}

## Soal 9
Untuk mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34. yaitu menggunakan query ip.src == 10.51.40.1 && ip.dst != 10.39.55.34 dimana ip source yang menunjukkan ip 10.51.40.1 dan ip destination tidak menunjukkan 10.39.55.34
FLAG : Jarkom2023{y3s_its_OiPkSjNgOlO_qu3ry1ng}

## Soal 10
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/95972129/bf1ac602-9500-4613-ac00-ccc46b50db4b)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/95972129/e5ae9fde-8903-430a-addd-c801abd46315)

Untuk mendapatkan kredensial login Telnet, filter hasil capture dengan kueri `telnet`. Pilih paket dari hasil filter, lalu klik follow dan TCP stream.

![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/95972129/06be4039-b70e-494f-8805-b79278937b7d)
![image](https://github.com/gustino7/Jarkom-Modul-1-E20/assets/95972129/49084050-583b-49b0-9260-f19202707f56)


Karena terdapat beberapa password, maka saya mencoba satu-satu mulai dari `tcp.stream eq 1`. Kredensial yang benar yaitu `dhafin:kesayangannyak0k0`
FLAG : Jarkom2023{t3lnet_is_242zCx57zCBBx3BAx_N0tSecu2e}
