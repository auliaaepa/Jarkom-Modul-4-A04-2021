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
    ![WhatsApp Image 2021-11-27 at 17 14 42](https://user-images.githubusercontent.com/76677130/143677195-fc276d4e-4fe3-4830-a615-56f68241c256.jpeg)    
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
    | **Subnet**	| **NID**	| **Subnet Mask**	| **Broadcast Address** |
    | :---: | :---: | :---: | :---: |
    | A1	| 10.1.0.128	| 255.255.255.128	| 10.1.0.255 |
    | A2	| 10.1.24.0	| 255.255.248.0	| 10.1.31.255 |
    | A3	| 10.1.0.0	| 255.255.255.252	| 10.1.0.3 |
    | A4	| 10.1.4.0	| 255.255.252.0	| 10.1.7.255 |
    | A5	| 10.1.0.4	| 255.255.255.252	| 10.1.0.7 |
    | A6	| 10.1.8.0	| 255.255.252.0	| 10.1.11.255 |
    | A7	| 10.1.0.32	| 255.255.255.252	| 10.1.0.35 |
    | A8	| 10.1.0.8	| 255.255.255.252	| 10.1.0.11 |
    | A9	| 10.1.12.0	| 255.255.252.0	| 10.1.15.255 |
    | A10	| 10.1.2.0	| 255.255.254.0	| 10.1.3.255 |
    | A11	| 10.1.0.16	| 255.255.255.240	| 10.1.0.31 |
    | A12	| 10.1.0.12	| 255.255.255.252	| 10.1.0.13 |
    | A13	| 10.1.1.0	| 255.255.255.0	| 10.1.1.255 |
    | A14	| 10.1.16.0	| 255.255.252.0	| 10.1.19.255 |
    | A15	| 10.1.0.36	| 255.255.255.252	| 10.1.0.39 |
5. Atur IP untuk masing-masing interface pada setiap router dengan cara `klik router` > `Config` > `INTERFACE` > `(nama interface)`, isi `IPv4 Address` dan `Subnet Mask` pada IP Configuration dengan hasil subnetting, serta ubah `Port Status` menjadi on.
    * PUCCI
        ```
        # FastEthernet0/0 (mengarah ke WATER7)
        IPv4 Address : 10.1.0.2
        Subnet Mask : 255.255.255.252
        
        # FastEthernet0/1 (mengarah ke JIPANGU)
        IPv4 Address : 10.1.0.129
        Subnet Mask : 255.255.255.128
        
        # FastEthernet1/0 (mengarah ke COURTYARD dan CALMBELT)
        IPv4 Address : 10.1.24.1
        Subnet Mask : 255.255.248.0
        ```     
        ![WhatsApp Image 2021-11-27 at 21 35 01](https://user-images.githubusercontent.com/76677130/143686070-ba73954d-e0d5-489c-9383-99295979fa8a.jpeg)
    * Dan seterusnya
6. Atur IP untuk masing-masing interface pada setiap end system (server dan client) dengan cara `klik end system` > `Desktop` > `IP Configuration`, dan ubah `IPv4 Address`, `Subnet Mask`, serta `Default Gateway` dengan hasil subnetting dan IP interface router.
    * JIPANGU
        ```
        IPv4 Address : 10.1.0.130
        Subnet Mask : 255.255.255.128
        Default Gateway : 10.1.0.129
        ```
    * COURTYARD
        ```
        IPv4 Address : 10.1.24.2
        Subnet Mask : 255.255.248.0
        Default Gateway : 10.1.24.1
        ```
    * CALMBELT
        ```
        IPv4 Address : 10.1.24.3
        Subnet Mask : 255.255.248.0
        Default Gateway : 10.1.24.1
        ```
        ![WhatsApp Image 2021-11-27 at 21 37 07](https://user-images.githubusercontent.com/76677130/143686076-9f99a9c5-8329-43fa-9e83-12631b592e23.jpeg)
    * Dan seterusnya
7. Atur static route untuk setiap router dengan cara `klik router` > `Config` > `ROUTING` > `Static`, dan tambahkan `Network`, `Mask`, dan `Next Hop` untuk seluruh device baik end system maupun router yang dapat terhubung melalui router tersebut.
    * FOOSHA
        ```
        Network 10.1.4.0 Mask 255.255.252.0 Next Hop 10.1.0.6
        Network 10.1.0.128 Mask 255.255.255.128 Next Hop 10.1.0.6
        Network 10.1.24.0 Mask 255.255.248.0 Next Hop 10.1.0.6
        Network 10.1.0.0 Mask 255.255.255.252 Next Hop 10.1.0.6
        Network 10.1.12.0 Mask 255.255.252.0 Next Hop 10.1.0.10
        Network 10.1.2.0 Mask 255.255.254.0 Next Hop 10.1.0.10
        Network 10.1.0.16 Mask 255.255.255.240 Next Hop 10.1.0.10
        Network 10.1.0.12 Mask 255.255.255.252 Next Hop 10.1.0.10
        Network 10.1.1.0 Mask 255.255.255.0 Next Hop 10.1.0.10
        Network 10.1.16.0 Mask 255.255.252.0 Next Hop 10.1.0.10
        Network 10.1.0.36 Mask 255.255.255.252 Next Hop 10.1.0.10
        ```
    * WATER7
        ```
        Network 0.0.0.0 Mask 0.0.0.0 Next Hop 10.1.0.5
        Network 10.1.0.128 Mask 255.255.255.128 Next Hop 10.1.0.2
        Network 10.1.24.0 Mask 255.255.248.0 Next Hop 10.1.0.2
        ```
    * PUCCI
        ```
        Network 0.0.0.0 Mask 0.0.0.0 Next Hop 10.1.0.1
        ```
    * GUANHAO
        ```
        Network 0.0.0.0 Mask 0.0.0.0 Next Hop 10.1.0.9
        Network 10.1.1.0 Mask 255.255.255.0 Next Hop 10.1.0.14
        Network 10.1.16.0 Mask 255.255.252.0 Next Hop 10.1.0.14
        Network 10.1.0.36 Mask 255.255.255.252 Next Hop 10.1.0.14
        Network 10.1.0.16 Mask 255.255.255.240 Next Hop 10.1.2.2
        ```
    * ALABASTA
        ```
        Network 0.0.0.0 Mask 0.0.0.0 Next Hop 10.1.2.1
        ```
    * OIMO
        ```
        Network 0.0.0.0 Mask 0.0.0.0 Next Hop 10.1.0.13
        Network 10.1.16.0 Mask 255.255.252.0 Next Hop 10.1.1.2
        ```
    * SEASTONE
        ```
        Network 0.0.0.0 Mask 0.0.0.0 Next Hop 10.1.1.1
        ```
8. Testing pengaturan subnetting dan routing
    * CALMBERT menuju ELENA
        ![WhatsApp Image 2021-11-27 at 21 38 20](https://user-images.githubusercontent.com/76677130/143686083-70d2e5fa-37d3-4529-9e94-6fe18121cd36.jpeg)
    * FUKUROU menuju BLUENO
        ![WhatsApp Image 2021-11-27 at 21 40 06](https://user-images.githubusercontent.com/76677130/143686085-8ff08829-366d-4b80-adf0-7a1c00616bfc.jpeg)
    * DORIKI menuju ALABASTA
        ![WhatsApp Image 2021-11-27 at 21 41 03](https://user-images.githubusercontent.com/76677130/143686089-c374cc43-7dfe-4012-8ab9-e794e720c2fa.jpeg)
    * Dan seterusnya 

### GNS3 - CIDR
1. Buat topologi hingga diperoleh hasil sebagai berikut.
    ![WhatsApp Image 2021-11-27 at 21 41 40](https://user-images.githubusercontent.com/76677130/143686352-bb8602c2-09eb-4e2d-98ef-7a55cdf5b4cf.jpeg)
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
        ![Subnetting-CIDR-8](https://user-images.githubusercontent.com/76677130/143619097-e06a1332-3ae7-4e94-8236-45c7e2969811.png)
    * Tahap ke-7
        ![Subnetting-CIDR-9](https://user-images.githubusercontent.com/76677130/143619111-994f5947-17d7-4ef8-96c9-dc40ba3a49d5.png)
4. Hitung pembagian IP (subnetting) berdasarkan penggabungan subnet yang telah dilakukan dengan pohon sebagai berikut.
    ![Subnetting-CIDR-tree](https://user-images.githubusercontent.com/76677130/143620568-dfd7502b-5e15-4960-b2b9-3358dfe464c3.png)
    Berikut adalah hasil perhitungan IP setiap subnet berdasarkan pohon tersebut.
    | **Subnet**	| **NID**	| **Subnet Mask**	| **Broadcast Address** |
    | :---: | :---: | :---: | :---: |
    | A1	| 10.1.8.0	| 255.255.255.128	| 10.1.8.127 |
    | A2	| 10.1.0.0	| 255.255.248.0	| 10.1.7.255 |
    | A3	| 10.1.16.0	| 255.255.255.252	| 10.1.16.3 |
    | A4	| 10.1.32.0	| 255.255.252.0	| 10.1.35.255 |
    | A5	| 10.1.64.0	| 255.255.255.252	| 10.1.64.3 |
    | A6	| 10.1.128.0	| 255.255.252.0	| 10.1.131.255 |
    | A7	| 10.2.128.0	| 255.255.255.252	| 10.2.128.3 |
    | A8	| 10.2.64.0	| 255.255.255.252	| 10.2.64.3 |
    | A9	| 10.2.36.0	| 255.255.252.0	| 10.2.39.255 |
    | A10	| 10.2.32.0	| 255.255.254.0	| 10.2.33.255 |
    | A11	| 10.2.34.0	| 255.255.255.240	| 10.2.34.15 |
    | A12	| 10.2.16.0	| 255.255.255.252	| 10.2.16.3 |
    | A13	| 10.2.4.0	| 255.255.255.0	| 10.2.4.255 |
    | A14	| 10.2.0.0	| 255.255.252.0	| 10.2.3.255 |
    | A15	| 10.2.8.0	| 255.255.255.252	| 10.2.8.3 |
5. Atur IP untuk masing-masing interface pada setiap device dengan cara `klik kanan device` > `Configure` > `Edit Network Configuration` dan ubah menjadi sebagai berikut.
    * OIMO
        ```
        ## A12+
        auto eth0
        iface eth0 inet static
          address 10.2.16.2
          netmask 255.255.255.252
          
        ## A13-
        auto eth1
        iface eth1 inet static
          address 10.2.4.1
          netmask 255.255.255.0
          
        ## A15-
        auto eth2
        iface eth2 inet static
          address 10.2.8.1
          netmask 255.255.255.252
        ```
    * ENIESLOBBY
        ```
        ## A13+
        auto eth0
        iface eth0 inet static
          address 10.2.4.2
          netmask 255.255.255.0
          gateway 10.2.4.1
        ```
    * SEASTONE
        ```
        ## A13+
        auto eth0
        iface eth0 inet static
          address 10.2.4.3
          netmask 255.255.255.0
          
        ## A14-
        auto eth1
        iface eth1 inet static
          address 10.2.0.1
          netmask 255.255.252.0
        ```
    * ELENA
        ```
        ## A14+
        auto eth0
        iface eth0 inet static
          address 10.2.0.2
          netmask 255.255.252.0
          gateway 10.2.0.1
        ```
    * FUKUROU
        ```
        ## A15+
        auto eth0
        iface eth0 inet static
          address 10.2.8.2
          netmask 255.255.255.252
          gateway 10.2.8.1
        ```
        ![WhatsApp Image 2021-11-27 at 21 45 16](https://user-images.githubusercontent.com/76677130/143686358-138085e4-7210-4c61-9d95-85e8fbc65aa2.jpeg)
    * Dan seterusnya
6. Routing untuk setiap router dengan menuliskan perintah sebagai berikut.
    * FOOSHA
        ```
        ## A5
        route add -net 10.1.32.0 netmask 255.255.252.0 gw 10.1.64.2   # A4
        route add -net 10.1.8.0 netmask 255.255.255.128 gw 10.1.64.2  # A1
        route add -net 10.1.0.0 netmask 255.255.248.0 gw 10.1.64.2    # A2
        route add -net 10.1.16.0 netmask 255.255.255.252 gw 10.1.64.2 # A3
        ## A8
        route add -net 10.2.36.0 netmask 255.255.252.0 gw 10.2.64.2   # A9
        route add -net 10.2.32.0 netmask 255.255.254.0 gw 10.2.64.2   # A10
        route add -net 10.2.34.0 netmask 255.255.255.240 gw 10.2.64.2 # A11
        route add -net 10.2.16.0 netmask 255.255.255.252 gw 10.2.64.2 # A12
        route add -net 10.2.4.0 netmask 255.255.255.0 gw 10.2.64.2    # A13
        route add -net 10.2.0.0 netmask 255.255.252.0 gw 10.2.64.2    # A14
        route add -net 10.2.8.0 netmask 255.255.255.252 gw 10.2.64.2  # A15
        ```
    * WATER7
        ```
        ## DEFAULT (A5)
        route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.1.64.1
        ## A3
        route add -net 10.1.8.0 netmask 255.255.255.128 gw 10.1.16.2  # A1
        route add -net 10.1.0.0 netmask 255.255.248.0 gw 10.1.16.2    # A2
        ```
    * PUCCI
        ```
        ## DEFAULT (A3)
        route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.1.16.1
        ```
    * GUANHAO
        ```
        ## DEFAULT (A8)
        route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.2.64.1
        ## A12
        route add -net 10.2.4.0 netmask 255.255.255.0 gw 10.2.16.2    # A13
        route add -net 10.2.0.0 netmask 255.255.252.0 gw 10.2.16.2    # A14
        route add -net 10.2.8.0 netmask 255.255.255.252 gw 10.2.16.2  # A15
        ## A10
        route add -net 10.2.34.0 netmask 255.255.255.240 gw 10.2.32.3 # A11
        ```
    * ALABASTA
        ```
        ## DEFAULT (A10)
        route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.2.32.1
        ```
    * OIMO
        ```
        ## DEFAULT (A12)
        route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.2.16.1
        ## A13
        route add -net 10.2.0.0 netmask 255.255.252.0 gw 10.2.4.3 # A14
        ```
    * SEASTONE
        ```
        ## DEFAULT (A13)
        route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.2.4.1
        ```
7. Hubungkan topologi dengan jaringan luar menggunakan perintah sebagai berikut.
    * FOOSHA
        ```
        iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.1.0.0/14
        ```
    * Device lainnya
        ```
        echo nameserver 192.168.122.1 > /etc/resolv.conf
        ```
9. Testing pengaturan subnetting dan routing
    * JIPANGU ping my.its.ac.id
        ![WhatsApp Image 2021-11-27 at 21 48 44](https://user-images.githubusercontent.com/76677130/143686382-948539e0-697e-4350-a977-f1660fd6a2fc.jpeg)
    * CALMBERT ping ELENA (10.2.0.2)
        ![WhatsApp Image 2021-11-27 at 21 49 36](https://user-images.githubusercontent.com/76677130/143686390-08bae8cb-7026-4bf7-a95f-43ffc579de1d.jpeg)
    * Dan seterusnya


## Kendala
Kendala yang dialami selama pengerjaan praktikum modul ini adalah sebagai berikut.
* Untuk pengaturan source iptables pada GNS3-CIDR tidak dapat menggunakan subnet terbesar yang diperoleh (/15) karena akan menghasilkan ip dengan range 10.0.0.0 - 10.1.255.255 bukan 10.1.0.0 - 10.2.255.255. Sehingga source iptables yang digunakan adalah 10.1.0.0/14 dengan range ip 10.0.0.0 - 10.3.255.255.
* Tidak dapat melakukan ping its.ac.id, sehingga menggunakan ping ke my.its.ac.id
