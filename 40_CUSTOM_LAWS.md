# 📜 Lingyuan World — Hukum Kultivasi Kustom (Custom Cultivation Laws)

> **Modul:** 40 — Custom Cultivation Laws
> **Fungsi:** Tempat Admin dan Pemain mencatat Hukum Kultivasi Kustom baru yang telah disetujui untuk digunakan di dunia.
> **Pengelolaan:** Dikelola oleh Admin. AI GM wajib memeriksa file ini jika pemain mengklaim mempelajari Hukum di luar 5 Hukum Standar di `09_CULTIVATION_LAW_SYSTEM.md`.
> **Rujukan silang:** `09_CULTIVATION_LAW_SYSTEM.md` (formula dasar Qi, HP, Attack, Defense), `00_CORE_RULES_AI_GM.md` (§1.11)

---

## 📋 Aturan Pembuatan Hukum Kustom

1. **Format Wajib:** Setiap Hukum Kustom harus mencantumkan Modifikator HP, Modifikator Attack, Modifikator Defense, Elemen Utama, Keunggulan Khusus, dan Kelemahan/Risiko Qi Deviation.
2. **Keseimbangan Mekanik:** Modifikator total tidak boleh melebihi batas rata-rata $1.0$. Jika Attack tinggi (misal $1.5$), HP atau Defense harus lebih rendah (misal $0.8$).
3. **Law Origin Requirement:** Penguasaan Hukum Kustom wajib mencantumkan Law Origin (Guru / Manual Kuno / Pencerahan Mandiri).

---

## 📜 DAFTAR HUKUM KULTIVASI KUSTOM RESMI

### LAW-CUST-001: Hukum Api Purba Vermilion (Vermilion Ancient Flame Law)
- **Nama Hukum:** Hukum Api Purba Vermilion (*Vermilion Flame Law*)
- **Kategori:** Demonic / Offense Aggressive
- **Elemen Utama:** Api / Yang Murni
- **Pencipta / Asal-Usul:** Manuskrip Reruntuhan Gunung Yanmo (`21_ISTANA_YANMO.md`)
- **Modifikator Statistik:**
  - **LawHPMultiplier:** $0,9$ (Tubuh sedikit lebih rapuh karena panas api)
  - **LawAttackMultiplier:** $1,4$ (Serangan api sangat membakar & destruktif)
  - **LawDefenseMultiplier:** $0,8$ (Minim pertahanan pasif)
- **Keunggulan Khusus:**
  - *Burn Effect:* Setiap serangan fisik/Qi memberikan efek luka bakar bertahap ($10\%$ dari Attack Power selama 2 giliran combat).
  - *Flame Immunity:* Kebal terhadap serangan atribut es/dingin Tier 1–2.
- **Kelemahan & Risiko:**
  - Risiko Qi Deviation +15% saat terdesak.
  - Sangat rawan terhadap serangan atribut Air Purba (-20% Defense vs Air).

---

### LAW-CUST-002: Hukum Bayangan Ilusi Wuying (Wuying Phantom Shadow Law)
- **Nama Hukum:** Hukum Bayangan Ilusi Wuying (*Phantom Shadow Law*)
- **Kategori:** Unortodoks / Stealth & Speed
- **Elemen Utama:** Kegelapan / Angin
- **Pencipta / Asal-Usul:** Didirikan oleh Pendiri Perkumpulan Wuying (`33_PERKUMPULAN_WUYING.md`)
- **Modifikator Statistik:**
  - **LawHPMultiplier:** $0,85$
  - **LawAttackMultiplier:** $1,1$
  - **LawDefenseMultiplier:** $0,9$
- **Keunggulan Khusus:**
  - *Shadow Evasion:* +15% Chance menghindar dari serangan jarak jauh (`12_COMBAT_SYSTEM.md`).
  - *Silent Movement:* Tidak menghasilkan suara saat bergerak di malam hari / tempat gelap.
- **Kelemahan & Risiko:**
  - Kerusakan dari Qi Atribut Cahaya/Suci (Buddhis) meningkat +25%.

---

### LAW-CUST-003: Hukum Hati Nirwana Welas Asih (Nirvana Compassion Law)
- **Nama Hukum:** Hukum Hati Nirwana Welas Asih (*Nirvana Heart Law*)
- **Kategori:** Ortodoks Buddhis / Defense & Healing
- **Elemen Utama:** Cahaya / Tanah
- **Pencipta / Asal-Usul:** Turunan Ajaran Kuil Ciyun (`31_KUIL_CIYUN.md`)
- **Modifikator Statistik:**
  - **LawHPMultiplier:** $1,3$ (Daya tahan fisik sangat tinggi)
  - **LawAttackMultiplier:** $0,7$ (Serangan bersifat melumpuhkan, bukan membunuh)
  - **LawDefenseMultiplier:** $1,3$ (Pertahanan pasif sangat kokoh)
- **Keunggulan Khusus:**
  - *Rapid Qi Recovery:* Pemulihan Qi alami bertambah +30% saat bermeditasi.
  - *Purification:* Dapat membuang 5 Poin Dan-Du/Racun per hari tanpa pil (`43_ALCHEMY_PILL_SYSTEM.md`).
- **Kelemahan & Risiko:**
  - Mengurangi Sin/Merit Penalty saat membunuh musuh (Karma Sin bertambah 2× lipat jika membunuh musuh menyerah).
