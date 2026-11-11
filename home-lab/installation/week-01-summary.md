# Week 01 — Bangun Home Lab Pertama

## Learning Objectives
- Memastikan perangkat host (laptop) memenuhi persyaratan untuk menjalankan Virtual Machine (VM).
- Memahami konfigurasi dasar VM dan teknologi virtualisasi.
- Menyiapkan dan mengonfigurasi lingkungan Linux (Debian & Kali Linux) untuk praktikum cybersecurity.
- Mengelola jaringan virtual (NAT vs Host-only) dan menguji konektivitas sistem.
- Menerapkan pembuatan snapshot sebagai titik pemulihan sistem (restore point).

## Learning Activities
- Memeriksa spesifikasi hardware dan status hypervisor/virtualisasi pada host Windows.
- Mengalokasikan sumber daya VM (RAM, vCPU, Disk) menggunakan VMware Workstation.
- Mengidentifikasi antarmuka jaringan, alamat IP, penggunaan memori, dan tabel routing pada Linux menggunakan CLI.
- Menguji konektivitas jaringan (ICMP/ping) dari Guest OS ke internet.
- Memperbarui sistem operasi (`apt update` & `upgrade`) dan membuat snapshot VMware.
- Menganalisis perbedaan konektivitas saat berpindah dari mode jaringan NAT ke Host-only.

## Lab Environment

| Component | Configuration |
| :--- | :--- |
| **Host OS** | Windows 11 (AMD Ryzen 5 6600H, 16GB RAM) |
| **Virtualization** | VMware Workstation |
| **Guest OS** | Debian Linux (Lab 1) / Kali Linux (Lab 2-5) |
| **CPU** | 2 vCPU -> 4 vCPU |
| **RAM** | 4 GB |
| **Storage** | 80 GB |
| **Network** | NAT / Host-only |

## Documentation

Complete practical lab reports for Week 01:

| Lab | Report |
|---|---|
| D-001 | [Lab D-001](./lab-d-001.md) |
| D-002 | [Lab D-002](./lab-d-002.pdf) |
| D-003 | [Lab D-003](./lab-d-003.pdf) |
| D-004 | [Lab D-004](./lab-d-004.pdf) |
| D-005 | [Lab D-005](./lab-d-005.pdf) |

## Key Takeaways
- **Verifikasi Sistem:** Kapasitas RAM host 16 GB sangat ideal untuk menjalankan virtualisasi. Pemeriksaan awal melalui PowerShell dan `systeminfo` penting untuk memastikan hypervisor Windows aktif sebelum instalasi VM.
- **Utilitas CLI Linux:** Mahir menggunakan perintah dasar Linux seperti `ip addr` (cek IP), `ip route` (tabel routing), `nproc` (cek CPU), `lsblk` (partisi disk), dan `free -h` (cek RAM/Swap) sangat esensial untuk memvalidasi alokasi *hardware* virtual dari dalam Guest OS.
- **Isolasi Jaringan (NAT vs Host-only):** Mode NAT memberikan akses internet kepada VM melalui gateway host (memungkinkan `ping 8.8.8.8` berhasil dengan 0% packet loss), sedangkan mode Host-only mengisolasi VM ke jaringan privat lokal yang memutuskan koneksi ke internet luar (*Network is unreachable*).
- **Manajemen Risiko (Snapshot):** Membuat snapshot (`clean-install`) sesaat setelah pembaruan sistem operasi memastikan tersedianya titik pemulihan yang bersih (baseline) sebelum melakukan pengujian keamanan atau konfigurasi tingkat lanjut.

## Evidence

The following screenshots provide evidence of the practical activities completed during Week 01.

### 1. Virtual Machine Configuration

![VM Configuration](../screenshots/vm-configuration.png)

*VM hardware configuration, including allocated CPU, RAM, and storage.*

### 2. Linux Network Configuration

![Linux Network](../screenshots/linux-network.png)

*Linux network interface and routing table verification using CLI commands.*

### 3. Network Connectivity Testing

![Network Connectivity](../screenshots/network-connectivity.png)

*Network connectivity testing under NAT and Host-only configurations.*

### 4. VM Snapshot Management

![VM Snapshot](../screenshots/vm-snapshot.png)

*Creating the clean-install snapshot as a recovery point.*

