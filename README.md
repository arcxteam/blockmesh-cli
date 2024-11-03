FOTO FOTO

# Blockmesh Node, Run Validator Extension with Docker - Full Guides CLI

BlockMesh Network adalah proyek jaringan proxy terdesentralisasi yang memungkinkan pengguna mengakses internet secara aman dan privat melalui sistem sentinel node berjalan pada Solana blockchain.

## He We Go...Gas bang!!!
*Apakah ada disebutkan dalam FAQ atau Discord, Apakah ada insentif atau poin konversi??*
> **Insentif apa yang Anda tawarkan untuk berkontribusi pada jaringan? Belum ada konfirmasi untuk masalah ini**

*Tunggu aja, nanti gue update jika ada konfirmasi dari Dev*

| Aktivitas             | Alokasi |
|-----------------------|---------|
| Run Extention CLI | 0% (TBA) |
| Ingpo bang | (TBA) |

## 1. Persiapan Sebelum Jalankan Node
**1. Persyaratan hardware VPS** 

`Untuk menjalankan node extension sebagai CLI, perlu Linux server (VPS) spesifikasi rendah kentang bang`
| Spesifikasi                       | Rincian                                       |
|-----------------------------------|----------------------------------------------|
| RAM                               | 1-4 GB                                       |
| CPU/vCPU                          | 1-4 Cores                                    |
| Ruang Penyimpanan                 | 1-50 GB                                      |
| Dukungan OS                       | Ubuntu 22.04 LTS yang lain modif aja         |

**2. Persyaratan hardware BROWSER** 

`Untuk menjalankan node extension sebagai BROWSER, membutuhkan perangkat`
|  Spesifikasi                       | Rincian                                         |
|-----------------------------------|------------------------------------------------|
| Internet                          | Koneksi Stabil                            |
| Perangkat                         | Handphones, PC/Laptop/Netbooks, Tablet dll | 
| Web Browser                       | Chrome, Firefox, Safari, Opera, Brave, Edge, UC/Kiwi/Mises dll.. |

**3. Konfigurasi Blockmesh Node-CLI**

- Pertama registrasi untuk membuat akun [https://app.blockmesh.xyz/](https://app.blockmesh.xyz/register?invite_code=4441bdfe-90b2-4e99-b899-d2375d36fc30)
- Download extensi [Blockmesh](https://chromewebstore.google.com/detail/blockmesh-network/obfhoiefijlolgdmphcekifedagnkfjp) untuk login/koneksi pertama, setelah itu hapus
- Buka dashboard verifikasi lalu simpan alamat email dan kata sandi anda
- Jika belum ada `Docker` instal terlebih dahulu wajib
- Jika sudah punya semuanya langsung skip aja, cek tutor dibawah

## 2. Instal dan Build Langsung Lewat Docker

**1. Kloning repositori ini**

```
git clone https://github.com/arcxteam/blockmesh-cli.git
cd blockmesh-cli
```

**2. Jalankan CMD Perintah Ini**

- Edit alamat EMAIL=email_anda@example..com
- Edit alamat PASSWORD=password_anda
- Jalankan jangan lupa tanda (.) diakhir harus, tunggu beberapa menit dan siapkan kopi
- Baiknya jangan langsung copas di ssh, copas dulu dicatatan (menghindari salah perintah)
  
```
docker build -t blockmesh-cli --build-arg EMAIL=email_anda@example.com --build-arg PASSWORD=password_anda .
```
**CONTOH : docker build -t blockmesh-cli --build-arg EMAIL=bangsat69@gmail.com --build-arg PASSWORD=bangudahbang .**

- Jika sudah selesai build-docker, Selanjutnya paste perintah ini

```
docker run -d --name blockmesh-cli-container blockmesh-cli
```
- **SELESAI**, Node-CLI sudah berjalan pada Docker
- Cek pada dashboard website, apakah sudah `Connected` dengan IP Address VPS  [app.blockmesh.xyz](https://app.blockmesh.xyz/register?invite_code=4441bdfe-90b2-4e99-b899-d2375d36fc30)

## 3. Jika Ada Pembaruan Versi & Diharuskan

Setiap anda instal build Dockerfile repo ini sudah `versi terbaru` dan jika ingin update cek saja rilis versi terbarunya https://github.com/block-mesh/block-mesh-monorepo/releases

**1. Cara Update**

```
docker rm -f blockmesh-cli-container && \
docker build -t blockmesh-cli --build-arg EMAIL=email_anda@example.com --build-arg PASSWORD=password_anda . && \
docker run -d --name blockmesh-cli-container blockmesh-cli
```
- **Catatan: Alamat email & kata sandi harus di input lebih dahulu sebelum update**

## 4. Perintah CMD Semoga Berguna

**1. Basis-pada Docker**

`Start dan service`

- Cek logs blockmesh-cli: **docker logs -f blockmesh-cli-container**
- Hapus images: **docker rm blockmesh-cli-container**
- Jalankan ulang: **docker run -d --name blockmesh-cli-container blockmesh-cli**
- Jalankan stop: **docker stop blockmesh-cli-container**
- Melihat semua docker **docker ps -a** atau docker ps
- Melihat penggunaan cpu/ram dll **docker stats**
- docker ps | grep blockmesh-cli-container

`Bahaya Hapus Semua Blockmesh Node-CLI`

- Perintah hapus **docker stop blockmesh-cli-container && docker rm blockmesh-cli-container && rm -rf target/release**
