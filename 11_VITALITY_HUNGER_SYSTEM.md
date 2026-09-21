# ❤️ Lingyuan World — Sistem Vitalitas (HP) & Kelangsungan Hidup (Hunger System)

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
| 🆕 Hukum Pisau Sunyi (Custom) | ×0,8 | Presisi & disiplin eksekutor — cukup tangguh tapi bukan tanky, lihat `33_PERKUMPULAN_WUYING.md` |

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


## 3A. Sistem Stamina — Fondasi Universal

### 3A.1 Hasil Audit Canon

Audit repository memisahkan state Stamina, efek Stamina yang eksplisit, dan formula yang sebelumnya belum didefinisikan.

Canon yang dapat diverifikasi:
- Stamina adalah state yang WAJIB dilacak bersama HP, Qi, Satiety, dan kondisi tubuh.
- Fondasi karakter menggunakan **Stamina 100/100**.
- Haiyuan memiliki efek lingkungan eksplisit: setiap 6 jam waktu in-game, Arus Pasang Lepas dapat menyebabkan **−30 Stamina per luapan** pada karakter yang tidak terikat jangkatan.
- Qingyun memiliki Mata Air Bambu Giok yang mempercepat pemulihan stamina raga.
- Tekanan Awan Embun di Lembah Yuzhu mengurangi **regenerasi Stamina sebesar 15%** bila karakter tidak menggunakan teknik penyesuaian Qi.
- Repository tidak memiliki formula canon lama yang menetapkan biaya Stamina universal per jenis aksi.

Karena itu, angka kategori **1/3/5/10/15/20** dan recovery **+10/+15/+5 per jam** dari revisi sebelumnya dinyatakan **dibatalkan**. Angka tersebut bukan fondasi canon asli.

### 3A.2 Kapasitas Stamina

Fondasi universal tetap:

```
MaxStamina = 100
CurrentStamina = clamp(CurrentStamina, 0, MaxStamina)
```

**100/100 adalah baseline asli karakter.**

Perubahan MaxStamina hanya sah jika ada aturan canon/Admin yang secara eksplisit mengubah kapasitas fisik. Realm, Qi, Law, atau teknik tidak otomatis menaikkan MaxStamina.

### 3A.3 Formula Universal Pengeluaran Stamina

```
StaminaCost = round(MaxStamina × PhysicalLoad × ActionDurationHours / 3, 1)
```

Dengan batas:

```
0 ≤ PhysicalLoad ≤ 1
ActionDurationHours ≤ 3
StaminaCost ≥ 0
```

PhysicalLoad adalah beban fisik aktual; ActionDurationHours adalah waktu aksi yang benar-benar dijalankan. Cost tidak boleh dikalikan lagi hanya karena jumlah pesan bertambah.

Kalibrasi formula Admin: pada MaxStamina 100, aksi 3 jam dengan PhysicalLoad 0,10 = 10 Stamina; 0,25 = 25; 0,50 = 50. Ini kalibrasi formula, bukan kategori aktivitas.

Jika teknik, item, Law, atau bahaya canon memiliki Stamina Cost spesifik, cost spesifik tersebut berlaku hanya dalam scope efek tersebut.

### 3A.4 Formula Recovery Universal

```
BaseStaminaRecoveryPerHour = MaxStamina × 10% = 10 Stamina/jam
RecoveredStamina = BaseStaminaRecoveryPerHour × ElapsedRecoveryHours × RecoveryModifier
CurrentStamina = min(MaxStamina, CurrentStamina + RecoveredStamina)
```

RecoveryModifier default = 1,0. Recovery hanya dihitung dari World Time yang benar-benar berlalu dalam kondisi recovery valid.

Tekanan Awan Embun Qingyun memberi RecoveryModifier 0,85 bila syarat canon terpenuhi. Mata Air Bambu Giok hanya diketahui mempercepat recovery; besaran tambahannya belum canon → `??? / UNRESOLVED`.

### 3A.4 Kalibrasi PhysicalLoad — Universal

PhysicalLoad = clamp(BasePhysicalDemand × ToolFactor × EnvironmentFactor × BodyConditionFactor, 0, 1)

PhysicalLoad adalah estimasi **beban fisik nyata**, bukan daftar cost per aksi dan bukan kategori tetap.

### A. BasePhysicalDemand

GM menilai seberapa besar tenaga fisik yang benar-benar dibutuhkan pekerjaan berdasarkan bukti runtime:
- **0** bila tindakan tidak membutuhkan tenaga fisik yang berarti;
- nilai kontinu **>0 sampai 1** bila tindakan benar-benar menggunakan tenaga fisik;
- penilaian mempertimbangkan beban/berat yang dipindahkan, tahanan, gaya yang diperlukan, repetisi, postur, dan apakah tubuh harus mempertahankan usaha secara aktif.

Tidak ada tabel aksi seperti 1/3/5/10/15/20 Stamina.

### B. ToolFactor

Alat yang benar-benar digunakan dapat mengurangi atau menambah tuntutan fisik.
- Alat bantu mekanis/spiritual yang secara canon mengurangi tenaga → `ToolFactor < 1`.
- Alat yang menambah beban atau sulit dikendalikan → `ToolFactor > 1`.
- Tanpa efek alat yang tervalidasi → `ToolFactor = 1`.
- Besaran perubahan harus ditetapkan dari kemampuan alat yang canon; bila tidak dapat ditentukan → `??? / UNRESOLVED`.

Alat tidak boleh menciptakan pengurangan Stamina hanya karena namanya terdengar membantu.

### C. EnvironmentFactor

Lingkungan hanya mengubah PhysicalLoad bila benar-benar meningkatkan atau mengurangi tuntutan fisik.
Contoh faktor yang dapat diperiksa:
- medan berat/lumpur/air;
- tekanan, suhu, atau kondisi udara yang secara canon memengaruhi usaha fisik;
- gravitasi atau hambatan khusus yang memang tercatat;
- kondisi permukaan kerja.

Lingkungan tanpa efek fisik yang tervalidasi → `EnvironmentFactor = 1`. Efek regional seperti **−15% regenerasi Stamina di Lembah Yuzhu** atau **−30 Stamina per luapan Haiyuan** bukan EnvironmentFactor dan tidak boleh dimasukkan lagi ke StaminaCost.

### D. BodyConditionFactor

Kondisi tubuh mengubah usaha yang diperlukan untuk melakukan pekerjaan yang sama.
- Kondisi tubuh normal tanpa faktor tambahan → `BodyConditionFactor = 1`.
- Cedera, kelelahan, sakit, atau kondisi lain yang canon membuat pekerjaan lebih berat dapat menaikkan faktor.
- Bantuan/pemulihan yang canon membuat pekerjaan lebih ringan dapat menurunkannya.
- Jika dampak kondisi terhadap tuntutan fisik belum dapat ditentukan secara canon/runtime → `??? / UNRESOLVED`.

BodyConditionFactor tidak boleh dipakai untuk membuat penalti HP/Qi baru.

### E. Physical-Work Gate

Sebelum menghitung formula, GM wajib menentukan apakah tindakan benar-benar memerlukan tenaga fisik.
- Jika **tidak** → `PhysicalLoad = 0` dan tidak ada StaminaCost dari formula fisik ini.
- Jika **ya** → hitung empat komponen di atas berdasarkan kondisi aktual.
- Jika bukti tidak cukup untuk menentukan apakah pekerjaan fisik atau seberapa besar bebannya → `UNRESOLVED`, bukan angka tebakan.

### F. Durasi tidak masuk dua kali

`ActionDurationHours` sudah menjadi variabel terpisah dalam formula StaminaCost. Karena itu, **durasi tidak boleh dimasukkan lagi ke BasePhysicalDemand sebagai pengali kedua**. BasePhysicalDemand menggambarkan intensitas tuntutan fisik; ActionDurationHours menggambarkan berapa lama tuntutan tersebut dilakukan.

### G. Audit Rule

GM harus dapat menjelaskan sumber penilaian PhysicalLoad secara singkat dari:
1. pekerjaan yang dilakukan;
2. beban/resistansi nyata;
3. alat;
4. lingkungan;
5. kondisi tubuh.

Jika salah satu faktor relevan tetapi datanya tidak tersedia, status hasil harus `??? / UNRESOLVED`, bukan diam-diam memakai angka baru.

## 3A.5 Drain Langsung dari Bahaya / Efek Canon

```
CurrentStaminaAfterDrain = max(0, CurrentStamina - DirectStaminaDrain)
```

Direct Drain tidak dicampur dengan action cost. Canon Haiyuan: **−30 Stamina per luapan**, interval 6 jam, bila syarat karakter tidak terikat jangkatan terpenuhi.

### 3A.6 Hubungan dengan World Time

- Action Cost memakai durasi aksi yang benar-benar terjadi.
- Recovery memakai elapsed World Time yang benar-benar berada dalam kondisi recovery.
- Direct Drain memakai interval/trigger canon.
- Growth Time tanaman bukan Stamina Cost.
- Tidak ada recovery/drain hanya karena jumlah TURN/pesan bertambah.

### 3A.6.1 Valid Recovery State — Anti-TURN

Recovery hanya dihitung ketika **World Time benar-benar berlalu** dan karakter berada dalam kondisi yang valid untuk pemulihan stamina. Valid recovery state minimal mencakup istirahat atau tidur yang benar-benar terjadi; keadaan lain hanya valid bila canon/runtime secara eksplisit menyatakan tubuh sedang memulihkan diri.

- Jumlah TURN/pesan **tidak pernah** menjadi satuan recovery.
- Menyelesaikan satu aksi tidak otomatis memulihkan Stamina pada akhir TURN.
- Active physical work menghentikan klaim recovery untuk durasi aksi tersebut.
- Active combat, perjalanan fisik, maintenance, atau aktivitas lain yang benar-benar menggunakan tenaga tidak dihitung sebagai recovery hanya karena waktunya berlalu.
- Cultivation time adalah **World Time**, tetapi cultivation tidak otomatis berarti recovery Stamina. Jika karakter berkultivasi secara aktif, recovery Stamina hanya boleh dihitung bila kondisi runtime/canon memang menunjukkan tubuh berada dalam keadaan recovery yang sah.
- RecoveryModifier diterapkan setelah valid recovery interval ditentukan.
- Regional recovery modifier seperti Qingyun `−15%` hanya memodifikasi recovery; ia tidak menciptakan recovery bila karakter tidak berada dalam recovery state.

### 3A.6.3 Timed Processing dan Vitality

Timed Processing pada 00_CORE_RULES_AI_GM.md §1.10 tidak berarti karakter yang menunggu proses otomatis kehilangan atau memulihkan Stamina.

- Stamina cost hanya diterapkan pada aktivitas fisik yang benar-benar dilakukan karakter.
- Memulai proses lalu menunggu hasil tidak otomatis memberi Stamina cost tambahan per jam.
- Jika karakter tetap bekerja, menjaga tungku, mengawasi proses, bepergian, bertarung, atau melakukan aktivitas fisik lain selama proses, aktivitas tersebut dinilai dan dicatat terpisah sesuai aturan Stamina dan Action Limit.
- Elapsed World Time selama proses tidak otomatis menjadi recovery; recovery tetap mengikuti aturan valid recovery state.
- Satiety/Hunger tetap mengikuti elapsed World Time dan aturan hunger yang berlaku, terlepas dari status PROCESSING.

### 3A.6.2 Interaksi dengan Action Limit dan Environmental Drain

- Batas aksi non-kultivasi tetap maksimal **3 jam** per prompt menurut `00_CORE_RULES_AI_GM.md`; formula Stamina tidak memperbolehkan memperpanjang aksi melebihi batas tersebut.
- Cultivation murni dapat memakai aturan durasi khusus Core Rules, tetapi durasi itu tidak mengubah formula Stamina menjadi biaya per TURN atau memberi recovery otomatis.
- Direct environmental drain, seperti Haiyuan `−30 Stamina` tiap luapan yang memenuhi syarat, adalah event terpisah dari StaminaCost dan recovery.
- Jika drain lingkungan terjadi saat World Time berjalan, drain diterapkan pada timestamp trigger; recovery dihitung hanya dari interval recovery yang benar-benar sah dan tidak boleh menghapus fakta bahwa drain tersebut terjadi.
- Pertumbuhan Gardening tetap berjalan berdasarkan World Time dan tidak mengubah World Time menjadi Stamina recovery.

### 3A.7 Hubungan dengan Qi, Realm, dan Law

Qi, Realm, dan Law tidak otomatis memberi bonus/pengurangan Stamina. Efek khusus hanya berlaku bila canon secara eksplisit mendefinisikannya.

### 3A.8 Kondisi Stamina

Repository asli tidak memiliki ambang universal yang sah untuk mengubah Stamina menjadi penalti HP, Qi, Attack, atau Defense.

- CurrentStamina tetap angka runtime utama.
- Tidak ada penalti persentase otomatis hanya karena Stamina rendah.
- CurrentStamina = 0 berarti tidak ada cadangan Stamina untuk biaya aksi fisik berikutnya; kemungkinan aksi ditentukan dari kondisi dan canon, bukan penalti baru.

### 3A.9 Adaptasi Universal untuk Gardening

Gardening tidak memiliki skala Stamina sendiri.

```
StaminaCostGardening = round(100 × GardeningPhysicalLoad × GardeningActionDurationHours / 3, 1)
```

GardeningPhysicalLoad adalah PhysicalLoad universal pada §3A.3.

Inspection, Standard Irrigation, Soil Care, Planting, Harvest, dan Special Maintenance memakai formula yang sama. Tidak ada lagi cost Gardening tetap 1/3/5/10/15/20.

Pertumbuhan tanaman tetap mengikuti Growth Duration dan World Time; Stamina hanya berkurang dari tindakan fisik yang benar-benar dilakukan.

### 3A.10 Checklist Audit Stamina

- [ ] MaxStamina baseline = 100?
- [ ] Cost memakai PhysicalLoad × Duration, bukan kategori 1/3/5/10/15/20?
- [ ] Recovery memakai baseline 10% MaxStamina/jam dan World Time nyata?
- [ ] Modifier canon diterapkan sebagai modifier?
- [ ] Direct environmental drain dicatat terpisah?
- [ ] Haiyuan −30 per luapan tetap?
- [ ] Qingyun −15% recovery tetap?
- [ ] Mata Air Bambu Giok tidak diberi angka tambahan tanpa canon?
- [ ] Gardening memakai formula universal yang sama?
- [ ] Growth Time tidak dicampur dengan Stamina Cost?
- [ ] Tidak ada penalti HP/Qi/Attack/Defense otomatis tanpa canon?

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

📌 Catatan realisme: kultivator awal (Realm 1–2) tetap harus makan hampir seperti manusia biasa, sementara kultivator menengah (Realm 3–4) baru mulai terasa keuntungan trope "bisa menahan lapar berhari-hari saat menjelajah" — cocok dengan rekomendasi jarak tempuh Xisha di `07_XISHA.md`.

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
