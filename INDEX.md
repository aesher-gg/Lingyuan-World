# 🧭 Wuxian World — INDEX

> **Ini adalah SATU-SATUNYA link yang perlu ditempel pemain di setiap sesi.**
> Semua modul lain (aturan, wilayah, sistem, data karakter) dijangkau AI secara otomatis dari sini lewat `web_fetch`/browsing, sesuai kondisi yang sedang terjadi di roleplay.
>
> **Untuk AI:** baca seluruh file ini dulu sampai habis, lalu jalankan **Prosedur Bootstrap** di §0 SEBELUM menulis balasan apa pun ke pemain. Jangan menjawab dari ingatan/memori bebas — dunia ini hanya sah kalau datanya berasal dari modul-modul yang ditautkan di sini.

---

## 0. Prosedur Bootstrap (WAJIB, Urutan Ini Persis)

1. **Fetch `00_CORE_RULES_AI_GM.md`** (link di tabel §1) — WAJIB pertama, tanpa kecuali. File itu berisi aturan mutlak, anti-cheat, aturan Sesi Roleplay (Tanpa Batas), dan format respon wajib yang mengikat seluruh sesi. Jangan lanjut ke langkah berikutnya sebelum ini selesai dibaca.
2. **Inisialisasi Indikator Step**:
   - Setiap balasan AI GM wajib mencantumkan header: `🕒 Waktu Wuxian World | 💬 Step: Tanpa Batas`.
   - Sesi berjalan tanpa batasan jumlah step, memberikan kebebasan penuh bagi pemain untuk terus bermain tanpa pembekuan sesi.
3. **Cek pesan pemain** untuk menentukan identitas & titik mulai karakter — ada 3 kemungkinan, jangan disamaratakan:
   - **(a) Karakter terdaftar, baru pertama kali dimainkan atau memulai sesi baru dari save repo** (nama cocok entri di `players.md`, TIDAK ada blok "Profil Karakter" yang ditempel/riwayat sebelumnya) ATAU **pemain menanyakan tentang karakter/player lain** → fetch `players.md` (link §1) atau langsung fetch file RAW karakter individual yang dituju di `players/<Nama_Karakter>.md` (misal: `https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players/Inggo.md`), muat data awalnya sebagai **titik mulai** narasi atau referensi informasi. `players.md` & folder `players/` dikelola oleh admin sebagai sumber save resmi.
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
| 00 | `00_CORE_RULES_AI_GM.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/00_CORE_RULES_AI_GM.md | Aturan mutlak, anti-cheat, format respon wajib, cheat-sheet formula — **selalu difetch pertama** |
| 👤 | `players.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/players.md | Katalog **data AWAL** karakter (statis, dikelola admin) — memuat link RAW ke file individual di `players/` |
| 01 | `01_WORLD_OVERVIEW_AND_CAPITAL.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/01_WORLD_OVERVIEW_AND_CAPITAL.md | Peta jarak dunia & Ibu Kota Tianjing |
| 02 | `02_CENTRAL_PLAINS.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/02_CENTRAL_PLAINS.md | Central Plains: kota, desa, sekte, NPC |
| 03 | `03_AZURE_MOUNTAIN_RANGE.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/03_AZURE_MOUNTAIN_RANGE.md | Azure Mountain Range |
| 04 | `04_SOUTHERN_DEMON_DOMAIN.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/04_SOUTHERN_DEMON_DOMAIN.md | Southern Demon Domain |
| 05 | `05_EASTERN_SEA_REGION.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/05_EASTERN_SEA_REGION.md | Eastern Sea Region |
| 06 | `06_NORTHERN_DESOLATE_TERRITORY.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/06_NORTHERN_DESOLATE_TERRITORY.md | Northern Desolate Territory |
| 07 | `07_WESTERN_SACRED_DESERTS.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/07_WESTERN_SACRED_DESERTS.md | Western Sacred Deserts |
| 08 | `08_CROSS_REGION_ORGANIZATIONS.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/08_CROSS_REGION_ORGANIZATIONS.md | Info broker, pegadaian, pembunuh bayaran, sanxiu, kriminal mortal |
| 09 | `09_CULTIVATION_LAW_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/09_CULTIVATION_LAW_SYSTEM.md | Realm, Hukum kultivasi, breakthrough, tribulasi, karma |
| 10 | `10_ECONOMY_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/10_ECONOMY_SYSTEM.md | Mata uang, tier/grade barang, harga jasa & aset |
| 11 | `11_VITALITY_HUNGER_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/11_VITALITY_HUNGER_SYSTEM.md | Formula HP, status luka, kelaparan |
| 12 | `12_COMBAT_SYSTEM.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/12_COMBAT_SYSTEM.md | Giliran, initiative, damage, defense, escape |
| 13 | `13_BESTIARY.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/13_BESTIARY.md | Monster & spirit beast per wilayah, ambush, loot |
| 14–37 | *(24 file sekte/dojo/organisasi individual)* | — | Lihat **§1a** di bawah untuk daftar lengkap per-file — **JANGAN** fetch semuanya sekaligus, cari nama sekte yang relevan lalu fetch HANYA file itu |
| 39 | `39_CUSTOM_EVENTS.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/39_CUSTOM_EVENTS.md | **Event khusus & peristiwa dunia** — diisi Admin, AI wajib cek di awal sesi |
| 40 | `40_CUSTOM_LAWS.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/40_CUSTOM_LAWS.md | **Hukum Kultivasi kustom** — buatan pemain/Admin, dicatat di sini agar resmi |
| 41 | `41_CUSTOM_SECTS.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/41_CUSTOM_SECTS.md | **Sekte/Dojo/Organisasi kustom** — buatan pemain/Admin, dicatat di sini agar resmi |
| 42 | `42_CUSTOM_TECHNIQUES.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/42_CUSTOM_TECHNIQUES.md | **Teknik & Jurus Kustom** — buatan pemain/Admin, dicatat di sini agar resmi |
| — | `README.md` | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/README.md | Dokumentasi setup untuk manusia (jarang perlu difetch AI) |

### 1a. Direktori Sekte, Dojo & Organisasi (24 File Individual)

> Setiap sekte/dojo/organisasi punya **file sendiri**, lengkap dengan hierarki, fasilitas, artefak/pusaka/seal-talisman, kurikulum teknik bertingkat, Hukum kultivasi detail, relasi antar-faksi, dan rahasia internal. **Fetch HANYA** link file yang relevan dengan situasi saat ini — jangan fetch banyak sekaligus.

**Central Plains**
| Sekte/Dojo | Link RAW (langsung klik/fetch) |
|---|---|
| Heavenly Sword Pavilion | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/14_HEAVENLY_SWORD_PAVILION.md |
| Profound Heaven Sect | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/15_PROFOUND_HEAVEN_SECT.md |
| Silver Rain Sword School | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/16_SILVER_RAIN_SWORD_SCHOOL.md |
| Dojo Bunga Aprikot | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/17_DOJO_BUNGA_APRIKOT.md |
| Dojo Godam Besi | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/18_DOJO_GODAM_BESI.md |

**Azure Mountain Range**
| Sekte/Dojo | Link RAW (langsung klik/fetch) |
|---|---|
| Golden Bell Monastery | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/19_GOLDEN_BELL_MONASTERY.md |
| Dojo Pahat Naga | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/20_DOJO_PAHAT_NAGA.md |

**Southern Demon Domain**
| Sekte/Dojo | Link RAW (langsung klik/fetch) |
|---|---|
| Demonic Flame Palace | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/21_DEMONIC_FLAME_PALACE.md |
| Nine Serpent Den | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/22_NINE_SERPENT_DEN.md |
| Seven Sins Cult | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/23_SEVEN_SINS_CULT.md |
| Blood Shadow Alliance | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/24_BLOOD_SHADOW_ALLIANCE.md |
| Dojo Bayangan Kelam | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/25_DOJO_BAYANGAN_KELAM.md |

**Eastern Sea Region**
| Sekte/Dojo | Link RAW (langsung klik/fetch) |
|---|---|
| Jade Purity Palace | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/26_JADE_PURITY_PALACE.md |
| Dojo Ombak Tenang | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/27_DOJO_OMBAK_TENANG.md |

**Northern Desolate Territory**
| Sekte/Dojo | Link RAW (langsung klik/fetch) |
|---|---|
| Whitecloud Medicine Hall | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/28_WHITECLOUD_MEDICINE_HALL.md |
| Ghost Valley Sect | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/29_GHOST_VALLEY_SECT.md |
| Dojo Cakar Serigala | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/30_DOJO_CAKAR_SERIGALA.md |

**Western Sacred Deserts**
| Sekte/Dojo | Link RAW (langsung klik/fetch) |
|---|---|
| Azure Cloud Temple | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/31_AZURE_CLOUD_TEMPLE.md |
| Dojo Mata Elang Pasir | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/32_DOJO_MATA_ELANG_PASIR.md |

**Lintas Wilayah**
| Organisasi | Link RAW (langsung klik/fetch) |
|---|---|
| Perkumpulan Pisau Sunyi | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/33_PERKUMPULAN_PISAU_SUNYI.md |
| Kelompok Racun Bayangan | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/34_KELOMPOK_RACUN_BAYANGAN.md |
| Serambi Seribu Bisik (info broker) | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/35_SERAMBI_SERIBU_BISIK.md |
| Rumah Gadai Giok Sejuk (bank tak resmi) | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/36_RUMAH_GADAI_GIOK_SEJUK.md |
| Perhimpunan Tabib Pengembara | https://raw.githubusercontent.com/aesher-gg/Wuxian_world/main/37_PERHIMPUNAN_TABIB_PENGEMBARA.md |

---

## 2. Alur Navigasi Otomatis (Trigger → Modul yang Difetch)

| Trigger dalam Roleplay | Modul yang Difetch | Catatan |
|---|---|---|
| Awal sesi (selalu) | `00_CORE_RULES_AI_GM.md` | Wajib pertama, lihat §0 |
| Awal sesi (setelah Bootstrap selesai) | `39_CUSTOM_EVENTS.md` | Cek apakah ada event aktif yang memengaruhi dunia |
| Karakter terdaftar di `players.md`, baru pertama kali dimainkan OR pemain menanyakan informasi karakter/player lain | `players.md` dan/atau `players/<Nama_Karakter>.md` | Muat/fetch data karakter dari link RAW individual sebagai titik mulai atau referensi informasi pemain/karakter lain |
| Melanjutkan karakter yang sudah pernah dimainkan | — | Pakai blok "Profil Karakter" terakhir yang ditempel/ada di riwayat chat — **jangan** fetch `players.md` / `players/` |
| Karakter benar-benar baru (tidak ada di `players.md`) | — | Ikuti `00` §1.6: minta Nama + Lokasi Awal |
| Karakter berada/menuju Central Plains | `02_CENTRAL_PLAINS.md` | Termasuk area ibu kota provinsi ini |
| Karakter berada/menuju Azure Mountain Range | `03_AZURE_MOUNTAIN_RANGE.md` | |
| Karakter berada/menuju Southern Demon Domain | `04_SOUTHERN_DEMON_DOMAIN.md` | |
| Karakter berada/menuju Eastern Sea Region | `05_EASTERN_SEA_REGION.md` | |
| Karakter berada/menuju Northern Desolate Territory | `06_NORTHERN_DESOLATE_TERRITORY.md` | |
| Karakter berada/menuju Western Sacred Deserts | `07_WESTERN_SACRED_DESERTS.md` | |
| Butuh konteks Ibu Kota Tianjing / peta jarak besar dunia | `01_WORLD_OVERVIEW_AND_CAPITAL.md` | |
| Bertemu info broker/pembunuh bayaran/sanxiu/kriminal mortal lintas wilayah | `08_CROSS_REGION_ORGANIZATIONS.md` | |
| Breakthrough realm / klaim teknik baru / cek Law Origin | `09_CULTIVATION_LAW_SYSTEM.md` | |
| Pemain menyebut Hukum kultivasi yang tidak ada di `09` | `40_CUSTOM_LAWS.md` | Cek apakah Hukum itu sudah dicatat Admin di file kustom |
| Transaksi, tawar-menawar, cek harga barang/jasa/aset | `10_ECONOMY_SYSTEM.md` | |
| Perlu hitung detail regen HP / efek kelaparan lanjut | `11_VITALITY_HUNGER_SYSTEM.md` | Formula dasarnya sudah ada ringkas di `00` §3 |
| Pertarungan resmi dimulai (giliran, initiative, damage) | `12_COMBAT_SYSTEM.md` | |
| Lawan monster/spirit beast liar, perjalanan lewat zona liar (ambush) | `13_BESTIARY.md` | Dipakai bersamaan dengan `12` |
| Karakter mau bergabung sekte/dojo, eksplorasi fasilitas sekte, belajar teknik bertingkat, atau cek hierarki/artefak sekte tertentu | Fetch langsung dari link RAW di §1a | Jangan rakit URL sendiri. Gunakan link yang sudah tertulis di kolom "Link RAW" tabel §1a. Pilih HANYA satu file yang sesuai dengan sekte yang sedang berinteraksi. |
| Pemain menyebut sekte yang tidak ada di `14`–`37` | `41_CUSTOM_SECTS.md` | Cek apakah sekte itu sudah dicatat Admin di file kustom |
| Pemain menyebut/mengklaim teknik yang tidak ada di file resmi | `42_CUSTOM_TECHNIQUES.md` | Cek apakah teknik itu sudah dicatat Admin di file kustom |
| Pemain minta bantuan setup GitHub / nanya cara pakai sistem ini | `README.md` | Ini file untuk manusia, sampaikan isinya ke pemain, bukan role-play |

**Efisiensi token:** jika sebuah modul sudah difetch sebelumnya dalam percakapan yang sama dan kondisinya belum berubah (mis. karakter masih di wilayah yang sama), **tidak perlu fetch ulang** — pakai isi yang sudah ada di riwayat chat.

---

## 3. Cara Kerja `players.md` & Folder `players/` (Manajemen Save File Karakter oleh Admin)

`players.md` dan file individual di folder `players/` berisi data karakter resmi pemain di core repository. File-file ini **hanya boleh diubah dan diperbarui oleh Admin (pemilik repo)** berdasarkan data Profil Karakter tersimpan yang dikirimkan oleh pemain.

> ✅ **Link katalog `players.md` dan file individual di `players/` sudah aktif.** Setiap karakter disimpan dalam file `.md` ringkas terpisah untuk menghindari batas ekstraksi teks AI (seperti limit 300 baris Qwen AI).

**Alur pemakaian & Sesi Baru:**
1. Pemain cukup menyebutkan nama karakternya (misal: `Inggo`) saat membuka chat/sesi baru.
2. AI GM akan men-fetch file `players/<Nama_Karakter>.md` dari core repository yang telah diperbarui oleh Admin.
3. Seluruh data di file karakter tersebut dimuat sebagai titik mulai sesi baru.
4. Selama sesi berlangsung, perkembangan karakter dilacak di dalam percakapan lewat blok Profil Karakter.
5. Pemain bebas menyalin Profil Karakter kapan saja dan mengirimkannya ke Admin untuk dimasukkan/diperbarui ke core repo (`players/<Nama_Karakter>.md`).

---

## 4. Batasan Penting yang Harus Diketahui Pemain

- **Tidak ada sistem save di dunia ini.** Katalog `players.md` dan folder `players/` murni lembar data AWAL karakter yang statis — bukan file yang mengikuti progres cerita.
- **Hanya admin (pemilik repo) yang boleh mengubah `players.md` dan folder `players/`.** AI tidak bisa dan tidak akan menulis, memperbarui, atau menyarankan perubahan pada file ini kapan pun, termasuk di akhir sesi.
- Perkembangan karakter selama roleplay (HP, item, breakthrough, lokasi, dst.) sepenuhnya hidup **di dalam riwayat percakapan** lewat blok "Profil Karakter" — bukan di file manapun di repo.
- **File `39_CUSTOM_EVENTS.md`, `40_CUSTOM_LAWS.md`, dan `41_CUSTOM_SECTS.md` dikelola sepenuhnya oleh Admin.** AI tidak boleh mengedit, menambah, atau menghapus isinya — hanya membaca dan menggunakan data yang sudah ada di dalamnya.
- Jika sebuah link 404/gagal fetch, itu paling sering karena: nama file salah huruf besar-kecil (GitHub case-sensitive), file belum ter-push ke branch `main`, atau repo tidak publik.

---

## 5. Ringkasan Dunia (satu baris, detail penuh di `01`)

Xianxia · Wuxia · Kultivasi Hardcore Realism — 7 wilayah besar, 9 Major Realm × 3 Stage, 5 Hukum kultivasi berbeda, ± 280 juta jiwa populasi, tanpa plot armor, semua mekanik tunduk formula anti-cheat di modul `09`–`13`.
