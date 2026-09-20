# Lingyuan World — Runtime Name Overlay

> **Status:** Runtime identity overlay — ACTIVE
> **Canon:** Repository module names remain the canonical identifiers.
> **Purpose:** Menyediakan nama runtime baru yang dipakai AI GM saat roleplay tanpa mengubah isi modul canon.
>
> **Scope perubahan saat ini:** 6 wilayah + 24 organisasi. Nama lokasi/NPC lain belum diubah oleh commit ini.

## 1. World

| Canon | Runtime |
|---|---|
| Wuxian World | Lingyuan World |

## 2. Regions

| Canon | Runtime |
|---|---|
| Central Plains | Tianzhou |
| Azure Mountain Range | Qingyun |
| Southern Demon Domain | Moyuan |
| Eastern Sea Region | Haiyuan |
| Northern Desolate Territory | Beiyuan |
| Western Sacred Deserts | Xisha |

## 3. Organizations

### Tianzhou

| Canon | Runtime |
|---|---|
| Heavenly Sword Pavilion | Sekte Tianjian |
| Profound Heaven Sect | Sekte Xuanyuan |
| Silver Rain Sword School | Sekte Yunjian |
| Dojo Bunga Aprikot | Perguruan Luohua |
| Dojo Godam Besi | Perguruan Tielu |

### Qingyun

| Canon | Runtime |
|---|---|
| Golden Bell Monastery | Biara Jinguang |
| Dojo Pahat Naga | Perguruan Shilong |

### Moyuan

| Canon | Runtime |
|---|---|
| Demonic Flame Palace | Istana Yanmo |
| Nine Serpent Den | Sarang Jiuyin |
| Seven Sins Cult | Kultus Qisha |
| Blood Shadow Alliance | Aliansi Anying |
| Dojo Bayangan Kelam | Perguruan Heiying |

### Haiyuan

| Canon | Runtime |
|---|---|
| Jade Purity Palace | Istana Qinglian |
| Dojo Ombak Tenang | Perguruan Haizhen |

### Beiyuan

| Canon | Runtime |
|---|---|
| Whitecloud Medicine Hall | Balai Yunyao |
| Ghost Valley Sect | Sekte Hunming |
| Dojo Cakar Serigala | Perguruan Langxue |

### Xisha

| Canon | Runtime |
|---|---|
| Azure Cloud Temple | Kuil Ciyun |
| Dojo Mata Elang Pasir | Perguruan Shaying |

### Cross-region

| Canon | Runtime |
|---|---|
| Perkumpulan Pisau Sunyi | Perkumpulan Wuying |
| Kelompok Racun Bayangan | Kelompok Yandu |
| Serambi Seribu Bisik | Paviliun Wanxin |
| Rumah Gadai Giok Sejuk | Rumah Gadai Hanbi |
| Perhimpunan Tabib Pengembara | Perhimpunan Youyi |

## 4. Core Terms — Do Not Rename

- Cultivation Realm
- Spirit Beast
- Qi
- Cultivation
- Technique
- Combat
- Economy
- Vitality
- Item
- Loot
- Crafting
- Alchemy

## 5. Runtime Resolution Rules

1. Saat roleplay, gunakan Runtime untuk nama yang memiliki mapping di file ini.
2. Saat mengambil data dari repository, gunakan Canon sebagai identifier sumber.
3. Jangan mengubah isi modul canon hanya untuk menerapkan alias.
4. Jangan mengubah mekanik, angka sistem, realm, statistik, teknik, item, loot, atau aturan AI GM akibat overlay ini.
5. Jika suatu nama belum memiliki alias aktif, gunakan nama canon; jangan mengarang alias baru.
6. Alias harus konsisten: satu Canon name → satu Runtime name.
7. Runtime alias bukan fakta canon baru.
8. Jika terjadi konflik antara alias dan data canon, data canon tetap menjadi sumber kebenaran.
9. Untuk organisasi, istilah **Perguruan** menggantikan label runtime **Dojo** pada lima organisasi yang dipetakan sebagai Dojo.
10. File dan path repository tetap menggunakan nama canon; overlay hanya mengatur nama yang tampil/digunakan dalam runtime roleplay.

## 6. Scope

Overlay ini saat ini berlaku untuk:
- World identity
- 6 geographic regions
- 24 canonical organizations

Overlay ini **belum mengubah** nama lokasi, NPC, event, item, teknik, atau isi modul canon.

**Implementation principle:** Canon Data → Runtime Alias Resolution → Player-facing Name
