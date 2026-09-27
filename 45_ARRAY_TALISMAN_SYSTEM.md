# ☯️ Lingyuan World — Sistem Formasi Array & Jimat (Array & Talisman System)

> **Modul:** 45 — Array & Talisman System
> **Status:** Canonical System
> **Prinsip:** Source-Traceable — Time-Bound — Anti-Cheat — Hardcore Realism
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` (aturan inti, batas waktu, timed processing §1.10), `09_CULTIVATION_LAW_SYSTEM.md` (Realm, Qi Cap & Law Origin), `10_ECONOMY_SYSTEM.md` (Tier/Grade, Provenance & harga), `12_COMBAT_SYSTEM.md` (serangan, pertahanan, area of effect), `38_GARDENING_SYSTEM.md` (sumber bahan herbal tinta spirit), `players/` (official save dikelola Admin)

---

## 0. Filosofi Sistem Formasi & Jimat

Seni Formasi Array (*Zhen-Fa*) dan Jimat Spirit (*Fu-Lu*) adalah cabang ilmu kultivasi kuno yang memanipulasi aliran Qi alam semesta melalui simpul garis rune geometris.

- **Jimat Spirit (Talismans / Fu-Lu):** Media serang/bertahan portabel sekali pakai (*single-use*). Qi dipadatkan ke dalam Kertas Cendana Spirit menggunakan Tinta Darah Monster dan Kuas Spirit.
- **Formasi Array (Arrays / Zhen-Fa):** Struktur pertahanan, ilusi, atau pengumpul Qi yang terpasang tetap di suatu area/domain. Dipicu oleh Kristal Batu Spirit (*Spirit Stones*) atau Jalur Vena Qi Bumi (*Leylines*).

---

## 1. Sistem Jimat Spirit (Talismans / Fu-Lu)

### 1.1 Material Pembuatan Jimat
1. **Kertas Jimat (Talisman Paper):**
   - **Tier 1 (Mortal Paper):** Kertas Bambu Kuning (Batas Qi: 100).
   - **Tier 2 (Spirit Paper):** Kertas Cendana Ling (Batas Qi: 500).
   - **Tier 3 (Earth Beast Paper):** Kulit Beast Tier 3 / Perkamen Emas (Batas Qi: 2.500).
   - **Tier 4 (Immortal Paper):** Perkamen Sutra Purba (Batas Qi: 12.500).
2. **Kuas Spirit (Spirit Brush):**
   - Kualitas kuas menentukan presisi garis rune (Bonus Success Rate +0% s/d +30%).
3. **Tinta Spirit (Spiritual Ink):**
   - Dibuat dari campuran Darah Monster (`13_BESTIARY.md`), Bubuk Batu Spirit, dan Herba Pelarut (`38_GARDENING_SYSTEM.md`).

### 1.2 Proses & Formula Pembuatan Jimat

Mengukir jimat membutuhkan konsentrasi Qi tanpa terputus (15 menit – 2 jam per lembar) dan mengonsumsi 10–30% Qi Cap pembuatnya.

$$\text{TalismanSuccessRate} = 50\% + (\text{RealmIndex} \times 5\%) + \text{BrushBonus} - (\text{TalismanTier} \times 15\%) + \text{TalismanSkillBonus}$$

- **Gagal:** Kertas jimat terbakar menjadi abu, Qi terbuang sia-sia.
- **Sukses:** Jimat tercipta dan tersimpan di inventory (dapat dipicu instan saat combat tanpa jeda melafalkan mantra).

### 1.3 Katalog Jimat Spirit Kanon

| Tier | Nama Jimat | Efek & Fungsi saat Dipicu | Durasi / Sifat | Harga Pasar Est. |
|---|---|---|---|---|
| **Tier 1** | **Jimat Kecepatan Angin (Wind-Walk Talisman)** | +30% Speed / Initiative Roll dalam combat (`12_COMBAT_SYSTEM.md`) | 3 Giliran | 20 Tael Perak |
| **Tier 1** | **Jimat Perisai Besi (Iron Shield Talisman)** | Menyerap $100$ Damage langsung sebelum pecah | Instan / 1 Hit | 30 Tael Perak |
| **Tier 2** | **Jimat Bola Api Suci (Fireball Talisman)** | Menembakkan ledakan api atribut Qi ($150$ Damage Area) | Instan | 2 Tael Emas |
| **Tier 2** | **Jimat Sembunyi Bayangan (Invisibility Talisman)** | Menyembunyikan hawa Qi dan keberadaan fisik dari musuh | 10 Menit / Hilang saat menyerang | 5 Tael Emas |
| **Tier 3** | **Jimat Petir Tribulasi (Thunderbolt Talisman)** | Memanggil petir dari langit ($600$ Damage Atribut Petir, Efek Stun 1 giliran) | Instan | 1 Giok Kecil |
| **Tier 3** | **Jimat Teleportasi Bintang (Star Shift Talisman)** | Menteleportasikan pengguna sejauh 50 li ke arah acak aman | Instan | 3 Giok Kecil |

---

## 2. Sistem Formasi Array (Arrays / Zhen-Fa)

Formasi Array adalah zona perlindungan/serangan yang dipasang di sebuah lokasi (Gua Bertapa, Kebun Herbal, Markas Sekte, atau Kota).

### 2.1 Komponen Utama Formasi Array
1. **Inti Array (Array Core / Zhen-Xin):** Benda pemancar utama (Kristal Spirit, Artefak, atau Cermin Jiwa).
2. **Tiang/Batu Formasi (Array Flags / Pillars):** 4, 8, 12, atau 36 tiang penanam batas wilayah yang saling terhubung oleh garis garis Qi.
3. **Cakupan Wilayah (Domain Area):**
   - **Kecil (Gua/Kamar Bertapa):** Radius 10–20 meter.
   - **Menengah (Kebun/Rumah Perguruan):** Radius 100–500 meter.
   - **Besar (Sekte/Kota):** Radius 1–10 li.

---

## 3. Jenis-Jenis Formasi Array Kanon

### 3.1 Formasi Pertahanan (Defensive Barrier Array / Hu-Shan Zhen)
- **Fungsi:** Mengisolasi area dan membentuk perisai transparan pelindung serangan fisik & Qi.
- **HP Perisai Barrier:**
  - **Tier 1 (Mortal Array):** $1.000$ HP Barrier | Konsumsi: 10 Tael Perak / hari.
  - **Tier 2 (Spirit Array):** $5.000$ HP Barrier | Konsumsi: 1 Tael Emas / hari.
  - **Tier 3 (Earth Array):** $25.000$ HP Barrier | Konsumsi: 1 Giok Kecil / hari.
  - **Tier 4 (Heaven Array):** $100.000$ HP Barrier | Konsumsi: 1 Giok Menengah / hari.

### 3.2 Formasi Kabut Ilusi (Illusion / Mist Array / Migu Zhen)
- **Fungsi:** Membuat siapapun yang memasuki area tersesat dan berputar-putar kembali ke luar tanpa menyadari gua/pintu masuk.
- **Efek Combat/Eksplorasi:**
  - Musuh tanpa kemampuan Persepsi Spiritual tinggi wajib melakukan Perception Check vs DC Formasi ($15 + \text{ArrayTier} \times 5$).
  - Gagal = Tersesat selama 3 jam in-game dan terdorong keluar dari area.

### 3.3 Formasi Pengumpul Qi (Qi Gathering Array / Ju-Ling Zhen)
- **Fungsi:** Memerangkap Qi alam sekitar untuk meningkatkan Qi Density di lokasi bertapa/kebun herbal.
- **Efek:**
  - **Kebun Herbal (`38_GARDENING_SYSTEM.md`):** Mempercepat durasi tumbuh tanaman sebesar 20–30%.
  - **Kultivator Bertapa (`09_CULTIVATION_LAW_SYSTEM.md`):** Kecepatan pemulihan Qi +50% saat bermeditasi di dalam array dan +10% Chance Breakthrough Realm.

### 3.4 Formasi Pembunuh / Jebakan (Kill & Trap Array / Sha-Zhen)
- **Fungsi:** Menyerang siapapun yang masuk tanpa Izin Token Formasi (*Pass Token*).
- **Efek:**
  - Menembakkan serangan pedang Qi / petir otomatis setiap giliran ($50–500$ Damage per giliran bergantung Tier Array).

---

## 4. Pemasangan, Perawatan & Penghancuran Array

### 4.1 Pemasangan (Installation - Timed Processing)
- Pemasangan Array membutuhkan waktu nyata in-game (Tier 1: 2 jam, Tier 2: 12 jam, Tier 3: 3 hari).
- Mengonsumsi biaya bahan Tiang Formasi dan Batu Spirit Penggerak.

### 4.2 Perawatan & Konsumsi Batu Spirit (Maintenance)
- Array wajib dipasok Batu Spirit / Tael Emas secara rutin. Jika pasokan habis, Array mati/non-aktif otomatis.

### 4.3 Cara Membobol Formasi Array (Breaking the Array)
1. **Serangan Paksa (Brute Force):** Mengurangi HP Barrier Array menggunakan serangan combat sampai HP-nya 0.
2. **Mencari Mata Formasi (Finding the Array Eye / Zhen-Yan):**
   - Kultivator yang ahli Formasi Array dapat melakukan *Perception & Array Knowledge Check*.
   - Jika berhasil menemukan Mata Formasi (Zhen-Yan), mereka dapat mencabut tiang utama untuk mematikan array secara damai tanpa merusaknya.

---

## 5. Status Modul

**CANONICAL — SYSTEM MODULE**
Seluruh aturan jimat, formasi array, biaya perawatan, dan metode peretasan di atas adalah aturan resmi Lingyuan World.
