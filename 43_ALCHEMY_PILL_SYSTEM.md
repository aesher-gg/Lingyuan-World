# ⚗️ Lingyuan World — Sistem Alkemia & Pembuatan Pil Lingdan

> **Modul:** 43 — Alchemy & Pill System
> **Status:** Canonical System
> **Prinsip:** Source-Traceable — Time-Bound — Anti-Cheat — Hardcore Realism
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` (aturan inti, batas waktu, timed processing §1.10), `09_CULTIVATION_LAW_SYSTEM.md` (Realm, Qi, Qi Deviation), `10_ECONOMY_SYSTEM.md` (Tier/Grade, Provenance & harga), `11_VITALITY_HUNGER_SYSTEM.md` (Stamina, efek racun), `38_GARDENING_SYSTEM.md` (sumber bahan herbal), `players/` (official save dikelola Admin)

---

## 0. Filosofi Sistem Alkemia

Alkemia adalah seni menyuling esensi spiritual dari bahan-bahan alam (tanaman obat, bagian tubuh monster/spirit beast, kristal energi) dan memadatkannya menjadi **Pil Lingdan**. Di Lingyuan World, alkemia adalah jalur yang sangat dihormati namun dipenuhi risiko tinggi: kegagalan dapat menghancurkan bahan mahal, merusak tungku, atau memicu ledakan dahsyat (*Furnace Explosion*) yang mencederai pembuatnya.

### Aturan Emas Alkemia

1. **Bahan Berasal dari Sumber Sah (Provenance):** Semua herba/bahan yang digunakan WAJIB memiliki asal-usul yang tercatat (dari `38_GARDENING_SYSTEM.md`, hasil looting `13_BESTIARY.md`, atau pembelian `10_ECONOMY_SYSTEM.md`). Bahan yang tidak memiliki catatan provenance TIDAK BISA digunakan.
2. **Tidak Ada Pembuatan Instan:** Pembuatan pil membutuhkan waktu in-game nyata dan tunduk pada aturan **Timed Processing** (`00_CORE_RULES_AI_GM.md` §1.10) serta batas waktu aksi 3 jam (`00` §1.9).
3. **Risiko Dan-Du (Racun Pil / Pill Toxicity):** Mengonsumsi pil secara berlebihan menumpuk residu racun dalam tubuh (*Dan-Du*). Karakter yang mengonsumsi pil melampaui batas batas aman akan mengalami penurunan regenerasi Qi, penyumbatan meridian, atau bahkan Qi Deviation.
4. **Formula & Peluang Terukur:** Keberhasilan peracikan dihitung secara transparan berdasarkan Realm Pembuat, Tingkat Control Qi, Quality Tungku, dan Quality Bahan.
5. **Peringkat Pil (Tier & Grade):** Efek pil ditentukan secara ketat oleh Tier (Mortal, Earth, Heaven, Immortal) dan Quality Grade (Rendah, Menengah, Tinggi, Puncak, Flawless).

---

## 1. Komponen Utama Alkemia

### 1.1 Tungku Alkemia (Alchemy Furnace / Dan-Lu)

Tungku alkemia menentukan stabilitas panas dan daya tahan terhadap tekanan Qi selama peracikan.

| Tier Tungku | Nama / Jenis Tungku | Bonus Stabilitas | Durabilitas Maksimal | Batas Maksimal Tier Pil | Harga Pasar Est. |
|---|---|---|---|---|---|
| **Tier 1 (Mortal)** | Tungku Perunggu/Besi Biasa | +0% | 50 Poin | Tier 1 (Mortal) | 100 Tael Perak |
| **Tier 2 (Earth)** | Tungku Tembaga Spirit Ling | +10% | 150 Poin | Tier 2 (Earth) | 50 Tael Emas |
| **Tier 3 (Heaven)** | Tungku Besi Meteorik Spirit | +25% | 500 Poin | Tier 3 (Heaven) | 10 Giok Kecil |
| **Tier 4 (Immortal)**| Tungku Purba Api Suci | +45% | 2.000 Poin | Tier 4 (Immortal) | 100 Giok Menengah |

> **Pengurangan Durabilitas:** Setiap kali meracik pil, durabilitas tungku berkurang 2–10 poin. Jika durabilitas mencapai 0, tungku pecah dan tidak dapat digunakan.

### 1.2 Nyala Api Alkemia (Alchemy Flame)

Tipe api memengaruhi kecepatan peracikan dan bonus kemurnian pil:

1. **Api Mortal / Kayu Bakar Spirit (Mortal Flame):** Api standar dari bahan bakar kayu spirit. Tanpa bonus, hanya bisa meracik pil Tier 1–2.
2. **Api Qi Internal (True Qi Flame):** Dihasilkan dari Qi pembuat pil (butuh minimal Realm 3 Pembentukan Fondasi). +5% Success Rate, +5% Kemurnian.
3. **Api Spirit Alam / Api Purba (Heavenly / Earthly Beast Flame):** Api dari inti monster/spirit beast atau fenomena alam. +15% Success Rate, +15% Kemurnian, mampu meracik pil Tier 3–4.

---

## 2. Proses Peracikan Pil (Pill Refining Stages)

Proses pembuatan pil dibagi menjadi 4 tahap berurutan:

```
[1. Pembersihan & Ekstraksi Bahan] ➔ [2. Pengontrolan Api & Peleburan] ➔ [3. Pemadatan Inti Pil (Condensation)] ➔ [4. Pembentukan & Penyegelan (Pill Formation)]
```

### 2.1 Formula Keberhasilan Peracikan (Success Rate)

AI GM menghitung peluang sukses peracikan pil dengan rumus:

$$\text{SuccessRate} = 50\% + (\text{RealmIndex} \times 5\%) + \text{FurnaceBonus} + \text{FlameBonus} - (\text{PillTier} \times 15\%) + \text{SkillBonus}$$

- **RealmIndex:** 1 (Mortal Foundation), 2 (Qi Refining), 3 (Foundation Establishment), 4 (Core Formation), dst.
- **PillTier:** 1 (Mortal), 2 (Earth), 3 (Heaven), 4 (Immortal).
- **SkillBonus:** Bonus dari teknik alkemia khusus yang dikuasai (0% - 20%).
- **Batas Peluang:** Minimal 5%, Maksimal 95%.

### 2.2 Penentuan Quality Grade Hasil Pil

Jika peracikan berhasil, GM melakukan pengecekan Quality Grade berdasarkan sisa margin keberhasilan:

| Hasil D20 / Margin Roll | Quality Grade Pil | Kemanjuran Efek | Residu Dan-Du (Racun) |
|---|---|---|---|
| Margin 1–20% | **Low Grade (Kualitas Rendah)** | 70% Efek Standar | +10 Poin Dan-Du |
| Margin 21–50% | **Mid Grade (Kualitas Menengah)** | 100% Efek Standar | +5 Poin Dan-Du |
| Margin 51–80% | **High Grade (Kualitas Tinggi)** | 130% Efek Standar | +2 Poin Dan-Du |
| Margin 81–95% | **Peak Grade (Kualitas Puncak)** | 160% Efek Standar | +1 Poin Dan-Du |
| Roll Kritis (Natural 100 / Special Critical) | **Flawless Grade (Sempurna)** | 200% Efek Standar | **0 Poin Dan-Du** (Murni) |

---

## 3. Kegagalan & Risiko Meledaknya Tungku (Furnace Explosion)

Jika kalkulasi peracikan gagal, tentukan tingkat kegagalan:

- **Gagal Biasa (Margin Gagal 1–25%):** Bahan-bahan hangus menjadi abu hitam (*Scorched Ash*). Tungku kehilangan 5 Poin Durabilitas.
- **Gagal Parah / Meledak (Margin Gagal > 25%):** Terjadi ledakan tekanan Qi pada tungku (*Dan-Lu Meledak*).
  - **Efek Ledakan:**
    - Pembuat pil terkena damage langsung sebesar $\text{PillTier} \times 50$ HP.
    - Tungku kehilangan $20–50$ Poin Durabilitas (atau langsung hancur jika durabilitas rendah).
    - Risiko Qi Deviation: Pembuat pil harus melakukan tes ketahanan Qi (Stamina/Qi check) atau terkena status *Meridian Backfire* (Qi Regen -50% selama 24 jam in-game).

---

## 4. Sistem Dan-Du (Racun Pil / Pill Toxicity)

Setiap pil (kecuali Flawless Grade) meninggalkan akumulasi racun spiritual (*Dan-Du*) dalam tubuh pembuat/pengonsumsi.

- **Batas Maksimal Dan-Du Safe Cap:** $\text{RealmIndex} \times 20$ Poin.
- **Penumpukan Dan-Du:**
  - Jika Dan-Du melampaui Safe Cap:
    - **Tingkat 1 (Ringan):** Efek pil berikutnya berkurang 50%.
    - **Tingkat 2 (Sedang):** Kecepatan regenerasi Qi alami berkurang 50%, timbul rasa mual dan lemas (-10% Hit Chance).
    - **Tingkat 3 (Parah):** Terjadi penyumbatan meridian total (tidak bisa memulihkan Qi dari pil), penurunan HP 2% per jam sampai Dan-Du dibersihkan.
- **Pembersihan Dan-Du:**
  - Bertapa meditasi murni tanpa pil (menghilangkan 1 Poin Dan-Du per 12 jam bertapa).
  - Mengonsumsi Pil Pembersih Racun (*Cleansing Pill*) atau menggunakan teknik penyembuhan khusus.

---

## 5. Katalog Resep Pil Kanon (Pill Recipes)

### 5.1 Pil Pemulihan Qi (Qi Gathering Pill / Ju-Qi Dan)
- **Tier:** Tier 1 (Mortal)
- **Bahan Wajib:** 2× Rumput Lingzhu (Tier 1), 1× Akar Ginseng Salju (Tier 1).
- **Waktu Peracikan:** 2 Jam in-game.
- **Efek:** Memulihkan $100$ Qi secara instan saat dikonsumsi.
- **Dan-Du:** +5 Poin.

### 5.2 Pil Pembentuk Fondasi (Foundation Building Pill / Tsukijidan)
- **Tier:** Tier 2 (Earth)
- **Bahan Wajib:** 1× Bunga Teratai Salju Purba (Tier 2), 1× Inti Monster Tier 2, 2× Rumput Spirit Api (Tier 2).
- **Waktu Peracikan:** 12 Jam in-game (Timed Processing).
- **Efek:** Memberikan +25% Success Rate saat melakukan breakthrough dari Realm 2 (Qi Refining) ke Realm 3 (Foundation Establishment).
- **Dan-Du:** +15 Poin.

### 5.3 Pil Pemulihan Darah & Luka (Blood Vitality Pill / Huan-Xue Dan)
- **Tier:** Tier 1 (Mortal)
- **Bahan Wajib:** 2× Bunga Darah Ling, 1× Air Murni Pegunungan.
- **Waktu Peracikan:** 1 Jam in-game.
- **Efek:** Menghentikan Pendarahan dan memulihkan $150$ HP bertahap selama 5 giliran combat.
- **Dan-Du:** +3 Poin.

### 5.4 Pil Pembersih Meridian & Dan-Du (Cleansing Pill / Qing-Xue Dan)
- **Tier:** Tier 2 (Earth)
- **Bahan Wajib:** 1× Bunga Embun Teratai, 2× Daun Mint Spirit Purba.
- **Waktu Peracikan:** 4 Jam in-game.
- **Efek:** Membuang 15 Poin Dan-Du dari dalam tubuh secara instan.
- **Dan-Du:** 0 Poin.

### 5.5 Pil Penguat Inti Spirit (Core Solidifying Pill / Ning-Sui Dan)
- **Tier:** Tier 3 (Heaven)
- **Bahan Wajib:** 1× Buah Spirit Jiwa Purba (Tier 3), 1× Inti Monster Tier 3 (Beast King), 3× Rumput Giok Es.
- **Waktu Peracikan:** 3 Hari in-game (Timed Processing).
- **Efek:** Memberikan perlindungan dari Qi Deviation selama breakthrough Realm 4 (Core Formation) dan +30% Success Rate.
- **Dan-Du:** +25 Poin.

---

## 6. Integrasi Timed Processing & Checkpoint

 Alkemia tunduk pada aturan Timed Processing (`00` §1.10):
- Saat peracikan dimulai, AI GM mencatat `StartTime`, `RequiredDuration`, dan `CompletionTime`.
- Selama peracikan berlangsung, statusnya adalah `PROCESSING`. Pil belum ada di inventory dan bahan dianggap sudah terpakai.
- Pada saat `CompletionTime`, AI GM melakukan roll keberhasilan peracikan.
- Pemain yang memotong peracikan di tengah jalan kehilangan seluruh bahan dan tungku berisiko meledak.

---

## 7. Status Modul

**CANONICAL — SYSTEM MODULE**
Seluruh aturan peracikan, resep pil, racun Dan-Du, dan batas waktu di atas adalah aturan resmi Lingyuan World.
