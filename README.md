Manipulasi Citra

Abror Alfarisi Haninda

Citra digital pada dasarnya merupakan matriks dua dimensi (atau tiga dimensi untuk citra berwarna) yang
berisi nilai-nilai intensitas pixel diskret. Pengolahan citra digital memegang peranan krusial dalam
menjembatani data visual mentah agar dapat dipahami lebih optimal oleh mata manusia maupun algoritma
Computer Vision. Laporan praktikum ini mendokumentasikan serangkaian eksperimen manipulasi dasar
citra digital menggunakan bahasa pemrograman Python serta library OpenCV, NumPy, dan Matplotlib.
Fokus utama dari eksperimen ini bukan sekadar menjalankan sintaks kode, melainkan menganalisis secara
fundamental bagaimana operasi matematika sederhana—baik linear maupun non-linear—dapat
memengaruhi karakteristik visual, distribusi histogram, tingkat kecerahan (brightness), kontras (contrast),
hingga detail informasi pada citra digital. 

Saya Menggunakan Citra dari gambar yang ada di local storage saya

Teknik paling mudah dipahami: Image Negative. Alasannya karena persamaan
matematikanya bersifat pengurangan linear sederhana ($255 - I$) yang polanya
langsung dapat ditebak secara intuitif (hitam menjadi putih, putih menjadi hitam).
Teknik paling sulit dianalisis: Transformasi Gamma. Karena membutuhkan
proses pemahaman konseptual yang berlapis, mulai dari melakukan normalisasi nilai
pixel ke rentang float [0,1], memahami sifat eksponensial kurva pangkat, hingga
mengembalikannya lagi ke format asli uint8 .
Perbedaan efek Logaritmik vs Gamma: Transformasi logaritmik hanya beroperasi
satu arah untuk mencerahkan area gelap secara masif dan konstan. Sementara
transformasi gamma bersifat dinamis dan fleksibel dua arah tergantung nilai
parameternya, di mana ia bisa mencerahkan ($\gamma < 1$) maupun menggelapkan
citra ($\gamma > 1$).
Hal baru yang dipahami tentang nilai pixel: Pixel bukan sekadar representasi
warna visual di layar, melainkan sekumpulan data angka di dalam matriks yang
perilakunya dapat dimodifikasi secara akurat menggunakan hukum dan fungsi
matematika.
Teknik utama untuk aplikasi peningkatan citra: Saya akan memilih
Transformasi Gamma terlebih dahulu karena fleksibilitasnya yang tinggi dalam
menangani dua masalah pencahayaan sekaligus (under/overexposed) dalam satu
fungsi penyesuaian fungsional. 
