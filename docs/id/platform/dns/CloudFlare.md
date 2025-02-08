---
sidebar_position: 0
---

# Cloudflare

## Tambah Domain

1. Login ke CloudFlare Dashboard [di sini](https://dash.cloudflare.com/login)

2. Pilih domain di halaman "Website"

![CloudFlare Domains](./../../../assets/cloudflare-select-domain.png)

3. Salin domain Zone ID

![CloudFlare Domain Zone ID](./../../../assets/cloudflare-zone-id.png)

4. Buat CloudFlare Token [di sini](https://dash.cloudflare.com/profile/api-tokens)

![CloudFlare Tokens](./../../../assets/cloudflare-create-token.png)

5. Gunakan Token Template "Edit Zone DNS"

![CloudFlare Token Template](./../../../assets/cloudflare-token-template.png)

6. Pilih detail pengaturan token

![CloudFlare Token Detail](./../../../assets/cloudflare-token-detail.png)

7. Tambah domain [di sini](https://cloud.terpusat.com/domain)

![CloudFlare Token Detail](./../../../assets/cloudflare-add-domain.png)

## Kelola Domain

Setelah sukses [tambah domain](/docs/id/platform/dns/add-domain), pengelolaan domain di dPanel akan mempermudah proses integrasi dengan ekosistem aplikasi. Beberapa hal yang dapat dilakukan di platform *Kelola Domain*: 

## Tambah Subdomain

Menambahkan subdomain dengan type A dapat langsung diarahkan ke *sumber daya terkelola* (virtual machine) yang sudah dibuat di dPanel.

![Add Subdomain](./../../../assets/subdomain-add.png)

<!-- ## Ubah Subdomain

Coming soon! -->

## Hapus Subdomain

Untuk mnghapus subdomain yang sudah tidak digunakan, berikut langkah-langkah:

![Delete Subdomain](./../../../assets/sudomain-delete.png)
