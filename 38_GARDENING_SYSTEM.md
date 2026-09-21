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

Untuk setiap aksi, runtime mencatat:
- Actor;
- Action;
- Target;
- Start Time;
- End Time/duration;
- Stamina Cost;
- Result.

Aturan:
- Aksi gardening non-kultivasi mengikuti batas waktu non-kultivasi maksimal **3 jam per turn**.
- Gardening tidak boleh digunakan untuk menyamarkan time-skip.
- Stamina Cost **tidak diasumsikan 0**. Jika canon belum menetapkan biaya untuk aksi tertentu, nilainya = `???`/`UNRESOLVED` sampai ada basis canon.
- Satiety tetap berjalan sesuai waktu dunia.
- Kelelahan, cedera, atau kondisi tubuh yang sudah tercatat dapat membatasi hasil aksi.
- Teknik tidak menghapus biaya fisik kecuali efek teknik canon memang menyatakannya.
- Tidak ada angka Stamina baru yang ditambahkan oleh modul ini.

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

## 27. Priority 2 Integration

### 27.1 Qi Density Interaction

Qi Density **tidak memiliki efek gardening universal**.

Pengaruh Qi Density hanya dapat diterapkan bila:
- plant canon menyatakan kebutuhan/sensitivitas terhadap Qi;
- lokasi canon menyatakan hubungan tersebut;
- atau hukum dunia/technique canon secara eksplisit memberikan efek.

Tidak boleh membuat:
- growth multiplier otomatis;
- bonus harvest otomatis;
- quality/grade naik otomatis;
- tanaman Spiritual otomatis tumbuh lebih cepat.

Jika hubungan Qi Density dengan tanaman belum diketahui = `UNRESOLVED`.

### 27.2 Plant Tier vs Grade

Gardening mengikuti pemisahan dari `10_ECONOMY_SYSTEM.md`:
- **Plant Category** = klasifikasi tanaman;
- **Tier** = tingkat material/item;
- **Grade** = kualitas;
- **Quality** = kondisi/atribut kualitas bila canon menyediakannya;
- **Condition** = keadaan runtime.

Tidak boleh mengubah Ordinary/Spiritual/Demonic menjadi Tier atau Grade secara otomatis.

Contoh: `Tier-1` pada Benih Akar Penenang tetap **Tier 1**, bukan Grade.

### 27.3 Regional Production & Supply

Jika hasil kebun masuk ke pasar, produksi mengikuti rantai:

`Garden Production → Regional Supply → Active Supply → Demand Index → Final Price`

Aturan:
- hasil kebun tidak otomatis masuk pasar;
- pemilik/manager garden menentukan penggunaan sesuai canon;
- output yang dikonsumsi sendiri, disimpan, diberikan, atau diproses tidak dihitung sebagai market supply;
- hanya unit yang benar-benar ditawarkan untuk pasar yang menjadi `Active Supply`;
- kapasitas produksi harus berasal dari garden/plant state yang nyata;
- tidak boleh menciptakan stok tak terbatas;
- Final Price tetap tunduk pada `10_ECONOMY_SYSTEM.md`;
- provenance/Item Origin Log tetap wajib.

### 27.4 Gardening Technique Interaction

Technique gardening adalah modifier terpisah dari action gardening.

AI GM wajib memeriksa:
1. technique benar-benar canon;
2. character memiliki/mengetahui technique;
3. target dan kondisi penggunaan terpenuhi;
4. efek technique relevan dengan action;
5. efek tidak diperluas melebihi teks canon.

**Qi cultivation ≠ gardening technique.**

Contoh yang sudah tercatat pada lore: **Pemeliharaan Kebun Sadar** dapat diperiksa sebagai technique bila character benar-benar memilikinya. Modul ini tidak menetapkan bonus growth, pengurangan waktu, bonus yield, atau pengurangan Stamina tanpa efek canon yang eksplisit.

### 27.5 Failure Conditions

Failure gardening harus memiliki sebab runtime/lore yang dapat ditelusuri.

Kategori:
- **Environmental Failure:** lokasi/soil/water tidak kompatibel atau hazard canon aktif;
- **Maintenance Failure:** kebutuhan canon tidak terpenuhi;
- **Material Failure:** planting material rusak/tidak valid;
- **Time/State Failure:** growth belum mencapai state yang diperlukan;
- **External Failure:** gangguan NPC, creature, event, atau kerusakan eksternal yang benar-benar terjadi.

Failure tidak boleh diputuskan hanya dari rarity, Tier, Grade, harga, atau keinginan GM.

### 27.6 Environmental Hazard Resolution

Hazard lingkungan hanya aktif jika ada basis canon lokasi/event.

Resolution:
- **NONE:** tidak ada hazard relevan;
- **PRESENT:** hazard aktif dan dapat memengaruhi target;
- **MITIGATED:** hazard ada tetapi efeknya dinetralisasi oleh perlindungan canon;
- **UNKNOWN:** data tidak cukup;
- **UNRESOLVED:** data saling bertentangan/tidak cukup untuk resolusi.

Hazard tidak boleh dibuat hanya untuk menghukum player. Sebaliknya, ketiadaan hazard juga tidak boleh diasumsikan bila lore jelas menyatakan bahaya.

### 27.7 Runtime Checklist Priority 2

Sebelum resolution gardening:
- [ ] Time action ≤ 3 jam untuk aksi non-kultivasi?
- [ ] Stamina Cost berasal dari canon atau ditandai `UNRESOLVED`?
- [ ] Satiety mengikuti waktu dunia?
- [ ] Qi Density tidak diberi efek otomatis?
- [ ] Plant Category ≠ Tier ≠ Grade ≠ Quality ≠ Condition?
- [ ] Supply pasar hanya menghitung output yang benar-benar ditawarkan?
- [ ] Technique benar-benar dimiliki dan efeknya canon?
- [ ] Failure memiliki sebab tervalidasi?
- [ ] Environmental hazard memiliki basis lore/event?
- [ ] Tidak ada angka growth/yield/bonus baru yang diciptakan?

---

## 28. Status Modul

**CANONICAL — PRIORITY 1 + PRIORITY 2 INTEGRATION IMPLEMENTED**

Priority 2 sekarang mencakup:
- stamina/time semantics;
- Qi Density boundary;
- Plant Tier vs Grade separation;
- regional production/supply integration;
- gardening technique validation;
- failure conditions;
- environmental hazard resolution.

Tidak ada spesies, item, resep, harga, yield, bonus, atau angka Stamina baru yang diciptakan.

---
## 29. Operational Canon Chain
Gardening wajib di-resolve dalam urutan berikut:
Lore Tanaman → Plant Registry → Environment → Plant Instance → World Time → Growth → Maintenance → Harvest → Output → Propagation/Post-Harvest → Alchemy/Crafting/Economy → Shared Runtime → Checkpoint → Official Save
Tidak boleh melompati node yang diperlukan.

### 29.1 Lore Tanaman
Lore tanaman adalah sumber fakta tentang identitas, kategori/nature, habitat, pertumbuhan, bahan tanam, bagian panen, propagasi, kebutuhan lingkungan, hubungan alchemy/crafting, risiko atau efek. Lore yang belum tersedia tidak boleh dibuat oleh Gardening System.

### 29.2 Plant Registry
Setiap tanaman yang dipakai runtime harus dapat dipetakan ke record registry.
| Field | Nilai |
|---|---|
| Plant ID | Identifier stabil |
| Canon Name | Nama canon |
| Object Type | Plant / Planting Material / Output / Plant Creature |
| Cultivable | YES / NO / UNKNOWN |
| Nature | Ordinary / Spiritual / Demonic / UNKNOWN |
| Source Reference | Modul/file sumber |
| Habitat | Canon atau ??? |
| Growth Duration | Canon atau ??? |
| Propagation | Canon atau ??? |
| Harvest Part | Canon atau ??? |
| Environment Requirement | Canon atau ??? |
| Alchemy Use | Canon atau ??? |
| Crafting Use | Canon atau ??? |
| Post-Harvest | Canon atau ??? |
UNKNOWN tidak boleh diubah menjadi YES karena asumsi genre.

### 29.3 Environment Resolution
Plant Registry dibaca bersama lokasi runtime.
Plant Requirement → Garden Location → Regional Lore → Soil → Water → Environmental Hazard → Compatibility Result
Result hanya: COMPATIBLE, INCOMPATIBLE, UNKNOWN, CONTAMINATED, SPECIAL, UNRESOLVED.

### 29.4 Plant Instance
Plant Instance hanya dibuat setelah material tanam, provenance, ownership/access, planting dan environment tervalidasi. Setiap instance memiliki identity/state sendiri; dua tanaman spesies sama tidak boleh dianggap satu instance.

### 29.5 World Time
Setiap state growth menggunakan Planted Time dan Current World Time.
Elapsed Growth Time = Current World Time - Planted Time.
Elapsed time bukan action duration; maintenance bukan growth time; menunggu tanpa world-time resolution bukan growth; satu turn tidak boleh menjadi time-skip.

### 29.6 Growth Resolution
Growth hanya dari elapsed world time, canon growth duration, environment, condition, maintenance requirement, dan external event yang benar-benar terjadi. Jika duration tidak tersedia, jangan memaksa MATURE.

### 29.7 Maintenance
Maintenance adalah event runtime: Actor → Action → Target Plant Instance → World Time → Cost → Result. Maintenance tidak otomatis mempercepat growth, menaikkan Grade/Tier, menambah yield, atau menghapus hazard tanpa canon.

### 29.8 Harvest
MATURE + Valid Harvest → Output Instance + Post-Harvest State. Output tidak boleh dibuat sebelum source Plant Instance dan harvest event valid.

### 29.9 Output
Output wajib mempertahankan provenance: Output → Source Plant Instance → Planting Material → Acquisition → Original Source. Processing tidak boleh memutus origin chain.

### 29.10 Propagation / Post-Harvest
Propagation adalah event baru, bukan cloning otomatis. Canon Propagation Source → Propagation Material Instance → Ownership → Planting Validation → New Plant Instance. Post-harvest mengikuti record tanaman; jika belum diketahui = ???.

### 29.11 Alchemy / Crafting / Economy
Output hanya dapat memasuki sistem lain bila bridge canon tersedia.
Output → Valid Material → Canon Recipe → Processing → New Output.
Untuk economy: Output → Origin Log → Usage / Trade → Regional Supply bila benar-benar ditawarkan → Demand → Price. Tidak ada automatic market entry.

## 30. Shared Runtime Gardening State
Karena Gardening dapat disentuh player/NPC berbeda, state bersama wajib memakai satu record authoritative.
| Field | Wajib |
|---|---|
| Garden ID | Ya |
| Garden Owner | Ya |
| Access Policy | Ya |
| Location | Ya |
| Plant Instance IDs | Ya |
| Current World-Time Marker | Ya |
| Active Maintenance Events | Bila ada |
| Active Harvest Events | Bila ada |
| Output Instances | Bila ada |
| External Effects | Bila ada |
| Last Verified Checkpoint | Ya |

### 30.1 Cross-Chat Rule
Jika dua player berada di chat berbeda, state gardening tidak boleh dianggap sinkron hanya berdasarkan klaim salah satu chat. State lintas-chat hanya sah jika berasal dari shared authoritative runtime state atau checkpoint yang telah diverifikasi Admin. Jika tidak tersedia: Cross-Chat Gardening State = UNRESOLVED.

### 30.2 Concurrency
Dua aksi terhadap Plant Instance yang sama harus di-resolve berdasarkan urutan waktu. Contoh A menyiram → B memanen harus memeriksa World Time A < World Time B dan access B valid. Jika event tidak dapat diurutkan secara authoritative, hasil = UNRESOLVED.

### 30.3 Ownership
Ownership tidak berubah hanya karena player menyentuh, menyiram, menemukan kebun, atau membantu maintenance. Transfer ownership harus berupa event canon/runtime yang tercatat.

## 31. Checkpoint Contract
Checkpoint gardening adalah snapshot state runtime, bukan narasi bebas.
Minimum: Garden → Plant Instances → World Time → Environment → Maintenance → Growth → Harvest → Outputs → Propagation → Processing → Economy/Usage → History.
Data unknown tetap ???; data konflik tetap UNRESOLVED. Admin tidak boleh mengisi missing field dengan inferensi hanya agar save lengkap.

## 32. Official Save Contract
Official Player Save hanya diperbarui melalui:
Runtime State → Checkpoint → Admin Verification → Official Player Save
Qwen tidak boleh menulis langsung ke official player save.
Admin verification wajib memeriksa runtime event, world time, ownership/access, uniqueness Plant Instance, provenance output, propagation, canon recipes, economy consistency, unresolved fields, dan state lama yang berubah secara sah.

## 33. Garden State Identity
Garden ID ≠ Plant Instance ID ≠ Planting Material Instance ID ≠ Output Instance ID.
Identifier contoh hanya format, bukan ID canon. AI GM tidak boleh mengarang ID permanen official save tanpa checkpoint/Admin verification.

## 34. Current Canon Registry Boundary
Registry hanya berisi data yang dapat ditelusuri ke lore/repo. Data Azmud yang belum lengkap tetap memiliki gap pada exact provenance, exact planted time, canon growth duration, water source, soil specification, harvest quantity, dan Grade. Semua tetap ???/UNRESOLVED sampai ada source canon atau checkpoint terverifikasi.

## 35. Final Resolution Rule
FETCH CANON → IDENTIFY REGISTRY → RESOLVE ENVIRONMENT → VALIDATE INSTANCE → RESOLVE WORLD TIME → RESOLVE GROWTH → VALIDATE MAINTENANCE → VALIDATE HARVEST → CREATE OUTPUT → RESOLVE PROPAGATION/POST-HARVEST → RESOLVE ALCHEMY/CRAFTING/ECONOMY → UPDATE SHARED RUNTIME → CHECKPOINT → ADMIN VERIFICATION → OFFICIAL SAVE
Jika satu node wajib gagal karena data tidak tersedia, proses berhenti pada node tersebut dengan ??? atau UNRESOLVED.
Tidak ada fallback berupa improvisasi GM.


---

## 36. Operational Audit — Gardening Integration

Setelah rantai utama Gardening aktif, audit lanjutan WAJIB menjaga integrasi berikut:

### 36.1 Bestiary → Planting Material
- Flora/Plant Creature dari Bestiary tidak otomatis menjadi Cultivable Plant.
- Loot hanya dapat menjadi Planting Material bila canon loot secara eksplisit mendukung fungsi tanam.
- Jika hubungan loot → planting belum terbukti = `UNRESOLVED`.

### 36.2 Garden Facility → Production
Existing garden facility adalah lore location/facility sampai runtime production benar-benar memiliki basis canon.
Minimum production state bila tersedia:
`Garden Facility → Owner/Manager → Plant Registry → Capacity/State → Production Event → Output Instance`.
Kapasitas, siklus, yield, dan worker tidak boleh diisi dengan asumsi.

### 36.3 Environment Registry
Resolusi wajib mengikuti:
`Region → Location → Soil → Water → Environmental Condition → Compatibility`.
Tidak boleh membuat weather, season, Qi bonus, fertilizer bonus, atau environmental multiplier baru tanpa canon.

### 36.4 Growth Registry
System cap:
- Ordinary Plant ≤ 7 hari.
- Spiritual Plant ≤ 15 hari.

Species-specific duration tetap terpisah dari system cap. Bila duration spesies tidak diketahui, growth tidak boleh dipaksa menjadi MATURE.

### 36.5 Alchemy/Crafting Bridge
Tidak ada implicit conversion:
`Harvest Output → Valid Material → Canon Recipe → Processing → New Output`.
Material shape/name saja tidak cukup untuk menjadikannya recipe ingredient.

### 36.6 Propagation/Post-Harvest
Propagation adalah event tersendiri. Harvest tidak otomatis menghasilkan seed, cutting, cloning material, atau regrowth.
Post-harvest state harus plant-specific.

---

## 37. Multiplayer Gardening Resolution

Untuk interaksi antar-player:

`Actor → Permission → Target Instance → World Time → Action Order → Cost → Result → Ownership → Output`

WAJIB diverifikasi berurutan.

Contoh:
`Player A plants → Player B waters → Player C harvests → Player D trades output`

Setiap tahap harus memiliki state dan permission yang sah. Aksi player lain tidak otomatis memberi ownership.

### 37.1 Concurrency
Jika dua aksi mengenai Plant Instance yang sama:
1. gunakan authoritative world-time/event order bila tersedia;
2. proses perubahan state berdasarkan urutan tersebut;
3. bila urutan tidak dapat dibuktikan, hasil = `UNRESOLVED`;
4. jangan memilih hasil yang menguntungkan salah satu player hanya karena narasi muncul lebih dulu di chat yang tidak terhubung.

### 37.2 Cross-Chat
Chat berbeda tidak dianggap satu runtime otomatis.
State lintas-chat hanya sah bila:
- terdapat authoritative shared runtime; atau
- ada checkpoint yang telah diverifikasi Admin.

Tanpa keduanya, state lintas-chat = `UNRESOLVED`.

---

## 38. Checkpoint Conflict Resolution

Checkpoint adalah snapshot state, bukan bukti bahwa semua perubahan di dalamnya otomatis benar.

Jika terdapat checkpoint yang bertentangan:
1. identifikasi Garden/Plant/Output Instance yang sama;
2. bandingkan world-time marker;
3. bandingkan event history;
4. cek ownership/access;
5. cek provenance;
6. gunakan checkpoint yang dapat diverifikasi Admin;
7. jika konflik tidak dapat diselesaikan dari evidence canon/runtime = `UNRESOLVED`.

DILARANG:
- memilih checkpoint hanya karena lebih baru secara nama file;
- menggabungkan dua state yang saling bertentangan tanpa event resolution;
- menghapus perubahan player lain tanpa dasar.

---

## 39. Official Save Integrity

Official save hanya menerima state yang lolos:
`Runtime State → Checkpoint → Admin Verification → Official Player Save`.

Admin verification minimum:
- identity instance;
- world time;
- location;
- owner/access;
- source/provenance;
- growth/maintenance history;
- harvest event;
- output identity;
- propagation;
- alchemy/crafting processing;
- economy/use;
- unresolved/conflict fields.

Field yang belum dapat diverifikasi tetap `???` atau `UNRESOLVED`; Admin tidak boleh melengkapinya dengan asumsi.

---

## 40. Gardening Audit Stop Conditions

Gardening resolution WAJIB berhenti sebelum menghasilkan state final jika salah satu node berikut tidak memiliki basis:
- Plant Registry;
- Planting Material provenance;
- Plant Instance identity;
- Environment compatibility;
- World Time;
- Growth Duration;
- Harvest validity;
- Output basis;
- Propagation method;
- Canon recipe;
- ownership/access;
- authoritative shared runtime untuk interaksi lintas-chat.

Berhenti berarti tidak mengarang hasil; gunakan `???`/ `UNRESOLVED` sesuai jenis kekurangan data.
