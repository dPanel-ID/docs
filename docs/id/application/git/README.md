---
sidebar_position: 0
---

# Git

dPanel dirancang untuk mengotomatiskan dan menyederhanakan proses penghubungan antara repositori Git dan deployment aplikasi, memungkinkan pengembang untuk lebih fokus pada pengembangan kode dan tidak perlu mengelola proses deployment secara manual. Dengan integrasi langsung antara Git dan sistem deployment, platform ini mempercepat siklus pengembangan perangkat lunak, meningkatkan efisiensi, dan mengurangi risiko kesalahan selama proses deploy.

dPanel membutuhkan **file konfigurasi** yang memastikan aplikasi dapat ter-deploy dengan benar dan sesuai dengan pengaturan yang diinginkan. File konfigurasi ini memainkan peran penting dalam mendefinisikan bagaimana aplikasi akan dibangun, dikonfigurasi, dan dijalankan pada server atau cloud environment yang dipilih.

## Fungsi

1. Memungkinkan pengguna untuk mendefinisikan dependencies yang diperlukan oleh aplikasi di file konfigurasi. Ini mencakup framework, pustaka, atau perangkat lunak lain yang dibutuhkan agar aplikasi dapat berjalan dengan baik pada server atau lingkungan cloud.

2. Berfungsi untuk mendefinisikan skrip build yang digunakan untuk membangun aplikasi sebelum diterapkan, serta skrip deployment yang menentukan bagaimana aplikasi akan di-deploy pada server atau container yang dipilih.

3. Berisi definisi berbagai variabel lingkungan, seperti database connection strings, API keys, dan konfigurasi lainnya yang diperlukan selama aplikasi berjalan.

4. Dengan menggunakan file konfigurasi yang dikelola dalam Git repository, pengguna dapat dengan mudah melacak perubahan dalam pengaturan deployment aplikasi. Jika ada kesalahan atau kebutuhan untuk kembali ke konfigurasi sebelumnya, pengguna dapat menggunakan kontrol versi Git untuk mengembalikan file konfigurasi ke versi yang lebih stabil.

5. Mendukung penggunaan file konfigurasi untuk multiple environments (seperti dev, staging, dan production), memungkinkan pengelolaan aplikasi yang lebih efisien di berbagai tahap pengembangan dan deployment. Setiap lingkungan dapat memiliki pengaturan berbeda dalam file konfigurasi, memastikan aplikasi bekerja dengan benar di setiap tahap.

## Persyaratan

Berikut adalah persyaratan untuk dapat membuat file konfigurasi:

1. File konfigurasi harus menggunakan format yang didukung, yakni YAML.

2. File konfigurasi dapat di buat di folder `.devetek`.

3. Di dalam repository dapat memiliki lebih dari 1 file konfigurasi. Manfaat dari pemisahan file konfigurasi ini salah satunya untuk memisahkan environment jika memiliki multi-versi (*alpha, staging, beta, production*).

## Spesifikasi

File konfigurasi memiliki 3 komponen utama sebagai spesifikasi untuk dapat digunakan sebagai pengaturan deployment aplikasi:

### 1. Setup

Digunakan untuk membuat pengaturan global yang digunakan saat membangun aplikasi (*buildtime*) dan menjalankan aplikasi (*runtime*).

| Nama | Deskripsi |
|--|--|
| language.name | Nama bahasa pemrograman yang digunakan | 
| language.version | Versi bahasa pemrograman yang digunakan |

Contoh:
```sh
setup:
  language:
    name: nodejs
    version: v18.19.0
```

### 2. Build

Digunakan untuk mengatur kebutuhan aplikasi selama proses pembangunan aplikasi.

| Nama | Deskripsi |
|--|--|
| build.target.(WORKER_NAME) | Digunakan untuk memilih pekerja yang digunakan untuk membangun aplikasi |
| build.target.(WORKER_NAME).workdir | Lokasi directory yang digunakan saat membangun aplikasi |
| build.target.(WORKER_NAME).steps | Peraturan yang akan digunakan selama proses membangun |
| build.target.(WORKER_NAME).steps.command | Langkah-langkah yang dijalankan untuk membangun aplikasi |
| build.target.(WORKER_NAME).steps.archive | Daftar file dan folder yang akan dijadikan artefak |
| build.target.(WORKER_NAME).environment | Variabel lingkungan yang digunakan saat membangun aplikasi |
| build.target.(WORKER_NAME).environment.key | Nama variabel lingkungan buildtime |
| build.target.(WORKER_NAME).environment.value | Isi variabel lingkungan buildtime |

Contoh:
```sh
build:
  target:
    machine:
      workdir: .
      steps:
        - name: "Build laravel application"
          cmd:
            # (ignore error!) clear previous cache
            - php artisan optimize:clear | echo "No cache need to clear"

            # create configuration
            - touch database.db # create sqllite database
            - cp .env.example .env # create config from example

            # install dependencies
            - composer install --optimize-autoloader --no-dev
            - php artisan migrate
            # (ignore error!)
            - php artisan storage:link | echo "storage:link alrady exist"

            # (ignore error!) re-create cache
            - php artisan key:generate | echo "APP_KEY already exist"
            - php artisan optimize
        - name: "create application artifact"
          archive:
            - ./.next
            - ${BUILD_DIR}
            - node_modules
        environment:
            - key: BUILD_DIR
            value: .build-$(git rev-parse --short HEAD)
            - key: BUILD_ENV
            value: beta
```

### 3. Run

Digunakan untuk mengatur kebutuhan saat aplikasi berjalan.

| Nama | Deskripsi |
|--|--|
| run.name | Nama aplikasi saat berjalan |
| run.description | Deskripsi aplikasi saat berjalan |
| run.command | Script yang digunakan aplikasi untuk berjalan |
| run.port | Port yang digunakan aplikasi untuk berjalan |
| run.environment | Variabel lingkungan yang digunakan saat membangun aplikasi |
| run.environment.key | Nama variabel lingkungan runtime |
| run.environment.value | Isi variabel lingkungan runtime |
| no_service | Digunakan jika tidak diperlukan membuat service |

Contoh:
```sh
run:
  name: nextjs-example
  description: NextJS Example
  command: node .next/standalone/server.js
  port: 3000
  environment:
    - key: PORT
      value: 3000
```

```sh
run:
  name: vitejs-example
  no_service: true
```

Untuk contoh lengkap bagaimana file konfigurasi di aplikasi, di bawah adalah contoh-contoh dari beberapa framework terkenal.

## Template

Untuk mempermudah pengguna, dPanel menyediakan template yang dapat digunakan sebagai contoh untuk melakukan deployment aplikasi dengan framework populer.

- [Laravel](https://github.com/dPanel-ID/laravel-example)
- [Next.js 14](https://github.com/dPanel-ID/nextjs14-example)
- [vite.dev](https://github.com/dPanel-ID/vite-example)
- [Docusaurus](https://github.com/dPanel-ID/docs)
- [CodeIgniter 3](https://github.com/dPanel-ID/codeigniter3-example)
- [ElysiaJS](https://github.com/dPanel-ID/elysiajs-example)
- [Remix](https://github.com/dPanel-ID/remix-example)
- [Modern.js](https://github.com/dPanel-ID/modernjs-example)
- [Golang](https://github.com/dPanel-ID/go-example)
- [Flask + uWSGI](https://github.com/dPanel-ID/flask-example)