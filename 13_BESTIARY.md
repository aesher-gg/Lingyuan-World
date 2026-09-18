
| Modifier | Nilai |
|---|---|
| DangerModifier — Wilayah Normal | ×1,0 |
| DangerModifier — Wilayah Liar/Hutan Belantara | ×2,0 |
| DangerModifier — Zona Terlarang | ×4,0 |
| TimeModifier — Siang hari | ×1,0 |
| TimeModifier — Malam hari | ×2,0 (mayoritas monster, khususnya Bayangan/Yin, lebih aktif malam) |

**Contoh:** melintasi Endless Primeval Forest (Zona Liar, ×2,0) di malam hari (×2,0): `AmbushChance = 5% × 2,0 × 2,0 = 20% per jam perjalanan`.

📌 **Anti-cheat:** AI GM yang melempar kemungkinan ambush tiap interval perjalanan — bukan player memutuskan sendiri "monster muncul" atau "tidak ada monster sama sekali" tanpa alasan naratif kuat (seperti membawa jimat pengusir/formasi pelindung tervalidasi).

---

## 💎 4. Sistem Drop Loot

`LootDropRate = BaseDropRate(rarity)` — dilempar AI GM **setelah** monster benar-benar dikalahkan dalam roleplay.

| Rarity | BaseDropRate | Contoh |
|---|---|---|
| Umum (Common) — bahan dasar tubuh monster | 70–90% | Kulit, taring, bulu, inti qi kecil |
| Jarang (Rare) — organ/inti spiritual | 20–40% | Inti elemen, kelenjar racun, sisik langka |
| Legendaris (hanya monster Ancient Guardian/boss) | 5–15%, atau 100% sekali seumur (unique kill pertama) | Pusaka/bahan Tier 7+, artefak bernama |

Semua loot mengikuti Tier & Grade Sistem Ekonomi (`10_ECONOMY_SYSTEM.md` §2) sesuai Tier monster tersebut, dan **WAJIB dicatat di Item Origin Log** sebelum bisa dijual/dipakai breakthrough (`10_ECONOMY_SYSTEM.md` §7).

---

## 📖 5. Daftar Monster per Wilayah

---

### 🏯 Central Plains
*(lihat `02_CENTRAL_PLAINS.md`)*

Wilayah paling padat dan "aman" relatif, tapi bukan tanpa bahaya. Monster di sini cenderung lebih rendah tier-nya, tapi tetap mematikan bagi pemula.

| Monster | Kategori | Tier (Realm Setara) | HP | Attack Power | Kemampuan & Deskripsi | Loot Drop |
|---|---|---|---|---|---|---|
| Roh Prajurit Gugur | 👻 Undead | 3, Awal | 225 | 67 | Muncul dari Ancient Battlefield of Gods, mengembara membawa tombak karatan, menyerang siapa pun yang dianggap "musuh lama"-nya yang sudah lama mati. Kebal senjata fisik biasa, hanya bisa dilukai qi. Bergerak lambat tapi tak kenal lelah. | Umum: Serpihan Baju Zirah Kuno (Tier 2) — Jarang: Inti Roh Prajurit (Tier 4, bahan Hukum Roh Hantu) |
| Naga Sungai Kecil | 🐺 Spirit Beast | 2, Menengah | 90 | 22 | Menghuni Sungai Emas & Golden River Basin, menyerang perahu kecil yang lewat malam hari, gemar mengoleksi barang mengkilap yang jatuh ke sungai. Bisa menyemburkan air bertekanan tinggi dari jarak 10 meter. | Umum: Sisik Naga Sungai (Tier 1) — Jarang: Mutiara Sungai Kecil (Tier 3) |
| Macan Gunung Tri-Sect | 🐺 Spirit Beast | 3, Menengah | 450 | 112 | Sangat teritorial di lereng Tri-Sect Mountain, sering jadi alasan sekte-sekte menghindari area tertentu gunung ini selain sengketa klaim wilayah. Bisa melompat hingga 15 meter dan menerkam dari ketinggian. | Umum: Kulit Macan Gunung (Tier 2) — Jarang: Taring Macan Bertuah (Tier 3) |
| Babi Hutan Raksasa | 🐺 Spirit Beast | 2, Awal | 75 | 18 | Menghuni hutan di sekitar Desa Xingcun dan Qingshui, biasanya tidak agresif kecuali diganggu atau saat musim kawin. Bisa berlari kencang menabrak pohon kecil. | Umum: Gading Babi Hutan (Tier 1) — Jarang: Daging Babi Bertuah (Tier 2) |
| Serigala Malam Berbulu Hitam | 🐺 Spirit Beast | 3, Awal | 300 | 75 | Berkelana di sekitar perbatasan Central Plains–Southern Demon Domain, sering memangsa kafilah kecil yang bepergian malam hari. Bergerak dalam kawanan 3–7 ekor, sangat koordinatif. | Umum: Bulu Serigala Hitam (Tier 2) — Jarang: Taring Serigala Beracun (Tier 3) |
| Ular Tanah Raksasa | 🌿 Flora/Plant Creature | 4, Awal | 1.562 | 250 | Menghuni area persawahan dan ladang di Central Plains, bersembunyi di dalam tanah, menyerang dengan menjerat korban lalu menariknya ke bawah. Sulit dideteksi sebelum menyerang. | Umum: Kulit Ular Tanah (Tier 3) — Jarang: Inti Bumi (Tier 4) |
| Elang Malam Pemburu | 🐺 Spirit Beast | 4, Awal | 1.250 | 450 | Mengincar korban dari udara di Central Plains bagian selatan, menukik dengan kecepatan luar biasa — target sering tak sempat bereaksi. Aktif di senja dan malam hari. | Umum: Bulu Elang Malam (Tier 3) — Jarang: Cakar Elang Tajam (Tier 4) |
| Kera Batu | 🐺 Spirit Beast | 3, Menengah | 450 | 112 | Menghuni perbukitan batu di sekitar Tri-Sect Mountain, sangat agresif, suka melempar batu besar dari ketinggian. Bergerak dalam kelompok 5–15 ekor. | Umum: Kulit Kera Batu (Tier 2) — Jarang: Batu Inti Kera (Tier 3) |
| Naga Lumpur | 🔥 Elemental (Tanah) | 4, Menengah | 2.812 | 675 | Menghuni rawa-rawa di sekitar Sungai Emas, makhluk purba berbentuk ular raksasa dengan sisik berlumpur. Bisa menenggelamkan korban ke dalam lumpur dalam hitungan detik. | Umum: Sisik Lumpur (Tier 3) — Jarang: Inti Lumpur Purba (Tier 4) |
| Kalajengking Merah Kabut | 🐛 Insect/Gu Swarm | 4, Awal | 1.000 | 375 | Menghuni Lembah Kabut Merah (Chiwu Valley), bersembunyi di dalam tanah lembap dan kabut merah. Sengatan ekornya menyuntikkan racun pengendap Qi. | Umum: Cangkang Kalajengking Merah (Tier 3) — Jarang: Kelenjar Racun Pemurni (Tier 4) |
| Monster Akar Purba Raksasa | 🌿 Flora/Plant Creature | 5, Awal | 5.000 | 1.875 | Menghuni Hutan Purba Akar Kuno, wujud sulur kayu purba beracun yang menjerat mangsa ke rawa lumpur isap Qi. | Umum: Kayu Akar Purba (Tier 4) — Jarang: Inti Kehidupan Purba (Tier 5) |

---

### ⛰️ Azure Mountain Range
*(lihat `03_AZURE_MOUNTAIN_RANGE.md`)*

Wilayah pegunungan dengan qi kaya, monster di sini lebih kuat dan lebih bervariasi. Hutan Bambu Berbisik (Whispering Bamboo Forest) adalah zona paling berbahaya di wilayah ini.

| Monster | Kategori | Tier (Realm Setara) | HP | Attack Power | Kemampuan & Deskripsi | Loot Drop |
|---|---|---|---|---|---|---|
| Kabut Pemakan Arah | 👤 Bayangan/Yin | 5, Awal | 3.750 | 2.812 | Menghuni Void Mist Forest, tak berwujud jelas — hanya kabut tebal yang membingungkan indra arah korban hingga tersesat selamanya. Menyerang dari segala arah sekaligus tanpa peringatan. | Umum: Esens Kabut Sesat (Tier 4) — Jarang: Inti Disorientasi (Tier 5, bahan formasi ilusi) |
| Ular Salju Lembah Bunga | 🔥 Elemental (Es/Racun) | 2, Awal | 50 | 18 | Menjaga Lembah Bunga Salju secara alami, bisanya justru jadi bahan penawar racun langka yang diperebutkan Whitecloud Medicine Hall & Nine Serpent Den. | Umum: Bisa Ular Salju (Tier 1) — Jarang: Kelenjar Penawar Langka (Tier 3) |
| Burung Guntur Puncak | 🔥 Elemental (Petir) | 4, Menengah | 1.875 | 675 | Bersarang di Heaven Reaching Peak, menyerang dengan sambaran petir kecil saat merasa sarangnya terancam, sangat sensitif pada pendaki yang berisik. | Umum: Bulu Berlistrik (Tier 3) — Jarang: Inti Guntur Kecil (Tier 4, bahan formasi petir) |
| Harimau Es | 🐺 Spirit Beast | 4, Menengah | 1.875 | 675 | Menghuni puncak-puncak tinggi Azure Mountain Range, bulunya putih kebiruan menyatu dengan salju. Menyerang dari jarak dekat dengan cakaran dingin yang bisa membekukan luka. | Umum: Kulit Harimau Es (Tier 3) — Jarang: Cakar Es (Tier 4) |
| Babi Hutan Bertanduk | 🐺 Spirit Beast | 4, Awal | 1.250 | 450 | Menghuni Zona Tengah Hutan Bambu Berbisik. Berkelompok dalam keluarga 3–8 ekor. Tanduknya tajam seperti tombak bambu, bisa menusuk zirah besi tipis. Sangat agresif jika satu anggota terancam. | Umum: Tanduk Babi Hutan (Tier 3) — Jarang: Kulit Tebal Bertuah (Tier 3) |
| Roh Bambu (Bamboo Spirit) | 👻 Undead | 4, Awal | 1.687 | 450 | Menghuni Zona Tengah Hutan Bambu Berbisik. Berwujud humanoid ramping dari bambu, bergerak tanpa suara. Menyerang dengan serangan qi tajam dari jarak dekat. Muncul berkelompok 2–5 entitas. | Umum: Serpihan Bambu Giok Kecil (Tier 3) — Jarang: Inti Roh Bambu (Tier 4) |
| Prajurit Bambu (Bamboo Warrior) | 🗿 Ancient Guardian | 6, Awal | 125.000 | 16.875 | Menghuni Zona Dalam Hutan Bambu Berbisik. Golem bambu raksasa setinggi 5 meter, tubuhnya dari bambu giok yang tak bisa ditembus senjata biasa. Berjaga sendirian, bergiliran di beberapa posisi. Tidak menyerang pengunjung yang langsung pergi — hanya menghalangi mereka yang mencoba masuk ke zona paling dalam. | Legendaris: Serpihan Bambu Giok Murni (Tier 6, bahan craft Grade 4+) |
| Ular Bambu (Bamboo Snake) | 🗿 Ancient Guardian (Mitos) | 8+ (Tidak Diketahui) | ??? | ??? | Legenda mengatakan bahwa di pusat Hutan Bambu Berbisik, tepat di atas urat nadi spiritual utama, bersemayam Ular Bambu — iblis purba berwujud Ular dengan sisik dari bambu giok. Konon ia adalah penjaga terakhir dari "Hati Hutan" (Heart of the Forest). **Belum pernah terbukti kebenarannya** — tak ada yang selamat dari zona dalam untuk bercerita. | Tidak Diketahui |
| Kera Bambu Abu-abu | 🐺 Spirit Beast | 2, Awal | 60 | 15 | Menghuni Zona Luar Hutan Bambu Berbisik. Berkoloni 10–30 ekor, dipimpin satu jantan alfa. Agresif jika teritorinya diganggu, suka melempar ranting, buah, atau kotoran. Bergerak sangat lincah di antara batang bambu. | Umum: Bulu Kera Abu-abu (Tier 1) — Jarang: Batu Giok Kecil (Tier 2) |
| Ular Hijau Daun | 🐺 Spirit Beast | 2, Awal | 60 | 15 | Menghuni Zona Luar Hutan Bambu Berbisik. Bersarang berkelompok 5–15 ekor di rumpun bambu. Bisa melompat dari cabang ke cabang. Racunnya menyebabkan mati rasa sementara (1–2 jam), tidak mematikan bagi kultivator. | Umum: Taring Beracun (Tier 1) — Jarang: Sisik Hijau (Tier 2, bahan jimat) |
| Elang Puncak Salju | 🐺 Spirit Beast | 4, Awal | 1.250 | 450 | Menghuni puncak-puncak tertinggi Azure Mountain Range, memangsa kambing gunung dan kadang anak-anak kera. Terbang tinggi dan menukik dengan kecepatan luar biasa. | Umum: Bulu Elang Salju (Tier 3) — Jarang: Cakar Elang Puncak (Tier 4) |
| Ular Naga Gunung | 🐺 Spirit Beast | 5, Awal | 7.500 | 1.875 | Ular raksasa yang menghuni gua-gua dalam di Azure Mountain Range, konon keturunan naga kuno. Sisiknya berwarna hijau giok, bisa menyemburkan qi beracun dari jarak jauh. Sangat teritorial. | Umum: Sisik Ular Naga (Tier 4) — Jarang: Inti Ular Naga (Tier 5, bahan terobosan) |
| Binatang Es Abadi (Frost Abyss Beast) | 🗿 Ancient Guardian | 6, Puncak | 125.000 | 33.750 | Makhluk purba raksasa bertanduk es yang menjaga kedalaman Jurang Es Abadi. Kulit tebal es giok kebal serangan fisik ringan; napas es membekukan jaringan tubuh (-20% Dex). | Umum: Tanduk Es Abadi (Tier 5) — Legendaris: Inti Jiwa Es Purba (Tier 7) |
| Ular Bambu Giok Purba | 🐺 Spirit Beast | 5, Menengah | 7.500 | 2.812 | Menghuni Lembah Embun Lautan Bambu, berkulit sekeras bambu giok transparan, melilit target dan meremukkan pertahanan raga. | Umum: Sisik Bambu Giok (Tier 4) — Jarang: Mutiara Embun Bambu (Tier 5) |

---

### 🔥 Southern Demon Domain
*(lihat `04_SOUTHERN_DEMON_DOMAIN.md`)*

Wilayah paling berbahaya di dunia. Monster di sini lebih buas, lebih agresif, dan sering berafiliasi dengan faksi iblis.

| Monster | Kategori | Tier (Realm Setara) | HP | Attack Power | Kemampuan & Deskripsi | Loot Drop |
|---|---|---|---|---|---|---|
| Serigala Api Neraka | 🔥 Elemental (Api) | 4, Awal | 1.250 | 450 | Penghuni asli Hellfire Island, sengaja dipakai Demonic Flame Palace sebagai "makhluk uji" murid Zona Luar & Tengah pulau ujian. Kulitnya membara terus-menerus. Bisa menyemburkan api dari mulut. | Umum: Bulu Api Abadi (Tier 3) — Jarang: Inti Api Serigala (Tier 4, bahan Hukum Qi Naga Api) |
| Ular Berbisa Liar Rawa | 🔥 Elemental (Racun) | 3, Awal | 250 | 90 | Berkeliaran liar di Thousand Poison Marsh, tidak berafiliasi dengan Nine Serpent Den, kadang malah diburu sekte tersebut untuk diambil bisanya. Gigitannya bisa melumpuhkan dalam hitungan detik. | Umum: Bisa Ular Rawa (Tier 2) — Jarang: Kulit Ular Kebal Racun (Tier 3) |
| Kutu Iblis Pemakan Qi | 🐛 Insect/Gu Swarm | 1, Puncak (per individu) | 0* (×20–50 individu) | 0* (per individu, menumpuk) | Menghuni Endless Primeval Forest dalam kawanan besar, tiap gigitan menyedot sedikit Qi korban — berbahaya bukan karena kuat sendiri, tapi karena jumlahnya. Bisa menghabiskan Qi seorang kultivator Realm 3 dalam hitungan menit jika tak dilawan. | Umum: Cangkang Kutu Iblis (Tier 1, dijual per kilo) — Jarang: Inti Kawanan (Tier 2, hanya drop dari kutu ratu) |
| Mayat Hidup Rawa Jiwa Tenggelam | 👻 Undead | 5, Menengah | 8.437 | 2.531 | Penghuni Rawa Jiwa Tenggelam, ditakuti bahkan oleh Ghost Valley Sect sendiri. Bergerak lambat tapi cengkeramannya menyerap vitalitas korban perlahan. Tubuhnya kebal terhadap senjata fisik biasa. | Umum: Daging Membusuk Bertuah (Tier 4) — Jarang: Inti Jiwa Tenggelam (Tier 5, bahan Hukum Roh Hantu langka) |
| Kalajengking Raksasa Abu Vulkanik | 🐺 Spirit Beast | 3, Puncak | 600 | 150 | Menghuni Perbukitan Abu Vulkanik, kulitnya tahan panas ekstrem, sengatannya melumpuhkan sementara. Bergerak cepat di atas pasir vulkanik. | Umum: Cangkang Kalajengking (Tier 2) — Jarang: Racun Sengat Vulkanik (Tier 3) |
| Anjing Neraka Berkepala Tiga | 🔥 Elemental (Api) | 5, Awal | 7.500 | 1.875 | Menghuni sekitar Demonic Flame Palace, dipelihara oleh iblis tingkat tinggi sebagai penjaga. Setiap kepala bisa menyemburkan api dengan warna berbeda — merah, biru, dan hitam. | Umum: Bulu Anjing Neraka (Tier 4) — Jarang: Inti Api Tiga Warna (Tier 5) |
| Piton Beracun Thousand Poison Marsh | 🐺 Spirit Beast | 4, Menengah | 1.875 | 675 | Ular raksasa yang menghuni Thousand Poison Marsh, tubuhnya sebesar paha manusia, panjang hingga 15 meter. Bisa menyemburkan racun dari jarak 20 meter. | Umum: Kulit Piton Beracun (Tier 3) — Jarang: Kelenjar Racun Piton (Tier 4) |
| Roh Darah Bukit Tengkorak | 👻 Undead | 5, Awal | 5.625 | 2.812 | Menghuni Bukit Tengkorak Seribu, terdiri dari darah dan tulang prajurit yang gugur di masa lalu. Menyerang dengan ledakan qi berdarah. | Umum: Esens Darah Purba (Tier 4) — Jarang: Inti Roh Darah (Tier 5) |
| Belalang Sembah Iblis Merah | 🐛 Insect/Gu Swarm | 3, Menengah | 450 | 112 | Serangga raksasa sebesar manusia, bersayap merah menyala. Bergerak cepat dan bisa memotong daging dengan cakarnya yang tajam. Sering muncul di Crimson Blood Jungle. | Umum: Sayap Belalang Merah (Tier 2) — Jarang: Cakar Belalang (Tier 3) |
| Tawon Racun Rawa | 🐛 Insect/Gu Swarm | 2, Menengah | 90 | 22 | Kawanan tawon sebesar kepalan tangan, sarangnya di pepohonan rawa. Sengatannya menyebabkan demam tinggi dan halusinasi. | Umum: Sarang Tawon Racun (Tier 1) — Jarang: Sengat Tawon (Tier 2) |
| Siluman Bayangan Malam | 👤 Bayangan/Yin | 6, Awal | 15.000 | 8.437 | Siluman tak berwujud yang muncul di malam hari di Southern Demon Domain, memangsa kultivator yang bepergian sendirian. Menyerang dari belakang tanpa suara. | Umum: Esens Bayangan Malam (Tier 5) — Jarang: Inti Bayangan (Tier 6) |
| Ular Api Lahar | 🔥 Elemental (Api) | 5, Menengah | 7.500 | 2.812 | Menghuni Lembah Darah Mendidih (Boiling Blood Ravine), berenang di lahar mendidih. Menyemburkan semburan darah api yang membakar Qi dan vitalitas target secara bersamaan. | Umum: Sisik Lahar Merah (Tier 4) — Jarang: Inti Api Lahar Mendidih (Tier 5) |
| Iblis Pohon Tulang Merah | 👻 Undead | 5, Puncak | 10.000 | 3.750 | Menghuni Hutan Tulang Merah Beracun, bergerak menyerap darah dan menembakkan duri tulang beracun Miasma. | Umum: Kayu Tulang Merah (Tier 4) — Jarang: Esens Darah Miasma (Tier 5) |

---

### 🌊 Eastern Sea Region
*(lihat `05_EASTERN_SEA_REGION.md`)*

Wilayah maritim yang luas. Monster di sini sebagian besar adalah makhluk laut dengan elemen air.

| Monster | Kategori | Tier (Realm Setara) | HP | Attack Power | Kemampuan & Deskripsi | Loot Drop |
|---|---|---|---|---|---|---|
| Kraken Muda Laut Timur | 🔥 Elemental (Air) | 5, Puncak | 12.500 | 4.500 | Menghuni perairan dalam Eastern Sea, menyerang kapal besar yang berlayar terlalu jauh dari jalur aman, tentakelnya bisa menghancurkan lambung kapal kecil dalam sekali lilitan. | Umum: Tentakel Kraken (Tier 4) — Jarang: Inti Air Dalam (Tier 5, bahan Hukum Dao Abadi varian Air) |
| Siput Mutiara Iblis | 🐺 Spirit Beast | 2, Awal | 60 | 15 | Bersembunyi di dasar laut dekat Desa Zhenzhu, cangkangnya berisi mutiara spiritual palsu yang bisa meledak jadi racun jika dipaksa dibuka tanpa teknik yang benar. | Umum: Cangkang Siput (Tier 1) — Jarang: Mutiara Semu (Tier 2, bisa dimurnikan jadi Mutiara Spiritual asli oleh tabib ahli) |
| Hiu Sentinel Liar | 🐺 Spirit Beast | 3, Menengah | 450 | 112 | Varian liar dari hiu yang biasa dijinakkan Jade Purity Palace, agresif pada siapa pun yang bukan anggota sekte tersebut. Bisa mendeteksi darah dari jarak 5 kilometer. | Umum: Kulit Hiu Sentinel (Tier 2) — Jarang: Gigi Hiu Bertuah (Tier 3) |
| Kawanan Camar Badai | 🐛 Insect/Gu Swarm (setara) | 1, Awal (per individu) | 0* (×10–30 ekor) | 0* (per individu) | Berkerumun di sekitar Floating Cloud Archipelago saat badai, lebih mengganggu daripada mematikan, tapi bisa membutakan pandangan pelaut dalam jumlah besar. | Umum: Bulu Camar (Tier 1, dijual per ikat) |
| Ular Laut Raksasa | 🐺 Spirit Beast | 4, Menengah | 1.875 | 675 | Ular laut sepanjang 20 meter, menghuni perairan dalam. Bisa menenggelamkan kapal kecil dengan melilitnya. | Umum: Sisik Ular Laut (Tier 3) — Jarang: Inti Ular Laut (Tier 4) |
| Gurita Raksasa | 🐺 Spirit Beast | 4, Awal | 1.250 | 450 | Menghuni karang-karang dalam, tentakelnya bisa meraih korban dari jarak 10 meter. Sering menyerang penyelam mutiara di Desa Zhenzhu. | Umum: Tentakel Gurita (Tier 3) — Jarang: Tinta Gurita Raksasa (Tier 4) |
| Penyu Raksasa | 🗿 Ancient Guardian | 6, Awal | 62.500 | 16.875 | Penyu purba yang menghuni perairan dalam Eastern Sea, usianya dipercaya ribuan tahun. Menjaga pulau-pulau suci, tidak agresif kecuali diganggu. | Umum: Cangkang Penyu (Tier 5) — Legendaris: Inti Penyu Purba (Tier 7) |
| Lumba-lumba Iblis | 🐺 Spirit Beast | 3, Awal | 300 | 75 | Varian iblis dari lumba-lumba, lebih agresif dan cerdik. Sering menggiring kapal ke perairan berbahaya dengan sengaja. | Umum: Kulit Lumba-lumba Iblis (Tier 2) — Jarang: Gigi Lumba-lumba (Tier 3) |
| Hiu Putih Raksasa | 🐺 Spirit Beast | 5, Awal | 7.500 | 1.875 | Hiu raksasa yang memangsa kapal-kapal besar di jalur laut Eastern Sea. Mulutnya bisa menelan manusia utuh. | Umum: Kulit Hiu Putih (Tier 4) — Jarang: Gigi Hiu Putih (Tier 5) |
| Paus Iblis Pemakan Kapal | 🗿 Ancient Guardian | 7, Awal | 390.625 | 56.250 | Paus raksasa yang dikutuk, muncul sekali setiap beberapa dekade. Menabrak kapal dengan kekuatan yang bisa menghancurkan kapal perang. | Legendaris: Tulang Paus Iblis (Tier 7) — Legendaris: Inti Paus Purba (Tier 8) |
| Kuda Laut Iblis | 🐺 Spirit Beast | 2, Menengah | 90 | 22 | Makhluk kecil beracun yang bersembunyi di rumput laut. Sengatannya menyebabkan kelumpuhan sementara. | Umum: Sisik Kuda Laut (Tier 1) — Jarang: Racun Kuda Laut (Tier 2) |
| Gurita Karang Gelap | 🐺 Spirit Beast | 5, Puncak | 10.000 | 3.750 | Menghuni Palung Karang Gelap (Canghai Abyss), menggunakan kamuflase kegelapan dasar laut. Tentakelnya menyerap Qi target yang dililit. | Umum: Tentakel Karang Gelap (Tier 4) — Jarang: Tinta Pemikat Bayangan (Tier 5) |
| Kepiting Bakau Besi Hitam | 🐺 Spirit Beast | 4, Puncak | 2.000 | 750 | Menghuni Hutan Bakau Naga Hitam, memiliki cangkang sekeras besi baja dan supitu pelumat perahu. | Umum: Cangkang Bakau Besi (Tier 3) — Jarang: Supit Besi Hitam (Tier 4) |

---

### ❄️ Northern Desolate Territory
*(lihat `06_NORTHERN_DESOLATE_TERRITORY.md`)*

Wilayah dingin dan tandus. Monster di sini tangguh dan tahan terhadap suhu ekstrem.

| Monster | Kategori | Tier (Realm Setara) | HP | Attack Power | Kemampuan & Deskripsi | Loot Drop |
|---|---|---|---|---|---|---|
| Serigala Es Abadi | 🗿 Ancient Guardian | 6, Awal | 62.500 | 16.875 | Penghuni legendaris Eternal Frost Peak, dipercaya sudah hidup ratusan tahun, auranya bisa membekukan darah dari jarak jauh. Sangat jarang terlihat langsung. | Umum: Bulu Es Abadi (Tier 5) — Legendaris: Inti Es Purba (Tier 7, bahan Tribulasi Realm 7→8 varian es) |
| Roh Beku Bukit Tulang | 👻 Undead | 4, Awal | 1.125 | 337 | Menghuni Bukit Tulang Beku, sisa jenderal-jenderal kuno yang gugur, mengembara mencari "pasukan" untuk direkrut kembali — berbahaya bagi yang lewat sendirian di malam hari. | Umum: Serpihan Tulang Beku (Tier 3) — Jarang: Inti Roh Jenderal (Tier 4) |
| Beruang Salju Raksasa | 🐺 Spirit Beast | 3, Menengah | 450 | 112 | Menghuni sekitar Desa Xueying, biasanya tidak menyerang kecuali sarangnya terancam atau musim dingin ekstrem membuatnya kelaparan. | Umum: Kulit Beruang Salju (Tier 2) — Jarang: Cakar Beruang Bertuah (Tier 3) |
| Angin Menjerit Berwujud | 🔥 Elemental (Angin/Suara) | 4, Menengah | 1.875 | 675 | Menghuni Lembah Angin Menjerit, berwujud pusaran angin yang mengeluarkan suara mirip jeritan manusia, bisa merobek kulit tanpa perlindungan Qi. | Umum: Esens Angin Menjerit (Tier 3) — Jarang: Inti Suara Ganas (Tier 4, bahan formasi suara) |
| Rubah Es Berekor Sembilan | 🐺 Spirit Beast (Langka) | 6, Menengah | 56.250 | 14.062 | Sangat jarang terlihat, dipercaya sebagai pertanda keberuntungan atau bencana tergantung sikap yang menemuinya. Berkelana bebas di seluruh Northern Territory. | Umum: Bulu Ekor Rubah (Tier 5) — Legendaris: Inti Rubah Sembilan Ekor (Tier 6, sangat diburu alkemis) |
| Mammoth Es Raksasa | 🗿 Ancient Guardian | 5, Awal | 7.500 | 1.875 | Mammoth purba yang masih hidup di padang es Northern Territory. Tubuhnya ditutupi bulu tebal dan gading es yang bisa menembus zirah besi. | Umum: Gading Mammoth (Tier 4) — Jarang: Kulit Mammoth (Tier 5) |
| Serigala Es Kecil | 🐺 Spirit Beast | 2, Awal | 60 | 15 | Serigala kecil yang hidup berkelompok di sekitar Desa Xueying. Tidak terlalu agresif, tapi berbahaya dalam jumlah besar. | Umum: Bulu Serigala Es (Tier 1) — Jarang: Taring Serigala Es (Tier 2) |
| Elang Salju Raksasa | 🐺 Spirit Beast | 4, Awal | 1.250 | 450 | Elang raksasa yang bersarang di puncak-puncak es. Bisa membawa mangsa sebesar manusia dalam satu cengkeraman. | Umum: Bulu Elang Salju (Tier 3) — Jarang: Cakar Elang Salju (Tier 4) |
| Ular Es | 🔥 Elemental (Es) | 3, Awal | 300 | 75 | Ular kecil berwarna putih bening yang bersembunyi di bawah salju. Gigitannya menyebabkan rasa dingin yang melumpuhkan. | Umum: Sisik Ular Es (Tier 2) — Jarang: Bisa Ular Es (Tier 3) |
| Roh Salju | 👻 Undead | 3, Puncak | 600 | 150 | Roh halus yang muncul saat badai salju. Menyerang dengan menerbangkan salju ke mata korban lalu menusuk dari belakang. | Umum: Serpihan Salju Bertuah (Tier 2) — Jarang: Inti Roh Salju (Tier 3) |
| Yeti Gunung Es | 🐺 Spirit Beast | 5, Awal | 7.500 | 1.875 | Makhluk humanoid berbulu putih yang menghuni pegunungan es. Tingginya 3 meter, sangat kuat dan agresif jika teritorinya diganggu. | Umum: Bulu Yeti (Tier 4) — Jarang: Tulang Yeti (Tier 5) |
| Naga Es Purba | 🗿 Ancient Guardian | 8, Awal | 1.562.500 | 421.875 | Legenda hidup yang konon menjaga rahasia Eternal Frost Peak. Sangat jarang muncul — pertarungan dengannya setara peristiwa besar. | Legendaris: Sisik Naga Es (Tier 8) — Legendaris: Inti Es Purba Abadi (Tier 9) |
| Monster Badai Salju Gulch | 👤 Bayangan/Yin | 5, Awal | 5.000 | 1.875 | Menghuni Lembah Angin Beku (Frostwind Gulch), tercipta dari kumpulan roh pemburu yang tewas kedinginan. Menerkam target saat pandangan terhalang badai salju. | Umum: Esens Angin Beku (Tier 4) — Jarang: Inti Badai Es (Tier 5) |
| Serigala Pinus Es Purba | 🐺 Spirit Beast | 5, Awal | 5.000 | 1.875 | Menghuni Hutan Salju Pinus Kuno, bergerak sangat cepat di atas salju, melesatkan pecahan jarum pinus es dari bulunya. | Umum: Bulu Pinus Es (Tier 4) — Jarang: Taring Es Purba (Tier 5) |

---

### 🏜️ Western Sacred Deserts
*(lihat `07_WESTERN_SACRED_DESERTS.md`)*

Wilayah gurun paling ekstrem. Monster di sini tangguh, tahan panas, dan sering bersembunyi di bawah pasir.

| Monster | Kategori | Tier (Realm Setara) | HP | Attack Power | Kemampuan & Deskripsi | Loot Drop |
|---|---|---|---|---|---|---|
| Cacing Pasir Raksasa | 🐺 Spirit Beast | 5, Awal | 7.500 | 1.875 | Bersembunyi di bawah Bukit Pasir Menyanyi dan sekitarnya, menyerang dari bawah tanah tanpa peringatan — alasan utama kafilah selalu bergerak berkelompok dan tak pernah berjalan sendirian di gurun terbuka. | Umum: Kulit Cacing Pasir (Tier 4) — Jarang: Inti Getaran Bawah Tanah (Tier 5) |
| Elang Pasir Iblis | 🐺 Spirit Beast | 3, Awal | 300 | 75 | Menyambar dari udara di sekitar Reruntuhan Gushatta, sering mengincar barang mengkilap yang dibawa penjelajah. | Umum: Bulu Elang Pasir (Tier 2) — Jarang: Cakar Elang Bertuah (Tier 3) |
| Skorpion Emas Legendaris | 🗿 Ancient Guardian | 6, Puncak | 125.000 | 33.750 | Penjaga tak resmi Formasi Batu Buddha Tidur, konon terikat sumpah kuno menjaga reruntuhan biara — hanya menyerang mereka yang mencoba merusak formasi, damai pada peziarah biasa. | Umum: Cangkang Skorpion Emas (Tier 5) — Legendaris: Racun Emas Purba (Tier 7, bahan langka Hukum Gu Karma) |
| Ular Pasir | 🐺 Spirit Beast | 2, Awal | 60 | 15 | Ular kecil yang bersembunyi di bawah pasir, menyerang dengan cepat lalu kabur. Racunnya menyebabkan demam tinggi. | Umum: Sisik Ular Pasir (Tier 1) — Jarang: Bisa Ular Pasir (Tier 2) |
| Kadal Gurun Raksasa | 🐺 Spirit Beast | 3, Menengah | 450 | 112 | Kadal sebesar manusia yang berlari cepat di atas pasir. Bisa memanjat tebing batu dengan mudah. | Umum: Kulit Kadal Gurun (Tier 2) — Jarang: Cakar Kadal (Tier 3) |
| Rubah Pasir Ekor Sembilan | 🐺 Spirit Beast (Langka) | 5, Menengah | 8.437 | 2.531 | Varian rubah gurun yang sangat langka, konon membawa keberuntungan bagi yang melihatnya. Bulunya berwarna keemasan. | Umum: Bulu Rubah Pasir (Tier 4) — Legendaris: Inti Rubah Pasir (Tier 6) |
| Burung Phoenix Api Gurun | 🔥 Elemental (Api) | 7, Awal | 390.625 | 56.250 | Legenda burung api yang konon bersarang di Bukit Pasir Menyanyi. Muncul sekali setiap seratus tahun. | Legendaris: Bulu Phoenix (Tier 7) — Legendaris: Inti Api Abadi (Tier 8) |
| Kumbang Pasir Raksasa | 🐛 Insect/Gu Swarm | 3, Awal | 250 | 90 | Kumbang sebesar kepalan tangan yang hidup berkoloni di bawah pasir. Bisa menggigit melalui kulit tipis. | Umum: Cangkang Kumbang Pasir (Tier 2) — Jarang: Inti Kumbang (Tier 3) |
| Laba-laba Pasir Raksasa | 🐺 Spirit Beast | 4, Awal | 1.250 | 450 | Laba-laba sebesar kuda yang bersembunyi di bawah pasir, menjebak mangsa dengan jaring sutra yang kuat. | Umum: Kaki Laba-laba (Tier 3) — Jarang: Jaring Sutra (Tier 4) |
| Naga Pasir | 🗿 Ancient Guardian | 7, Awal | 390.625 | 56.250 | Naga gurun purba yang konon menjaga reruntuhan kota kuno. Tubuhnya terbuat dari pasir dan batu. | Legendaris: Sisik Naga Pasir (Tier 7) — Legendaris: Inti Pasir Purba (Tier 8) |
| Kalajengking Meratung | 🐛 Insect/Gu Swarm | 4, Menengah | 1.500 | 562 | Menghuni Lembah Angin Meratung (Whistling Canyon), cangkangnya sekeras batu pasir merah. Bergerak cepat menembus badai pasir untuk menyengat. | Umum: Cangkang Batu Pasir (Tier 3) — Jarang: Kelenjar Racun Meratung (Tier 4) |
| Kalajengking Kurma Purba | 🐛 Insect/Gu Swarm | 4, Puncak | 2.000 | 750 | Menghuni Oasis Kuno Pohon Kurma Purba, bersembunyi di bawah pasir isap untuk menyengat mangsa dengan racun dahaga. | Umum: Cangkang Kurma Emas (Tier 3) — Jarang: Sengat Racun Dahaga (Tier 4) |

---

### 🎋 Hutan Bambu Berbisik — Monsters Khusus
*(Zona khusus di Azure Mountain Range, lihat `03_AZURE_MOUNTAIN_RANGE.md`)*

| Zona | Monster | Kategori | Tier (Realm Setara) | HP | Attack Power | Kemampuan & Deskripsi | Loot Drop |
|---|---|---|---|---|---|---|---|
| **Zona Luar (0–5 li)** | Kera Bambu Abu-abu | 🐺 Spirit Beast | 2, Awal | 60 | 15 | Berkoloni 10–30 ekor, dipimpin satu jantan alfa. Agresif jika teritorinya diganggu, suka melempar ranting, buah, atau kotoran. Bergerak sangat lincah di antara batang bambu. | Umum: Bulu Kera Abu-abu (Tier 1) — Jarang: Batu Giok Kecil (Tier 2) |
| **Zona Luar (0–5 li)** | Ular Hijau Daun | 🐺 Spirit Beast | 2, Awal | 60 | 15 | Bersarang berkelompok 5–15 ekor di rumpun bambu. Bisa melompat dari cabang ke cabang. Racunnya menyebabkan mati rasa sementara (1–2 jam). | Umum: Taring Beracun (Tier 1) — Jarang: Sisik Hijau (Tier 2) |
| **Zona Tengah (5–20 li)** | Babi Hutan Bertanduk | 🐺 Spirit Beast | 4, Awal | 1.250 | 450 | Berkelompok dalam keluarga 3–8 ekor. Tanduknya tajam seperti tombak bambu, bisa menusuk zirah besi tipis. Sangat agresif jika satu anggota terancam. | Umum: Tanduk Babi Hutan (Tier 3) — Jarang: Kulit Tebal Bertuah (Tier 3) |
| **Zona Tengah (5–20 li)** | Roh Bambu | 👻 Undead | 4, Awal | 1.687 | 450 | Berwujud humanoid ramping dari bambu, bergerak tanpa suara. Menyerang dengan serangan qi tajam dari jarak dekat. Muncul berkelompok 2–5 entitas. | Umum: Serpihan Bambu Giok Kecil (Tier 3) — Jarang: Inti Roh Bambu (Tier 4) |
| **Zona Dalam (20–50+ li)** | Prajurit Bambu | 🗿 Ancient Guardian | 6, Awal | 125.000 | 16.875 | Golem bambu raksasa setinggi 5 meter, tubuhnya dari bambu giok yang tak bisa ditembus senjata biasa. Berjaga sendirian, bergiliran di beberapa posisi. Tidak menyerang pengunjung yang langsung pergi. | Legendaris: Serpihan Bambu Giok Murni (Tier 6) |
| **Zona Dalam (20–50+ li)** | Naga Bambu | 🗿 Ancient Guardian (Mitos) | 8+ (Tidak Diketahui) | ??? | ??? | Legenda — tak ada yang selamat untuk bercerita. Konon menjaga "Hati Hutan" di pusat hutan. | Tidak Diketahui |
| **Semua Zona** | Bisikan Tanpa Sumber | 👤 Bayangan/Yin | — | — | — | Efek mental — bukan monster fisik. Semakin dalam, semakin kuat efeknya. Bisa menyebabkan kebingungan, halusinasi, hilang arah, dan paranoia. | Tidak Ada |

---

### 🐉 Monster Langka Lintas Wilayah (Rare/Boss Tier)
*Bisa muncul di beberapa zona terlarang, tidak terikat satu wilayah saja.*

| Monster | Kategori | Tier (Realm Setara) | HP | Attack Power | Kemampuan & Deskripsi | Loot Drop |
|---|---|---|---|---|---|---|
| Bayangan Tanpa Wujud | 👤 Bayangan/Yin | 5, Menengah | 5.625 | 4.218 | Berkelana acak di zona-zona gelap seluruh dunia (hutan malam, reruntuhan, lembah berkabut) — tak punya habitat tetap, muncul lalu menghilang tanpa jejak begitu kehilangan lebih dari 50% HP-nya, membuatnya nyaris mustahil dikalahkan sepenuhnya. | Umum: Esens Bayangan (Tier 4) — hanya drop jika berhasil dipojokkan sampai HP 0% sekaligus (sangat sulit) |
| Naga Kabut Purba | 🗿 Ancient Guardian (Boss Langka) | 8, Awal | 1.562.500 | 421.875 | Legenda hidup yang konon menjaga rahasia Immortal Peach Island & Ancient Battlefield of Gods secara bergantian, hanya muncul saat formasi kuno terganggu serius. Pertarungan dengannya setara peristiwa besar dalam cerita, bukan encounter biasa. | Legendaris (100% sekali kill pertama): Sisik Naga Purba (Tier 8, bahan Tribulasi Realm 8→9) + Insight Point otomatis untuk semua yang terlibat pertarungan |
| Feniks Kegelapan | 🔥 Elemental (Api/Gelap) | 8, Awal | 1.562.500 | 421.875 | Legenda burung api kegelapan yang konon muncul di Southern Demon Domain setiap seribu tahun. Api hitamnya bisa membakar qi. | Legendaris: Bulu Feniks Kegelapan (Tier 8) — Legendaris: Inti Api Kegelapan (Tier 9) |
| Naga Air Purba | 🗿 Ancient Guardian | 8, Awal | 1.562.500 | 421.875 | Naga air yang menjaga kedalaman laut Timur. Sangat jarang muncul — hanya saat terjadi bencana laut besar. | Legendaris: Sisik Naga Air (Tier 8) — Legendaris: Inti Air Purba (Tier 9) |
| Kura-kura Giok Raksasa | 🗿 Ancient Guardian | 7, Awal | 390.625 | 56.250 | Kura-kura purba yang konon membawa pulau di punggungnya. Bergerak sangat lambat, tapi pertahanannya nyaris tak tertembus. | Legendaris: Cangkang Kura-kura Giok (Tier 7) — Legendaris: Inti Giok Purba (Tier 8) |
| Roh Hutan Purba | 👻 Undead | 7, Awal | 390.625 | 56.250 | Roh hutan yang menjaga keseimbangan alam. Menyerang siapa pun yang merusak hutan secara berlebihan. | Legendaris: Inti Roh Hutan (Tier 7) — Legendaris: Esens Kehidupan (Tier 8) |

📌 **\*Catatan Realm 1 (§5a):** Monster berbasis Realm 1 (Mortal Foundation, RealmBase=0 sesuai `09` §9) secara formula punya HP/Attack individual = 0. Ini bukan bug — kawanan seperti Kutu Iblis Pemakan Qi & Kawanan Camar Badai memang dirancang "tak berbahaya sendirian", ancamannya murni dari efek naratif kumulatif (gigitan berkali-kali, penyedotan Qi bertahap, gangguan penglihatan massal) yang AI GM tangani sebagai deskripsi, bukan lewat resolusi damage baku `12_COMBAT_SYSTEM.md`. Untuk encounter yang butuh damage terukur dari swarm semacam ini, AI GM boleh menaikkan Tier/Realm kawanan tersebut secara situasional (mis. kawanan sangat besar/ratu kawanan hadir) dengan validasi naratif, bukan otomatis.

---

## ⚖️ 6. Checklist Anti-Cheat Monster

- [ ] HP & Attack Power monster dihitung dari formula §2, bukan klaim sepihak?
- [ ] Kemunculan (terutama ambush) dilempar via `AmbushChance` §3 oleh AI GM, bukan diatur sepihak player?
- [ ] Monster Tier 6+ hanya muncul di habitat resminya (§5), tidak di zona tak sesuai?
- [ ] Loot hanya didapat setelah monster benar-benar dikalahkan dalam roleplay, dicatat di Item Origin Log?
- [ ] Serangan "ultimate" monster (>×1 Attack Power normal) dibatasi cooldown, tidak dipakai tiap giliran?
- [ ] Respawn monster unik/bernama dibatasi cooldown naratif wajar, tidak di-farming berulang dalam waktu singkat?

Jika salah satu poin gagal → encounter/loot DITOLAK atau dikoreksi AI GM.

---

## 🗺️ 7. Integrasi dengan Sistem Lain

- **Dengan Sistem Hukum Kultivasi** (`09_CULTIVATION_LAW_SYSTEM.md`): `MonsterQiCap` memakai tabel QiCap yang sama, dan loot monster tertentu langsung dipetakan ke Bahan Terobosan per Hukum (mis. Serigala Api Neraka → bahan Hukum Qi Naga Api, Mayat Hidup Rawa Jiwa Tenggelam → bahan Hukum Roh Hantu) sesuai §8.5 file tersebut.
- **Dengan Sistem Ekonomi** (`10_ECONOMY_SYSTEM.md`): semua loot tunduk Tier & Grade serta `FinalPrice` formula saat dijual, dan WAJIB Item Origin Log sebelum ditransaksikan.
- **Dengan Sistem HP** (`11_VITALITY_HUNGER_SYSTEM.md`): HP monster & player dihitung dari formula yang sama (basis QiCap), sehingga pertarungan tetap seimbang dan bisa diprediksi tanpa power creep sepihak dari kedua sisi.
- **Dengan Sistem Pertempuran** (`12_COMBAT_SYSTEM.md`): MonsterAttackPower & MonsterHP langsung dipakai tanpa konversi tambahan — monster dan kultivator bertarung dengan sistem identik.
- **Dengan modul regional** (`01`–`07`): tiap monster terkunci ke habitat spesifik yang sudah ditetapkan (Void Mist Forest, Hellfire Island, Rawa Jiwa Tenggelam, dsb) — mencegah monster tingkat tinggi muncul di zona yang seharusnya aman seperti Kota Fengyang atau Floating Cloud Archipelago (pasar netral).

---

## 📊 8. Ringkasan Jumlah Monster per Wilayah

| Wilayah | Jumlah Monster | Monster Tier Tertinggi |
|:---|:---|:---|
| Central Plains | 10 | Tier 5 (Naga Lumpur) |
| Azure Mountain Range | 13 | Tier 8+ (Naga Bambu — Mitos) |
| Southern Demon Domain | 11 | Tier 6 (Siluman Bayangan Malam) |
| Eastern Sea Region | 11 | Tier 8 (Paus Iblis, Naga Air Purba) |
| Northern Desolate Territory | 12 | Tier 8 (Naga Es Purba) |
| Western Sacred Deserts | 11 | Tier 8 (Naga Pasir, Phoenix Api Gurun) |
| Hutan Bambu Berbisik (Khusus) | 7 | Tier 8+ (Naga Bambu — Mitos) |
| Lintas Wilayah (Boss Langka) | 5 | Tier 8 (Naga Kabut Purba, Feniks Kegelapan, Naga Air Purba) |

---

## 🎯 9. Panduan Penggunaan untuk AI GM

### 9.1 Memilih Monster yang Tepat

1. **Tentukan wilayah** tempat pemain berada (Central Plains, Azure Mountain, dsb.)
2. **Pilih monster** dari daftar wilayah tersebut yang sesuai dengan:
   - **Tingkat bahaya** yang ingin diberikan (sesuai tier)
   - **Kondisi naratif** (siang/malam, cuaca, lokasi spesifik)
   - **Kekuatan pemain** (jangan berikan Tier 6 ke pemain Realm 3)
3. **Gunakan tabel AmbushChance** (§3) untuk menentukan apakah monster muncul.

### 9.2 Menjalankan Pertarungan

1. **Gunakan formula** dari `12_COMBAT_SYSTEM.md` untuk resolusi pertarungan.
2. **Monster Attack Power & HP** sudah dihitung di tabel §5 — pakai langsung.
3. **Serangan Ultimate:** Boleh menggunakan ×3 Attack Power sekali per pertarungan (cooldown 5+ giliran).
4. **Jika pemain melarikan diri:** Gunakan aturan escape di `12_COMBAT_SYSTEM.md`.

### 9.3 Menentukan Loot

1. **Setelah monster dikalahkan**, lempar `BaseDropRate` (§4).
2. **Tentukan rarity** yang berhasil didapat.
3. **Catat Item Origin Log** (`10_ECONOMY_SYSTEM.md` §7) sebelum item dijual/dipakai.

### 9.4 Contoh Skenario

**Skenario:** Pemain (Realm 3, Foundation Establishment) memasuki Hutan Bambu Berbisik di malam hari.

1. AI GM menentukan zona: Zona Luar (0–5 li).
2. Melempar AmbushChance: `5% × 1,0 (zona normal) × 2,0 (malam) = 10%` per jam.
3. Hasil: 10% berhasil → muncul Kera Bambu Abu-abu (koloni 10 ekor).
4. Pertarungan: Gunakan Attack Power 15 per ekor → total 150 Attack Power jika semua menyerang bersama.
5. Pemain berhasil mengalahkan 5 ekor, sisanya kabur.
6. Loot: Lempar BaseDropRate → dapat Bulu Kera Abu-abu (Tier 1) ×5.
7. Catat Item Origin Log.

---

> **Catatan Admin:** Bestiarium ini adalah dokumen hidup — monster baru bisa ditambahkan kapan saja di `42_CUSTOM_TECHNIQUES.md` atau langsung di file ini sebagai monster custom. Pastikan semua statistik mengikuti formula §2 dan habitatnya sesuai §5.
