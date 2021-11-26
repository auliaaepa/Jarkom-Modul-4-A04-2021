# Jarkom-Modul-4-A04-2021

**Nama Anggota Kelompok:**
* Julietta Anastasia Rodiah Boru Panjaitan (05111940000033)
* Aulia Eka Putri Aryani (05111940000044)
* Abdun Nafi’ (05111940000066)

Prefix IP: 10.1

## Soal
Pada soal ini diminta untuk membuat subnetting dan routing menggunakan Cisco Packet Tracer dan GNS3 dengan metode perhitungan classless yang berbeda, dimana pembagian IP dan routing harus seefisien mungkin.

### Cisco - VLSM
1. Buat topologi hingga diperoleh hasil sebagai berikut.

2. Beri label pada setiap subnet.
    ![Subnetting-VLSM + server](https://user-images.githubusercontent.com/76677130/143471095-40470956-64cf-4656-a960-eb43dbd6ad9a.png)
3. Hitung jumlah alamat IP yang dibutuhkan oleh tiap subnet.
    | **Subnet** | **Jumlah IP** | **Netmask** |
    | :---: | :---: | :---: |
    | A1 | 101 | /25 |
    | A2 | 2021 | /22 |
    | A3 | 2 | /30 |
    | A4 | 701 | /22 |
    | A5 | 2 | /30 |
    | A6 | 1001 | /22 |
    | A7 | 2 | /30 |
    | A8 | 2 | /30 |
    | A9 | 521 | /22 |
    | A10 | 502 | /23 |
    | A11 | 13 | /28 |
    | A12 | 2 | /30 |
    | A13 | 252 | /24 |
    | A14 | 721 | /22 |
    | A15 | 2 | /30 |
    | **Total** | **5845** | **/19** |
4. Hitung pembagian IP (subnetting) berdasarkan netmask yang diperoleh melalui perhitungan jumlah ip (/19) menggunakan pohon sebagai berikut.
    ![Subnetting-tree](https://user-images.githubusercontent.com/76677130/143471573-f8869d21-ba03-4003-abdb-19d74dc569a1.png)
    Berikut adalah hasil perhitungan IP setiap subnet berdasarkan pohon tersebut.

5. Atur IP untuk masing-masing interface pada setiap router dengan cara `klik router` > `Config` > `INTERFACE` > `(nama interface)`, isi `IP Configuration` (IPv4 Address dan Subnet Mask) dengan hasil subnetting, dan ubah `Port Status` menjadi on.
    * Pucci
        * FastEthernet0/0 (mengarah ke Water7)
            ```
            IPv4 Address : 
            Subnet Mask : 
            ```
            
        * FastEthernet0/1 (mengarah ke Jipangu)
            ```
            IPv4 Address : 
            Subnet Mask : 
            ```
            
        * FastEthernet1/0 (mengarah ke Courtyard dan Calmbelt)
            ```
            IPv4 Address : 
            Subnet Mask : 
            ```
            
    * Dan seterusnya
6. Atur IP untuk masing-masing interface pada setiap end system (server dan client) dengan cara `klik end system` > `Desktop` > `IP Configuration`, dan ubah `IPv4 Address`, `Subnet Mask`, serta `Default Gateway` dengan hasil subnetting dan IP router.
    * Jipangu
        ```
        IPv4 Address : 
        Subnet Mask : 
        Default Gateway : 
        ```
    * Courtyard
        ```
        IPv4 Address : 
        Subnet Mask : 
        Default Gateway : 
        ```
    * Calmbelt
        ```
        IPv4 Address : 
        Subnet Mask : 
        Default Gateway : 
        ```
    * Dan seterusnya
7. Atur static route untuk setiap router dengan cara `klik router` > `Config` > `ROUTING` > `Static`, dan tambahkan `Network`, `Mask`, dan `Next Hop` untuk seluruh end system yang dapat terhubung memlaui router tersebut.
    * Foosha
        ```
        
        ```
    * Water7
        ```
        
        ```
    * Pucci
        ```
        
        ```
    * Guanhao
        ```
        
        ```
    * Alabasta
        ```
        
        ```
    * Oimo
        ```
        
        ```
    * Seastone
        ```
        
        ```
8. Testing pengaturan subnetting dan routing
    * ... menuju ...
    * Dan seterusnya 

### GNS3 - CIDR
1. Buat topologi hingga diperoleh hasil sebagai berikut.

2. Beri label pada setiap subnet.
    ![Subnetting-CIDR-1](https://user-images.githubusercontent.com/76677130/143618962-98fd9b20-d984-45a6-803d-d95bc9ea83ea.png)
3. Gabungkan subnet untuk memperoleh subnet terbesar.
    * Tahap ke-1
        ![Subnetting-CIDR-2](https://user-images.githubusercontent.com/76677130/143619037-1c2e96ce-9339-4912-9b52-056d69200a90.png)
    * Tahap ke-2
        ![Subnetting-CIDR-3](https://user-images.githubusercontent.com/76677130/143619047-f62ab743-bb09-4d9c-a490-ce575ef7c4f3.png)
    * Tahap ke-3
        ![Subnetting-CIDR-4](https://user-images.githubusercontent.com/76677130/143619057-43fb6bc7-feab-4244-8d9d-4e039d86de07.png)
    * Tahap ke-4
        ![Subnetting-CIDR-5](https://user-images.githubusercontent.com/76677130/143619062-87ee32ac-22d4-44de-8ab4-fbd10844e705.png)
    * Tahap ke-5
        ![Subnetting-CIDR-6](https://user-images.githubusercontent.com/76677130/143619072-3ed3261d-8897-4471-a264-6b4b34a931b5.png)
    * Tahap ke-6
        ![Subnetting-CIDR-7](https://user-images.githubusercontent.com/76677130/143619082-e7eb88cc-7f44-46f6-9068-093ce7c3c2c2.png)
    * Tahap ke-7
        ![Subnetting-CIDR-8](https://user-images.githubusercontent.com/76677130/143619097-e06a1332-3ae7-4e94-8236-45c7e2969811.png)
    * Tahap ke-8
        ![Subnetting-CIDR-9](https://user-images.githubusercontent.com/76677130/143619111-994f5947-17d7-4ef8-96c9-dc40ba3a49d5.png)
4. Hitung pembagian IP (subnetting) berdasarkan penggabungan subnet yang telah dilakukan dengan pohon sebagai berikut.
    ![Subnetting-CIDR-TREE](https://user-images.githubusercontent.com/76677130/143619160-f2a442e2-70ac-4060-a1e6-d1c1611ef682.png)
    Berikut adalah hasil perhitungan IP setiap subnet berdasarkan pohon tersebut.
    
5. Atur IP untuk masing-masing interface pada setiap device dengan cara `klik device` > `Configure` > `Edit Network Configuration` dan ubah menjadi sebagai berikut.
    * Foosha
        ```
        
        ```
    * Dan seterusnya
6. Routing untuk setiap router dengan menuliskan perintah sebagai berikut.
    * Foosha
        ```
        
        ```
    * Dan seterusnya
7. Testing pengaturan subnetting dan routing dengan melakukan ping ke its.ac.id
    * ...
    * Dan seterusnya
