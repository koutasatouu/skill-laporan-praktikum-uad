# Skill Laporan Praktikum UAD

Skill untuk asisten AI yang membantu menyusun, memeriksa, dan merevisi laporan praktikum Prodi S1 Informatika FTI Universitas Ahmad Dahlan. Skill ini berisi satu file instruksi (`SKILL.md`) yang dibaca oleh AI, jadi bisa dipakai di Claude, ChatGPT, Gemini, dan asisten lain yang bisa menerima instruksi tertulis.

Tujuannya sederhana: kamu menyerahkan catatan praktikum, dan AI menyusun laporan dengan format template UAD, bahasa yang terdengar seperti mahasiswa (bukan seperti AI), dan jumlah halaman yang tidak membengkak.

## Isi

- [Fitur](#fitur)
- [Cara pasang](#cara-pasang)
- [Cara pakai](#cara-pakai)
- [Template isian](#template-isian)
- [Aturan yang ditegakkan skill](#aturan-yang-ditegakkan-skill)
- [Batasan](#batasan)
- [Kustomisasi](#kustomisasi)
- [Struktur repo](#struktur-repo)
- [Catatan penggunaan](#catatan-penggunaan)
- [Lisensi](#lisensi)

## Fitur

- Mode `all`: dari satu file catatan praktikum, skill menyusun seluruh laporan, mulai dari materi, langkah praktikum, ulasan, sampai jawaban post-test, lalu menutup dengan daftar tindak lanjut.
- Tiga jenis keluaran: teks siap copy-paste, dokumen `.docx`, atau keduanya.
- Memakai screenshot yang sudah ada di catatanmu. Pengambilan ulang hanya diminta bila gambar tidak terbaca, tidak cocok dengan teks, atau memang tidak ada.
- Gaya tulis anti-AI: ada daftar konkret ciri tulisan AI yang harus dihindari (penghubung formal yang menumpuk, daftar tiga hal yang simetris, paragraf yang selalu ditutup kesimpulan, kata abstrak berlebihan, tanda pisah panjang) dan pengganti yang dianjurkan.
- Kontrol panjang halaman: batas kalimat per bagian, aturan menggabung langkah, dan ukuran gambar supaya satu pertemuan tetap sekitar 6 sampai 8 halaman.
- Format dokumen yang rinci: sampul, judul bab romawi, daftar huruf untuk langkah, caption (Calibri 9, italic, biru), kode dalam frame bernomor baris.
- Template isian yang bisa ditempel di awal pesan. Kolom yang kosong dilewati, tidak ditanyakan, dan tidak dikarang.
- Contoh acuan dari laporan nyata beserta daftar kesalahan di contoh itu yang tidak boleh ditiru.
- Berlaku untuk mata praktikum apa pun. PWD, KK, PBA, dan TekMul sudah punya catatan khusus.
- Pemeriksaan akhir: frasa penunjuk gambar, titik koma, format caption, kecocokan ulasan dengan materi, dan jumlah halaman.

## Cara pasang

Pilih sesuai asisten AI yang kamu pakai. Menu dan lokasi folder tiap aplikasi bisa berubah, jadi bila ada yang berbeda, cek dokumentasi resmi aplikasinya.

### Claude (claude.ai, aplikasi desktop, dan aplikasi mobile)

Cara A, sebagai skill:
1. Unduh repo ini lewat tombol Code, lalu Download ZIP.
2. Buka pengaturan Claude, cari bagian Skills (biasanya di Settings, Capabilities), lalu unggah ZIP-nya.
3. Bila unggahan ditolak, buat ZIP sendiri yang berisi satu folder bernama `laprak-uad` dengan `SKILL.md` di dalamnya, lalu unggah ZIP itu.
4. Aktifkan skill `laprak-uad`, lalu mulai chat baru.

Cara B, lewat Project (tanpa fitur skill):
1. Buat Project baru.
2. Unggah `SKILL.md` ke Project Knowledge, dan unggah template laporan `.docx` UAD bila punya.
3. Di custom instructions Project, tulis: "Ikuti SKILL.md sebagai standar menulis laporan praktikum."

### Claude Code

```bash
git clone https://github.com/koutasatouu/skill-laporan-praktikum-uad ~/.claude/skills/laprak-uad
```

Untuk satu proyek saja, clone ke `.claude/skills/laprak-uad` di folder proyek. Mulai sesi baru supaya skill terbaca.

### ChatGPT

Cara A, Custom GPT:
1. Buat GPT baru.
2. Di bagian Knowledge, unggah `SKILL.md` dan template `.docx` UAD bila ada.
3. Di Instructions, tulis: "Ikuti SKILL.md sebagai standar menulis laporan praktikum. Baca seluruh isinya sebelum menjawab."
4. Aktifkan Code Interpreter bila kamu ingin keluaran `.docx`.

Cara B, Project:
1. Buat Project, unggah `SKILL.md` ke file project, dan tambahkan instruksi yang sama seperti di atas.

Cara C, tanpa pengaturan apa pun: buka chat baru, lampirkan `SKILL.md`, lalu kirim "Ikuti SKILL.md ini untuk semua pekerjaan di chat ini." Cara ini paling cepat, tetapi harus diulang di tiap chat.

### Gemini

1. Buat Gem baru.
2. Salin seluruh isi `SKILL.md` ke kolom instruksi, atau unggah sebagai file pengetahuan bila tersedia.
3. Pakai Gem itu untuk mengerjakan laporan.

### Asisten lain berbasis chat (Perplexity, Copilot, DeepSeek, Grok, dan sejenisnya)

Lampirkan `SKILL.md` di awal chat, atau tempel isinya ke kolom instruksi khusus (custom instructions, space, atau sejenisnya) bila ada. Lalu kirim: "Ikuti SKILL.md ini untuk semua pekerjaan di chat ini."

### Asisten coding di editor atau terminal

Prinsipnya sama: taruh isi `SKILL.md` di file aturan yang dibaca asisten itu, atau rujuk file-nya.

| Alat | Cara |
| --- | --- |
| Cursor | Salin ke `.cursor/rules/laprak-uad.mdc`, atau rujuk dari `AGENTS.md` |
| Windsurf | Salin ke `.windsurf/rules/` |
| Cline atau Roo Code | Salin ke `.clinerules/` atau `.roo/rules/` |
| GitHub Copilot | Tambahkan ke `.github/copilot-instructions.md` |
| Codex CLI dan agen lain yang membaca `AGENTS.md` | Tambahkan isinya ke `AGENTS.md`, atau tulis "baca SKILL.md" di sana |
| Aider | `aider --read SKILL.md` |

### Catatan untuk keluaran .docx

Pembuatan dokumen `.docx` hanya berjalan bila asisten yang kamu pakai bisa membuat atau menjalankan file (misalnya Claude dengan fitur file, ChatGPT dengan Code Interpreter, atau asisten coding). Di asisten yang tidak bisa, isi kolom `Output: teks` supaya kamu menerima teks yang tinggal ditempel ke template.

## Cara pakai

1. Siapkan file pendukung:
   - Catatan praktikum: file Notepad atau Word berisi apa yang kamu kerjakan saat praktikum. Sertakan screenshot di dalamnya bila ada.
   - Modul praktikum (sangat disarankan, supaya materi dan soal post-test lebih tepat).
   - Template laporan `.docx` UAD, bila kamu ingin hasilnya langsung memakai template itu.
   - Foto lembar pre-test, bila ada.
2. Buka chat baru di asisten yang sudah dipasangi skill.
3. Tempel [template isian](#template-isian) di awal pesan dan isi seperlunya.
4. Lampirkan file dari langkah 1, lalu kirim.
5. Baca balasannya. Bagian paling penting adalah daftar tindak lanjut di akhir: screenshot yang perlu diulang dan hal yang janggal di catatanmu.
6. Minta revisi lewat chat yang sama. Contoh: "ringkas bagian langkah 3", "ulasan tambahkan kendala koneksi database", atau "periksa konsistensi caption".
7. Buka dokumen hasilnya dan cek sendiri sebelum dikumpulkan. Skill ini membantu menulis dan merapikan, tetapi kamu yang bertanggung jawab atas isi laporanmu.

Versi paling singkat:

```
Mata praktikum: PBA
Pertemuan: 5
Tugas: all
```

Lalu lampirkan catatan dan modul.

## Template isian

Tempel di awal pesan. Kolom yang kosong dianggap tidak ada.

```
Mata praktikum: (nama bebas, mis. PWD / KK / PBA / TekMul / lainnya)
Pertemuan:
Tugas: (all / periksa / tulis penjelasan / revisi / post-test)
Output: (teks / docx / keduanya)
Nama dan NIM: (untuk sampul)
Hari, tanggal, sesi: (untuk sampul)
File catatan praktikum: (lampirkan)
File modul: (lampirkan bila ada)
File template laporan: (lampirkan .docx template UAD bila ada)
Foto lembar pre-test: (lampirkan bila ada)
Kendala saat praktikum: (kosongkan bila tidak ada)
Solusi kendala:
Kesan atau ulasan asisten: (kosongkan bila tidak ada)
Bagian yang dilewati atau beda dari modul:
Instruksi tambahan:
```

Arti kolom yang tidak jelas dengan sendirinya:

| Kolom | Perilaku |
| --- | --- |
| Tugas: all | Mengerjakan seluruh laporan sekaligus, ditutup daftar tindak lanjut |
| Output kosong | Dianggap `keduanya` (teks dan dokumen) |
| Kendala kosong | Ulasan Praktikum memakai default yang baik-baik saja, tanpa menyebut kendala |
| Kesan asisten kosong | Default: asisten menjelaskan lancar dan materi mudah dipahami |
| Bagian yang dilewati | Tidak dianggap kekurangan laporan dan tidak ditambahkan |
| Nama, NIM, atau tanggal kosong | Dibiarkan kosong dan ditandai di daftar tindak lanjut, tidak dikarang |

## Aturan yang ditegakkan skill

| Aturan | Isi singkat |
| --- | --- |
| Tanpa frasa penunjuk gambar | Teks penjelasan tidak boleh memakai "pada Gambar 2.2", "pada gambar tersebut", dan sejenisnya |
| Tanpa titik koma | Tanda titik koma tidak dipakai di teks laporan |
| Ulasan Praktikum | Satu paragraf, 3 sampai 5 kalimat |
| Deskripsi langkah | Satu kalimat |
| Penjelasan per gambar | Dua sampai tiga kalimat, tidak mengulang deskripsi |
| Caption | Gambar, kode, dan tabel: Calibri 9, italic, biru, rata tengah. Gambar dan kode di bawah, tabel di atas |
| Kode | Frame bernomor baris, Courier New 10, dipakai bila pendek (sampai sekitar 15 baris) |
| Post-test | Soal diolah, tidak disalin mentah, dan jawaban tanpa label "Jawaban" |
| Tidak mengarang | Hasil percobaan yang tidak ada di catatan ditandai dan ditanyakan, tidak diisi sembarang |
| Pre-test | Tidak dikerjakan. Hanya foto lembarnya yang dipasang di Bab I |

## Batasan

- Skill tidak mengerjakan pre-test.
- Skill tidak bisa mengarang hasil percobaan. Kalau catatanmu terlalu minim untuk sebuah langkah, bagian itu ditandai dan kamu ditanya.
- Ukuran kertas dan margin mengikuti template yang kamu lampirkan. Tanpa template, dipakai margin 3 cm dan kertas A4. Bila template resmi di kelasmu berbeda, lampirkan template itu.
- Keluaran `.docx` bergantung pada kemampuan asisten yang dipakai (lihat catatan di bagian pasang).
- Instruksi memakai bahasa Indonesia, jadi paling cocok untuk laporan berbahasa Indonesia.

## Kustomisasi

Semua perilaku ada di `SKILL.md`, jadi kamu bisa mengubahnya sendiri:

- Catatan per mata praktikum: tambah atau ubah bagian "Catatan per mata praktikum" untuk mata praktikum dan dosen yang berbeda.
- Gaya bahasa: ubah daftar kata yang dihindari dan kata favorit di bagian "Gaya bahasa".
- Panjang halaman: ubah angka di bagian "Batas panjang".
- Format dokumen: ubah font, ukuran, dan caption di bagian "Format dokumen".
- Contoh acuan: ganti dengan laporan terbaikmu supaya nada tulisannya mengikuti gayamu sendiri.

## Struktur repo

```
.
├── SKILL.md    Instruksi lengkap yang dibaca AI
├── README.md   Dokumen ini
└── LICENSE     Lisensi MIT
```

## Catatan penggunaan

Skill ini dibuat untuk membantu menulis dan merapikan laporan dari praktikum yang benar-benar kamu kerjakan. Isi laporan harus mencerminkan pekerjaanmu, dan peraturan praktikum di kampusmu tetap berlaku. Contoh acuan di `SKILL.md` adalah patokan struktur dan nada, bukan untuk disalin.

Masukan dan perbaikan dipersilakan lewat issue atau pull request.

## Lisensi

Dirilis dengan lisensi MIT. Lihat berkas [LICENSE](LICENSE).
