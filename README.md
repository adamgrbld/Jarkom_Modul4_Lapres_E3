# Jarkom_Modul4_Lapres_E3

## Soal Shift

1. Melakukan perhitungan VLSM dan CIDR

2. Mengimplementasikan ke Cisco Packet Tracer (CPT) dan UML

3. Dengan ilustrasi sebagai berikut:

![soal](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/soal.png)
    

## VLSM

Kami mengimplementasikan **VLSM** pada **Cisco Packet Tracer (CPT)**

- Membuat topologi di CPT sesuai dengan soal

- Mengelompokkan router, switch dan host. Hasil setelah dikelompokkan sebagai berikut:

  ![vlsm](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/vlsm.png)
  
- Dari perhitungan jumlah IP didapatkan ```Lenght = /19```. Kemudian menentukan ```NID``` dan ```netmask``` dari hasil perhitungan dan didapatkan hasil sebagai berikut:

  ![ip](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/IP.jpg)
  
  ![nid](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/nid.png)
  
  ![server](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/server.png)
  
- Dari NID diatas, berikut pembagian IP untuk masing-masing device

  ```
  A1
  Lumajang (250): 192.168.1.3
  Blitar: 192.168.1.1
  Kediri: 192.168.1.2

  A2
  Tulungagung (720): 192.168.12.2
  Blitar: 192.168.12.1

  A3
  Kediri: 192.168.0.9
  Batu: 192.168.0.10

  A4
  Ngajuk: 192.168.4.2
  Batu: 192.168.4.1

  A5
  Bojonegoro (12): 192.8.0.18
  Madiun: 192.168.0.17

  A6
  Jombang (500): 192.168.2.3
  Madiun: 192.168.2.1
  Batu: 192.169.2.2

  A7
  Surabaya: 192.168.0.13
  Batu: 192.168.0.14

  A8
  Bondowoso (100): 192.168.16.2
  Probolinggo: 192.168.16.1

  A9
  Jember (1020): 192.168.24.3
  Banyuwangi (1000): 192.168.24.2
  Probolinggo: 192.168.24.1

  A10
  Probolinggo: 192.168.0.1
  Pasuruan: 192.168.0.2

  A11
  Sidoarjo (700): 192.168.8.2
  Pasuruan: 192.168.8.1

  A12
  Surabaya: 192.168.0.5
  Pasuruan: 192.168.0.6

  A13
  Sampang (1000): 192.168.0.130
  Suarabaya: 192.168.0.129
  ```
  
- Setting IP diatas pada device di CPT. Berikut contoh untuk setting pada subnet A2:
  
  - Rangkaian device pada subnet A2
  
    ![a2](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/A2.png)
    
  - BLITAR (Router)
  
    - Klik icon router ```BLITAR```
    - Pilih ```Config -> INTERFACE -> FastEthernet0/0``` (Fa yang mengarah ke TULUNGAGUNG)
    - Masukkan IP dan netmask sesuai pembagian diatas
    - Centang ```On``` di kanan atas
    
      ![blitar](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/blitar.png)
    
  - TULUNGAGUNG (PC)
  
    - Klik icon PC ```TULUNGAGUNG```
    - Pilih ```Desktop``` > ```IP COnfiguration```
    - Masukkan IP dan netmask sesuai pembagian diatas, dan isikan gateway dengan IP Fa0/0 milik BLITAR
    
      ![ta](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/tulungagung.png)
    
  - Setting semua device sesuai langkah-langkah diatas

- Routing semua router dengan cara:

  - Klik icon router
  - Pilih ```Config -> ROUTING -> Static```
  - Masukkan IP dan netmask seperti berikut:
  
    *setting default routing*
    
    ![routing](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/batu.png)
    
    Kemudian klik ```Add```
    
  - Tambahkan default routing berikut:
  
    ```
    SURABAYA
    0.0.0.0/0 via 192.168.0.6
    0.0.0.0/0 via 192.168.0.14

    PASURUAN
    0.0.0.0/0 via 192.168.0.5
    0.0.0.0/0 via 192.168.0.1

    PROBOLINGGO
    0.0.0.0/0 via 192.168.0.2

    MADIUN
    0.0.0.0/0 via 192.168.2.2

    BATU
    0.0.0.0/0 via 192.168.0.13
    0.0.0.0/0 via 192.168.2.1
    0.0.0.0/0 via 192.168.0.9

    KEDIRI
    0.0.0.0/0 via 192.168.0.10
    0.0.0.0/0 via 192.168.1.1

    BLITAR
    0.0.0.0/0 via 192.168.1.2
    ```
    
- Setting sudah selesai, kemudian test topologi

## CIDR

menggabungkan subnet-subnet menjadi 1
![b1](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/Soal_Shift_Modul_4.png)
![b2](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/Soal_Shift_Modul_4_1.png)
![b3](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/Soal_Shift_Modul_4_1_1.png)
![b4](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/Soal_Shift_Modul_4_1_1_1.png)
![b5](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/Soal_Shift_Modul_4_1_1_1_1.png)
![b6](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/Soal_Shift_Modul_4_1_1_1_1_1.png)
![b7](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/Soal_Shift_Modul_4_1_1_1_1_1_1.png)
setelah dibagi subnet dapat dibentuk pohon pembagian IP nya
![b8](https://github.com/adamgrbld/Jarkom_Modul4_Lapres_E3/blob/main/image/CIDR.png)
setelah itu dibuatlah topologi.sh nya 
```
# Switch
uml_switch -unix switch1 > /dev/null < /dev/null &
uml_switch -unix switch2 > /dev/null < /dev/null &
uml_switch -unix switch3 > /dev/null < /dev/null &
uml_switch -unix switch4 > /dev/null < /dev/null &
uml_switch -unix switch5 > /dev/null < /dev/null &
uml_switch -unix switch13 > /dev/null < /dev/null &
uml_switch -unix switch15 > /dev/null < /dev/null &
uml_switch -unix switch16 > /dev/null < /dev/null &
uml_switch -unix switch17 > /dev/null < /dev/null &
uml_switch -unix switch18 > /dev/null < /dev/null &
uml_switch -unix switch19 > /dev/null < /dev/null &
uml_switch -unix switch20 > /dev/null < /dev/null &
uml_switch -unix switch21 > /dev/null < /dev/null &
uml_switch -unix switch22 > /dev/null < /dev/null &
uml_switch -unix switch25 > /dev/null < /dev/null &

# Router
xterm -T SURABAYA -e linux ubd0=SURABAYA,jarkom umid=SURABAYA eth0=tuntap,,,10.151.70.17 eth1=daemon,,,switch1 eth2=daemon,,,switch2 eth3=daemon,,,switch4 eth4=daemon,,,switch13 mem=64M &
xterm -T PASURUAN -e linux ubd0=PASURUAN,jarkom umid=PASURUAN eth0=daemon,,,switch2 eth1=daemon,,,switch3 eth2=daemon,,,switch19 mem=64M &
xterm -T PROBOLINGGO -e linux ubd0=PROBOLINGGO,jarkom umid=PROBOLINGGO eth0=daemon,,,switch3 eth1=daemon,,,switch15 eth2=daemon,,,switch16 mem=64M &
xterm -T BATU -e linux ubd0=BATU,jarkom umid=BATU eth0=daemon,,,switch4 eth1=daemon,,,switch5 eth2=daemon,,,switch21 eth3=daemon,,,switch22 mem=64M &
xterm -T MADIUN -e linux ubd0=MADIUN,jarkom umid=MADIUN eth0=daemon,,,switch22 eth1=daemon,,,switch25 mem=64M &
xterm -T KEDIRI -e linux ubd0=KEDIRI,jarkom umid=KEDIRI eth0=daemon,,,switch5 eth1=daemon,,,switch17 eth2=daemon,,,switch18 mem=64M &
xterm -T BLITAR -e linux ubd0=BLITAR,jarkom umid=BLITAR eth0=daemon,,,switch17 eth1=daemon,,,switch20 mem=64M &

# Server
xterm -T MALANG -e linux ubd0=MALANG,jarkom umid=MALANG eth0=daemon,,,switch18 mem=64M &
xterm -T MOJOKERTO -e linux ubd0=MOJOKERTO,jarkom umid=MOJOKERTO eth0=daemon,,,switch13 mem=64M &

# Klien
xterm -T SAMPANG -e linux ubd0=SAMPANG,jarkom umid=SAMPANG eth0=daemon,,,switch1 mem=64M &
xterm -T SIDOARJO -e linux ubd0=SIDOARJO,jarkom umid=SIDOARJO eth0=daemon,,,switch19 mem=64M &
xterm -T BANYUWANGI -e linux ubd0=BANYUWANGI,jarkom umid=BANYUWANGI eth0=daemon,,,switch16 mem=64M &
xterm -T JEMBER -e linux ubd0=JEMBER,jarkom umid=JEMBER eth0=daemon,,,switch16 mem=64M &
xterm -T BONDOWOSO -e linux ubd0=BONDOWOSO,jarkom umid=BONDOWOSO eth0=daemon,,,switch15 mem=64M &
xterm -T BOJONEGORO -e linux ubd0=BOJONEGORO,jarkom umid=BOJONEGORO eth0=daemon,,,switch25 mem=64M &
xterm -T JOMBANG -e linux ubd0=JOMBANG,jarkom umid=JOMBANG eth0=daemon,,,switch22 mem=64M &
xterm -T NGANJUK -e linux ubd0=NGANJUK,jarkom umid=NGANJUK eth0=daemon,,,switch21 mem=64M &
xterm -T TULUNGAGUNG -e linux ubd0=TULUNGAGUNG,jarkom umid=TULUNGAGUNG eth0=daemon,,,switch20 mem=64M &
xterm -T LUMAJANG -e linux ubd0=LUMAJANG,jarkom umid=LUMAJANG eth0=daemon,,,switch17 mem=64M &
```
pada setiap melakukan perintah ``` nano /etc/sysctl.conf ``` lalu menghapus # pada net.ipv4.ip_forward=1,
lalu melakukan konfigurasi pada ``` nano /etc/network/interfaces ``` seperti berikut
#SURABAYA
```
#cloud
auto eth0
iface eth0 inet static
address 10.151.70.18
netmask 255.255.255.252
gateway 10.151.70.47
 
#sampang
auto eth1
iface eth1 inet static
address 192.168.64.1
netmask 255.255.252.0
 
#pasuruan
auto eth2
iface eth2 inet static
address 192.168.192.1
netmask 255.255.255.252
 
#batu
auto eth3
iface eth3 inet static
address 192.168.32.1
netmask 255.255.255.252
 
#mojokerto
auto eth4
iface eth4 inet static
address 10.151.71.34
netmask 255.255.255.252

```
