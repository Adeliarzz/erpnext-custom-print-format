# ERPNext Internship Learning Documentation

Repository ini berisi dokumentasi proses pembelajaran dan implementasi ERPNext selama kegiatan magang menggunakan ERPNext.

## Daftar Isi

- Chapter 1 - Accounting
- Chapter 2 - Buying
- Chapter 3 - Selling
- Chapter 4 - Cost Center & Project
- Chapter 5 - Letter Head & Custom Print Format
- Chapter 6 - Purchase Cycle
- Chapter 7 - Batch Management
- Chapter 8 - POS Profile
- Chapter 9 - Batch Number pada POS
- Chapter 10 - Users, Roles & Permission
- Chapter 11 - Role Permission Manager
- Chapter 12 - Manufacturing Module
- Chapter 16 - Invoice Payment Reconciliation

---

# Chapter 1 - Accounting

## Tujuan
Mempelajari dasar penggunaan ERPNext pada modul Accounting, mulai dari pembuatan perusahaan, penyusunan Chart of Accounts, pencatatan transaksi menggunakan Journal Entry, hingga melihat laporan keuangan.

---

## Materi yang Dipelajari

### 1. ERPNext
ERPNext adalah software Enterprise Resource Planning (ERP) yang digunakan untuk membantu perusahaan mengelola seluruh proses bisnis dalam satu sistem terintegrasi, seperti:
- Pembelian (Buying)
- Penjualan (Selling)
- Persediaan (Stock)
- Keuangan (Accounting)

---

### 2. Membuat Company
Membuat perusahaan dengan nama:

- **PT. Testing ERP**

---

### 3. Chart of Accounts (COA)

Chart of Accounts merupakan daftar seluruh akun akuntansi yang digunakan perusahaan untuk mencatat transaksi.

Kategori akun yang dipelajari:

- Asset
- Liability
- Equity
- Expense
- Income

Contoh akun yang dibuat:

- HSBC (Asset - Bank)
- John (Equity)
- Mary (Equity)

Semua transaksi akuntansi menggunakan akun-akun yang terdapat pada Chart of Accounts.

---

### 4. Bank Account

Membuat rekening perusahaan menggunakan akun:

- HSBC

Bank Account digunakan sebagai rekening perusahaan untuk menerima maupun melakukan pembayaran.

---

### 5. Journal Entry

Journal Entry digunakan untuk mencatat seluruh transaksi akuntansi ke dalam sistem ERPNext.

Contoh transaksi yang dilakukan:

- Menyetor modal investor
- Mencatat biaya sewa kantor

Pencatatan menggunakan prinsip **Double Entry**, yaitu:

- Total Debit = Total Kredit

---

## Laporan Keuangan

### Trial Balance

Digunakan untuk memastikan keseimbangan pencatatan akuntansi.

Menampilkan:

- Semua akun
- Total Debit
- Total Kredit

---

### Balance Sheet

Digunakan untuk melihat posisi keuangan perusahaan.

Menampilkan:

- Asset
- Liability
- Equity

---

### Profit & Loss

Digunakan untuk melihat laba atau rugi perusahaan.

Menampilkan:

- Income
- Expense

---

### General Ledger

General Ledger merupakan kumpulan seluruh transaksi jurnal yang telah dicatat.

Informasi yang ditampilkan:

- Tanggal transaksi
- Akun
- Debit
- Kredit
- Saldo

---

## Catatan

- John dan Mary merupakan akun **Equity (Modal)** karena berperan sebagai investor yang memberikan modal kepada perusahaan.
- HSBC termasuk akun **Asset**, karena merupakan rekening bank yang menyimpan aset perusahaan.
- Pada akun Asset berlaku aturan:
  - Asset bertambah → Debit
  - Asset berkurang → Kredit

---

## Hasil Pembelajaran

Pada Chapter 1 telah mempelajari:

- Membuat Company
- Memahami Chart of Accounts (COA)
- Membuat akun Shareholder (John dan Mary)
- Membuat Bank Account (HSBC)
- Mencatat transaksi menggunakan Journal Entry
- Melihat laporan Trial Balance
- Melihat laporan Balance Sheet
- Melihat laporan Profit & Loss
- Melihat laporan General Ledger


---

# Chapter 2 - Buying

## Tujuan
Mempelajari alur pembelian (Buying Cycle) pada ERPNext, mulai dari membuat Purchase Order hingga barang diterima dan transaksi tercatat pada laporan keuangan.

---

## Alur Buying

Purchase Order (PO)
↓
Purchase Invoice (PI)
↓
Payment Entry
↓
Purchase Receipt
↓
Laporan Keuangan

---

## Materi yang Dipelajari

### 1. Purchase Order (PO)

Purchase Order merupakan dokumen pemesanan barang yang dikirim perusahaan kepada supplier.

Yang dilakukan:

- Membuat Supplier.
- Membuat Purchase Order (PO).
- Menentukan barang yang akan dipesan.

---

### 2. Purchase Invoice (PI)

Purchase Invoice merupakan tagihan dari supplier kepada perusahaan atas barang yang telah dipesan.

Yang dipelajari:

- Data Purchase Invoice dapat diambil dari Purchase Order menggunakan **Get Items From**.
- Setelah Purchase Invoice dibuat, akan muncul akun sementara:

```
Stock Received But Not Billed
```

Artinya:

- Barang sudah diterima.
- Invoice masih berstatus **Unpaid**.
- Perusahaan belum melakukan pembayaran kepada supplier.

---

### 3. Payment Entry

Payment Entry digunakan untuk melakukan pembayaran tagihan kepada supplier.

Data yang diisi:

- Payment Type
- Party Type
- Mode of Payment
- Bank
- Reference

Setelah Payment Entry disubmit:

Status Purchase Invoice berubah dari:

```
Unpaid → Paid
```

---

### 4. Purchase Receipt

Purchase Receipt digunakan untuk mencatat bahwa barang telah diterima oleh perusahaan.

Hasil yang terjadi:

- Barang masuk ke Warehouse.
- Quantity stok bertambah.
- Persediaan perusahaan bertambah.

Status akun berubah dari:

```
Stock Received But Not Billed
↓
Stock In Hand
```

Artinya persediaan tersebut sudah menjadi aset perusahaan.

---

## Pengaruh terhadap Laporan Keuangan

Pada Balance Sheet terjadi perubahan pada aset perusahaan.

- Uang perusahaan berkurang karena pembayaran supplier.
- Persediaan barang bertambah sebagai aset perusahaan.

---

## Catatan

### Purchase Order (PO)

Merupakan surat pemesanan barang kepada supplier.

### Purchase Invoice (PI)

Merupakan tagihan dari supplier kepada perusahaan.

### Status Unpaid

Menunjukkan invoice sudah diterima tetapi belum dibayar.

### Payment Entry

Digunakan untuk melakukan pembayaran kepada supplier sehingga status Purchase Invoice berubah menjadi **Paid**.

### Purchase Receipt

Menjadi bukti bahwa barang telah diterima perusahaan dan stok barang otomatis bertambah.

---

## Ringkasan Pembelajaran

Pada Chapter 2 mempelajari proses pembelian (Buying Cycle) pada ERPNext, dimulai dari membuat Purchase Order (PO), membuat Purchase Invoice (PI), melakukan Payment Entry untuk melunasi tagihan supplier, hingga membuat Purchase Receipt sebagai bukti penerimaan barang. Setelah seluruh proses selesai, transaksi akan tercatat secara otomatis pada laporan keuangan seperti:

- General Ledger
- Trial Balance
- Balance Sheet
- Profit & Loss

Sehingga seluruh transaksi pembelian dapat terdokumentasi dengan benar dan memengaruhi laporan keuangan perusahaan secara otomatis.

---

# Chapter 3 - Selling

## Tujuan

Mempelajari alur penjualan (Selling Cycle) pada ERPNext, mulai dari membuat Customer, memberikan penawaran (Quotation), membuat Sales Order, membuat Sales Invoice, menerima pembayaran, mengirim barang, hingga melihat pengaruh transaksi terhadap laporan keuangan.

---

## Alur Selling

Customer
↓
Quotation
↓
Sales Order
↓
Sales Invoice
↓
Payment Entry
↓
Delivery Note
↓
Review Laporan

---

## Materi yang Dipelajari

### 1. Customer

Customer merupakan pihak yang membeli barang dari perusahaan.

Yang dilakukan:

- Membuat data Customer.
- Menyimpan informasi customer yang akan melakukan transaksi.

---

### 2. Quotation

Quotation merupakan dokumen penawaran harga kepada customer.

Yang dilakukan:

- Membuat Quotation.
- Menentukan barang dan harga yang ditawarkan kepada customer.

---

### 3. Sales Order

Sales Order merupakan dokumen yang mencatat pesanan dari customer.

Yang dipelajari:

- Data Sales Order dapat dibuat dari Quotation sehingga tidak perlu memasukkan data barang dari awal.
- Sales Order menjadi dasar proses penjualan berikutnya.

---

### 4. Sales Invoice

Sales Invoice merupakan tagihan yang diberikan kepada customer.

Pencatatan akuntansi yang terjadi:

Debit

- Piutang Customer

Kredit

- Penjualan

Contoh:

```
Debit  : Piutang Customer   Rp15.000.000
Kredit : Penjualan          Rp15.000.000
```

Sales Invoice menandakan perusahaan telah melakukan penjualan kepada customer.

---

### 5. Payment Entry

Payment Entry digunakan untuk menerima pembayaran dari customer.

Payment Type yang digunakan:

- Receive

Setelah Payment Entry disubmit:

```
Status Sales Invoice

Unpaid → Paid
```

---

### 6. Delivery Note

Delivery Note digunakan untuk mencatat proses pengiriman barang kepada customer.

Yang terjadi setelah Delivery Note dibuat:

- Barang keluar dari gudang.
- Stok barang berkurang sesuai jumlah yang dikirim.
- Nilai persediaan berpindah menjadi Harga Pokok Penjualan (HPP).

---

## Review Laporan

Setelah seluruh transaksi selesai, dilakukan pengecekan pada laporan keuangan.

Laporan yang ditinjau:

- Profit & Loss
- Trial Balance
- Balance Sheet

Contoh hasil laporan:

### Profit & Loss

- Pendapatan : Rp15.000.000
- Harga Pokok Penjualan (HPP) : Rp10.000.000
- Biaya Lain (contoh: sewa kantor) : Rp500.000
- Profit : Rp4.500.000

### Trial Balance

- Total Debit : Rp25.500.000
- Total Kredit : Rp25.500.000

### Balance Sheet

- Profit : Rp4.500.000

---

## Catatan

### Quotation

Merupakan penawaran harga kepada customer.

### Sales Order

Merupakan dokumen pesanan dari customer.

### Sales Invoice

Merupakan tagihan yang diberikan kepada customer.

### Payment Entry (Receive)

Digunakan untuk menerima pembayaran dari customer.

### Delivery Note

Digunakan sebagai bukti bahwa barang telah dikirim kepada customer.

### Profit & Loss

Menampilkan laporan laba atau rugi perusahaan.

### Stock Ledger

Menampilkan riwayat pergerakan stok barang.

---

## Ringkasan Pembelajaran

Pada Chapter 3 mempelajari proses penjualan barang menggunakan ERPNext. Proses dimulai dari membuat Customer, kemudian membuat Quotation sebagai penawaran harga, dilanjutkan dengan Sales Order, Sales Invoice, menerima pembayaran melalui Payment Entry, dan mengirim barang menggunakan Delivery Note. Setelah seluruh proses selesai, dilakukan pengecekan laporan keuangan melalui Profit & Loss, Trial Balance, dan Balance Sheet untuk memastikan transaksi telah tercatat dengan benar.


---

# Chapter 4 - Cost Center & Project

## Tujuan

Mempelajari penggunaan **Cost Center** dan **Project** pada ERPNext untuk mengelompokkan transaksi sehingga pendapatan dan biaya dapat dipantau berdasarkan divisi maupun proyek tertentu.

---

## Materi yang Dipelajari

### Cost Center

Cost Center digunakan untuk mengelompokkan transaksi berdasarkan divisi atau bagian tertentu dalam perusahaan.

Contoh:

```
Sales1 - PTE
```

Digunakan agar transaksi penjualan maupun pembelian dapat dipantau melalui laporan keuangan.

---

### Project

Project digunakan untuk mengelompokkan transaksi berdasarkan suatu proyek tertentu.

Contoh:

```
Project2
```

Dengan Project, seluruh transaksi yang berkaitan dengan proyek dapat dilihat pada laporan keuangan.

---

## Membuat Cost Center

Langkah yang dilakukan:

- Search
- Cost Center
- Add Cost Center

---

## Membuat Project

Langkah yang dilakukan:

- Search
- Project
- Add Project

---

## Alur Transaksi

Cost Center & Project

↓

Purchase Order

↓

Purchase Receipt

↓

Purchase Invoice

↓

Payment Entry

↓

Sales Order

↓

Delivery Note

↓

Sales Invoice

↓

Payment Entry

↓

Review Laporan Keuangan

---

## Buying

### 1. Membuat Supplier

Membuat data supplier sebagai pihak yang menjual barang kepada perusahaan.

---

### 2. Purchase Order

Membuat Purchase Order dan memastikan bagian **Accounting** menggunakan:

- Cost Center : Sales1 - PTE
- Project : Project2

---

### 3. Purchase Receipt

Mencatat barang yang diterima perusahaan.

Yang dicek:

- Warehouse : Stores - PTE
- Accounting
- Cost Center
- Project

---

### 4. Purchase Invoice

Membuat Purchase Invoice dan memastikan bagian Accounting menggunakan:

- Cost Center : Sales1 - PTE
- Project : Project2

---

### 5. Payment Entry

Melakukan pembayaran kepada supplier.

Pengaturan:

- Paid From : HSBC
- Reference Type : Purchase Invoice

---

## Selling

### 1. Customer

Membuat data Customer.

---

### 2. Sales Order

Membuat Sales Order dan memastikan Accounting menggunakan:

- Cost Center : Sales1 - PTE
- Project : Project2

---

### 3. Delivery Note

Membuat Delivery Note.

Yang dicek:

- Warehouse : Stores - PTE
- Cost Center
- Project

---

### 4. Sales Invoice

Membuat Sales Invoice dan memastikan Accounting menggunakan:

- Cost Center : Sales1 - PTE
- Project : Project2

---

### 5. Payment Entry

Menerima pembayaran dari customer.

Pengaturan:

- Paid To : HSBC - PTE

---

## Review Laporan Keuangan

Setelah seluruh transaksi Buying dan Selling selesai, dilakukan pengecekan laporan keuangan dengan filter:

- Cost Center : Sales1 - PTE
- Project : Project2

Hasil laporan menunjukkan nilai transaksi sebesar **Rp3.000.000**, sehingga transaksi berhasil dicatat dan dipisahkan berdasarkan Cost Center dan Project yang digunakan.

---

## Catatan

Pada Chapter 4 mempelajari penggunaan **Cost Center** dan **Project** untuk memisahkan serta melacak transaksi perusahaan.

Pada proses pengujian digunakan:

- Cost Center : Sales1 - PTE
- Project : Project2

Keduanya diterapkan pada seluruh proses Buying dan Selling, mulai dari Purchase Order hingga Sales Invoice. Setelah seluruh transaksi selesai, laporan keuangan dapat difilter berdasarkan Cost Center dan Project sehingga setiap transaksi dapat dipantau sesuai divisi maupun proyek yang dipilih.

---

## Ringkasan Pembelajaran

Pada Chapter 4 mempelajari cara membuat dan menggunakan Cost Center serta Project pada ERPNext. Fitur ini digunakan untuk mengelompokkan transaksi pembelian dan penjualan sehingga laporan keuangan dapat dianalisis berdasarkan divisi maupun proyek tertentu. Seluruh transaksi berhasil tercatat dan dapat ditampilkan melalui filter Cost Center dan Project pada laporan keuangan.


---

# Chapter 5 - Letter Head & Custom Print Format

## Tujuan

Mempelajari cara mengatur dan menyesuaikan tampilan dokumen pada ERPNext menggunakan **Letter Head** dan **Custom Print Format** sehingga dokumen yang dicetak memiliki identitas perusahaan dan format yang sesuai kebutuhan.

---

## Materi yang Dipelajari

### 1. Letter Head

Letter Head digunakan untuk menampilkan identitas resmi perusahaan pada dokumen ERPNext.

Informasi yang dapat ditampilkan antara lain:

- Logo perusahaan
- Nama perusahaan
- Nomor telepon
- Email
- Alamat perusahaan

Letter Head dapat digunakan pada berbagai dokumen ERPNext seperti:

- Sales Invoice
- Purchase Invoice
- Quotation
- Delivery Note
- Dokumen lainnya

---

### 2. Print Format

Print Format digunakan untuk mengatur tampilan dokumen yang akan dicetak atau disimpan menjadi PDF.

Dengan Print Format, informasi yang ditampilkan pada dokumen dapat disesuaikan dengan kebutuhan perusahaan.

---

## Alur Pengujian

### 1. Menggunakan Sales Invoice

Menggunakan Sales Invoice yang telah dibuat pada chapter sebelumnya sebagai dokumen uji untuk melihat perubahan tampilan tanpa perlu membuat transaksi baru.

---

### 2. Membuat Letter Head

Membuat Letter Head dengan nama:

```
PT Testing ERP Letter Head
```

Letter Head digunakan sebagai identitas resmi perusahaan pada dokumen ERPNext.

---

### 3. Membuat Footer Menggunakan HTML

Membuat footer menggunakan HTML pada bagian bawah dokumen.

Contoh informasi yang ditampilkan:

- Nama perusahaan
- Nomor telepon
- Email
- Alamat perusahaan

Penggunaan HTML memungkinkan pengaturan:

- Posisi teks
- Ukuran teks
- Warna
- Format tampilan

Sehingga footer terlihat lebih rapi dan sesuai kebutuhan.

---

### 4. Membuat Custom Print Format

Membuat Print Format baru.

Konfigurasi yang digunakan:

- Print Format Name : Custom Sales Invoice
- DocType : Sales Invoice
- Module : Accounts
- Default Print Language : English

Custom Print Format digunakan untuk membuat tampilan Sales Invoice tanpa mengubah Print Format bawaan ERPNext.

---

### 5. Mengubah Judul Dokumen

Mengubah heading dokumen dari:

```
Sales Invoice
```

menjadi

```
Customer Invoice
```

Tujuannya agar nama dokumen sesuai dengan kebutuhan perusahaan.

---

### 6. Menghapus Field yang Tidak Diperlukan

Melakukan penyederhanaan tampilan invoice dengan menghapus field yang tidak diperlukan.

Field yang dipertahankan:

- Customer Name
- Posting Date
- Payment Due Date
- Cost Center
- Items
- Total Quantity
- Total
- Grand Total
- Rounded Total
- In Words

Tujuannya agar invoice menjadi lebih sederhana, rapi, dan hanya menampilkan informasi yang diperlukan.

---

### 7. Menggunakan Custom Print Format

Setelah Custom Print Format selesai dibuat, Sales Invoice dibuka kembali kemudian pada bagian **Print Format** dipilih:

```
Custom Sales Invoice
```

Letter Head yang digunakan:

```
PT Testing ERP Letter Head
```

---

### 8. Pengecekan Akhir

Melakukan Print Preview untuk memastikan seluruh perubahan berhasil diterapkan.

Yang diperiksa:

- Letter Head tampil dengan benar.
- Footer HTML tampil pada bagian bawah dokumen.
- Heading berubah menjadi **Customer Invoice**.
- Field yang tidak diperlukan berhasil dihapus.
- Data customer tetap tampil.
- Posting Date dan Payment Due Date tampil.
- Cost Center tampil.
- Data Item tampil.
- Total transaksi tampil.
- Footer perusahaan muncul sesuai HTML yang dibuat.

---

## Hasil

Custom Print Format berhasil diterapkan pada Sales Invoice.

Hasil Print Preview menunjukkan:

- Judul dokumen berubah menjadi **Customer Invoice**.
- Data Customer tetap tampil.
- Posting Date dan Payment Due Date tampil.
- Cost Center tampil.
- Data Item tampil.
- Total transaksi tampil.
- Footer perusahaan berhasil muncul sesuai HTML yang dibuat.

---

## Ringkasan Pembelajaran

Pada Chapter 5 mempelajari cara membuat **Letter Head** dan **Custom Print Format** pada ERPNext. Proses dimulai dengan membuat identitas perusahaan menggunakan Letter Head, kemudian membuat footer menggunakan HTML, membuat Custom Print Format khusus untuk Sales Invoice, mengubah judul dokumen, menghapus field yang tidak diperlukan, hingga melakukan Print Preview. Hasil akhirnya adalah Sales Invoice memiliki tampilan yang lebih rapi, sesuai identitas perusahaan, dan memenuhi kebutuhan perusahaan tanpa mengubah Print Format bawaan ERPNext.


---

# Chapter 6 - Purchase Cycle

## Tujuan

Mempelajari alur lengkap proses pembelian barang pada ERPNext mulai dari pembuatan Item, Purchase Order, penerimaan barang, pembayaran kepada supplier, hingga pengecekan transaksi pada laporan.

---

## Purchase Cycle

Purchase Cycle merupakan proses pembelian barang dari supplier yang meliputi:

- Pemesanan barang
- Penerimaan barang
- Pencatatan tagihan
- Pembayaran kepada supplier
- Pengecekan transaksi pada laporan

---

## Alur Purchase Cycle

Item

↓

Purchase Order

↓

Purchase Receipt

↓

Stock Ledger

↓

Purchase Invoice

↓

Payment Entry

↓

General Ledger

---

## Studi Kasus

Melakukan pembelian:

- Supplier : Supplier1
- Item : ITEM02 (Pensil)
- Quantity : 10 unit
- Harga : Rp10.000 / unit
- Total Pembelian : Rp100.000

---

## Membuat Item

Membuat data item yang akan digunakan pada transaksi ERPNext.

Data yang digunakan:

- Item Code : ITEM02
- Item Name : Pensil
- Item Group : Products

Item yang dibuat akan digunakan sebagai stok dan dapat digunakan pada seluruh transaksi ERPNext.

---

## Purchase Order

Membuat Purchase Order kepada Supplier.

Data yang digunakan:

- Supplier : Supplier1
- Item : ITEM02 - Pensil
- Quantity : 10
- Rate : Rp10.000
- Total : Rp100.000

---

## Purchase Receipt

Mencatat bahwa barang dari supplier telah diterima.

Data transaksi:

- Supplier : Supplier1
- Accepted Quantity : 10
- Item : ITEM02 - Pensil
- Warehouse : Stores - PTE
- Grand Total : Rp100.000

---

## Stock Ledger

Melakukan pengecekan Stock Ledger untuk melihat riwayat pergerakan stok barang.

Hasil pengujian menunjukkan stok ITEM02 bertambah sebanyak 10 unit setelah Purchase Receipt dilakukan.

---

## Purchase Invoice

Membuat Purchase Invoice sebagai tagihan dari supplier.

---

## Payment Entry

Melakukan pembayaran kepada supplier.

---

## General Ledger

Melakukan pengecekan General Ledger untuk memastikan seluruh transaksi Purchase Receipt, Purchase Invoice, dan Payment Entry telah tercatat dengan benar.

---

## Ringkasan Pembelajaran

Pada Chapter 6 mempelajari proses Purchase Cycle pada ERPNext mulai dari membuat Item, Purchase Order, Purchase Receipt, Purchase Invoice, Payment Entry hingga pengecekan Stock Ledger dan General Ledger. Seluruh transaksi berhasil tercatat sehingga stok barang dan laporan keuangan diperbarui secara otomatis.

---


---

# Chapter 7 - Batch Management

## Tujuan

Mempelajari penggunaan fitur Batch Management pada ERPNext untuk mencatat dan melacak pergerakan stok barang berdasarkan Batch Number.

---

## Batch Management

Batch Management digunakan untuk:

- Mengelompokkan barang berdasarkan batch tertentu.
- Melacak pergerakan stok.
- Digunakan pada produk yang memiliki tanggal kedaluwarsa, seperti obat-obatan dan makanan.

---

## Langkah Pengujian

### Membuat Item Baru

Data item:

- Item Code : ITEM03
- Item Name : Panadol Extra
- Item Group : Products

Mengaktifkan fitur:

- Has Batch No
- Maintain Stock

---

### Membuat Batch Baru

Contoh Batch:

- BATCH-ITEM03-001

---

### Purchase Receipt

Menerima barang ke:

- Warehouse : Stores - PTE

---

### Purchase Invoice

Status:

- Unpaid

---

### Payment Entry

Data:

- Payment Type : Pay
- Party : Supplier

---

### Stock Ledger

Melakukan filter berdasarkan:

- Item : ITEM03
- Batch : BATCH-ITEM03-001

---

### Delivery Note

Membuat Delivery Note untuk proses pengiriman barang.

---

### Sales Invoice

Status:

- Unpaid

---

### Payment Entry

Status:

- Paid

---

### Stock Ledger

Melakukan pengecekan kembali Stock Ledger untuk memastikan pergerakan stok berdasarkan Batch Number.

---

## Ringkasan Pembelajaran

Pada Chapter 7 dilakukan pengujian Batch Management pada ERPNext untuk mencatat dan melacak pergerakan stok berdasarkan Batch Number sehingga setiap batch barang dapat dipantau secara terpisah.

---


---

# Chapter 8 - POS Profile

## Tujuan

Mempelajari proses transaksi menggunakan Point of Sale (POS) pada ERPNext.

---

## POS Profile

POS digunakan untuk melakukan transaksi penjualan secara langsung kepada pelanggan, seperti sistem kasir pada minimarket, toko, apotek, maupun restoran.

Berbeda dengan proses penjualan biasa, pada POS transaksi dilakukan lebih cepat karena pelanggan langsung memilih barang, melakukan pembayaran, menerima barang, dan transaksi selesai.

---

## Proses Pengujian

Melakukan pengujian mulai dari:

- Membuat POS Profile
- POS Opening Entry
- Transaksi Penjualan
- POS Closing Entry

---

### Membuat POS Profile

Konfigurasi:

- Warehouse : Stores - PTE
- User : Administrator
- Price List : Standard
- Mode Pembayaran : Cash

---

### POS Opening Entry

Data:

- Cashier : Administrator
- Opening Amount : Rp1.000.000

---

### Melakukan Transaksi POS

Melakukan transaksi menggunakan:

- Item : Panadol
- Quantity : 3
- Payment : Cash

POS digunakan sebagai halaman kasir untuk menerima pembayaran pelanggan.

---

### POS Invoice

ERPNext secara otomatis membuat POS Invoice sebagai bukti transaksi.

Perbedaan:

- Sales Invoice : Unpaid sebelum pembayaran.
- POS Invoice : Langsung Paid karena pembayaran dilakukan saat transaksi berlangsung.

---

### POS Closing Entry

Digunakan untuk menutup sesi kasir.

Fungsi:

- Menampilkan seluruh transaksi selama sesi POS.
- Melakukan pengecekan transaksi sejak POS Opening dibuat.

---

### Payment Reconciliation

Perhitungan:

- Opening Amount : Rp1.000.000
- Penjualan POS : Rp45.000
- Closing Amount : Rp1.045.000
- Difference : Rp0

Tidak terdapat selisih kas.

---

## Ringkasan Pembelajaran

Pada Chapter 8 mempelajari proses transaksi menggunakan Point of Sale mulai dari membuat POS Profile, membuka sesi kasir, melakukan transaksi penjualan, membuat POS Invoice, hingga menutup sesi kasir dan melakukan pengecekan saldo kas.

---


---

# Chapter 9 - Batch Number pada POS

## Tujuan

Mempelajari penggunaan Batch Number pada transaksi Point of Sale.

---

## Batch Number

Batch Number merupakan identitas kelompok barang yang digunakan untuk membedakan stok dari produk yang sama tetapi berasal dari batch yang berbeda.

Umumnya digunakan pada produk yang memiliki tanggal kedaluwarsa, seperti makanan dan obat-obatan.

---

## Langkah Pengujian

- Membuat Batch kedua.
- Melakukan Purchase Receipt.
- Membuka POS Opening Entry.
- Melakukan transaksi POS.
- Checkout.
- Complete Order.
- Membuat POS Closing Entry.

---

## Hasil

Closing:

- Opening Amount : Rp1.000.000
- Penjualan : Rp45.000
- Closing Amount : Rp1.045.000
- Difference : Rp0

---

## Catatan

ERPNext memiliki keterbatasan dalam penggunaan barcode batch karena scanner belum dapat langsung membedakan batch hanya berdasarkan barcode produk.

Solusinya adalah melakukan customisasi barcode yang menggabungkan informasi Item dengan Batch.

---

## Ringkasan Pembelajaran

Pada Chapter 9 mempelajari penggunaan Batch Number pada transaksi Point of Sale untuk membedakan stok barang berdasarkan kelompok batch sehingga pergerakan barang lebih mudah dilacak.

---


---

# Chapter 10 - Users, Roles & Permission

## Tujuan

Mempelajari pengelolaan User, Role, dan Permission pada ERPNext.

---

## Konsep

- User : akun yang digunakan untuk masuk ke sistem.
- Role : jabatan atau fungsi user.
- Permission : hak akses yang dimiliki user.

Tujuan Permission adalah membatasi akses sesuai tugas dan tanggung jawab masing-masing pengguna.

---

## Langkah Pengujian

### Membuat User Baru

Data:

- Nama : Tony
- Email : Tony@Testing.com

Mengatur password untuk user tersebut.

---

### Memberikan Role

Role yang diberikan:

- Sales User

Role ini digunakan oleh pengguna yang bekerja pada bagian penjualan.

---

### Menguji Hak Akses

Melakukan pengujian pada menu:

Selling → Quotation

User Tony dapat:

- Membuka Quotation List
- Membuat Quotation
- Memilih Customer
- Menambahkan Item
- Menyimpan Quotation

---

### Menguji Pembatasan Hak Akses

Saat mencoba membuka User List milik Administrator muncul pesan:

```
Not Permitted
```

Artinya user hanya dapat mengakses fitur sesuai Role yang dimiliki.

---

## Ringkasan Pembelajaran

Pada Chapter 10 mempelajari pengelolaan User, Role, dan Permission sehingga setiap pengguna hanya memiliki hak akses sesuai pekerjaan masing-masing.

---


---

# Chapter 11 - Role Permission Manager

## Tujuan

Mempelajari pengaturan hak akses secara lebih rinci menggunakan Role Permission Manager.

---

## Materi

Role Permission Manager digunakan untuk menentukan tindakan yang boleh dilakukan oleh setiap Role.

Contoh:

Staff Sales Junior dapat membuat dan mengedit Quotation, tetapi tidak dapat melakukan Submit atau Delete.

---

## Jenis Permission

Permission yang tersedia:

- Read
- Write
- Create
- Delete
- Submit
- Cancel
- Amend
- Print

---

## Pengujian

Role Sales User diberikan hak:

- Read
- Write
- Create

Hak yang dibatasi:

- Delete
- Submit
- Cancel
- Amend

---

## Hasil

Saat login sebagai Tony:

- Masih dapat membuat Quotation.
- Masih dapat mengedit Quotation.
- Tidak dapat Delete.
- Tidak dapat Submit.
- Tidak dapat Cancel.
- Tidak dapat Amend.

---

## Ringkasan Pembelajaran

Pada Chapter 11 mempelajari penggunaan Role Permission Manager untuk mengatur hak akses setiap Role secara lebih rinci sehingga keamanan sistem lebih terjaga.

---


---

# Chapter 12 - Manufacturing Module

## Tujuan

Mempelajari proses produksi pada ERPNext mulai dari Bill of Materials (BOM) hingga menghasilkan Finished Goods.

---

## BOM (Bill of Materials)

BOM berisi daftar bahan baku yang dibutuhkan untuk membuat suatu produk.

Contoh:

Produk:

FG - Plumcake

Bahan baku:

- Tepung : 5 kg
- Gula : 2 kg
- Telur : 20 butir

---

## Work Order

Work Order digunakan sebagai perintah untuk menjalankan proses produksi berdasarkan BOM.

---

## Menyiapkan Bahan Baku

Mengisi stok awal menggunakan Stock Reconciliation.

Contoh:

- Tepung
- Gula
- Telur

Jika valuation rate belum tersedia maka akan muncul error **Valuation Missing**.

---

## Material Transfer for Manufacture

Memindahkan bahan baku dari gudang menuju Work In Progress.

---

## Job Card

Digunakan untuk menjalankan setiap proses produksi seperti:

- Mixing
- Cooking
- Packing

Proses:

Start Job → Complete Job → Submit

---

## Hasil

Setelah seluruh proses selesai, ERPNext menghasilkan Finished Goods dan memasukkannya ke gudang.

---

## Ringkasan Pembelajaran

Pada Chapter 12 mempelajari proses produksi menggunakan Manufacturing Module mulai dari membuat BOM, Work Order, menyiapkan bahan baku, Material Transfer, Job Card hingga menghasilkan Finished Goods.

---


---

# Chapter 16 - Invoice Payment Reconciliation

## Tujuan

Mempelajari pencatatan pembayaran invoice dan proses rekonsiliasi pembayaran pada ERPNext.

---

## Langkah Pengujian

### Membuat Sales Invoice

Data:

- Customer
- Item
- Quantity : 1
- Total Invoice : Rp500.000

Status:

- Unpaid

---

### Pembayaran Sebagian

Melakukan Payment Entry.

- Total Invoice : Rp500.000
- Pembayaran : Rp200.000
- Sisa Tagihan : Rp300.000

Status:

- Partly Paid

---

### Pelunasan

Melakukan Payment Entry kedua.

- Outstanding Amount : Rp300.000
- Paid Amount : Rp300.000

Status berubah menjadi:

- Paid

---

## Payment Reconciliation

Digunakan untuk menghubungkan pembayaran yang belum dialokasikan dengan Sales Invoice yang sesuai.

Perbedaan:

- **Payment Entry** digunakan untuk mencatat pembayaran customer.
- **Payment Reconciliation** digunakan untuk menghubungkan pembayaran yang belum teralokasi dengan invoice.

---

## Ringkasan Pembelajaran

Pada Chapter 16 mempelajari proses pembayaran invoice secara bertahap hingga lunas serta penggunaan Payment Reconciliation untuk memastikan pembayaran telah terhubung dengan invoice yang sesuai.


---

# Kesimpulan

Selama proses magang, saya mempelajari berbagai modul ERPNext mulai dari Accounting, Buying, Selling, Cost Center & Project, Letter Head & Custom Print Format, Purchase Cycle, Batch Management, POS, Users & Permission, Manufacturing Module, hingga Invoice Payment Reconciliation. Dokumentasi ini disusun berdasarkan praktik langsung dan catatan pembelajaran pada setiap chapter.
