# Glosarium QA 
FASE 1: 
BAGIAN A:Fundamental Quality Assurance

QA (Quality Assurance) proses untuk memastikan kualitas sebuah produk atau aplikasi sesuai standard yang bersifat mencegah (preventive)

QC (Quality Control) adalah proses untuk memastikan kualitas sebuah produk atau aplikasi apakah sudah sesuai dengan standard yang bersifat mendeteksi

Bug/Defect adalah  fungsi aplikasi yang tidak sesuai dengan kebutuhan pengguna yang sudah ditentukan sebelumnya

Requirement adalah kebutuhan yang disepakati tentang apa yang wajib dibuat pada aplikasi

BAGIAN B: SDLC dan STLC

SDLC (Software Development Life Cycle) adalah proses pembuatan aplikasi. 
Tahapan SDLC:
- Requirement (mengumpulkan kebutuhan kebutuhan pengguna)
- Design (desain tampilan aplikasi & struktur database)
- Development (developer membangun aplikasi sesuai dengan kebutuhan kebutuhan yang disepakati pada tahap requirement)
- Testing (qa menguji aplikasi apakah sudah sesuai dengan kebutuhan yang disepakati, jika terdapat bug maka akan melaporkan ke developer dan akan menguji ulang jika sudah diperbaiki)
- Deployment (Aplikasi diliris ke pengguna)
- Maintenance (memperbaiki bug dan menambah fitur baru sesuai kebutuhan pengguna)

STLC (Software Testing Life Cycle) adalah proses khusus yang dilakukan oleh QA pada tahapan pengujian
Tahapan STLC:
- Requirement Analys (mempelajari hasil requirement)
- Test Planning (merencanakan apa yang akan diuji dan akan menggunakan tools apa)
- Test Case Deevelopment (membuat skenario dan langkah pengujian)
- Test Environment Setup(menyiapkan lingkungan pengujian)
- Test Execution (menjalankan tes case, mencatata hasil dan melaporkan bug)
- Test Closure (menutup pengujian dan merangkum hasil pengujian)

BAGIAN C: Agile, Scrum, dan Peran QA di Tim

Shift-left adalah melakukan pengujian pada tahap awal agar meminimalisir biaya perbaikan

Sprint adalah siklus kerja pendek  di Scrum biasanya dalam 1-4 minggu

User Story adalah kebutuhan dari sudut pandang pengguna dalam bentuk kalimat

Acceptance Criteria adalah syarat terukur agar sebuah user story dianggap selesai

FASE 2:
BAGIAN A: Functional vs Non-Functional, Black Box vs White Box

Functional Testing adalah menguji fitur suatu aplikasi apakah bekerja sesuai fungsi

Non-functional Testing adalah menguji seberapa baik suatu aplikasi bekerja (kecepatan, keamanan, kenyamanan)

Black-box Testing adalah menguji aplikasi tanpa melihat kode seperti menguji fitur suatu aplikasi

White-box Testing adalah menguji aplikasi dengan melihat struktur kode yang biasanya dilakukan oleh developer


BAGIAN B: Positive, Negative, Smoke, Sanity, Regression, Retesting

Positive Testing adalah pengujian dengan input data yang valid

Negative Testing adalah pengujian dengan input data yang tidak valid

Smoke Testing adalah pengujian cepat fungsi inti dari aplikasi saat build baru diterima 

Sanity Testing adalah pengecekan cepat bagian yang diperbaiki

Retesting adalah menguji ulang bug yang sama setelah diperbaiki

Regression Testing adalah memastikan fitur lama tidak rusak ketika adanya perubahan atau penambahan fitur baru

BAGIAN C: Integration, System, UAT, Severity vs Priority

Integration Testing adalah menguji gabungan beberapa aplikasi 

System Testing adalah menguji keseluruhan bagian dari aplikasi

UAT (User Acceptance Testing) adalah pengujian oleh pengguna/ klien untuk menerima palikasi atau produk

Severity adalah tingkat keparahan dampak bug terhadap aplikasi

Priority adalah urutan kecepatan perbaikan bug

Exploratory Testing adalah menjelajah aplikasi dengan rasa ingin tahu untuk mencari perilaku tak terduga

## Fase 3: Test Documentation

**Test Plan** adalah dokumen perencanaan pengujian: apa yang diuji, siapa, kapan, dan dengan tools apa.

**Test Scenario** adalah gambaran singkat satu kalimat tentang apa yang diuji. 
Contoh: "Pengguna bisa checkout dengan data valid."

**Test Case** adalah langkah detail beserta hasil yang diharapkan untuk satu tujuan pengujian. 

Komponen test case:
- **ID**: nomor unik, contoh TC-CHECKOUT-001.
- **Title**: judul singkat yang sesuai isi.
- **Precondition**: kondisi yang harus terpenuhi sebelum mulai.
- **Steps**: langkah berurutan yang bisa diikuti orang lain.
- **Test Data**: data yang dipakai (gunakan data fiktif).
- **Expected Result**: hasil yang seharusnya, spesifik dan bisa dijawab lulus atau gagal.
- **Actual Result**: hasil sebenarnya saat dijalankan.
- **Status**: Pass, Fail, Blocked, atau Not Executed.

**Ciri test case yang baik:** satu tujuan per test case, langkah jelas, expected result spesifik, data tertulis eksplisit.

**Pass vs Fail:** Pass jika actual sama dengan expected. Fail jika berbeda. Aplikasi yang menolak input salah dengan benar berarti Pass, bukan Fail. 

**Blocked** adalah test case yang tidak bisa dijalankan karena ada hambatan, misalnya situs sedang down. Berbeda dengan Fail, yang sudah dijalankan tetapi hasilnya salah. 

**Equivalence Partitioning (EP)** membagi input menjadi kelompok yang berperilaku sama, lalu menguji satu wakil dari tiap kelompok. 
Contoh: jumlah barang 1-10, kelompok: kurang dari 1 (wakil 0), 1-10 (wakil 8), lebih dari 10 (wakil 15).

**Boundary Value Analysis (BVA)** menguji nilai tepat di batas dan di sekitarnya, karena bug sering muncul di sana (misalnya `<` tertukar dengan `<=`). 
Contoh batas 1-10: uji 0, 1, 2, 9, 10, 11.

**Decision Table** adalah tabel kombinasi beberapa kondisi beserta hasilnya, dipakai saat hasil bergantung pada kombinasi kondisi. 
Temuan saya: pada checkout saucedemo, jika First Name dan Last Name sama-sama kosong, hanya pesan "First Name is required" yang muncul.

**Test Data** adalah data masukan pengujian: valid, invalid, kosong, batas, dan karakter khusus.

**Test Execution** adalah menjalankan test case persis sesuai langkah dan mencatat hasil sebenarnya.

**Test Summary Report** adalah laporan ringkas hasil pengujian: ruang lingkup, lingkungan, jumlah Pass/Fail/Blocked, pass rate, daftar bug, dan kesimpulan layak rilis atau tidak.

**Pass rate** = jumlah Pass dibagi total test case. Contoh: 6 dari 8 = 75%.

**Evidence** adalah bukti pengujian (screenshot atau rekaman), wajib untuk hasil Fail.

## Tambahan: Bug Report dan API

**Bug Lifecycle:** New -> Open -> In Progress -> Fixed -> Retest -> Closed (atau Reopened jika masih bermasalah).

**Reproducible** artinya bug bisa diulang dengan langkah yang sama. Bug yang tidak bisa direproduksi belum layak dilaporkan.

**API** adalah penghubung antar aplikasi. 

**HTTP Method:** GET (ambil data), POST (buat data), PUT/PATCH (ubah data), DELETE (hapus data).

**Status Code:** 2xx sukses (200, 201), 4xx salah di sisi klien (400, 401, 404), 5xx salah di sisi server (500).

**Assertion** adalah baris pemeriksa yang membandingkan actual dengan expected, contoh `pm.response.to.have.status(404)`.


## Fase 7: Database Testing (SQL), Bagian A

**Database Testing** adalah memeriksa apakah data di database sama dengan yang ditampilkan atau dikirim aplikasi. 

**SELECT** membaca data dari tabel. Contoh: `SELECT * FROM users;`

**WHERE** menyaring baris sesuai syarat. Contoh: `WHERE id = 1`.

**INSERT** menambah baris baru. **UPDATE** mengubah data. **DELETE** menghapus data. 

**Peringatan:** UPDATE dan DELETE tanpa WHERE mengenai seluruh baris. Selalu pakai WHERE dan jalankan hanya di database pengujian.

**JOIN** menggabungkan dua tabel lewat kolom yang berhubungan, misalnya `orders.user_id = users.id`. 

**NULL** artinya nilai kosong (belum ada isinya), berbeda dengan angka 0 atau teks kosong. Mencarinya memakai `IS NULL`, bukan `= NULL`.

**NULL** artinya "tidak ada nilai". Mencarinya memakai `IS NULL`, bukan `= NULL`, karena `=` hanya bisa membandingkan dua nilai. 

**Query yang salah tidak selalu error.** `WHERE email = NULL` berjalan tanpa pesan error, tapi hasilnya kosong dan menyesatkan. Hasil query harus selalu diperiksa, tidak hanya pesan errornya.

**Error #1054 Unknown column** artinya nama kolom yang ditulis tidak ada di tabel. Penyebab umum: salah ketik atau menyalin tempat kosong dari contoh. Perbaikannya: periksa nama kolom di struktur tabel.

**Mengapa QA memeriksa database:** tampilan bisa terlihat benar padahal data tersimpan salah atau tidak valid. 
Contoh: kode pos `abc!@#` diterima saat checkout, sehingga data pengiriman yang tersimpan bisa tidak valid.

## Fase 7: Database Testing (SQL), Bagian B

**AUTO_INCREMENT** membuat database mengisi id secara otomatis dan unik, sehingga id tidak perlu ditulis saat INSERT. 

**Kebiasaan QA setelah INSERT:** selalu buktikan dengan SELECT bahwa data benar-benar masuk.

**UPDATE** mengubah data yang sudah ada. Selalu pakai WHERE, lebih baik dengan id yang unik. Setelah UPDATE, periksa bahwa baris yang dituju berubah **dan baris lain tidak ikut berubah**. 

**DELETE** menghapus data dan tidak bisa dibatalkan. Kebiasaan aman: SELECT dulu dengan syarat yang sama, lalu DELETE, lalu SELECT lagi. 

**Primary Key** adalah kolom yang nilainya unik untuk setiap baris, contohnya `id`.

**Foreign Key** adalah kolom yang menunjuk ke primary key tabel lain. Contoh: `orders.user_id` menunjuk ke `users.id`.

**JOIN** menggabungkan data dari beberapa tabel lewat kolom yang berhubungan. Data hanya dibaca, tidak diubah. 

**INNER JOIN** hanya menampilkan baris yang punya pasangan di kedua tabel. Pengguna tanpa pesanan tidak akan muncul.

**Data tidak konsisten** terjadi saat data di satu tabel menunjuk ke data yang tidak ada, misalnya pesanan dengan `user_id` milik pengguna yang sudah dihapus. JOIN membantu menemukannya. 