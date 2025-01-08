---
sidebar_position: 2
---

# Manual

Mendaftarkan mesin dari berbagai cloud provider menggunakan SSH private key yang dibuat dari dPanel. Akan mengurangi waktu instalasi server secara manual

1. Buat SSH Key di dPanel

![create-ssh-keygen](./../../assets/create-ssh-key.png)

2. Open SSH Key

![open-ssh-pubkey](./../../assets/open-ssh-key.png)

3. Copy SSH Public Key

![copy-ssh-pubkey](./../../assets/copy-ssh-key.png)

4. Login via SSH to the Server.

```sh
ssh <yourUser>@<yourIpAddress>
```

5. Paste SSH public key ke dalam mesin di file `~/.ssh/authorized_keys`

6. Buat Virtual Machine External di dPanel

![create-virtual-machine-external](./../../assets/create-virtual-machine-external.png)


6. Setup Virtual Machine External di dPanel

![create-virtual-machine-external](./../../assets/setup-virtual-machine.png)