---
sidebar_position: 4
---

# Service Management

Service Management menyediakan antarmuka yang mudah digunakan untuk memantau dan mengelola layanan (services) yang berjalan pada sistem, baik yang dikelola oleh systemd maupun Docker.

🔍 Fitur Utama:
- Lihat Status Layanan: Pantau status terkini dari setiap service – apakah sedang berjalan (active), berhenti (inactive), atau gagal (failed).
- Start Service: Memulai layanan secara manual kapan saja dibutuhkan.
- Stop Service: Menghentikan layanan yang sedang berjalan.
- Restart Service: Melakukan restart layanan untuk menerapkan konfigurasi baru atau memulihkan dari error.
- Dukungan Ganda: Mendukung manajemen layanan untuk:
    - Systemd Services (contoh: nginx, ssh, mysql)
    - Docker Containers (mengelola container sebagai service, seperti nginx:latest, my-app)

🎯 Kegunaan:
Panel ini sangat berguna bagi administrator sistem dan developer untuk:
- Melakukan troubleshooting dengan cepat
- Memastikan layanan penting tetap berjalan
- Mengontrol lifecycle dari layanan tanpa perlu menggunakan terminal