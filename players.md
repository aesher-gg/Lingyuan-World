# 📇 Lingyuan World — Players (Katalog Data Karakter Awal)

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
| **Jiang Ziling** *(contoh)* | Desa Qingmu, Tianzhou | Foundation Establishment, Menengah | Perguruan Luohua | [`Jiang_Ziling.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Jiang_Ziling.md?v=1) |
| **Tji An Coek** | Pondok Tabib Gunung, Qingyun | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Tji_An_Coek.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Tji_An_Coek.md?v=1) |
| **Nox** | Perguruan Luohua (Desa Qingmu), Tianzhou | Qi Refining, Awal | Perguruan Luohua (Murid Resmi) | [`Nox.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Nox.md?v=1) |
| **Ghi** | Desa Lingquan, Tianzhou | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Ghi.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Ghi.md?v=1) |
| **Tatsuya / Yin Zheng** | Sekte Tianjian (Tianzhou) | Qi Refining, Awal - Puncak | Sekte Tianjian (Murid Luar) | [`Tatsuya_Yin_Zheng.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Tatsuya_Yin_Zheng.md?v=1) |
| **Wang Zixiin** | Desa Luoye, Tianzhou | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Wang_Zixiin.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Wang_Zixiin.md?v=1) |
| **Ying Luo** | Desa Yinfeng, Qingyun | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Ying_Luo.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Ying_Luo.md?v=1) |
| **Yūmei** | Mirror Lake Inn, Beiyuan | Core Formation, Awal | Sanxiu / Pemilik Mirror Lake Inn | [`Yūmei.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Y%C5%ABmei.md?v=1) |
| **Lu Qingxuan** | Desa Qingmu, Tianzhou | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Lu_Qingxuan.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Lu_Qingxuan.md?v=1) |
| **Paijo** | Desa Huolian, Tianzhou | Mortal Foundation, Awal | Perguruan Tielu (Murid Magang) | [`Paijo.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Paijo.md?v=1) |
| **Azmud** | Desa Heiyan, Moyuan | Mortal Foundation, Awal | Sanxiu / Petani Herbal Rahasia | [`Azmud.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Azmud.md?v=1) |
| **Xu qin** | Desa Huolian, Tianzhou | Foundation Establishment, Awal | Perguruan Luohua (Murid Inti) & Vanguard Kekaisaran | [`Xu_qin.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Xu_qin.md?v=1) |
| **Lu Chen** | Desa Qingmu, Tianzhou | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Lu_Chen.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Lu_Chen.md?v=1) |
| **Inggo** | Hutan Lingzhu, Qingyun | Core Formation, Awal | Sanxiu (tanpa sekte) | [`Inggo.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Inggo.md?v=1) |
| **Yuma** | Desa Heiyan, Moyuan | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Yuma.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Yuma.md?v=1) |
| **Nafila** | Perbatasan Tianzhou & Qingyun | Foundation Establishment, Awal | Sanxiu (Kultivator Independen) | [`Nafila.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Nafila.md?v=1) |
| **Shi Guta** | Perguruan Shilong, Qingyun | Mortal Foundation, Awal | Perguruan Shilong (Pemahat Magang) | [`Shi_Guta.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Shi_Guta.md?v=1) |
| **Seraph** | Kota Luoyang Kecil, Tianzhou | Qi Refining, Puncak | Perguruan Luohua (Murid Senior) | [`Seraph.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Seraph.md?v=1) |
| **Suy** | Tepi Sungai Desa Lingquan, Tianzhou | Mortal Foundation, Awal | Sanxiu (tanpa sekte) | [`Suy.md`](https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Suy.md?v=1) |

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
