# 🌙 TASK: Build "Goodnight" — A Special Single-Page Website for My Girlfriend

---

## 🎯 Tujuan

Buat sebuah website single-page yang **sangat istimewa**, dibuat oleh seorang programmer yang juga seorang pacar yang manis. Website ini khusus untuk mengucapkan **selamat malam** kepada kekasihnya. Bukan website biasa — ini adalah pengalaman yang hanya bisa dibuat oleh seseorang yang tahu cara bicara ke hati orang yang dicintai *lewat kode*.

---

## 🖥️ Spesifikasi Teknis

- **Format**: Single HTML file (semua CSS + JS inline dalam satu file `index.html`)
- **Responsif**: Wajib mulus di semua ukuran layar — mobile (≥320px), tablet, desktop
- **No framework eksternal**: Boleh pakai Google Fonts dan CDN font saja. Semua JS/CSS ditulis manual.
- **Browser support**: Chrome, Firefox, Safari (modern)
- **Performance**: Animasi harus smooth (gunakan `transform` dan `opacity`, bukan `top/left/width`)
- **Output file**: `index.html`

---

## 🎨 Arah Estetika (WAJIB DIIKUTI)

### Tema Visual
**"Dreamy Night Sky Luxury"** — langit malam yang dalam, bintang yang berkedip perlahan, suasana hangat seperti lampu kamar tidur, nuansa yang intim, personal, dan sedikit puitis. Bukan gelap yang menakutkan, tapi gelap yang nyaman seperti dipeluk.

### Palette Warna
```
--bg-deep:        #070B14   /* biru tua sangat gelap */
--bg-mid:         #0E1525   /* biru navy gelap */
--accent-warm:    #F4C87A   /* emas hangat / bintang */
--accent-rose:    #E8879B   /* pink mawar lembut */
--accent-lavender:#B8A4D8   /* lavender malam */
--text-main:      #F0EDE6   /* putih krem hangat */
--text-dim:       #8A8FA8   /* abu kebiruan */
--glow:           rgba(244, 200, 122, 0.15)
```

### Tipografi
- **Display/Heading**: `Playfair Display` (Google Fonts) — serif elegan, romantis
- **Body/Paragraph**: `Lora` (Google Fonts) — serif yang nyaman dibaca, hangat
- **Accent/Code snippets**: `DM Mono` (Google Fonts) — untuk "easter egg programmer"
- Import di `<head>`: `https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Lora:ital,wght@0,400;0,500;1,400&family=DM+Mono:wght@300;400&display=swap`

---

## 📜 STRUKTUR HALAMAN & KONTEN PER SECTION

> Setiap section **hanya muncul / terpicu saat user scroll ke area tersebut** (Intersection Observer). Animasi masuk harus terasa seperti sesuatu yang *muncul perlahan di kegelapan*.

---

### SECTION 0 — Hero: "Selamat Malam, Sayang"
**Posisi**: Full viewport height, langsung terlihat saat halaman dibuka.

**Konten**:
- Latar: Canvas animasi bintang bertebaran (partikel kecil berwarna `--accent-warm` dan `--accent-lavender`, berkedip perlahan dengan `opacity` oscillating)
- Teks tengah:
  ```
  selamat malam,
  ```
  (Playfair Display, italic, kecil, `--text-dim`)
  lalu nama pacar muncul satu per satu dengan **typewriter effect**:
  ```
  Sayang. 🌙
  ```
  (Playfair Display, bold, besar sekali, `--accent-warm`)
- Di bawah nama: teks kecil berkedip (blink slow):
  ```
  scroll ke bawah ↓
  ```
- **Efek khusus**: Mouse/touch move membuat bintang-bintang bergerak sedikit mengikuti kursor (parallax ringan).

---

### SECTION 1 — "Kamu Tahu Gak Sih…"
**Trigger**: Scroll masuk viewport.

**Konten**:
- Header: `"Kamu tahu gak sih…"` — muncul fade-in dari bawah
- Lalu muncul satu per satu (staggered, delay 400ms tiap item) daftar fakta kecil tentang malam:
  ```
  🌙  Bulan tadi nemenin aku sambil nunggu kamu tidur.
  ⭐  Ada 9.096 bintang yang bisa dilihat mata, tapi cuma satu yang paling terang.
  🫧  Suhu turun 3 derajat tiap malam. Makanya tidur pakai selimut ya.
  💤  Orang butuh rata-rata 7 menit buat ketiduran. Kamu butuh berapa?
  ```
- **Efek khusus**: Setiap item punya hover state — saat di-hover, kartu sedikit terangkat (`translateY(-4px)`) dengan glow tipis di sekelilingnya.

---

### SECTION 2 — "Pesan dari si Programmer"
**Trigger**: Scroll masuk viewport.

**Konten**:
- Visual: Tampilan mirip terminal/code editor mini (bukan full screen, cuma blok kecil di tengah) dengan background `#0D1117`, border tipis `--accent-lavender`.
- Teks di dalam terminal muncul dengan **typing animation** (seperti diketik langsung):
  ```
  > running: send_love.py

  print("Hai kamu yang lagi baca ini.")
  print("Aku lagi di depan layar, masih mikirin kamu.")
  print("Tapi setidaknya aku sempat bikin ini buat kamu.")
  
  # output:
  # Selamat malam. Tidur yang nyenyak ya. 🌙
  # Kamu di-debug dari semua kekhawatiran malam ini.
  # — dari yang selalu ada di commit history hatimu
  ```
- Cursor berkedip di akhir setelah selesai mengetik.
- **Efek khusus**: Ada tombol kecil di pojok kanan atas terminal: `[ RUN ✦ ]` — kalau diklik, muncul confetti kecil berwarna emas dan lavender.

---

### SECTION 3 — "Ribuan Mil, Satu Malam yang Sama"
**Trigger**: Scroll masuk viewport.

**Konten**:
- Visual: Ilustrasi SVG sederhana tapi cantik — dua siluet (satu di kiri, satu di kanan) yang duduk di bawah langit yang sama, dengan bulan besar di tengah atas.
- Teks di bawah ilustrasi (muncul fade-in):
  ```
  "Di manapun kamu tidur malam ini,
   kita masih di bawah bulan yang sama."
  ```
  (Playfair Display, italic, centered, ukuran besar)
- **Efek khusus**: Bulan di SVG punya animasi `pulse` glow yang sangat halus (scale 1 → 1.03 → 1, loop). Bintang-bintang kecil di SVG berkedip secara independen.

---

### SECTION 4 — "Alasan Aku Bilang Goodnight"
**Trigger**: Scroll masuk viewport.

**Konten**:
- Header: `"Kenapa aku selalu bilang goodnight?"` — fade in
- Lalu sebuah **reveal card** — awalnya terlihat seperti amplop tertutup (CSS shape, ada ikon amplop ✉️ di tengahnya).
- Saat user klik amplop, ada animasi amplop terbuka (CSS transform) dan muncul teks surat:
  ```
  Karena setiap "goodnight" yang aku kirim
  itu artinya: aku mau jadi hal terakhir
  yang kamu pikirkan sebelum tidur.
  
  Dan semoga hal pertama yang kamu senyumin
  pas bangun besok pagi. 🌅
  
                          — dari aku 🩷
  ```
- **Efek khusus**: Animasi amplop terbuka dengan CSS `transform: rotateX()` — elegan dan halus. Teks di dalam muncul dengan fade-in staggered per baris.

---

### SECTION 5 — "Playlist Malam Ini"
**Trigger**: Scroll masuk viewport.

**Konten**:
- Header: `"Playlist buat nemenin tidur kamu"` — fade in
- Tampilkan **3 kartu lagu** (visual saja, bukan player sungguhan) dengan desain seperti vinyl record / album art mini:
  ```
  🎵 "Comptine d'un autre été" — Yann Tiersen
  🎵 "Bloom" — The Paper Kites  
  🎵 "Die with a Smile" — Bruno Mars & Lady Gaga
  ```
- Setiap kartu punya ikon vinyl yang berputar saat di-hover (`animation: spin 4s linear infinite` on hover).
- Di bawah kartu: teks kecil italic:
  ```
  "Dengerin salah satunya sambil tutup mata. Aku jamin kamu tidur."
  ```
- **Efek khusus**: Kartu muncul dengan stagger dari kiri ke kanan. Hover state: slight `scale(1.04)` + glow hangat.

---

### SECTION 6 — "Mimpi Indah Generator"
**Trigger**: Scroll masuk viewport.

**Konten**:
- Header: `"Mau mimpi apa malam ini?"` — fade in
- Sebuah tombol besar bercahaya:
  ```
  [ ✨ Generate Mimpiku ✨ ]
  ```
- Saat diklik, tampilkan salah satu dari array mimpi secara random (ganti dengan animasi fade):
  ```javascript
  const dreams = [
    "☁️ Kamu lagi jalan di taman bunga wisteria, anginnya hangat, dan ada seseorang yang genggam tanganmu.",
    "🌊 Pantai yang sepi, pasirnya putih, dan kamu duduk nonton matahari tenggelam sambil makan es krim.",
    "🏔️ Puncak gunung yang tenang. Kamu di atas, dan seluruh kota ada di bawah kakimu.",
    "🌌 Kamu bisa terbang pelan-pelan di atas langit malam, dan semua bintang nyapa kamu.",
    "🍵 Pagi yang slow, teh hangat, hujan di luar jendela, dan buku favorit di tangan.",
    "🎠 Festival lampu terbang di tepi danau. Setiap lampu yang kamu lepas membawa satu kekhawatiran pergi.",
    "🌸 Kebun sakura di musim semi. Kelopaknya jatuh pelan kayak salju merah muda.",
  ]
  ```
- Tombol bisa diklik berkali-kali untuk dapat mimpi baru.
- **Efek khusus**: Setiap kali klik, ada small particle burst berwarna emas dari tombol.

---

### SECTION 7 — "Final Goodnight"
**Trigger**: Scroll ke paling bawah.

**Konten**:
- Full viewport height, latar sangat gelap dengan efek nebula warna lavender dan rose yang sangat halus (CSS radial gradients, opacity rendah).
- Teks muncul satu per satu, baris per baris, dengan delay:
  ```
  Oke.
  
  Sekarang taruh HP-mu.
  
  Tutup mata.
  
  Aku gak kemana-mana kok. 🌙
  
  Selamat malam, sayang.
  ```
  (Semua Playfair Display, centered, ukuran variatif — "Oke" kecil, "Selamat malam, sayang" besar)
- Di bawah teks: jam digital real-time kecil (HH:MM:SS) dalam font `DM Mono`, warna `--text-dim`
- **Efek khusus**: Setelah semua teks muncul, ada **animasi bulan sabit** kecil bersinar di pojok atas yang perlahan-lahan membesar lalu mengecil (breathing).
- **Easter egg**: Kalau user shake device (devicemotion) atau tekan tombol `S` di keyboard, muncul overlay gelap pelan-pelan dengan teks: `"Sudah aku bilang, taruh HP-nya. 😄 Goodnight. 💙"` lalu setelah 3 detik fade out.

---

## ✨ Global Effects & Polish

### Background Stars (Canvas)
- Buat `<canvas id="stars">` yang cover seluruh halaman (fixed, z-index rendah)
- Generate 200 bintang random, masing-masing dengan:
  - Ukuran: 0.5px – 2px
  - Opacity: random 0.3–1, oscillating dengan speed berbeda-beda
  - Warna: mix antara `#F4C87A` dan `#B8A4D8` dan `#FFFFFF`
- Paralax: pada `mousemove`/`touchmove`, geser canvas sejauh `deltaX * 0.02, deltaY * 0.02`

### Scroll Animations (Intersection Observer)
- Semua section punya class `fade-section` yang defaultnya `opacity: 0; transform: translateY(40px)`
- Saat masuk viewport (threshold 0.15), tambahkan class `visible`: `opacity: 1; transform: translateY(0); transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1)`
- Staggered children: gunakan `--delay` CSS variable per child element

### Custom Scrollbar
```css
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(--bg-deep); }
::-webkit-scrollbar-thumb { background: var(--accent-warm); border-radius: 2px; }
```

### Custom Cursor (Desktop only)
- Cursor: titik kecil `8px` warna `--accent-warm`, dengan lingkaran follower `24px` yang follow dengan lag (`lerp`)
- Di mobile: sembunyikan custom cursor

### Smooth Scroll
```css
html { scroll-behavior: smooth; }
```

### Section Dividers
- Antara section, bukan garis lurus biasa — gunakan SVG wave atau diagonal clip-path dengan warna yang sedikit berbeda dari sekitarnya.

---

## 📱 Responsivitas

| Breakpoint | Penyesuaian |
|---|---|
| Mobile (< 480px) | Font scale turun 20%, padding section dikurangi, terminal section menjadi full-width, kartu lagu stack vertikal |
| Tablet (480–768px) | 2 kolom untuk kartu lagu, ukuran SVG ilustrasi dikecilkan |
| Desktop (> 768px) | Layout penuh, custom cursor aktif, semua efek aktif |

Gunakan `clamp()` untuk ukuran font agar fluid:
```css
font-size: clamp(2rem, 5vw, 4.5rem);
```

---

## 🗂️ Struktur File Output

```
index.html   ← SATU FILE SAJA, semua inline
```

Struktur HTML:
```html
<!DOCTYPE html>
<html lang="id">
<head>
  <!-- meta, viewport, title, Google Fonts -->
  <style>/* SEMUA CSS DI SINI */</style>
</head>
<body>
  <canvas id="stars"></canvas>
  <div id="cursor-dot"></div>
  <div id="cursor-ring"></div>

  <section id="hero">...</section>
  <section id="did-you-know">...</section>
  <section id="programmer-note">...</section>
  <section id="same-moon">...</section>
  <section id="why-goodnight">...</section>
  <section id="playlist">...</section>
  <section id="dream-gen">...</section>
  <section id="final">...</section>

  <script>/* SEMUA JS DI SINI */</script>
</body>
</html>
```

---

## ✅ Definition of Done

- [ ] Semua 8 section terimplementasi dengan konten lengkap
- [ ] Animasi scroll (Intersection Observer) bekerja di semua section
- [ ] Canvas bintang berjalan smooth (60fps, no jank)
- [ ] Parallax bintang merespons mouse/touch
- [ ] Typewriter effect di Hero dan Terminal section berjalan
- [ ] Terminal section: typing animation + tombol RUN + confetti
- [ ] Amplop section: animasi buka amplop berfungsi saat diklik
- [ ] Dream Generator: random mimpi tampil saat klik + particle burst
- [ ] Easter egg keyboard `S` / device shake berfungsi
- [ ] Jam real-time berjalan di section final
- [ ] Custom cursor di desktop
- [ ] Fully responsive di mobile (320px), tablet, dan desktop
- [ ] Hanya 1 file `index.html`, tidak ada dependensi eksternal selain Google Fonts
- [ ] Tidak ada error di browser console
- [ ] Halaman terasa *personal*, *hangat*, dan *istimewa* — bukan template generik

---

## 💡 Catatan untuk Developer

> Website ini bukan portofolio. Ini adalah **surat cinta yang dikodekan**. Setiap detail kecil penting. Jangan terburu-buru di animasi — `cubic-bezier` yang tepat membuat perbedaan antara "oke" dan "wow". Kalau ada bagian yang bisa dibuat lebih indah dengan 5 baris kode tambahan, lakukan. Pacar si programmer ini layak mendapat yang terbaik.

Prioritas: **keindahan > performa > brevitas kode**. Boleh panjang, asal hasilnya luar biasa.
