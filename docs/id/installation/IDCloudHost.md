---
sidebar_position: 3
---

# IDCloudHost

Membuat server IDCloudHost dari dPanel, mempermudah pengelolaan server secara terpadu tanpa perlu berpindah-pindah dashboard.

Ikuti langkah berikut:

### Login IDCloudHost Console 

Kunjungi halaman login [console IDCloudHost](https://console.idcloudhost.com/hub/login) dan login dengan akun IDCloudHost.

### Buat Token

Buat token di IDCloudHost console yang akan digunakan di dPanel.

![create-token-idcloudhost](./../../assets/idcloudhost-token.png)

Salin *Token* di halaman detail token

![copy-token-idcloudhost](./../../assets/idcloudhost-token-detail.png)

### Buat *Cloud Provider* IDCloudHost

Buat Cloud Project baru di dPanel, dan pilih provider `IDCloudHost`.

![paste-token-idcloudhost](./../../assets/create-cloud-project-idcloudhost-dark.png)

### Buat server instant

Masuk ke halaman buat server [di sini](https://cloud.terpusat.com/v2/resources/servers/create), dan buat server instant.

![create-server-instant-idcloudhost](./../../assets/create-server-instant-dark.png)

Gunakan provider `IDCloudHost` dan pilih token yang sudah dibuat. Lalu masukkan informasi server, seperti regional, CPU, RAM, dan disk, dan lain-lain.

![create-server-instant-input-idcloudhost](./../../assets/create-server-instant-input-dark.png)