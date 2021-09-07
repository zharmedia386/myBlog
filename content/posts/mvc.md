---
title: 'Mengenal MVC(Model, View, Controller)'
date: 2021-09-07
tags: ['website', 'framework']
type: post
weight: 20
---

![alt text](/images/img-1.jpg)

# Pendahuluan

Jika Anda sedang belajar coding, Anda pasti sudah tak asing dengan yang namanya framework. Saat ini hampir semua framework populer, seperti framework laravel, sudah menggunakan konsep MVC untuk pengembangan website.

MVC sendiri merupakan pola desain arsitektur website yang terbagi menjadi tiga bagian, yaitu model, view, dan controller. Konsep ini diyakini bisa mengefektifkan proses pembuatan website.

Nah, seperti apa sih penjelasan lebih detail mengenai MVC? Tenang, kami akan membahasnya di artikel ini pada bab berikutnya. Selain itu, kami juga akan membahas lengkap cara kerja, manfaat, serta beberapa contohnya. Penasaran kan? Yuk simak artikel ini sampai selesai ya.

# Pengertian MVC

MVC adalah sebuah pendekatan perangkat lunak yang memisahkan aplikasi logika dari presentasi. MVC memisahkan aplikasi berdasarkan komponen- komponen aplikasi, seperti : manipulasi data, controller, dan user interface.

1. Model, Model mewakili struktur data. Biasanya model berisi fungsi-fungsi yang membantu seseorang dalam pengelolaan basis data seperti memasukkan data ke basis data, pembaruan data dan lain-lain.
2. View, View adalah bagian yang mengatur tampilan ke pengguna. Bisa dikatakan berupa halaman web.
3. Controller, Controller merupakan bagian yang menjembatani model dan view.

# Alur Kerja MVC

![alt text](/images/img-2.png)

1. Bagian view akan merequest informasi untuk bisa ditampilkan kepada pengguna.
2. Request tersebut kemudian diambil oleh controller dan diserahkan bagian model untuk diproses;
3. Model akan mengolah dan mencari data informasi tersebut di dalam database;
   Model memberikan kembali pada controller untuk ditampilkan hasilnya di view;
4. Controller mengambil hasil olahan yang dilakukan di bagian model dan menatanya di bagian view.

# Framework yang Menggunakan Konsep MVC

Untuk framework PHP, ada cukup banyak dan hampir semuanya menggunakan konsep MVC:

- Laravel
- Symfony
- CakePHP
- Zend
- Codeigniter (versi 3 kebawah sudah tidak recommended untuk dipelajari)
- dll

Untuk framework Python di antaranya:

- Django
- Turbogears2
- Watson-Framework
- dll

Untuk framework Nodejs di antaranya:

- Express
- Adonis
- Sails.js
- Total.js
- Mean.js
- Mojito
- dll

# Referensi

- [Niagahoster](https://www.niagahoster.co.id/blog/mvc-adalah/)

- [JagoanNgoding](https://jagongoding.com/web/memahami-konsep-mvc/)

- [Medium](https://medium.com/@kevinnfa0107/pengertian-mvc-model-view-controller-pada-framework-laravel-20f261ccf233)
