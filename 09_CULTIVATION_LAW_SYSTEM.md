# 📜 Wuxian World — Sistem Hukum Kultivasi (Cultivation Laws System)

> **Modul:** 09 — Cultivation Law System
> **Untuk:** Roleplay AI Game Master "Jianghu: Legend of the Wuxia"
> **Prinsip:** Anti-Cheat Enforced — Stable Tier Scaling — Karma-Linked Tribulation
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` (aturan wajib), `10_ECONOMY_SYSTEM.md` (harga bahan), `11_VITALITY_HUNGER_SYSTEM.md` (HP pakai QiCap yang sama), `12_COMBAT_SYSTEM.md` (Attack/Defense pakai QiCap yang sama), file regional `02`–`07` (Qi Density & sekte)

---

## 🧭 1. Filosofi Sistem

Setiap "Hukum" (Law) adalah jalur kultivasi berbeda dengan sumber daya berbeda (True Qi, Dou Qi/Battle Qi, Gu, dsb), tapi **semua Hukum tunduk pada satu Formula Batas Qi (Qi Cap Formula)** yang sama, supaya tidak ada jalur yang overpower dibanding yang lain.

**AI GM WAJIB menolak** klaim kekuatan/qi/item yang melampaui batas formula di bawah ini — tanpa pengecualian, tanpa "power creep" naratif.

### Aturan Emas Anti-Cheat
- Qi/energi karakter tidak boleh melebihi `QiCap(realm, stage)` — dihitung ulang tiap turn oleh AI.
- Breakthrough (terobosan) HARUS memenuhi 3 syarat sekaligus: bahan minimum, insight/comprehension tervalidasi GM, dan (untuk realm 7+) selamat dari Tribulasi.
- Tidak ada retroactive edit stat oleh player — semua log qi/item bertimestamp dan tidak bisa diubah mundur.
- Item/pil hanya boleh menaikkan qi sebatas ±1 tier dari tier user saat ini (material tier matching).
- Law custom TETAP tunduk pada formula qi cap yang sama — hanya reskin mekanik, bukan reskin batas.
- **Player TIDAK BOLEH mendeklarasikan sendiri "aku terobosan pakai Hukum X" di saat momen terobosan.** AI GM yang menentukan Hukum/teknik apa yang berlaku, berdasarkan teknik yang benar-benar dilatih/dipraktikkan player sepanjang cerita — dan itu hanya sah jika sudah punya **Asal-Usul Hukum** yang tervalidasi (§3.0). Deklarasi sepihak tanpa asal-usul = otomatis DITOLAK.

---

## 🌀 2. Struktur Realm Universal (9 Major Realm × 3 Stage = 27 Sub-Tier)

Semua Hukum memakai kerangka realm yang sama, hanya penamaan yang berbeda per Hukum.

| # | Major Realm (Universal) | Realm Base (RB) |
|---|---|---|
| 1 | Fondasi Fana (Mortal Foundation) | 0 |
| 2 | Pemurnian Qi (Qi Refining) | 100 |
| 3 | Pembentukan Fondasi (Foundation Establishment) | 500 |
| 4 | Pembentukan Inti (Core Formation) | 2.500 |
| 5 | Roh Bayi (Nascent Soul) | 12.500 |
| 6 | Transformasi Roh (Soul Transformation) | 62.500 |
| 7 | Pemutus Kehampaan (Void Severing) | 312.500 |
| 8 | Penerobosan Tribulasi (Tribulation Crossing) ⚡ | 1.562.500 |
| 9 | Kenaikan Abadi (Immortal Ascension) | 7.812.500 |

📌 **Catatan desain (v3.0):** Fondasi Fana (Realm 1) sengaja diberi RealmBase **0** — mortal sejati yang belum benar-benar berkultivasi memang tidak punya Qi Cap sama sekali, ini pilihan desain untuk realisme, bukan kesalahan. Konsekuensinya, RealmBase tiap realm di atasnya bergeser turun satu tingkat dibanding versi sebelumnya (setiap Realm sekarang bernilai 1/5 dari versi lama). **Ini mengubah QiCap SEMUA karakter di seluruh dunia** — lihat §9 di bagian bawah file ini untuk aturan migrasi.

Tiap Major Realm punya 3 Stage: **Awal (×1,0) → Menengah (×1,5) → Puncak (×2,0)**

### 🔒 Formula Qi Cap (WAJIB DIPAKAI AI GM)

```
QiCap(realm, stage) = RealmBase(realm) × StageMultiplier(stage)
```

Contoh: Core Formation Puncak = 2.500 × 2,0 = **5.000 poin Qi maksimum**. Klaim di atas ini otomatis DITOLAK sistem.

⚠️ **ATURAN WAJIB — Qi Cap SELALU dihitung ulang dari formula ini, TIDAK PERNAH dibaca langsung dari angka "Qi Cap: X" yang tertulis di tabel NPC manapun (`01`–`08`, `14`–`37`, `players.md`).** Angka-angka tersebut ditulis sebelum RealmBase direvisi ke versi v3.0 ini dan sebagian besar **sudah tidak akurat (5× terlalu tinggi)** untuk Realm 2 ke atas. AI GM WAJIB menghitung ulang QiCap dari Realm+Stage karakter/NPC yang tertulis menggunakan tabel RealmBase v3.0 di atas — bukan dari angka Qi Cap lama yang mungkin masih tertulis di file lain. Lihat §9 untuk detail & daftar file yang sudah diperbarui manual vs yang masih perlu dihitung ulang saat dipakai.

Realm 8 (Tribulation Crossing) hanya bisa dicapai lewat event Tribulasi Petir (§5) — tidak bisa lewat pil/item sebesar apapun.

---

## ⚔️ 3. Daftar Hukum Kultivasi (Cultivation Laws)

### 🔐 3.0 Asal-Usul Hukum (Law Origin) — WAJIB SEBELUM APAPUN

Ini fondasi anti-cheat paling penting: **tidak ada Hukum yang aktif tanpa asal-usul yang sah.** AI GM tidak pernah menerima kalimat sepihak seperti "aku pakai Hukum Api" atau "aku terobosan pakai Hukum Custom aku" begitu saja. Yang menentukan Hukum apa yang berlaku adalah **teknik konkret yang sudah dilatih player lewat roleplay**, dan teknik itu hanya sah kalau berasal dari salah satu dari 3 jalur berikut:

| Jalur Asal-Usul | Syarat Sah | Contoh Tidak Sah (Ditolak) |
|---|---|---|
| **1. Guru (Master/Mentor)** | Harus ada NPC guru yang sudah diperkenalkan & berinteraksi lewat beberapa adegan pengajaran nyata (bukan cuma 1 baris dialog). AI GM mencatat *siapa* gurunya, *teknik apa* yang diajarkan, dan *kapan* pengajaran itu terjadi di log cerita. | Player tiba-tiba bilang "guruku dulu mengajariku Hukum Petir" padahal belum pernah ada guru/adegan itu di cerita sebelumnya. |
| **2. Manual/Kitab Pusaka** | Kitab/manual harus sudah ada di inventory karakter lewat cara yang sah dan tercatat (ditemukan lewat quest, hadiah sekte, hasil pertarungan, dll). Isinya ditentukan AI GM saat item itu pertama kali didapat, bukan saat dipakai. | Player mendadak bilang "aku punya kitab rahasia" tepat sebelum terobosan tanpa item itu pernah tercatat di inventory. |
| **3. Pencerahan (Genuine Enlightenment)** | Hanya bisa dipicu **oleh AI GM**, bukan diklaim player, dan hanya setelah Insight Point terkumpul cukup (§4) lewat proses panjang: meditasi mendalam yang benar-benar dinarasikan, pertempuran mendekati kematian, atau momen filosofis besar dalam cerita. | Player bilang "aku tiba-tiba tercerahkan dan menciptakan Hukum baru" di tengah pertarungan tanpa proses insight sebelumnya. |

**Aturan pengikat:**
- Setiap karakter WAJIB punya **Law Origin Log** — catatan permanen: Hukum apa, dari jalur mana (1/2/3), kapan diperoleh, siapa/apa sumbernya.
- Hukum (termasuk Hukum Custom di §3.E) **tidak bisa dipilih atau diciptakan di saat yang sama dengan momen terobosan** — origin harus sudah ada & tervalidasi SEBELUM proses breakthrough dimulai.
- Kalau player memakai teknik/Hukum yang tidak match dengan Law Origin Log miliknya, AI GM WAJIB menolak dan meminta player membangun origin yang sah dulu lewat roleplay.
- Ganti Hukum di tengah jalan (multi-Law character) tetap harus lewat salah satu dari 3 jalur ini lagi — tidak ada "law switching" gratis.

### A. 🥋 Hukum Raga Sejati — *True Qi Body Tempering*
- Sumber daya: **True Qi (Zhen Qi)**, disimpan di Dantian & disalurkan lewat meridian.
- Mekanik unik: setiap sub-tier menempa 1 bagian tubuh (kulit → otot → tulang → sumsum → organ → darah → jiwa raga). Body Tempering yang gagal menyebabkan **Qi Deviation** (cedera permanen −10% cap sampai disembuhkan).
- Kelemahan wajib: pertumbuhan qi 20% lebih lambat dari Hukum Dao Abadi, sebagai kompensasi durabilitas fisik yang superior.
- Sekte pengguna: Golden Bell Monastery, Silver Rain Sword School (hybrid).

### B. 🔥 Hukum Qi Naga Api — *Battle Qi (Dou Qi), atribut Api*
- Sumber daya: **Dou Qi** dibakar dari inti api dalam tubuh (Fire Core).
- Mekanik unik: bisa menyerap "Api Langit/Bumi" (Heaven & Earth Fire) untuk lompatan qi instan — TAPI penyerapan Api tier tinggi tanpa realm yang cukup memicu **Backlash Damage** = 15% dari QiCap realm saat ini.
- Kelemahan wajib: rentan terhadap elemen Air/Es (−25% efektivitas serangan).
- Sekte pengguna: Demonic Flame Palace.

### C. 🌌 Hukum Dao Abadi — *Standard Immortal Qi Cultivation*
- Sumber daya: **Spiritual Qi** murni dari Heaven & Earth, dikumpulkan lewat meditasi/formasi.
- Mekanik unik: bisa membentuk **Dao Insight** — comprehension pasif yang mempercepat breakthrough bila player benar-benar merenungkan "Dao" tertentu dalam roleplay (jalan pedang, jalan api, jalan alam, dll).
- Kelemahan wajib: butuh lingkungan kaya qi (spirit vein) — di zona miskin qi, regenerasi qi −50%.
- Sekte pengguna: Heavenly Sword Pavilion (varian Pedang), Profound Heaven Sect (standar), Jade Purity Palace (varian Air/Laut), Azure Cloud Temple (varian Welas Asih/Buddhis), Silver Rain Sword School (hybrid).

### D. 🐛 Hukum Gu Karma — *Gu Immortal Path (gaya Fang Yuan)*
- Sumber daya: **Gu** (makhluk/energi hidup hasil biakan) + **Dao Marks** (jejak jalan yang terbentuk dari pengalaman/pembunuhan/pencerahan).
- Mekanik unik: kekuatan tidak murni dari qi tapi dari jumlah & kualitas Gu yang dikuasai. Setiap Gu premium yang dipakai berisiko memberi efek samping permanen (racun, mutasi, ketergantungan) — sumber "Karma Buruk" alami jalur ini.
- Kelemahan wajib: jalur ini secara default menaikkan **Sin Points** (§6) lebih cepat, sehingga Tribulasi jalur ini biasanya lebih berat.
- Qi cap Gu dihitung dengan mengonversi total "Gu Value" ke satuan Qi standar (1 Gu Value = 1 poin Qi), tetap tunduk pada `QiCap(realm, stage)`.
- Sekte pengguna: Nine Serpent Den (varian Racun), Seven Sins Cult (varian instan, Sin tinggi).

### E. 🛠️ Hukum Custom (Buatan Player — Divalidasi Ketat AI)
Player boleh mengajukan Hukum sendiri, TAPI pengajuan itu sendiri **tidak berarti apa-apa sampai ada Asal-Usul Hukum yang sah (§3.0)**. Urutan wajib:

1. **Origin dulu, mekanik kemudian.** Player tidak mengajukan "aku mau Hukum yang bisa X, Y, Z" secara abstrak lalu langsung dipakai. AI GM membentuk Hukum Custom **dari apa yang benar-benar terjadi di roleplay** — baru dari situ AI GM merumuskan nama, mekanik, dan batasan Hukumnya.
2. AI GM memetakan Hukum baru ke realm/stage terdekat berdasarkan deskripsi kekuatan yang muncul dari origin tersebut (bukan dari permintaan player).
3. Menerapkan QiCap yang identik — tidak ada Hukum custom yang boleh melebihi cap standar.
4. Mewajibkan **minimal 1 kelemahan signifikan** yang seimbang dengan keunikan kekuatannya (no free lunch).
5. Menolak mekanik yang secara fungsional menduplikasi Hukum lain tanpa biaya tambahan (mencegah "reskin OP").
6. Hukum Custom dicatat di **Law Origin Log** karakter sebelum bisa dipakai untuk breakthrough apapun — tidak ada pengecualian, bahkan untuk breakthrough Realm 1→2 sekalipun.

**Custom Law yang sudah diformalkan dalam dunia ini** (§8.3):
- **Hukum Bayangan Darah** (Blood Shadow Alliance)
- **Hukum Roh Hantu** (Ghost Valley Sect)

---

## 🧪 4. Bahan Minimum Terobosan (Breakthrough Material Floor)

Formula umum (berlaku semua Hukum, n = index realm 1–9):

```
Bahan Utama Minimum = n × 10 unit material Tier-n
Inti/Core Minimum   = n unit Core Tier-n
Insight Point       = WAJIB, hanya didapat dari event naratif (tidak bisa dibeli/difarming)
```

| Realm (n) | Bahan Utama Min. | Core Min. | Insight Wajib? |
|---|---|---|---|
| 1→2 | 10 unit Tier-1 | 1 Core Tier-1 | Tidak |
| 2→3 | 20 unit Tier-2 | 2 Core Tier-2 | Ya |
| 3→4 | 30 unit Tier-3 | 3 Core Tier-3 | Ya |
| 4→5 | 40 unit Tier-4 | 4 Core Tier-4 | Ya |
| 5→6 | 50 unit Tier-5 | 5 Core Tier-5 | Ya + Restu Sekte/Guru |
| 6→7 | 60 unit Tier-6 | 6 Core Tier-6 | Ya + Trial Kehampaan |
| 7→8 | 70 unit Tier-7 | 7 Core Tier-7 | Ya + **Tribulasi Petir wajib** |
| 8→9 | 80 unit Tier-8 | 8 Core Tier-8 | Ya + Tribulasi Petir Agung |

📌 **Anti-cheat:** Material Tier harus match ±1 dari Realm player. Tier-9 material dipakai player Realm-2 otomatis ditolak sistem (overflow protection).

---

## ⚡ 5. Tribulasi Petir (Heavenly Tribulation) — Realm 7 ke atas

```
Tribulation_Damage = BasePunishment(realm) × KarmaModifier × BoltFactor × Random(0,8–1,2)
```

- **BasePunishment(realm)** = 5% dari `QiCap(realm, Puncak)` per bolt.
- **BoltFactor**: Minor Tribulation = 3 bolt, Major = 5 bolt, Full = 7 bolt, Heaven-Defying = 9 bolt.
- **Random(0,8–1,2)**: variasi acak per bolt, di-seed sistem (bukan pilihan player) — mencegah manipulasi hasil.

### 🕯️ KarmaModifier (formula karma)

```
Karma_Score   = Merit_Points − Sin_Points
KarmaModifier = clamp(1 + (Sin_Points − Merit_Points) / 1000, 0,5, 3,0)
```

- Merit tinggi → KarmaModifier turun sampai minimum **0,5** (Tribulasi lebih ringan).
- Sin tinggi → KarmaModifier naik sampai maksimum **3,0** (Tribulasi jauh lebih berat, trope "menentang langit").
- Merit/Sin **hanya** bertambah lewat aksi naratif yang divalidasi GM — **tidak bisa** diklaim sendiri oleh player.

**Contoh perhitungan** (Realm 7→8, Full Tribulation, karma netral):
```
BasePunishment = 5% × QiCap(7, Puncak) = 5% × (312.500 × 2,0) = 31.250 per bolt
KarmaModifier  = 1,0 (netral)
BoltFactor     = 7 bolt
Total Damage   = 31.250 × 1,0 × 7 × (rata-rata 1,0) ≈ 218.750 damage kumulatif
```

HP/Vitalitas karakter (lihat `11_VITALITY_HUNGER_SYSTEM.md`) harus lebih besar dari total ini (atau punya mitigasi tervalidasi GM: pil pelindung, formasi, bantuan sesama) atau karakter mengalami **Qi Deviation Permanen / Kematian Tribulasi** sesuai tingkat kegagalan.

---

## ⚖️ 6. Formula Karma (Merit & Sin)

| Aksi | Efek |
|---|---|
| Menyelamatkan nyawa tak bersalah | +Merit (5–20, tergantung skala) |
| Menjunjung janji/keadilan sekte | +Merit (5–15) |
| Membunuh orang tak bersalah | +Sin (15–30) |
| Memakai teknik/jalur terlarang (mis. Gu iblis) | +Sin (10–25) |
| Merampok/menipu demi keuntungan pribadi | +Sin (5–15) |

`Karma_Score` memengaruhi: KarmaModifier Tribulasi (§5), reputasi sekte/NPC, serta akses ke quest/Dao Insight tertentu (jalur "Righteous Dao" vs "Devil Dao").

---

## 🛡️ 7. Checklist Validasi AI GM (WAJIB DICEK SETIAP BREAKTHROUGH)

- [ ] Hukum/teknik yang dipakai sudah tercatat di **Law Origin Log** karakter (Guru/Manual/Pencerahan tervalidasi, bukan deklarasi sepihak saat momen terobosan)?
- [ ] Qi reported ≤ `QiCap(realm, stage)` saat ini?
- [ ] Bahan & Core memenuhi tabel minimum §4?
- [ ] Material tier dalam rentang ±1 dari realm player?
- [ ] Insight/comprehension sudah divalidasi lewat event naratif (bukan klaim sepihak)?
- [ ] Untuk realm 7+: Tribulasi sudah dijalankan dengan formula §5 (bukan di-skip)?
- [ ] Karma_Score dihitung dari log aksi tervalidasi, bukan input player langsung?
- [ ] Semua perubahan log bertimestamp & tidak diubah mundur?

Jika salah satu poin gagal → breakthrough **DITOLAK**, sistem memberi alasan spesifik ke player.

---

## 🗺️ 8. Integrasi dengan World Document (Peta Wilayah & Sekte)

### 8.1 Kepadatan Qi per Wilayah (Qi Density Modifier)

Memengaruhi regenerasi qi Hukum Dao Abadi (§3.C) dan ketersediaan bahan terobosan (§4).

| Wilayah | Qi Density Modifier | Catatan |
|---|---|---|
| Central Plains | ×1,0 (Normal) | Padat penduduk, qi stabil tapi tak istimewa — cocok untuk semua Hukum tanpa penalti/bonus |
| Azure Mountain Range | ×1,5 (Kaya) | Spirit vein alami di puncak gunung → lokasi favorit Golden Bell Monastery, cocok untuk Hukum Raga Sejati |
| Southern Demon Domain | ×1,2 (Kaya tapi Impure/Chaotic) | Qi "kotor"/liar — bonus regen untuk Hukum Gu Karma & Hukum Qi Naga Api, tapi −20% efisiensi untuk Hukum Dao Abadi murni |
| Eastern Sea Region | ×1,1 (Sedang, atribut Air) | Cocok untuk varian Dao Abadi beratribut Air; Hukum Qi Naga Api kena −25% efektivitas |
| Northern Desolate Territory | ×0,6 (Miskin, dingin) | Regen qi lambat untuk semua Hukum; ideal untuk kultivator es/roh. Hukum Dao Abadi kena penalti dasar −50% **ditambah** −0,6 modifier ini (stacking, sangat berat) |
| Western Sacred Deserts | ×0,4 (Termiskin) | Qi paling langka di dunia. Hanya kultivator Realm 4 (Core Formation) ke atas yang disarankan menyeberang. Azure Cloud Temple bertahan lewat Dao Insight welas asih, bukan kelimpahan qi |

### 8.2 Pemetaan Sekte → Hukum Kultivasi Utama

| Sekte/Faksi | Wilayah | Hukum Utama | Alasan |
|---|---|---|---|
| Heavenly Sword Pavilion | Central Plains | Hukum Dao Abadi (varian Pedang) | Disiplin kaku & "kemurnian jalan" cocok filosofi Dao Insight |
| Profound Heaven Sect | Central Plains | Hukum Dao Abadi (standar) | Sekte ortodoks besar, sumber daya qi terbanyak lewat kekayaan/kekuasaan |
| Silver Rain Sword School | Central Plains | Hukum Raga Sejati + Dao Abadi (hybrid) | Sekte menengah, lebih fleksibel, cocok murid yang gabung 2 jalur dasar |
| Golden Bell Monastery | Azure Mountain Range | Hukum Raga Sejati | Nama "Golden Bell" = klasik body-tempering; tertutup & jarang campur urusan luar cocok progres lambat tapi kokoh |
| Demonic Flame Palace | Southern Demon Domain | Hukum Qi Naga Api | Nama "Api Abadi" & basis di Hellfire Island cocok mutlak dengan Fire Core/Battle Qi |
| Nine Serpent Den | Southern Demon Domain | Hukum Gu Karma (varian Racun) | Ahli racun tertutup — Gu beracun/parasit representasi alami jalur ini |
| Seven Sins Cult | Southern Demon Domain | Hukum Gu Karma (varian instan, Sin tinggi) | "Janji kekuatan instan" = trope klasik Gu shortcut berbahaya, Sin Points naik sangat cepat |
| Blood Shadow Alliance | Southern Demon Domain (tersebar) | Custom Law: **Hukum Bayangan Darah** | Tanpa struktur tetap → Custom Law fleksibel, kelemahan wajib: qi tidak stabil bila jauh dari target kontrak (§8.3) |
| Jade Purity Palace | Eastern Sea Region | Hukum Dao Abadi (varian Air/Laut) | Penjaga jalur laut ortodoks, selaras qi Air alami wilayah |
| Whitecloud Medicine Hall | Northern Desolate Territory | *Bukan Hukum tempur* — Jalur Alkimia/Support | Netral, fokus pengobatan; tidak butuh Qi Cap tempur, tapi tetap tunduk cap qi standar bila anggotanya bertarung |
| Ghost Valley Sect | Northern Desolate Territory | Custom Law: **Hukum Roh Hantu** | Ilmu roh ekstrem → butuh Custom Law baru (§8.3), Sin Points naik otomatis |
| Azure Cloud Temple | Western Sacred Deserts | Hukum Dao Abadi (varian Welas Asih/Buddhis) | Qi miskin di wilayah ini dikompensasi lewat Dao Insight welas asih |
| 🆕 Perkumpulan Pisau Sunyi | Lintas Wilayah | Custom Law: **Hukum Pisau Sunyi** | Organisasi pembunuh bayaran paling terstruktur di dunia, kode "satu kontrak satu nyawa" butuh mekanik disiplin tersendiri (§8.3) |
| 🆕 Kelompok Racun Bayangan | Lintas Wilayah (kota besar) | Hukum Gu Karma (varian Racun) | Spesialis racun kontrak — selaras Nine Serpent Den, skala jauh lebih kecil & fokus urban |

### 8.3 Custom Law Baru (Diformalkan sesuai Faksi, tetap tunduk §3.E)

**Hukum Bayangan Darah** (Blood Shadow Alliance)
- Sumber daya: Qi standar, tapi efektivitas naik/turun tergantung "Kontrak Aktif" (target pembunuhan/misi).
- Kelemahan wajib: tanpa kontrak aktif, QiCap efektif turun 15% (representasi "tanpa ideologi tetap, kekuatan kurang stabil").
- Tetap tunduk `QiCap(realm, stage)` standar — hanya efisiensi yang berubah, bukan batas maksimum.

**Hukum Roh Hantu** (Ghost Valley Sect)
- Sumber daya: Qi Roh (Soul Qi), dikonversi dari vitalitas/jiwa alih-alih qi lingkungan — cocok wilayah miskin qi (Northern Territory, ×0,6).
- Mekanik unik: bisa "meminjam" qi dari roh yang telah diikat (mirip Gu, tapi berbasis jiwa bukan makhluk hidup).
- Kelemahan wajib: setiap penggunaan qi roh berlebih menambah Sin Points otomatis (+3–8 per pemakaian besar).

**🆕 Hukum Pisau Sunyi** (Perkumpulan Pisau Sunyi — lihat detail lengkap di `33_PERKUMPULAN_PISAU_SUNYI.md`)
- Sumber daya: Qi standar, LawHPMultiplier ×0,8, LawAttackMultiplier ×1,25 (lihat `11_VITALITY_HUNGER_SYSTEM.md` §1.2 dan `12_COMBAT_SYSTEM.md` §3.1).
- Mekanik unik: +10% HitChance selama kontrak resmi (lewat Token Pisau) masih berjalan dan belum diselesaikan/dibatalkan — representasi fokus ekstrem eksekutor profesional.
- Kelemahan wajib: melanggar kode "satu kontrak, satu nyawa, tanpa pengecualian" (membatalkan/menggagalkan kontrak di tengah jalan) memicu +20 Sin Points instan (terpisah dari Sin Points normal akibat membunuh, §6) DAN −10% QiCap efektif selama 7 hari in-game. Anggota yang belum pernah menerima kontrak resmi tidak mendapat bonus HitChance apa pun.

### 8.4 Lokasi Trial & Tribulasi (mengikat §4 & §5 ke peta)

| Event | Lokasi yang Ditetapkan | Alasan |
|---|---|---|
| Trial Kehampaan (Realm 6→7) | Reruntuhan Gushatta, Western Sacred Deserts | Reruntuhan kota kuno = tempat alami untuk trial kuno/formasi purba |
| Tribulasi Petir Realm 7→8 | Platform Tribulasi milik masing-masing sekte besar (mis. puncak Heavenly Sword Pavilion, Hellfire Island, dsb) | Butuh langit terbuka bebas formasi pelindung — tiap sekte besar punya "Tribulation Platform" sendiri |
| Tribulasi Petir Agung (Realm 8→9) | **Hanya boleh terjadi di Scar of Heaven** (perbatasan Central Plains–Southern Demon Domain) | "Retakan langit" satu-satunya di dunia yang memungkinkan Tribulasi Agung — event sangat langka & terikat lokasi (anti-cheat: tidak bisa breakthrough Realm 9 sembarangan tempat) |

### 8.5 Sumber Bahan Terobosan per Wilayah (mengikat §4 ke peta)

| Material/Insight | Sumber di World Document |
|---|---|
| Bahan Tier Api (Hukum Naga Api) | Hellfire Island (Southern Demon Domain) |
| Bahan Tier Racun/Gu (Hukum Gu Karma) | Desa Duchong & Thousand Poison Marsh (Southern Demon Domain) |
| Bahan Tier Es/Roh (Hukum Roh Hantu) | Desa Bingxin & Ghost Valley (Northern Desolate Territory) |
| Bahan Tier Air/Mutiara Spiritual (Dao Abadi varian Laut) | Desa Zhenzhu & Kepulauan Perak Kecil (Eastern Sea Region) |
| Pil & Alkimia umum (semua Hukum) | Whitecloud Medicine Hall (Northern Territory) |
| Artefak/Insight Point langka | Reruntuhan Gushatta & Menara Bintang Jatuh (Western Sacred Deserts) |

📌 **Anti-cheat tambahan:** breakthrough yang mengklaim bahan dari wilayah tertentu HARUS konsisten dengan jarak tempuh & waktu perjalanan karakter (`01_WORLD_OVERVIEW_AND_CAPITAL.md`) — tidak bisa "instan" dapat bahan dari Hellfire Island kalau posisi karakter sedang di Northern Territory tanpa waktu tempuh yang logis.

---

## 🔄 9. Migrasi RealmBase v3.0 (WAJIB DIBACA AI GM)

Tabel RealmBase di §2 direvisi oleh admin dunia ini: **Fondasi Fana (Realm 1) sekarang RealmBase = 0** (mortal sejati benar-benar tanpa Qi Cap, by design, untuk realisme). Konsekuensinya, **setiap Realm 2–9 sekarang bernilai 1/5 dari versi sebelumnya**. Ini BUKAN typo — sudah dikonfirmasi eksplisit oleh admin.

### 9.1 Tabel Konversi Cepat (Qi Cap Lama → Qi Cap Baru)

Gunakan tabel ini untuk mengoreksi angka "Qi Cap: X" apa pun yang masih tertulis dengan nilai LAMA di file manapun (`01`–`08`, `14`–`37`, `players.md`):

| Realm & Stage | Qi Cap LAMA (v2.x, jangan dipakai lagi) | Qi Cap BARU (v3.0, resmi) |
|---|---|---|
| Mortal Foundation, Awal/Menengah/Puncak | 100 / 150 / 200 | **0 / 0 / 0** |
| Qi Refining, Awal/Menengah/Puncak | 500 / 750 / 1.000 | **100 / 150 / 200** |
| Foundation Establishment, Awal/Menengah/Puncak | 2.500 / 3.750 / 5.000 | **500 / 750 / 1.000** |
| Core Formation, Awal/Menengah/Puncak | 12.500 / 18.750 / 25.000 | **2.500 / 3.750 / 5.000** |
| Nascent Soul, Awal/Menengah/Puncak | 62.500 / 93.750 / 125.000 | **12.500 / 18.750 / 25.000** |
| Soul Transformation, Awal/Menengah/Puncak | 312.500 / 468.750 / 625.000 | **62.500 / 93.750 / 125.000** |
| Void Severing, Awal/Menengah/Puncak | 1.562.500 / 2.343.750 / 3.125.000 | **312.500 / 468.750 / 625.000** |
| Tribulation Crossing, Awal/Menengah/Puncak | 7.812.500 / 11.718.750 / 15.625.000 | **1.562.500 / 2.343.750 / 3.125.000** |
| Immortal Ascension, Awal/Menengah/Puncak | 39.062.500 / 58.593.750 / 78.125.000 | **7.812.500 / 11.718.750 / 15.625.000** |

Pola cepat: **Qi Cap Baru = Qi Cap Lama ÷ 5** untuk Realm 2 ke atas. Realm 1 (Mortal Foundation) selalu **0**, berapa pun stage-nya.

### 9.2 Aturan Wajib untuk AI GM
1. **Realm & Stage tertulis di NPC/karakter TETAP SAH** (mis. "Kaisar Long Wei, Nascent Soul, Puncak" tidak berubah) — yang berubah HANYA angka Qi Cap turunannya.
2. Jika sebuah NPC/karakter menyebutkan angka "Qi Cap: X" yang cocok dengan kolom **LAMA** di tabel §9.1 → AI GM diam-diam mengoreksinya ke kolom **BARU** saat dipakai dalam sesi (tidak perlu mengoreksi teks file, cukup pakai angka yang benar saat menghitung).
3. Formula HP (`11_VITALITY_HUNGER_SYSTEM.md`), AttackPower & Defense (`12_COMBAT_SYSTEM.md`), MonsterHP/MonsterAttackPower (`13_BESTIARY.md`) semuanya diturunkan dari QiCap — otomatis ikut terkoreksi begitu QiCap dihitung ulang dengan benar, tanpa perlu formula terpisah diubah.
4. Status file per Agustus 2026: **Migrasi v3.0 TUNTAS di seluruh proyek.** Tabel resmi di `09` §2 (file ini), cheat-sheet di `00_CORE_RULES_AI_GM.md` §3, contoh HP di `11_VITALITY_HUNGER_SYSTEM.md`, seluruh tabel monster di `13_BESTIARY.md`, seluruh ~107 angka Qi Cap NPC individual di `01`–`08`, dan contoh karakter di `players.md` semuanya **sudah** memakai RealmBase v3.0. File sekte `14`–`37` tidak menyimpan angka Qi Cap eksplisit sama sekali (hanya Realm & Stage dalam teks), jadi otomatis tidak terdampak dan tidak perlu migrasi. §9.1 tetap dipertahankan sebagai referensi cepat & jaring pengaman bila suatu saat ada angka lama yang lolos tak terdeteksi.
