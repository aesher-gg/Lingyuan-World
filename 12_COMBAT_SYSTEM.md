# ⚔️ Wuxian World — Sistem Pertempuran (Battle & Combat Rules)

> **Modul:** 12 — Combat System
> **Prinsip:** Anti-Cheat Enforced — Strict Turn-Based — Terintegrasi dengan Sistem Hukum Kultivasi, HP, dan Bestiarium
> **Rujukan silang:** `09_CULTIVATION_LAW_SYSTEM.md` (QiCap basis Attack/Defense), `11_VITALITY_HUNGER_SYSTEM.md` (FinalDamage mengurangi HP), `13_BESTIARY.md` (monster pakai sistem identik)

---

## 0. Filosofi Sistem

Pertarungan di jianghu harus terasa berbahaya dan adil bagi **SEMUA** pihak — player, NPC, maupun monster. Prinsip paling dasar: setiap pihak yang terlibat pertarungan punya hak giliran yang sama, dan tidak ada pihak yang bisa "menyerang terus-menerus" sementara pihak lain dipaksa diam.

### Aturan Emas Anti-Cheat Pertempuran
- Giliran bersifat **WAJIB bergantian** — setelah 1 karakter bertindak, giliran otomatis pindah ke pihak berikutnya sesuai urutan Initiative. Tidak ada pengecualian.
- Player **TIDAK PERNAH** menentukan hasil aksi musuh — hanya AI GM yang memutuskan hasil aksi siapa pun selain aksi milik karakter player sendiri.
- Satu giliran = maksimal **1 Aksi Utama + 1 Aksi Kecil** — tidak bisa dipadatkan jadi "menyerang 10 kali sekaligus" lewat deskripsi naratif.
- NPC/monster **WAJIB bertindak sesuai Karakteristik & Sifat** yang sudah ditetapkan — tidak bisa "dilupakan" atau "dibuat pasif" oleh player tanpa alasan mekanik sah.
- Semua damage, Qi yang terpakai, dan hasil giliran dicatat di combat log bertimestamp — tidak bisa diedit mundur.

---

## 1. Struktur Giliran (Initiative & Turn Order)

### 1.1 Formula Initiative

```
InitiativeScore = (RealmIndex × 100 + StageBonus) + Random(1–20)
```

RealmIndex = 1–9 (sesuai Major Realm) | StageBonus: Awal=0, Menengah=10, Puncak=20 | Random(1–20) = lemparan dadu AI GM (bukan klaim player).

Semua karakter yang terlibat (player, sekutu, NPC musuh, monster) dihitung Initiative-nya di awal setiap Ronde Pertempuran, lalu bertindak berurutan dari skor tertinggi ke terendah.

### 1.2 Struktur Ronde

Ronde Pertempuran = 1 putaran penuh di mana **SETIAP** karakter yang terlibat mendapat tepat 1 giliran, sesuai urutan Initiative. Initiative dilempar **ULANG** tiap ronde baru (mencegah satu pihak "selalu menang giliran" selamanya). Urutan dalam 1 ronde yang sudah ditetapkan **TIDAK BISA** diubah di tengah ronde oleh klaim player.

📌 Anti-cheat: jika player mencoba bertindak di luar gilirannya, AI GM WAJIB menolak dan mengembalikan ke urutan yang benar.

---

## 2. Ekonomi Aksi (Action Economy) — Inti Anti-Spam

Setiap giliran, **SETIAP** karakter (player maupun NPC/monster) hanya mendapat:

**1 Aksi Utama (Main Action)** — pilih salah satu:
- Serang — memakai satu teknik/jurus dari Law Origin Log yang sah, lewat Equipment yang sedang terpakai (lihat `00_CORE_RULES_AI_GM.md` §2)
- Bertahan — meningkatkan pertahanan giliran ini
- Gunakan Item — mengonsumsi/mengaktifkan pil, ramuan, atau item habis pakai dari inventory tervalidasi
- Kabur — mencoba melarikan diri dari pertarungan
- Bantu Sekutu — memberi buff/dukungan kecil pada sekutu

**1 Aksi Kecil (Minor Action)** — pilih salah satu:
- Reposisi kecil (pindah jarak dekat)
- Bicara singkat (satu kalimat, tidak mengonsumsi Qi)
- Minum pil kecil pemulih ringan
- Pasang/lepas/ganti 1 Equipment (senjata, zirah, atau aksesoris) — pindah satu item antara Inventory dan slot Equipment; tidak bisa gratis/instan tanpa menghabiskan Aksi Kecil ini

📌 Anti-cheat: "menyerang berkali-kali dalam satu giliran" via deskripsi naratif panjang **TETAP dihitung sebagai 1 Aksi Utama dengan 1 kali resolusi damage** — deskripsi boleh dramatis, mekanik tetap satu kali perhitungan.

---

## 3. Formula Damage (Serangan)

### 3.1 Attack Power Karakter (Player & NPC Kultivator)

```
AttackPower(realm, stage, law) = QiCap(realm, stage) × 0,15 × LawAttackMultiplier(law)
```

| Hukum | LawAttackMultiplier | LawHPMultiplier (pengingat) |
|---|---|---|
| Hukum Raga Sejati | ×0,8 | ×1,5 (tanky, ofensif lebih rendah) |
| Hukum Dao Abadi | ×1,0 | ×1,0 (baseline) |
| Hukum Qi Naga Api | ×1,3 | ×0,9 (ofensif tinggi, rapuh) |
| Hukum Gu Karma | ×1,4 | ×0,7 (paling ofensif, paling rapuh) |
| Hukum Bayangan Darah | ×1,2 (×1,35 saat Kontrak Aktif) | ×0,85 (×1,0 saat Kontrak Aktif) |
| Hukum Roh Hantu | ×1,1 | ×0,75 |
| 🆕 Hukum Pisau Sunyi | ×1,25 (+10% HitChance saat kontrak resmi aktif, lihat `33_PERKUMPULAN_PISAU_SUNYI.md`) | ×0,8 |

### 3.2 Resolusi Damage

```
RawDamage = AttackPower(penyerang) × TechniqueTierBonus × HitConfirmed
```

TechniqueTierBonus: Serangan biasa ×1,0 | Teknik Andalan/Signature ×1,5 | Jurus Ultimate (cooldown) ×3,0. HitConfirmed: hasil lemparan HitChance oleh AI GM — 1 jika kena, 0 jika meleset.

```
FinalDamage = max(0, RawDamage − TotalDefense(bertahan))
```

### 3.3 Peluang Kena (Hit Chance)

```
HitChance = clamp(70% + (RealmIndex_penyerang − RealmIndex_bertahan) × 5%, 10%, 95%)
```

Dilempar AI GM setiap kali Aksi "Serang" dipakai — bukan otomatis kena, bahkan dari kultivator kuat sekalipun.

### 3.4 Cooldown Jurus Ultimate

Teknik Andalan/Signature (×1,5): boleh dipakai tiap giliran selama Qi cukup. Jurus Ultimate (×3,0): cooldown **WAJIB 3 ronde** setelah dipakai, dicatat AI GM, tidak bisa dipakai lagi sebelum cooldown habis meski Qi mencukupi.

---

## 4. Formula Pertahanan (Defense)

```
PassiveDefense(realm, stage) = QiCap(realm, stage) × 0,05
```
(selalu aktif, berlaku otomatis tanpa perlu memilih aksi apa pun)

```
ActiveDefenseBonus = QiCap(realm, stage) × 0,10
```
(hanya aktif jika Aksi Utama giliran ini adalah "Bertahan" — karakter yang memilih "Serang" TIDAK mendapat bonus ini)

```
TotalDefense = PassiveDefense + (ActiveDefenseBonus jika memilih Bertahan, 0 jika tidak)
```

---

## 5. Biaya Qi per Aksi (Anti-Spam Teknik)

| Jenis Aksi | Biaya Qi |
|---|---|
| Serangan Biasa | QiCap × 5% |
| Teknik Andalan | QiCap × 12% |
| Jurus Ultimate | QiCap × 25% |

Qi tersisa dilacak AI GM tiap pertarungan. Jika Qi karakter habis (0), ia hanya bisa melakukan **Pukulan Kosong (Mortal Strike)**:
```
MortalStrikeDamage = AttackPower × 0,3 (tanpa TechniqueTierBonus, HitChance turun 15%)
```

📌 Ini mencegah player "menyerang tanpa henti dengan kekuatan penuh selamanya" — Qi adalah sumber daya terbatas per pertarungan, harus dikelola.

---

## 6. Kabur dari Pertarungan (Escape)

```
EscapeChance = clamp(50% + (RealmIndex_kabur − RealmIndex_pengejar) × 5%, 10%, 90%)
```

Dilempar AI GM saat Aksi "Kabur" dipilih. Jika **GAGAL**, pihak lawan mendapat **Aksi Kesempatan (Opportunity Attack)** gratis — satu serangan tambahan di luar giliran normalnya.

---

## 7. Pertempuran Kelompok (Multi-Combatant)

- Semua karakter yang terlibat — player, sekutu, banyak musuh sekaligus — masuk dalam **SATU** urutan Initiative bersama, bukan giliran terpisah per tim.
- Jika player dikeroyok banyak musuh, **SETIAP** musuh tetap mendapat giliran independennya sendiri sesuai Initiative masing-masing.
- AI GM menentukan perilaku tiap NPC/monster berdasarkan Karakteristik & Sifat yang sudah ditetapkan sebelumnya (NPC "pemarah" akan memilih Aksi Serang; NPC "sangat sabar" akan memilih Bertahan di giliran awal).

---

## 8. Checklist Anti-Cheat Pertempuran (Wajib Dicek AI GM)

- [ ] Urutan Initiative sudah dilempar & ditetapkan di awal ronde, tidak diubah sepihak di tengah ronde?
- [ ] Setiap karakter (termasuk NPC/monster) benar-benar mendapat gilirannya, tidak ada yang "dilewati" tanpa alasan mekanik sah?
- [ ] Player hanya melakukan 1 Aksi Utama + 1 Aksi Kecil per giliran, tidak lebih meski dinarasikan panjang?
- [ ] Player tidak menentukan sendiri hasil aksi pihak lain (hit/miss, damage, reaksi NPC)?
- [ ] Damage dihitung dari formula, bukan klaim sepihak angka damage oleh player?
- [ ] HitChance & EscapeChance dilempar AI GM tiap kali dipakai, bukan otomatis berhasil?
- [ ] Qi yang terpakai dicatat & dikurangi sesuai §5?
- [ ] Cooldown Jurus Ultimate (3 ronde) benar-benar ditegakkan?
- [ ] NPC/monster bertindak sesuai Karakteristik & Sifat yang sudah tercatat?
- [ ] Combat log bertimestamp, tidak diedit mundur?

Jika salah satu poin gagal → giliran/aksi terkait DITOLAK, AI GM mengulang dengan mekanik yang benar.

---

## 9. Integrasi dengan Sistem Lain

- **Dengan Sistem HP** (`11_VITALITY_HUNGER_SYSTEM.md`): `FinalDamage` langsung mengurangi `HP(realm, stage, law)` — status kondisi diperbarui otomatis tiap kali HP berubah.
- **Dengan Sistem Hukum Kultivasi** (`09_CULTIVATION_LAW_SYSTEM.md`): AttackPower & Defense memakai QiCap yang sama, Teknik Andalan harus sesuai Law Origin Log karakter.
- **Dengan Bestiarium** (`13_BESTIARY.md`): MonsterAttackPower & MonsterHP langsung dipakai tanpa konversi tambahan — monster dan kultivator bertarung dengan sistem identik.
- **Dengan Sistem Ekonomi** (`10_ECONOMY_SYSTEM.md`): item/pil yang dipakai lewat Aksi "Gunakan Item" harus tervalidasi Item Origin Log.
