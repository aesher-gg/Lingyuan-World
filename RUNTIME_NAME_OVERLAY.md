# Lingyuan World — Runtime Name Overlay

> **Status:** Runtime overlay only  
> **Canon:** Repository module names remain unchanged.  
> **Purpose:** Menyediakan nama runtime yang dipakai AI GM saat roleplay tanpa mengubah isi modul canon.

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

## 3. Locations

### Central Plains → Tianzhou
| Canon | Runtime |
|---|---|
| Kota Yunjing | Kota Yuntian |
| Kota Luoxing | Kota Haoyang |
| Desa Baihe | Desa Qinghe |
| Kota Heiyu | Kota Heiyuan |
| Lembah Qinghe | Lembah Qingyuan |

Routes:
- Kota Yuntian ↔ Kota Haoyang
- Kota Haoyang ↔ Desa Qinghe
- Kota Haoyang ↔ Kota Heiyuan
- Desa Qinghe ↔ Lembah Qingyuan

### Azure Mountain Range → Qingyun
| Canon | Runtime |
|---|---|
| Kota Lingshan | Kota Lingxiao |
| Desa Yunmu | Desa Yunhe |
| Lembah Qingsong | Lembah Cangzhu |
| Puncak Tianque | Puncak Tianyun |
| Hutan Wuyin | Hutan Mizong |

### Southern Demon Domain → Moyuan
| Canon | Runtime |
|---|---|
| Kota Nanyao | Kota Yaoyang |
| Pelabuhan Chixia | Pelabuhan Chiyang |
| Hutan Cangmang | Hutan Wanmang |
| Lembah Seratus Bunga | Lembah Baiyue |
| Pegunungan Huoyan | Pegunungan Yanling |

### Eastern Sea Region → Haiyuan
| Canon | Runtime |
|---|---|
| Kota Haicheng | Kota Haijing |
| Pulau Yuehai | Pulau Yuehua |
| Kepulauan Lanyue | Kepulauan Lanxing |
| Jurang Laut Canglong | Jurang Laut Longyuan |
| Pulau Qionghua | Pulau Qiongyu |

### Northern Desolate Territory → Beiyuan
| Canon | Runtime |
|---|---|
| Kota Beixue | Kota Xueyuan |
| Benteng Hanjiang | Benteng Hanlu |
| Desa Xuehe | Desa Linghe |
| Lembah Bingxin | Lembah Hanyue |
| Reruntuhan Tianhan | Reruntuhan Xuetian |

### Western Sacred Deserts → Xisha
| Canon | Runtime |
|---|---|
| Kota Shajing | Kota Shayan |
| Kota Jinyue | Kota Jinsha |
| Oasis Qingyu | Oasis Qinglan |
| Laut Pasir Wuheng | Laut Pasir Wuhuang |
| Makam Tianri | Makam Riyuan |

## 4. Organizations

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

## 5. Core Terms — Do Not Rename
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

## 6. Runtime Resolution Rules
1. Saat roleplay, gunakan Runtime untuk nama yang memiliki mapping.
2. Saat mengambil data dari repository, gunakan Canon sebagai identifier sumber.
3. Jangan mengubah isi modul canon hanya untuk menerapkan alias.
4. Jangan mengubah mekanik atau angka sistem akibat overlay ini.
5. Jika suatu nama belum memiliki alias, gunakan nama canon; jangan mengarang alias baru.
6. Alias harus konsisten: satu canon name → satu runtime name.
7. Runtime alias bukan fakta canon baru dan tidak boleh dianggap sebagai pengganti data modul.
8. Jika terjadi konflik antara alias dan data canon, data canon tetap menjadi sumber kebenaran.

## 7. Scope
Overlay ini berlaku untuk nama dunia, region, lokasi, route location, serta sekte/dojo/organisasi yang sudah memiliki mapping.

Overlay ini tidak mengubah isi modul canon, sistem permainan, statistik, realm, teknik, item, loot, NPC facts, ekonomi, combat, atau aturan AI GM.

Implementation principle: Canon Data → Runtime Alias Resolution → Player-facing Name
