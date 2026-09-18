# 📇 Wuxian World — Players (Katalog Data Karakter Awal)

> **Modul:** players — dirujuk lewat `INDEX.md` §3, HANYA dipakai saat karakter yang namanya terdaftar di sini dimainkan untuk **pertama kali**.
> **⚠️ SIFAT FILE & DIREKTORI: READ-ONLY MUTLAK BAGI AI.** Ini murni katalog & referensi **data awal** karakter — bukan sistem save, bukan checkpoint, bukan status terkini. AI tidak pernah menulis, mengedit, atau menyarankan perubahan pada file ini maupun file individual di folder `players/`. Hanya **admin (Inggoxxx)** yang berhak mengubah isinya, langsung di GitHub, di luar sesi roleplay.
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` §1.6 & §1.10, `09_CULTIVATION_LAW_SYSTEM.md` (Law Origin), `10_ECONOMY_SYSTEM.md` (Item Origin & mata uang)

---

## 0. Aturan Pemakaian (WAJIB DIPAHAMI AI GM)

1. File ini dan file individual di folder `players/` **hanya** berisi kondisi karakter **sebelum cerita dimulai**. Bukan status "terakhir dimainkan", bukan save slot, bukan progres yang sedang berjalan.
2. AI membaca file karakter **satu kali saja** — persis di momen karakter yang namanya ada di sini mulai dimainkan untuk **pertama kalinya**. Sejak saat itu, seluruh perkembangan karakter (HP berubah, Qi terpakai, item baru, breakthrough, pindah lokasi, dst.) **hanya** dicatat di dalam blok "Profil Karakter" pada percakapan yang sedang berjalan (format resmi ada di `00_CORE_RULES_AI_GM.md` §2) — **tidak pernah** ditulis balik ke file mana pun.
3. **Instruksi Fetch untuk AI GM:** Untuk mencegah batasan ekstraktor teks AI (misalnya limit 300 baris), data detail setiap karakter telah dipisahkan ke file individual di dalam folder `players/`. AI GM **WAJIB** mengambil/fetch file RAW karakter spesifik yang dimaksud (`players/<Nama_Karakter>.md`) melalui Link RAW pada tabel §1 di bawah saat:
   - Karakter tersebut dimainkan untuk **pertama kalinya**.
   - Pemain/Player bertanya atau menanyakan informasi/status/latar belakang mengenai karakter/player lain yang terdaftar di `players.md`.
4. AI **dilarang keras**: menulis ke file mana pun, menyarankan pemain "menyimpan"/"update" progres ke file ini, atau memperlakukan isi file karakter sebagai kondisi yang **terkini** setelah roleplay berjalan.
5. Untuk **melanjutkan** karakter yang sudah pernah dimainkan sebelumnya (bukan memulai baru), pemain menempelkan ulang blok "Profil Karakter" **terakhir** dari sesi sebelumnya di pesan pembuka. Folder `players/` **tidak dipakai** untuk kasus itu — isinya tetap/statis.

---

## 1. Daftar Katalog Karakter Terdaftar

> Klik atau fetch link RAW individual untuk memuat data awal lengkap karakter secara utuh tanpa terpotong limit ekstraktor teks AI.

| Nama Karakter | Lokasi Awal | Realm Awal | Sekte/Afiliasi Awal | File Detail & Link RAW |
|---|---|---|---|---|
| **Jiang Ziling** *(contoh)* | Desa Xingcun, Central Plains | Foundation Establishment, Menengah | Dojo Bunga Aprikot | [`Jiang_Ziling.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Jiang_Ziling.md?v=1) |
| **Tji An Coek** | Pondok Tabib Gunung, Azure Mountain Range | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Tji_An_Coek.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Tji_An_Coek.md?v=1) |
| **Nox** | Dojo Bunga Aprikot (Desa Xingcun), Central Plains | Qi Refining, Awal | Dojo Bunga Aprikot (Murid Resmi) | [`Nox.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Nox.md?v=1) |
| **Ghi** | Desa Qingshui, Central Plains | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Ghi.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Ghi.md?v=1) |
| **Tatsuya / Yin Zheng** | Heavenly Sword Pavilion (Central Plains) | Qi Refining, Awal - Puncak | Heavenly Sword Pavilion (Murid Luar) | [`Tatsuya_Yin_Zheng.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Tatsuya_Yin_Zheng.md?v=1) |
| **Wang Zixiin** | Desa Luoye, Central Plains | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Wang_Zixiin.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Wang_Zixiin.md?v=1) |
| **Ying Luo** | Desa Qingfeng, Azure Mountain Range | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Ying_Luo.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Ying_Luo.md?v=1) |
| **Yūmei** | Mirror Lake Inn, Northern Desolate Territory | Core Formation, Awal | Sanxiu / Pemilik Mirror Lake Inn | [`Yūmei.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Y%C5%ABmei.md?v=1) |
| **Lu Qingxuan** | Desa Xingcun, Central Plains | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Lu_Qingxuan.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Lu_Qingxuan.md?v=1) |
| **Paijo** | Desa Tiedao, Central Plains | Mortal Foundation, Awal | Dojo Godam Besi (Murid Magang) | [`Paijo.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Paijo.md?v=1) |
| **Azmud** | Desa Heiyan, Southern Demon Domain | Mortal Foundation, Awal | Sanxiu / Petani Herbal Rahasia | [`Azmud.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Azmud.md?v=1) |
| **Xu qin** | Desa Tiedao, Central Plains | Foundation Establishment, Awal | Dojo Bunga Aprikot (Murid Inti) & Vanguard Kekaisaran | [`Xu_qin.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Xu_qin.md?v=1) |
| **Lu Chen** | Desa Xingcun, Central Plains | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Lu_Chen.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Lu_Chen.md?v=1) |
| **Inggo** | Hutan Bambu Berbisik, Azure Mountain Range | Core Formation, Awal | Sanxiu (tanpa sekte) | [`Inggo.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Inggo.md?v=1) |
| **Yuma** | Desa Heiyan, Southern Demon Domain | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Yuma.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Yuma.md?v=1) |
| **Nafila** | Perbatasan Central Plains & Azure Mountain Range | Foundation Establishment, Awal | Sanxiu (Kultivator Independen) | [`Nafila.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Nafila.md?v=1) |
| **Shi Guta** | Dojo Pahat Naga, Azure Mountain Range | Mortal Foundation, Awal | Dojo Pahat Naga (Pemahat Magang) | [`Shi_Guta.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Shi_Guta.md?v=1) |
| **Seraph** | Kota Luoyang Kecil, Central Plains | Qi Refining, Puncak | Dojo Bunga Aprikot (Murid Senior) | [`Seraph.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Seraph.md?v=1) |
| **Suy** | Tepi Sungai Desa Qingshui, Central Plains | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Suy.md`](https://raw.githubusercontent.com/inggo-alvn/Core/refs/heads/main/players/Suy.md?v=1) |

*(Admin menambah baris baru di sini dan membuat file di `players/` setiap kali mendaftarkan karakter baru.)*

---

## 2. Template Kosong (Untuk Admin — Salin untuk Mendaftarkan Karakter Baru di `players/[Nama_Karakter].md`)

```markdown
# 👤 [Nama Karakter]

> **Data Karakter Awal** — Statis, dikelola Admin. Bukan save-state.
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` §1.6 & §1.10

---

**Nama Karakter:** [Nama Karakter]
**Lokasi Awal:** [nama lokasi, sesuai modul 01–07]
**Realm & Stage Awal:** [Realm, Stage] — Qi Cap: [angka]
**Hukum Kultivasi Awal:** [nama Hukum, atau "Belum ada — akan ditentukan lewat roleplay"]
**Law Origin (jika sudah ada Hukum):** Jalur [Guru/Manual/Pencerahan] — [detail singkat]
**Sekte/Afiliasi Awal:** [nama sekte + peran, atau "Sanxiu"]

**Kondisi Awal:** HP X/Y · Qi X/Y · Stamina X/100 · Satiety X% · Kondisi Normal · Karma Netral

**Currency Awal:**
- Tael Tembaga × [jumlah]

**Equipment Awal (terpakai/digenggam):**
- Senjata: [nama item — Tier/Grade, asal singkat, atau "Tidak ada"]
- Zirah/Pelindung: [nama item, atau "Tidak ada"]
- Aksesoris: [nama item, atau "Tidak ada"]

**Inventory Awal (dibawa, tidak terpakai):**
- [Item 1 — Tier/Grade, asal singkat]
- [Item 2]

**Teknik Awal:**
- [teknik — sumber]

**Latar Belakang & Kepribadian:**
[1–2 paragraf: siapa dia, sifatnya, motivasinya, relasi penting dengan NPC kanon jika ada]
```
