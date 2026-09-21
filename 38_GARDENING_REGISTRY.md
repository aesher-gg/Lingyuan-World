# Lingyuan World — Gardening Registry

> Modul pendamping: 38 — Gardening System
> Status: Canonical Registry Boundary
> Prinsip: hanya data yang dapat ditelusuri ke lore/repo; field yang belum diketahui tetap ??? atau UNRESOLVED.

## 1. Registry Rules

Registry ini bukan tempat menciptakan spesies baru. Record hanya boleh berasal dari lore regional, faction/sect lore, Bestiary, atau official player state.

Field kosong tidak berarti tidak ada di dunia. Jika belum ada bukti canon, gunakan ???.

Plant Category, Nature, Tier, Grade, Quality, Condition, dan Object Type tidak boleh digabung.

## 2. Current Known Plant / Planting Material Records

| Record | Object Type | Nature / Category | Source | Cultivable | Growth Duration | Propagation | Harvest | Status |
|---|---|---|---|---|---|---|---|---|
| Semak Duri Miasma | Plant Instance | Demonic/??? | players/Azmud.md | ??? | ??? | Stek/kloning tercatat pada save; detail method ??? | ??? | Official player state |
| Rumput Darah [Mutasi Demonic] | Plant Instance | Demonic | players/Azmud.md | YES dalam state Azmud | ??? | Polong biji hitam tercatat sebagai bibit mutasi | ??? | Official player state |
| Benih Rumput Darah [Normal] | Planting Material | Normal/??? | players/Azmud.md | ??? | ??? | ??? | ??? | 2 instance dalam save |
| Benih Teh Fana [Tianzhou] | Planting Material | ??? | players/Azmud.md | ??? | ??? | ??? | ??? | 1 instance dalam save |
| Benih Akar Penenang [Tier-1] | Planting Material | ??? | players/Azmud.md | ??? | ??? | ??? | ??? | 3 instances; Tier-1 bukan Grade |

## 3. Regional Lore References

| Region / Location | Known Lore | Gardening Rule |
|---|---|---|
| Tianzhou — Lembah Xuewu | Herba spiritual pemurni darah | Compatibility/output tetap harus diverifikasi dari plant-specific canon |
| Qingyun — Hutan Lingzhu | Flora terkait lore lokasi | Tidak semua flora otomatis cultivable |
| Qingyun — Jurang Hanxu | Flora terkait lore lokasi | Sifat/output mengikuti lore yang tersedia |
| Moyuan — Pegunungan Huijin | Tanah subur tetapi beracun; tanaman demonic tumbuh | Environmental compatibility wajib diperiksa |
| Beiyuan / fasilitas sekte | Kebun herbal pada fasilitas tertentu | Produksi tidak otomatis menjadi market supply |

## 4. Known Garden Facilities

| Garden | Owner/Operator | Location | Known Function | Plant Registry | Production State |
|---|---|---|---|---|---|
| Kebun Obat Kekayaan | Sekte Xuanyuan | Tianzhou | Kebun ramuan langka | ??? | ??? |
| Kebun aprikot | Perguruan Luohua | Tianzhou | Kebun aprikot; dipelihara bersama | ??? | ??? |
| Kebun Herbal Tinggi | Biara Jinguang | Qingyun | Kebun swasembada dan latihan kesabaran | ??? | ??? |
| Kebun Obat Luas | Balai Yunyao | Beiyuan | Sumber bahan mentah utama | ??? | ??? |
| Kebun Rahasia Azmud | Azmud | Celah Bukit / Desa Yemo, Moyuan | Official player garden state | See §2 | Runtime mengikuti save/checkpoint |

## 5. Plant Creature Boundary

Plant Creature dari Bestiary bukan Cultivable Plant secara otomatis.

Contoh Bestiary memiliki flora/creature seperti Iblis Pohon Tulang Merah dan Monster Akar Purba Raksasa. Loot creature hanya menjadi planting material bila canon secara eksplisit mendukung fungsi tersebut.

## 6. Growth Registry Boundary

System caps:
- Ordinary Plant ≤ 7 hari.
- Spiritual Plant ≤ 15 hari.

Caps bukan durasi species.

Jika species-specific duration belum tersedia:
- Growth Duration = ???
- Growth resolution = UNRESOLVED bila duration dibutuhkan.

Tidak boleh mengisi duration berdasarkan Tier, Grade, rarity, price, realm, atau lokasi tanpa canon.

## 7. Environment Registry Boundary

Environment checks dapat memakai:
- region;
- location;
- soil;
- water;
- Qi Density;
- toxic/death/demonic conditions;
- event;
hanya jika hubungan tersebut didukung canon.

Qi Density tidak memberi bonus gardening universal.

## 8. Propagation Registry Boundary

Propagation harus plant-specific.

Tidak ada aturan:
- harvest → automatic seed;
- plant → automatic cloning;
- output → automatic planting material.

Setiap propagation membutuhkan source dan canon method.

## 9. Output / Processing Boundary

Output Instance harus mempertahankan:
Plant Instance → Harvest Event → Output Instance → Origin.

Alchemy/crafting hanya dapat berjalan bila recipe/formula dan material requirement canon tersedia.

Economy hanya menerima output yang benar-benar digunakan/ditawarkan sesuai aturan economy; harvest tidak otomatis masuk pasar.

## 10. Shared Runtime Boundary

Garden state lintas player/chat wajib memakai authoritative shared runtime atau verified checkpoint.

Minimum:
Garden ID, Owner, Access Policy, Location, Plant Instance IDs, World-Time Marker, active events, outputs, external effects, last verified checkpoint.

Jika state lintas-chat tidak dapat diverifikasi:
UNRESOLVED.

## 11. Checkpoint Boundary

Checkpoint bukan narasi bebas.

Minimum chain:
Garden → Plant Instance → World Time → Environment → Maintenance → Growth → Harvest → Output → Propagation/Post-Harvest → Processing → Economy/Usage → History.

Unknown tetap ???.

## 12. Official Save Boundary

Runtime State → Checkpoint → Admin Verification → Official Player Save.

Qwen tidak menulis official save langsung.

## 13. Audit Status

Registry ini sengaja mempertahankan unknown fields. Tidak ada species, growth duration, yield, recipe, price, stamina number, propagation rule, atau environmental bonus baru yang diciptakan oleh registry.
