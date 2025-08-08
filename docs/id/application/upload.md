---
sidebar_position: 1
---

# Upload (Deprecated)

### Internal Usage

Metode ini diperlukan untuk mengakomodasi kebutuhan internal ketika ingin melakukan deployment tanpa perlu melakukan perubahan ke git repository. Proses build dan compression aplikasi dilakukan di device developer secara manual. Deployment dilakukan dengan melakukan dengan menjalankan perintah `dpanel deploy ./artifact.tar.gz` di dalam folder project.