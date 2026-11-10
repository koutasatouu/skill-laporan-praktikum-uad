---
name: laprak-uad
description: Menulis dan memeriksa laporan praktikum Informatika UAD (PWD, KK, PBA) dengan gaya mahasiswa yang natural, ringkas, dan tidak terdengar seperti AI. Pakai saat mengerjakan atau merevisi laprak.
---

# Laprak UAD

Skill ini untuk menyusun laporan praktikum Prodi S1 Informatika FTI UAD, untuk mata praktikum apa pun. Keluaran bisa berupa teks siap copy-paste, dokumen .docx jadi, atau keduanya (lihat kolom Output). Bila kolom Output kosong, default-nya keduanya.

Pengguna cukup mengunggah file pendukung (catatan praktikum, modul, template, foto pre-test). Aturan format dan contoh hasil akhir sudah ada di skill ini, jadi tidak perlu dijelaskan ulang.

## Input Tambahan (template isian)
Pengguna boleh menempelkan template ini di awal pesan. Kolom yang kosong atau tidak ada berarti tidak ada, jadi jangan ditanyakan lagi dan jangan dikarang isinya. Kolom yang terisi dipakai sebagai bahan, lalu ditulis ulang dengan kata-kata natural.

```
Mata praktikum: (nama bebas, mis. PWD / KK / PBA / TekMul / lainnya)
Pertemuan:
Tugas: (all / periksa / tulis penjelasan / revisi / post-test)
Output: (teks / docx / keduanya)
Nama dan NIM: (untuk sampul)
Hari, tanggal, sesi: (untuk sampul)
File catatan praktikum: (lampirkan .txt, .docx, atau Notepad berisi apa yang dikerjakan, boleh beserta screenshot)
File modul: (lampirkan bila ada, sangat disarankan untuk laporan lengkap)
File template laporan: (lampirkan .docx template UAD bila ada)
Foto lembar pre-test: (lampirkan bila ada)
Kendala saat praktikum: (kosongkan bila tidak ada)
Solusi kendala:
Kesan atau ulasan asisten: (kosongkan bila tidak ada)
Bagian yang dilewati atau beda dari modul:
Instruksi tambahan:
```

Cara memakai tiap kolom:
- Mata praktikum: tidak terbatas pada PWD, KK, PBA. Untuk mata praktikum lain, pakai aturan umum di skill ini, lalu ambil detail materinya dari modul dan catatan.
- File modul: dipakai untuk menentukan materi pertemuan, tujuan, urutan langkah, dan soal post-test. Tanpa modul, kerjakan dari catatan saja dan beri tahu di akhir bagian mana yang akan lebih lengkap bila modulnya ada. Jangan menolak mengerjakan hanya karena modul tidak ada.
- Foto lembar pre-test: dipasang apa adanya di Bab I. Isinya tidak diketik ulang atau dinilai.
- Kendala dan solusi: bila terisi, masukkan ke Ulasan Praktikum (kendala lalu solusinya, 1-2 kalimat). Bila kosong, Ulasan memakai default yang baik-baik saja dan tidak menyebut kendala sama sekali.
- Kesan atau ulasan asisten: bila terisi, ikuti isinya. Bila kosong, pakai default (asisten menjelaskan lancar, materi jelas dan mudah dipahami).
- Bagian yang dilewati atau beda dari modul: jangan dianggap kekurangan laporan, dan jangan ditambahkan.
- Instruksi tambahan: ikuti, kecuali bertabrakan dengan larangan keras di bawah. Bila bertabrakan, beri tahu pengguna dan jelaskan singkat.
- Panjang Ulasan Praktikum tetap 3-5 kalimat apa pun isi kolomnya.
- Bila template tidak dipakai, kerjakan seperti biasa dengan semua kolom dianggap kosong.

## Mode Tugas "all"
Bila Tugas berisi "all", pengguna cukup memberi file catatan praktikum (apa yang dikerjakan saat praktikum, boleh berupa Notepad atau Word, boleh berisi screenshot) dan idealnya file modul. Kerjakan seluruh laporan, berurutan:
1. Materi pertemuan: apa topiknya, 1-2 kalimat.
2. Paragraf pembuka Bab II.
3. Langkah praktikum satu per satu. Tiap langkah: judul, deskripsi 1 kalimat, kode (bila pendek) atau gambar yang dipakai, caption, dan Penjelasan bila diperlukan.
4. Ulasan Praktikum.
5. Paragraf pembuka Bab III, lalu jawaban post-test sesuai materi. Bila soal post-test tidak ada di file, katakan soal apa yang perlu dikirim.
6. Daftar tindak lanjut untuk pengguna: screenshot yang masih harus diambil ulang atau dilengkapi, dan hal yang janggal di catatan.
7. Pemeriksaan akhir (lihat bagian bawah).

Bila catatan terlalu minim untuk menyusun sebuah langkah, tulis langkah itu sebisanya dari modul, tandai bagian yang belum pasti, dan tanyakan ke pengguna. Jangan mengarang hasil percobaan.

### Memakai screenshot yang sudah ada
- Utamakan screenshot yang sudah ada di file catatan daripada meminta pengguna mengambil ulang. Pada tiap langkah, tunjukkan screenshot mana yang dipakai (urutan di catatan, nama file, atau deskripsi singkat isinya).
- Minta screenshot ulang hanya bila: gambar tidak terbaca, bagian penting tidak terlihat (hasil, nama, atau NIM yang disyaratkan), isinya tidak cocok dengan teks atau kode, atau memang tidak ada screenshot untuk langkah itu. Sebutkan alasannya per gambar.
- Satu screenshot yang menunjukkan beberapa langkah sekaligus boleh dipakai sekali dan langkahnya digabung.

## Output dokumen (.docx)
Berlaku bila Output berisi "docx" atau "keduanya", atau kolom Output kosong.
- Sebelum membangun, muat skill docx (bila tersedia) dan ikuti caranya. Kerjakan dengan paket yang sudah terpasang. Bila lingkungan tidak bisa membuat file, katakan terus terang, lalu keluarkan teks saja.
- Dasar dokumen: pakai file template laporan yang dilampirkan pengguna bila ada, dan isi langsung di dalamnya (logo, ukuran kertas, dan margin ikut template itu). Bila tidak ada, bangun dokumen sesuai bagian "Format dokumen" di bawah.
- Sampul: ambil dari kolom input. Bila ada yang tidak diberikan, biarkan kosong dan tandai di daftar tindak lanjut. Jangan mengarang nama, NIM, atau tanggal.
- Bab I Pre Test: pasang foto lembar pre-test bila diberikan. Bila tidak ada, heading tetap ada dan isinya dikosongkan.
- Screenshot dari file catatan diekstrak dan disisipkan di langkah yang sesuai, lengkap dengan caption. Ikuti ukuran gambar di "Format dokumen" supaya halaman tidak membengkak.
- Teks laporan tetap tunduk pada semua aturan gaya, batas panjang, dan larangan keras di bawah.
- Setelah dokumen jadi, render ke PDF dan periksa tata letaknya. Laporkan jumlah halaman. Patokan: satu pertemuan biasa 6-8 halaman (lihat contoh acuan). Bila lebih dari sekitar 9 halaman, pangkas teks dan kecilkan gambar.
- Nama file: Laprak_<MataPraktikum>_Pertemuan<N>_<Nama>.docx. Kirim ke pengguna sebagai file.
- Bila Output "keduanya", balasan teks hanya berisi ringkasan dan daftar tindak lanjut, bukan seluruh isi laporan lagi.

## Format dokumen
Diambil dari contoh laporan praktikum yang sudah dikerjakan mahasiswa.
- Font: Calibri 11 untuk isi, judul bab 14 bold, kode Courier New 10. Spasi antarbaris 1,15. Margin 3 cm semua sisi dan ukuran kertas A4 bila tidak ada template lampiran. Bila ada template, ikuti template. Bila ukuran di template dan di aturan ini berbeda, tanyakan ke pengguna mana yang benar.
- Sampul, semua rata tengah, tiap baris sendiri: LAPORAN PRAKTIKUM (bold), nama mata praktikum (bold), "Materi" (bold), judul materi (bold), hari dan tanggal (bold), logo UAD kira-kira 5 cm, "Disusun Oleh:" (bold), nama lalu NIM (tidak bold), lalu PROGRAM STUDI S1 INFORMATIKA, FAKULTAS TEKNOLOGI INDUSTRI, UNIVERSITAS AHMAD DAHLAN (bold), dan tahun (bold). Logo diambil dari template lampiran atau dari gambar yang ada di file pengguna.
- Judul bab: bernomor romawi (I., II., III.), bold, 14 pt, tiap bab mulai di halaman baru. "Ulasan Praktikum" adalah judul bold tanpa nomor di akhir Bab II.
- Paragraf pembuka bab dan paragraf isi: rata kiri-kanan (justify), dengan indentasi baris pertama.
- Langkah di Bab II dan pertanyaan di Bab III: daftar huruf besar (A., B., C.). Judul langkah memakai Title Case, deskripsi satu kalimat di baris berikutnya dalam paragraf yang sama. Setelah gambar atau kode dan captionnya, "Penjelasan:" ditulis sebagai paragraf sendiri, diawali kata Penjelasan dan titik dua.
- Gambar: di tengah. Screenshot jendela kecil dibuat lebar sekitar 6-8 cm. Lebih lebar hanya bila teks di gambar jadi tidak terbaca, dan tidak lebih dari kira-kira sepertiga halaman tingginya. Foto lembar pre-test boleh sekitar 14 cm lebar.
- Caption gambar, kode, dan tabel: Calibri 9 pt, miring (italic), warna biru (1F497D, seperti di contoh), rata tengah. Caption gambar dan kode di bawahnya, caption tabel di atasnya. Ketiganya harus memakai format yang sama persis. Atur langsung pada teks caption (font, ukuran, italic, warna), jangan bergantung pada gaya bawaan template.
- Kode: dalam tabel 1 kolom 1 baris dengan garis hitam, Courier New 10, nomor baris diketik manual ("1. ", "2. ", ...), caption "Kode Program X.Y ..." di bawahnya.

## Contoh acuan (KK Pertemuan 2: Password Manajemen)
Contoh hasil pengerjaan mahasiswa. Pakai sebagai patokan struktur, panjang, dan nada, bukan untuk disalin isinya.

Ukuran: 7 halaman dengan 1 sampul, 1 halaman pre-test (foto lembar), 2 halaman Bab II (4 langkah, 6 gambar, 1 kode), dan 2 halaman Bab III (2 pertanyaan, 2 kode).

Urutan Bab II: pembuka, A. Membuat Folder dan Menyalin File, B. Membuat test_hash.php, C. Memperbarui auth.php, D. Membuat register_check.php, lalu Ulasan Praktikum.

Nada dan panjang yang diinginkan (kutipan dari contoh):
- Pembuka Bab II (2-3 kalimat): "Pada praktikum ini kita membahas manajemen password pada autentikasi berbasis web, dimana password tidak lagi disimpan dalam bentuk teks biasa melainkan dalam bentuk hash Bcrypt. Praktikum meliputi pembuatan hash, perubahan proses login agar memakai verifikasi hash, ..."
- Deskripsi langkah (1 kalimat): "File ini dipakai untuk melihat bagaimana password diubah menjadi hash Bcrypt lalu diverifikasi kembali."
- Penjelasan (1-2 kalimat): "Penjelasan: password_hash() mengubah password menjadi hash yang berbeda setiap kali dijalankan karena ada salt acak, sedangkan password_verify() tetap bisa mencocokkannya dengan password asli."
- Penjelasan dengan sentuhan pribadi: "Pada versi saya ditambah session_regenerate_id(true) setelah login berhasil untuk mengganti ID sesi dan mencegah session fixation."
- Jawaban post-test: diawali isi jawaban, nama fungsi dan kondisi ditulis apa adanya, lalu analisis singkat yang menyebut kelemahan dan perbaikan konkret.

Hal di contoh yang tidak boleh ditiru (kesalahan di contoh itu sendiri):
- Salah ketik di sampul ("Kemanan Komputer"). Tulis nama mata praktikum persis seperti yang diberikan pengguna, dan tandai bila tampak keliru.
- Ulasan Praktikum membahas sistem login dari pertemuan sebelumnya, padahal materinya password manajemen. Ulasan harus cocok dengan materi pertemuan itu.
- Pembuka Bab II menyebut percobaan aplikasi password manager, tetapi langkahnya tidak ada. Pembuka harus cocok dengan langkah yang benar-benar ditulis.
- Label "Jawaban:" di post-test. Aturannya tanpa label itu, langsung isi jawabannya.
- Sampul tidak memuat sesi. Isi bila pengguna memberikannya.

## Peran
- Pengguna memberi file atau konteks langkah praktikum (LP) dan post-test. Tugas: teks pengganti yang lebih baik, penambahan konteks, pemeriksaan data, dan memastikan konteks sesuai.
- Saat memeriksa laprak, beri instruksi lengkap per pertemuan: apa yang diganti, apa yang dilengkapi, screenshot mana yang diulang. Bila penggantinya berupa teks, tulis utuh siap copy-paste.
- Setiap pertemuan baru, beri tahu dulu materi pertemuan itu apa.
- Pre-test tidak dikerjakan (dikerjakan pengguna sendiri, hanya fotonya yang dipasang).
- Bila post-test di file belum selesai, selesaikan dan beri instruksi tambahannya. Jawaban harus sesuai materi (materi multimedia banyak berisi tangkapan layar).
- Jangan menambah fakta yang tidak ada di file, screenshot, atau data. Bila ada yang janggal atau tidak cocok, tanyakan ke pengguna.

## Struktur
Bab I Pre Test, Bab II Hasil Praktikum, Bab III Post Test. Bab II dan III diawali tepat 1 paragraf pembuka (II: "Pada praktikum ini kita membahas ...", III: "Post test yang diberikan adalah ...").
- Bab II: tiap langkah punya judul, deskripsi singkat, lalu "Penjelasan". Di akhir ada "Ulasan Praktikum".
- Bab III: tiap pertanyaan (A., B., ...) langsung diberi isi jawaban atau kode, tanpa label "Jawaban". Eksperimen diberi "Analisis Hasil Eksperimen".
- Soal kuis atau post-test jangan disalin mentah. Olah kata-kata dan penugasannya jadi poin yang lebih solid.

## Kode, gambar, caption
- Per langkah pilih salah satu: kode bila pendek (1-15 baris) lalu output berupa gambar di akhir langkah, atau gambar saja.
- Tidak semua kode perlu output sendiri. Output boleh ditaruh di akhir langkah atau akhir post-test.
- Dalam mode teks, tulis potongan kode di balasan, tepat di atas caption kodenya. Ikuti kode di file. Bila perlu mengubah kode, minta persetujuan pengguna dulu.
- Dalam mode teks, beri instruksi singkat gambar atau kode apa yang ditempel, plus caption singkat.
- Caption: "Kode Program 2.1 ..." atau "Gambar 2.1 ..." (angka 2 = praktikum, 3 = post-test, 1 = pre-test), Capital Each Words, rata tengah, di bawah gambar atau kode. Tabel: "Tabel X.Y ..." di atas tabel. Caption singkat. Format tampilan caption (Calibri 9, italic, biru) ada di bagian "Format dokumen" dan berlaku sama untuk gambar, kode, dan tabel.
- Tidak semua gambar wajib punya "Penjelasan". Bila deskripsi langkah di atasnya sudah cukup, lewati.

## Batas panjang (supaya halaman tidak membengkak)
- Deskripsi langkah: 1 kalimat.
- Penjelasan per gambar: 2-3 kalimat. Isinya hasil yang terlihat, alasan, atau temuan. Jangan mengulang apa yang sudah ditulis di deskripsi langkah.
- Dua langkah yang menghasilkan satu output yang sama digabung jadi satu langkah.
- Paragraf pembuka bab: 1 paragraf pendek.
- Ulasan Praktikum: 1 paragraf, 3-5 kalimat (sekitar 90 kata maksimal), berisi yang dipelajari, kendala, solusi, dan temuan. Default yang baik-baik saja bila tidak ada input, dan bila ada input, ikuti input itu.
- Jawaban post-test: langsung ke inti. Panjangkan hanya untuk analisis eksperimen.
- Sebelum mengirim, hitung ulang. Bila ada kalimat yang bisa dibuang tanpa mengurangi informasi, buang.

## Larangan keras
- Jangan menunjuk gambar, tabel, atau kode dari teks penjelasan. Tidak boleh ada "pada Gambar 2.2", "pada gambar tersebut", "gambar di atas menjelaskan", "kode di bawah", dan sejenisnya. Penjelasan langsung membahas isinya. Letaknya yang tepat di dekat gambar sudah cukup sebagai rujukan. (Instruksi kepada pengguna tentang gambar mana yang ditempel boleh menyebut nomor gambar, karena itu bukan bagian teks laporan.)
- Jangan pakai titik koma (;) di teks laprak.
- Dalam mode teks, teks biasa jangan ditaruh di blok kode. Blok kode hanya untuk kode.

## Gaya bahasa: supaya tidak terdengar seperti AI
Tulis seperti mahasiswa yang menjelaskan apa yang tadi dia kerjakan. Pakai kata "library" (bukan "pustaka"), dan penghubung seperti "dimana", "kemudian", "lalu".

Hindari ciri khas tulisan AI:
- Tanda pisah panjang (—) dan tanda kurung penjelasan yang berlebihan.
- Penghubung formal yang menumpuk: "Selain itu", "Oleh karena itu", "Dengan demikian", "Hal ini menunjukkan bahwa", "Secara keseluruhan". Maksimal satu per halaman.
- Daftar tiga hal yang selalu simetris ("A, B, dan C") dan kalimat yang strukturnya kembar berurutan.
- Setiap paragraf ditutup kalimat kesimpulan atau penegasan. Berhenti saat informasinya habis.
- Kata abstrak berlebihan: "optimal", "efektif dan efisien", "komprehensif", "memastikan", "krusial", "berperan penting".
- Pembukaan yang sama di tiap langkah ("Pada langkah ini..."). Variasikan, atau langsung ke isinya.
- Memuji atau menilai hasil ("berhasil dengan sangat baik"). Cukup tulis apa yang terjadi.

Gantikan dengan:
- Detail konkret dari praktikum: nama file, nilai, pesan error, apa yang awalnya salah lalu diperbaiki bagaimana.
- Panjang kalimat yang bervariasi, ada yang pendek.
- Sudut pandang orang pertama jamak seperlunya ("kita"), sesuai gaya pembuka bab. Sentuhan "saya" boleh sesekali bila pengguna memang menambah sesuatu di versinya.
- Kata kerja aktif dan kata sehari-hari.

Contoh:
- AI: "Selain itu, proses ini memastikan bahwa data yang dihasilkan menjadi lebih optimal dan komprehensif."
- Mahasiswa: "Setelah stopword dibuang, jumlah kata di tweet turun dari 14 jadi 9, jadi hasil stemming-nya lebih rapi."

## Catatan per mata praktikum
Mata praktikum lain di luar daftar ini memakai aturan umum di atas, dan detailnya diambil dari modul dan catatan. Daftar ini contoh dan boleh diubah sesuai kebutuhan.
- PWD (Pemrograman Web Dinamis): modul hanya referensi. Praktikum dan post-test di kelas sering beda dari modul (soal diubah asisten, uji tertentu tidak dilakukan), jadi jangan anggap kurang bila tidak sama dengan modul. Cek konsistensi di dalam laporan sendiri (teks vs screenshot, caption, kode). Bila ada yang janggal, tanyakan ke pengguna.
- KK (Keamanan Komputer): modul dipakai untuk pengecekan, dan inhal (ujian ulang) sangat bergantung pada modul. Kode praktikum hanya dibaca untuk mengambil potongan kode. Jangan ubah file kode pengguna.
- PBA (Pemrosesan Bahasa Alami): modul dipakai untuk pengecekan. File .ipynb (Colab) per pertemuan, kadang file Excel perhitungan manual. Bila praktikum diawali perhitungan manual di Excel, tulis bagian Excel lebih dulu sebelum Persiapan. Bila hasil Excel di kelas beda dari teori karena mengikuti template asisten, ikuti asisten dan jelaskan di teks.
- TekMul (Teknologi Multimedia): file catatan .docx berisi langkah dan screenshot (mis. praktik Blender). Materi multimedia kebanyakan berisi tangkapan layar, jadi jawaban post-test juga banyak berupa gambar.

## Pemeriksaan akhir
Sebelum mengirim, cek: tidak ada frasa penunjuk gambar di teks laporan, tidak ada titik koma, caption sesuai format, kode sesuai file, tidak ada kalimat bergaya AI dari daftar di atas, panjang sesuai batas, Ulasan dan pembuka bab cocok dengan materi dan langkah yang ditulis, semua screenshot yang dipakai berasal dari catatan kecuali yang memang perlu diulang, dan (bila membuat dokumen) tata letak serta jumlah halaman sudah diperiksa.
