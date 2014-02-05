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

<!-- This Ruby style guide recommends best practices so that real-world Ruby
programmers can write code that can be maintained by other real-world Ruby
programmers. A style guide that reflects real-world usage gets used, and a
style guide that holds to an ideal that has been rejected by the people it is
supposed to help risks not getting used at all &ndash; no matter how good it is. -->

Petunjuk style Ruby ini menyarankan praktek terbaik, sehingga programmer Ruby real-world
dapat menulis kode yang dapat dipertahankan oleh programmer Ruby real-world yang lain. Sebuah
petunjuk  yang merefleksikan penggunaan di dunia nyata akan terpakai, dan sebuah
petunjuk yang memegang teguh idealisme yang tertolak oleh orang-orang yang ditujukannya
beresiko menjadi sia-sia &ndash; betapapun baiknya petunjuk itu.

<!-- The guide is separated into several sections of related rules. I've
tried to add the rationale behind the rules (if it's omitted I've
assumed it's pretty obvious). -->

Guide ini dibagi menjadi beberapa bagian dari aturan-aturan yang berhubungan. Saya telah mencoba
untuk menambahkan alasan di balik aturan-aturan tersebut (dan kalau tidak ada, saya berasumsi
bahwa alasannya cukup jelas).

<!-- I didn't come up with all the rules out of nowhere - they are mostly
based on my extensive career as a professional software engineer,
feedback and suggestions from members of the Ruby community and
various highly regarded Ruby programming resources, such as
["Programming Ruby 1.9"](http://pragprog.com/book/ruby4/programming-ruby-1-9-2-0)
and ["The Ruby Programming Language"](http://www.amazon.com/Ruby-Programming-Language-David-Flanagan/dp/0596516177). -->

Saya tidak membuat-buat aturan tersebut - aturan-aturan itu kebanyakan berdasarkan pengalaman
saya sebagai seorang software engineer profesional, masukan dan sugesti dari komunitas Ruby, atau
datang dari berbagai macam sumber-sumber programming Ruby yang sangat terkenal, seperti 
["Programming Ruby 1.9"](http://pragprog.com/book/ruby4/programming-ruby-1-9-2-0)
dan ["The Ruby Programming Language"](http://www.amazon.com/Ruby-Programming-Language-David-Flanagan/dp/0596516177).
