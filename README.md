# Portofolio Next.js

Next.js 14 (App Router), React 18, Tailwind CSS 3, dan Lucide Icons.

## Menjalankan
1. Pasang Node.js 18.17 atau lebih baru.
2. Jalankan `npm install`, lalu `npm run dev`.
3. Buka http://localhost:3000.

## Hosting
- Vercel: upload project ke GitHub, lalu import di vercel.com. Tidak perlu pengaturan tambahan.
- Hosting statis: aktifkan `output: "export"` di next.config.mjs, jalankan `npm run build`, lalu upload folder `out`.

## Struktur
```
src/
  app/
    layout.jsx          font, metadata (judul tab, deskripsi), provider
    page.jsx            merakit semua section
    globals.css         Tailwind dan animasi
  data/                 semua isi konten (edit di sini)
    profile.js  navigation.js  credentials.js  stack.js
    projects.js  highlights.js  socials.js
  sections/             Hero  Education  TechStack  Projects  Highlights  Contact
  components/
    TShape.jsx          potret animasi + bentuk T di hero
    layout/             FloatingNav, Footer
    layout/             FloatingNav, Footer
    ui/                 Glow, Chip, Section, ImageSlot, CertFrame, LinkBtn, Lightbox,
                        Reveal, Typewriter, ThemeToggle, CursorAura, AuroraBackground
  lib/theme.js          fungsi ganti tema
public/                 foto/, sertifikat/
```

File yang diawali "use client" membutuhkan interaksi di browser (hover, state, audio, form).
Sisanya dirender di server.

## Fitur tampilan
- Mode terang/gelap: tombol di navbar, tersimpan di browser, bawaan gelap. Transisi berupa lingkaran yang mengembang dari tombol.
- Aurora latar, cahaya mengikuti kursor, reveal saat scroll, teks terminal yang diketik, filter proyek (dibagi kelompok Coding dan UI/UX).
- Semua animasi mati otomatis bila perangkat memilih "reduce motion".

## Yang perlu diisi
- `src/data/projects.js`:
  - `github` untuk OpenJob (belum ada)
- `public/projects/openjob-postman.png`: screenshot hasil run Postman collection

## Aset (taruh di folder public)
- projects/openjob-postman.png (bukti Postman)
- foto/Gibranfoto.jpeg (ganti nama file di `src/data/profile.js` bila memakai foto baru; atur `photoTone` di file yang sama)
- sertifikat/dicoding.jpg, sertifikat/BNSP_SMK.jpg, sertifikat/bnsp_Sosmed.jpeg
- sertifikat/fls2n-smk-2022.jpg, sertifikat/fls2n-smp-duet-gitar.jpg (path bisa diubah di `src/data/highlights.js`)
- sertifikat/pengalaman-kerja-pengarsipan.jpg

Selama file belum ada, situs menampilkan kotak placeholder.
