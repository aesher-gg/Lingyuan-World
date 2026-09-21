# Lingyuan World — Shared World Runtime Contract

> **Status:** Canonical System Contract
> **Purpose:** authoritative resolution boundary untuk interaksi state lintas-player/lintas-chat.
> **Scope:** runtime world state; bukan engine server dan bukan klaim bahwa GitHub/Qwen menyediakan live synchronization.

---

## 0. Prinsip

Lingyuan World dapat memiliki banyak player, tetapi banyaknya player tidak berarti semua chat otomatis berbagi state runtime.

State bersama hanya authoritative bila berasal dari:
1. shared runtime yang benar-benar tersedia; atau
2. checkpoint yang telah diverifikasi Admin.

Tanpa salah satunya, state lintas-chat = `UNRESOLVED`.

---

## 1. Identity

Setiap persistent runtime object WAJIB memiliki identity yang dapat dibedakan.

Contoh kelas:
- Player State;
- NPC State;
- Monster/Spirit Beast State;
- Garden State;
- Plant Instance;
- Item Instance;
- Output Instance;
- Location State;
- World Event State;
- Transaction/Event Record.

ID contoh hanya format. ID permanent harus berasal dari authoritative state/checkpoint.

---

## 2. Minimum Shared State

Bila object membutuhkan shared runtime, minimum state dapat mencakup:
- Instance ID;
- Owner/Custodian;
- Location;
- World-Time Marker;
- Current Condition/Status;
- Access Policy;
- Active Effects/Events;
- Event History;
- Last Verified Checkpoint.

Field yang tidak tersedia tetap `???`.

---

## 3. Event Contract

Setiap perubahan state harus dapat direpresentasikan:

`Actor → Action → Target → World Time → Permission → Preconditions → Cost → Result → State Delta → Provenance`

Player intent hanya mengisi bagian Action/Target yang diminta; hasil tetap harus di-resolve.

---

## 4. Permission

Permission tidak boleh diasumsikan dari kedekatan lokasi atau keberadaan player.

Minimal:
- Owner;
- Custodian;
- Access Policy;
- Canon authority;
- Transfer Event bila ownership berpindah.

Menyentuh, melihat, membantu, menemukan, atau melakukan satu aksi tidak otomatis mengubah ownership.

---

## 5. Event Ordering

Jika beberapa event memengaruhi object yang sama:
1. gunakan authoritative world time;
2. gunakan event sequence bila tersedia;
3. gunakan checkpoint history;
4. bila order tidak dapat dibuktikan = `UNRESOLVED`.

Tidak boleh memakai urutan pesan dari chat berbeda sebagai bukti world-time order.

---

## 6. Conflict Resolution

Konflik state harus dibandingkan pada:
- Instance identity;
- World time;
- Event history;
- Ownership;
- Location;
- Preconditions;
- Result;
- Provenance.

Tidak boleh:
- memilih state berdasarkan siapa yang lebih dulu mengirim pesan di chat berbeda;
- menggabungkan dua state yang bertentangan;
- menghapus event tanpa evidence.

Jika evidence tidak cukup = `UNRESOLVED`.

---

## 7. Cross-Chat Encounter

Player A dan Player B dapat berada di dunia canon yang sama, tetapi encounter lintas-chat hanya dapat dinyatakan terjadi bila:
- shared runtime authoritative mencatat keduanya pada state/location yang compatible; atau
- Admin memverifikasi checkpoint/event yang menghubungkan keduanya.

Jika tidak ada bukti tersebut, GM tidak boleh menyatakan:
- mereka sudah bertemu;
- telah berbicara;
- telah bertarung;
- telah bertukar item;
- telah mengubah state satu sama lain.

---

## 8. Transaction / Transfer

Transfer item/currency/ownership mengikuti:

`Source Instance → Actor → Permission → Transaction Event → Recipient → New Ownership/Balance → History`

Tidak ada duplication dari dua chat yang sama-sama mengklaim object yang sama.

---

## 9. Death / Destruction / Consumption

State irreversible seperti:
- death;
- destruction;
- item consumption;
- harvest;
- sale;
- transfer;
- facility depletion

harus memiliki event evidence sebelum diterapkan ke shared state.

Jika dua chat memiliki hasil berbeda untuk object yang sama, state menjadi `UNRESOLVED` sampai conflict resolution selesai.

---

## 10. Checkpoint Contract

Checkpoint minimal:
- Runtime timestamp/world-time marker;
- relevant instances;
- locations;
- ownership/access;
- condition/status;
- event history;
- inventory/output changes;
- unresolved conflicts.

Checkpoint bukan narasi bebas dan tidak boleh menghapus unknown field tanpa evidence.

---

## 11. Official Save

`Runtime State → Checkpoint → Admin Verification → Official Save`

Qwen/AI GM tidak menulis official save langsung.

Official save hanya boleh menerima perubahan yang dapat diverifikasi.

---

## 12. Anti-Exploit

DILARANG:
- cross-chat synchronization by assumption;
- duplicate item/object dari dua chat;
- ownership transfer tanpa event;
- teleport/encounter tanpa location/time evidence;
- retroactive event tanpa checkpoint/evidence;
- merge conflict tanpa resolution;
- memilih hasil hanya karena menguntungkan player;
- mengubah `UNRESOLVED` menjadi fakta melalui inferensi.

---

## 13. Gardening Integration

Gardening menggunakan contract ini untuk:
`Garden → Plant Instance → Maintenance → Growth → Harvest → Output → Transfer/Usage`.

Aksi player lain hanya sah bila permission + shared state dapat diverifikasi.

---

## 14. Runtime Limitation

Contract ini mendefinisikan aturan adjudication, bukan live multiplayer server.

Jika belum ada engine/shared runtime eksternal yang menyediakan authoritative state lintas-chat, Admin checkpoint adalah fallback verification mechanism.
