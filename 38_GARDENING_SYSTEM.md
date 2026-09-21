# 🌱 Lingyuan World — Sistem Gardening

> **Modul:** 38 — Gardening System
> **Status:** Canonical System
> **Prinsip:** Source-Traceable — Time-Bound — Anti-Cheat — Integrated with Economy & Player State
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` (aturan inti & batas waktu), `10_ECONOMY_SYSTEM.md` (Tier/Grade, Origin & harga), `11_VITALITY_HUNGER_SYSTEM.md` (Stamina/Satiety), `13_BESTIARY.md` (lingkungan liar bila relevan), file regional `02`–`07` (lokasi & kondisi wilayah), `players/` (data awal/save resmi yang dikelola Admin)

---

## 0. Filosofi Sistem

Gardening adalah aktivitas dunia yang mengubah bahan tanam yang memiliki sumber sah menjadi **Plant Instance**, kemudian melalui waktu dunia, kondisi tanah, air, dan maintenance menjadi tanaman yang dapat dipanen.

AI GM WAJIB membedakan **niat pemain** dari **hasil nyata**. Pernyataan "aku menanam" tidak otomatis berarti tanaman berhasil tumbuh, matang, atau menghasilkan output.

### Aturan Emas Gardening

- Setiap bahan tanam WAJIB memiliki sumber yang dapat dilacak.
- Penanaman WAJIB menghasilkan **Plant Instance** yang dapat dilacak selama sesi.
- Tidak ada pertumbuhan instan.
- Standard irrigation dan soil care adalah maintenance; keduanya TIDAK menciptakan time-skip.
- Durasi pertumbuhan mengikuti waktu dunia dan batas sistem tanaman.
- Tidak boleh menciptakan tanaman, benih, pupuk, alat, hasil panen, grade, kualitas, efek, atau harga baru tanpa basis canon.
- Data yang belum diketahui = `???`.
- Data canon yang belum cukup untuk menentukan hasil = `UNRESOLVED`.
- Kegagalan hanya boleh terjadi bila ada basis kondisi, lingkungan, tindakan, atau aturan canon yang mendukungnya.
- Semua output bernilai ekonomi tunduk pada `10_ECONOMY_SYSTEM.md`.

---

## 1. Alur Gardening Canon

```
Plant Source
→ Acquisition
→ Plant Instance
→ Planting
→ Soil / Irrigation / Maintenance
→ Growth
→ Harvest
→ Output Instance
→ Usage / Economy
→ Origin / History
→ Checkpoint / Save
```

Setiap tahap harus memiliki hubungan sebab-akibat yang dapat diverifikasi.

---

## 2. Sumber & Akuisisi Bahan Tanam

Bahan tanam dapat berasal dari sumber canon yang sah, misalnya:

- inventory awal karakter;
- hasil panen sebelumnya;
- loot yang memang mencantumkan bahan tanam;
- pembelian atau perdagangan yang tervalidasi;
- pemberian NPC atau player lain yang tercatat;
- sumber regional lain yang memang disebut dalam canon.

Jika sumber bahan tanam tidak diketahui atau tidak tercatat, AI GM TIDAK BOLEH menganggap bahan tersebut ada.

**Format minimum provenance:**

| Field | Nilai |
|---|---|
| Plant / Planting Material | Nama canon atau `???` |
| Source | Asal bahan |
| Acquisition | Cara diperoleh |
| Acquisition Time | Waktu dunia |
| Owner | Pemilik saat ini |

---

## 3. Plant Classification & Canon Boundary

Gardening WAJIB membedakan jenis objek flora sebelum membuat Plant Instance. Kategori berikut adalah kategori sistem, bukan daftar spesies baru:

| Classification | Makna Runtime |
|---|---|
| Cultivable Plant | Tanaman yang canon memang dapat ditanam/dipelihara melalui Gardening |
| Wild Plant | Tanaman yang canon tumbuh liar; tidak otomatis dapat dijadikan Plant Instance |
| Spiritual Plant | Tanaman yang canon memang diklasifikasikan sebagai spiritual |
| Demonic Plant | Tanaman yang canon memang memiliki sifat/klasifikasi demonic |
| Plant Creature | Makhluk flora dari Bestiary; tidak otomatis merupakan tanaman budidaya |
| UNKNOWN / UNRESOLVED | Data canon belum cukup untuk menentukan klasifikasi |

**Aturan pengikat:**
- Wild Plant dan Cultivable Plant TIDAK BOLEH dianggap identik.
- Plant Creature TIDAK BOLEH otomatis dipanen, ditanam, atau diperbanyak sebagai tanaman.
- Spiritual Plant atau Demonic Plant TIDAK otomatis berarti Tier/Grade tinggi.
- Klasifikasi hanya mengikuti canon yang sudah ada; modul 38 tidak menciptakan spesies baru.

### 3.1 Existing Lore Integration

Gardening wajib membaca lore regional dan fasilitas yang sudah canon sebelum menentukan apakah suatu flora dapat dibudidayakan. Contoh yang harus dipertahankan sebagai data Lore, bukan dibuat ulang oleh modul 38:

- Hutan Lingzhu di Qingyun memiliki zona flora bambu dengan perilaku pertumbuhan/regenerasi yang berbeda; data tersebut harus diperlakukan sebagai aturan flora regional ketika Gardening memang berinteraksi dengan bambu di lokasi tersebut.
- Pegunungan Huijin di Moyuan memiliki tanah subur tetapi beracun dan canon menyatakan hanya tanaman demonic yang tumbuh di sana. Gardening tidak boleh memperlakukan lokasi tersebut sebagai lahan universal.
- Fasilitas sekte yang canon memiliki kebun/herbal, termasuk Balai Yunyao dan fasilitas lain yang memang disebut dalam modul sekte/regional, dapat menjadi lokasi Gardening atau sumber produksi hanya sejauh fungsi tersebut benar-benar didukung canon.

Modul 38 tidak boleh mengubah deskripsi Lore menjadi angka produksi, durasi, quantity, harga, atau bonus baru tanpa sumber canon.

## 4. Wild Gathering vs Cultivated Gardening

Pengumpulan tanaman liar dan budidaya adalah dua jalur runtime berbeda.

```
Wild Plant
→ Valid Wild Location
→ Gathering
→ Resource / Material Instance
→ Usage / Economy
```

sedangkan:

```
Cultivable Plant
→ Planting Material
→ Plant Instance
→ Growth / Maintenance
→ Harvest
→ Output Instance
```

Hasil gathering liar TIDAK otomatis menjadi Plant Instance. Sebaliknya, keberadaan Plant Instance tidak berarti tanaman tersebut tumbuh liar di lokasi itu. Bila canon memang mengizinkan bagian tanaman liar menjadi bahan tanam, acquisition tersebut harus dicatat terlebih dahulu dan divalidasi sebagai planting material.

## 5. Plant Creature vs Cultivable Plant

Objek yang tercatat sebagai Flora/Plant Creature dalam Bestiary diperlakukan sebagai entitas hidup dengan aturan Bestiary. Ia tidak otomatis dapat ditanam sebagai crop, dipanen sebagai item Gardening, dijadikan benih, diperbanyak, atau dipindahkan menjadi Plant Instance.

Semua tindakan tersebut membutuhkan basis canon spesifik untuk entitas tersebut.

## 6. Plant Instance

Saat bahan tanam benar-benar ditanam, AI GM membuat state runtime **Plant Instance**.

| Field | Keterangan |
|---|---|
| Plant | Tanaman canon |
| Category | Ordinary Plant / Spiritual Plant bila canon mendukung |
| Source | Sumber bahan tanam |
| Location | Lokasi penanaman |
| Planted Time | Waktu dunia saat ditanam |
| Growth Duration | Durasi canon yang berlaku atau `???` |
| Soil Condition | Kondisi tanah |
| Water Status | Status air |
| Maintenance Status | Status maintenance |
| Growth Status | Status pertumbuhan |
| Condition | Kondisi tanaman |
| Harvest Status | Belum dipanen / dipanen / gagal / `UNRESOLVED` |

Plant Instance adalah objek runtime. Ia tidak boleh muncul kembali hanya karena pemain menyatakan pernah menanam tanaman tanpa state yang dapat dilacak.

---

## 7. Penanaman

Penanaman WAJIB divalidasi terhadap:

1. bahan tanam yang benar-benar dimiliki;
2. lokasi yang memungkinkan aktivitas tersebut;
3. kondisi tanah atau media yang relevan bila canon mengaturnya;
4. waktu dan aksi yang wajar menurut aturan inti;
5. metode penanaman yang diketahui.

Jika salah satu unsur penting tidak diketahui, AI GM menggunakan `???` atau `UNRESOLVED`, bukan mengarang.

Penanaman tidak sama dengan keberhasilan pertumbuhan.

---

## 8. Soil, Water, Environment & Maintenance

Maintenance standar mencakup:

- **Soil Care** — perawatan kondisi tanah sesuai metode yang canon;
- **Standard Irrigation** — penyiraman standar;
- pemeriksaan kondisi tanaman;
- kebutuhan khusus yang memang dinyatakan canon.

Maintenance:

- mengubah kondisi runtime hanya bila tindakan tersebut secara logis dan canon memang memberi perubahan;
- tidak mempercepat waktu dunia secara otomatis;
- tidak menjamin tanaman pasti tumbuh;
- tidak menghasilkan item baru dengan sendirinya.

Pupuk, alat khusus, nutrisi spiritual, metode mutasi, atau efek khusus hanya boleh digunakan jika sudah memiliki basis canon.

---

## 9. Growth Duration

### 6.1 Ordinary Plant

**Batas maksimum pertumbuhan: 7 hari**, bergantung pada jenis tanaman.

### 6.2 Spiritual Plant

**Batas maksimum pertumbuhan: 15 hari**, bergantung pada jenis tanaman.

Batas maksimum bukan jaminan keberhasilan panen dan bukan berarti semua tanaman tumbuh selama tepat batas tersebut.

Durasi aktual harus berasal dari canon tanaman atau data yang tersedia. Jika jenis tanaman atau durasi aktual belum diketahui, gunakan `???` / `UNRESOLVED`.

### 6.3 Status Pertumbuhan

| Status | Arti |
|---|---|
| PLANTED | Baru ditanam |
| GROWING | Sedang tumbuh |
| MATURE | Mencapai kondisi matang menurut canon |
| HARVESTED | Sudah dipanen |
| FAILED | Pertumbuhan gagal berdasarkan sebab yang tervalidasi |
| UNRESOLVED | Canon belum cukup menentukan status |

Tidak boleh mengubah `GROWING` menjadi `MATURE` hanya karena pemain menunggu satu giliran tanpa waktu dunia yang benar-benar berlalu.

---

## 10. Integrasi Waktu & Aksi

Gardening mengikuti batas waktu pada `00_CORE_RULES_AI_GM.md` §1.9:

- aktivitas non-kultivasi tidak boleh melompati lebih dari **3 jam** dalam satu prompt;
- gardening tidak mendapat pengecualian kultivasi;
- pertumbuhan tanaman berlangsung berdasarkan **waktu dunia yang benar-benar berlalu**, bukan jumlah pesan;
- maintenance tidak boleh digunakan sebagai metode untuk melakukan time-skip tersembunyi;
- jika pemain meminta rentang waktu panjang, AI GM harus menerapkan aturan checkpoint dan validasi waktu yang berlaku.

Dengan demikian, "menyiram tanaman" adalah aksi, sedangkan "tanaman telah tumbuh selama 3 hari" adalah hasil dari waktu dunia yang memang telah berlalu.

---

## 11. Environmental Dependency

Pengaruh lingkungan hanya diterapkan jika didukung canon.

Faktor yang dapat diperiksa bila memang tersedia:

- wilayah;
- lokasi;
- kondisi tanah;
- ketersediaan air;
- Qi Density;
- kondisi khusus tanaman;
- event dunia;
- gangguan eksternal.

AI GM TIDAK BOLEH memberikan bonus atau penalti pertumbuhan hanya karena suatu lokasi terdengar cocok.

---

## 12. Harvest Validation

Panen hanya sah jika:

- Plant Instance benar-benar ada;
- tanaman telah mencapai status matang menurut canon;
- durasi pertumbuhan yang diperlukan telah terpenuhi;
- lokasi dan kondisi tanaman masih valid;
- metode panen sesuai bila canon mengaturnya.

Hasil panen dibuat sebagai **Output Instance**.

| Field | Keterangan |
|---|---|
| Source Plant Instance | Plant Instance asal |
| Harvest Time | Waktu dunia |
| Method | Cara panen |
| Output | Hasil canon |
| Quantity | Jumlah canon |
| Tier / Grade | Hanya jika canon menentukan |
| Condition | Kondisi output |
| Origin | Riwayat asal |

Jika quantity, grade, atau fungsi output tidak memiliki basis canon, jangan mengarang nilainya.

---

## 13. Economy & Origin

Output gardening yang bernilai ekonomi tunduk pada `10_ECONOMY_SYSTEM.md`.

Khususnya:

- Tier dan Grade mengikuti sistem ekonomi yang sudah canon;
- harga tidak boleh ditentukan sepihak oleh player;
- item bernilai yang memerlukan Item Origin Log harus memiliki provenance dari Plant Instance;
- hasil panen tidak boleh langsung berubah menjadi mata uang tanpa transaksi atau penggunaan yang sah;
- proses crafting/alchemy berikutnya harus dapat menunjuk Output Instance sebagai sumber material.

Gardening tidak membuat jalur ekonomi baru di luar sistem ekonomi canon.

---

## 14. History & Provenance

Riwayat minimum harus dapat ditelusuri:

```
Plant Source
→ Acquisition
→ Plant Instance
→ Maintenance / Growth
→ Harvest
→ Output Instance
→ Usage / Economy
→ Origin
→ History
```

Jika output diproses menjadi item lain, provenance diteruskan ke proses berikutnya dan tidak boleh terputus.

---

## 15. Runtime & Checkpoint

Gardening state hidup di runtime selama sesi.

Qwen/AI GM TIDAK menulis state runtime langsung ke GitHub.

Jika pemain meminta checkpoint, AI GM menyusun kondisi terakhir yang benar-benar terjadi, termasuk bila relevan:

- Plant Instance;
- lokasi;
- waktu tanam;
- waktu dunia terakhir;
- growth status;
- soil condition;
- water status;
- maintenance;
- condition;
- harvest status;
- Output Instance;
- provenance dan history.

Alur persistence:

```
Runtime Gardening State
→ Checkpoint
→ Admin Verification
→ Official Player Save
```

Admin adalah pihak yang memperbarui file karakter resmi di repository setelah checkpoint diverifikasi.

---

## 16. Anti-Exploit

AI GM WAJIB menolak:

- benih muncul tanpa sumber;
- tanaman muncul tanpa Plant Instance;
- panen tanpa tanaman matang;
- pertumbuhan instan;
- watering yang sekaligus dianggap time-skip;
- maintenance yang otomatis menjamin sukses;
- output quantity/grade yang dibuat tanpa canon;
- penggunaan tanaman atau hasil panen yang tidak dapat ditelusuri;
- perubahan status tanaman tanpa waktu dunia atau sebab yang sah;
- penghapusan failure/condition hanya karena pemain mengulang klaim;
- pemindahan Plant Instance tanpa perubahan lokasi yang sah;
- penggunaan data tanaman dari karakter lain sebagai milik karakter saat ini tanpa transfer yang tervalidasi.

---

## 17. Alchemy & Crafting Integration

Gardening hanya menyediakan Output Instance sebagai bahan; ia tidak menciptakan resep.

### 17.1 Alchemy

Jika canon alchemy/sect menyatakan suatu hasil Gardening sebagai bahan resep:

```
Harvest Output Instance
→ Valid Alchemy Raw Material
→ Existing Canon Recipe
→ Processing
→ Alchemy Output
→ Origin / History
```

Jika tidak ada resep canon yang menyebut material tersebut, AI GM TIDAK BOLEH membuat resep baru. `???` atau `UNRESOLVED` digunakan bila hubungan bahan belum dapat ditentukan.

### 17.2 Crafting

Jika canon crafting/economy menyatakan output Gardening sebagai material:

```
Harvest Output Instance
→ Valid Crafting Material
→ Existing Canon Recipe / Process
→ Processing
→ Crafted Output
→ Origin / History
```

`ECONOMY_ORACLE.md` adalah sistem bot Discord dan BUKAN sumber crafting/alchemy Gardening RP. Ia tidak boleh digunakan untuk membuat hubungan material, resep, item, harga, atau grade dalam Lingyuan World.

## 18. Seed Propagation & Post-Harvest State

Panen TIDAK otomatis menghasilkan seed. Setiap jenis tanaman harus mengikuti aturan reproduksi/propagasi yang memang tersedia dalam canon.

| Kondisi Canon | Hasil |
|---|---|
| Tanaman memang menghasilkan seed/planting material | Output propagation dapat dibuat sesuai canon |
| Tanaman tumbuh kembali setelah panen | Plant Instance dapat memasuki state recovery/regrowth sesuai canon |
| Tanaman mati setelah panen | Plant Instance berakhir sesuai aturan canon |
| Hanya bagian tertentu yang dipanen | Plant Instance tetap ada bila canon mendukung |
| Data tidak tersedia | `???` / `UNRESOLVED` |

Growth awal, regrowth, regeneration, dan recovery setelah harvest adalah konsep yang berbeda. Durasi masing-masing tidak boleh disamakan kecuali canon memang menyamakannya.

## 19. Canon Boundary

Gardening TIDAK secara otomatis menambahkan:

- jenis tanaman baru;
- benih baru;
- pupuk;
- alat berkebun;
- resep;
- hasil panen;
- harga;
- grade;
- efek spiritual;
- bonus wilayah;
- loot;
- NPC;
- lokasi kebun.

Jika data tersebut belum ada di World Bible, statusnya adalah `???` atau `UNRESOLVED` sampai Admin menetapkannya sebagai canon.

---


## 20.1 NPC / Sect Garden Production

Kebun milik NPC, sekte, biara, perguruan, atau organisasi diperlakukan sebagai production source hanya bila fasilitas tersebut memang canon memiliki fungsi kebun/herbal atau produksi tanaman.

Production NPC/Sect TIDAK sama dengan inventory tanpa batas.
- Keberadaan kebun sekte TIDAK otomatis berarti selalu ada stok hasil panen.
- Jumlah produksi, frekuensi panen, kapasitas lahan, tenaga kerja, dan stok hanya digunakan bila ada basis canon atau state runtime.
- NPC dapat mengelola kebun sesuai peran dan akses mereka, tetapi hasil produksi tetap tunduk pada waktu dunia, Plant Instance, maintenance, maturity, dan harvest validation.
- Output kebun NPC/sekte tidak otomatis masuk inventory pemain.
- Output kebun tidak otomatis masuk pasar; diperlukan distribusi, penjualan, penggunaan internal, atau transfer yang tervalidasi.

## 20.2 Regional Supply Integration

Jika hasil Gardening benar-benar dilepas ke pasar regional, jalurnya adalah:

Harvested Output Instance → Valid Allocation / Transaction → Regional Supply → Active Market Supply → Demand / Market Conditions → FinalPrice → Transaction Ledger

Harvested Output ≠ Market Supply. Output yang disimpan, dipakai internal sekte, diberikan, rusak, atau belum dialokasikan ke pasar tidak dihitung sebagai ActiveSupply.

AI GM TIDAK BOLEH membuat Regional Supply dari klaim bahwa sebuah wilayah punya banyak kebun saja. Supply harus memiliki sumber produksi dan output yang benar-benar tervalidasi.

## 20.3 Maintenance → Time / Stamina Semantics

Gardening membedakan durasi aksi, waktu dunia, dan biaya Stamina.

- Action Duration = waktu yang dipakai melakukan tindakan gardening.
- World Time = waktu dunia yang benar-benar berlalu setelah tindakan.
- Stamina Cost = biaya fisik tindakan yang mengikuti skala universal pada 11_VITALITY_HUNGER_SYSTEM.md §3A.
- Growth Time = waktu biologis/canon tanaman; bukan hadiah dari maintenance.

Soil Care, Standard Irrigation, Inspection, Planting, dan Harvest adalah aksi dan tetap tunduk pada batas aksi Core Rules.

Stamina TIDAK BOLEH diada-adakan. Jika biaya Stamina belum ditentukan canon, nilainya ??? / UNRESOLVED; AI GM tidak boleh membuat angka baru. Maintenance dapat memengaruhi Condition / Maintenance Status, tetapi tidak mengubah jam tanam menjadi jam panen secara otomatis.

## 20.4 Qi Density Interaction

Qi Density regional hanya menjadi input Gardening jika canon tanaman, lokasi, atau aturan khusus secara eksplisit menghubungkannya dengan pertumbuhan atau kondisi tanaman.

- Qi Density TIDAK memberikan bonus pertumbuhan otomatis.
- Qi Density tinggi tidak mengubah Ordinary Plant menjadi Spiritual Plant.
- Qi Density rendah tidak otomatis menyebabkan tanaman gagal.
- Jika tanaman memang Qi-sensitive menurut canon, efeknya mengikuti aturan tanaman tersebut; jika besaran efek belum tersedia, gunakan ??? / UNRESOLVED.
- Modifier Qi Density untuk kultivasi karakter tidak boleh dipindahkan ke Gardening tanpa aturan Gardening yang sah.

## 20.5 Custom-Content Boundary

Konten pada 39_CUSTOM_EVENTS.md–42_CUSTOM_TECHNIQUES.md adalah canon kustom yang dikelola Admin, tetapi scope override harus dibatasi pada data yang memang didefinisikan oleh konten tersebut.

Custom Sect, Law, Event, atau Technique dapat mengubah/memperluas data spesifik yang memang dicatat sebagai bagian dari konten tersebut, tetapi TIDAK otomatis mengubah hukum waktu, formula ekonomi, formula Vitality, aturan provenance, batas Gardening, atau aturan global lain.

Jika custom content ingin memberi efek pada Gardening, efek tersebut harus tertulis jelas dalam canon kustom. Jika scope tidak jelas, gunakan UNRESOLVED sampai Admin memperjelas batasnya.

## 20.6 Tier / Grade Inheritance Rules

Tier dan Grade adalah atribut ekonomi output/item; keduanya bukan atribut otomatis dari kategori tanaman.

1. Plant Classification (Ordinary / Spiritual / Demonic) TIDAK menentukan Tier atau Grade dengan sendirinya.
2. Output panen mewarisi Tier/Grade hanya jika canon tanaman/output atau aturan proses memang menetapkannya.
3. Provenance/origin dapat diteruskan dari Plant Instance ke Output Instance, tetapi provenance bukan berarti Tier/Grade otomatis diwariskan.
4. Saat Output Instance diproses melalui alchemy/crafting, Tier/Grade hasil akhir TIDAK otomatis sama dengan bahan. Gunakan Tier/Grade yang ditentukan recipe/process canon; jika tidak ada, ??? / UNRESOLVED.
5. Processing hanya menghasilkan perbedaan Tier/Grade bila proses canon mendukungnya.
6. Status fasilitas, reputasi sekte, kekayaan, atau realm pengelola tidak otomatis menaikkan Tier/Grade hasil panen.

Plant Classification ≠ Tier/Grade
Provenance Inheritance ≠ Tier/Grade Inheritance
Processing Input Tier/Grade ≠ Automatic Output Tier/Grade

## 20. Checklist Validasi AI GM

- [ ] Objek flora sudah diklasifikasikan dengan benar (Cultivable / Wild / Spiritual / Demonic / Plant Creature / UNKNOWN)?
- [ ] Planting material benar-benar ada?
- [ ] Source dan acquisition dapat dilacak?
- [ ] Plant Instance sudah dibuat?
- [ ] Lokasi penanaman valid dan kompatibel dengan environmental lore?
- [ ] Waktu aksi sesuai §1.9 Core Rules?
- [ ] Growth duration tidak melebihi 7 hari untuk Ordinary Plant?
- [ ] Growth duration tidak melebihi 15 hari untuk Spiritual Plant?
- [ ] Tidak ada time-skip tersembunyi?
- [ ] Maintenance tidak dianggap sebagai instant growth?
- [ ] Harvest hanya dilakukan setelah maturity tervalidasi?
- [ ] Output memiliki basis canon?
- [ ] Wild Gathering tidak tercampur dengan Cultivated Gardening?
- [ ] Plant Creature tidak diperlakukan sebagai crop tanpa canon?
- [ ] Seed/propagation hanya diberikan bila canon mendukung?
- [ ] Post-harvest state mengikuti jenis tanaman/canon?
- [ ] Alchemy/crafting hanya menggunakan recipe/process yang sudah canon?
- [ ] Tier/Grade tidak dikarang?
- [ ] Origin/History tetap tersambung?
- [ ] Checkpoint menggunakan state runtime terakhir?
- [ ] Official save hanya dilakukan setelah verifikasi Admin?
- [ ] NPC/Sect garden production memiliki Plant Instance dan output nyata, bukan stok fiktif?
- [ ] Harvested Output dibedakan dari Regional Supply/Active Market Supply?
- [ ] Action Duration, World Time, dan Stamina Cost tidak dicampur?
- [ ] Qi Density hanya memengaruhi Gardening jika ada basis canon eksplisit?
- [ ] Custom content hanya meng-override scope yang memang didefinisikan?
- [ ] Provenance diwariskan tanpa menganggap Tier/Grade otomatis diwariskan?
- [ ] Tier/Grade output processing berasal dari recipe/process canon?

Jika salah satu poin gagal, hasil gardening harus ditahan, dikoreksi, atau ditandai `UNRESOLVED` sesuai kondisi.

---

## 21. Status Modul

**CANONICAL — SYSTEM MODULE**

Modul ini mendefinisikan mekanik gardening, tetapi tidak menambahkan daftar tanaman, benih, pupuk, alat, hasil panen, resep, atau item baru. Data tersebut hanya sah setelah ditetapkan Admin sebagai canon.
