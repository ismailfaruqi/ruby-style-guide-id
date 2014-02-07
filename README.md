# Pendahuluan

> Role models are important. <br/>
> -- Officer Alex J. Murphy / RoboCop

Satu hal yang selalu mengganggu pikiran saya sebagai seorang developer Ruby - 
bahwa developer Python memiliki referensi style programming yang hebat 
([PEP-8](http://www.python.org/dev/peps/pep-0008/)) dan kita tidak pernah
memiliki sebuah petunjuk resmi, yang mendokumentasikan style coding Ruby dan
best practice-nya. Dan saya percaya bahwa style itu penting. Saya juga percaya
bahwa sebuah komunitas hacker yang hebat, seperti yang dimiliki Ruby, harusnya
cukup capable untuk membuat dokumen yang didambakan ini.

Petunjuk ini memulai hidupnya sebagai sebuah petunjuk coding Ruby untuk
perusahaan kami (ditulis oleh hamba). Dalam satu waktu, saya memutuskan bahwa
karya yang sedang saya kerjakan ini mungkin menarik bagi komunitas Ruby secara umum,
dan bahwa dunia ini tidak terlalu memerlukan petunjuk internal perusahaan lainnya.
Namun dunia tentu saja bisa mendapatkan keuntungan dari sebuah kumpulan praktek,
idiom, dan rekomendasi style untuk Ruby programming yang berbasis dan didukung oleh
komunitas.

Sejak permulaan petunjuk ini, saya mendapatkan banyak feedback dari anggota-anggota
komunitas Ruby yang luar biasa di seluruh dunia. Terima kasih atas semua saran dan
dukungannya! Bersama kita bisa membuat petunjuk ini bermanfaat bagi setiap dan semua
developer Ruby di luar sana.

Ngomong-ngomong, kalau anda juga bekerja dengan Rails, mungkin guide tambahan ini akan
berguna juga untuk anda [Ruby on Rails 3 & 4 Style Guide](https://github.com/bbatsov/rails-style-guide).

# Petunjuk Style Programming Ruby

Petunjuk style Ruby ini menyarankan praktek terbaik, sehingga programmer Ruby real-world
dapat menulis kode yang dapat dipertahankan oleh programmer Ruby real-world yang lain. Sebuah
petunjuk  yang merefleksikan penggunaan di dunia nyata akan terpakai, dan sebuah
petunjuk yang memegang teguh idealisme yang tertolak oleh orang-orang yang ditujukannya
beresiko menjadi sia-sia &ndash; betapapun baiknya petunjuk itu.

Guide ini dibagi menjadi beberapa bagian dari aturan-aturan yang berhubungan. Saya telah mencoba
untuk menambahkan alasan di balik aturan-aturan tersebut (dan kalau tidak ada, saya berasumsi
bahwa alasannya cukup jelas).

Saya tidak membuat-buat aturan tersebut - aturan-aturan itu kebanyakan berdasarkan pengalaman
saya sebagai seorang software engineer profesional, masukan dan sugesti dari komunitas Ruby, atau
datang dari berbagai macam sumber-sumber programming Ruby yang sangat terkenal, seperti 
["Programming Ruby 1.9"](http://pragprog.com/book/ruby4/programming-ruby-1-9-2-0)
dan ["The Ruby Programming Language"](http://www.amazon.com/Ruby-Programming-Language-David-Flanagan/dp/0596516177).

Guide ini masih terus berlanjut - beberapa aturan masih tidak memiliki contoh-contoh, beberapa aturan lain
tidak memiliki contoh yang menggambarkan aturan tersebut dengan cukup jelas. Dalam waktu dekat, permasalahan
ini akan diatasi - cukup supaya hal tersebut diperhatikan untuk sekarang.

Anda dapat membuat versi PDF atau HTML dari petunjuk ini menggunakan [Transmuter](https://github.com/TechnoGate/transmuter).

[RuboCop](https://github.com/bbatsov/rubocop) adalah sebuah code analyzer yang berbasis petunjuk ini.

Translasi dari petunjuk ini tersedia dalam bahasa-bahasa berikut ini:

* [Chinese Simplified](https://github.com/JuanitoFatas/ruby-style-guide/blob/master/README-zhCN.md)
* [Chinese Traditional](https://github.com/JuanitoFatas/ruby-style-guide/blob/master/README-zhTW.md)
* [French](https://github.com/porecreat/ruby-style-guide/blob/master/README-frFR.md)
* [Spanish](https://github.com/alemohamad/ruby-style-guide/blob/master/README-esLA.md)
* [Vietnamese](https://github.com/scrum2b/ruby-style-guide/blob/master/README-viVN.md) 

