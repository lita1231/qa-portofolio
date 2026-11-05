# Test Case: Fitur Checkout (saucedemo.com)

**Lingkungan:** Google Chrome, https://www.saucedemo.com
**Akun:** standard_user
**Precondition umum:** Pengguna sudah login, ada satu produk di keranjang, dan berada di halaman data checkout (Checkout: Your Information).

| ID | Title | Steps | Test Data | Expected Result | Actual Result | Status |
|---|---|---|---|---|---|---|
| TC-CHECKOUT-001 | Checkout dengan data valid | 1. Isi First Name 2. Isi Last Name 3. Isi Postal Code 4. Klik Continue | First Name: lula, Last Name: hehe, Postal Code: 12345 | Pengguna berpindah ke halaman Checkout: Overview yang menampilkan produk dan total harga | Pengguna berhasil ke halaman Overview yang menampilkan payment information, shipping information, dan price total | Pass |

| TC-CHECKOUT-002 | Checkout ditolak saat First Name kosong | 1. Kosongkan First Name 2. Isi Last Name 3. Isi Postal Code 4. Klik Continue | First Name: (kosong), Last Name: hehe, Postal Code: 12345 | Pengguna tetap di halaman data checkout dan muncul pesan error bahwa First Name wajib diisi | Pengguna tetap di halaman data checkout. Muncul pesan "Error: First Name is required" | Pass |

| TC-CHECKOUT-003 | Checkout ditolak saat Last Name kosong | 1. Isi First Name 2. Kosongkan Last Name 3. Isi Postal Code 4. Klik Continue | First Name: lula, Last Name: (kosong), Postal Code: 12345 | Pengguna tetap di halaman data checkout dan muncul pesan error bahwa Last Name wajib diisi | Pengguna tetap di halaman data checkout. Muncul pesan "Error: Last Name is required" | Pass |

| TC-CHECKOUT-004 | Checkout ditolak saat Postal Code kosong | 1. Isi First Name 2. Isi Last Name 3. Kosongkan Postal Code 4. Klik Continue | First Name: lula, Last Name: hehe, Postal Code: (kosong) | Pengguna tetap di halaman data checkout dan muncul pesan error bahwa Postal Code wajib diisi | Error: Postal Code is required | Pass |

| TC-CHECKOUT-005 | Postal Code berisi huruf dan simbol | 1. Isi First Name 2. Isi Last Name 3. Isi Postal Code dengan huruf dan simbol 4. Klik Continue | First Name: lula, Last Name: hehe, Postal Code: abc!@# | Ditolak dengan pesan error (menurut requirement, perlu dikonfirmasi ke Product Owner) | Diterima tanpa pesan error, pengguna lanjut ke halaman Overview | Fail (calon bug, lihat bug report) |

| TC-CHECKOUT-006 | Checkout ditolak saat First Name dan Last Name kosong | 1. Kosongkan First Name 2. Kosongkan Last Name 3. Isi Postal Code 4. Klik Continue | First Name: (kosong), Last Name: (kosong), Postal Code: 12345 | Pengguna tetap di halaman data checkout dan muncul pesan error | Pengguna tetap di halaman data checkout. Hanya muncul "Error: First Name is required" | Pass |

| TC-CHECKOUT-007 | Membatalkan checkout | 1. Klik tombol Cancel di halaman data checkout | (tidak ada) | Pengguna kembali ke halaman keranjang dan produk masih ada | pengguna kembali ke halaman your card yang menampilkan list product di keranjang | (Pass/Fail) |
