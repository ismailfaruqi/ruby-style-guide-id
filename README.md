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

## Daftar Isi

* [Layout Source Code](#source-code-layout)
* [Syntax](#syntax)
* [Penamaan](#naming)
* [Komentar](#comments)
    * [Anotasi Komentar](#comment-annotations)
* [Kelas](#classes--modules)
* [Eksepsi](#exceptions)
* [Koleksi](#collections)
* [String](#strings)
* [Ekspresi Regular](#regular-expressions)
* [Literal Persen](#percent-literals)
* [Metaprogramming](#metaprogramming)
* [Lain-lain](#misc)
* [Tools](#tools)

## Layout Source Code

> Nearly everybody is convinced that every style but their own is
> ugly and unreadable. Leave out the "but their own" and they're
> probably right... <br/>
> -- Jerry Coffin (on indentation)

* Gunakan `UTF-8` sebagai encoding dari file source code.
* Gunakan dua **spasi** per level indentasi (alias soft tab). Jangan gunakan hard tab.

    ```Ruby
    # buruk - empat spasi
    def some_method
        do_something
    end

    # baik
    def some_method
      do_something
    end
    ```
* Use Unix-style line endings. (*BSD/Solaris/Linux/OS X users are covered by default,
  Windows users have to be extra careful.)
    * If you're using Git you might want to add the following
    configuration setting to protect your project from Windows line
    endings creeping in:

    ```bash
    $ git config --global core.autocrlf true
    ```

* Gunakan akhiran baris Unix-style. (*pengguna BSD/Solaris/Linux/OS X telah tersetting secara default,
  pengguna Windows harus ekstra hati-hati.)
    * Kalau anda menggunakan Git, anda mungkin perlu menambahkan setting konfigurasi
    berikut untuk melindungi project anda supaya tidak tersisipi oleh akhiran baris Windows:

    ```bash
    $ git config --global core.autocrlf true
    ```

* Jangan gunakan `;` untuk memisahkan statement and ekspresi. akibatnya - gunakan satu baris per ekspresi.

    ```Ruby
    # buruk
    puts 'foobar'; # titik koma yang mubazir

    puts 'foo'; puts 'bar' # dua ekspresi dalam satu baris

    # baik
    puts 'foobar'

    puts 'foo'
    puts 'bar'

    puts 'foo', 'bar' # ini khususnya berlaku untuk puts
    ```
* Gunakan format single-line untuk definisi kelas tanpa body.

    ```Ruby
    # buruk
    class FooError < StandardError
    end

    # baik
    class FooError < StandardError; end

    # baik
    FooError = Class.new(StandardError)
    ```

* Hindari method single-line. Meski hal tersebut agak populer di luar sana,
  ada beberapa keganjilan mengenai definisi syntax-nya yang menyebabkan 
  penggunaannya tidak diajurkan. Pokoknya - seharusnya tidak boleh ada
  lebih dari satu ekspresi dalam sebuah method single-line.

    ```Ruby
    # buruk
    def too_much; something; something_else; end

    # lumayan - perhatikan bahwa tanda ; yang pertama diperlukan
    def no_braces_method; body end

    # lumayan - perhatikan bahwa tanda ; yang kedua opsional
    def no_braces_method; body; end

    # lumayan - sintaks-nya valid, tapi dengan tidak adanya tanda ; menyebabkan sulit dibaca
    def some_method() body end

    # baik
    def some_method
      body
    end
    ```

    Satu pengecualian terhadap rule ini adalah method tanpa body.

    ```Ruby
    # baik
    def no_op; end
    ```

* Gunakan spasi di antara operator, sesudah tanda koma, titik, dan titik koma, di sekitar `{`
  dan sebelum `}`. Whitespace mungkin (kebanyakan) tidak relevan bagi interpreter Ruby,
  tapi penggunaan whitespace dengan benar merupakan kunci bagi penulisan kode yang mudah dibaca.

    ```Ruby
    sum = 1 + 2
    a, b = 1, 2
    1 > 2 ? true : false; puts 'Hi'
    [1, 2, 3].each { |e| puts e }
    ```

    Sebuah pengecualian tunggal, mengenai operator, adalah operator eksponensial:
    
    ```Ruby
    # buruk
    e = M * c ** 2

    # baik
    e = M * c**2
    ```

    `{` and `}` deserve a bit of clarification, since they are used
    for block and hash literals, as well as embedded expressions in
    strings. For hash literals two styles are considered acceptable.

    `{` dan `}` memerlukan sedikit klarifikasi, karena keduanya digunakan untuk
    literal block dan hash, dan juga sebagai ekspresi embedded di dalam string.
    Untuk literal hash, dua gaya berikut ini dianggap diterima.

    ```Ruby
    # baik - spasi sesudah { dan sebelum }
    { one: 1, two: 2 }

    # baik - tanpa spasi sesudah { dan sebelum }
    {one: 1, two: 2}
    ```

    Varian pertama sedikit lebih terbaca (dan bisa dibilang lebih populer
    di komunitas Ruby secara umum). Varian kedua memiliki kelebihan dalam
    menambahkan perbedaan visual antara literal block dan hash. Apapun yang
    anda gunakan - gunakanlah secara konsisten.

    Sebagai ekspresi embedded, ada juga dua opsi yang dapat diterima:

    ```Ruby
    # baik - tanpa spasi
    "string#{expr}"

    # ok - bisa dibilang lebih terbaca
    "string#{ expr }"
    ```

    Gaya pertama sangat populer dan anda disarankan untuk menggunakannya. 
    Di lain pihak, gaya kedua (bisa dibilang) sedikit lebih mudah terbaca.
    Sementara untuk hash - pilihlah satu gaya dan gunakanlah secara konsisten