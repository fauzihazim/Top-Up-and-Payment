# Top Up and Payment

![Node.js](https://logos-download.com/wp-content/uploads/2016/09/Node_logo_NodeJS.png)
## Keterangan
Repositori ini berisi implementasi backend untuk sistem Top Up dan Pembayaran (Node.js + MySQL). Selain itu dilengkapi dengan Nginx sebagai load balancer untuk menjaga performa utamanya ketika load tinggi dan Docker untuk menghindari dependency conflict. Aplikasi memiliki alur dan fitur berikut: registrasi dan autentikasi (JWT), manajemen profil dan unggah gambar, daftar banner & layanan, pengecekan saldo, Top Up, proses pembayaran, serta riwayat transaksi. Tujuan utamanya adalah untuk menunjukkan arsitektur API dan integrasi fungsionalitas; untuk penggunaan produksi diperlukan pengujian tambahan, audit keamanan, penanganan skala, validasi input lebih ketat, dan pengaturan konfigurasi deployment.

## Fitur

| Feature         | Description |
|---------------|------------|
| Register | User dapat melakukan registrasi `/registration` selanjutnya user akan menerima notifikasi hasil pendaftaran. |
| login | User dapat melakukan login melalui `/login`. Pada req.body user menambahkan email dan password, setelah itu user akan menerima access token untuk validasi |
| Profile | User dapat mengakses melalui `/profile`. Pada halaman ini user akan mendapatkan detail profilnya, tetapi user harus menambahkan `Bearer Token` yang didapat setelah Login. |
| Edit Profil | User dapat mengakses melalui `/profile/update`. Pada halaman ini user dapat mengedit profilenya, tetapi user harus menambahkan `Bearer Token` yang didapat setelah Login. |
| Upload Profile Image | User dapat mengakses melalui `/profile/image`. Pada halaman ini user dapat meng-upload image, tetapi user harus menambahkan `Bearer Token` yang didapat setelah Login. |
| Banner | User dapat mengakses melalui `/banner`. Pada halaman ini user akan mendapatkan list banner |
| Services | User dapat mengakses melalui `/services`. Pada halaman ini user akan mendapatkan list service, tetapi user harus menambahkan `Bearer Token` yang didapat setelah Login. |
| Get Balance | User dapat mengakses melalui `/balance`. Pada halaman ini user akan mendapatkan informasi balance/saldo terakhir, tetapi user harus menambahkan `Bearer Token` yang didapat setelah Login. |
| Top Up | User dapat mengakses melalui `/topup`. Pada halaman ini user dapat melakukan TopUp atau menambah saldo, tetapi user harus menambahkan `Bearer Token` yang didapat setelah Login. |
| Transaction | User dapat mengakses melalui `/transaction`. Pada halaman ini user dapat melakukan transaction berupa pembayaran/payment dan saldo/balance akan berkurang, tetapi user harus menambahkan `Bearer Token` yang didapat setelah Login. |
| Transaction History | User dapat mengakses melalui `/transaction/history`. Pada halaman ini user dapat mendapatkan history transaksi baik TopUp maupun pembayaran/payment, tetapi user harus menambahkan `Bearer Token` yang didapat setelah Login. |

## Teknologi
- **Backend**: Node.js (Express)
- **Database**: MySQL
- **Containerization**: Docker
- **Load Balancer**: Nginx

**Alasan MySQL cocok untuk proyek ini**:  
- Mengelola data keuangan dengan terstruktur dan relasi yang jelas (ACID) sehingga cocok untuk transaksi keuangan
- Menawarkan konsistensi data lebih baik dibanding NoSQL

## Prasyarat
- Docker

## Instalasi
1. Clone repository:
   ```bash
   git clone https://github.com/fauzihazim/Top-Up-and-Payment.git

2. Menuju ke folder tersebut
    ```bash
   cd top-up-and-payment 
3. Menjalankan project dengan Docker
    ```bash
   docker-compose up -d --build 
4. Testing
   ``` bash
   npm test

