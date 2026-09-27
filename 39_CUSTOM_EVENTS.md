# 🎭 Lingyuan World — Event Khusus & Peristiwa Dunia

> **Modul:** 39 — Custom Events
> **Fungsi:** Tempat Admin mencatat event-event khusus yang terjadi di dunia, baik yang sedang berlangsung, mendatang, maupun yang telah berlalu.
> **Pengelolaan:** Admin (pemilik repo) mengelola file ini. AI GM WAJIB membaca bagian EVENT AKTIF sebelum memulai setiap sesi.
> **Rujukan silang:** `01`–`08` (lokasi event), `10` (ekonomi), `13` (bestiary), `43`–`47` (sistem mekanik)

---

## 📋 Cara Menggunakan File Ini

1. **Event Aktif** adalah event yang sedang berlangsung atau akan segera terjadi. AI GM WAJIB memasukkan event ini ke dalam narasi.
2. **Event Selesai** adalah event yang sudah berlalu. AI GM bisa merujuknya sebagai sejarah/latar belakang.
3. **Event Mendatang** adalah event yang sudah dijadwalkan tapi belum terjadi. AI GM bisa memberi "firasat" atau "desas-desus" tentang event ini.
4. Setiap event diberi **ID unik** (misal: `EVT-001`) agar mudah dirujuk.

---

## 🔴 EVENT AKTIF (Sedang Berlangsung)

### EVT-001: Fenomena Kemunculan Makam Kuno Hutan Lingzhu
- **Status:** 🔴 AKTIF
- **Lokasi:** Hutan Lingzhu, Qingyun (200 li dari Kota Yinfeng)
- **Tanggal Mulai:** Tahun 1024, Musim Semi, Tanggal 01 Bulan 03
- **Tanggal Berakhir:** Tahun 1024, Musim Panas, Tanggal 01 Bulan 06
- **Deskripsi Singkat:**
  Gempa bumi dahsyat mengungkapkan reruntuhan Istana Pedang Kuno yang tersembunyi di bawah dasar Hutan Lingzhu. Cahaya Qi berwarna hijau zamrud terpancar ke langit setiap tengah malam. Berbagai faksi dari sekte ortodoks maupun demonic mulai berdatangan menuju Hutan Lingzhu untuk memperebutkan Warisan Pedang Purba (*Ancient Sword Inheritance*).
- **Dampak ke Dunia:**
  - Harga jimat penyembuhan, pil pemulihan Qi (`43`), dan senjata besi spirit (`44`) di Kota Yinfeng naik sebesar +30%.
  - Kepadatan monster spirit beast di Hutan Lingzhu meningkat, monster menjadi lebih agresif (`13_BESTIARY.md`).
  - Patroli Sekte Yunjian dan pembunuh bayaran Aliansi Anying terlihat berkeliaran di sekitar lokasi.
- **NPC Terkait:**
  - Tetua Xu dari Sekte Yunjian (`16_SEKTE_YUNJIAN.md`).
  - Bayangan Merah (Informan Paviliun Wanxin, `35_PAVILIUN_WANXIN.md`).
- **Hadiah/Bonus untuk Pemain:**
  - Peluang menemukan Artefak Pedang Spirit Tier 3 (`44`) dan Manuskrip Jurus Kustom Purba.
- **Trigger untuk AI GM:**
  - Jika pemain berada di Qingyun / Hutan Lingzhu / Kota Yinfeng, sampaikan desas-desus tentang fenomena cahaya zamrud di langit malam dan keramaian kultivator yang berbondong-bondong membawa senjata.
  - Jika pemain bertarung di Hutan Lingzhu, tingkatkan *AmbushChance* sebesar +10%.

---

### EVT-002: Pelelangan Besar Pusaka Laut Timur
- **Status:** 🔴 AKTIF
- **Lokasi:** Paviliun Wanxin Branch Kota Haizhen, Haiyuan
- **Tanggal Mulai:** Tahun 1024, Musim Semi, Tanggal 15 Bulan 03
- **Tanggal Berakhir:** Tahun 1024, Musim Semi, Tanggal 20 Bulan 03
- **Deskripsi Singkat:**
  Paviliun Wanxin menggelar lelang akbar 5 tahunan di Haiyuan. Barang-barang langka yang dilelang termasuk Telur Beast Naga Laut Tier 3 (`46`), Resep Pil Pembentuk Fondasi Flawless (`43`), dan Logam Emas Purba Xuanjin (`44`).
- **Dampak ke Dunia:**
  - Banyak kultivator kaya dan perwakilan sekte besar berkumpul di Kota Haizhen.
  - Kamar penginapan di Kota Haizhen penuh, harga sewa naik 100%.
- **Trigger untuk AI GM:**
  - Jika pemain berada di Haiyuan, berikan brosur lelang dari Paviliun Wanxin atau ajakan ikut serta dalam pelelangan (`47_BOUNTY_AUCTION_SYSTEM.md`).

---

## 🟡 EVENT MENDAFTAR (Belum Terjadi)

### EVT-003: Fenomena Pasang Petir Tribulasi Lembah Tianlie
- **Status:** 🟡 MENDAFTAR
- **Lokasi:** Lembah Tianlie (Perbatasan Tianzhou–Moyuan)
- **Tanggal Mulai:** Tahun 1024, Musim Gugur, Tanggal 01 Bulan 09
- **Deskripsi Singkat:**
  Prakiraan astronomi menunjukkan alignment bintang yang memicu badai petir purba di Lembah Tianlie. Energi Qi Atribut Petir murni akan melonjak 500% di lokasi tersebut.
- **Pertanda/Firasat:**
  - Langit di perbatasan Tianzhou–Moyuan sering berkilat jingga walau tanpa hujan.
  - Kultivator elemen petir merasakan kehangatan di meridian mereka.
- **Trigger untuk AI GM:**
  - Sampaikan kabar desas-desus bahwa para ahli Formasi Array (`45`) dan penempa senjata (`44`) sedang menuju Lembah Tianlie untuk memanen *Batu Petir Murni*.

---

## ⚪ EVENT SELESAI (Sudah Berlalu)

### EVT-000: Pemberontakan Bandit Lembah Heifeng
- **Status:** ⚪ SELESAI
- **Lokasi:** Desa Luoye & Lembah Heifeng, Tianzhou
- **Tanggal:** Tahun 1023, Musim Dingin
- **Deskripsi:**
  Kumpulan bandit Heifeng dikalahkan oleh gabungan pasukan Perguruan Luohua dan kultivator pengembara.
- **Dampak yang Tersisa:**
  - Jalur perdagangan Desa Luoye menuju Tianjing kembali aman.
  - Sisa-sisa bandit melarikan diri menjadi buronan papan misi Grade C (`47`).
