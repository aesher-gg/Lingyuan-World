# 📜 Lingyuan World — Sistem Misi Bounty & Rumah Lelang (Bounty Mission & Auction System)

> **Modul:** 47 — Bounty Mission & Auction System
> **Status:** Canonical System
> **Prinsip:** Source-Traceable — Time-Bound — Anti-Cheat — Hardcore Realism
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` (aturan inti & batas waktu), `08_CROSS_REGION_ORGANIZATIONS.md` (Paviliun Wanxin, Rumah Gadai Hanbi, Perhimpunan Youyi), `10_ECONOMY_SYSTEM.md` (Mata uang, Tier/Grade, harga & komisi), `players/` (official save dikelola Admin)

---

## 0. Filosofi Sistem Misi & Lelang

Di dunia Lingyuan World, ekonomi dan reputasi kultivator digerakkan oleh dua institusi vital:

1. **Papan Misi Bounty (Bounty Mission Boards / Ling-Xhang):** Tempat kekaisaran, sekte, pedagang, atau individu memajang tugas berbahaya (berburu monster, mengawal karavan, membunuh buronan, mencari herba langka) dengan imbalan Tael atau Batu Spirit.
2. **Rumah Lelang (Auction Houses / Pai-Mai Hang):** Tempat barang-barang paling langka di dunia (senjata pusaka, teknik kuno, pil Flawless, telur spirit beast) dijual kepada penawar tertinggi melalui mekanisme persaingan harga yang ketat.

---

## 1. Sistem Papan Misi Bounty (Bounty Boards)

Papan misi dapat ditemukan di setiap kota besar (`01`–`07`), Paviliun Wanxin (`35`), Perhimpunan Youyi (`37`), atau aula sekte besar.

### 1.1 Klasifikasi Grade Misi Bounty

| Grade Misi | Rekomendasi Realm | Jenis Tugas Umum | Hadiah Imbalan Standar | Potensi Bahaya & Risiko |
|---|---|---|---|---|
| **Grade D (Mortal)** | Realm 1 (Mortal Foundation) | Pengawalan barang, pembasmi binatang pengganggu, pencarian bahan biasa | 10–50 Tael Perak | Rendah |
| **Grade C (Refining)** | Realm 2 (Qi Refining) | Perburuan monster Tier 1, pembersihan bandit jalanan, pengumpulan herba spirit | 1–5 Tael Emas | Sedang |
| **Grade B (Establishment)** | Realm 3 (Foundation Est.) | Pembunuhan buronan sekte demonic, eksplorasi reruntuhan berbahaya, herba Tier 2 | 20–50 Tael Emas / 1 Giok Kecil | Tinggi |
| **Grade A (Core Formation)** | Realm 4 (Core Formation) | Perburuan Beast King Tier 3, pengawalan artefak bumi, konflik sekte | 5–20 Giok Kecil | Sangat Tinggi |
| **Grade S (Nascent & Above)** | Realm 5+ (Nascent Soul+) | Ekspedisi zona terlarang, perburuan iblis tua, materi Tier 4 | 50+ Giok Menengah / Pusaka Spirit | Mematikan |

### 1.2 Alur Pengambilan & Penyelesaian Misi

```
[1. Melihat Papan Misi] ➔ [2. Registrasi & Deposit Jaminan] ➔ [3. Pelaksanaan Tugas (Timed Processing)] ➔ [4. Penyerahan Bukti (Loot/Kepala/Barang)] ➔ [5. Verifikasi & Klaim Imbalan]
```

1. **Deposit Jaminan (Mission Deposit):** Mengambil misi Grade B ke atas membutuhkan uang jaminan sebesar 10% dari imbalan misi untuk mencegah pembatalan sepihak/penipuan.
2. **Batas Waktu Misi:** Setiap misi memiliki durasi aktif in-game (misal: 3 hari). Jika dilewati tanpa penyelesaian, misi dinyatakan gagal, jaminan hangus, dan Reputasi (`Karma / Fame`) berkurang.
3. **Verifikasi Bukti:** Pembunuhan buronan butuh token/kepala buronan; perburuan monster butuh bagian tubuh spesifik (`13_BESTIARY.md`).

---

## 2. Sistem Rumah Lelang (Auction House System)

Rumah lelang terbesar dikelola oleh faksi netral/kekaisaran seperti **Paviliun Wanxin** (`35_PAVILIUN_WANXIN.md`) dan **Rumah Gadai Hanbi** (`36_RUMAH_GADAI_HANBI.md`).

### 2.1 Alur Penjualan Barang via Lelang (Consignment)

1. **Pemeriksaan & Penilaian Barang (Item Appraisal):**
   - Juru taksir (*Appraiser*) memeriksa keaslian, Tier, dan Provenance barang (`10_ECONOMY_SYSTEM.md`).
   - Barang tanpa provenance yang jelas atau barang curian berisiko ditolak atau dijual di Pasar Gelap (*Black Market*) dengan komisi lebih tinggi.
2. **Penetapan Harga Awal (Starting Price):**
   - Harga awal ditetapkan sebesar 50% dari estimasi Harga Pasar Standar.
3. **Komisi Rumah Lelang (Auction Fee):**
   - Rumah Lelang mengambil komisi sebesar **10% dari harga penawaran akhir**.

---

## 3. Mekanik Penawaran Lelang (Bidding Mechanics)

Saat karakter mengikuti lelang (sebagai pembeli atau penjual), AI GM memandu jalannya lelang menggunakan simulasi penawar NPC:

### 3.1 Aturan Penawaran
- **Kenaikan Minimal (Minimum Increment):**
  - Untuk transaksi Tael Emas: Minimal kenaikan 1 Tael Emas.
  - Untuk transaksi Giok Kecil: Minimal kenaikan 1 Giok Kecil.
- **Tipe Penawar NPC:**
  - **Kultivator Kaya Sekte Ortodoks:** Menawar dengan tenang sampai harga standar +50%.
  - **Tetua Faksi Demonic / Kriminal:** Menawar dengan agresif, kadang mencoba mengintimidasi penawar lain.
  - **Saudagar / Info Broker:** Menawar hanya untuk dijual kembali, berhenti jika harga terlalu mahal.

### 3.2 Simulasi Putaran Lelang (Bidding Rounds)

Setiap barang lelang disimulasikan dalam 3 putaran penawaran:

```
[Putaran 1: Harga Awal dibuka] ➔ [Putaran 2: Persaingan Penawar NPC/Player] ➔ [Putaran 3: Penawaran Tertinggi Ketiga (Ketukan Palu - Sold!)]
```

If player menawar:
- Pemain harus memastikan saldo mata uangnya cukup di Profil Karakter.
- Pemain bisa mencoba melakukan *Intimidation Check / Fame Check* untuk menakut-nakuti penawar NPC agar mundur dari lelang.

---

## 4. Contoh Katalis Barang Lelang Kanon

1. **Buat Spirit Jiwa Purba (Tier 3 Herbal - `38`):**
   - Harga Awal: 3 Giok Kecil | Est. Harga Akhir: 8–12 Giok Kecil.
2. **Resep Pil Pembentuk Fondasi (Tier 2 Alchemy - `43`):**
   - Harga Awal: 20 Tael Emas | Est. Harga Akhir: 60–100 Tael Emas.
3. **Senjata Pusaka Pedang Bintang Es (Tier 3 Forging - `44`):**
   - Harga Awal: 5 Giok Kecil | Est. Harga Akhir: 15–20 Giok Kecil.
4. **Telur Spirit Beast Elang Petir (Tier 3 Beast Egg - `46`):**
   - Harga Awal: 2 Giok Kecil | Est. Harga Akhir: 6–10 Giok Kecil.

---

## 5. Status Modul

**CANONICAL — SYSTEM MODULE**
Seluruh aturan papan misi, mekanisme lelang, komisi, dan simulasi penawaran di atas adalah aturan resmi Lingyuan World.
