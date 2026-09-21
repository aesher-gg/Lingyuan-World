# 💰 Lingyuan World — Sistem Ekonomi Jianghu (Economy & Pricing System)

> **Modul:** 10 — Economy System
> **Prinsip:** Anti-Cheat Enforced — Supply-Demand Driven — Terintegrasi dengan Sistem Hukum Kultivasi & World Document
> **Rujukan silang:** `09_CULTIVATION_LAW_SYSTEM.md` (Tier material breakthrough), `01_WORLD_OVERVIEW_AND_CAPITAL.md` (jarak antar wilayah untuk Region Scarcity), `38_GARDENING_SYSTEM.md` (Output Instance & provenance hasil Gardening), file regional `02`–`07` (kekayaan per wilayah)

---

## 0. Filosofi Sistem

Sama seperti Qi tunduk pada `QiCap` formula, setiap harga di dunia ini — barang, jasa, aset — tunduk pada satu **Formula Harga Dasar** yang sama, supaya tidak ada barang yang harganya "dikarang" sepihak oleh player maupun NPC secara sembarangan. AI GM WAJIB menghitung harga lewat formula di bawah ini, bukan menerima klaim harga dari player ("aku jual pil ini seharga 10 Giok" tanpa dasar perhitungan = DITOLAK).

### Aturan Emas Anti-Cheat Ekonomi
- Harga TIDAK BOLEH dideklarasikan sepihak oleh player — semua harga dihitung AI GM lewat formula, bukan permintaan naratif.
- Setiap barang bernilai (Tier 3+ atau Grade Xuan ke atas) WAJIB punya **Item Origin Log** — asal-usul tervalidasi. Tanpa origin, barang tidak bisa dijual/ditukar/dipakai breakthrough.
- Tidak ada retroactive price edit — semua transaksi bertimestamp, tidak bisa diubah mundur setelah disepakati.
- Stok toko/NPC terbatas sesuai kapasitas produksi wilayah — tidak bisa membeli borongan barang Tier tinggi tanpa alasan naratif kuat.
- Tawar-menawar dibatasi ±15% dari harga hasil formula, tidak bisa lebih meski roleplay meyakinkan.
- Fluktuasi harga akibat supply-demand dibatasi hard cap 0,2×–5,0× dari Grade Value dasar.

---

## 1. Mata Uang (Currency)

| Tingkat | Nama | Nilai Tukar | Kegunaan |
|---|---|---|---|
| 1 | Tael Tembaga (铜两) | 1 (satuan dasar) | Transaksi harian rakyat jelata, makanan, penginapan murah |
| 2 | Tael Perak (银两) | 100 Tael Tembaga | Transaksi umum kota, upah jasa, senjata biasa |
| 3 | Tael Emas (金两) | 100 Tael Perak (10.000 Tembaga) | Transaksi besar, pil kultivasi, senjata sekte |
| 4 | Giok Kecil (小灵石) | 1.000 Tael Emas | Transaksi kultivator, bahan terobosan Tier 5+ |
| 5 | Giok Menengah (中灵石) | 100 Giok Kecil | Transaksi sekte besar, aset properti besar |
| 6 | Giok Purba (古灵石) | 100 Giok Menengah | Transaksi tingkat kekaisaran/sekte elite, sangat langka |

**Mata uang internal non-tradeable:** Poin Kontribusi Sekte (贡献点) — hanya berlaku di dalam satu sekte, dipakai menukar manual/pil/hak akses ruang latihan, **TIDAK BISA** ditukar ke Tael dalam bentuk apapun (mencegah exploit "cuci uang" lintas sekte).

---

## 2. Struktur Tier & Grade Barang (Anti-Cheat Item Ceiling)

### 2.1 Tier Barang (selaras Tier Material Sistem Hukum Kultivasi, lihat `09_CULTIVATION_LAW_SYSTEM.md` §4)

| Tier | TierBase (Tael Tembaga) | Konversi Praktis | Contoh Barang |
|---|---|---|---|
| 1 | 5 | 5 Tael Tembaga | Ramuan herbal biasa, senjata besi desa |
| 2 | 50 | 50 Tael Tembaga | Pil pemulih qi ringan, senjata pandai besi |
| 3 | 500 | 5 Tael Perak | Pil penyembuh luka dalam, pedang bermutu |
| 4 | 5.000 | 50 Tael Perak | Pil terobosan Foundation, senjata bertuah ringan |
| 5 | 50.000 | 5 Tael Emas | Pil terobosan Core Formation, pusaka bertuah |
| 6 | 500.000 | 50 Tael Emas | Pil terobosan Nascent Soul, senjata pusaka sekte |
| 7 | 5.000.000 | 0,5 Giok Kecil | Pil terobosan Void Severing, pusaka legendaris |
| 8 | 50.000.000 | 5 Giok Kecil | Bahan Tribulasi Realm 8, pusaka mitos |
| 9 | 500.000.000 | 50 Giok Kecil | Bahan Realm 9, artefak tingkat dewa |

```
TierBase(n) = 5 × 10^(n−1) Tael Tembaga
```

📌 Anti-cheat: barang Tier-9 tidak bisa muncul di toko biasa manapun — hanya lewat quest/warisan/reruntuhan bersejarah (§9.3).

### 2.2 Grade Kualitas (Quality Grade, berlaku lintas Tier)

| Grade | Nama | Multiplier | Catatan |
|---|---|---|---|
| 1 | Fan-Grade (凡品) | ×0,5 | Kualitas mortal/kasar, buatan tangan amatir |
| 2 | Huang-Grade (黄品) | ×1,0 | Standar baseline, kualitas perguruan/pandai besi biasa |
| 3 | Xuan-Grade (玄品) | ×2,5 | Kualitas sekte menengah, ada sentuhan formasi |
| 4 | Di-Grade (地品) | ×6,0 | Kualitas sekte besar, bahan langka terpakai |
| 5 | Tian-Grade (天品) | ×15,0 | Kualitas tetua/pusaka sekte, jarang diperjualbelikan |
| 6 | Sheng-Grade (聖品) | ×40,0 | Tingkat legendaris/warisan kuno, hampir tak pernah dijual bebas |

```
GradeValue(tier, grade) = TierBase(tier) × GradeMultiplier(grade)
```

---

## 3. Formula Suplai & Permintaan (Supply-Demand Formula)

```
FinalPrice = GradeValue(tier, grade) × RegionScarcity × DemandIndex × EventModifier × ConditionModifier
FinalPrice = clamp(hasil di atas, 0,2 × GradeValue, 5,0 × GradeValue)
```

### 3.1 Region Scarcity (Kelangkaan Regional)

| Kondisi | RegionScarcity |
|---|---|
| Dijual di wilayah asal/produksi barang (native region) | ×0,6 |
| Dijual di wilayah tetangga langsung (perbatasan, ≤1.500 li) | ×1,5 |
| Dijual di wilayah jauh (>1.500 li, sesuai Peta Jarak `01_WORLD_OVERVIEW_AND_CAPITAL.md`) | ×3,0 |
| Barang dari zona sangat langka (Immortal Peach Island, Hellfire Island, reruntuhan kuno, dsb) | ×5,0 (minimum) |

### 3.2 Demand Index (Indeks Permintaan)

```
Jika `ActiveSupply = 0`, rumus DemandIndex tidak boleh dihitung karena pembagian dengan nol. Dalam kondisi ini, DemandIndex = `??? / UNRESOLVED` sampai ada ActiveSupply tervalidasi atau aturan pasar khusus yang canon.

Jika `ActiveSupply > 0`, gunakan:

```text
DemandIndex = clamp(0,5 + (ActiveBuyOrders − ActiveSupply) / ActiveSupply × 0,5, 0,5, 3,0)
```

`ActiveBuyOrders` dan `ActiveSupply` ditentukan AI GM dari kondisi naratif pasar
```

`ActiveBuyOrders` dan `ActiveSupply` ditentukan AI GM dari kondisi naratif pasar (wabah penyakit menaikkan permintaan pil, musim turnamen menaikkan permintaan senjata, dll) — tidak bisa diklaim sepihak oleh player.

### 3.3 Event Modifier (Modifier Peristiwa Sementara)

Ditentukan AI GM berdasarkan kejadian besar di cerita: perang (×2,0 kelangkaan senjata/obat), festival damai (×0,8 diskon umum), lelang rahasia sekte (×3,0 untuk barang yang dilelang), bencana alam (×2,5 kebutuhan pokok). Modifier ini bersifat sementara dan harus dicatat GM sebagai event log dengan durasi jelas.

### 3.4 Condition Modifier (Kondisi Fisik Barang)

Rusak/using: ×0,7 | Standar: ×1,0 | Kondisi prima: ×1,1 | Bersejarah/antik terverifikasi: ×1,5

### 📌 Contoh Perhitungan Lengkap

Pil Penyembuh Luka Dalam (Tier 3, Grade Xuan) diproduksi Balai Yunyao (Beiyuan), dijual di Kota Haoyang (Tianzhou, >1.500 li dari sumber):

```
GradeValue      = TierBase(3) × 2,5 = 500 × 2,5 = 1.250 Tael Tembaga (12,5 Tael Perak)
RegionScarcity  = ×3,0 (wilayah jauh)
DemandIndex     = 1,2 (permintaan sedikit tinggi, wabah kecil di kota)
EventModifier   = 1,0 (tidak ada event khusus)
ConditionModifier = 1,0 (standar)
FinalPrice      = 12,5 × 3,0 × 1,2 × 1,0 × 1,0 = 45 Tael Perak
```

Cek batas: harus dalam rentang [2,5 – 62,5 Tael Perak] → 45 Tael Perak **VALID**, tidak perlu clamp.

---

## 4. Harga Jasa (Service Pricing)

### 4.1 Jasa Pengobatan (Tabib)

```
HealingFee = InjurySeverityBase × TabibRealmMultiplier
```

| Tingkat Luka | InjurySeverityBase |
|---|---|
| Luka ringan | 10–50 Tael Perak |
| Luka sedang | 100–500 Tael Perak |
| Luka berat/nyaris mati | 1.000–5.000 Tael Emas |
| Perbaikan Qi Deviation permanen | 5–50 Giok Kecil (hanya tabib Nascent Soul+) |

TabibRealmMultiplier: Foundation Establishment ×1,0 | Nascent Soul ×0,8 (lebih efisien) | Soul Transformation+ ×0,6 (jarang mau menerima kecuali kasus istimewa).

### 4.2 Jasa Pengawalan (Biro Pengawalan Wan'an, dsb)

```
EscortFee = (CargoValue × 5%) + (Jarak_li ÷ 100 × 5 Tael Perak) × RiskMultiplier
```

RiskMultiplier: Rute aman (dalam Tianzhou) ×1,0 | Rute rawan bandit ×2,5 | Rute zona perang (mis. Lembah Tianlie) ×5,0

### 4.3 Jasa Informasi (Paviliun Wanxin)

| Tingkat Info | Harga |
|---|---|
| Kabar umum/gosip | 5–20 Tael Perak |
| Info sekte (kekuatan, rahasia internal) | 100–500 Tael Perak |
| Info kelas atas (harta karun, secret realm) | 1.000+ Tael Emas |
| Info "Kelas Langit" (rahasia kaisar/sekte besar) | Lelang rahasia, minimum 10 Giok Kecil |

### 4.4 Kontrak Pembunuhan (Aliansi Anying / Perkumpulan Wuying)

```
ContractFee = (TargetQiCap × 0,001 Tael Tembaga) + DifficultyBonus
```

`TargetQiCap` diambil dari `QiCap(realm, stage)` target sesuai `09_CULTIVATION_LAW_SYSTEM.md`. DifficultyBonus ditentukan AI GM dari tingkat penjagaan target (tanpa pengawalan +0, dijaga sekte besar +500 Tael Emas hingga +50 Giok Kecil). Floor minimum kontrak: 50 Tael Perak.

### 4.5 Iuran Sekte (Poin Kontribusi, bukan Tael)

```
SectDues = MemberRealmTier × BaseDuesRate(sekte)
```

Dibayar dalam Poin Kontribusi Sekte, bukan Tael — tidak bisa dikonversi ke mata uang umum.

### 4.6 Instalasi Formasi (Pemasangan Array Pelindung/Serangan)

```
FormationCost = FormationTier × TierBase(materialTier) × ArtisanSkillMultiplier
```

ArtisanSkillMultiplier: pengrajin perguruan kecil ×1,0 | pengrajin sekte menengah ×2,0 | pengrajin sekte besar/tetua ×5,0

---

## 5. Harga Aset (Property & Asset Pricing)

| Jenis Aset | Kisaran Harga |
|---|---|
| Rumah/lahan pedesaan | 20–100 Tael Perak |
| Toko kota kecil | 500–5.000 Tael Perak |
| Toko/paviliun kota besar (lokasi strategis) | 1–10 Tael Emas |
| Pendirian perguruan kecil (minimum viable) | 500 Tael Emas + izin lahan otoritas lokal |
| Estate sekte menengah (skala Sekte Yunjian) | 50.000+ Tael Emas, minimum pendiri Nascent Soul |
| Perahu nelayan | 50–200 Tael Perak |
| Kapal dagang | 5–50 Tael Emas |
| Kapal perang/kapal bajak bendera | 200–2.000 Tael Emas |

📌 Anti-cheat: pembelian aset besar (perguruan ke atas) WAJIB melalui proses naratif (negosiasi dengan otoritas lokal), bukan transaksi instan sekali klik.

---

## 6. Tawar-Menawar (Haggling) & Batas Fluktuasi

Player boleh menawar hasil `FinalPrice` lewat roleplay, TAPI dibatasi maksimum, tergantung sifat NPC penjual:

| Sifat NPC | Rentang Tawar yang Diizinkan |
|---|---|
| NPC "genit dan lihai menawar" / ramah dalam negosiasi | ±20% |
| NPC standar/netral | ±15% (default) |
| NPC "keras kepala soal angka" / kaku | ±5% |
| NPC tak bisa ditawar (formasi kuno, harga tetap resmi kekaisaran) | 0% (harga mati) |

Haggling sukses ditentukan AI GM dari kualitas roleplay tawar-menawar player, bukan otomatis diberikan.

---

### 6.1 Timed Processing untuk Barang & Jasa

Setiap barang atau jasa yang secara sah memerlukan proses dengan durasi dunia tertentu wajib mengikuti **Timed Processing** pada 00_CORE_RULES_AI_GM.md §1.10.

- Item/material yang sedang dikerjakan memiliki status runtime PROCESSING dan belum menjadi output final.
- StartTime, RequiredDuration, dan CompletionTime harus dapat ditelusuri.
- Sebelum CompletionTime, output tidak boleh dijual, dipakai, dipindahkan sebagai hasil selesai, atau dianggap telah terpasang/terupgrade.
- Setelah CompletionTime, AI GM melakukan completion validation sebelum mengubah status menjadi COMPLETED.
- Menunggu di narasi, pergantian turn, atau jumlah pesan tidak boleh menggantikan elapsed World Time.
- Jika durasi proses, hasil, atau status tidak memiliki basis canon yang cukup, gunakan ??? / UNRESOLVED.

Aturan ini mencakup proses pandai besi, crafting, alchemy, produksi NPC, repair/upgrade equipment, dan jasa lain yang menghasilkan perubahan pada item atau output bernilai ekonomi. Modul ini tidak menciptakan recipe atau durasi baru; ia hanya memastikan proses yang memang ada dicatat secara temporal.

## 7. Sistem Anti-Cheat: Item Origin Log & Ledger

> **Item Instance Boundary:** Nama/tipe item, Tier/Grade, dan Item Instance adalah atribut berbeda. Nama item tidak otomatis berarti satu instance tertentu. Acquisition atau processing yang sah harus menunjuk instance/output yang dapat dilacak; quantity hanya boleh bertambah melalui acquisition/output yang tervalidasi.

Sama seperti Law Origin Log di sistem kultivasi, tiap barang bernilai (Tier 3+ atau Grade Xuan+) WAJIB punya asal-usul tervalidasi sebelum bisa dijual, ditukar, atau dipakai breakthrough:

| Jalur Asal-Usul yang Sah | Syarat Sah |
|---|---|
| 1. Pembelian | Tercatat di Ledger Transaksi GM (harga, penjual, waktu) saat pertama dibeli |
| 2. Hadiah Quest | Diberikan GM sebagai hasil quest naratif, dicatat sumber & alasannya |
| 3. Loot Pertarungan | Hasil sah dari pertarungan yang benar-benar terjadi di roleplay |
| 4. Hasil Crafting | Dibuat dari bahan yang sudah tercatat asal-usulnya |
| 5. Hasil Gardening | Berasal dari Output Instance hasil panen Plant Instance yang provenance-nya tervalidasi |

**Aturan Pengikat:**
- Barang tanpa Item Origin Log tidak bisa dijual, ditukar, atau dipakai bahan breakthrough — otomatis DITOLAK.
- Barang unik tidak bisa "muncul dua kali" — sekali terjual/dipakai, statusnya berubah permanen di ledger.
- Semua transaksi bertimestamp, tidak bisa diedit mundur oleh player.
- Stok toko/NPC dibatasi kapasitas produksi wilayah — NPC tidak bisa tiba-tiba punya stok tak terbatas barang Tier tinggi.

---

## 8. Checklist Validasi AI GM (Wajib Dicek Setiap Transaksi)

- [ ] Harga dihitung lewat formula `FinalPrice` (bukan klaim sepihak player)?
- [ ] Item Origin Log barang yang diperjualbelikan sudah tervalidasi?
- [ ] Region Scarcity dihitung sesuai jarak wilayah di World Document?
- [ ] Demand Index berdasarkan kondisi naratif tervalidasi GM, bukan klaim player?
- [ ] Harga akhir berada dalam batas clamp 0,2×–5,0× Grade Value?
- [ ] Tawar-menawar tidak melebihi batas sifat NPC?
- [ ] Konversi mata uang memakai nilai tukar resmi?
- [ ] Transaksi tercatat di ledger dengan timestamp, tidak diubah mundur?
- [ ] Stok barang Tier tinggi tidak melebihi kapasitas produksi wilayah?

Jika salah satu poin gagal → transaksi DITOLAK, AI GM memberi alasan spesifik ke player.

---

## 9. Integrasi dengan World Document (Kekayaan Regional & Pasar)

### 9.1 Batas Volume Transaksi per Wilayah

| Wilayah | Kekayaan Regional | Implikasi Soft-Cap |
|---|---|---|
| Tianzhou | ± 950 juta Tael | Volume transaksi besar dimungkinkan, pasar paling likuid |
| Moyuan | ± 260 juta Tael | Transaksi menengah, banyak barang gelap/ilegal |
| Haiyuan | ± 410 juta Tael | Likuiditas tinggi lewat perdagangan laut |
| Beiyuan | ± 190 juta Tael | Ekonomi kecil, barang impor jauh lebih mahal |
| Xisha | ± 150 juta Tael | Ekonomi terkecil, rawan monopoli lokal |
| Qingyun | ± 140 juta Tael | Ekonomi kecil tapi stabil, kerajinan bernilai tinggi |

### 9.2 Pasar Khusus (Pengecualian Region Scarcity)

- **Floating Cloud Archipelago** — Region Scarcity hanya ×1,0–1,5 terlepas dari jarak asal barang, karena statusnya pasar netral.
- **Kota Jinsha / Konsorsium Kafilah Jinsha** — barang impor lintas gurun kena markup tambahan ×1,3 di atas RegionScarcity normal.
- **Reruntuhan Gushatta / Menara Bintang Jatuh** — barang antik/artefak kuno pakai lelang naratif, minimum RegionScarcity ×5,0.


### 9.4 Regional Supply dari Gardening

Hasil Gardening hanya menjadi bagian dari ActiveSupply jika Output Instance benar-benar dialokasikan ke pasar melalui tindakan/transaksi yang sah.

Gardening supply flow:

Harvested Output Instance → Allocation / Sale → Regional Supply → ActiveSupply → DemandIndex → FinalPrice

- Kebun yang ada tetapi belum menghasilkan panen tidak menambah supply.
- Panen yang disimpan untuk konsumsi internal, riset, alchemy, crafting, hadiah, atau inventory tidak otomatis dihitung sebagai ActiveSupply.
- Stok NPC/sekte tidak boleh dianggap tak terbatas hanya karena fasilitas produksi mereka besar atau terkenal.
- Jika kapasitas produksi atau volume output regional belum memiliki basis canon/runtime, nilainya tidak boleh diarang dan harus diperlakukan sebagai `???` / `UNRESOLVED`.
- Gardening tidak membuat formula harga baru; setelah output sah masuk pasar, harga tetap memakai `FinalPrice` pada §3.

### 9.3 Sumber Barang Tier Tinggi

Barang Tier 7+ hanya bisa didapat lewat quest/reruntuhan/warisan sekte di lokasi spesifik (Hellfire Island, Reruntuhan Gushatta, Menara Bintang Jatuh, dsb) — tidak muncul di toko biasa manapun.
