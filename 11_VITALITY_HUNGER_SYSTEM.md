# ❤️ Wuxian World — Sistem Vitalitas (HP) & Kelangsungan Hidup (Hunger System)

> **Modul:** 11 — Vitality & Hunger System
> **Prinsip:** Anti-Cheat Enforced — Law-Specific Scaling — Terintegrasi dengan Sistem Hukum Kultivasi & Sistem Ekonomi
> **Rujukan silang:** `09_CULTIVATION_LAW_SYSTEM.md` (QiCap sebagai basis HP), `10_ECONOMY_SYSTEM.md` §4.1 (HealingFee), `12_COMBAT_SYSTEM.md` (FinalDamage mengurangi HP di sini)

---

## 0. Filosofi Sistem

Sama seperti Qi tunduk pada `QiCap` dan harga tunduk pada `FinalPrice`, HP (Vitalitas) dan rasa lapar juga tunduk pada formula tetap — tidak boleh dideklarasikan sepihak oleh player. Tiap Hukum kultivasi punya karakter HP berbeda sesuai filosofinya, dan tiap Realm punya ketahanan lapar berbeda.

### Aturan Emas Anti-Cheat Vitalitas & Kelaparan
- HP TIDAK BOLEH dideklarasikan sepihak oleh player — dihitung AI GM lewat formula `HP(realm, stage, law)`.
- Kerusakan HP (damage) dicatat di log bertimestamp, tidak bisa diedit mundur atau "dilupakan" player.
- Regenerasi HP di luar batas alami hanya lewat pil/jasa tabib yang tunduk Sistem Ekonomi (`10_ECONOMY_SYSTEM.md` §4.1).
- Status kelaparan dihitung otomatis per jam in-game oleh AI GM, bukan klaim sepihak player.
- Breakthrough Realm langsung memperbarui HP Cap dan Fasting Multiplier karakter secara otomatis.

---

## 1. Formula HP Universal

### 1.1 Formula Dasar

```
HPBase(realm, stage) = QiCap(realm, stage) × K_HP
K_HP = 0,4 (Konstanta Vitalitas Universal — tetap untuk semua Hukum, memastikan Tribulasi tetap berisiko nyata)

HP(realm, stage, law) = HPBase(realm, stage) × LawHPMultiplier(law)
```

### 1.2 Law HP Multiplier (Beda Tiap Hukum)

| Hukum | LawHPMultiplier | Alasan Filosofis |
|---|---|---|
| Hukum Raga Sejati (Body Tempering) | ×1,5 | Penempaan tubuh — paling tahan banting, kompensasi qi tumbuh 20% lebih lambat |
| Hukum Dao Abadi (Standar) | ×1,0 | Baseline — seimbang, tidak superior/inferior |
| Hukum Qi Naga Api (Battle Qi) | ×0,9 | Agresif dan ofensif, sedikit lebih rapuh |
| Hukum Gu Karma (Gu Immortal Path) | ×0,7 | Kekuatan licik-berisiko, trade-off klasik "kekuatan besar, harga mahal" |
| Hukum Bayangan Darah (Custom) | ×0,85 (×1,0 saat Kontrak Aktif) | Tanpa ideologi tetap = kurang stabil |
| Hukum Roh Hantu (Custom) | ×0,75 | Berbasis jiwa/vitalitas, rapuh secara raga |
| 🆕 Hukum Pisau Sunyi (Custom) | ×0,8 | Presisi & disiplin eksekutor — cukup tangguh tapi bukan tanky, lihat `33_PERKUMPULAN_PISAU_SUNYI.md` |

📌 Anti-cheat: Hukum Custom baru WAJIB diberi LawHPMultiplier oleh AI GM saat origin-nya divalidasi — rentang wajib **0,6–1,5**, tidak boleh di luar itu tanpa kelemahan tambahan yang jelas.

### 1.3 Contoh Perhitungan

- **Murid Inti Lin Xue** (Core Formation Puncak, Hukum Dao Abadi): QiCap(4,Puncak)=5.000 → HPBase=2.000 → HP=2.000×1,0=**2.000 HP**
- **Kepala Biara Jin Zhong** (Soul Transformation Puncak, Hukum Raga Sejati): QiCap(6,Puncak)=125.000 → HPBase=50.000 → HP=50.000×1,5=**75.000 HP** (konsisten dengan lore "sekeras lonceng emas legendaris")
- **Ratu Ular She Yin** (Soul Transformation Menengah, Hukum Gu Karma): QiCap(6,Menengah)=93.750 → HPBase=37.500 → HP=37.500×0,7=**26.250 HP** (lebih rapuh meski Realm setara)

---

## 2. Status Kondisi HP & Ambang Bahaya

| % HP Tersisa | Status | Efek |
|---|---|---|
| 100%–50% | Sehat (Healthy) | Tidak ada penalti |
| 49%–20% | Terluka (Wounded) | −10% output Qi, −5% efektivitas serangan |
| 19%–1% | Kritis (Critical) | −30% output Qi, −20% efektivitas serangan, risiko Qi Deviation ringan |
| 0% | Pingsan / Qi Deviation Onset | Tak sadarkan diri, WAJIB pertolongan tabib dalam batas waktu naratif |
| −1% s/d −30% | Nyaris Mati | Butuh tabib realm ≥ realm karakter; jika gagal → Qi Deviation Permanen (−10% HP Cap & QiCap selamanya) |
| Di bawah −50% | Kematian | Hanya overkill ekstrem tervalidasi GM — bukan default otomatis |

---

## 3. Regenerasi HP

### 3.1 Regenerasi Alami

```
HPRegenPerJam(realm, stage, law) = HP(realm, stage, law) × 0,5%
```

Berlaku saat karakter beristirahat/bermeditasi. Regenerasi dua kali lipat (×2) bila didampingi lingkungan kaya qi (Qi Density Modifier ≥1,2 — lihat `09_CULTIVATION_LAW_SYSTEM.md` §8.1).

### 3.2 Regenerasi Dibantu (Tabib/Pil)

Tunduk penuh pada `10_ECONOMY_SYSTEM.md` §4.1 (HealingFee) — jumlah HP yang dipulihkan sebanding tingkat luka yang dibayar, dicatat di Item/Service Ledger, tidak instan tanpa transaksi tervalidasi.

---

## 4. Checklist Anti-Cheat HP

- [ ] HP dihitung dari formula `HP(realm, stage, law)`, bukan klaim sepihak player?
- [ ] Damage yang diterima tercatat di log bertimestamp, tidak diedit mundur?
- [ ] Regenerasi di luar alami memakai jasa/pil tervalidasi Sistem Ekonomi?
- [ ] Status kondisi diperbarui otomatis tiap kali HP berubah, bukan diklaim manual player?
- [ ] Breakthrough Realm memperbarui HP Cap secara otomatis?
- [ ] Kematian karakter hanya terjadi lewat validasi GM atas overkill ekstrem, bukan otomatis di 0%?

Jika salah satu poin gagal → status HP/damage DITOLAK, AI GM mengoreksi dengan angka yang benar.

---

## 5. Sistem Kelaparan (Hunger System)

### 5.1 Filosofi

Trope klasik xianxia: kultivator tingkat tinggi bisa "hidup dari qi" dan makin jarang butuh makan seiring realm naik (辟谷 / Bi Gu). Sistem ini merumuskannya bertahap dan realistis: mortal biasa tetap butuh makan seperti manusia normal, sementara kultivator elite nyaris tak butuh makan sama sekali — transisinya bertahap sesuai realm.

### 5.2 Formula Kekenyangan (Satiety)

```
SatietyMax = 100 poin (universal)
DecayRatePerJam(realm) = BaseDecayRate ÷ FastingMultiplier(realm)
BaseDecayRate = 16,67 poin/jam (mortal biasa kehilangan kekenyangan penuh dalam 6 jam)
JamSampaiKosong(realm) = SatietyMax ÷ DecayRatePerJam(realm) = 6 jam × FastingMultiplier(realm)
```

### 5.3 Fasting Multiplier per Realm

| Realm | FastingMultiplier | Waktu Sampai Sangat Lapar |
|---|---|---|
| 0 (Non-Kultivator/Mortal) | ×1,0 | 6 jam (pola makan manusia normal) |
| 1 — Fondasi Fana | ×1,2 | 7,2 jam |
| 2 — Pemurnian Qi | ×2,0 | 12 jam (setengah hari) |
| 3 — Pembentukan Fondasi | ×5,0 | 30 jam (~1,25 hari) |
| 4 — Pembentukan Inti | ×15,0 | 90 jam (~3,75 hari) |
| 5 — Roh Bayi | ×50,0 | 300 jam (~12,5 hari) |
| 6 — Transformasi Roh | ×150,0 | 900 jam (~37,5 hari) |
| 7 — Pemutus Kehampaan | ×500,0 | 3.000 jam (~4 bulan) |
| 8 — Penerobosan Tribulasi | ×2.000,0 | 12.000 jam (~1,4 tahun) |
| 9 — Kenaikan Abadi | Tak terbatas | Tidak butuh makan sama sekali (Bi Gu sempurna) |

📌 Catatan realisme: kultivator awal (Realm 1–2) tetap harus makan hampir seperti manusia biasa, sementara kultivator menengah (Realm 3–4) baru mulai terasa keuntungan trope "bisa menahan lapar berhari-hari saat menjelajah" — cocok dengan rekomendasi jarak tempuh Western Sacred Deserts di `07_WESTERN_SACRED_DESERTS.md`.

### 5.4 Status Efek Kelaparan

| Satiety Tersisa | Status | Efek |
|---|---|---|
| 100–70 | Kenyang (Full) | +5% regenerasi HP/Qi alami (bonus kecil) |
| 69–30 | Normal | Tidak ada efek |
| 29–10 | Lapar (Hungry) | −10% regenerasi Qi, −5% efektivitas serangan |
| 9–1 | Sangat Lapar (Starving) | −30% regenerasi Qi, −20% efektivitas serangan, **TIDAK BISA breakthrough** |
| 0 (berkepanjangan) | Kelaparan Kritis | Mulai kehilangan HP (0,5% HP Cap/jam), −50% semua stat, risiko Qi Deviation |

### 5.5 Pemulihan Kekenyangan (Makan)

| Jenis Makanan | Satiety Dipulihkan | Harga |
|---|---|---|
| Makanan sederhana (nasi, sup desa) | +40 poin | 1–5 Tael Tembaga |
| Makanan enak (restoran kota) | +70 poin | 10–50 Tael Tembaga |
| Jamuan/pesta | +100 poin (penuh) | 1–5 Tael Perak |
| Buah/pil spiritual (bonus tambahan) | +100 poin + bonus 5% regen Qi 6 jam | Tier 2+ sesuai `10_ECONOMY_SYSTEM.md` |

---

## 6. Checklist Anti-Cheat Kelaparan

- [ ] Satiety dihitung otomatis per jam in-game sejak waktu makan terakhir tercatat, bukan klaim sepihak player?
- [ ] FastingMultiplier sesuai realm karakter saat ini (diperbarui otomatis tiap breakthrough)?
- [ ] Status efek diterapkan otomatis sesuai Satiety tersisa?
- [ ] Pemulihan Satiety lewat makanan tervalidasi (tercatat & sesuai harga Sistem Ekonomi)?
- [ ] Kultivator Realm 3 ke bawah tidak mengklaim bisa menahan lapar berminggu-minggu tanpa alasan tervalidasi GM?

Jika salah satu poin gagal → status kelaparan DIKOREKSI oleh AI GM sesuai formula.

---

## 7. Integrasi dengan Sistem Lain

- **Dengan Sistem Hukum Kultivasi:** HP memakai `QiCap(realm, stage)` sebagai basis, memastikan Tribulasi Petir tetap berisiko nyata — HPBase Realm 7 Puncak (250.000 dengan K_HP=0,4) hampir sepadan dengan total damage Tribulasi Penuh (≈218.750, lihat `09_CULTIVATION_LAW_SYSTEM.md` §5).
- **Dengan Sistem Ekonomi:** semua penyembuhan HP di luar regenerasi alami dan semua makanan tunduk pada `FinalPrice` & Item Origin Log (`10_ECONOMY_SYSTEM.md`).
- **Dengan World Document:** wilayah miskin qi tidak memengaruhi Satiety secara langsung, tapi memengaruhi ketersediaan makanan (desa miskin hanya punya varian "sederhana").
