# 📜 Wuxian World — Hukum Kultivasi Kustom (Custom Laws)

> **Modul:** 40 — Custom Laws
> **Fungsi:** Tempat Admin mencatat Hukum Kultivasi buatan pemain atau tambahan Admin.
> **Pengelolaan:** Hanya Admin (pemilik repo) yang boleh mengedit file ini. AI GM WAJIB membaca daftar ini saat pemain menggunakan/bertemu Hukum kustom.
> **Rujukan silang:** `09_CULTIVATION_LAW_SYSTEM.md` (sistem dasar Hukum), `10_ECONOMY_SYSTEM.md` (harga resource terkait)

---

## 📋 Cara Menggunakan File Ini

1. Setiap Hukum Kustom diberi **ID unik** (misal: `LAW-001`).
2. Hukum ini **bisa berasal dari**:
   - Kreasi Admin untuk memperkaya dunia.
   - Kreasi pemain yang disetujui Admin.
3. Hukum yang sudah dicatat di sini dianggap **RESMI** dan berlaku di dunia.
4. AI GM WAJIB menggunakan data di sini saat berinteraksi dengan Hukum tersebut.
5. Jika ada konflik dengan Hukum di `09_CULTIVATION_LAW_SYSTEM.md`, maka **Hukum di file ini (Custom) yang menang (override)** untuk Hukum spesifik tersebut.

---

## 📜 DAFTAR HUKUM KULTIVASI KUSTOM

### LAW-001: [Nama Hukum]
- **Jenis:** [Dao Abadi / Raga Sejati / Gu Karma / Qi Naga Api / Roh Hantu / Kustom Lainnya]
- **Asal Usul:** [Admin / Nama Pemain]
- **Deskripsi Singkat:**
  [Penjelasan tentang apa yang membuat Hukum ini unik]
- **Afinitas Elemen:** [Api/Air/Tanah/Angin/Es/Racun/Roh/Darah/dll]
- **Qi Cap Modifier:** [×1,0 / ×1,2 / ×0,8, dst] — lihat `09` §8
- **Kelebihan:**
  - [Kelebihan 1]
  - [Kelebihan 2]
- **Kekurangan:**
  - [Kekurangan 1]
  - [Kekurangan 2]
- **Teknik Andalan Khas:**
  - [Teknik 1 — nama & efek singkat]
  - [Teknik 2]
- **Wilayah Paling Cocok:** [Wilayah dengan Qi Density sesuai]
- **Pengguna Terkenal:** [NPC yang menggunakan Hukum ini, jika ada]
- **Trigger untuk AI GM:**
  - Jika pemain menggunakan Hukum ini, pastikan [efek khas] terjadi.
  - Jika pemain bertemu pengguna Hukum ini, NPC memiliki [sifat khas/teknik andalan].

---

### LAW-002: [Nama Hukum]
- **Jenis:** [Dao Abadi / Raga Sejati / Gu Karma / Qi Naga Api / Roh Hantu / Kustom Lainnya]
- **Asal Usul:** [Admin / Nama Pemain]
- **Deskripsi Singkat:**
  [Penjelasan]
- **Afinitas Elemen:** [Elemen]
- **Qi Cap Modifier:** [×1,0 dst]
- **Kelebihan:**
  - [Kelebihan 1]
- **Kekurangan:**
  - [Kekurangan 1]
- **Teknik Andalan Khas:**
  - [Teknik 1]
- **Wilayah Paling Cocok:** [Wilayah]
- **Pengguna Terkenal:** [NPC]
- **Trigger untuk AI GM:**
  - [Trigger 1]

---

## 📝 Template Kosong untuk Admin

Salin template di bawah ini untuk menambahkan Hukum baru:

```markdown
### LAW-XXX: [Nama Hukum]
- **Jenis:** [Dao Abadi / Raga Sejati / Gu Karma / Qi Naga Api / Roh Hantu / Kustom Lainnya]
- **Asal Usul:** [Admin / Nama Pemain]
- **Deskripsi Singkat:**
  [Tulis deskripsi di sini]
- **Afinitas Elemen:** [Elemen]
- **Qi Cap Modifier:** [×1,0 dst]
- **Kelebihan:**
  - [Kelebihan 1]
  - [Kelebihan 2]
- **Kekurangan:**
  - [Kekurangan 1]
  - [Kekurangan 2]
- **Teknik Andalan Khas:**
  - [Teknik 1 — nama & efek]
  - [Teknik 2]
- **Wilayah Paling Cocok:** [Wilayah]
- **Pengguna Terkenal:** [Nama NPC]
- **Trigger untuk AI GM:**
  - [Trigger 1]
  - [Trigger 2]
