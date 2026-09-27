# 🌱 Lingyuan World — Sistem Gardening (Sistem Budidaya Tanaman)

> **Modul:** 38 — Gardening System
> **Status:** Canonical System
> **Prinsip:** Source-Traceable — Time-Bound — Anti-Cheat — Integrated with Economy, Alchemy, Formations, Beasts & Player State
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` (aturan inti, batas waktu, timed processing §1.10), `10_ECONOMY_SYSTEM.md` (Tier/Grade, Origin & harga), `11_VITALITY_HUNGER_SYSTEM.md` (Stamina/Satiety), `13_BESTIARY.md` (lingkungan liar & hama spirit), file regional `02`–`07` (lokasi, iklim & kondisi wilayah), `43_ALCHEMY_PILL_SYSTEM.md` (resep & ampas alkemia), `45_ARRAY_TALISMAN_SYSTEM.md` (array pengumpul Qi & pelindung), `46_SPIRIT_BEAST_TAMING_SYSTEM.md` (pupuk kotoran spirit beast & penjaga), `players/` (data awal/save resmi yang dikelola Admin)

---

## 0. Filosofi Sistem

Gardening adalah aktivitas dunia yang mengubah bahan tanam yang memiliki sumber sah menjadi **Plant Instance**, kemudian melalui waktu dunia, kondisi tanah, air, iklim, dan maintenance menjadi tanaman yang dapat dipanen untuk kebutuhan konsumsi, alkemia, tempa, atau perdagangan.

AI GM WAJIB membedakan **niat pemain** dari **hasil nyata**. Pernyataan "aku menanam" tidak otomatis berarti tanaman berhasil tumbuh, matang, atau menghasilkan output.

### Aturan Emas Gardening

1. **Provenance Sah:** Setiap bahan tanam (benih, bibit, spora, stek) WAJIB memiliki sumber yang dapat dilacak.
2. **Plant Instance Mandatory:** Penanaman WAJIB menghasilkan **Plant Instance** yang dapat dilacak selama sesi.
3. **Tidak Ada Pertumbuhan Instan:** Durasi pertumbuhan mengikuti Waktu Dunia yang benar-benar berlalu dan batas biologis/spiritual tanaman.
4. **Maintenance Buka Time-Skip:** Standard irrigation dan soil care adalah maintenance; keduanya TIDAK menciptakan time-skip tersembunyi.
5. **Kepatuhan Canon:** Tidak boleh menciptakan tanaman, benih, pupuk, alat, hasil panen, grade, kualitas, efek, mutasi, atau harga baru tanpa basis canon atau verifikasi Admin.
6. **Data Belum Diketahui:** Data yang belum diketahui = `???`. Data canon yang belum cukup untuk menentukan hasil = `UNRESOLVED`.
7. **Kegagalan Berbasis Aturan:** Kegagalan hanya boleh terjadi bila ada basis kondisi tanah, lingkungan, hama, tindakan salah, atau aturan canon yang mendukungnya.
8. **Integrasi Ekonomi:** Semua output bernilai ekonomi tunduk pada `10_ECONOMY_SYSTEM.md`.

---

## 1. Alur Gardening Canon

```
Plant Source (Acquisition & Provenance)
➔ Soil & Location Validation
➔ Planting (Creates Plant Instance)
➔ Environment & Maintenance (Soil, Water, Fertilizer, Weather, Pests)
➔ Growth Progress (World Time Elapsed)
➔ Maturity & Quality Determination
➔ Harvest Validation (Creates Output Instance)
➔ Usage / Economy / Processing (Alchemy #43, Crafting #44, Trade #10)
➔ Checkpoint & Save State
```

Setiap tahap harus memiliki hubungan sebab-akibat yang dapat diverifikasi.

---

## 2. Sumber & Akuisisi Bahan Tanam

Bahan tanam dapat berasal dari sumber canon yang sah, misalnya:
- inventory awal karakter yang tervalidasi;
- hasil panen atau propagasi benih sebelumnya;
- loot monster/lingkungan liar yang memang mencantumkan bahan tanam (`13_BESTIARY.md`);
- pembelian atau perdagangan yang tervalidasi (`10_ECONOMY_SYSTEM.md`);
- pemberian NPC atau player lain yang tercatat di riwayat RP;
- sumber regional/sekte yang memang disebut dalam canon.

Jika sumber bahan tanam tidak diketahui atau tidak tercatat, AI GM TIDAK BOLEH menganggap bahan tersebut ada.

**Format minimum provenance bahan tanam:**

| Field | Nilai / Deskripsi |
|---|---|
| Plant / Planting Material | Nama canon bahan tanam |
| Source | Asal bahan (pembelian/wild gathering/loot/sekte) |
| Acquisition | Cara diperoleh |
| Acquisition Time | Waktu dunia saat diperoleh |
| Owner | Pemilik saat ini |

---

## 3. Plant Classification & Canon Boundary

Gardening WAJIB membedakan jenis objek flora sebelum membuat Plant Instance:

| Classification | Makna Runtime |
|---|---|
| **Cultivable Ordinary Plant** | Tanaman biasa/konsumsi yang canon dapat ditanam dan dipelihara |
| **Cultivable Spiritual Plant** | Tanaman berpati Qi/spiritual yang canon dapat dibudidayakan |
| **Cultivable Demonic Plant** | Tanaman berpati demonic/racun yang membutuhkan tanah & kondisi khusus |
| **Wild Plant** | Tanaman yang canon tumbuh liar; tidak otomatis dapat dijadikan Plant Instance tanpa metode budidaya |
| **Plant Creature** | Makhluk flora dari Bestiary (`13_BESTIARY.md`); tidak otomatis merupakan tanaman budidaya |
| **UNKNOWN / UNRESOLVED** | Data canon belum cukup untuk menentukan klasifikasi |

**Aturan pengikat:**
- Wild Plant dan Cultivable Plant TIDAK BOLEH dianggap identik.
- Plant Creature TIDAK BOLEH otomatis dipanen, ditanam, atau diperbanyak sebagai tanaman tanpa teknik khusus canon.
- Spiritual Plant atau Demonic Plant TIDAK otomatis berarti Tier/Grade tinggi.
- Klasifikasi hanya mengikuti canon yang sudah ada; modul 38 tidak menciptakan spesies baru tanpa verifikasi Admin.

### 3.1 Existing Lore Integration

Gardening wajib membaca lore regional dan fasilitas yang sudah canon sebelum menentukan apakah suatu flora dapat dibudidayakan:
- **Hutan Lingzhu (Qingyun):** Zona flora bambu dengan perilaku pertumbuhan/regenerasi khusus; diperlakukan sebagai aturan flora regional.
- **Pegunungan Huijin (Moyuan):** Tanah subur beracun; canon menyatakan hanya tanaman demonic/beracun yang tumbuh di sana.
- **Fasilitas Kebun Herbal Sekte (seperti Balai Yunyao, Perguruan Luohua, dll.):** Memiliki bonus lingkungan atau proteksi array yang relevan sesuai canon sekte masing-masing.

---

## 4. Wild Gathering vs Cultivated Gardening

Pengumpulkan tanaman liar dan budidaya adalah dua jalur runtime terpisah:

```
Wild Gathering: Valid Wild Location ➔ Gathering Roll/Action ➔ Resource/Material Instance ➔ Usage/Economy
Cultivated Gardening: Planting Material ➔ Plant Instance ➔ Growth/Maintenance ➔ Harvest ➔ Output Instance
```

Hasil gathering liar TIDAK otomatis menjadi Plant Instance. Sebaliknya, keberadaan Plant Instance tidak berarti tanaman tersebut tumbuh liar di lokasi itu. Bila bagian tanaman liar ingin dijadikan bahan tanam, acquisition tersebut harus divalidasi sebagai planting material yang cocok.

---

## 5. Plant Instance Runtime State

Saat bahan tanam benar-benar ditanam, AI GM membuat state runtime **Plant Instance**.

| Field | Keterangan |
|---|---|
| **Instance ID / Name** | Identifikasi tanaman (contoh: `Plant#001 - Rumput Lingzhu`) |
| **Plant Type** | Nama tanaman canon & klasifikasi |
| **Source / Provenance** | Asal benih/bibit |
| **Location** | Lokasi spesifik & jenis lahan/kebun |
| **Planted Time** | Waktu dunia saat ditanam |
| **Growth Duration Target** | Durasi canon yang dibutuhkan hingga matang |
| **Soil Grade & Status** | Tingkat tanah & nutrisi saat ini |
| **Water Status** | Status pengairan (Kering / Cukup / Lembap / Tergenang) |
| **Fertilizer Status** | Status pupuk/nutrisi aktif |
| **Pest / Disease Status** | Status hama/penyakit (Sehat / Hama Ringan / Blight / Terinfeksi) |
| **Environmental Effects** | Pengaruh cuaca/musim/array |
| **Health Condition (%)** | Kesehatan fisik & spiritual tanaman (0–100%) |
| **Growth Progress (%)** | Persentase pertumbuhan menuju kematangan (0–100%) |
| **Growth Status** | `PLANTED` / `GROWING` / `MATURE` / `HARVESTED` / `FAILED` / `UNRESOLVED` |

Plant Instance adalah objek runtime. Ia tidak boleh muncul kembali hanya karena pemain menyatakan pernah menanam tanpa state yang dapat dilacak.

---

## 6. Soil Quality & Spirit Soil (Tingkat Kualitas Tanah)

Kualitas tanah memengaruhi kecepatan pertumbuhan, batas kesehatan, dan potensi mutasi/kualitas hasil panen tanaman.

| Soil Tier | Jenis Tanah | Siklus Nutrisi | Modifikasi Kecepatan Tumbuh | Maksimal Plant Tier yang Didukung |
|---|---|---|---|---|
| **Tier 0** | Tanah Tandus / Berbatu | Sangat Buruk | -50% Kecepatan (-50% Health/hari jika tanpa pupuk) | Ordinary Plant saja |
| **Tier 1** | Tanah Kebun Subur Biasa | Normal | +0% Kecepatan | Ordinary Plant & Spiritual Tier 1 |
| **Tier 2** | Tanah Spirit Rendah (Low Spirit Soil) | Baik | +20% Kecepatan | Spiritual Plant Tier 1–2 |
| **Tier 3** | Tanah Spirit Menengah (Mid Spirit Soil) | Sangat Baik | +40% Kecepatan | Spiritual Plant Tier 1–3 |
| **Tier 4** | Tanah Spirit Tinggi / Purba (High Spirit Soil) | Luar Biasa | +60% Kecepatan | Spiritual Plant Tier 1–4 |
| **Special** | Tanah Demonic / Toxic Soil | Khusus | Demonic Plant +50% / Non-Demonic FAILED | Demonic Plant All Tiers |

**Aturan Upgrade Tanah:**
Tanah dapat ditingkatkan tingkatnya melalui aplikasi Pupuk Spirit secara rutin, Air Murni Qi, atau Formasi Array Pengumpul Qi (`45_ARRAY_TALISMAN_SYSTEM.md`). Upgrade tanah bersifat bertahap dan memerlukan akumulasi perawatan.

---

## 7. Pengairan, Pupuk & Nutrisi Spirit (Irrigation & Fertilization)

### 7.1 Status Pengairan (Irrigation)
- **Kering (Dry):** Health tanaman berkurang 10% per 24 jam Waktu Dunia.
- **Cukup (Optimal):** Pertumbuhan berjalan normal (100%).
- **Lembap Spirit (Qi Watered):** Penyiraman menggunakan Air Mata Air Qi/Air Murni Spirit memberikan bonus pertumbuhan +10% dan memulihkan Health +5%/hari.
- **Tergenang (Overwatered):** Risiko pembusukan akar (+15% kemungkinan terkena Blight/Penyakit).

### 7.2 Pupuk & Nutrisi Spirit (Fertilizers & Nutrients)
Pupuk memberikan dorongan nutrisi sementara atau permanen pada tanah/tanaman:

| Jenis Pupuk | Asal / Provenance | Efek pada Plant Instance | Durasi Efek |
|---|---|---|---|
| **Kompos Organik Biasa** | Sisa tanaman / sampah organik | Mempertahankan kelembapan & nutrisi tanah Tier 1 | 7 Hari |
| **Pupuk Kotoran Spirit Beast** | Dikumpulkan dari Spirit Beast (`46_SPIRIT_BEAST_TAMING_SYSTEM.md`) | +15% Kecepatan Tumbuh, +10% Health. Tier Pupuk mengikuti Tier Beast | 5 Hari |
| **Ampas Alkemia (Pill Dregs / Refinement Ash)** | Hasil sisa peracikan pil (`43_ALCHEMY_PILL_SYSTEM.md`) | +25% Kecepatan Tumbuh, +10% Peluang Quality Grade Tinggi pada Harvest. Jika ampas beracun (Dan-Du tinggi), memicu mutasi/kerusakan | 3 Hari |
| **Cairan Nutrisi Spirit Khusus** | Hasil peracikan khusus/resep canon | Mempercepat pertumbuhan +50% untuk 24 jam | 24 Jam |

---

## 8. Cuaca & Musim Regional (Weather & Seasonal Modifiers)

Pengaruh musim dan cuaca mengikuti iklim wilayah tempat tanaman berada (lihat modul regional `02`–`07`):

### 8.1 Pengaruh Musim

| Musim | Efek Umum pada Gardening |
|---|---|
| **Musim Semi (Spring)** | Kondisi ideal. Kecepatan tumbuh +15%, tingkat keberhasilan propagasi +10%. |
| **Musim Panas (Summer)** | Kebutuhan air meningkat 2× lipat. Risiko kekeringan. Tanaman atribut Api +20% tumbuh. |
| **Musim Gugur (Autumn)** | Kecepatan tumbuh standar. Waktu ideal panen tanaman buah/biji-bijian. |
| **Musim Dingin (Winter)** | Tanaman non-Es mengalami penurunan kecepatan tumbuh -40%. Risiko pembekuan tanah (-10% Health/hari tanpa pelindung/array). |

### 8.2 Anomali Cuaca & Cuaca Ekstrem
- **Hujan Gerimis Spirit:** Otomatis memenuhi kebutuhan air & memberikan bonus Qi (+5% Health).
- **Badai Es / Hujan Angin:** Tanaman tanpa rumah kaca / array pelindung kehilangan 20% Health per kejadian.
- **Badai Qi (Qi Storm / Anomali Regio):** Memicu peluang Mutasi Spirit (+10%), namun jika tanaman tidak kuat, Health berkurang -30%.

---

## 9. Hama Spirit & Penyakit Tanaman (Pests & Blight)

Tanaman spiritual yang kaya akan Qi dapat menarik perhatian hama spirit atau terserang penyakit spiritual.

### 9.1 Kategori Hama & Penyakit

| Tipe Gangguan | Pemicu / Penyebab | Dampak pada Plant Instance | Metode Penanganan |
|---|---|---|---|
| **Serangga Spirit (Qi Insects)** | Qi Density tinggi, tanah subur | Menggerogoti Qi & daun; Progress berhenti, Health -5%/hari | Pembasmian manual, Insektisida Spirit, atau dipredasi oleh Spirit Beast Serangga/Burung (`46`) |
| **Jamur Pembusuk (Qi Blight / Root Rot)** | Pengairan berlebihan, kelembapan ekstrem | Health -15%/hari; dapat menular ke Plant Instance sekitar dalam jarak 5 meter | Pemotongan bagian terinfeksi, Pil Cleansing/Pengusir Jamur, atau sanitasi tanah |
| **Gulma Penyerap Qi (Qi-Sucking Weeds)** | Pemeliharaan tanah diabaikan (>3 hari tanpa Soil Care) | Menyerap 50% nutrisi tanah; Kecepatan tumbuh -50% | Penyiangan manual (Soil Care Action) |

### 9.2 Formula Kemunculan Hama (Pest Chance)
AI GM mengecek potensi hama/penyakit setiap 24 jam Waktu Dunia yang berlalu:
$$\text{PestChance} = 5\% + \text{SoilTier} \times 2\% + \text{UnmaintainedDays} \times 5\% - \text{ArrayProtectionBonus}$$

Jika PestChance berhasil: tanaman terkena salah satu status gangguan di atas.

---

## 10. Growth Duration & Status Pertumbuhan

### 10.1 Batas Maksimum Pertumbuhan Canon
- **Ordinary Plant:** Maksimal **7 hari Waktu Dunia** hingga matang.
- **Spiritual Plant:** Maksimal **15 hari Waktu Dunia** hingga matang (kecuali spesies purba langka yang memiliki durasi spesifik di canon resmi/Admin).

### 10.2 Growth Progress Status

| Status | Arti & Ketentuan Runtime |
|---|---|
| **PLANTED** | Baru ditanam, Plant Instance aktif, Health 100%, Progress 0% |
| **GROWING** | Sedang tumbuh, Progress bertambah seiring elapsed World Time |
| **MATURE** | Progress mencapai 100%, siap dipanen (Harvest Validation aktif) |
| **HARVESTED** | Sudah dipanen, Output Instance dibuat, Plant Instance diakhiri/masuk regrowth |
| **FAILED** | Tanaman mati/gagal tumbuh akibat Health mencapai 0%, hama, atau kondisi lingkungan ekstrim |
| **UNRESOLVED** | Data canon belum cukup untuk menentukan status |

> **Pengingat Anti-Cheat:** Tidak boleh mengubah `GROWING` menjadi `MATURE` hanya karena pemain menunggu giliran RP tanpa elapsed World Time yang sah.

---

## 11. Integrasi Waktu & Aksi RP

Gardening mengikuti aturan waktu `00_CORE_RULES_AI_GM.md` §1.9 dan §1.10:
- **Aksi Non-Kultivasi:** Maksimal **3 jam Waktu Dunia** per prompt/giliran.
- **Penyiraman & Maintenance:** Merupakan Aksi Fisik biasa (Action Duration: 15–30 menit, PhysicalLoad sesuai kondisi).
- **Pertumbuhan Tanaman:** Berjalan berdasarkan **Waktu Dunia aktual yang berlalu** dari aksi-aksi karakter (misal: perjalanan, retret kultivasi, pertempuran, istirahat), BUKAN dari jumlah prompt atau penyiraman.
- **Pencegahan Time-Skip Tersembunyi:** Pemain tidak boleh menyatakan "aku menyiram tanaman sampai tumbuh matang" dalam satu prompt.

---

## 12. Cross-System Integrations (Integrasi Lintas Sistem)

### 12.1 Integrasi Alkemia (`43_ALCHEMY_PILL_SYSTEM.md`)
- **Hasil Panen sebagai Bahan Alkemia:** Output Instance dengan Quality High/Peak memberikan bonus margin keberhasilan peracikan pil.
- **Ampas Alkemia sebagai Pupuk:** Refinement Ash dari peracikan pil yang gagal/sukses dapat diolah menjadi pupuk kaya mineral spiritual.

### 12.2 Integrasi Formasi Array & Jimat (`45_ARRAY_TALISMAN_SYSTEM.md`)
- **Array Pengumpul Qi (Qi Gathering Array):** Meningkatkan Qi Density kebun, meningkatkan Soil Tier efektif +1, dan mempercepat pertumbuhan +20%.
- **Array Pengendali Iklim (Climate Control Array):** Melindungi kebun dari efek buruk musim dingin, kekeringan, dan badai cuaca.
- **Array Penghalang Hama (Warding Array):** Mengurangi PestChance hingga 0% selama array aktif.

### 12.3 Integrasi Penjinakan Spirit Beast (`46_SPIRIT_BEAST_TAMING_SYSTEM.md`)
- **Pupuk Kotoran Beast:** Beast jinak menghasilkan kotoran bernutrisi tinggi sesuai Tier Beast tersebut.
- **Spirit Beast Penjaga Kebun:** Spirit Beast tipe herbivora/burung/serangga jinak dapat ditugaskan menjaga kebun dari hama atau penyusup.
- **Kerusakan oleh Beast Liar:** Beast liar dapat merusak Plant Instance jika kebun tidak dipagar/dijaga.

---

## 13. Hybridization & Mutation Mechanics (Persilangan & Mutasi)

Dua tanaman spiritual cultivable dari genus/famili yang kompatibel dapat disilangkan di media tanah khusus (Minimal Mid Spirit Soil Tier 3):

### 13.1 Syarat Persilangan
1. Pemain memiliki 2 jenis Plant Instance matang/benih yang kompatibel menurut canon/Admin.
2. Proses penanaman berdampingan dengan perawatan khusus (Nutrisi Spirit + Air Qi Murni).
3. Menggunakan Waktu Dunia penuh sesuai durasi tanaman yang paling lama.

### 13.2 Formula Peluang Mutasi (Mutation Chance)
$$\text{MutationChance} = 5\% + \text{SoilTier} \times 2\% + \text{QiDensityBonus} + \text{RefinementAshBonus}$$

- **Jika Mutasi Berhasil:** Menghasilkan benih/varietas mutasi baru yang **WAJIB divalidasi oleh Admin** sebelum efek/namanya dicatat secara resmi di file kustom.
- **Jika Mutasi Gagal:** Menghasilkan tanaman infertil biasa atau tanaman rusak (*FAILED*).

---

## 14. Harvest Validation & Output Instance

Panen hanya sah jika:
1. Plant Instance dalam status `MATURE` (Progress 100%);
2. Lokasi dan kondisi fisik tanaman masih utuh;
3. Metode panen sesuai dengan karakteristik tanaman (alat khusus jika canon memerlukan).

Hasil panen dicatat sebagai **Output Instance**.

**Format Minimum Output Instance:**

| Field | Keterangan / Nilai |
|---|---|
| **Output Item Name** | Nama hasil panen canon |
| **Source Plant Instance** | ID Plant Instance asal |
| **Harvest Time** | Waktu dunia saat dipanen |
| **Quantity** | Jumlah unit hasil panen |
| **Quality Grade** | Low / Mid / High / Peak / Flawless (berdasarkan Health & Soil) |
| **Tier** | Tunduk pada `10_ECONOMY_SYSTEM.md` |
| **Item Origin / Provenance** | Tracing ID dari benih hingga panen |

---

## 15. Seed Propagation & Post-Harvest State

Panen TIDAK otomatis menghasilkan benih.
- **Tanaman Satu Kali Panen (Annual/Single Harvest):** Plant Instance berakhir/mati setelah dipanen (`HARVESTED`).
- **Tanaman Panen Berulang (Perennial/Regrowth):** Plant Instance memasuki status `REGROWTH` dengan Progress kembali ke 20–40% dan membutuhkan durasi recovery sebelum panen berikutnya.
- **Ekstraksi Benih (Seed Extraction):** Membutuhkan bagian dari hasil panen atau teknik propagasi khusus yang diizinkan canon.

---

## 16. Format Display AI GM (UI Template Gardening)

Setiap kali AI GM memberikan pembaharuan mengenai status kebun/tanaman pemain dalam narasi RP, AI GM disarankan menggunakan format blok standar berikut di dalam respon:

```markdown
🌱 ─── STATUS KEBUN & CULTIVATION PLOT ───
📍 Lokasi: [Nama Lokasi / Kebun] | 🏞️ Soil Quality: [Tier X - Jenis Tanah]
🌧️ Cuaca & Musim: [Musim] — [Status Cuaca] | 🔮 Qi Density: [Rendah/Sedang/Tinggi]

[ID Plant Instance] — [Nama Tanaman Canon]
├─ 📊 Growth Progress : [▓▓▓▓▓░░░░░] XX% ([Status: GROWING/MATURE])
├─ ❤️ Health Condition : XX% ([Sehat / Terkena Hama / Kering])
├─ 💧 Pengairan & Nutrisi: [Cukup / Lembap Qi / Butuh Air] | Pupuk: [Aktif/Tidak]
└─ ⏱️ Est. Matang      : [Sisa Waktu Dunia / Jam / Hari]
─────────────────────────────────────────
```

---

## 17. Expanded Canon Principles & Boundary

Modul ini mendefinisikan seluruh mekanik budidaya, tanah, iklim, hama, dan integrasi sistem, namun **TIDAK SECARA OTOMATIS MENAMBAHKAN**:
- Spesies tanaman spiritual baru;
- Resep pil baru;
- Alat/jimat kustom baru;
- Efek obat/racun fiktif tanpa penetapan Admin.

Setiap penemuan varietas mutasi baru, resep pupuk ajaib, atau tanaman kustom WAJIB dicatatkan oleh Admin melalui file kustom (`39`–`42`) sebelum dianggap resmi dalam dunia Lingyuan World.

---

## 18. Checklist Validasi AI GM (Gardening Resolution)

- [ ] Plant Instance memiliki provenance benih/bibit yang sah?
- [ ] Soil Tier sesuai dengan kebutuhan jenis tanaman?
- [ ] Batas waktu aksi RP sesuai §1.9 Core Rules (maks 3 jam per prompt)?
- [ ] Pertumbuhan tanaman didasarkan pada Waktu Dunia aktual yang berlalu, bukan jumlah prompt?
- [ ] Status pengairan, pupuk, dan cuaca sudah diperhitungkan dalam Health & Growth Progress?
- [ ] Pengecekan PestChance dilakukan jika waktu dunia berlalu >24 jam?
- [ ] Harvest Validation memastikan Progress = 100% sebelum Output Instance dibuat?
- [ ] Quality Grade dan Tier Output Instance tunduk pada `10_ECONOMY_SYSTEM.md`?
- [ ] Mutasi/Persilangan baru ditahan untuk verifikasi Admin (`UNRESOLVED`) jika belum ada di canon?
- [ ] Output Instance terhubung ke Item Origin Log untuk penggunaan Alkemia/Crafting/Perdagangan berikutnya?

---

## 19. Status Modul

**CANONICAL — SYSTEM MODULE**
Modul ini adalah aturan standar resmi untuk seluruh aktivitas Gardening dan Budidaya Flora di Lingyuan World.
