# 🏯 Lingyuan World — World Bible (Edisi Markdown Modular)

**Versi:** 2.1 (Reorganisasi & Perluasan Mekanik Sistem)
**Genre:** Xianxia · Wuxia · Kultivasi · Hardcore Realism
**Tujuan:** Roleplay kultivasi yang adil, mendalam, konsisten, dan realistis dengan AI Game Master — dioptimalkan agar AI tidak perlu memindai satu dokumen raksasa tiap giliran, dan agar dunia tetap **terkendali & konkrit** lewat rujukan file yang jelas.

Repo ini diorganisasikan secara modular ke dalam file `.md` yang saling terhubung: modul lore/sistem, `INDEX.md` (hub navigasi), `players.md` (katalog data awal), dan folder `players/` yang berisi file data karakter individual ringkas (di bawah 300 baris agar kompatibel penuh dengan AI seperti Qwen AI).

> 🧭 **Cara tercepat mulai main:** tempel **satu link saja** — raw link `INDEX.md` — lalu sebutkan nama karaktermu (atau tempel link file RAW karaktermu dari folder `players/`). AI akan menjelajah sendiri ke modul lain sesuai kebutuhan cerita. Lihat bagian "💬 Cara Main" di bawah.

---

## 📂 Struktur Modul

| # | File | Isi | Wajib / Situasional |
|---|---|---|---|
| 🧭 | [`INDEX.md`](./INDEX.md) | **Hub navigasi tunggal** — seluruh link + logika kapan fetch modul apa | ✅ **Inilah yang ditempel ke AI, bukan link lain** |
| 📇 | [`players.md`](./players.md) | Katalog **data awal** karakter; file `players/` adalah official save — admin-only, read-only bagi AI | Difetch otomatis lewat `INDEX.md` HANYA saat karakter dimainkan pertama kali |
| 👤 | [`players/`](./players/) | Folder berisi file `.md` official save karakter individual | Difetch spesifik sesuai nama karakter saat pertama kali dimainkan |
| — | [`README.md`](./README.md) | Peta navigasi & dokumentasi ini | Referensi manusia (tidak perlu ditautkan ke AI) |
| 00 | [`00_CORE_RULES_AI_GM.md`](./00_CORE_RULES_AI_GM.md) | Aturan mutlak AI GM, anti-cheat, format respon wajib, cheat-sheet formula inti | ✅ **WAJIB tiap sesi** (difetch otomatis lewat `INDEX.md`) |
| 01 | [`01_WORLD_OVERVIEW_AND_CAPITAL.md`](./01_WORLD_OVERVIEW_AND_CAPITAL.md) | Peta jarak dunia, Ibu Kota Tianjing & Kekaisaran | Situasional (konteks besar / karakter di ibu kota) |
| 02–07 | Regional Modules (`02_TIANZHOU` s/d `07_XISHA`) | Detail 7 wilayah utama Lingyuan World | Saat karakter berada di wilayah terkait |
| 08 | [`08_CROSS_REGION_ORGANIZATIONS.md`](./08_CROSS_REGION_ORGANIZATIONS.md) | Info broker, pegadaian, perhimpunan tabib, pembunuh bayaran, sanxiu | Saat berurusan dengan organisasi lintas wilayah / buronan |
| 09 | [`09_CULTIVATION_LAW_SYSTEM.md`](./09_CULTIVATION_LAW_SYSTEM.md) | 9 Realm, 5 Hukum kultivasi, breakthrough, tribulasi, karma | Saat breakthrough, klaim teknik, atau hitung Qi detail |
| 10 | [`10_ECONOMY_SYSTEM.md`](./10_ECONOMY_SYSTEM.md) | Mata uang, tier/grade barang, harga jasa, aset, tawar-menawar | Saat transaksi/jual-beli |
| 11 | [`11_VITALITY_HUNGER_SYSTEM.md`](./11_VITALITY_HUNGER_SYSTEM.md) | Formula HP, status luka, regenerasi, kelaparan | Saat cek status detail / efek kelaparan |
| 12 | [`12_COMBAT_SYSTEM.md`](./12_COMBAT_SYSTEM.md) | Giliran, initiative, damage, defense, escape | Setiap kali terjadi pertarungan |
| 13 | [`13_BESTIARY.md`](./13_BESTIARY.md) | Monster & spirit beast per wilayah, ambush, loot | Perjalanan liar / hunting / ambush |
| 38 | [`38_GARDENING_SYSTEM.md`](./38_GARDENING_SYSTEM.md) | Penanaman, perawatan, pertumbuhan, panen herbal | Berkebun / budidaya herba spirit |
| 39–42 | Custom Content (`39_CUSTOM_EVENTS` s/d `42_CUSTOM_TECHNIQUES`) | Event aktif, hukum kustom, sekte kustom, jurus kustom | Cek event dunia / konten kustom buatan Admin |
| 43 | [`43_ALCHEMY_PILL_SYSTEM.md`](./43_ALCHEMY_PILL_SYSTEM.md) | Alkemia, resep pil lingdan, tungku, Dan-Du (racun pil), ledakan tungku | Saat memuat tungku, meracik pil, atau terkena racun pil |
| 44 | [`44_FORGING_CRAFTING_SYSTEM.md`](./44_FORGING_CRAFTING_SYSTEM.md) | Tempa & artefak, senjata/zirah spirit, inskripsi rune, durabilitas | Saat menempa/memperbaiki senjata dan zirah |
| 45 | [`45_ARRAY_TALISMAN_SYSTEM.md`](./45_ARRAY_TALISMAN_SYSTEM.md) | Formasi array & jimat spirit, domain perlindungan gua/sekte | Saat mengukir/menggunakan jimat atau memasang formasi |
| 46 | [`46_SPIRIT_BEAST_TAMING_SYSTEM.md`](./46_SPIRIT_BEAST_TAMING_SYSTEM.md) | Penjinakan spirit beast, kontrak jiwa, tumpangan, partner tempur | Saat menjinakkan/melatih spirit beast |
| 47 | [`47_BOUNTY_AUCTION_SYSTEM.md`](./47_BOUNTY_AUCTION_SYSTEM.md) | Papan misi bounty & rumah lelang, komisi lelang | Saat mengambil misi bounty atau ikut pelelangan barang langka |
| 14–37 | *(lihat `INDEX.md` §1a)* | 24 file individual per sekte/perguruan/organisasi | Bergabung sekte, eksplorasi fasilitas, belajar teknik |

---

## 🚀 Cara Setup di GitHub

1. Buat repository baru di GitHub — **harus PUBLIC** (repo privat butuh token otentikasi supaya raw link bisa diakses AI).
2. Upload seluruh file `.md` ini ke root repo — termasuk `INDEX.md`, `players.md`, dan folder `players/`.
3. Setiap file punya "raw link" dengan format:
   ```
   https://raw.githubusercontent.com/USERNAME/REPO/BRANCH/NAMA_FILE.md
   ```
4. Buka `INDEX.md` §1 dan `players.md`, pastikan seluruh link di tabel sudah cocok dengan username/repo-mu sendiri.
5. Setelah itu, **kamu hanya perlu menempel link** `INDEX.md` di setiap sesi baru.

---

## 💬 Cara Main — Metode Utama (Satu Link / Direct Character Link)

Pilih salah satu dari template di bawah sesuai situasimu:

### A. Mulai Karakter dari Katalog `players.md` (Pertama Kali Dimainkan)
```
analisis link berikut ini secara penuh dan pelajari dengan seksama untuk memulai permainan roleplay ini : https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/INDEX.md dan https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/players/Inggo.md untuk Memulai permainan sebagai Inggo!
```

### B. Karakter Custom Baru (Belum Terdaftar di `players.md`)
```
Kamu akan jadi AI Game Master untuk roleplay Lingyuan World. Baca dan ikuti seluruh isi link berikut sebagai satu-satunya sumber kebenaran:

https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/INDEX.md

Data karakterku (karakter baru, belum terdaftar di players.md):
- Nama: [nama karaktermu]
- Lokasi awal: [pilih dari daftar lokasi di modul wilayah yang sesuai]
```

---

## 🌏 Dunia dalam Angka

- **Luas total:** ± 48 juta li² · **Populasi:** ± 298 juta jiwa
- **8 wilayah besar:** Tianzhou, Qingyun, Moyuan, Haiyuan, Beiyuan, Xisha, Cangmu, plus organisasi lintas wilayah
- **9 Major Realm × 3 Stage** kultivasi, **5 Hukum kultivasi** utama
- **Sistem Mekanik Lengkap:** Alkemia, Penempaan, Formasi Array & Jimat, Penjinakan Beast, Papan Misi & Rumah Lelang, Gardening, Pertempuran Turn-based, dan Ekonomi Terukur.
