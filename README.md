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
