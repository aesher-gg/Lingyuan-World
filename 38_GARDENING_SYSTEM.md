# 🌱 Lingyuan World — Sistem Gardening

> **Modul:** 38 — Gardening System
> **Status:** Canonical System
> **Prinsip:** Source-Traceable — Time-Bound — Anti-Cheat — Lore-Integrated
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md`, `10_ECONOMY_SYSTEM.md`, `11_VITALITY_HUNGER_SYSTEM.md`, `13_BESTIARY.md`, file regional `02`–`07`, file sekte/faksi terkait, `players/`

---

## 0. Batas Canon

Gardening hanya memformalkan tanaman, kebun, bahan tanam, lingkungan, dan hasil yang **sudah memiliki basis canon**. Modul ini tidak menciptakan spesies, benih, pupuk, alat, resep, hasil panen, harga, efek, atau loot baru.

Jika data belum cukup:
- fakta yang belum diketahui = `???`;
- canon yang ada tetapi belum cukup untuk resolusi = `UNRESOLVED`.

**Player intent ≠ hasil.** Klaim "aku menanam", "aku menyiram", atau "aku panen" hanya merupakan niat sampai validasi runtime terpenuhi.

---

## 1. Klasifikasi Gardening

Gardening WAJIB membedakan objek berikut:

| Kelas | Definisi | Boleh menjadi Plant Instance? |
|---|---|---|
| **Cultivable Plant** | Tanaman yang memang dapat dibudidayakan berdasarkan canon | Ya |
| **Wild Plant** | Tanaman liar yang ditemukan/gathered tanpa Plant Instance | Tidak |
| **Plant Creature** | Makhluk flora/berbasis tanaman dari Bestiary | Tidak otomatis; diperlakukan sebagai creature |
| **Planting Material** | Benih, stek, akar, bagian tanaman, atau material tanam lain yang canon memang dapat ditanam | Menjadi sumber Plant Instance setelah planting tervalidasi |
| **Output Instance** | Hasil sah dari panen | Bukan Plant Instance baru kecuali output tersebut secara canon memang merupakan bahan tanam dan kemudian ditanam secara terpisah |

### 1.1 Category Tanaman

Field `Category` pada Plant Instance hanya boleh memakai klasifikasi yang didukung data tanaman. Klasifikasi yang sudah digunakan sistem adalah:
- **Ordinary Plant**;
- **Spiritual Plant**.

Data lore yang secara eksplisit menunjukkan sifat **Demonic** harus tetap dapat direkam tanpa otomatis menyamakan Demonic dengan Spiritual, Tier, atau Grade.

**Plant Type, Tier, Grade, Quality, dan Condition adalah field berbeda.**

---

## 2. Lore Integration

Gardening WAJIB membaca lore wilayah/lokasi yang relevan sebelum menentukan kompatibilitas tanaman.

Contoh canon yang sudah ada dan harus diperlakukan sebagai data dunia:
- Tianzhou memiliki Lembah Xuewu sebagai lokasi herba spiritual pemurni darah.
- Qingyun memiliki lokasi flora seperti Hutan Lingzhu dan Jurang Hanxu; sifat dan hasilnya mengikuti lore lokasi tersebut.
- Moyuan memiliki Pegunungan Huijin, yang secara eksplisit disebut subur tetapi beracun dan hanya tanaman demonic yang tumbuh.
- Beberapa sekte memiliki fasilitas kebun yang sudah tercatat, termasuk **Kebun Obat Kekayaan** Sekte Xuanyuan, **Kebun aprikot** Perguruan Luohua, **Kebun Herbal Tinggi** Biara Jinguang, dan **Kebun Obat Luas** Balai Yunyao.

Lore tersebut **bukan** izin otomatis untuk menanam semua tanaman. Kompatibilitas harus tetap diverifikasi.

---

## 3. Plant Source & Acquisition

Setiap Planting Material WAJIB memiliki provenance:

| Field | Wajib |
|---|---|
| Plant / Material | Nama canon atau `???` |
| Source | Asal |
| Acquisition | Cara diperoleh |
| Acquisition Time | Waktu dunia |
| Owner | Pemilik |
| Transfer History | Bila pernah berpindah |

Sumber sah dapat berupa:
- inventory/save resmi;
- hasil panen sebelumnya;
- loot yang memang mencantumkan bahan tanam;
- pembelian/perdagangan tervalidasi;
- hadiah/transfer NPC atau player yang tercatat;
- sumber regional canon.

Bahan tanam tanpa sumber tervalidasi **tidak boleh digunakan**.

---

## 4. Plant Instance

Plant Instance adalah objek runtime yang dibuat hanya setelah planting tervalidasi.

| Field | Keterangan |
|---|---|
| Plant | Tanaman canon |
| Category | Ordinary / Spiritual / kategori canon lain |
| Planting Material | Material yang dipakai |
| Source | Provenance material |
| Owner | Pemilik Plant Instance |
| Access Policy | Hak akses |
| Location | Lokasi kebun |
| Planted Time | Waktu dunia |
| Growth Duration | Durasi canon atau `???` |
| Soil Condition | Kondisi tanah |
| Water Status | Status dan sumber air |
| Maintenance Status | Maintenance yang sudah dilakukan |
| Environment Status | Validasi lingkungan |
| Growth Status | Status pertumbuhan |
| Condition | Kondisi tanaman |
| Harvest Status | Status panen |
| Post-Harvest State | State setelah panen bila relevan |

Plant Instance tidak boleh dipulihkan hanya dari klaim pemain tanpa state yang dapat dilacak.

---

## 5. Wild Plant vs Cultivated Plant

**Wild Plant** dan **Cultivated Plant** adalah dua state berbeda.

- Wild gathering menghasilkan bahan dari sumber liar; tidak menciptakan Plant Instance.
- Planting menghasilkan Plant Instance hanya bila bahan tanam sah.
- Wild Plant tidak otomatis menjadi milik player hanya karena ditemukan.
- Plant Instance tidak boleh diklaim sebagai Wild Plant untuk menghindari aturan growth/maintenance.
- Hasil gathering liar tidak otomatis dapat ditanam; kemampuan propagasi harus didukung canon tanaman.

Alur:

`Wild Source → Gathering → Output/Material Instance`

berbeda dari:

`Planting Material → Plant Instance → Growth → Harvest → Output Instance`

---

## 6. Plant Creature vs Cultivable Plant

Makhluk flora/Plant Creature di `13_BESTIARY.md` diperlakukan sebagai creature.

**Plant Creature ≠ Cultivable Plant.**

Mengalahkan atau menemukan Plant Creature tidak otomatis menghasilkan benih atau Plant Instance. Loot hanya sah bila Bestiary/canon menyatakannya.

---

## 7. Planting Validation

Sebelum membuat Plant Instance, AI GM WAJIB memeriksa:

1. material benar-benar dimiliki;
2. provenance valid;
3. tanaman/material memang dapat ditanam menurut canon;
4. lokasi memungkinkan aktivitas;
5. soil/media kompatibel atau statusnya dapat ditentukan;
6. water requirement dapat dipenuhi bila relevan;
7. metode planting diketahui bila canon mengaturnya;
8. owner/access dapat ditentukan.

Jika syarat penting tidak dapat ditentukan, hasil = `UNRESOLVED`, bukan asumsi.

---

## 8. Soil & Environment Resolution

`Soil Condition` tidak boleh diperlakukan sebagai angka abstrak yang selalu cocok.

Minimal resolusi lingkungan:

| Status | Arti |
|---|---|
| COMPATIBLE | Canon mendukung kecocokan |
| INCOMPATIBLE | Canon menunjukkan kondisi tidak cocok |
| UNKNOWN | Data tidak tersedia |
| CONTAMINATED | Ada pencemaran canon yang relevan |
| SPECIAL | Ada kondisi khusus canon yang harus dipenuhi |
| UNRESOLVED | Data ada tetapi belum cukup untuk menentukan hasil |

Faktor yang dapat diperiksa bila tersedia:
- wilayah/lokasi;
- sifat tanah;
- racun;
- death-Qi;
- demonic/chaotic Qi;
- kondisi air;
- kondisi khusus tanaman;
- event dunia.

**Qi Density tidak memberikan bonus/penalti otomatis.** Pengaruhnya terhadap tanaman hanya sah jika tanaman, lokasi, atau hukum dunia yang relevan secara eksplisit mendukungnya.

---

## 9. Water & Irrigation Validation

Standard irrigation adalah maintenance, bukan time-skip.

Sebelum irrigation, AI GM memeriksa:
- sumber air;
- kepemilikan/akses sumber;
- kualitas air bila canon menentukan;
- jumlah/consumption bila canon menentukan;
- kecocokan air dengan tanaman bila canon menentukan.

Jika quantity atau quality belum memiliki basis canon, jangan mengarang angka atau efek.

Air yang digunakan untuk menyiram tidak otomatis menjadi item baru atau menghasilkan growth progress instan.

---

## 10. Maintenance

Maintenance standar:
- Soil Care;
- Standard Irrigation;
- Condition Check;
- kebutuhan khusus yang memang tercatat canon.

Maintenance harus memiliki:
- actor;
- target Plant Instance;
- waktu dunia;
- durasi bila diketahui;
- hasil kondisi bila didukung canon;
- biaya Stamina bila sistem Vitality mengaturnya.

Jika biaya Stamina atau durasi belum ditentukan canon, gunakan `???`/`UNRESOLVED`; jangan menetapkan angka baru.

Gardening berlaku untuk mortal maupun cultivator. Memiliki Qi **tidak otomatis** memberi bonus gardening.

---

## 11. Growth & World Time

### 11.1 Batas Sistem

- **Ordinary Plant:** maksimum **7 hari**.
- **Spiritual Plant:** maksimum **15 hari**.

Batas maksimum bukan durasi default dan bukan jaminan panen.

Durasi aktual hanya boleh berasal dari canon tanaman/data runtime yang sah. Jangan menurunkan durasi dari Tier, Grade, harga, rarity, realm, atau asumsi lokasi.

### 11.2 Growth Status

| Status | Arti |
|---|---|
| PLANTED | Baru ditanam |
| GROWING | Dalam pertumbuhan |
| MATURE | Matang menurut canon |
| HARVESTED | Sudah dipanen |
| FAILED | Gagal dengan sebab tervalidasi |
| UNRESOLVED | Canon belum cukup |

Growth mengikuti waktu dunia yang benar-benar berlalu. Maintenance tidak menciptakan time-skip.

---

## 12. Failure & Environmental Hazard

Failure hanya sah bila ada sebab yang dapat diverifikasi, misalnya:
- kondisi tanah incompatible;
- air tidak sesuai bila canon menyatakannya;
- kebutuhan khusus tidak terpenuhi;
- lingkungan berbahaya;
- gangguan eksternal;
- kerusakan tanaman yang benar-benar terjadi.

AI GM **tidak boleh** menentukan failure hanya karena tanaman dianggap langka/sulit.

Environmental hazard hanya diterapkan bila berasal dari lore wilayah/lokasi atau event canon.

Weather/season tidak menjadi mekanik tersendiri kecuali sudah didukung canon.

---

## 13. Harvest Validation & Output Instance

Panen hanya sah jika:
1. Plant Instance ada;
2. maturity tervalidasi;
3. waktu pertumbuhan terpenuhi;
4. lokasi/condition valid;
5. metode panen valid bila canon mengaturnya.

Setiap panen sah menghasilkan **Output Instance** hanya sesuai output yang memang didukung canon.

| Field | Keterangan |
|---|---|
| Source Plant Instance | ID/source tanaman |
| Harvest Time | Waktu dunia |
| Method | Metode |
| Output | Hasil canon |
| Quantity | Jumlah canon atau `???` |
| Tier | Hanya jika canon menentukan |
| Grade | Hanya jika canon menentukan |
| Quality | Hanya jika canon menentukan |
| Condition | Kondisi |
| Origin | Provenance |

**Tier ≠ Grade ≠ Quality ≠ Plant Category.**

---

## 14. Post-Harvest State

Harvest tidak otomatis berarti seluruh tanaman mati.

Post-harvest state harus mengikuti sifat tanaman yang canon:
- bagian tertentu dipanen;
- tanaman tetap hidup;
- tanaman rusak;
- tanaman mati;
- menghasilkan material propagasi;
- atau state lain yang didukung canon.

Jika sifat pascapanen tidak diketahui = `???`.

---

## 15. Seed / Propagation Rule

Tidak semua tanaman otomatis menghasilkan benih.

Propagation hanya sah bila canon tanaman mendukung metode tersebut, misalnya benih, stek, akar, atau metode lain yang telah tercatat.

Alur:

`Harvest/Propagation Source → Propagation Material Instance → Acquisition/Ownership → Planting → New Plant Instance`

Output propagasi tetap membutuhkan provenance. Tidak boleh menggandakan jumlah bahan hanya dengan deklarasi pemain.

---

## 16. Economy & Item Origin Log

Output gardening yang menjadi item/material bernilai mengikuti `10_ECONOMY_SYSTEM.md`.

Minimum chain:

`Plant Source → Acquisition → Plant Instance → Growth → Harvest → Output Instance → Item Origin Log → Usage/Economy`

Aturan:
- output tidak berubah menjadi currency tanpa transaksi/penggunaan sah;
- Tier/Grade mengikuti canon ekonomi;
- barang yang memerlukan Item Origin Log tidak boleh dipakai/dijual/ditukar tanpa origin;
- provenance tidak boleh terputus saat output dipindahkan atau diproses.

---

## 17. Alchemy Integration

Gardening **tidak menciptakan resep alchemy**.

Output gardening dapat menjadi raw material alchemy hanya jika:
1. output tersebut canon sebagai material;
2. recipe/formula yang menggunakan material itu benar-benar tersedia di canon;
3. quantity requirement tersedia;
4. processing method tersedia;
5. source Output Instance tercatat.

Jika salah satu unsur formula belum tersedia, proses berhenti pada `UNRESOLVED`. Tidak boleh mengarang resep, quantity, yield, atau efek pil.

Alur:

`Harvested Output Instance → Valid Alchemy Material → Canon Recipe → Processing → Alchemy Output Instance → Origin Inheritance`

---

## 18. Crafting Integration

Aturan identik berlaku untuk crafting.

`Harvested Output Instance → Valid Crafting Material → Canon Recipe → Processing → Crafted Output Instance → Origin Inheritance`

Gardening tidak otomatis membuat material menjadi bahan crafting hanya karena material tersebut berbentuk kayu, daun, akar, buah, atau herba.

---

## 19. Sect / NPC Garden Production

Kebun sekte, organisasi, NPC, dan fasilitas dunia yang sudah tercatat sebagai kebun tetap dianggap sebagai **existing lore**, bukan kebun baru.

Produksi hanya boleh terjadi bila canon mendukung:
- jenis tanaman;
- kapasitas/keberadaan kebun;
- pemelihara;
- siklus produksi;
- hasil;
- tujuan penggunaan.

Output produksi menjadi aset pihak yang memiliki/mengelola kebun, bukan otomatis milik player.

Jika kebun NPC/sect memasok pasar, jalurnya:

`Garden Production → Regional Supply → Market Supply → Demand → Final Price`

Tetapi tidak semua hasil panen otomatis masuk pasar.

---

## 20. Ownership & Multiplayer Access

Setiap Garden/Plant Instance WAJIB memiliki:
- **Owner**;
- **Custodian** bila berbeda;
- **Access Policy**.

Default:
- planter yang sah menjadi Owner kecuali garden canon dimiliki NPC/sect;
- orang lain tidak boleh menyiram, memindahkan, memanen, atau mengambil output tanpa izin/access canon;
- transfer ownership harus menjadi event runtime yang tercatat;
- aksi player lain tidak otomatis mengubah ownership.

Model interaksi yang sah:

`Player A plants → Player B allowed to maintain → Player C allowed to harvest`

hanya jika permission masing-masing terpenuhi.

**Catatan shared runtime:** modul ini mendefinisikan permission gardening, tetapi tidak mengklaim sudah menyediakan authoritative shared runtime lintas-chat untuk seluruh dunia. Tanpa shared runtime, interaksi lintas-chat harus dianggap `UNRESOLVED` sampai state bersama diverifikasi.

---

## 21. Gardening Technique Interaction

Technique bukan sinonim gardening action.

Teknik hanya boleh memengaruhi gardening jika:
- teknik tersebut canon;
- efeknya relevan dengan gardening;
- syarat penggunaan terpenuhi;
- efeknya benar-benar dinyatakan.

Qi tidak otomatis mempercepat growth.

Teknik seperti **Pemeliharaan Kebun Sadar** dapat dicatat sebagai teknik karakter, tetapi efek gardening-nya tidak boleh diperluas di luar canon teknik tersebut.

---

## 22. Vitality & Action Cost

Gardening adalah aktivitas fisik dan harus mengikuti `11_VITALITY_HUNGER_SYSTEM.md` serta batas aksi `00_CORE_RULES_AI_GM.md`.

Untuk setiap aksi, runtime idealnya mencatat:
- Actor;
- Action;
- Target;
- Start Time;
- End Time/duration;
- Stamina Cost;
- Result.

Jika biaya belum canon = `???`, bukan nol secara otomatis.

---

## 23. Existing Player Garden: Azmud

State kebun Azmud di `players/Azmud.md` adalah **official player state**, bukan daftar tanaman global.

Setiap entri harus dibaca sebagai state yang sudah ada dan ditelusuri ke Plant Instance/Planting Material sesuai data yang tersedia.

Canon yang saat ini tercatat:
- Semak Duri Miasma;
- Rumput Darah [Mutasi Demonic];
- 2 Benih Rumput Darah [Normal];
- 1 Benih Teh Fana [Tianzhou];
- 3 Benih Akar Penenang [Tier-1].

Status yang tidak memiliki provenance, exact planted time, growth duration, atau output basis lengkap tidak boleh diisi ulang dengan tebakan. Field yang hilang tetap `???`/`UNRESOLVED`.

**Tier-1 pada Benih Akar Penenang tidak boleh dianggap sebagai Grade.**

---

## 24. Checkpoint & Persistence

Gardening state hidup di runtime.

Alur persistence:

`Runtime Gardening State → Checkpoint → Admin Verification → Official Player Save`

Qwen/AI GM tidak menulis GitHub secara langsung.

Checkpoint minimal mencakup bila relevan:
- Garden;
- Plant Instance;
- owner/access;
- location;
- planting material;
- source;
- planted time;
- world time;
- soil;
- water;
- maintenance;
- growth status;
- condition;
- harvest;
- Output Instance;
- provenance/history.

---

## 25. Anti-Exploit

DILARANG:
- material tanam tanpa source;
- tanaman tanpa Plant Instance;
- wild plant diperlakukan sebagai cultivated plant;
- Plant Creature diperlakukan sebagai tanaman budidaya;
- growth instan;
- watering = time-skip;
- Qi = growth boost otomatis;
- seed duplication;
- harvest tanpa maturity;
- output quantity/grade/quality tanpa canon;
- recipe alchemy/crafting buatan GM;
- garden NPC/sect otomatis menjadi milik player;
- player lain mengakses/memanen tanpa permission;
- post-harvest state ditebak;
- cross-chat state dianggap sinkron tanpa verifikasi;
- weather/season dijadikan aturan baru tanpa canon.

---

## 26. Canon Integration Checklist

- [ ] Plant classification valid?
- [ ] Existing lore plant/location sudah diperiksa?
- [ ] Source & acquisition valid?
- [ ] Plant Instance ada?
- [ ] Wild vs cultivated benar?
- [ ] Plant Creature vs cultivable plant benar?
- [ ] Soil/environment tervalidasi?
- [ ] Water source/quality tervalidasi?
- [ ] Qi Density tidak diberi efek otomatis?
- [ ] Maintenance/action/time/Stamina valid atau `UNRESOLVED`?
- [ ] Growth duration sesuai canon dan batas 7/15 hari?
- [ ] Failure punya sebab?
- [ ] Harvest tervalidasi?
- [ ] Output Instance dibuat dari source yang benar?
- [ ] Item Origin Log tersambung?
- [ ] Alchemy recipe benar-benar canon?
- [ ] Crafting recipe benar-benar canon?
- [ ] Seed propagation didukung canon?
- [ ] Post-harvest state didukung canon?
- [ ] NPC/sect production tidak menjadi milik player tanpa transfer?
- [ ] Ownership/access multiplayer tervalidasi?
- [ ] Checkpoint mengikuti runtime state?
- [ ] Official save hanya setelah verifikasi Admin?

---

## 27. Status Modul

**CANONICAL — PRIORITY 1 INTEGRATION IMPLEMENTED**

Modul ini sekarang mengintegrasikan klasifikasi, lore regional, provenance, wild/cultivated separation, Plant Creature boundary, soil/water validation, harvest/output, economy origin, alchemy/crafting bridges, NPC/sect gardens, propagation, post-harvest state, dan gardening access control tanpa menambahkan spesies atau resep baru.
