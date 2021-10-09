---
title: 'Pengenalan Machine Learning'
date: 2021-10-08T17:55:28+08:00
tags: ['Data-Science', 'Machine-Learning']
type: post
weight: 20
---

![alt text](/images/img-8.jpg)

Dalam satu dekade terakhir machine learning menjelma sebagai bidang yang berkembang sangat pesat dan terus dikembangkan para ilmuwan seluruh dunia. Inilah inti dari berbagai macam produk berteknologi tinggi terkini. Perannya sangat signifikan dalam disrupsi industri 4.0 yang sarat dengan transformasi digital.

Tahukah Anda, apa itu machine learning?

“A field of study that gives computers the ability to learn without being explicitly programmed.”

--Arthur Samuel, 1959.

Istilah machine learning pertama kali dipopulerkan oleh Arthur Samuel, seorang ilmuwan komputer yang memelopori kecerdasan buatan pada tahun 1959. Menurut Arthur Samuel, machine learning adalah suatu cabang ilmu yang memberi komputer kemampuan untuk belajar tanpa diprogram secara eksplisit. Apa maksudnya?

Mari kita mundur sejenak ke masa sebelum machine learning ditemukan. Seperti dikemukakan oleh Moroney [1], prinsip atau paradigma pemrograman sejak permulaan era komputasi direpresentasikan dalam diagram berikut.

![alt text](/images/machineLearningPath/pemrogramantradisional.png)

Aturan dan data adalah masukan atau input bagi sistem. Secara eksplisit, aturan diekspresikan dalam bahasa pemrograman. Tambahan masukan berupa data kemudian akan menghasilkan solusi sebagai keluaran. Paradigma pemrograman seperti pada diagram di atas sering disebut sebagai pemrograman tradisional.

Pemrograman tradisional memiliki keterbatasan. Sifatnya rigid dengan sekumpulan aturan “if” dan “else” untuk memproses data atau menyesuaikan dengan masukan. Sebagai contoh, kita ingin membuat sebuah program untuk mendeteksi aktivitas fisik. Kita bisa menggunakan parameter “kecepatan” sebagai data untuk membedakan aktivitas satu dan lainnya.

Misal untuk aktivitas berjalan, kita membuat algoritma program dengan bahasa python sebagai berikut.

```python
if kecepatan<4:
    aktivitas=BERJALAN
```

Untuk aktivitas berlari, kecepatannya tentu menjadi lebih besar, misalnya 12 km/jam sehingga algoritmanya menjadi seperti ini.

```python
if kecepatan<4:
    aktivitas=BERJALAN
else:
    aktivitas=BERLARI
```

Jika kemudian kita ingin mendeteksi aktivitas bersepeda, algoritma program kita menjadi seperti ini:

```python
if kecepatan<4:
    aktivitas=BERJALAN
elif kecepatan<12:
    aktivitas=BERLARI
else
    aktivitas=BERSEPEDA
```

Cukup mudah, ya? Kita hanya perlu mendeteksi kecepatan seseorang untuk menentukan aktivitas yang sedang dilakukannya. Tapi bagaimana jika kita diminta untuk mendeteksi aktivitas lain seperti “bermain basket”?

Kita akan menemui masalah. Orang yang sedang bermain basket akan melakukan aktivitas berjalan, kadang berlari, sekejap berhenti, dan seterusnya. Lantas, bagaimana cara program mendeteksi aktivitas tersebut? Hal ini membuat kita menyadari bahwa pemrograman tradisional memiliki keterbatasan dalam menyelesaikan masalah.

Sampai sini jelas, ya? Agar lebih memahami, kita akan berikan satu contoh lain. Misal kita ingin mengetahui bagaimana pemrograman tradisional bekerja untuk mengenali gambar.

Pendekatan tradisional menggunakan teknik feature extraction untuk mendeteksi objek. Teknik ini merepresentasikan gambar dengan mengekstrak beberapa fitur pada gambar. Fitur adalah bagian kecil yang menarik, deskriptif, atau informatif. Ia bisa berupa sudut, tepi, skema warna, tekstur gambar, dan lain-lain. Beberapa contoh algoritma feature extraction yang sering digunakan adalah: Harris Corner Detection, Scale-Invariant Feature Transform (SIFT), Speeded-Up Robust Features (SURF), Features from Accelerated Segment Test (FAST), dan Binary Robust Independent Elementary Features (BRIEF).

S. Campbell dalam makalahnya yang berjudul Deep Learning vs, Traditional Computer Vision [2] menyebutkan bahwa fitur-fitur diekstrak dari gambar untuk membentuk definisi dari setiap objek kelas. Dalam tahap penerapan, definisi ini dicari di berbagai tempat pada gambar. Jika sejumlah fitur ditemukan pada gambar lain, gambar diklasifikasikan sebagai gambar yang mengandung objek tertentu.

Kesulitan yang muncul dari pendekatan tradisional ini adalah kita perlu memilih mana fitur yang penting di setiap gambar. Seiring dengan meningkatnya jumlah kelas yang akan diklasifikasikan, proses ekstraksi fitur menjadi semakin rumit. Proses ini sangat bergantung pada keahlian manusia untuk menilai fitur mana yang bisa mendeskripsikan kelas yang berbeda. Prosesnya cukup rumit, ya? Tapi tentu ada cara yang lebih baik.

Perkenalkan: paradigma baru pemrograman dengan machine learning!

Perhatikan diagram di bawah ini. Paradigma pemrograman pada machine learning itu berkebalikan dengan pemrograman tradisional.

![alt text](/images/machineLearningPath/MLprogramming.png)

Pada pemrograman tradisional kita merepresentasikan masalah menjadi aturan dalam bahasa pemrograman. Kini ketika hal itu tidak lagi memungkinkan, kita perlu mengubah alur berpikir kita dengan cara yang berbeda. Paradigma baru pemrograman dengan machine learning adalah kita memiliki banyak sekali data dan label bagi data tersebut. Kita juga telah mengetahui keterkaitan antara data dengan label sebagai suatu solusi.

Ilustrasinya seperti ini, ya.

![alt text](/images/machineLearningPath/MLparadigm-Page-1.jpg)

Algoritma machine learning mencari pola tertentu dari setiap kumpulan data yang menentukan kekhasan masing-masing untuk kemudian menyimpulkan sebuah aturan. Selanjutnya, aturan ini dapat digunakan untuk melakukan identifikasi dan prediksi bagi data baru yang relevan dengan model yang kita miliki. Sangat powerful dan menarik ya?

![alt text](</images/machineLearningPath/UntitledDiagram(2).png>)

Ilustrasi-ilustrasi di atas menjelaskan proses belajar pada pemrograman dengan machine learning. Lantas apa contoh sederhana dari machine learning? Filter spam pada layanan email, misalnya. Saat kita menandai satu email sebagai spam, maka program akan mempelajari anatomi email tersebut untuk mengantisipasi email-email masuk berikutnya itu spam atau bukan. Jika mirip, sebuah email baru akan masuk kategori spam, demikian juga sebaliknya.

Berikut adalah contoh email yang telah ditandai sebagai spam oleh algoritma ML dan masuk ke dalam kotak spam.

![alt text](/images/machineLearningPath/spamemail.png)

Anda tentu pernah mendapati email dalam kotak spam. Uniknya, filter email spam ini bukanlah hal yang baru, melainkan telah ada sejak tahun 1990-an saat internet tengah booming. Alhasil, hidup jutaan orang pengguna email jadi lebih mudah. Kita jadi tak perlu sering menandai sebuah email jika itu adalah spam.

Setelah fase itu mulai muncul ratusan implementasi dari ML yang kita gunakan sehari-hari saat ini. Merentang dari rekomendasi video di Youtube, fitur pengenal wajah pada gambar, kontrol suara seperti pada Google Assistant, hingga sistem pemilihan pengemudi dan rekomendasi restoran pada aplikasi ojek online. Yup, itu semua adalah bentuk implementasi dari machine learning. Ternyata dekat ya, machine learning dengan kehidupan kita sehari-hari?

Selain machine learning, Anda juga pasti pernah mendengar tentang artificial intelligence dan deep learning. Lalu, apa hubungan antara AI, ML, dan deep learning?

Machine learning adalah cabang dari artificial intelligence. Kecerdasan buatan memiliki pengertian yang sangat luas tapi secara umum dapat dipahami sebagai komputer dengan kecerdasan layaknya manusia. Sedangkan ML memiliki arti lebih spesifik yaitu menggunakan metode statistika untuk membuat komputer dapat mempelajari pola pada data tanpa perlu diprogram secara eksplisit. Lebih lanjut, deep learning adalah cabang machine learning dengan algoritma jaringan syaraf tiruan yang dapat belajar dan beradaptasi terhadap sejumlah besar data. Algoritma jaringan syaraf tiruan pada deep learning terinspirasi dari struktur otak manusia.

Jadi, ketika Anda ditanya tentang hubungan antara artificial intelligence, machine learning, dan deep learning di kemudian hari, Anda bisa menjawabnya demikian. Seperti inilah ilustrasinya dalam sebuah diagram.

![alt text](/images/machineLearningPath/20201229091743901b5459de9c688b2772d6ca69e37b31.jpg)

# Referensi

- Machine Learning Path (Dicoding Academy)
