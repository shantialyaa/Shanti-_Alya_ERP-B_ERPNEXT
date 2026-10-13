# SKENARIO PRAKTIK TRANSAKSI MANUFAKTUR DI ERPNEXT

Gunakan skenario ini untuk melakukan simulasi transaksi di ERPNext dari awal hingga akhir.

---

## 🎯 SKENARIO 1: Pengadaan Bahan Baku (Procurement Cycle)

**Tujuan:** Membeli stok bahan baku yang cukup untuk memproduksi 10 unit Meja Belajar.

### Langkah 1.1: Buat Purchase Order (PO) ke Supplier
1. Buka menu **Buying** > **Purchase Order** > klik **Add Purchase Order**.
2. **Supplier:** `PT Rimba Mahoni Lestari`
3. Tambahkan Item:
   * `RM-KY-001` (Papan Kayu Mahoni): Qty **25 Lembar**, Rate: **Rp 45.000**
4. Klik **Save** lalu **Submit**.

*(Lakukan hal serupa untuk membeli Pipa Besi, Sekrup, Lem, Vernis, dan Amplas ke supplier terkait).*

### Langkah 1.2: Penerimaan Barang (Purchase Receipt)
1. Buka Purchase Order yang sudah di-submit.
2. Klik tombol **Create** di kanan atas > pilih **Receipt**.
3. Pastikan **Accepted Warehouse** diarahkan ke **Gudang Bahan Baku**.
4. Klik **Save** lalu **Submit**.
5. *Hasil:* Stok bahan baku sekarang resmi bertambah di sistem.

### Langkah 1.3: Catat Tagihan Supplier (Purchase Invoice)
1. Dari Purchase Receipt atau PO, klik **Create** > **Invoice**.
2. Klik **Save** dan **Submit**.
3. *(Opsional)* Catat pembayaran lewat tombol **Create** > **Payment**.

---

## ⚙️ SKENARIO 2: Proses Produksi Manufaktur (Work Order & Execution)

**Tujuan:** Memproduksi 10 Unit Meja Belajar Shanti (`FG-MB-001`).

### Langkah 2.1: Buat Work Order (Perintah Kerja Pabrik)
1. Buka menu **Manufacturing** > **Work Order** > klik **Add Work Order**.
2. **Item To Manufacture:** `FG-MB-001`
3. **Qty to Manufacture:** `10`
4. **BOM No:** Pilih BOM yang sudah dibuat sebelumnya.
5. **Source Warehouse:** `Gudang Bahan Baku` (gudang asal bahan baku).
6. **WIP Warehouse:** `Gudang Work In Progress` (gudang lantai produksi).
7. **Target Warehouse:** `Gudang Barang Jadi` (tujuan barang saat jadi).
8. Klik **Save** lalu **Submit**.

### Langkah 2.2: Transfer Bahan Baku ke Lantai Pabrik (Start)
1. Di dalam Work Order yang aktif, klik tombol **Create** / **Start** di pojok kanan atas.
2. Sistem akan membuat dokumen **Stock Entry (Material Transfer for Manufacture)**.
3. Dokumen ini otomatis memindahkan:
   * 20 Lembar Kayu
   * 10 Meter Pipa Besi
   * 2 Box Sekrup
   * 2.5 Botol Lem
   * 2 Kaleng Cat Vernis
   * 5 Lembar Amplas
   dari **Gudang Bahan Baku** ke **Gudang WIP**.
4. Klik **Save** lalu **Submit**.

### Langkah 2.3: Catat Barang Jadi (Finish Production)
1. Kembali ke dokumen **Work Order** tadi.
2. Klik tombol **Finish**.
3. Sistem akan membuat **Stock Entry (Manufacture)**:
   * Mengonsumsi seluruh bahan di Gudang WIP.
   * Menambahkan **10 Unit FG-MB-001** ke **Gudang Barang Jadi**.
4. Klik **Save** lalu **Submit**.
5. Status Work Order sekarang berubah menjadi **Completed**!

---

## 💰 SKENARIO 3: Siklus Penjualan (Order to Cash)

**Tujuan:** Menjual 5 unit Meja Belajar ke `Toko Mebel Nusantara Indah`.

### Langkah 3.1: Buat Sales Order (Pesanan Penjualan)
1. Buka menu **Selling** > **Sales Order** > klik **Add Sales Order**.
2. **Customer:** `Toko Mebel Nusantara Indah`
3. **Item:** `FG-MB-001`, Qty: `5 Unit`, Rate: `Rp 750.000`.
   *(Total: Rp 3.750.000)*
4. Klik **Save** lalu **Submit**.

### Langkah 3.2: Kirim Barang (Delivery Note)
1. Di dalam Sales Order, klik **Create** > **Delivery**.
2. Pastikan **Set Source Warehouse** adalah **Gudang Barang Jadi**.
3. Klik **Save** lalu **Submit**.
4. *Hasil:* Stok di Gudang Barang Jadi otomatis berkurang 5 unit.

### Langkah 3.3: Terbitkan Faktur Penjualan (Sales Invoice)
1. Di dalam Sales Order atau Delivery Note, klik **Create** > **Invoice**.
2. Klik **Save** lalu **Submit**.

### Langkah 3.4: Terima Pembayaran Customer
1. Di Sales Invoice, klik **Create** > **Payment**.
2. Masukkan akun penerima (misal: Bank / Cash).
3. Klik **Save** lalu **Submit**.

---

## 📊 SKENARIO 4: Pemeriksaan Laporan

1. **Laporan Kartu Stok:**
   * Buka **Stock** > **Stock Ledger**.
   * Anda bisa melihat mutasi stok dari pembelian, transfer produksi, hingga pengiriman barang jadi.
2. **Laporan Laba Rugi:**
   * Buka **Accounting** > **Profit and Loss Statement**.
   * Lihat Pendapatan Penjualan (Revenue), Harga Pokok Penjualan (COGS), dan Laba Bersih yang diperoleh dari transaksi di atas!
