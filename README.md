<div align="center">

# SeLA

**Super Easy Learning AI**

Buat soal latihan dari materi apapun, dalam hitungan detik.

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-00d4aa?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](LICENSE)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Cerebras](https://img.shields.io/badge/Cerebras_API-qwen--3--235b-00D4AA?style=for-the-badge&logo=lightning&logoColor=white)](https://cerebras.ai)

<br/>

[![No Server](https://img.shields.io/badge/Server-Not_Required-lightgrey?style=flat-square&logo=serverfault&logoColor=white)]()
[![Mobile Ready](https://img.shields.io/badge/Responsive-Mobile_%26_Desktop-00d4aa?style=flat-square&logo=googlechrome&logoColor=white)]()
[![KaTeX](https://img.shields.io/badge/KaTeX-Math_Rendering-008080?style=flat-square&logo=latex&logoColor=white)](https://katex.org)
[![Tailwind](https://img.shields.io/badge/Tailwind_CSS-Utility_Classes-38BDF8?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat-square&logo=github)](CONTRIBUTING.md)

</div>

---

## Gambaran Umum

**SeLA (Super Easy Learning AI)** adalah aplikasi web berbasis kecerdasan buatan yang memungkinkan siapa saja membuat soal pilihan ganda secara otomatis dari materi apapun — Matematika, Sejarah, Python, Excel, dan lainnya.

Cukup masukkan topik, jumlah soal, dan tingkat kesulitan. SeLA akan menghasilkan soal beserta jawaban dan penjelasannya dalam hitungan detik.

Cocok untuk:
- Pelajar yang ingin berlatih soal secara mandiri
- Guru yang ingin membuat latihan cepat
- Siapapun yang ingin menguji pemahaman mereka terhadap suatu materi

---

## Peringatan Penting

> **Proyek ini tidak menyertakan API key.**

Untuk menjalankan SeLA, kamu wajib menyediakan API key Cerebras milikmu sendiri.

- Gunakan API key milik sendiri yang diperoleh dari [console.cerebras.ai](https://console.cerebras.ai)
- Jaga kerahasiaan API key — jangan bagikan ke siapapun
- Jangan commit `index.html` yang sudah berisi API key ke repositori publik
- Jangan hardcode API key di fork publik milikmu

Penggunaan tanpa pengamanan yang tepat dapat menyebabkan **penyalahgunaan akses dan biaya tak terduga** pada akun kamu.

---

## Fitur

| Fitur | Deskripsi |
|---|---|
| Pembuatan soal otomatis | Generate soal pilihan ganda dari topik apapun via AI |
| Pilih jumlah soal | Slider interaktif, antara 3 hingga 30 soal |
| Pilih tingkat kesulitan | Input bebas: mudah, SD, SMA, sulit, dll. |
| Rendering LaTeX | Rumus matematika/fisika/kimia ditampilkan dengan benar via KaTeX |
| Progress quiz | Progress bar dan hitungan soal terjawab secara real-time |
| Review jawaban | Setelah selesai, lihat mana yang benar/salah beserta penjelasannya |
| Skor visual | Ditampilkan dengan animasi ring yang elegan |
| Animasi partikel | Background animasi partikel yang ringan dan non-distracting |
| Fully responsive | Tampilan optimal di mobile dan desktop |
| No backend | Berjalan 100% di sisi klien, tidak perlu server |

---

## Teknologi

```
SeLA
├── Frontend
│   ├── HTML5          - Struktur aplikasi
│   ├── CSS3           - Custom properties, animasi, dark theme
│   ├── JavaScript     - Logic quiz, state management, API call
│   └── Tailwind CSS   - Utility classes (via CDN)
│
├── AI Layer
│   └── Cerebras API   - Model qwen-3-235b-a22b-instruct-2507
│
├── Rendering
│   └── KaTeX          - Render rumus matematika/LaTeX
│
└── Font
    ├── Space Grotesk  - Display / heading
    └── DM Sans        - Body text
```

---

## Cara Memulai

### Prasyarat

- Browser modern (Chrome, Firefox, Edge, Safari)
- Koneksi internet
- API key dari [console.cerebras.ai](https://console.cerebras.ai)

### Instalasi

Clone repositori:

```bash
git clone https://github.com/ikyletwar/SeLA.git
cd SeLA
```

Struktur direktori:

```
SeLA/
├── index.html    <- Seluruh aplikasi ada di sini
└── README.md
```

### Konfigurasi API Key

Buka `index.html` dengan text editor, lalu cari bagian berikut:

```javascript
const API_CONFIG = {
  url: 'https://api.cerebras.ai/v1/chat/completions',
  key: '',   // <-- Isi di sini
  model: 'qwen-3-235b-a22b-instruct-2507',
  ...
};
```

Ganti `key: ''` dengan API key kamu:

```javascript
key: 'csk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
```

Simpan file, lalu buka di browser.

**Cara mendapatkan API key:**
1. Kunjungi [console.cerebras.ai](https://console.cerebras.ai)
2. Daftar atau login
3. Navigasi ke bagian **API Keys**
4. Klik **Create New Key**
5. Salin dan simpan key dengan aman

### Menjalankan Aplikasi

**Metode 1 — Langsung (paling simpel):**

Klik dua kali `index.html`, buka di browser.

**Metode 2 — Local server (direkomendasikan):**

```bash
# Python 3
python -m http.server 8080

# Node.js
npx serve .
```

Buka `http://localhost:8080` di browser.

---

## Penggunaan

**1. Isi form**
- Masukkan materi pelajaran (contoh: "Integral Tentu", "Perang Dunia II", "Dasar Python")
- Geser slider untuk menentukan jumlah soal (3-30)
- Masukkan tingkat kesulitan (contoh: "SMA kelas 12", "pemula", "sulit")

**2. Generate soal**
- Klik tombol **Generate Soal**
- Tunggu AI memproses — ada 4 step loading yang ditampilkan
- Soal muncul secara otomatis

**3. Kerjakan quiz**
- Pilih jawaban untuk setiap soal
- Progress bar menunjukkan berapa soal yang sudah dijawab
- Tombol **Selesai** aktif setelah semua soal dijawab

**4. Lihat hasil**
- Skor ditampilkan dalam bentuk persen dengan animasi ring
- Review per soal: jawaban kamu, jawaban benar, dan penjelasan
- Klik **Buat Quiz Baru** untuk mulai dari awal

---

## Dukungan LaTeX

Untuk materi yang mengandung rumus, SeLA mendukung rendering LaTeX via KaTeX. AI akan otomatis menggunakan format LaTeX saat materi membutuhkannya (matematika, fisika, kimia, dll.).

Format yang didukung di dalam soal yang dihasilkan AI:

- Inline: `$E = mc^2$`
- Display: `$$\int_{a}^{b} f(x)dx$$`
- Alternatif inline: `\(x^2 + y^2\)`
- Alternatif display: `\[F = ma\]`

---

## Kustomisasi

**Ubah model AI** — di dalam `API_CONFIG`:

```javascript
model: 'qwen-3-235b-a22b-instruct-2507'
```

**Ubah batas soal** — di elemen slider HTML:

```html
<input type="range" min="3" max="30" ...>
```

**Ubah tema warna** — via CSS custom properties:

```css
:root {
  --bg-primary: #08090c;
  --accent: #00d4aa;      /* Warna utama */
  --fg-primary: #f0f2f5;
  --border: #252d3d;
}
```

**Ubah persona AI** — modifikasi variabel `systemPrompt` di dalam fungsi `fetchQuestions()`.

---

## Pemecahan Masalah

**Error 401 / API key tidak valid**
- Pastikan key disalin dengan benar tanpa spasi tambahan
- Cek status key di [console.cerebras.ai](https://console.cerebras.ai)
- Coba generate key baru jika masalah berlanjut

**Soal tidak muncul / loading terus**
- Buka DevTools (`F12`) > Console, cek pesan error
- Pastikan koneksi internet stabil
- Refresh dan coba generate ulang

**Rumus tidak ter-render**
- Pastikan tidak ada spasi setelah `$` pembuka: `$x^2$` bukan `$ x^2$`
- Cek apakah KaTeX berhasil dimuat di tab Network DevTools

**Clipboard tidak berfungsi**
- Jalankan via local server, bukan langsung dari `file://`

---

## Integrasi API

[![Cerebras Console](https://img.shields.io/badge/Cerebras_Console-Daftar_Sekarang-00D4AA?style=for-the-badge&logo=lightning&logoColor=white)](https://console.cerebras.ai)

| Parameter | Nilai Default |
|---|---|
| Model | `qwen-3-235b-a22b-instruct-2507` |
| Max Tokens | `20000` |
| Temperature | `0.7` |
| Top P | `0.8` |
| Timeout | `120 detik` |
| Stream | `false` |

---

## Kontribusi

```bash
git checkout -b fitur/nama-fitur
git commit -m "feat: deskripsi perubahan"
git push origin fitur/nama-fitur
# Buat Pull Request
```

Area yang bisa dikembangkan:
- Export soal ke PDF
- Simpan hasil quiz ke localStorage
- Mode timer per soal
- Dukungan gambar/diagram dalam soal
- Toggle dark/light mode

---

## Kredit

| Komponen | Sumber |
|---|---|
| AI Model | [Cerebras AI](https://cerebras.ai) |
| Math Rendering | [KaTeX](https://katex.org) oleh Khan Academy |
| Utility CSS | [Tailwind CSS](https://tailwindcss.com) |
| Font Display | [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk) |
| Font Body | [DM Sans](https://fonts.google.com/specimen/DM+Sans) |

---

## Lisensi

[![License: MIT](https://img.shields.io/badge/License-MIT-00d4aa?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](LICENSE)

MIT License — bebas digunakan, dimodifikasi, dan didistribusikan.

---

## Kontak

[![GitHub Issues](https://img.shields.io/badge/GitHub-Issues-181717?style=for-the-badge&logo=github&logoColor=white)](../../issues)
[![GitHub Discussions](https://img.shields.io/badge/GitHub-Discussions-00d4aa?style=for-the-badge&logo=github&logoColor=white)](../../discussions)

Laporkan bug atau ajukan fitur baru melalui GitHub Issues.

---

<div align="center">

*Belajar lebih mudah, mulai sekarang.*

[![GitHub stars](https://img.shields.io/github/stars/USERNAME/SeLA?style=for-the-badge&logo=github&color=00d4aa)](../../stargazers)

</div>
