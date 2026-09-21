# 🧭 Lingyuan World — INDEX

> **Ini adalah SATU-SATUNYA link yang perlu ditempel pemain di setiap sesi.**
> Semua modul lain (aturan, wilayah, sistem, data karakter) dijangkau AI secara otomatis dari sini lewat `web_fetch`/browsing, sesuai kondisi yang sedang terjadi di roleplay.
>
> **Untuk AI:** baca seluruh file ini dulu sampai habis, lalu jalankan **Prosedur Bootstrap** di §0 SEBELUM menulis balasan apa pun ke pemain. Jangan menjawab dari ingatan/memori bebas — dunia ini hanya sah kalau datanya berasal dari modul-modul yang ditautkan di sini.

---

## 0. Prosedur Bootstrap (WAJIB, Urutan Ini Persis)

1. **Fetch `00_CORE_RULES_AI_GM.md`** (link di tabel §1) — WAJIB pertama, tanpa kecuali. File itu berisi aturan mutlak, anti-cheat, aturan Sesi Roleplay (Tanpa Batas), dan format respon wajib yang mengikat seluruh sesi. Jangan lanjut ke langkah berikutnya sebelum ini selesai dibaca.
2. **Inisialisasi Indikator Step**:
   - Setiap balasan AI GM wajib mencantumkan header: `🕒 Waktu Lingyuan World | 💬 Step: Tanpa Batas`.
   - Sesi berjalan tanpa batasan jumlah step, memberikan kebebasan penuh bagi pemain untuk terus bermain tanpa pembekuan sesi.
3. **Cek pesan pemain** untuk menentukan identitas & titik mulai karakter — ada 3 kemungkinan, jangan disamaratakan:
   - **(a) Karakter terdaftar, baru pertama kali dimainkan atau memulai sesi baru dari save repo** (nama cocok entri di `players.md`, TIDAK ada blok "Profil Karakter" yang ditempel/riwayat sebelumnya) ATAU **pemain menanyakan tentang karakter/player lain** → fetch `players.md` (link §1) atau langsung fetch file RAW karakter individual yang dituju di `players/<Nama_Karakter>.md` (misal: `https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/players/Inggo.md`), muat data awalnya sebagai **titik mulai** narasi atau referensi informasi. `players.md` & folder `players/` dikelola oleh admin sebagai sumber save resmi.
   - **(b) Melanjutkan karakter yang sudah pernah dimainkan di dalam chat yang sama** (pemain menempel blok "Profil Karakter" dari sesi sebelumnya, atau riwayatnya masih ada di chat yang sama) → pakai kondisi TERKINI itu sebagai starting state.
   - **(c) Karakter benar-benar baru** (nama tidak ada di `players.md` maupun riwayat manapun) → perlakukan sebagai karakter baru custom sesuai `00_CORE_RULES_AI_GM.md` §1.6, minta Nama + Lokasi Awal.
4. **Tentukan lokasi karakter** (dari file karakter individual di `players/` atau dari input baru pemain), lalu fetch modul wilayah yang sesuai (`01`–`07`) dari tabel §1.
5. **Fetch `39_CUSTOM_EVENTS.md`** — cek apakah ada event aktif yang sedang berlangsung di dunia. Jika ada, pastikan event itu terasa dalam narasi (suasana, dialog NPC, kejadian acak).
6. **Mulai sesi** mengikuti format respon wajib di `00` dengan header `Step: Tanpa Batas`.
7. **Selama sesi berlangsung**, fetch modul tambahan secara dinamis begitu kondisinya muncul — lihat tabel pemicu di §2. Jangan fetch banyak file sekaligus di awal; itu boros token dan bertentangan dengan tujuan modularitas sistem ini.
8. Jika sebuah link gagal diakses (404/error), beri tahu pemain bahwa file itu mungkin belum ter-upload atau nama filenya salah — **jangan mengarang isinya**.

---

## 1. Direktori Lengkap Seluruh Modul

| Kode | File | Link Raw | Isi Singkat |
|---|---|---|---|
| 00 | `00_CORE_RULES_AI_GM.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/00_CORE_RULES_AI_GM.md | Aturan mutlak, anti-cheat, format respon wajib, cheat-sheet formula — **selalu difetch pertama** |
| 👤 | `players.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/players.md | Katalog **data AWAL** karakter (statis, dikelola admin) — memuat link RAW ke file individual di `players/` |
| 01 | `01_WORLD_OVERVIEW_AND_CAPITAL.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/01_WORLD_OVERVIEW_AND_CAPITAL.md | Peta jarak dunia & Ibu Kota Tianjing |
| 02 | `02_TIANZHOU.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/02_TIANZHOU.md | Tianzhou: kota, desa, sekte, NPC |
| 03 | `03_QINGYUN.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/03_QINGYUN.md | Qingyun |
| 04 | `04_MOYUAN.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/04_MOYUAN.md | Moyuan |
| 05 | `05_HAIYUAN.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/05_HAIYUAN.md | Haiyuan |
| 06 | `06_BEIYUAN.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/06_BEIYUAN.md | Beiyuan |
| 07 | `07_XISHA.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/07_XISHA.md | Xisha |
| 08 | `08_CROSS_REGION_ORGANIZATIONS.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/08_CROSS_REGION_ORGANIZATIONS.md | Info broker, pegadaian, pembunuh bayaran, sanxiu, kriminal mortal |
| 09 | `09_CULTIVATION_LAW_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/09_CULTIVATION_LAW_SYSTEM.md | Realm, Hukum kultivasi, breakthrough, tribulasi, karma |
| 10 | `10_ECONOMY_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/10_ECONOMY_SYSTEM.md | Mata uang, tier/grade barang, harga jasa & aset |
| 11 | `11_VITALITY_HUNGER_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/11_VITALITY_HUNGER_SYSTEM.md | Formula HP, status luka, kelaparan |
| 12 | `12_COMBAT_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/12_COMBAT_SYSTEM.md | Giliran, initiative, damage, defense, escape |
| 13 | `13_BESTIARY.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/13_BESTIARY.md | Monster & spirit beast per wilayah, ambush, loot |
| 38 | `38_GARDENING_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/38_GARDENING_SYSTEM.md | Penanaman, maintenance, pertumbuhan, panen, provenance & checkpoint gardening |
| 14–37 | *(24 file sekte/perguruan/organisasi individual)* | — | Lihat **§1a** di bawah untuk daftar lengkap per-file — **JANGAN** fetch semuanya sekaligus, cari nama sekte yang relevan lalu fetch HANYA file itu |
| 39 | `39_CUSTOM_EVENTS.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/39_CUSTOM_EVENTS.md | **Event khusus & peristiwa dunia** — diisi Admin, AI wajib cek di awal sesi |
| 40 | `40_CUSTOM_LAWS.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/40_CUSTOM_LAWS.md | **Hukum Kultivasi kustom** — buatan pemain/Admin, dicatat di sini agar resmi |
| 41 | `41_CUSTOM_SECTS.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/41_CUSTOM_SECTS.md | **Sekte/Perguruan/Organisasi kustom** — buatan pemain/Admin, dicatat di sini agar resmi |
| 42 | `42_CUSTOM_TECHNIQUES.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/42_CUSTOM_TECHNIQUES.md | **Teknik & Jurus Kustom** — buatan pemain/Admin, dicatat di sini agar resmi |
| — | `README.md` | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/README.md | Dokumentasi setup untuk manusia (jarang perlu difetch AI) |

### 1a. Direktori Sekte, Perguruan & Organisasi (24 File Individual)

> Setiap sekte/perguruan/organisasi punya **file sendiri**, lengkap dengan hierarki, fasilitas, artefak/pusaka/seal-talisman, kurikulum teknik bertingkat, Hukum kultivasi detail, relasi antar-faksi, dan rahasia internal. **Fetch HANYA** link file yang relevan dengan situasi saat ini — jangan fetch banyak sekaligus.

**Tianzhou**
| Sekte/Perguruan | Link RAW (langsung klik/fetch) |
|---|---|
| Sekte Tianjian | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/14_SEKTE_TIANJIAN.md |
| Sekte Xuanyuan | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/15_SEKTE_XUANYUAN.md |
| Sekte Yunjian | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/16_SEKTE_YUNJIAN.md |
| Perguruan Luohua | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/17_PERGURUAN_LUOHUA.md |
| Perguruan Tielu | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/18_PERGURUAN_TIELU.md |

**Qingyun**
| Sekte/Perguruan | Link RAW (langsung klik/fetch) |
|---|---|
| Biara Jinguang | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/19_BIARA_JINGUANG.md |
| Perguruan Shilong | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/20_PERGURUAN_SHILONG.md |

**Moyuan**
| Sekte/Perguruan | Link RAW (langsung klik/fetch) |
|---|---|
| Istana Yanmo | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/21_ISTANA_YANMO.md |
| Sarang Jiuyin | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/22_SARANG_JIUYIN.md |
| Kultus Qisha | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/23_KULTUS_QISHA.md |
| Aliansi Anying | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/24_ALIANSI_ANYING.md |
| Perguruan Heiying | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/25_PERGURUAN_HEIYING.md |

**Haiyuan**
| Sekte/Perguruan | Link RAW (langsung klik/fetch) |
|---|---|
| Istana Qinglian | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/26_ISTANA_QINGLIAN.md |
| Perguruan Haizhen | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/27_PERGURUAN_HAIZHEN.md |

**Beiyuan**
| Sekte/Perguruan | Link RAW (langsung klik/fetch) |
|---|---|
| Balai Yunyao | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/28_BALAI_YUNYAO.md |
| Sekte Hunming | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/29_SEKTE_HUNMING.md |
| Perguruan Langxue | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/30_PERGURUAN_LANGXUE.md |

**Xisha**
| Sekte/Perguruan | Link RAW (langsung klik/fetch) |
|---|---|
| Kuil Ciyun | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/31_KUIL_CIYUN.md |
| Perguruan Shaying | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/32_PERGURUAN_SHAYING.md |

**Lintas Wilayah**
| Organisasi | Link RAW (langsung klik/fetch) |
|---|---|
| Perkumpulan Wuying | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/33_PERKUMPULAN_WUYING.md |
| Kelompok Yandu | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/34_KELOMPOK_YANDU.md |
| Paviliun Wanxin (info broker) | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/35_PAVILIUN_WANXIN.md |
| Rumah Gadai Hanbi (bank tak resmi) | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/36_RUMAH_GADAI_HANBI.md |
| Perhimpunan Youyi | https://raw.githubusercontent.com/aesher-gg/Lingyuan-World/main/37_PERHIMPUNAN_YOUYI.md |

---

## 2. Alur Navigasi Otomatis (Trigger → Modul yang Difetch)

| Trigger dalam Roleplay | Modul yang Difetch | Catatan |
|---|---|---|
| Awal sesi (selalu) | `00_CORE_RULES_AI_GM.md` | Wajib pertama, lihat §0 |
| Awal sesi (setelah Bootstrap selesai) | `39_CUSTOM_EVENTS.md` | Cek apakah ada event aktif yang memengaruhi dunia |
| Karakter terdaftar di `players.md`, baru pertama kali dimainkan OR pemain menanyakan informasi karakter/player lain | `players.md` dan/atau `players/<Nama_Karakter>.md` | Muat/fetch data karakter dari link RAW individual sebagai titik mulai atau referensi informasi pemain/karakter lain |
| Melanjutkan karakter yang sudah pernah dimainkan | — | Pakai blok "Profil Karakter" terakhir yang ditempel/ada di riwayat chat — **jangan** fetch `players.md` / `players/` |
| Karakter benar-benar baru (tidak ada di `players.md`) | — | Ikuti `00` §1.6: minta Nama + Lokasi Awal |
| Karakter berada/menuju Tianzhou | `02_TIANZHOU.md` | Termasuk area ibu kota provinsi ini |
| Karakter berada/menuju Qingyun | `03_QINGYUN.md` | |
| Karakter berada/menuju Moyuan | `04_MOYUAN.md` | |
| Karakter berada/menuju Haiyuan | `05_HAIYUAN.md` | |
| Karakter berada/menuju Beiyuan | `06_BEIYUAN.md` | |
| Karakter berada/menuju Xisha | `07_XISHA.md` | |
| Butuh konteks Ibu Kota Tianjing / peta jarak besar dunia | `01_WORLD_OVERVIEW_AND_CAPITAL.md` | |
| Bertemu info broker/pembunuh bayaran/sanxiu/kriminal mortal lintas wilayah | `08_CROSS_REGION_ORGANIZATIONS.md` | |
| Breakthrough realm / klaim teknik baru / cek Law Origin | `09_CULTIVATION_LAW_SYSTEM.md` | |
| Pemain menyebut Hukum kultivasi yang tidak ada di `09` | `40_CUSTOM_LAWS.md` | Cek apakah Hukum itu sudah dicatat Admin di file kustom |
| Transaksi, tawar-menawar, cek harga barang/jasa/aset | `10_ECONOMY_SYSTEM.md` | |
| Perlu hitung detail regen HP / efek kelaparan lanjut | `11_VITALITY_HUNGER_SYSTEM.md` | Formula dasarnya sudah ada ringkas di `00` §3 |
| Pertarungan resmi dimulai (giliran, initiative, damage) | `12_COMBAT_SYSTEM.md` | |
| Lawan monster/spirit beast liar, perjalanan lewat zona liar (ambush) | `13_BESTIARY.md` | Dipakai bersamaan dengan `12` |
| Berkebun, menanam, merawat tanaman, mengecek pertumbuhan, atau memanen | `38_GARDENING_SYSTEM.md` | Wajib dipakai bersama `00`, `10`, dan `11` bila kondisi terkait muncul |
| Karakter mau bergabung sekte/perguruan, eksplorasi fasilitas sekte, belajar teknik bertingkat, atau cek hierarki/artefak sekte tertentu | Fetch langsung dari link RAW di §1a | Jangan rakit URL sendiri. Gunakan link yang sudah tertulis di kolom "Link RAW" tabel §1a. Pilih HANYA satu file yang sesuai dengan sekte yang sedang berinteraksi. |
| Pemain menyebut sekte yang tidak ada di `14`–`37` | `41_CUSTOM_SECTS.md` | Cek apakah sekte itu sudah dicatat Admin di file kustom |
| Pemain menyebut/mengklaim teknik yang tidak ada di file resmi | `42_CUSTOM_TECHNIQUES.md` | Cek apakah teknik itu sudah dicatat Admin di file kustom |
| Pemain minta bantuan setup GitHub / nanya cara pakai sistem ini | `README.md` | Ini file untuk manusia, sampaikan isinya ke pemain, bukan role-play |

**Efisiensi token:** jika sebuah modul sudah difetch sebelumnya dalam percakapan yang sama dan kondisinya belum berubah (mis. karakter masih di wilayah yang sama), **tidak perlu fetch ulang** — pakai isi yang sudah ada di riwayat chat.

---

## 3. Cara Kerja `players.md` & Folder `players/` (Manajemen Save File Karakter oleh Admin)

`players.md` adalah katalog data awal. File individual di folder `players/` menjadi **official player save** yang dikelola Admin. Keduanya hanya boleh diubah oleh Admin berdasarkan checkpoint/profil terakhir yang telah diverifikasi.

> ✅ **Link katalog `players.md` dan file individual di `players/` sudah aktif.** Setiap karakter disimpan dalam file `.md` ringkas terpisah untuk menghindari batas ekstraksi teks AI (seperti limit 300 baris Qwen AI).

**Alur pemakaian & Sesi Baru:**
1. Pemain cukup menyebutkan nama karakternya (misal: `Inggo`) saat membuka chat/sesi baru.
2. AI GM men-fetch file `players/<Nama_Karakter>.md` sebagai official save saat sesi baru dimulai.
3. Seluruh data di file karakter tersebut dimuat sebagai starting state.
4. Selama sesi berlangsung, runtime state hidup di percakapan melalui blok Profil Karakter dan checkpoint.
5. Pemain dapat meminta checkpoint; checkpoint dikirim kepada Admin untuk diverifikasi.
6. Setelah verifikasi, Admin memperbarui official save `players/<Nama_Karakter>.md`.

---

## 4. Batasan Penting yang Harus Diketahui Pemain

- `players.md` adalah katalog data awal; file individual `players/<Nama_Karakter>.md` adalah **official save** yang dikelola Admin.
- **AI GM/Qwen tidak menulis langsung ke GitHub.** Runtime state tetap berada di sesi sampai dibuat checkpoint.
- Alur save resmi: **Runtime State → Checkpoint → Admin Verification → Official Player Save**.
- Hanya Admin yang boleh memperbarui `players.md` dan file `players/` berdasarkan checkpoint yang diverifikasi.
- **File `39_CUSTOM_EVENTS.md`, `40_CUSTOM_LAWS.md`, dan `41_CUSTOM_SECTS.md` dikelola sepenuhnya oleh Admin.** AI tidak boleh mengedit, menambah, atau menghapus isinya — hanya membaca dan menggunakan data yang sudah ada di dalamnya.
- Jika sebuah link 404/gagal fetch, itu paling sering karena: nama file salah huruf besar-kecil (GitHub case-sensitive), file belum ter-push ke branch `main`, atau repo tidak publik.

---

## 5. Ringkasan Dunia (satu baris, detail penuh di `01`)

Xianxia · Wuxia · Kultivasi Hardcore Realism — 7 wilayah besar, 9 Major Realm × 3 Stage, 5 Hukum kultivasi berbeda, ± 280 juta jiwa populasi, tanpa plot armor, semua mekanik tunduk formula anti-cheat di modul `09`–`13`.
