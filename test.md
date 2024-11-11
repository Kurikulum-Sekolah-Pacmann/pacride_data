# Deskripsi Data untuk Tabel Database Penjualan

---

## Tabel `product`
Menyimpan informasi terkait produk yang dijual oleh perusahaan.

- **product_key** *(int)*: Identifier untuk setiap produk.
- **name** *(varchar)*: Nama produk.
- **standard_cost** *(varchar)*: Biaya standar produksi per produk (dalam dolar)
- **color** *(varchar)*: Warna produk.
- **subcategory** *(varchar)*: Subkategori dari produk. (contoh: Bottles and Cages, Touring Frames, Handlebars, Cleaners)
- **category** *(varchar)*: Kategori produk. (Bikes, Accessories, Clothing, Components)
- **background_color_format** *(varchar)*: Warna latar belakang produk.
- **font_color_format** *(varchar)*: Warna font prodok.

---

## Tabel `region`
Menyimpan informasi terkait wilayah penjualan produk

- **sales_teritory_key** *(int)*: Indentifier regionn.
- **name** *(varchar)*: Nama wilayah.
- **country** *(varchar)*: Negara tempat wilayah berada.
- **group** *(varchar)*: Grup wilayah, dapat berupa negara atau negara bagian.

---

## Tabel `reseller`
Menyimpan data tentang reseller yang menjual produk dari perusahaan.

- **reseller_key** *(int)*: Identifier untuk setiap reseller.
- **name** *(varchar)*: Nama reseller.
- **bussiness_type** *(varchar)*: Jenis bisnis yang dimiliki oleh reseller, seperti Warehouse, Specialty Bike Shop atau Value Added Reseller.
- **city** *(varchar)*: Kota tempat reseller berada.
- **state_province** *(varchar)*: Provinsi atau negara bagian dari reseller.
- **country** *(varchar)*: Negara tempat reseller.

---

## Tabel `sales_person`
Menyimpan data tentang karyawan yang bertanggung jawab atas departemen sales.

- **employee_key** *(int)*: Indentifier karyawan .
- **employee_id** *(int)*: ID unik dari karyawan di dalam perusahaan.
- **name** *(varchar)*: Nama karyawan.
- **title** *(varchar)*: Jabatan atau posisi pekerjaan.
- **upn** *(varchar)*: User Principal Name atau username yang digunakan sebagai alamat email karyawan (username@adventureworks.com)

---

## Tabel `sales`
Menyimpan catatan transaksi penjualan produk.

- **sales_key** *(int)*: Identifier unik untuk setiap transaksi penjualan.
- **sales_order_number** *(varchar)*: Nomor untuk setiap pesanan penjualan.
- **order_date** *(date)*: Tanggal pesanan dibuat.
- **product_key** *(int)*: Produk yang dijual, mengacu ke `product` kolom product_key.
- **reseller_key** *(int)*: Reseller yang membeli produk, mengacu ke `reseller` kolom reseller_key.
- **employee_key** *(int)*: Karyawan yang menangani penjualan, mengacu ke `sales_person` kolom employee_key.
- **sales_teritory_key** *(int)*: Wilayah transaksi penjualan, mengacu ke `region` kolom sales_teritory_key.
- **quantity** *(varchar)*: Jumlah produk yang dijual.
- **unit_price** *(varchar)*: Harga per unit produk. (dalam dolar)
- **sales** *(varchar)*: Total nilai penjualan untuk transaksi. (dalam dolar)
- **cost** *(varchar)*: Total biaya dari transaksi tersebut. (dalam dolar)

---

## Tabel `sales_person_region`
Menyimpan hubungan antara karyawan penjualan dan wilayah penjualan yang dikelola.

- **employee_key** *(int)*: FK karyawan, mengacu ke `sales_person`.
- **SalesTerritoryKey** *(int)*: FK wilayah penjualan, mengacu ke `region`.

---

## Tabel `target`
Menyimpan informasi tentang target penjualan bulanan yang diberikan kepada setiap karyawan.

- **employee_key** *(int)*: karyawan yang memiliki target, mengacu ke `sales_person`.
- **target_month** *(date)*: Bulan target penjualan.
- **target_value** *(varchar)*: Nilai target penjualan dalam bentuk angka. (dalam dolar)

---