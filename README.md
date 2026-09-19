# 🏯 Wuxian World — World Bible (Edisi Markdown Modular)

**Versi:** 2.0 (Reorganisasi dari `JIANGHU.docx` versi 1.0)
**Genre:** Xianxia · Wuxia · Kultivasi · Hardcore Realism
**Tujuan:** Roleplay kultivasi yang adil, mendalam, konsisten, dan realistis dengan AI Game Master — dioptimalkan agar AI tidak perlu memindai satu dokumen raksasa tiap giliran, dan agar dunia tetap **terkendali & konkrit** lewat rujukan file yang jelas.

Repo ini diorganisasikan secara modular ke dalam file `.md` yang saling terhubung: modul lore/sistem, `INDEX.md` (hub navigasi), `players.md` (katalog data awal), dan folder `players/` yang berisi file data karakter individual ringkas (di bawah 300 baris agar kompatibel penuh dengan AI seperti Qwen AI).

> 🧭 **Cara tercepat mulai main:** tempel **satu link saja** — raw link `INDEX.md` — lalu sebutkan nama karaktermu (atau tempel link file RAW karaktermu dari folder `players/`). AI akan menjelajah sendiri ke modul lain sesuai kebutuhan cerita. Lihat bagian "💬 Cara Main" di bawah.

---

## 📂 Struktur Modul

| # | File | Isi | Wajib / Situasional |
|---|---|---|---|
| 🧭 | [`INDEX.md`](./INDEX.md) | **Hub navigasi tunggal** — seluruh link + logika kapan fetch modul apa | ✅ **Inilah yang ditempel ke AI, bukan link lain** |
| 📇 | [`players.md`](./players.md) | Katalog **data awal** karakter & link file di `players/` — admin-only, read-only bagi AI, BUKAN save system | Difetch otomatis lewat `INDEX.md` HANYA saat karakter dimainkan pertama kali |
| 👤 | [`players/`](./players/) | Folder berisi 17 file `.md` data awal karakter individual | Difetch spesifik sesuai nama karakter saat pertama kali dimainkan |
| — | [`README.md`](./README.md) | Peta navigasi & dokumentasi ini | Referensi manusia (tidak perlu ditautkan ke AI) |
| 00 | [`00_CORE_RULES_AI_GM.md`](./00_CORE_RULES_AI_GM.md) | Aturan mutlak AI GM, anti-cheat, format respon wajib, cheat-sheet formula inti | ✅ **WAJIB tiap sesi** (difetch otomatis lewat `INDEX.md`) |
| 01 | [`01_WORLD_OVERVIEW_AND_CAPITAL.md`](./01_WORLD_OVERVIEW_AND_CAPITAL.md) | Peta jarak dunia, Ibu Kota Tianjing & Kekaisaran | Situasional (konteks besar / karakter di ibu kota) |
| 02 | [`02_CENTRAL_PLAINS.md`](./02_CENTRAL_PLAINS.md) | Dataran Tengah: kota, desa, sekte, bandit, NPC | Saat karakter di Central Plains |
| 03 | [`03_AZURE_MOUNTAIN_RANGE.md`](./03_AZURE_MOUNTAIN_RANGE.md) | Pegunungan Azure | Saat karakter di Azure Mountain Range |
| 04 | [`04_SOUTHERN_DEMON_DOMAIN.md`](./04_SOUTHERN_DEMON_DOMAIN.md) | Daerah Iblis Selatan | Saat karakter di Southern Demon Domain |
| 05 | [`05_EASTERN_SEA_REGION.md`](./05_EASTERN_SEA_REGION.md) | Wilayah Laut Timur | Saat karakter di Eastern Sea Region |
| 06 | [`06_NORTHERN_DESOLATE_TERRITORY.md`](./06_NORTHERN_DESOLATE_TERRITORY.md) | Wilayah Utara Gersang | Saat karakter di Northern Territory |
| 07 | [`07_WESTERN_SACRED_DESERTS.md`](./07_WESTERN_SACRED_DESERTS.md) | Gurun Suci Barat | Saat karakter di Western Deserts |
| 08 | [`08_CROSS_REGION_ORGANIZATIONS.md`](./08_CROSS_REGION_ORGANIZATIONS.md) | Info broker, pegadaian, perhimpunan tabib, pembunuh bayaran, sanxiu, kriminal mortal | Saat berurusan dengan organisasi lintas wilayah / buronan |
| 09 | [`09_CULTIVATION_LAW_SYSTEM.md`](./09_CULTIVATION_LAW_SYSTEM.md) | 9 Realm, 5 Hukum kultivasi, breakthrough, tribulasi, karma | Saat breakthrough, klaim teknik, atau hitung Qi detail |
| 10 | [`10_ECONOMY_SYSTEM.md`](./10_ECONOMY_SYSTEM.md) | Mata uang, tier/grade barang, harga jasa, aset, tawar-menawar | Saat transaksi/jual-beli |
| 11 | [`11_VITALITY_HUNGER_SYSTEM.md`](./11_VITALITY_HUNGER_SYSTEM.md) | Formula HP, status luka, regenerasi, kelaparan | Saat cek status detail / efek kelaparan |
| 12 | [`12_COMBAT_SYSTEM.md`](./12_COMBAT_SYSTEM.md) | Giliran, initiative, damage, defense, escape | Setiap kali terjadi pertarungan |
| 13 | [`13_BESTIARY.md`](./13_BESTIARY.md) | Monster & spirit beast per wilayah, ambush, loot | Perjalanan liar / hunting / ambush |
| 14–37 | *(lihat `INDEX.md` §1a)* | 24 file individual — satu file per sekte/dojo/organisasi: hierarki, fasilitas, artefak/seal/talisman, kurikulum teknik bertingkat, Hukum kultivasi detail, relasi antar-faksi, rahasia internal | Bergabung sekte, eksplorasi fasilitas, belajar teknik (fetch hanya file sekte yang relevan) |

---

## 🚀 Cara Setup di GitHub

1. Buat repository baru di GitHub — **harus PUBLIC** (repo privat butuh token otentikasi supaya raw link bisa diakses AI, jadi hindari kecuali kamu tahu cara handle itu).
2. Upload seluruh file `.md` ini ke root repo — termasuk `INDEX.md`, `players.md`, dan folder `players/`.
3. Setiap file punya "raw link" dengan format:
   ```
   https://raw.githubusercontent.com/USERNAME/REPO/BRANCH/NAMA_FILE.md
   ```
   atau `.../refs/heads/BRANCH/NAMA_FILE.md` — keduanya format resmi GitHub yang valid.
4. Buka `INDEX.md` §1 dan `players.md`, pastikan seluruh link di tabel sudah cocok dengan username/repo-mu sendiri.
5. Setelah itu, **kamu hanya perlu menempel link** `INDEX.md` (dan opsi link RAW karakter spesifik di folder `players/`) di setiap sesi baru.

---

## 💬 Cara Main — Metode Utama (Satu Link / Direct Character Link)

Pilih salah satu dari template di bawah sesuai situasimu:

### A. Mulai Karakter dari Katalog `players.md` (Pertama Kali Dimainkan)
```
analisis link berikut ini secara penuh dan pelajari dengan seksama untuk memulai permainan roleplay ini : https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/INDEX.md dan https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Inggo.md untuk Memulai permainan sebagai Inggo!
```
*(Ganti `Inggo.md` dan `Inggo` dengan nama karaktermu, misal: `Tji_An_Coek.md`, `Nox.md`, `Jiang_Ziling.md`, dll.)*

### B. Karakter Custom Baru (Belum Terdaftar di `players.md`)
```
Kamu akan jadi AI Game Master untuk roleplay Wuxian World. Baca dan ikuti seluruh isi link berikut sebagai satu-satunya sumber kebenaran:

https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/INDEX.md

Data karakterku (karakter baru, belum terdaftar di players.md):
- Nama: [nama karaktermu]
- Lokasi awal: [pilih dari daftar lokasi di modul wilayah yang sesuai]
```

### C. Melanjutkan Karakter di Sesi Baru (Setelan Save File Diperbarui Admin)
```
analisis link berikut ini secara penuh dan pelajari dengan seksama untuk melanjutkan permainan roleplay ini : https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/INDEX.md dan https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Inggo.md untuk Memelanjutkan permainan sebagai Inggo!
```

---

## ⏳ Aturan Sesi Roleplay & Sistem Save Data (Tanpa Batas)

1. **Sesi Roleplay Tanpa Batas Step**:
   - Sesi roleplay berjalan tanpa batasan jumlah step (`💬 Step: Tanpa Batas`).
   - Tidak ada lagi perhitungan batas step/counter max, dan tidak ada pembekuan sesi. Pemain bebas melanjutkan petualangan sesuka hati.
2. **Alur Save Karakter**:
   - Pemain **bebas menyalin (copy)** isi dari blok **Profil Karakter** kapan saja.
   - Kirimkan data Profil Karakter tersebut kepada **Admin (pemilik repo)** kapan saja untuk dimasukkan/diperbarui ke dalam file save karakter resmi di `players/<Nama_Karakter>.md`.
   - Setelah Admin memperbarui file Anda di core repository, Anda dapat membuka chat/sesi baru kapan saja dan cukup sebutkan nama karakter Anda (atau tempel link INDEX + link file karakter Anda) untuk memuat save file terbaru dan melanjutkan petualangan!

---

## 🎯 Metode Manual (Fallback, Jika AI Tidak Bisa Fetch Link)

Kalau AI yang kamu pakai tidak punya kemampuan membuka link sendiri, kamu masih bisa menempel modul satu-satu secara manual. Pakai pola ini supaya hemat token:

| Situasi | Link yang Ditempel |
|---|---|
| **Selalu** (tiap sesi baru / ganti chat) | `00_CORE_RULES_AI_GM.md` + modul wilayah tempat karaktermu berada saat ini |
| Mulai karakter dari katalog `players.md` (pertama kali) | + file karakter spesifik di `players/<Nama_Karakter>.md` |
| Melanjutkan karakter yang sudah pernah main | Tempel manual blok "Profil Karakter" terakhir (**bukan** file karakter) |
| Karakter pindah wilayah | Ganti link modul wilayah ke wilayah tujuan |
| Mau breakthrough / klaim teknik baru | + `09_CULTIVATION_LAW_SYSTEM.md` |
| Mau berdagang / lihat harga | + `10_ECONOMY_SYSTEM.md` |
| Pertarungan serius | + `12_COMBAT_SYSTEM.md` (dan `13_BESTIARY.md` jika lawan monster) |

---

## 🌏 Dunia dalam Angka

- **Luas total:** ± 48 juta li² · **Populasi:** ± 280 juta jiwa · **Kekayaan total:** ± 3,2 miliar Tael Perak
- **7 wilayah besar:** Central Plains, Azure Mountain Range, Southern Demon Domain, Eastern Sea Region, Northern Desolate Territory, Western Sacred Deserts, plus organisasi lintas wilayah
- **9 Major Realm × 3 Stage** kultivasi, **5 Hukum kultivasi** berbeda

---

## ✅ Checklist Sebelum Main

- [ ] Repo GitHub sudah publik & seluruh file sudah ter-upload (termasuk folder `players/`)
- [ ] Link raw `INDEX.md` dan `players/Inggo.md` sudah dites bisa dibuka di browser
- [ ] Tahu karaktermu mulai dari lokasi mana
