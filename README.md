# ERPNext Progress

Repository ini berisi progress pembelajaran dan implementasi ERPNext yang telah saya kerjakan selama proses magang.

---

## 📌 Chapter 1 - Accounting

### Tujuan
Mempelajari dasar penggunaan ERPNext pada modul Accounting, mulai dari pembuatan perusahaan, penyusunan *Chart of Accounts*, pencatatan transaksi menggunakan *Journal Entry*, hingga melihat laporan keuangan.

### Materi yang Dipelajari

#### 1. ERPNext
ERPNext adalah software *Enterprise Resource Planning* (ERP) yang digunakan untuk membantu perusahaan mengelola seluruh proses bisnis dalam satu sistem terintegrasi, seperti:
* Pembelian (*Buying*)
* Penjualan (*Selling*)
* Persediaan (*Stock*)
* Keuangan (*Accounting*)

#### 2. Membuat Company
Membuat perusahaan dengan nama: **PT. Testing ERP**

#### 3. Chart of Accounts (COA)
*Chart of Accounts* merupakan daftar seluruh akun akuntansi yang digunakan perusahaan untuk mencatat transaksi. Kategori akun yang dipelajari meliputi: **Asset, Liability, Equity, Expense, dan Income**.
* **Contoh akun yang dibuat:** `HSBC` (Asset - Bank), `John` (Equity), `Mary` (Equity).
> **Catatan:** Semua transaksi akuntansi wajib menggunakan akun-akun yang terdaftar pada Chart of Accounts.

#### 4. Bank Account
Membuat rekening perusahaan menggunakan akun `HSBC`. Bank Account ini digunakan sebagai rekening resmi perusahaan untuk menerima maupun melakukan pembayaran.

#### 5. Journal Entry
*Journal Entry* digunakan untuk mencatat seluruh transaksi akuntansi ke dalam sistem ERPNext. 
* **Contoh transaksi:** Menyetor modal investor dan mencatat biaya sewa kantor.
* Pencatatan menggunakan prinsip **Double Entry**: $\text{Total Debit} = \text{Total Kredit}$.

### Laporan Keuangan yang Dipelajari
* **Trial Balance:** Digunakan untuk memastikan keseimbangan pencatatan akuntansi (Menampilkan semua akun, Total Debit, dan Total Kredit).
* **Balance Sheet:** Digunakan untuk melihat posisi keuangan perusahaan (Menampilkan Asset, Liability, dan Equity).
* **Profit & Loss:** Digunakan untuk melihat laba atau rugi perusahaan (Menampilkan Income dan Expense).
* **General Ledger:** Kumpulan seluruh transaksi jurnal yang telah dicatat (Menampilkan tanggal transaksi, akun, debit, kredit, dan saldo).

### 💡 Catatan Penting
* `John` dan `Mary` merupakan akun **Equity (Modal)** karena berperan sebagai investor yang menyetor modal awal.
* `HSBC` termasuk akun **Asset**, karena merupakan rekening bank yang menyimpan aset perusahaan.
* Aturan saldo normal akun Asset:
  * Asset bertambah $\rightarrow$ **Debit**
  * Asset berkurang $\rightarrow$ **Kredit**

### Hasil Pembelajaran
Pada Chapter 1 ini, saya telah berhasil mempraktikkan: pembuatan Company, pemahaman COA, pembuatan akun Shareholder & Bank Account, pencatatan Journal Entry, hingga analisis laporan keuangan (*Trial Balance, Balance Sheet, Profit & Loss,* dan *General Ledger*).

---

## 📌 Chapter 2 - Buying

### Tujuan
Mempelajari alur pembelian (*Buying Cycle*) pada ERPNext, mulai dari membuat *Purchase Order* hingga barang diterima dan transaksi tercatat pada laporan keuangan.

### Alur Buying
$$\text{Purchase Order (PO)} \rightarrow \text{Purchase Invoice (PI)} \rightarrow \text{Payment Entry} \rightarrow \text{Purchase Receipt} \rightarrow \text{Laporan Keuangan}$$

### Materi yang Dipelajari

#### 1. Purchase Order (PO)
Dokumen pemesanan barang yang dikirim perusahaan kepada supplier. Langkahnya meliputi pembuatan data Supplier, membuat PO, dan menentukan barang yang akan dipesan.

#### 2. Purchase Invoice (PI)
Tagihan dari supplier kepada perusahaan atas barang yang telah dipesan.
* Data PI dapat ditarik otomatis dari PO menggunakan fitur **Get Items From**.
* Setelah PI dibuat, akan muncul akun sementara: `Stock Received But Not Billed`.
* **Artinya:** Barang sudah diterima, namun invoice masih berstatus *Unpaid* (belum dibayar).

#### 3. Payment Entry
Digunakan untuk melunasi tagihan kepada supplier. Data yang diisi meliputi: *Payment Type, Party Type, Mode of Payment, Bank,* dan *Reference*. Setelah disubmit, status *Purchase Invoice* berubah dari **Unpaid $\rightarrow$ Paid**.

#### 4. Purchase Receipt
Dokumen bukti bahwa barang telah diterima fisik oleh perusahaan. Akibatnya:
* Barang masuk ke Warehouse dan quantity stok bertambah (Persediaan bertambah).
* Status akun berubah dari: `Stock Received But Not Billed` $\rightarrow$ `Stock In Hand` (Persediaan resmi menjadi aset perusahaan).

### Pengaruh terhadap Laporan Keuangan
Pada **Balance Sheet** terjadi penyesuaian aset: Uang perusahaan berkurang (akibat kas keluar pada *Payment Entry*), namun persediaan barang bertambah sebagai aset baru (*Stock In Hand*).

### Hasil Pembelajaran
Menguasai siklus *end-to-end* proses pembelian pada ERPNext (PO $\rightarrow$ PI $\rightarrow$ Payment $\rightarrow$ Receipt) serta memahami bagaimana transaksi tersebut otomatis memperbarui *General Ledger, Trial Balance, Balance Sheet,* dan *Profit & Loss*.

---

## 📌 Chapter 3 - Selling

### Tujuan
Mempelajari alur penjualan (*Selling Cycle*) pada ERPNext, mulai dari pembuatan Customer, penawaran harga (*Quotation*), pembuatan *Sales Order*, *Sales Invoice*, penerimaan pembayaran, pengiriman barang, hingga analisis pengaruhnya ke laporan keuangan.

### Alur Selling
$$\text{Customer} \rightarrow \text{Quotation} \rightarrow \text{Sales Order} \rightarrow \text{Sales Invoice} \rightarrow \text{Payment Entry} \rightarrow \text{Delivery Note} \rightarrow \text{Review Laporan}$$

### Materi yang Dipelajari

#### 1. Customer & Quotation
* **Customer:** Membuat dan menyimpan data pihak yang akan membeli barang.
* **Quotation:** Membuat dokumen penawaran harga dan barang yang ditawarkan ke customer.

#### 2. Sales Order (SO) & Sales Invoice (SI)
* **Sales Order:** Mencatat pesanan resmi dari customer (dibuat langsung dari data *Quotation* agar efisien).
* **Sales Invoice:** Dokumen tagihan resmi kepada customer. Transaksi ini mencatat jurnal akuntansi:
  * **Debit:** Piutang Customer (e.g., Rp15.000.000)
  * **Kredit:** Penjualan (e.g., Rp15.000.000)

#### 3. Payment Entry & Delivery Note
* **Payment Entry:** Menerima pembayaran menggunakan tipe *Receive*. Mengubah status SI dari **Unpaid $\rightarrow$ Paid**.
* **Delivery Note:** Mencatat proses pengiriman fisik barang. Setelah disubmit, stok di gudang akan berkurang dan nilai persediaan akan diakui sebagai Harga Pokok Penjualan (HPP).

### Simulasi Hasil Laporan Keuangan
* **Profit & Loss:** 
  * Pendapatan: Rp15.000.000
  * HPP: Rp10.000.000
  * Biaya Lain (Sewa): Rp500.000
  * **Net Profit: Rp4.500.000**
* **Trial Balance:** Total Debit & Kredit seimbang di Rp25.500.000.
* **Balance Sheet:** Menampilkan akumulasi Profit sebesar Rp4.500.000.

### Hasil Pembelajaran
Memahami siklus penjualan lengkap di ERPNext beserta dampaknya pada pengurangan stok di *Stock Ledger* serta pengakuan pendapatan dan HPP di laporan *Profit & Loss*.

---

## 📌 Chapter 4 - Cost Center & Project

### Tujuan
Mempelajari penggunaan **Cost Center** dan **Project** pada ERPNext untuk mengelompokkan transaksi sehingga pendapatan dan biaya dapat dipantau secara spesifik per divisi maupun per proyek.

### Konsep Dasar
* **Cost Center:** Mengelompokkan transaksi berdasarkan divisi/bagian internal perusahaan (Contoh: `Sales1 - PTE`).
* **Project:** Mengelompokkan transaksi berdasarkan proyek tertentu eksternal/internal (Contoh: `Project2`).

### Alur Implementasi
$$\text{Setup Cost Center \& Project} \rightarrow \text{Buying Cycle (Tagging Project \& CC)} \rightarrow \text{Selling Cycle (Tagging Project \& CC)} \rightarrow \text{Filter Laporan Keuangan}$$

### Detail Pengujian (Buying & Selling)
1. **Saat Pemelian (Buying):** Pada *Purchase Order*, *Purchase Receipt*, dan *Purchase Invoice*, kolom *Accounting* wajib di-tag ke Cost Center: `Sales1 - PTE` dan Project: `Project2`.
2. **Saat Penjualan (Selling):** Pada *Sales Order*, *Delivery Note*, dan *Sales Invoice*, filter yang sama diterapkan agar biaya HPP dan Pendapatan masuk ke kantong yang sama.

### Review Laporan Keuangan
Setelah seluruh transaksi selesai, laporan keuangan (*Profit & Loss* / *Balance Sheet*) difilter berdasarkan Cost Center: `Sales1 - PTE` dan Project: `Project2`. Hasilnya, nilai transaksi (sebesar Rp3.000.000) berhasil terisolasi dan terdokumentasi khusus untuk divisi & proyek tersebut.

---

## 📌 Chapter 5 - Letter Head & Custom Print Format

### Tujuan
Mempelajari cara mengatur dan menyesuaikan tampilan cetak dokumen pada ERPNext menggunakan **Letter Head** dan **Custom Print Format** agar sesuai dengan identitas resmi perusahaan.

### Komponen Utama

#### 1. Letter Head & HTML Footer
* Membuat Letter Head bernama `PT Testing ERP Letter Head` yang berisi logo dan info resmi perusahaan.
* Membuat *Footer* kustom menggunakan kode HTML untuk menampilkan nama, alamat, email, dan nomor telepon agar tata letak teks, warna, dan ukuran lebih rapi.

#### 2. Custom Print Format
Membuat format cetak baru bernama `Custom Sales Invoice` untuk DocType `Sales Invoice` pada modul *Accounts* tanpa merusak template bawaan ERPNext.

#### 3. Modifikasi Tampilan Dokumen
* Mengubah judul (*Heading*) dokumen dari **Sales Invoice** menjadi **Customer Invoice**.
* Menyederhanakan tampilan dengan menghapus field tidak penting dan mempertahankan field krusial (*Customer Name, Dates, Cost Center, Items, Totals, In Words*).

### Hasil Akhir
Saat melakukan *Print Preview* pada Sales Invoice dengan memilih format kustom, perubahan berhasil diterapkan secara penuh: Judul telah berubah, *field* menjadi ringkas, serta *Letter Head* dan *HTML Footer* muncul dengan presisi.

---

## 📌 Chapter 6 - Purchase Cycle

### Tujuan
Mempelajari alur lengkap (*end-to-end*) proses pembelian barang dagang di ERPNext, mulai dari pembuatan master *Item* baru hingga pengecekan jurnal di laporan keuangan.

### Alur Detail
$$\text{Create Item} \rightarrow \text{Purchase Order} \rightarrow \text{Purchase Receipt} \rightarrow \text{Check Stock Ledger} \rightarrow \text{Purchase Invoice} \rightarrow \text{Payment Entry} \rightarrow \text{Check General Ledger}$$

### Studi Kasus Pengujian
* **Supplier:** Supplier1
* **Item:** `ITEM02` (Pensil) | **Group:** Products
* **Kuantitas:** 10 unit | **Harga:** Rp10.000 / unit
* **Total Transaksi:** Rp100.000

### Hasil Pengujian
* **Stock Ledger:** Valid, kuantitas `ITEM02` terbukti bertambah 10 unit di gudang `Stores - PTE` sesaat setelah *Purchase Receipt* di-submit.
* **General Ledger:** Valid, mencatat mutasi keuangan secara tepat untuk akrual penerimaan barang (*Purchase Receipt*), pengakuan utang (*Purchase Invoice*), dan pelunasan kas (*Payment Entry*).

---

## 📌 Chapter 7 - Batch Management

### Tujuan
Mempelajari penggunaan fitur *Batch Management* pada ERPNext untuk mencatat dan melacak pergerakan stok barang berdasarkan nomor batch (sangat penting untuk produk dengan tanggal kedaluwarsa seperti obat/makanan).

### Alur Pengujian
1. **Master Item:** Membuat item `ITEM03` (Panadol Extra), mengaktifkan opsi **Has Batch No** dan **Maintain Stock**.
2. **Batch Creation:** Membuat nomor batch baru `BATCH-ITEM03-001`.
3. **Inbound Transaksi:** Memproses *Purchase Receipt* $\rightarrow$ *Purchase Invoice* $\rightarrow$ *Payment Entry* dengan memasukkan nomor batch yang telah dibuat ke gudang `Stores - PTE`.
4. **Outbound Transaksi:** Memproses penjualan menggunakan *Delivery Note* dan *Sales Invoice* dengan mengambil stok dari batch yang sama.

### Hasil Pembelajaran
Stok barang sukses ter-filter dan terlacak secara spesifik berdasarkan nomor batch pada *Stock Ledger*, memudahkan pelacakan jika sewaktu-waktu dibutuhkan *product recall* atau pengecekan *expiry date*.

---

## 📌 Chapter 8 - POS Profile

### Tujuan
Mempelajari proses transaksi penjualan ritel/langsung menggunakan fitur **Point of Sale (POS)** di ERPNext, mirip dengan sistem kasir minimarket atau apotek.

### Langkah Kerja & Hasil Pengujian
* **POS Profile Setup:** Mengonfigurasi kasir dengan gudang `Stores - PTE`, user `Administrator`, daftar harga *Standard*, dan metode pembayaran *Cash*.
* **POS Opening Entry:** Membuka sesi kasir dengan modal awal (*Opening Amount*) sebesar **Rp1.000.000**.
* **Transaksi POS:** Menjual `Panadol` sebanyak 3 unit secara tunai. Sistem otomatis menghasilkan *POS Invoice* dengan status langsung **Paid**.
* **POS Closing Entry & Rekonsiliasi:** Menutup sesi kasir di akhir hari.
  * *Opening Amount:* Rp1.000.000
  * *Penjualan POS:* Rp45.000
  * *Expected Closing Amount:* Rp1.045.000
  * *Difference:* **Rp0** (Tidak ada selisih kas / Valid).

---

## 📌 Chapter 9 - Batch Number pada POS

### Tujuan
Mempelajari integrasi dan penggunaan *Batch Number* barang saat melakukan transaksi di modul kasir *Point of Sale* (POS).

### Alur & Keterbatasan Sistem
Proses pengujian dilakukan dengan membuat batch kedua, menerima stok via *Purchase Receipt*, lalu melakukan transaksi retail via POS hingga *Closing Entry* dengan hasil rekonsiliasi kas yang sesuai (selisih Rp0).

> ⚠️ **Catatan Penting (Constraint):** ERPNext memiliki keterbatasan bawaan pada scanner barcode batch karena belum bisa otomatis memisahkan nomor batch hanya dari barcode produk standar.
> * **Solusi:** Perlu dilakukan kustomisasi barcode yang menggabungkan informasi kode *Item* dan *Batch Number* sekaligus.

---

## 📌 Chapter 10 - Users, Roles & Permission

### Tujuan
Mempelajari pengelolaan keamanan sistem ERPNext melalui pembatasan akses pengguna berdasarkan konsep *User*, *Role*, dan *Permission*.

### Konsep Dasar
* **User:** Akun login pengguna (e.g., Tony - `Tony@Testing.com`).
* **Role:** Jabatan/fungsi kerja di sistem (e.g., `Sales User`).
* **Permission:** Hak aksi yang melekat pada Role untuk menjaga kerahasiaan data perusahaan.

### Hasil Pengujian Akses
* **Hak Akses Sukses:** User Tony dengan role `Sales User` sukses membuka, membuat, mengedit, dan menyimpan dokumen di menu `Selling -> Quotation`.
* **Pembatasan Sukses:** Saat Tony mencoba mengakses *User List* milik Administrator, sistem menolak dan menampilkan pesan error **"Not Permitted"**.

---

## 📌 Chapter 11 - Role Permission Manager

### Tujuan
Mempelajari pengaturan hak akses dokumen secara lebih granular/rinci (Read, Write, Create, Delete, Submit, Cancel, Amend, Print) menggunakan fitur **Role Permission Manager**.

### Kasus Pengujian
Mengonfigurasi Role `Sales User` (akun Tony) agar memiliki hak untuk **Read, Write, dan Create**, namun mematikan hak untuk melakukan **Delete, Submit, Cancel, dan Amend** pada dokumen *Quotation*.

### Hasil Pengujian
Sistem berjalan sesuai aturan: Akun Tony tetap bisa membuat dan merevisi draf *Quotation*, tetapi tombol untuk *Submit* (Posting resmi) maupun opsi untuk *Delete* hilang/dihalang oleh sistem. Hal ini memastikan proses approval tetap berada di level supervisor.

---

## 📌 Chapter 12 - Manufacturing Module

### Tujuan
Mempelajari proses produksi manufaktur pada ERPNext, mulai dari perakitan bahan baku hingga menghasilkan produk jadi (*Finished Goods*).

### Alur Kerja Manufaktur
1. **BOM (Bill of Materials):** Membuat resep formula produk jadi. Contoh: Produk `FG - Plumcake` membutuhkan bahan baku Tepung (5 kg), Gula (2 kg), dan Telur (20 butir).
2. **Work Order (WO):** Dokumen perintah resmi untuk memulai proses produksi berdasarkan BOM.
3. **Stock Reconciliation:** Menyiapkan dan memasukkan saldo stok awal bahan baku.
   > **Insight:** Jika *valuation rate* bahan baku kosong, sistem akan memicu error *Valuation Missing*.
4. **Material Transfer for Manufacture:** Memindahkan bahan baku fisik dari gudang utama menuju gudang *Work In Progress* (WIP).
5. **Job Card:** Menjalankan instruksi kerja per tahapan (*Mixing $\rightarrow$ Cooking $\rightarrow$ Packing*). Tahapan: *Start Job $\rightarrow$ Complete Job $\rightarrow$ Submit*.
6. **Finished Goods:** Setelah seluruh *Job Card* disubmit, sistem otomatis mengurangi stok bahan baku di WIP dan menerbitkan stok produk jadi (`FG - Plumcake`) di gudang akhir.

---

## 📌 Chapter 16 - Invoice Payment Reconciliation

### Tujuan
Mempelajari pencatatan pembayaran cicilan/bertahap pada invoice serta proses rekonsiliasi data pembayaran yang belum teralokasi di ERPNext.

### Langkah Pengujian Pembayaran Bertahap
* Membuat *Sales Invoice* dengan total nilai **Rp500.000** (Status awal: *Unpaid*).
* **Pembayaran 1 (Sebagian):** Melakukan *Payment Entry* senilai **Rp200.000**. Status invoice otomatis berubah menjadi **Partly Paid** dengan sisa tagihan Rp300.000.
* **Pembayaran 2 (Pelunasan):** Melakukan *Payment Entry* kedua senilai **Rp300.000**. Status invoice berubah menjadi **Paid**.

### Fitur Payment Reconciliation
Modul ini digunakan secara khusus untuk menjodohkan dokumen pembayaran masuk (*unallocated payment*) dengan dokumen piutang *Sales Invoice* yang menggantung secara manual apabila kasir menerima uang terlebih dahulu sebelum invoice diterbitkan.
```text
Bedakan:
- Payment Entry        : Untuk mencatat mutasi uang masuk/keluar secara langsung atas invoice.
- Payment Reconciliation: Menghubungkan kas gantung agar bersih (clearing) dengan invoice yang tepat.
