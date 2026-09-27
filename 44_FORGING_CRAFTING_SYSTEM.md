# ⚒️ Lingyuan World — Sistem Tempa & Pembuatan Artefak (Forging & Crafting System)

> **Modul:** 44 — Forging & Crafting System
> **Status:** Canonical System
> **Prinsip:** Source-Traceable — Time-Bound — Anti-Cheat — Hardcore Realism
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` (aturan inti, batas waktu, timed processing §1.10), `09_CULTIVATION_LAW_SYSTEM.md` (Realm & Qi), `10_ECONOMY_SYSTEM.md` (Tier/Grade, Provenance & harga), `12_COMBAT_SYSTEM.md` (senjata, zirah, damage & passive defense), `13_BESTIARY.md` (loot kulit/tulang/tanduk monster), `players/` (official save dikelola Admin)

---

## 0. Filosofi Sistem Tempa & Artefak

Senjata, zirah, dan alat pusaka (*Spirit Artifacts*) di Lingyuan World bukan sekadar besi biasa. Mereka ditempa dengan menggabungkan bijih logam spirit (*Ling Ore*), bahan biologis monster/spirit beast (tulang, kulit, tanduk, inti), serta diukir dengan **Garis Inskripsi Rune Spirit**.

Seorang Tukang Tempa (*Blacksmith / Artificer*) memandukan kekuatan api, martil, dan Qi internal untuk membentuk peralatan berkualitas tinggi.

### Aturan Emas Tempa & Crafting

1. **Bahan Berasal dari Sumber Sah (Provenance):** Logam spirit dan bahan monster WAJIB memiliki asal-usul yang terverifikasi (loot `13_BESTIARY.md`, tambang/wilayah `01`–`07`, atau pembelian `10_ECONOMY_SYSTEM.md`).
2. **Timed Processing Wajib:** Tempa butuh waktu nyata in-game (jam hingga hari) dan tunduk pada aturan **Timed Processing** (`00_CORE_RULES_AI_GM.md` §1.10).
3. **Durabilitas & Kerusakan:** Senjata dan zirah mengalami aus/penurunan durabilitas saat digunakan bertarung (`12_COMBAT_SYSTEM.md`). Senjata yang rusak (durabilitas 0) tidak bisa memberi bonus damage/defense.
4. **Klasifikasi Tier Equipment:** Senjata/zirah dibagi menjadi 4 Tier Utama:
   - **Tier 1 (Mortal Equipment):** Senjata/zirah besi biasa tanpa Qi.
   - **Tier 2 (Spirit Equipment / Ling-Qi):** Terbuat dari bahan spirit, dapat menyalurkan Qi pengguna.
   - **Tier 3 (Earth Treasure / Earth Artifact):** Terbuat dari logam purba & materi monster tingkat tinggi, memiliki efek pasif/aktif khusus.
   - **Tier 4 (Heaven / Immortal Artifact):** Senjata pusaka legendaris berkesadaran spiritual (*Spiritual Spirit*).
5. **Inskripsi Rune Formasi:** Menambahkan Rune ke senjata/zirah memberikan efek statistik tambahan namun meningkatkan kesulitan penempaan.

---

## 1. Landasan Fasilitas Tempa (Blacksmith Workshop & Anvil)

| Tier Landasan / Bengkel | Jenis Pandai Besi | Bonus Success Rate | Batas Maksimal Tier Barang | Durabilitas Landasan | Harga Sewa / Buat |
|---|---|---|---|---|---|
| **Tier 1 (Mortal)** | Tungku Besi Desa Biasa | +0% | Tier 1 (Mortal) | 100 Poin | 10 Tael Perak / hari |
| **Tier 2 (Spirit)** | Bengkel Tempa Sekte Spirit | +10% | Tier 2 (Spirit) | 300 Poin | 5 Tael Emas / hari |
| **Tier 3 (Earth)** | Landasan Besi Meteorik Flame | +25% | Tier 3 (Earth) | 1.000 Poin | 2 Giok Kecil / hari |
| **Tier 4 (Immortal)**| Landasan Purba API Suci Dewa | +45% | Tier 4 (Immortal) | 5.000 Poin | 20 Giok Menengah / hari |

---

## 2. Bahan Tempa Kanon (Forging Materials)

### 2.1 Logam Spirit Utama (Ling Ores)
- **Besi Hitam Mortal (Black Iron - Tier 1):** Logam keras biasa, tidak menyerap Qi.
- **Tembaga Spirit Ling (Spirit Copper - Tier 2):** Menghantarkan Qi dengan baik, cocok untuk senjata tajam.
- **Besi Meteorik Cold-Ice (Cold Ice Ore - Tier 2):** Memiliki atribut dingin/es alami.
- **Emas Purba Xuanjin (Xuanjin Gold - Tier 3):** Sangat kokoh, mampu menahan tekanan Qi dalam jumlah besar.
- **Kristal Perak Bintang (Star Silver Crystal - Tier 3):** Logam ringan berkecepatan tinggi, cocok untuk pedang terbang / jimat.
- **Batu Meteorik Dewa Purba (Immortal Ore - Tier 4):** Logam legendaris tingkat tinggi.

### 2.2 Material Tambahan Monster / Spirit Beast (`13_BESTIARY.md`)
- **Tanduk / Cakar Monster:** Menambah Armor Penetration atau Critical Damage.
- **Kulit / Sisik Monster:** Bahan utama pembuatan Zirah / Armor Fleksibel (Pelindung Dada/Jubah).
- **Inti Monster (Monster Core):** Sumber daya energi aktif untuk inskripsi rune pada senjata Tier 2–4.

---

## 3. Proses Penempaan & Formula Keberhasilan

Proses penempaan dibagi menjadi 4 tahap:

```
[1. Peleburan Logam (Melting)] ➔ [2. Pengandupan & Pembentukan (Forging & Shaping)] ➔ [3. Penyepuhan & Penyejukan (Quenching)] ➔ [4. Inskripsi Rune Spirit (Inscribing)]
```

### 3.1 Formula Success Rate Penempaan

$$\text{SuccessRate} = 50\% + (\text{RealmIndex} \times 5\%) + \text{WorkshopBonus} - (\text{ItemTier} \times 15\%) + \text{ForgingSkillBonus}$$

- **RealmIndex:** 1 (Mortal), 2 (Qi Refining), 3 (Foundation Establishment), 4 (Core Formation), dst.
- **ItemTier:** 1 (Mortal), 2 (Spirit), 3 (Earth), 4 (Immortal).
- **ForgingSkillBonus:** Bonus dari teknik tempa yang dikuasai (0% - 20%).
- **Batas Peluang:** Minimal 5%, Maksimal 95%.

### 3.2 Penentuan Quality Grade Hasil Tempa

| Margin Success Roll | Quality Grade Equipment | Bonus Statistik Equipment | Durabilitas Maksimal Item |
|---|---|---|---|
| Margin 1–20% | **Low Quality (Rendah)** | +0% dari Stat Base | 50 Poin |
| Margin 21–50% | **Mid Quality (Menengah)** | +15% dari Stat Base | 100 Poin |
| Margin 51–80% | **High Quality (Tinggi)** | +30% dari Stat Base | 150 Poin |
| Margin 81–95% | **Peak Quality (Puncak)** | +50% dari Stat Base | 200 Poin |
| Roll Kritis (Natural 100) | **Masterpiece / Flawless** | +100% Stat Base + 1 Slot Rune Ekstra | 300 Poin |

---

## 4. Statistik Dasar Senjata & Zirah Per Tier

### 4.1 Senjata (Pedang, Tombak, Golok, Panah)
- **Tier 1 (Mortal):** Attack Power +15 | Armor Penetration 0% | Max Durability: 50
- **Tier 2 (Spirit):** Attack Power +50 | Modifikator Pengaliran Qi: +10% | Max Durability: 100
- **Tier 3 (Earth):** Attack Power +200 | Armor Penetration +15% | Max Durability: 200
- **Tier 4 (Immortal):** Attack Power +800 | Armor Penetration +35% | Max Durability: 500

### 4.2 Zirah / Pelindung (Baju Zirah, Jubah Spirit, Perisai)
- **Tier 1 (Mortal):** Passive Defense +10 | Movement Speed -5% | Max Durability: 50
- **Tier 2 (Spirit):** Passive Defense +35 | Damage Reduction +5% | Max Durability: 100
- **Tier 3 (Earth):** Passive Defense +150 | Damage Reduction +15% | Max Durability: 200
- **Tier 4 (Immortal):** Passive Defense +600 | Damage Reduction +30% | Max Durability: 500

---

## 5. Sistem Durabilitas & Perbaikan (Durability & Repair)

- **Konsumsi Durabilitas dalam Combat (`12_COMBAT_SYSTEM.md`):**
  - Senjata berkurang **1 Poin Durabilitas** setiap kali menyerang zirah keras atau menangkis serangan berat.
  - Zirah berkurang **1–3 Poin Durabilitas** setiap kali menerima hit langsung dari musuh.
- **Kondisi Aus:**
  - Jika Durabilitas < 50%: Bonus stat berkurang 25%.
  - Jika Durabilitas < 20%: Bonus stat berkurang 70%.
  - Jika Durabilitas = 0%: Senjata/Zirah patah/rusak total, tidak memberikan bonus stat sama sekali sampai diperbaiki.
- **Biaya Perbaikan (Repairing):**
  - Membutuhkan waktu 1–3 jam di bengkel tempa.
  - Membutuhkan biaya 20% dari material dasar tempa.

---

## 6. Risko Kegagalan Tempa

- **Gagal Biasa (Margin Gagal 1–25%):** Material utama cacat, tingkat kualitas turun 1 grade, atau kehilangan 50% material pendukung.
- **Gagal Total (Margin Gagal > 25%):** Material meledak/hancur total menjadi terak besi tanpa sisa. Penempa menerima damage $20 \times \text{ItemTier}$ HP dan Landasan tempa berkurang durabilitasnya 10 poin.

---

## 7. Contoh Resep Tempa Kanon (Crafting Recipes)

### 7.1 Pedang Spirit Tembaga Ling (Ling Copper Sword)
- **Tier:** Tier 2 (Spirit Equipment)
- **Bahan Wajib:** 3× Batangan Tembaga Spirit Ling, 1× Teras Kayu Lingzhu, 1× Inti Monster Tier 2.
- **Waktu Tempa:** 6 Jam in-game (Timed Processing).
- **Hasil Stat:** Attack Power +50 | Multiplier Pengaliran Qi +10% | Max Durability: 100.

### 7.2 Zirah Sisik Naga Serigala (Wolf-Dragon Scale Armor)
- **Tier:** Tier 2 (Spirit Equipment)
- **Bahan Wajib:** 5× Sisik Serigala Air (`13_BESTIARY.md`), 2× Batangan Tembaga Spirit Ling, 1× Tali Urat Beast.
- **Waktu Tempa:** 8 Jam in-game (Timed Processing).
- **Hasil Stat:** Passive Defense +40 | Resistance Efek Beku +10% | Max Durability: 120.

### 7.3 Pedang Terbang Bintang Es (Cold Star Flying Sword)
- **Tier:** Tier 3 (Earth Treasure)
- **Bahan Wajib:** 2× Besi Meteorik Cold-Ice, 2× Kristal Perak Bintang, 1× Inti Monster Tier 3 (Raja Beast).
- **Waktu Tempa:** 2 Hari in-game (Timed Processing).
- **Hasil Stat:** Attack Power +220 | Kecepatan Serang +20% | Efek Pembekuan Qi Musuh | Max Durability: 200.

---

## 8. Status Modul

**CANONICAL — SYSTEM MODULE**
Seluruh aturan penempaan, inskripsi rune, durabilitas, dan formula keberhasilan di atas adalah aturan resmi Lingyuan World.
