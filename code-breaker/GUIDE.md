# CODE-BREAKER - Panduan Bermain

## Overview
CODE-BREAKER adalah game kartu strategy berbasis pemrograman. Lawan AI dan kalahkan musuh dengan membangun program yang valid!

---

## Tujuan Game
Kurangi **INTEGRITY** (HP) musuh hingga 0 sebelum INTEGRITY kamu habis. Setiap pemain memulai dengan 100 INTEGRITY.

---

## Jenis Kartu

### 1. CMD (Command) - Warna Kuning
Kartu wajib untuk setiap baris program. Tanpa CMD, program tidak bisa dijalankan.

| Nama | Effect | Deskripsi |
|------|--------|------------|
| IF | condition_exec | Kondisi wajib dieksekusi |
| WHILE | loop_exec | Kondisi looping (terus dibanding) |
| FOR | loop_exec | Kondisi looping (counter) |
| RETURN | flat_boost | Kondisi selalu valid, +5 power |

### 2. COND (Condition) - Warna Biru
Kartu bonus yang memberikan efek tambahan jika kondisi tertentu terpenuhi.

| Nama | Power | Syarat |
|------|-------|--------|
| TRUE | +5 | Selalu valid |
| VALUE>5 | +8 | Jika musuh < 50 INTEGRITY |
| DEFINED | +6 | Jika punya 2+ program aktif |
| OVERFLOW | +10 | Jika tangan ≥ 5 kartu |
| LOOP!=0 | +7 | Jika ada kartu WHILE di baris |

### 3. ACT (Action) - Warna Merah
Kartu efek utama yang dieksekusi saat program berjalan.

| Nama | Power | Effect | Deskripsi |
|------|-------|--------|------------|
| ATTACK | 15 | damage | Deal 15 + bonus damage ke musuh |
| ENCRYPT | 10 | heal | Restore 10 INTEGRITY sendiri |
| DDoS | 12 | ddos | Deal 12 damage + crash 1 baris musuh |
| INJECT | 8 | draw_dmg | Deal 8 damage + draw 1 kartu |
| FIREWALL | 0 | shield |_BLOCK serangan berikutnya |
| EXPLOIT | 20 | big_dmg | Deal 20 damage (butuh 2 COND) |

### 4. INT (Interrupt) - Warna Ungu
Kartu instan yang bisa dimainkan kapan saja (bahkan saat musuh bermain).

| Nama | Effect | Deskripsi |
|------|--------|------------|
| NULL_PTR | crash_line | Hancurkan 1 baris program musuh |
| BACKDOOR | steal | Ambil 1 kartu dari deck musuh |
| LOG_OUT | mill | Buang kartu teratas deck musuh |
| PATCH | fix | Perbaiki 1 syntax error di barismu |
| ANTIVIRUS | counter | Batalkan interrupt musuh |

---

## Cara Bermain

### Fase Game
1. **DRAW PHASE** - Klik [DRAW] untuk menarik 2 kartu
2. **CODING PHASE** - Taruh kartu ke baris program
3. **COMPILE PHASE** - Compile program untuk eksekusi
4. **INTERACTION PHASE** - Mainkan interrupt jika perlu
5. **ENEMY TURN** - Musuh bermain

### Menempati Kartu
- **Click & Drop**: Klik kartu di tangan, lalu klik baris tujuan
- **Drag & Drop**: Tarik kartu ke baris yang diinginkan
- Setiap baris maksimal 4 kartu

### Syntax Validation
Baris program harus memiliki minimal:
- 1 kartu **CMD** (Command)
- 1 kartu **ACT** (Action)

Contoh baris valid:
```
[IF] [ATTACK] = ✅ Valid
[ATTACK] = ❌ CMD wajib ada
[IF] = ❌ ACT wajib ada
```

### Status Baris
- **Empty** - Kosong, belum ada kartu
- **Pending** - Sudah ada kartu, belum di-compile
- **Valid** - syntax benar, siap dieksekusi
- **Invalid** - syntax salah (bukan CMD+ACT), akan crash

### Jika Crash
Kartu di baris tersebut akan masuk ke trash dan tidak memberikan efek.

---

## Strategi Tips

### Combo Recommendations
1. **Damage Build**: IF + TRUE + ATTACK (damage + bonus)
2. **Heal Build**: FOR + ENCRYPT (restore HP)
3. **Draw Build**: IF + INJECT (damage + card advantage)
4. **Big Hit**: IF + DEFINED + OVERFLOW + EXPLOIT (damage besar)

### Interrupt Usage
- **PATCH**: Gunakan saat barismu invalid
- **ANTIVIRUS**: Gunakan saat musuh memainkan interrupt
- **NULL_PTR**: Hancurkan program berbahaya musuh

### Timing
- Simpan interrupt untuk momen krusial
- Jangan terlalu banyak taruh kartu di satu baris
- Prioritaskan membuat 2-3 baris valid

---

## Controls
- **Mouse Click**: Pilih kartu / Pilih baris
- **Drag & Drop**: Taruh kartu ke baris
- **Buttons**: DRAW, COMPILE, END TURN, INTERRUPT

---

## Menang
Kalahkan musuh dengan mengurangi INTEGRITY mereka ke 0 sebelum kamu kalah!

---

*Guide ini dibuat untuk CODE-BREAKER v1.0*