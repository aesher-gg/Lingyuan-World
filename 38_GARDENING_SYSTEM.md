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

## 3. Plant Instance

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

## 4. Penanaman

Penanaman WAJIB divalidasi terhadap:

1. bahan tanam yang benar-benar dimiliki;
2. lokasi yang memungkinkan aktivitas tersebut;
3. kondisi tanah atau media yang relevan bila canon mengaturnya;
4. waktu dan aksi yang wajar menurut aturan inti;
5. metode penanaman yang diketahui.

Jika salah satu unsur penting tidak diketahui, AI GM menggunakan `???` atau `UNRESOLVED`, bukan mengarang.

Penanaman tidak sama dengan keberhasilan pertumbuhan.

---

## 5. Soil Care, Irrigation & Maintenance

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

## 6. Growth Duration

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

## 7. Integrasi Waktu & Aksi

Gardening mengikuti batas waktu pada `00_CORE_RULES_AI_GM.md` §1.9:

- aktivitas non-kultivasi tidak boleh melompati lebih dari **3 jam** dalam satu prompt;
- gardening tidak mendapat pengecualian kultivasi;
- pertumbuhan tanaman berlangsung berdasarkan **waktu dunia yang benar-benar berlalu**, bukan jumlah pesan;
- maintenance tidak boleh digunakan sebagai metode untuk melakukan time-skip tersembunyi;
- jika pemain meminta rentang waktu panjang, AI GM harus menerapkan aturan checkpoint dan validasi waktu yang berlaku.

Dengan demikian, "menyiram tanaman" adalah aksi, sedangkan "tanaman telah tumbuh selama 3 hari" adalah hasil dari waktu dunia yang memang telah berlalu.

---

## 8. Environmental Dependency

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

## 9. Harvest Validation

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

## 10. Economy & Origin

Output gardening yang bernilai ekonomi tunduk pada `10_ECONOMY_SYSTEM.md`.

Khususnya:

- Tier dan Grade mengikuti sistem ekonomi yang sudah canon;
- harga tidak boleh ditentukan sepihak oleh player;
- item bernilai yang memerlukan Item Origin Log harus memiliki provenance dari Plant Instance;
- hasil panen tidak boleh langsung berubah menjadi mata uang tanpa transaksi atau penggunaan yang sah;
- proses crafting/alchemy berikutnya harus dapat menunjuk Output Instance sebagai sumber material.

Gardening tidak membuat jalur ekonomi baru di luar sistem ekonomi canon.

---

## 11. History & Provenance

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

## 12. Runtime & Checkpoint

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

## 13. Anti-Exploit

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

## 14. Canon Boundary

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

## 15. Checklist Validasi AI GM

- [ ] Planting material benar-benar ada?
- [ ] Source dan acquisition dapat dilacak?
- [ ] Plant Instance sudah dibuat?
- [ ] Lokasi penanaman valid?
- [ ] Waktu aksi sesuai §1.9 Core Rules?
- [ ] Growth duration tidak melebihi 7 hari untuk Ordinary Plant?
- [ ] Growth duration tidak melebihi 15 hari untuk Spiritual Plant?
- [ ] Tidak ada time-skip tersembunyi?
- [ ] Maintenance tidak dianggap sebagai instant growth?
- [ ] Harvest hanya dilakukan setelah maturity tervalidasi?
- [ ] Output memiliki basis canon?
- [ ] Tier/Grade tidak dikarang?
- [ ] Origin/History tetap tersambung?
- [ ] Checkpoint menggunakan state runtime terakhir?
- [ ] Official save hanya dilakukan setelah verifikasi Admin?

Jika salah satu poin gagal, hasil gardening harus ditahan, dikoreksi, atau ditandai `UNRESOLVED` sesuai kondisi.

---

## 16. Status Modul

**CANONICAL — SYSTEM MODULE**

Modul ini mendefinisikan mekanik gardening, tetapi tidak menambahkan daftar tanaman, benih, pupuk, alat, hasil panen, resep, atau item baru. Data tersebut hanya sah setelah ditetapkan Admin sebagai canon.
