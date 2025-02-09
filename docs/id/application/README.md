# Aplikasi

dpanel dirancang untuk mempermudah proses deployment aplikasi dengan dua metode utama: integrasi Git dan upload file tarball. Dengan menggunakan platform ini, pengembang dapat memilih antara keduanya sesuai dengan kebutuhan proyek dan preferensi tim.

Untuk mendukung fleksibilitas dan efisiensi, dPanel mendukung pemilihan runtime server aplikasi ke berbagai provider seperti AWS, Azure, dan Google atau provider lain. Sehingga pengguna dapat menentukan provider sesuai dengan anggaran yang tersedia.

<!-- Untuk mendukung fleksibilitas dan efisiensi, dPanel juga mendukung pemilihan runtime aplikasi di beberapa lingkungan seperti virtual machine (VM), container, dan serverless dari berbagai provider seperti AWS, Azure, dan Google. -->

## Fitur Utama:

1. Pemilihan Cloud Provider yang Fleksibel: Pengguna dapat memilih cloud provider yang diinginkan untuk aplikasi mereka, seperti AWS, Google Cloud, atau Microsoft Azure. Platform ini mendukung deployment ke virtual machine yang disediakan oleh penyedia cloud, seperti Amazon EC2, Google Compute Engine, Azure atau provider lain.

<!-- 1. Pemilihan Cloud Provider yang Fleksibel: Pengguna dapat memilih cloud provider yang diinginkan untuk aplikasi mereka, seperti AWS, Google Cloud, atau Microsoft Azure. Platform ini mendukung deployment ke berbagai layanan yang disediakan oleh penyedia cloud, seperti Amazon EC2, Google Compute Engine, atau Azure Virtual Machines untuk VM, serta layanan container dan serverless mereka seperti Amazon ECS/EKS, Google Kubernetes Engine (GKE), dan Azure Functions. -->

2. Dukungan untuk Berbagai Jenis Lingkungan:

    - Virtual Machine (VM): Platform ini memungkinkan Anda untuk melakukan deployment aplikasi pada mesin virtual di penyedia cloud pilihan Anda. Ini memberikan kontrol penuh terhadap lingkungan dan konfigurasi server.

    <!-- - Containerized Applications: Platform ini juga mendukung deployment aplikasi berbasis Docker containers atau Kubernetes, memungkinkan penyebaran aplikasi yang lebih ringan, portabel, dan skalabel. Anda bisa memilih untuk menggunakan Amazon ECS, Google Kubernetes Engine (GKE), atau Azure Kubernetes Service (AKS) untuk mengelola dan mengatur container Anda.

    - Serverless Deployment: Bagi aplikasi yang memanfaatkan arsitektur tanpa server (serverless), platform ini menyediakan integrasi dengan layanan seperti AWS Lambda, Google Cloud Functions, dan Azure Functions. -->

<!-- 4. Pemilihan Lingkungan yang Mudah: Platform ini memungkinkan pengguna untuk memilih dan mengonfigurasi jenis lingkungan (VM, container, atau serverless) dengan mudah, memberikan fleksibilitas bagi tim untuk mengelola dan mengontrol aplikasi mereka sesuai dengan kebutuhan infrastruktur mereka. -->

3. Rollbacks dan Versioning: Platform ini menyertakan fitur untuk melacak versi aplikasi dan melakukan rollback jika ada masalah setelah deployment. Hal ini memastikan aplikasi Anda tetap stabil dan berjalan dengan lancar meskipun ada pembaruan yang gagal atau menyebabkan gangguan.