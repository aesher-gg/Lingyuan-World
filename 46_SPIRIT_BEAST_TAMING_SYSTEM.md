# 🐾 Lingyuan World — Sistem Penjinakan & Pemeliharaan Beast (Spirit Beast Taming System)

> **Modul:** 46 — Spirit Beast Taming System
> **Status:** Canonical System
> **Prinsip:** Source-Traceable — Time-Bound — Anti-Cheat — Hardcore Realism
> **Rujukan silang:** `00_CORE_RULES_AI_GM.md` (aturan inti, batas waktu, timed processing §1.10), `09_CULTIVATION_LAW_SYSTEM.md` (Realm & Qi), `11_VITALITY_HUNGER_SYSTEM.md` (Stamina, Satiety beast), `12_COMBAT_SYSTEM.md` (partner tempur & giliran), `13_BESTIARY.md` (data monster, habitat & sifat beast), `players/` (official save dikelola Admin)

---

## 0. Filosofi Sistem Penjinakan Beast

Di Lingyuan World, monster dan binatang spiritual (*Spirit Beasts / Demon Beasts*) bukan sekadar mangsa untuk diburu (`13_BESTIARY.md`). Kultivator yang memiliki pemahaman Dao Hewan atau kemauan jiwa yang kuat dapat menjinakkan mereka menjadi **Tumpangan (Mounts)**, **Penjaga Wilayah**, atau **Rekan Tempur Setia (Combat Companions)**.

Penjinakan bukanlah proses instan; beast memiliki naluri liar, kebanggaan, dan kekuatan fisik yang dapat melukai penjinaknya jika gagal.

---

## 1. Klasifikasi Beast yang Dapat Dijinakkan

Tidak semua makhluk hidup dapat dijinakkan. Klasifikasi beast mengikuti ketentuan `13_BESTIARY.md`:

| Klasifikasi Beast | Potensi Penjinakan | Metode Utama Penjinakan | Sikap Alami terhadap Manusia |
|---|---|---|---|
| **Ordinary Beast (Binatang Biasa)** | Sangat Mudah | Makanan, Pelatihan Fisik, Kandang | Penakut / Liar |
| **Spirit Beast (Binatang Spirit)** | Sedang – Sulit | Kontrak Jiwa, Ujian Kekuatan, Makanan Spirit | Netral / Waspada |
| **Demon Beast (Binatang Demonic)** | Sangat Sulit – Berbahaya | Penundukan Paksa Jiwa, Kontrak Darah | Agresif / Hostile |
| **Venerable / Ancient Beast King** | Hampir Mustahil | Pengakuan Kesetaraan Jiwa, Bantuan Besar | Sangat Bangga / Mematikan |

---

## 2. Metode Penjinakan (Taming Methods)

Terdapat 3 jalur utama untuk menjinakkan Spirit Beast:

### 2.1 Jalur Ikatan Kesetaraan (Equality Soul Contract / Ling-Hun Qi-Yue)
- **Prinsip:** Penjinak dan Beast membentuk ikatan jiwa sebagai mitra yang sederajat. Tidak ada yang mendominasi.
- **Syarat:** Beast harus diselamatkan, diberi makanan favoritnya secara konsisten, atau dibujuk secara sukarela melalui roleplay.
- **Bonus:** Keharmonisan bertarung sangat tinggi (+15% Initiative Roll saat combat bersama), Beast tidak akan pernah mengkhianati penjinak kecuali disiksa.

### 2.2 Jalur Penundukan Paksa (Master-Servant Contract / Zhu-Nu Qi-Yue)
- **Prinsip:** Penjinak menundukkan Jiwa/Kesadaran Beast secara paksa menggunakan Qi dan Niat Pembunuh (*Kill Intent*).
- **Syarat:** Karakter harus mengalahkan Beast sampai HP-nya < 20% dalam combat (`12_COMBAT_SYSTEM.md`), lalu melakukan *Willpower / Spirit Check* vs *Beast Willpower*.
- **Risiko:** Jika kesetiaan (Loyalty) Beast turun ke 0%, Beast akan menyerang balik pemiliknya secara tiba-tiba (*Backfire Attack*) atau melarikan diri.

### 2.3 Jalur Pembesaran Sejak Telur / Bayi (Egg Hatching & Cub Rearing)
- **Prinsip:** Menetas dari telur atau dibesarkan sejak induknya mati.
- **Bonus:** Kesetiaan (Loyalty) otomatis 100% (Murni / Max), Beast menganggap penjinak sebagai induknya.

---

## 3. Formula Kalkulasi Penjinakan (Taming Check)

Saat menundukkan Beast liar, AI GM menghitung peluang sukses penjinakan:

$$\text{TamingSuccessRate} = 40\% + (\text{TamerRealmIndex} - \text{BeastTier}) \times 15\% + \text{LoyaltyBonus} + \text{FoodOrItemBonus} - \text{BeastWildness}$$

- **TamerRealmIndex:** Index Realm Penjinak (1: Mortal, 2: Qi Refining, 3: Foundation Est., dst.).
- **BeastTier:** Tier Beast dari `13_BESTIARY.md` (Tier 1 s/d Tier 4).
- **BeastWildness:**
  - Ordinary Beast: 0%
  - Spirit Beast: 15%
  - Demon Beast: 30%
  - Ancient Beast: 50%
- **Gagal Check:** Beast mengamuk (*Rage Mode*), mendapatkan +20% Attack Power dan langsung menyerang penjinak.

---

## 4. Parameter Status Spirit Beast Terjinak

Setiap Beast yang berhasil dijinakkan dicatat dalam **Profil Karakter** di bagian *Spirit Beast Companion*:

```markdown
┌───────────────────── Spirit Beast Companion ─────────────────────┐
Nama Beast: [Nama Panggilan]
Spesies / Tier: [Nama Spesies dari Bestiary] | Tier [1-4]
Realm Beast: [Equivalent Realm, misal: Qi Refining Puncak]
HP: [Current] / [Max] | Qi: [Current] / [Max]
Loyalty (Kesetiaan): [0 - 100]%
Satiety (Kenyang): [0 - 100]%
Status / Kondisi: [Sehat / Terluka / Mengamuk / Tidur Bertapa]
Peran: [Rekan Tempur / Tumpangan / Penjaga Markas]
Kemampuan Khusus: [Skill 1], [Skill 2]
└─────────────────────────────────────────────────────────────────┘
```

### 4.1 Mekanik Loyalty (Kesetiaan)
- **Loyalty 80–100%:** Sangat Setia. Mengorbankan nyawa untuk melindungi pemilik, bonus damage +10%.
- **Loyalty 40–79%:** Setia Standar. Mematuhi perintah bertarung dasar.
- **Loyalty 10–39%:** Ragu / Takut. Berisiko kabur jika HP Beast < 25% saat combat.
- **Loyalty < 10%:** Berbahaya! Beast menolak perintah, berpotensi menyerang pemilik saat terluka.

*Meningkatkan Loyalty:* Memberi makan daging/herba spirit berkualitas (`38_GARDENING_SYSTEM.md`), menyembuhkan lukanya, atau bertarung bersama.

---

## 5. Perkembangan Kultivasi Beast (Beast Advancement)

Spirit Beast dapat naik tingkat (*Advancement / Breakthrough*) jika diberi nutrisi yang sesuai:

1. **Konsumsi Inti Monster (Monster Cores):** Memakan Inti Monster dari elemen yang selaras memberi Exp Kultivasi pada Beast.
2. **Pil Khusus Beast (Beast Nurturing Pills):** Pil khusus buatan Alkemia (`43_ALCHEMY_PILL_SYSTEM.md`).
3. **Evolusi Spesies (Bloodline Awakening):** Pada titik puncak Tier, Beast dapat mengalami Tribulasi Darah (*Bloodline Tribulation*) untuk bertransformasi menjadi spesies yang lebih kuat (misal: Serigala Es ➔ Serigala Es Bintang Purba).

---

## 6. Peran Beast dalam Pertempuran (Combat Integration)

Sesuai `12_COMBAT_SYSTEM.md`:
- **Giliran Bertindak:** Beast bertindak pada giliran yang sama dengan pemiliknya atau menggunakan Initiative Roll tersendiri.
- **Peran Tumpangan (Mount):** Memberikan bonus Kecepatan Gerak / Escape Rate (+20% Chance melarikan diri dari pertarungan).
- **Peran Rekan Tempur (Combat Companion):** Menyerang target yang sama dengan pemiliknya (*Combo Attack*) atau menahan serangan musuh (*Tanking*).

---

## 7. Status Modul

**CANONICAL — SYSTEM MODULE**
Seluruh aturan penjinakan, ikatan jiwa, tingkat kesetiaan, dan kemajuan kultivasi beast di atas adalah aturan resmi Lingyuan World.
