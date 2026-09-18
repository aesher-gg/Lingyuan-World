# 🎭 Wuxian World — Event Khusus & Peristiwa Dunia

> **Modul:** 39 — Custom Events
> **Fungsi:** Tempat Admin mencatat event-event khusus yang terjadi di dunia, baik yang sudah terjadi maupun yang akan datang.
> **Pengelolaan:** Hanya Admin (pemilik repo) yang boleh mengedit file ini. AI GM WAJIB membaca bagian EVENT AKTIF sebelum memulai sesi.
> **Rujukan silang:** `01`–`08` (lokasi event)

---

## 📋 Cara Menggunakan File Ini

1. **Event Aktif** adalah event yang sedang berlangsung atau akan segera terjadi. AI GM WAJIB memasukkan event ini ke dalam narasi.
2. **Event Selesai** adalah event yang sudah berlalu. AI GM bisa merujuknya sebagai sejarah/latar belakang.
3. **Event Mendatang** adalah event yang sudah dijadwalkan tapi belum terjadi. AI GM bisa memberi "firasat" atau "desas-desus" tentang event ini.
4. Setiap event diberi **ID unik** (misal: `EVT-001`) agar mudah dirujuk.

---

## 🔴 EVENT AKTIF (Sedang Berlangsung)

*(Bagian ini diisi oleh Admin. Isi sesuai kebutuhan.)*

### EVT-001: [Nama Event]
- **Status:** 🔴 AKTIF
- **Lokasi:** [Wilayah/Kota]
- **Tanggal Mulai:** [Tahun/Bulan/Hari in-game]
- **Tanggal Berakhir:** [Tahun/Bulan/Hari in-game, jika ada]
- **Deskripsi Singkat:**
  [Cerita singkat tentang apa yang terjadi]
- **Dampak ke Dunia:**
  - [Dampak 1]
  - [Dampak 2]
- **NPC Terkait:** [Nama NPC yang terlibat, jika ada]
- **Hadiah/Bonus untuk Pemain:** [Jika ada]
- **Trigger untuk AI GM:**
  - Jika pemain berada di [lokasi], sampaikan [deskripsi suasana/kejadian]
  - Jika pemain bertemu [NPC tertentu], sampaikan [dialog/reaksi]

---

## 🟡 EVENT MENDAFTAR (Belum Terjadi)

*(Bagian ini diisi oleh Admin untuk event yang akan datang.)*

### EVT-002: [Nama Event]
- **Status:** 🟡 MENDAFTAR
- **Lokasi:** [Wilayah/Kota]
- **Tanggal Mulai:** [Tahun/Bulan/Hari in-game]
- **Deskripsi Singkat:**
  [Cerita singkat tentang apa yang akan terjadi]
- **Pertanda/Firasat:**
  - [Pertanda 1 yang bisa dirasakan pemain]
  - [Pertanda 2]
- **Trigger untuk AI GM:**
  - Jika pemain berada di [lokasi], sampaikan [firasat/desas-desus]

---

## ⚪ EVENT SELESAI (Sudah Berlalu)

*(Bagian ini diisi oleh Admin untuk event yang sudah selesai.)*

### EVT-000: [Contoh — Hapus atau ganti dengan event nyata]
- **Status:** ⚪ SELESAI
- **Lokasi:** [Wilayah/Kota]
- **Tanggal:** [Tahun/Bulan/Hari in-game]
- **Deskripsi:**
  [Cerita singkat tentang apa yang terjadi]
- **Dampak yang Tersisa:**
  - [Dampak jangka panjang]
- **Trigger untuk AI GM:**
  - Jika pemain bertanya tentang [topik], sampaikan [versi sejarah/kabar yang beredar]

---

## 📝 Template Kosong untuk Admin

Salin template di bawah ini untuk menambahkan event baru:

```markdown
### EVT-XXX: [Nama Event]
- **Status:** [🔴 AKTIF / 🟡 MENDAFTAR / ⚪ SELESAI]
- **Lokasi:** [Wilayah/Kota]
- **Tanggal Mulai:** [Tahun/Bulan/Hari]
- **Tanggal Berakhir:** [Tahun/Bulan/Hari, jika ada]
- **Deskripsi Singkat:**
  [Tulis deskripsi di sini]
- **Dampak ke Dunia:**
  - [Dampak 1]
  - [Dampak 2]
- **NPC Terkait:** [Nama NPC]
- **Hadiah/Bonus untuk Pemain:** [Jika ada]
- **Trigger untuk AI GM:**
  - [Trigger 1]
  - [Trigger 2]
