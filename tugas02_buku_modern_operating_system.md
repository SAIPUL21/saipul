1.1 WHAT IS AN OPERATING SYSTEM?
1.1 APA ITU SISTEM OPERASI?

It is hard to pin down what an operating system is other than saying it is the
software that runs in kernel mode—and even that is not always true. Part of the
problem is that operating systems perform two essentially unrelated functions:
providing application programmers (and application programs, naturally) a clean
abstract set of resources instead of the messy hardware ones and managing these
hardware resources. Depending on who is doing the talking, you might hear mostly
about one function or the other. Let us now look at both.

Sulit untuk menjelaskan apa itu sistem operasi selain mengatakan itu adalah
perangkat lunak yang berjalan dalam mode kernel—dan bahkan itu tidak selalu benar. Bagian dari
Masalahnya adalah bahwa sistem operasi melakukan dua fungsi yang pada dasarnya tidak terkait:
menyediakan programmer aplikasi (dan program aplikasi, tentu saja) yang bersih
kumpulan sumber daya abstrak alih-alih perangkat keras yang berantakan dan mengelolanya
sumber daya perangkat keras. Bergantung pada siapa yang berbicara, Anda mungkin mendengar sebagian besar
tentang satu fungsi atau yang lain. Sekarang mari kita lihat keduanya.

1.1.1 The Operating System as an Extended Machine
1.1.1 Sistem Operasi sebagai Mesin yang Diperpanjang

The architecture (instruction set, memory organization, I/O, and bus structure) of most computers at the machine-language level is primitive and awkward to
program, especially for input/output. To make this point more concrete, consider
modern SATA (Serial ATA) hard disks used on most computers. A book (Anderson, 2007) describing an early version of the interface to the disk—what a programmer would have to know to use the disk—ran over 450 pages. Since then, the
interface has been revised multiple times and is more complicated than it was in
2007. Clearly, no sane programmer would want to deal with this disk at the hardware level. Instead, a piece of software, called a disk driver, deals with the hardware and provides an interface to read and write disk blocks, without getting into
the details. Operating systems contain many drivers for controlling I/O devices.

Arsitektur (set instruksi, organisasi memori, I/O, dan struktur bus) dari kebanyakan komputer pada tingkat bahasa mesin adalah primitif dan canggung untuk
program, terutama untuk input/output. Untuk membuat poin ini lebih konkret, pertimbangkan
hard disk SATA (Serial ATA) modern yang digunakan di sebagian besar komputer. Sebuah buku (Anderson, 2007) yang menjelaskan versi awal antarmuka ke disk—apa yang harus diketahui oleh seorang programmer untuk menggunakan disk—berisi lebih dari 450 halaman. Sejak itu,
antarmuka telah direvisi beberapa kali dan lebih rumit daripada sebelumnya
2007. Jelas, tidak ada programmer waras yang mau berurusan dengan disk ini di tingkat perangkat keras. Sebagai gantinya, perangkat lunak, yang disebut driver disk, menangani perangkat keras dan menyediakan antarmuka untuk membaca dan menulis blok disk, tanpa masuk ke
Rinciannya. Sistem operasi berisi banyak driver untuk mengontrol perangkat I/O.

But even this level is much too low for most applications. For this reason, all
operating systems provide yet another layer of abstraction for using disks: files.
Using this abstraction, programs can create, write, and read files, without having to
deal with the messy details of how the hardware actually works.

Tetapi bahkan level ini terlalu rendah untuk sebagian besar aplikasi. Untuk alasan ini, semua
sistem operasi menyediakan lapisan abstraksi lain untuk menggunakan disk: file.
Dengan menggunakan abstraksi ini, program dapat membuat, menulis, dan membaca file, tanpa harus
berurusan dengan rincian berantakan tentang bagaimana perangkat keras benar-benar bekerja.

This abstraction is the key to managing all this complexity. Good abstractions
turn a nearly impossible task into two manageable ones. The first is defining and
implementing the abstractions. The second is using these abstractions to solve the
problem at hand. One abstraction that almost every computer user understands is
the file, as mentioned above. It is a useful piece of information, such as a digital
photo, saved email message, song, or Web page. It is much easier to deal with photos, emails, songs, and Web pages than with the details of SATA (or other) disks.
The job of the operating system is to create good abstractions and then implement
and manage the abstract objects thus created. In this book, we will talk a lot about
abstractions. They are one of the keys to understanding operating systems.

Abstraksi ini adalah kunci untuk mengelola semua kerumitan ini. Abstraksi yang bagus
mengubah tugas yang hampir mustahil menjadi dua tugas yang dapat dikelola. Yang pertama adalah mendefinisikan dan
mengimplementasikan abstraksi. Yang kedua adalah menggunakan abstraksi ini untuk menyelesaikan
masalah di tangan. Salah satu abstraksi yang dipahami oleh hampir setiap pengguna komputer adalah
file, seperti yang disebutkan di atas. Ini adalah informasi yang berguna, seperti digital
foto, pesan email yang disimpan, lagu, atau halaman Web. Jauh lebih mudah untuk menangani foto, email, lagu, dan halaman Web daripada dengan detail disk SATA (atau lainnya).
Tugas sistem operasi adalah membuat abstraksi yang baik dan kemudian mengimplementasikannya
dan mengelola objek abstrak yang dibuat. Dalam buku ini, kita akan berbicara banyak tentang
abstraksi. Mereka adalah salah satu kunci untuk memahami sistem operasi.

This point is so important that it is worth repeating in different words. With all
due respect to the industrial engineers who so carefully designed the Macintosh,
hardware is ugly. Real processors, memories, disks, and other devices are very
complicated and present difficult, awkward, idiosyncratic, and inconsistent interfaces to the people who have to write software to use them. Sometimes this is due
to the need for backward compatibility with older hardware. Other times it is an
attempt to save money. Often, however, the hardware designers do not realize (or
care) how much trouble they are causing for the software. One of the major tasks
of the operating system is to hide the hardware and present programs (and their
programmers) with nice, clean, elegant, consistent, abstractions to work with instead. Operating systems turn the ugly into the beautiful, as shown in Fig. 1-2.

Poin ini sangat penting sehingga perlu diulang dengan kata-kata yang berbeda. Dengan semua
hormat kepada para insinyur industri yang merancang Macintosh dengan sangat hati-hati,
perangkat kerasnya jelek. Prosesor nyata, memori, disk, dan perangkat lain sangat
rumit dan menghadirkan antarmuka yang sulit, canggung, istimewa, dan tidak konsisten kepada orang-orang yang harus menulis perangkat lunak untuk menggunakannya. Terkadang ini karena
dengan kebutuhan untuk kompatibilitas dengan perangkat keras yang lebih tua. Di lain waktu itu adalah
usaha untuk menghemat uang. Namun, seringkali, perancang perangkat keras tidak menyadari (atau
peduli) berapa banyak masalah yang mereka sebabkan untuk perangkat lunak. Salah satu tugas utama
dari sistem operasi adalah menyembunyikan perangkat keras dan menyajikan program (dan
programmer) dengan abstraksi yang bagus, bersih, elegan, konsisten, untuk digunakan. Sistem operasi mengubah yang jelek menjadi indah, seperti yang ditunjukkan pada Gambar 1-2.

It should be noted that the operating system’s real customers are the application programs (via the application programmers, of course). They are the ones
who deal directly with the operating system and its abstractions. In contrast, end
users deal with the abstractions provided by the user interface, either a command-line shell or a graphical interface. While the abstractions at the user interface
may be similar to the ones provided by the operating system, this is not always the
case. To make this point clearer, consider the normal Windows desktop and the
line-oriented command prompt. Both are programs running on the Windows operating system and use the abstractions Windows provides, but they offer very different user interfaces. Similarly, a Linux user running Gnome or KDE sees a very
different interface than a Linux user working directly on top of the underlying X
Window System, but the underlying operating system abstractions are the same in
both cases.

Perlu dicatat bahwa pelanggan nyata sistem operasi adalah program aplikasi (melalui pemrogram aplikasi, tentu saja). Mereka adalah orang-orangnya
yang berhubungan langsung dengan sistem operasi dan abstraksinya. Sebaliknya, akhir
pengguna berurusan dengan abstraksi yang disediakan oleh antarmuka pengguna, baik shell baris perintah atau antarmuka grafis. Sementara abstraksi di antarmuka pengguna
mungkin mirip dengan yang disediakan oleh sistem operasi, ini tidak selalu
kasus. Untuk memperjelas poin ini, pertimbangkan desktop Windows normal dan
prompt perintah berorientasi baris. Keduanya adalah program yang berjalan pada sistem operasi Windows dan menggunakan abstraksi yang disediakan Windows, tetapi keduanya menawarkan antarmuka pengguna yang sangat berbeda. Demikian pula, pengguna Linux yang menjalankan Gnome atau KDE melihat
antarmuka yang berbeda dari pengguna Linux yang bekerja langsung di atas X yang mendasarinya
Sistem Jendela, tetapi abstraksi sistem operasi yang mendasarinya sama dalam
kedua kasus.

In this book, we will study the abstractions provided to application programs in
great detail, but say rather little about user interfaces. That is a large and important
subject, but one only peripherally related to operating systems.

Dalam buku ini, kita akan mempelajari abstraksi yang disediakan untuk program aplikasi di
sangat detail, tetapi tidak banyak bicara tentang antarmuka pengguna. Itu besar dan penting
subjek, tetapi hanya satu yang terkait dengan sistem operasi.

1.1.2 The Operating System as a Resource Manager
1.1.2 Sistem Operasi sebagai Resource Manager

The concept of an operating system as primarily providing abstractions to application programs is a top-down view. An alternative, bottom-up, view holds that
the operating system is there to manage all the pieces of a complex system. Modern computers consist of processors, memories, timers, disks, mice, network interfaces, printers, and a wide variety of other devices. In the bottom-up view, the job
of the operating system is to provide for an orderly and controlled allocation of the
processors, memories, and I/O devices among the various programs wanting them.

Konsep sistem operasi yang menyediakan abstraksi untuk program aplikasi adalah pandangan dari atas ke bawah. Pandangan alternatif, dari bawah ke atas, menyatakan bahwa
sistem operasi ada untuk mengelola semua bagian dari sistem yang kompleks. Komputer modern terdiri dari prosesor, memori, timer, disk, mouse, antarmuka jaringan, printer, dan berbagai perangkat lainnya. Dalam tampilan bottom-up, pekerjaan
sistem operasi adalah untuk menyediakan alokasi yang teratur dan terkendali dari
prosesor, memori, dan perangkat I/O di antara berbagai program yang menginginkannya.

Modern operating systems allow multiple programs to be in memory and run
at the same time. Imagine what would happen if three programs running on some
computer all tried to print their output simultaneously on the same printer. The first
few lines of printout might be from program 1, the next few from program 2, then
some from program 3, and so forth. The result would be utter chaos. The operating
system can bring order to the potential chaos by buffering all the output destined
for the printer on the disk. When one program is finished, the operating system can
then copy its output from the disk file where it has been stored for the printer,
while at the same time the other program can continue generating more output,
oblivious to the fact that the output is not really going to the printer (yet).

Sistem operasi modern memungkinkan beberapa program berada di memori dan dijalankan
pada saat yang sama. Bayangkan apa yang akan terjadi jika tiga program berjalan pada beberapa
komputer semua mencoba untuk mencetak output mereka secara bersamaan pada printer yang sama. Pertama
beberapa baris cetakan mungkin berasal dari program 1, beberapa baris berikutnya dari program 2, lalu
beberapa dari program 3, dan sebagainya. Hasilnya akan menjadi kekacauan total. Pengoperasian
sistem dapat menertibkan potensi kekacauan dengan menyangga semua output yang ditentukan
untuk printer pada disk. Ketika satu program selesai, sistem operasi dapat
kemudian salin outputnya dari file disk tempat disimpan untuk printer,
sementara pada saat yang sama program lain dapat terus menghasilkan lebih banyak output,
tidak menyadari fakta bahwa output tidak benar-benar masuk ke printer (belum).

When a computer (or network) has more than one user, the need for managing
and protecting the memory, I/O devices, and other resources is even more since the
users might otherwise interfere with one another. In addition, users often need to
share not only hardware, but information (files, databases, etc.) as well. In short,
this view of the operating system holds that its primary task is to keep track of
which programs are using which resource, to grant resource requests, to account
for usage, and to mediate conflicting requests from different programs and users.

Ketika komputer (atau jaringan) memiliki lebih dari satu pengguna, kebutuhan untuk mengelola
dan melindungi memori, perangkat I/O, dan sumber daya lainnya bahkan lebih sejak
pengguna dapat mengganggu satu sama lain. Selain itu, pengguna sering kali perlu
berbagi tidak hanya perangkat keras, tetapi juga informasi (file, database, dll.) Pendeknya,
pandangan sistem operasi ini menyatakan bahwa tugas utamanya adalah untuk melacak
program mana yang menggunakan sumber daya mana, untuk mengabulkan permintaan sumber daya, untuk memperhitungkan
untuk penggunaan, dan untuk menengahi permintaan yang bertentangan dari program dan pengguna yang berbeda.

Resource management includes multiplexing (sharing) resources in two different ways: in time and in space. When a resource is time multiplexed, different
programs or users take turns using it. First one of them gets to use the resource,
then another, and so on. For example, with only one CPU and multiple programs
that want to run on it, the operating system first allocates the CPU to one program,
then, after it has run long enough, another program gets to use the CPU, then another, and then eventually the first one again. Determining how the resource is time
multiplexed—who goes next and for how long—is the task of the operating system. Another example of time multiplexing is sharing the printer. When multiple
print jobs are queued up for printing on a single printer, a decision has to be made
about which one is to be printed next.

Manajemen sumber daya mencakup multiplexing (berbagi) sumber daya dalam dua cara berbeda: dalam waktu dan dalam ruang. Ketika sumber daya digandakan waktu, berbeda
program atau pengguna bergiliran menggunakannya. Pertama, salah satu dari mereka dapat menggunakan sumber daya,
lalu yang lain, dan seterusnya. Misalnya, dengan hanya satu CPU dan beberapa program
yang ingin dijalankan di atasnya, sistem operasi terlebih dahulu mengalokasikan CPU ke satu program,
kemudian, setelah berjalan cukup lama, program lain akan menggunakan CPU, kemudian yang lain, dan akhirnya yang pertama lagi. Menentukan bagaimana sumber daya adalah waktu
multiplexing—siapa yang selanjutnya dan untuk berapa lama—adalah tugas sistem operasi. Contoh lain dari multiplexing waktu adalah berbagi printer. Ketika banyak
pekerjaan cetak diantrekan untuk dicetak pada satu printer, keputusan harus dibuat
tentang mana yang akan dicetak berikutnya.

The other kind of multiplexing is space multiplexing. Instead of the customers
taking turns, each one gets part of the resource. For example, main memory is normally divided up among several running programs, so each one can be resident at
the same time (for example, in order to take turns using the CPU). Assuming there
is enough memory to hold multiple programs, it is more efficient to hold several
programs in memory at once rather than give one of them all of it, especially if it
only needs a small fraction of the total. Of course, this raises issues of fairness,
protection, and so on, and it is up to the operating system to solve them. Another
resource that is space multiplexed is the disk. In many systems a single disk can
hold files from many users at the same time. Allocating disk space and keeping
track of who is using which disk blocks is a typical operating system task.

Jenis multiplexing lainnya adalah space multiplexing. Alih-alih pelanggan
bergiliran, masing-masing mendapat bagian dari sumber daya. Misalnya, memori utama biasanya dibagi di antara beberapa program yang sedang berjalan, sehingga masing-masing program dapat disimpan di
waktu yang sama (misalnya, untuk bergiliran menggunakan CPU). Dengan asumsi ada
cukup memori untuk menampung banyak program, lebih efisien untuk menampung beberapa
program dalam memori sekaligus daripada memberikan salah satu dari mereka semua, terutama jika itu
hanya membutuhkan sebagian kecil dari total. Tentu saja hal ini menimbulkan masalah keadilan,
perlindungan, dan sebagainya, dan terserah pada sistem operasi untuk menyelesaikannya. Lain
sumber daya yang di-multipleks ruang adalah disk. Dalam banyak sistem, satu disk dapat
menyimpan file dari banyak pengguna secara bersamaan. Mengalokasikan ruang disk dan menyimpannya
melacak siapa yang menggunakan blok disk mana yang merupakan tugas khas sistem operasi.

1.2 HISTORY OF OPERATING SYSTEMS
1.2 SEJARAH SISTEM OPERASI

Operating systems have been evolving through the years. In the following sections we will briefly look at a few of the highlights. Since operating systems have
historically been closely tied to the architecture of the computers on which they
run, we will look at successive generations of computers to see what their operating systems were like. This mapping of operating system generations to computer
generations is crude, but it does provide some structure where there would otherwise be none.

Sistem operasi telah berkembang selama bertahun-tahun. Pada bagian berikut kita akan melihat secara singkat beberapa sorotan. Karena sistem operasi memiliki
secara historis terkait erat dengan arsitektur komputer tempat mereka
dijalankan, kita akan melihat generasi komputer yang berurutan untuk melihat seperti apa sistem operasi mereka. Pemetaan generasi sistem operasi ini ke komputer
generasi itu kasar, tetapi itu memberikan beberapa struktur di mana jika tidak tidak akan ada.

The progression given below is largely chronological, but it has been a bumpy
ride. Each development did not wait until the previous one nicely finished before
getting started. There was a lot of overlap, not to mention many false starts and
dead ends. Take this as a guide, not as the last word.

Perkembangan yang diberikan di bawah ini sebagian besar kronologis, tetapi telah bergelombang
mengendarai. Setiap pengembangan tidak menunggu sampai yang sebelumnya selesai dengan baik sebelumnya
mulai. Ada banyak tumpang tindih, belum lagi banyak awal yang salah dan
jalan buntu. Ambil ini sebagai panduan, bukan sebagai kata terakhir. Perkembangan yang diberikan di bawah ini sebagian besar kronologis, tetapi telah bergelombang
mengendarai. Setiap pengembangan tidak menunggu sampai yang sebelumnya selesai dengan baik sebelumnya
mulai. Ada banyak tumpang tindih, belum lagi banyak awal yang salah dan
jalan buntu. Ambil ini sebagai panduan, bukan sebagai kata terakhir.

The first true digital computer was designed by the English mathematician
Charles Babbage (1792–1871). Although Babbage spent most of his life and fortune trying to build his ‘‘analytical engine,’’ he nev er got it working properly because it was purely mechanical, and the technology of his day could not produce
the required wheels, gears, and cogs to the high precision that he needed. Needless
to say, the analytical engine did not have an operating system.

Komputer digital pertama yang benar dirancang oleh ahli matematika Inggris
Charles Babbage (1792–1871). Meskipun Babbage menghabiskan sebagian besar hidup dan kekayaannya untuk mencoba membangun ''mesin analitiknya,'' dia tidak pernah membuatnya bekerja dengan baik karena itu murni mekanis, dan teknologi pada zamannya tidak dapat menghasilkan
roda, roda gigi, dan roda gigi yang dibutuhkan dengan presisi tinggi yang dia butuhkan. Tidak perlu
untuk mengatakan, mesin analitik tidak memiliki sistem operasi.

As an interesting historical aside, Babbage realized that he would need software for his analytical engine, so he hired a young woman named Ada Lovelace,
who was the daughter of the famed British poet Lord Byron, as the world’s first
programmer. The programming language Ada® is named after her.

Sebagai tambahan sejarah yang menarik, Babbage menyadari bahwa dia akan membutuhkan perangkat lunak untuk mesin analitiknya, jadi dia mempekerjakan seorang wanita muda bernama Ada Lovelace,
yang merupakan putri penyair Inggris terkenal Lord Byron, sebagai yang pertama di dunia
programmer. Bahasa pemrograman Ada® dinamai menurut namanya.

1.2.1 The First Generation (1945–55): Vacuum Tubes
1.2.1 Generasi Pertama (1945–55): Tabung Vakum

After Babbage’s unsuccessful efforts, little progress was made in constructing
digital computers until the World War II period, which stimulated an explosion of
activity. Professor John Atanasoff and his graduate student Clifford Berry built
what is now reg arded as the first functioning digital computer at Iowa State University. It used 300 vacuum tubes. At roughly the same time, Konrad Zuse in Berlin
built the Z3 computer out of electromechanical relays. In 1944, the Colossus was
built and programmed by a group of scientists (including Alan Turing) at Bletchley
Park, England, the Mark I was built by Howard Aiken at Harvard, and the ENIAC
was built by William Mauchley and his graduate student J. Presper Eckert at the
University of Pennsylvania. Some were binary, some used vacuum tubes, some
were programmable, but all were very primitive and took seconds to perform even
the simplest calculation.

Setelah upaya Babbage yang gagal, hanya sedikit kemajuan yang dibuat dalam konstruksi
komputer digital hingga periode Perang Dunia II, yang memicu ledakan
aktivitas. Profesor John Atanasoff dan mahasiswa pascasarjananya Clifford Berry membangun
apa yang sekarang disebut sebagai komputer digital pertama yang berfungsi di Iowa State University. Ini digunakan 300 tabung vakum. Pada waktu yang hampir bersamaan, Konrad Zuse di Berlin
membangun komputer Z3 dari relai elektromekanis. Pada tahun 1944, Colossus adalah
dibangun dan diprogram oleh sekelompok ilmuwan (termasuk Alan Turing) di Bletchley
Park, Inggris, Mark I dibangun oleh Howard Aiken di Harvard, dan ENIAC
dibangun oleh William Mauchley dan mahasiswa pascasarjananya J. Presper Eckert di
Universitas Pennsylvania. Beberapa biner, beberapa menggunakan tabung vakum, beberapa
dapat diprogram, tetapi semuanya sangat primitif dan membutuhkan waktu beberapa detik untuk tampil merata
perhitungan paling sederhana.

In these early days, a single group of people (usually engineers) designed,
built, programmed, operated, and maintained each machine. All programming was
done in absolute machine language, or even worse yet, by wiring up electrical circuits by connecting thousands of cables to plugboards to control the machine’s
basic functions. Programming languages were unknown (even assembly language
was unknown). Operating systems were unheard of. The usual mode of operation
was for the programmer to sign up for a block of time using the signup sheet on the
wall, then come down to the machine room, insert his or her plugboard into the
computer, and spend the next few hours hoping that none of the 20,000 or so vacuum tubes would burn out during the run. Virtually all the problems were simple 
straightforward mathematical and numerical calculations, such as grinding out
tables of sines, cosines, and logarithms, or computing artillery trajectories.

Pada hari-hari awal ini, sekelompok orang (biasanya insinyur) merancang,
dibangun, diprogram, dioperasikan, dan dipelihara setiap mesin. Semua pemrograman adalah
dilakukan dalam bahasa mesin mutlak, atau bahkan lebih buruk lagi, dengan memasang kabel sirkuit listrik dengan menghubungkan ribuan kabel ke plugboard untuk mengontrol mesin
fungsi dasar. Bahasa pemrograman tidak diketahui (bahkan bahasa assembly
tidak diketahui). Sistem operasi tidak pernah terdengar sebelumnya. Mode operasi biasa
adalah untuk programmer untuk mendaftar untuk blok waktu menggunakan lembar pendaftaran di
dinding, lalu turun ke ruang mesin, masukkan plugboard-nya ke dalam
komputer, dan menghabiskan beberapa jam berikutnya berharap bahwa tidak ada dari 20.000 atau lebih tabung vakum akan terbakar selama menjalankan. Hampir semua masalahnya sederhana
perhitungan matematis dan numerik langsung, seperti penggilingan
tabel sinus, cosinus, dan logaritma, atau menghitung lintasan artileri.

By the early 1950s, the routine had improved somewhat with the introduction
of punched cards. It was now possible to write programs on cards and read them in
instead of using plugboards; otherwise, the procedure was the same.

Pada awal 1950-an, rutinitas sedikit membaik dengan diperkenalkannya
dari kartu berlubang. Sekarang mungkin untuk menulis program pada kartu dan membacanya di
alih-alih menggunakan plugboard; jika tidak, prosedurnya sama.

1.2.2 The second generation (1955-56): transistors and batch systems
1.2.2 Generasi kedua (1955-56): transistor dan sistem batch

The introduction of the transistor in the mid-1950s changed the picture radically. Computers became reliable enough that they could be manufactured and sold
to paying customers with the expectation that they would continue to function long
enough to get some useful work done. For the first time, there was a clear separation between designers, builders, operators, programmers, and maintenance personnel.

Pengenalan transistor pada pertengahan 1950-an mengubah gambaran secara radikal. Komputer menjadi cukup andal sehingga dapat diproduksi dan dijual
untuk membayar pelanggan dengan harapan bahwa mereka akan terus berfungsi lama
cukup untuk menyelesaikan pekerjaan yang bermanfaat. Untuk pertama kalinya, ada pemisahan yang jelas antara desainer, pembangun, operator, pemrogram, dan personel pemeliharaan.

These machines, now called mainframes, were locked away in large, specially
air-conditioned computer rooms, with staffs of professional operators to run them.
Only large corporations or major government agencies or universities could afford
the multimillion-dollar price tag. To run a job (i.e., a program or set of programs),
a programmer would first write the program on paper (in FORTRAN or assembler), then punch it on cards. He would then bring the card deck down to the input
room and hand it to one of the operators and go drink coffee until the output was
ready.

Mesin-mesin ini, sekarang disebut mainframe, dikunci dalam jumlah besar, khususnya
ruang komputer ber-AC, dengan staf operator profesional untuk menjalankannya.
Hanya perusahaan besar atau lembaga pemerintah atau universitas besar yang mampu
label harga jutaan dolar. Untuk menjalankan pekerjaan (yaitu, program atau serangkaian program),
seorang programmer pertama-tama akan menulis program di atas kertas (dalam FORTRAN atau assembler), kemudian memencetnya di kartu. Dia kemudian akan membawa dek kartu ke input
kamar dan serahkan ke salah satu operator dan pergi minum kopi sampai outputnya
siap.

When the computer finished whatever job it was currently running, an operator
would go over to the printer and tear off the output and carry it over to the output
room, so that the programmer could collect it later. Then he would take one of the
card decks that had been brought from the input room and read it in. If the FORTRAN compiler was needed, the operator would have to get it from a file cabinet
and read it in. Much computer time was wasted while operators were walking
around the machine room.

Ketika komputer menyelesaikan pekerjaan apa pun yang sedang dijalankannya, seorang operator
akan pergi ke printer dan merobek output dan membawanya ke output
ruangan, sehingga programmer bisa mengumpulkannya nanti. Kemudian dia akan mengambil salah satu dari
deck kartu yang telah dibawa dari ruang input dan membacanya. Jika kompiler FORTRAN diperlukan, operator harus mendapatkannya dari lemari arsip
dan membacanya. Banyak waktu komputer terbuang saat operator berjalan
di sekitar ruang mesin.

Given the high cost of the equipment, it is not surprising that people quickly
looked for ways to reduce the wasted time. The solution generally adopted was the
batch system. The idea behind it was to collect a tray full of jobs in the input
room and then read them onto a magnetic tape using a small (relatively) inexpensive computer, such as the IBM 1401, which was quite good at reading cards,
copying tapes, and printing output, but not at all good at numerical calculations.
Other, much more expensive machines, such as the IBM 7094, were used for the
real computing. This situation is shown in Fig. 1-3.

Mengingat tingginya biaya peralatan, tidak mengherankan bahwa orang-orang dengan cepat
mencari cara untuk mengurangi waktu yang terbuang. Solusi yang umumnya diadopsi adalah
sistem batch. Ide di baliknya adalah untuk mengumpulkan baki yang penuh dengan pekerjaan di input
ruangan dan kemudian membacanya ke pita magnetik menggunakan komputer kecil (relatif) murah, seperti IBM 1401, yang cukup bagus dalam membaca kartu,
menyalin kaset, dan mencetak hasil, tetapi sama sekali tidak pandai dalam perhitungan numerik.
Mesin lain yang jauh lebih mahal, seperti IBM 7094, digunakan untuk
komputasi nyata. Situasi ini ditunjukkan pada Gambar. 1-3.

After about an hour of collecting a batch of jobs, the cards were read onto a
magnetic tape, which was carried into the machine room, where it was mounted on
a tape drive. The operator then loaded a special program (the ancestor of today’s
operating system), which read the first job from tape and ran it. The output was
written onto a second tape, instead of being printed. After each job finished, the
operating system automatically read the next job from the tape and began running
it. When the whole batch was done, the operator removed the input and output
tapes, replaced the input tape with the next batch, and brought the output tape to a
1401 for printing off line (i.e., not connected to the main computer).

Setelah sekitar satu jam mengumpulkan sejumlah pekerjaan, kartu-kartu itu dibacakan ke
pita magnetik, yang dibawa ke ruang mesin, di mana ia dipasang
sebuah kaset. Operator kemudian memuat program khusus (nenek moyang hari ini
sistem operasi), yang membaca pekerjaan pertama dari tape dan menjalankannya. Keluarannya adalah
ditulis ke kaset kedua, bukannya dicetak. Setelah setiap pekerjaan selesai,
sistem operasi secara otomatis membaca pekerjaan berikutnya dari rekaman itu dan mulai berjalan
dia. Ketika seluruh batch selesai, operator menghapus input dan output
kaset, mengganti pita input dengan batch berikutnya, dan membawa pita keluaran ke a
1401 untuk mencetak off line (yaitu, tidak terhubung ke komputer utama).

The structure of a typical input job is shown in Fig. 1-4. It started out with a
$JOB card, specifying the maximum run time in minutes, the account number to be
charged, and the programmer’s name. Then came a $FORTRAN card, telling the
operating system to load the FORTRAN compiler from the system tape. It was directly followed by the program to be compiled, and then a $LOAD card, directing
the operating system to load the object program just compiled. (Compiled programs were often written on scratch tapes and had to be loaded explicitly.) Next
came the $RUN card, telling the operating system to run the program with the data
following it. Finally, the $END card marked the end of the job. These primitive
control cards were the forerunners of modern shells and command-line interpreters.

Struktur pekerjaan input tipikal ditunjukkan pada Gambar. 1-4. Ini dimulai dengan
kartu $JOB, menentukan waktu berjalan maksimum dalam menit, nomor akun yang akan
dibebankan, dan nama programmer. Kemudian datang kartu $FORTRAN, memberi tahu
sistem operasi untuk memuat compiler FORTRAN dari sistem tape. Itu langsung diikuti oleh program yang akan dikompilasi, dan kemudian kartu $LOAD, mengarahkan
sistem operasi untuk memuat program objek yang baru saja dikompilasi. (Program yang dikompilasi sering ditulis pada kaset awal dan harus dimuat secara eksplisit.) Selanjutnya
datang kartu $RUN, memberi tahu sistem operasi untuk menjalankan program dengan data
mengikutinya. Akhirnya, kartu $END menandai akhir dari pekerjaan. Primitif ini
kartu kontrol adalah cikal bakal shell modern dan interpreter baris perintah.

Large second-generation computers were used mostly for scientific and engineering calculations, such as solving the partial differential equations that often occur in physics and engineering. They were largely programmed in FORTRAN and
assembly language. Typical operating systems were FMS (the Fortran Monitor
System) and IBSYS, IBM’s operating system for the 7094.

Komputer generasi kedua yang besar sebagian besar digunakan untuk perhitungan ilmiah dan teknik, seperti memecahkan persamaan diferensial parsial yang sering terjadi dalam fisika dan teknik. Mereka sebagian besar diprogram dalam FORTRAN dan
bahasa campuran. Sistem operasi yang umum adalah FMS (Fortran Monitor
System) dan IBSYS, sistem operasi IBM untuk 7094.

1.2.3 The Third Generation (1965–1980): ICs and Multiprogramming
1.2.3 Generasi Ketiga (1965–1980): IC dan Multiprogramming

By the early 1960s, most computer manufacturers had two distinct, incompatible, product lines. On the one hand, there were the word-oriented, large-scale scientific computers, such as the 7094, which were used for industrial-strength numerical calculations in science and engineering. On the other hand, there were the
character-oriented, commercial computers, such as the 1401, which were widely
used for tape sorting and printing by banks and insurance companies.

Pada awal 1960-an, sebagian besar produsen komputer memiliki dua lini produk yang berbeda dan tidak kompatibel. Di satu sisi, ada komputer ilmiah skala besar yang berorientasi pada kata, seperti 7094, yang digunakan untuk perhitungan numerik kekuatan industri dalam sains dan teknik. Di sisi lain, ada
berorientasi karakter, komputer komersial, seperti 1401, yang secara luas
digunakan untuk penyortiran dan pencetakan pita oleh bank dan perusahaan asuransi.

Developing and maintaining two completely different product lines was an expensive proposition for the manufacturers. In addition, many new computer customers initially needed a small machine but later outgrew it and wanted a bigger
machine that would run all their old programs, but faster.

Mengembangkan dan memelihara dua lini produk yang sama sekali berbeda merupakan proposisi yang mahal bagi produsen. Selain itu, banyak pelanggan komputer baru pada awalnya membutuhkan mesin kecil tetapi kemudian menjadi lebih besar dan menginginkan yang lebih besar
mesin yang akan menjalankan semua program lama mereka, tetapi lebih cepat.

IBM attempted to solve both of these problems at a single stroke by introducing the System/360. The 360 was a series of software-compatible machines ranging from 1401-sized models to much larger ones, more powerful than the mighty
7094. The machines differed only in price and performance (maximum memory,
processor speed, number of I/O devices permitted, and so forth). Since they all had
the same architecture and instruction set, programs written for one machine could
run on all the others—at least in theory. (But as Yogi Berra reputedly said: ‘‘In
theory, theory and practice are the same; in practice, they are not.’’) Since the 360
was designed to handle both scientific (i.e., numerical) and commercial computing,
a single family of machines could satisfy the needs of all customers. In subsequent
years, IBM came out with backward compatible successors to the 360 line, using
more modern technology, known as the 370, 4300, 3080, and 3090. The zSeries is
the most recent descendant of this line, although it has diverged considerably from
the original.

IBM berusaha untuk memecahkan kedua masalah ini dengan satu pukulan dengan memperkenalkan System/360. 360 adalah serangkaian mesin yang kompatibel dengan perangkat lunak mulai dari model berukuran 1401 hingga yang jauh lebih besar, lebih kuat daripada yang perkasa.
7094. Mesin hanya berbeda dalam harga dan kinerja (memori maksimum,
kecepatan prosesor, jumlah perangkat I/O yang diizinkan, dan sebagainya). Karena mereka semua memiliki
arsitektur dan set instruksi yang sama, program yang ditulis untuk satu mesin dapat
menjalankan semua yang lain-setidaknya dalam teori. (Tapi seperti yang dikatakan Yogi Berra: ''In
teori, teori dan praktek adalah sama; dalam praktiknya, mereka tidak.'') Sejak 360
dirancang untuk menangani komputasi ilmiah (yaitu, numerik) dan komersial,
satu keluarga mesin dapat memenuhi kebutuhan semua pelanggan. Selanjutnya
tahun, IBM keluar dengan penerus kompatibel ke garis 360, menggunakan
teknologi yang lebih modern, yang dikenal sebagai 370, 4300, 3080, dan 3090. Seri z
keturunan terbaru dari garis ini, meskipun telah menyimpang jauh dari
asli.

The IBM 360 was the first major computer line to use (small-scale) ICs (Integrated Circuits), thus providing a major price/performance advantage over the
second-generation machines, which were built up from individual transistors. It
was an immediate success, and the idea of a family of compatible computers was
soon adopted by all the other major manufacturers. The descendants of these machines are still in use at computer centers today. Now adays they are often used for
managing huge databases (e.g., for airline reservation systems) or as servers for
World Wide Web sites that must process thousands of requests per second.

IBM 360 adalah lini komputer utama pertama yang menggunakan IC (Sirkuit Terpadu) (skala kecil), sehingga memberikan keunggulan harga/kinerja utama dibandingkan
mesin generasi kedua, yang dibangun dari transistor individu. Dia
adalah sukses langsung, dan ide dari keluarga komputer yang kompatibel adalah
segera diadopsi oleh semua produsen besar lainnya. Keturunan dari mesin ini masih digunakan di pusat komputer sampai sekarang. Sekarang ini sering digunakan untuk
mengelola database besar (misalnya, untuk sistem reservasi maskapai penerbangan) atau sebagai server untuk
Situs World Wide Web yang harus memproses ribuan permintaan per detik.

The greatest strength of the ‘‘single-family’’ idea was simultaneously its greatest weakness. The original intention was that all software, including the operating
system, OS/360, had to work on all models. It had to run on small systems, which
often just replaced 1401s for copying cards to tape, and on very large systems,
which often replaced 7094s for doing weather forecasting and other heavy computing. It had to be good on systems with few peripherals and on systems with many
peripherals. It had to work in commercial environments and in scientific environments. Above all, it had to be efficient for all of these different uses.

Kekuatan terbesar dari ide '' keluarga tunggal '' secara bersamaan adalah kelemahan terbesarnya. Niat awalnya adalah bahwa semua perangkat lunak, termasuk operasi
sistem, OS/360, harus bekerja pada semua model. Itu harus berjalan pada sistem kecil, yang
sering kali hanya mengganti 1401 untuk menyalin kartu ke tape, dan pada sistem yang sangat besar,
yang sering menggantikan 7094 untuk melakukan prakiraan cuaca dan komputasi berat lainnya. Itu harus bagus pada sistem dengan sedikit periferal dan pada sistem dengan banyak
periferal. Itu harus bekerja di lingkungan komersial dan di lingkungan ilmiah. Di atas segalanya, itu harus efisien untuk semua kegunaan yang berbeda ini.

There was no way that IBM (or anybody else for that matter) could write a
piece of software to meet all those conflicting requirements. The result was an
enormous and extraordinarily complex operating system, probably two to three
orders of magnitude larger than FMS. It consisted of millions of lines of assembly
language written by thousands of programmers, and contained thousands upon
thousands of bugs, which necessitated a continuous stream of new releases in an
attempt to correct them. Each new release fixed some bugs and introduced new
ones, so the number of bugs probably remained constant over time.

Tidak mungkin IBM (atau siapa pun dalam hal ini) dapat menulis
bagian dari perangkat lunak untuk memenuhi semua persyaratan yang saling bertentangan. Hasilnya adalah
sistem operasi yang sangat besar dan luar biasa kompleks, mungkin dua hingga tiga
urutan besarnya lebih besar dari FMS. Itu terdiri dari jutaan jalur perakitan
bahasa yang ditulis oleh ribuan programmer, dan berisi ribuan
ribuan bug, yang memerlukan aliran rilis baru secara terus-menerus dalam
mencoba untuk memperbaikinya. Setiap rilis baru memperbaiki beberapa bug dan memperkenalkan yang baru
yang, sehingga jumlah bug mungkin tetap konstan dari waktu ke waktu.

One of the designers of OS/360, Fred Brooks, subsequently wrote a witty and
incisive book (Brooks, 1995) describing his experiences with OS/360. While it
would be impossible to summarize the book here, suffice it to say that the cover
shows a herd of prehistoric beasts stuck in a tar pit. The cover of Silberschatz et al.
(2012) makes a similar point about operating systems being dinosaurs.

Salah satu desainer OS/360, Fred Brooks, kemudian menulis sebuah jenaka dan
buku tajam (Brooks, 1995) menggambarkan pengalamannya dengan OS/360. Sementara itu
tidak mungkin untuk meringkas buku di sini, cukup untuk mengatakan bahwa sampulnya
menunjukkan kawanan binatang prasejarah terjebak di lubang tar. Sampul Silberschatz dkk.
(2012) membuat poin serupa tentang sistem operasi yang menjadi dinosaurus.

Despite its enormous size and problems, OS/360 and the similar third-generation operating systems produced by other computer manufacturers actually satisfied most of their customers reasonably well. They also popularized several key
techniques absent in second-generation operating systems. Probably the most important of these was multiprogramming. On the 7094, when the current job
paused to wait for a tape or other I/O operation to complete, the CPU simply sat
idle until the I/O finished. With heavily CPU-bound scientific calculations, I/O is
infrequent, so this wasted time is not significant. With commercial data processing,
the I/O wait time can often be 80 or 90% of the total time, so something had to be
done to avoid having the (expensive) CPU be idle so much.

Terlepas dari ukuran dan masalahnya yang sangat besar, OS/360 dan sistem operasi generasi ketiga serupa yang diproduksi oleh produsen komputer lain sebenarnya cukup memuaskan sebagian besar pelanggan mereka. Mereka juga mempopulerkan beberapa kunci
teknik yang tidak ada dalam sistem operasi generasi kedua. Mungkin yang paling penting adalah multiprogramming. Pada 7094, saat pekerjaan saat ini
dijeda untuk menunggu rekaman atau operasi I/O lainnya selesai, CPU hanya duduk
idle sampai I/O selesai. Dengan perhitungan ilmiah yang sangat terikat CPU, I/O adalah
jarang, jadi waktu yang terbuang ini tidak signifikan. Dengan pemrosesan data komersial,
waktu tunggu I/O seringkali bisa mencapai 80 atau 90% dari total waktu, jadi harus ada sesuatu
dilakukan untuk menghindari CPU (mahal) menganggur begitu banyak.

The solution that evolved was to partition memory into several pieces, with a
different job in each partition, as shown in Fig. 1-5. While one job was waiting for
I/O to complete, another job could be using the CPU. If enough jobs could be held
in main memory at once, the CPU could be kept busy nearly 100% of the time.
Having multiple jobs safely in memory at once requires special hardware to protect
each job against snooping and mischief by the other ones, but the 360 and other
third-generation systems were equipped with this hardware.

Solusi yang berkembang adalah dengan mempartisi memori menjadi beberapa bagian, dengan a
pekerjaan yang berbeda di setiap partisi, seperti yang ditunjukkan pada Gambar. 1-5. Sementara satu pekerjaan sedang menunggu
I/O selesai, pekerjaan lain bisa menggunakan CPU. Jika cukup banyak pekerjaan dapat diadakan
di memori utama sekaligus, CPU dapat tetap sibuk hampir 100% sepanjang waktu.
Memiliki banyak pekerjaan dengan aman di memori sekaligus membutuhkan perangkat keras khusus untuk melindungi
setiap pekerjaan melawan pengintaian dan kerusakan oleh yang lain, tetapi 360 dan lainnya
sistem generasi ketiga dilengkapi dengan perangkat keras ini.

Another major feature present in third-generation operating systems was the
ability to read jobs from cards onto the disk as soon as they were brought to the
computer room. Then, whenever a running job finished, the operating system could
load a new job from the disk into the now-empty partition and run it. This technique is called spooling (from Simultaneous Peripheral Operation On Line) and
was also used for output. With spooling, the 1401s were no longer needed, and
much carrying of tapes disappeared.

Fitur utama lain yang ada dalam sistem operasi generasi ketiga adalah
kemampuan untuk membaca pekerjaan dari kartu ke disk segera setelah dibawa ke
ruang komputer. Kemudian, setiap kali pekerjaan yang sedang berjalan selesai, sistem operasi dapat
memuat pekerjaan baru dari disk ke partisi yang sekarang kosong dan menjalankannya. Teknik ini disebut spooling (dari Simultaneous Peripheral Operation On Line) dan
juga digunakan untuk keluaran. Dengan spooling, 1401 tidak lagi diperlukan, dan
banyak membawa kaset menghilang.

Although third-generation operating systems were well suited for big scientific
calculations and massive commercial data-processing runs, they were still basically
batch systems. Many programmers pined for the first-generation days when they
had the machine all to themselves for a few hours, so they could debug their programs quickly. With third-generation systems, the time between submitting a job
and getting back the output was often several hours, so a single misplaced comma
could cause a compilation to fail, and the programmer to waste half a day. Programmers did not like that very much.

Meskipun sistem operasi generasi ketiga sangat cocok untuk ilmiah besar
perhitungan dan pemrosesan data komersial besar-besaran, pada dasarnya mereka masih
sistem batch. Banyak programmer merindukan hari-hari generasi pertama ketika mereka
memiliki mesin untuk diri mereka sendiri selama beberapa jam, sehingga mereka dapat men-debug program mereka dengan cepat. Dengan sistem generasi ketiga, waktu antara mengirimkan pekerjaan
dan mendapatkan kembali hasilnya seringkali beberapa jam, jadi satu koma salah tempat
dapat menyebabkan kompilasi gagal, dan pemrogram membuang waktu setengah hari. Programmer sangat tidak menyukainya.

This desire for quick response time paved the way for timesharing, a variant
of multiprogramming, in which each user has an online terminal. In a timesharing
system, if 20 users are logged in and 17 of them are thinking or talking or drinking
coffee, the CPU can be allocated in turn to the three jobs that want service. Since
people debugging programs usually issue short commands (e.g., compile a fiv epage procedure†) rather than long ones (e.g., sort a million-record file), the computer can provide fast, interactive service to a number of users and perhaps also
work on big batch jobs in the background when the CPU is otherwise idle. The
first general-purpose timesharing system, CTSS (Compatible Time Sharing System), was developed at M.I.T. on a specially modified 7094 (Corbato´ et al., 1962).
However, timesharing did not really become popular until the necessary protection
hardware became widespread during the third generation.

Keinginan untuk waktu respons yang cepat ini membuka jalan bagi pembagian waktu, sebuah varian
multiprogramming, di mana setiap pengguna memiliki terminal online. Dalam pembagian waktu
sistem, jika 20 pengguna masuk dan 17 dari mereka berpikir atau berbicara atau minum
kopi, CPU dapat dialokasikan secara bergantian ke tiga pekerjaan yang menginginkan layanan. Sejak
orang yang men-debug program biasanya mengeluarkan perintah pendek (misalnya, mengkompilasi prosedur lima halaman†) daripada yang panjang (misalnya, mengurutkan satu juta file rekaman), komputer dapat menyediakan layanan yang cepat dan interaktif ke sejumlah pengguna dan mungkin juga
mengerjakan pekerjaan batch besar di latar belakang saat CPU tidak digunakan. Itu
sistem timesharing tujuan umum pertama, CTSS (Compatible Time Sharing System), dikembangkan di M.I.T. pada 7094 yang dimodifikasi secara khusus (Corbato´ et al., 1962).
Namun, pembagian waktu tidak benar-benar menjadi populer sampai perlindungan yang diperlukan
perangkat keras menjadi luas selama generasi ketiga.

After the success of the CTSS system, M.I.T., Bell Labs, and General Electric
(at that time a major computer manufacturer) decided to embark on the development of a ‘‘computer utility,’’ that is, a machine that would support some hundreds
of simultaneous timesharing users. Their model was the electricity system—when
you need electric power, you just stick a plug in the wall, and within reason, as
much power as you need will be there. The designers of this system, known as
MULTICS (MULTiplexed Information and Computing Service), envisioned
one huge machine providing computing power for everyone in the Boston area.
The idea that machines 10,000 times faster than their GE-645 mainframe would be
sold (for well under $1000) by the millions only 40 years later was pure science
fiction. Sort of like the idea of supersonic trans-Atlantic undersea trains now.

Setelah keberhasilan sistem CTSS, M.I.T., Bell Labs, dan General Electric
(pada saat itu produsen komputer besar) memutuskan untuk memulai pengembangan '' utilitas komputer, '' yaitu, mesin yang akan mendukung beberapa ratus
pengguna timesharing simultan. Model mereka adalah sistem kelistrikan—ketika
Anda membutuhkan tenaga listrik, Anda cukup memasang steker di dinding, dan dengan alasan, sebagai
banyak kekuatan yang Anda butuhkan akan ada di sana. Perancang sistem ini, yang dikenal sebagai
MULTICS (Layanan Informasi dan Komputasi MULTIplexed), dibayangkan
satu mesin besar yang menyediakan daya komputasi untuk semua orang di wilayah Boston.
Gagasan bahwa mesin 10.000 kali lebih cepat daripada mainframe GE-645 mereka adalah
dijual (dengan harga di bawah $ 1000) oleh jutaan hanya 40 tahun kemudian adalah sains murni
fiksi. Semacam ide kereta bawah laut supersonik trans-Atlantik sekarang.

MULTICS was a mixed success. It was designed to support hundreds of users
on a machine only slightly more powerful than an Intel 386-based PC, although it
had much more I/O capacity. This is not quite as crazy as it sounds, since in those
days people knew how to write small, efficient programs, a skill that has subsequently been completely lost. There were many reasons that MULTICS did not
take over the world, not the least of which is that it was written in the PL/I programming language, and the PL/I compiler was years late and barely worked at all
when it finally arrived. In addition, MULTICS was enormously ambitious for its
time, much like Charles Babbage’s analytical engine in the nineteenth century.

MULTICS adalah sukses campuran. Itu dirancang untuk mendukung ratusan pengguna
pada mesin hanya sedikit lebih kuat daripada PC berbasis Intel 386, meskipun
memiliki lebih banyak kapasitas I/O. Ini tidak terlalu gila kedengarannya, karena di dalamnya
hari orang tahu bagaimana menulis kecil, program yang efisien, keterampilan yang kemudian benar-benar hilang. Ada banyak alasan mengapa MULTICS tidak
mengambil alih dunia, tidak sedikit yang ditulis dalam bahasa pemrograman PL/I, dan kompiler PL/I terlambat bertahun-tahun dan hampir tidak berfungsi sama sekali
ketika akhirnya tiba. Selain itu, MULTICS sangat ambisius untuk
waktu, seperti mesin analitik Charles Babbage di abad kesembilan belas.

To make a long story short, MULTICS introduced many seminal ideas into the
computer literature, but turning it into a serious product and a major commercial
success was a lot harder than anyone had expected. Bell Labs dropped out of the
project, and General Electric quit the computer business altogether. Howev er,
M.I.T. persisted and eventually got MULTICS working. It was ultimately sold as a
commercial product by the company (Honeywell) that bought GE’s computer business and was installed by about 80 major companies and universities worldwide.
While their numbers were small, MULTICS users were fiercely loyal. General
Motors, Ford, and the U.S. National Security Agency, for example, shut down their
MULTICS systems only in the late 1990s, 30 years after MULTICS was released,
after years of trying to get Honeywell to update the hardware.

Untuk mempersingkat cerita, MULTICS memperkenalkan banyak ide mani ke dalam
literatur komputer, tetapi mengubahnya menjadi produk yang serius dan komersial utama
kesuksesan jauh lebih sulit daripada yang diperkirakan siapa pun. Bell Labs keluar dari
proyek, dan General Electric keluar dari bisnis komputer sama sekali. Namun,
M.I.T. bertahan dan akhirnya membuat MULTICS bekerja. Itu akhirnya dijual sebagai
produk komersial oleh perusahaan (Honeywell) yang membeli bisnis komputer GE dan dipasang oleh sekitar 80 perusahaan besar dan universitas di seluruh dunia.
Meskipun jumlahnya sedikit, pengguna MULTICS sangat setia. Umum
Motors, Ford, dan Badan Keamanan Nasional AS, misalnya, menutup
Sistem MULTICS hanya di akhir 1990-an, 30 tahun setelah MULTICS dirilis,
setelah bertahun-tahun mencoba membuat Honeywell memperbarui perangkat kerasnya.

By the end of the 20th century, the concept of a computer utility had fizzled
out, but it may well come back in the form of cloud computing, in which relatively small computers (including smartphones, tablets, and the like) are connected to servers in vast and distant data centers where all the computing is done,
with the local computer just handling the user interface. The motivation here is
that most people do not want to administrate an increasingly complex and finicky
computer system and would prefer to have that work done by a team of professionals, for example, people working for the company running the data center. E-commerce is already evolving in this direction, with various companies running emails
on multiprocessor servers to which simple client machines connect, very much in
the spirit of the MULTICS design.

Pada akhir abad ke-20, konsep utilitas komputer telah gagal
keluar, tetapi mungkin kembali dalam bentuk komputasi awan, di mana komputer yang relatif kecil (termasuk smartphone, tablet, dan sejenisnya) terhubung ke server di pusat data yang luas dan jauh di mana semua komputasi dilakukan,
dengan komputer lokal hanya menangani antarmuka pengguna. Motivasi disini adalah
bahwa kebanyakan orang tidak ingin administrasi yang semakin kompleks dan rewel
sistem komputer dan lebih suka pekerjaan itu dilakukan oleh tim profesional, misalnya, orang yang bekerja untuk perusahaan yang menjalankan pusat data. E-commerce sudah berkembang ke arah ini, dengan berbagai perusahaan menjalankan email
pada server multiprosesor yang terhubung dengan mesin klien sederhana, sangat banyak
semangat desain MULTICS.

Despite its lack of commercial success, MULTICS had a huge influence on
subsequent operating systems (especially UNIX and its derivatives, FreeBSD,
Linux, iOS, and Android). It is described in several papers and a book (Corbato´ et
al., 1972; Corbato´ and Vyssotsky, 1965; Daley and Dennis, 1968; Organick, 1972;
and Saltzer, 1974). It also has an active Website, located at www.multicians.org,
with much information about the system, its designers, and its users.

Meskipun kurang sukses secara komersial, MULTICS memiliki pengaruh besar pada
sistem operasi berikutnya (terutama UNIX dan turunannya, FreeBSD,
Linux, iOS, dan Android). Hal ini dijelaskan dalam beberapa makalah dan buku (Corbato´ et
al., 1972; Corbato´ dan Vyssotsky, 1965; Daley dan Dennis, 1968; Organik, 1972;
dan Saltzer, 1974). Ia juga memiliki Situs Web aktif, yang terletak di www.multicians.org,
dengan banyak informasi tentang sistem, perancangnya, dan penggunanya.

Another major development during the third generation was the phenomenal
growth of minicomputers, starting with the DEC PDP-1 in 1961. The PDP-1 had
only 4K of 18-bit words, but at $120,000 per machine (less than 5% of the price of
a 7094), it sold like hotcakes. For certain kinds of nonnumerical work, it was almost as fast as the 7094 and gav e birth to a whole new industry. It was quickly followed by a series of other PDPs (unlike IBM’s family, all incompatible) culminating in the PDP-11.

Perkembangan besar lainnya selama generasi ketiga adalah fenomenal
pertumbuhan komputer mini, dimulai dengan DEC PDP-1 pada tahun 1961. PDP-1 memiliki
hanya 4K kata 18-bit, tetapi pada $ 120.000 per mesin (kurang dari 5% dari harga
a 7094), itu dijual seperti kacang goreng. Untuk jenis pekerjaan nonnumerik tertentu, itu hampir secepat tahun 7094 dan melahirkan industri yang sama sekali baru. Itu dengan cepat diikuti oleh serangkaian PDP lain (tidak seperti keluarga IBM, semuanya tidak kompatibel) yang berpuncak pada PDP-11.

One of the computer scientists at Bell Labs who had worked on the MULTICS
project, Ken Thompson, subsequently found a small PDP-7 minicomputer that no
one was using and set out to write a stripped-down, one-user version of MULTICS.
This work later developed into the UNIX operating system, which became popular
in the academic world, with government agencies, and with many companies.

Salah satu ilmuwan komputer di Bell Labs yang pernah mengerjakan MULTICS
proyek, Ken Thompson, kemudian menemukan komputer mini PDP-7 kecil yang tidak
salah satunya menggunakan dan mulai menulis MULTICS versi satu pengguna yang dilucuti.
Karya ini kemudian berkembang menjadi sistem operasi UNIX, yang menjadi populer
di dunia akademik, dengan instansi pemerintah, dan dengan banyak perusahaan.

The history of UNIX has been told elsewhere (e.g., Salus, 1994). Part of that
story will be given in Chap. 10. For now, suffice it to say that because the source
code was widely available, various organizations developed their own (incompatible) versions, which led to chaos. Two major versions developed, System V, from
AT&T, and BSD (Berkeley Software Distribution) from the University of California at Berkeley. These had minor variants as well. To make it possible to write
programs that could run on any UNIX system, IEEE developed a standard for
UNIX, called POSIX, that most versions of UNIX now support. POSIX defines a
minimal system-call interface that conformant UNIX systems must support. In
fact, some other operating systems now also support the POSIX interface.

Sejarah UNIX telah diceritakan di tempat lain (misalnya, Salus, 1994). Bagian dari itu
cerita akan diberikan di Bab. 10. Untuk saat ini, cukup dikatakan demikian karena sumbernya
kode tersedia secara luas, berbagai organisasi mengembangkan versi mereka sendiri (tidak kompatibel), yang menyebabkan kekacauan. Dua versi utama dikembangkan, Sistem V, dari
AT&T, dan BSD (Berkeley Software Distribution) dari University of California di Berkeley. Ini memiliki varian kecil juga. Untuk memungkinkan menulis
program yang dapat berjalan pada sistem UNIX apa pun, IEEE mengembangkan standar untuk
UNIX, disebut POSIX, yang sekarang didukung oleh sebagian besar versi UNIX. POSIX mendefinisikan a
antarmuka panggilan sistem minimal yang harus didukung oleh sistem UNIX yang sesuai. Di
faktanya, beberapa sistem operasi lain sekarang juga mendukung antarmuka POSIX.

As an aside, it is worth mentioning that in 1987, the author released a small
clone of UNIX, called MINIX, for educational purposes. Functionally, MINIX is
very similar to UNIX, including POSIX support. Since that time, the original version has evolved into MINIX 3, which is highly modular and focused on very high
reliability. It has the ability to detect and replace faulty or even crashed modules
(such as I/O device drivers) on the fly without a reboot and without disturbing running programs. Its focus is on providing very high dependability and availability.
A book describing its internal operation and listing the source code in an appendix
is also available (Tanenbaum and Woodhull, 2006). The MINIX 3 system is available for free (including all the source code) over the Internet at www.minix3.org.

Sebagai tambahan, perlu disebutkan bahwa pada tahun 1987, penulis merilis sedikit
tiruan dari UNIX, yang disebut MINIX, untuk tujuan pendidikan. Secara fungsional, MINIX adalah
sangat mirip dengan UNIX, termasuk dukungan POSIX. Sejak saat itu, versi aslinya telah berkembang menjadi MINIX 3, yang sangat modular dan berfokus pada yang sangat tinggi
keandalan. Ia memiliki kemampuan untuk mendeteksi dan mengganti modul yang rusak atau bahkan macet
(seperti driver perangkat I/O) dengan cepat tanpa reboot dan tanpa mengganggu program yang sedang berjalan. Fokusnya adalah menyediakan ketergantungan dan ketersediaan yang sangat tinggi.
Sebuah buku yang menjelaskan operasi internal dan daftar kode sumber dalam lampiran
juga tersedia (Tanenbaum dan Woodhull, 2006). Sistem MINIX 3 tersedia secara gratis (termasuk semua kode sumber) melalui Internet di www.minix3.org.

The desire for a free production (as opposed to educational) version of MINIX
led a Finnish student, Linus Torvalds, to write Linux. This system was directly
inspired by and developed on MINIX and originally supported various MINIX features (e.g., the MINIX file system). It has since been extended in many ways by
many people but still retains some underlying structure common to MINIX and to
UNIX. Readers interested in a detailed history of Linux and the open source
movement might want to read Glyn Moody’s (2001) book. Most of what will be
said about UNIX in this book thus applies to System V, MINIX, Linux, and other
versions and clones of UNIX as well.

Keinginan untuk produksi gratis (sebagai lawan dari pendidikan) versi MINIX
memimpin seorang mahasiswa Finlandia, Linus Torvalds, untuk menulis Linux. Sistem ini secara langsung
terinspirasi oleh dan dikembangkan pada MINIX dan awalnya mendukung berbagai fitur MINIX (mis., Sistem file MINIX). Sejak itu telah diperpanjang dalam banyak cara oleh
banyak orang tetapi masih mempertahankan beberapa struktur dasar yang umum untuk MINIX dan untuk
UNIX. Pembaca yang tertarik dengan sejarah rinci Linux dan open source
gerakan mungkin ingin membaca buku Glyn Moody (2001). Sebagian besar dari apa yang akan terjadi
dikatakan tentang UNIX dalam buku ini dengan demikian berlaku untuk Sistem V, MINIX, Linux, dan lainnya
versi dan klon UNIX juga.

1.2.4 The Fourth Generation (1980–Present): Personal Computers
1.2.4 Generasi Keempat (1980–Sekarang): Komputer Pribadi

With the development of LSI (Large Scale Integration) circuits—chips containing thousands of transistors on a square centimeter of silicon—the age of the
personal computer dawned. In terms of architecture, personal computers (initially
called microcomputers) were not all that different from minicomputers of the
PDP-11 class, but in terms of price they certainly were different. Where the
minicomputer made it possible for a department in a company or university to have
its own computer, the microprocessor chip made it possible for a single individual
to have his or her own personal computer.

Dengan berkembangnya sirkuit LSI (Large Scale Integration)—chip yang mengandung ribuan transistor pada satu sentimeter persegi silikon—usia
komputer pribadi muncul. Dalam hal arsitektur, komputer pribadi (awalnya
disebut mikrokomputer) tidak jauh berbeda dari komputer mini
Kelas PDP-11, tapi dari segi harga tentu berbeda. Dimana
komputer mini memungkinkan departemen di perusahaan atau universitas untuk memiliki
komputernya sendiri, chip mikroprosesor memungkinkan untuk satu individu
memiliki komputer pribadinya sendiri.

In 1974, when Intel came out with the 8080, the first general-purpose 8-bit
CPU, it wanted an operating system for the 8080, in part to be able to test it. Intel
asked one of its consultants, Gary Kildall, to write one. Kildall and a friend first
built a controller for the newly released Shugart Associates 8-inch floppy disk and
hooked the floppy disk up to the 8080, thus producing the first microcomputer with
a disk. Kildall then wrote a disk-based operating system called CP/M (Control
Program for Microcomputers) for it. Since Intel did not think that disk-based
microcomputers had much of a future, when Kildall asked for the rights to CP/M,
Intel granted his request. Kildall then formed a company, Digital Research, to further develop and sell CP/M

Pada tahun 1974, ketika Intel keluar dengan 8080, tujuan umum pertama 8-bit
CPU, ia menginginkan sistem operasi untuk 8080, sebagian untuk dapat mengujinya. Intel
meminta salah satu konsultannya, Gary Kildall, untuk menulis satu. Kildall dan seorang teman dulu
membuat pengontrol untuk floppy disk 8 inci Shugart Associates yang baru dirilis dan
menghubungkan floppy disk hingga 8080, sehingga menghasilkan komputer mikro pertama dengan
sebuah disk. Kildall kemudian menulis sistem operasi berbasis disk yang disebut CP/M (Kontrol
Program untuk Mikrokomputer) untuk itu. Karena Intel tidak berpikir bahwa berbasis disk
mikrokomputer memiliki banyak masa depan, ketika Kildall meminta hak atas CP/M,
Intel mengabulkan permintaannya. Kildall kemudian membentuk sebuah perusahaan, Digital Research, untuk lebih mengembangkan dan menjual CP/M

In 1977, Digital Research rewrote CP/M to make it suitable for running on the
many microcomputers using the 8080, Zilog Z80, and other CPU chips. Many application programs were written to run on CP/M, allowing it to completely dominate the world of microcomputing for about 5 years.

Pada tahun 1977, Digital Research menulis ulang CP/M agar cocok untuk dijalankan di
banyak mikrokomputer yang menggunakan 8080, Zilog Z80, dan chip CPU lainnya. Banyak program aplikasi yang ditulis untuk dijalankan pada CP/M, memungkinkannya untuk sepenuhnya mendominasi dunia mikrokomputer selama sekitar 5 tahun.

In the early 1980s, IBM designed the IBM PC and looked around for software
to run on it. People from IBM contacted Bill Gates to license his BASIC interpreter. They also asked him if he knew of an operating system to run on the PC.
Gates suggested that IBM contact Digital Research, then the world’s dominant operating systems company. Making what was surely the worst business decision in
recorded history, Kildall refused to meet with IBM, sending a subordinate instead.
To make matters even worse, his lawyer even refused to sign IBM’s nondisclosure
agreement covering the not-yet-announced PC. Consequently, IBM went back to
Gates asking if he could provide them with an operating system.

Pada awal 1980-an, IBM merancang PC IBM dan mencari-cari perangkat lunak
untuk berlari di atasnya. Orang-orang dari IBM menghubungi Bill Gates untuk melisensikan penerjemah BASIC-nya. Mereka juga bertanya apakah dia tahu sistem operasi yang bisa dijalankan di PC.
Gates menyarankan agar IBM menghubungi Digital Research, yang saat itu merupakan perusahaan sistem operasi yang dominan di dunia. Membuat apa yang pasti merupakan keputusan bisnis terburuk dalam
mencatat sejarah, Kildall menolak bertemu dengan IBM, malah mengirim bawahan.
Lebih buruk lagi, pengacaranya bahkan menolak menandatangani kerahasiaan IBM
perjanjian yang mencakup PC yang belum diumumkan. Akibatnya, IBM kembali ke
Gates bertanya apakah dia bisa memberi mereka sistem operasi.

When IBM came back, Gates realized that a local computer manufacturer,
Seattle Computer Products, had a suitable operating system, DOS (Disk Operating System). He approached them and asked to buy it (allegedly for $75,000),
which they readily accepted. Gates then offered IBM a DOS/BASIC package,
which IBM accepted. IBM wanted certain modifications, so Gates hired the person who wrote DOS, Tim Paterson, as an employee of Gates’ fledgling company,
Microsoft, to make them. The revised system was renamed MS-DOS (MicroSoft
Disk Operating System) and quickly came to dominate the IBM PC market. A
key factor here was Gates’ (in retrospect, extremely wise) decision to sell MS-DOS
to computer companies for bundling with their hardware, compared to Kildall’s
attempt to sell CP/M to end users one at a time (at least initially). After all this
transpired, Kildall died suddenly and unexpectedly from causes that have not been
fully disclosed.

Ketika IBM kembali, Gates menyadari bahwa produsen komputer lokal,
Seattle Computer Products, memiliki sistem operasi yang cocok, DOS (Disk Operating System). Dia mendekati mereka dan meminta untuk membelinya (diduga seharga $75.000),
yang mereka terima dengan senang hati. Gates kemudian menawarkan paket DOS/BASIC kepada IBM,
yang diterima IBM. IBM menginginkan modifikasi tertentu, jadi Gates mempekerjakan orang yang menulis DOS, Tim Paterson, sebagai karyawan perusahaan baru Gates,
Microsoft, untuk membuatnya. Sistem yang direvisi diubah namanya menjadi MS-DOS (MicroSoft
Disk Operating System) dan dengan cepat mendominasi pasar PC IBM. SEBUAH
faktor kunci di sini adalah keputusan Gates (dalam retrospeksi, sangat bijaksana) untuk menjual MS-DOS
ke perusahaan komputer untuk bundling dengan perangkat keras mereka, dibandingkan dengan Kildall's
mencoba menjual CP/M kepada pengguna akhir satu per satu (setidaknya pada awalnya). Setelah semua ini
terjadi, Kildall meninggal tiba-tiba dan tak terduga dari penyebab yang belum
diungkapkan sepenuhnya.

By the time the successor to the IBM PC, the IBM PC/AT, came out in 1983
with the Intel 80286 CPU, MS-DOS was firmly entrenched and CP/M was on its
last legs. MS-DOS was later widely used on the 80386 and 80486. Although the
initial version of MS-DOS was fairly primitive, subsequent versions included more
advanced features, including many taken from UNIX. (Microsoft was well aware
of UNIX, even selling a microcomputer version of it called XENIX during the
company’s early years.)

Pada saat penerus IBM PC, IBM PC/AT, keluar pada tahun 1983
dengan CPU Intel 80286, MS-DOS tertanam kuat dan CP/M berada di posisinya
kaki terakhir. MS-DOS kemudian banyak digunakan pada 80386 dan 80486. Meskipun
versi awal MS-DOS cukup primitif, versi selanjutnya termasuk lebih banyak
fitur-fitur canggih, termasuk banyak yang diambil dari UNIX. (Microsoft sangat menyadari
UNIX, bahkan menjual versi mikrokomputer yang disebut XENIX selama
tahun-tahun awal perusahaan.)

CP/M, MS-DOS, and other operating systems for early microcomputers were
all based on users typing in commands from the keyboard. That eventually changed due to research done by Doug Engelbart at Stanford Research Institute in the
1960s. Engelbart invented the Graphical User Interface, complete with windows,
icons, menus, and mouse. These ideas were adopted by researchers at Xerox PARC
and incorporated into machines they built.

CP/M, MS-DOS, dan sistem operasi lain untuk mikrokomputer awal adalah
semua berdasarkan pengguna yang mengetikkan perintah dari keyboard. Itu akhirnya berubah karena penelitian yang dilakukan oleh Doug Engelbart di Stanford Research Institute di
1960-an. Engelbart menemukan Graphical User Interface, lengkap dengan windows,
ikon, menu, dan mouse. Ide-ide ini diadopsi oleh para peneliti di Xerox PARC
dan dimasukkan ke dalam mesin yang mereka buat.

One day, Steve Jobs, who co-invented the Apple computer in his garage, visited PARC, saw a GUI, and instantly realized its potential value, something Xerox
management famously did not. This strategic blunder of gargantuan proportions
led to a book entitled Fumbling the Future (Smith and Alexander, 1988). Jobs then
embarked on building an Apple with a GUI. This project led to the Lisa, which
was too expensive and failed commercially. Jobs’ second attempt, the Apple Macintosh, was a huge success, not only because it was much cheaper than the Lisa,
but also because it was user friendly, meaning that it was intended for users who
not only knew nothing about computers but furthermore had absolutely no intention whatsoever of learning. In the creative world of graphic design, professional
digital photography, and professional digital video production, Macintoshes are
very widely used and their users are very enthusiastic about them. In 1999, Apple
adopted a kernel derived from Carnegie Mellon University’s Mach microkernel
which was originally developed to replace the kernel of BSD UNIX. Thus, Mac
OS X is a UNIX-based operating system, albeit with a very distinctive interface.

Suatu hari, Steve Jobs, yang ikut menciptakan komputer Apple di garasinya, mengunjungi PARC, melihat GUI, dan langsung menyadari nilai potensialnya, sesuatu yang Xerox
manajemen terkenal tidak. Kesalahan strategis dengan proporsi raksasa ini
menghasilkan sebuah buku berjudul Meraba-raba Masa Depan (Smith dan Alexander, 1988). Pekerjaan kemudian
memulai membangun Apple dengan GUI. Proyek ini mengarah ke Lisa, yang
terlalu mahal dan gagal secara komersial. Upaya kedua Jobs, Apple Macintosh, sukses besar, bukan hanya karena jauh lebih murah daripada Lisa,
tetapi juga karena ramah pengguna, artinya ditujukan untuk pengguna yang
tidak hanya tidak tahu apa-apa tentang komputer tetapi juga sama sekali tidak memiliki niat untuk belajar. Dalam dunia kreatif desain grafis, profesional
fotografi digital, dan produksi video digital profesional, Macintoshes adalah
sangat banyak digunakan dan pengguna mereka sangat antusias tentang mereka. Pada tahun 1999, Apple
mengadopsi kernel yang berasal dari mikrokernel Mach Universitas Carnegie Mellon
yang awalnya dikembangkan untuk menggantikan kernel BSD UNIX. Jadi, Mac
OS X adalah sistem operasi berbasis UNIX, meskipun dengan antarmuka yang sangat khas.

When Microsoft decided to build a successor to MS-DOS, it was strongly
influenced by the success of the Macintosh. It produced a GUI-based system called Windows, which originally ran on top of MS-DOS (i.e., it was more like a shell
than a true operating system). For about 10 years, from 1985 to 1995, Windows
was just a graphical environment on top of MS-DOS. However, starting in 1995 a
freestanding version, Windows 95, was released that incorporated many operating
system features into it, using the underlying MS-DOS system only for booting and
running old MS-DOS programs. In 1998, a slightly modified version of this system, called Windows 98 was released. Nevertheless, both Windows 95 and Windows 98 still contained a large amount of 16-bit Intel assembly language.

Ketika Microsoft memutuskan untuk membangun penerus MS-DOS, itu sangat
dipengaruhi oleh keberhasilan Macintosh. Ini menghasilkan sistem berbasis GUI yang disebut Windows, yang awalnya berjalan di atas MS-DOS (yaitu, itu lebih seperti shell
dari sistem operasi yang sebenarnya). Selama sekitar 10 tahun, dari 1985 hingga 1995, Windows
hanyalah lingkungan grafis di atas MS-DOS. Namun, mulai tahun 1995 a
versi berdiri bebas, Windows 95, dirilis yang menggabungkan banyak operasi
fitur sistem ke dalamnya, menggunakan sistem MS-DOS yang mendasarinya hanya untuk booting dan
menjalankan program MS-DOS lama. Pada tahun 1998, versi yang sedikit dimodifikasi dari sistem ini, yang disebut Windows 98 dirilis. Namun demikian, baik Windows 95 dan Windows 98 masih mengandung sejumlah besar bahasa rakitan Intel 16-bit.

Another Microsoft operating system, Windows NT (where the NT stands for
New Technology), which was compatible with Windows 95 at a certain level, but a
complete rewrite from scratch internally. It was a full 32-bit system. The lead designer for Windows NT was David Cutler, who was also one of the designers of the
VAX VMS operating system, so some ideas from VMS are present in NT. In fact,
so many ideas from VMS were present in it that the owner of VMS, DEC, sued
Microsoft. The case was settled out of court for an amount of money requiring
many digits to express. Microsoft expected that the first version of NT would kill
off MS-DOS and all other versions of Windows since it was a vastly superior system, but it fizzled. Only with Windows NT 4.0 did it finally catch on in a big way,
especially on corporate networks. Version 5 of Windows NT was renamed Windows 2000 in early 1999. It was intended to be the successor to both Windows 98
and Windows NT 4.0.

Sistem operasi Microsoft lainnya, Windows NT (di mana NT adalah singkatan dari
Teknologi Baru), yang kompatibel dengan Windows 95 pada tingkat tertentu, tetapi a
menulis ulang lengkap dari awal secara internal. Itu adalah sistem 32-bit penuh. Perancang utama untuk Windows NT adalah David Cutler, yang juga merupakan salah satu perancang dari
Sistem operasi VAX VMS, jadi beberapa ide dari VMS hadir di NT. Faktanya,
begitu banyak ide dari VMS yang hadir di dalamnya sehingga pemilik VMS, DEC, menggugat
Microsoft. Kasus ini diselesaikan di luar pengadilan untuk sejumlah uang yang membutuhkan
banyak angka untuk diekspresikan. Microsoft berharap bahwa versi pertama NT akan membunuh
mematikan MS-DOS dan semua versi Windows lainnya karena ini adalah sistem yang jauh lebih unggul, tetapi gagal. Hanya dengan Windows NT 4.0 akhirnya berhasil,
terutama pada jaringan perusahaan. Versi 5 Windows NT berganti nama menjadi Windows 2000 pada awal 1999. Ini dimaksudkan untuk menjadi penerus kedua Windows 98
dan Windows NT 4.0.

That did not quite work out either, so Microsoft came out with yet another version of Windows 98 called Windows Me (Millennium Edition). In 2001, a
slightly upgraded version of Windows 2000, called Windows XP was released.
That version had a much longer run (6 years), basically replacing all previous versions of Windows.

Itu juga tidak berhasil, jadi Microsoft mengeluarkan versi lain dari Windows 98 yang disebut Windows Me (Edisi Milenium). Pada tahun 2001,
sedikit upgrade versi Windows 2000, yang disebut Windows XP dirilis.
Versi itu berjalan lebih lama (6 tahun), pada dasarnya menggantikan semua versi Windows sebelumnya.

Still the spawning of versions continued unabated. After Windows 2000,
Microsoft broke up the Windows family into a client and a server line. The client
line was based on XP and its successors, while the server line included Windows
Server 2003 and Windows 2008. A third line, for the embedded world, appeared a
little later. All of these versions of Windows forked off their variations in the form
of service packs. It was enough to drive some administrators (and writers of operating systems textbooks) balmy.

Masih pemijahan versi terus berlanjut. Setelah Windows 2000,
Microsoft memecah keluarga Windows menjadi klien dan baris server. Klien
baris didasarkan pada XP dan penerusnya, sedangkan baris server termasuk Windows
Server 2003 dan Windows 2008. Baris ketiga, untuk dunia tertanam, muncul sebagai
sedikit kemudian. Semua versi Windows ini mengubah variasinya dalam bentuk
dari paket layanan. Itu sudah cukup untuk membuat beberapa administrator (dan penulis buku teks sistem operasi) nyaman.

Then in January 2007, Microsoft finally released the successor to Windows
XP, called Vista. It came with a new graphical interface, improved security, and
many new or upgraded user programs. Microsoft hoped it would replace Windows
XP completely, but it never did. Instead, it received much criticism and a bad press,
mostly due to the high system requirements, restrictive licensing terms, and support for Digital Rights Management, techniques that made it harder for users to
copy protected material.

Kemudian pada Januari 2007, Microsoft akhirnya merilis penerus Windows
XP, disebut Vista. Itu datang dengan antarmuka grafis baru, keamanan yang ditingkatkan, dan
banyak program pengguna baru atau yang ditingkatkan. Microsoft berharap itu akan menggantikan Windows
XP sepenuhnya, tetapi tidak pernah berhasil. Sebaliknya, ia menerima banyak kritik dan pers yang buruk,
sebagian besar karena persyaratan sistem yang tinggi, persyaratan lisensi yang ketat, dan dukungan untuk Manajemen Hak Digital, teknik yang mempersulit pengguna untuk
menyalin materi yang dilindungi.

With the arrival of Windows 7, a new and much less resource hungry version
of the operating system, many people decided to skip Vista altogether. Windows 7
did not introduce too many new features, but it was relatively small and quite stable. In less than three weeks, Windows 7 had obtained more market share than
Vista in seven months. In 2012, Microsoft launched its successor, Windows 8, an
operating system with a completely new look and feel, geared for touch screens.
The company hopes that the new design will become the dominant operating system on a much wider variety of devices: desktops, laptops, notebooks, tablets,
phones, and home theater PCs. So far, howev er, the market penetration is slow
compared to Windows 7.

Dengan kedatangan Windows 7, versi baru yang haus sumber daya jauh lebih sedikit
dari sistem operasi, banyak orang memutuskan untuk melewatkan Vista sama sekali. Windows 7
tidak memperkenalkan terlalu banyak fitur baru, tetapi relatif kecil dan cukup stabil. Dalam waktu kurang dari tiga minggu, Windows 7 telah memperoleh lebih banyak pangsa pasar daripada
Vista dalam tujuh bulan. Pada tahun 2012, Microsoft meluncurkan penggantinya, Windows 8, dan
sistem operasi dengan tampilan dan nuansa yang benar-benar baru, ditujukan untuk layar sentuh.
Perusahaan berharap bahwa desain baru akan menjadi sistem operasi yang dominan pada berbagai perangkat yang lebih luas: desktop, laptop, notebook, tablet,
telepon, dan PC home theater. Namun sejauh ini penetrasi pasarnya lambat
dibandingkan dengan Windows 7.

The other major contender in the personal computer world is UNIX (and its
various derivatives). UNIX is strongest on network and enterprise servers but is
also often present on desktop computers, notebooks, tablets, and smartphones. On
x86-based computers, Linux is becoming a popular alternative to Windows for students and increasingly many corporate users

Pesaing utama lainnya di dunia komputer pribadi adalah UNIX (dan
berbagai turunan). UNIX adalah yang terkuat di server jaringan dan perusahaan tetapi
juga sering hadir di komputer desktop, notebook, tablet, dan smartphone. Pada
komputer berbasis x86, Linux menjadi alternatif populer untuk Windows bagi pelajar dan semakin banyak pengguna korporat

As an aside, throughout this book we will use the term x86 to refer to all modern processors based on the family of instruction-set architectures that started with
the 8086 in the 1970s. There are many such processors, manufactured by companies like AMD and Intel, and under the hood they often differ considerably:
processors may be 32 bits or 64 bits with few or many cores and pipelines that may
be deep or shallow, and so on. Nevertheless, to the programmer, they all look quite
similar and they can all still run 8086 code that was written 35 years ago. Where
the difference is important, we will refer to explicit models instead—and use
x86-32 and x86-64 to indicate 32-bit and 64-bit variants.

Sebagai tambahan, di seluruh buku ini kita akan menggunakan istilah x86 untuk merujuk ke semua prosesor modern berdasarkan keluarga arsitektur set instruksi yang dimulai dengan
8086 pada 1970-an. Ada banyak prosesor seperti itu, yang diproduksi oleh perusahaan seperti AMD dan Intel, dan di bawah tenda mereka sering sangat berbeda:
prosesor mungkin 32 bit atau 64 bit dengan sedikit atau banyak inti dan saluran pipa yang mungkin
dalam atau dangkal, dan sebagainya. Namun demikian, bagi programmer, mereka semua terlihat cukup
serupa dan semuanya masih dapat menjalankan kode 8086 yang ditulis 35 tahun yang lalu. Di mana
perbedaannya penting, kami akan merujuk ke model eksplisit sebagai gantinya — dan gunakan
x86-32 dan x86-64 untuk menunjukkan varian 32-bit dan 64-bit.

FreeBSD is also a popular UNIX derivative, originating from the BSD project
at Berkeley. All modern Macintosh computers run a modified version of FreeBSD
(OS X). UNIX is also standard on workstations powered by high-performance
RISC chips. Its derivatives are widely used on mobile devices, such as those running iOS 7 or Android.

FreeBSD juga merupakan turunan UNIX yang populer, yang berasal dari proyek BSD
di Berkeley. Semua komputer Macintosh modern menjalankan versi modifikasi dari FreeBSD
(OSX). UNIX juga standar pada workstation yang didukung oleh kinerja tinggi
chip RISC. Turunannya banyak digunakan pada perangkat seluler, seperti yang menjalankan iOS 7 atau Android.

Many UNIX users, especially experienced programmers, prefer a commandbased interface to a GUI, so nearly all UNIX systems support a windowing system
called the X Window System (also known as X11) produced at M.I.T. This system handles the basic window management, allowing users to create, delete, move,
and resize windows using a mouse. Often a complete GUI, such as Gnome or
KDE, is available to run on top of X11, giving UNIX a look and feel something
like the Macintosh or Microsoft Windows, for those UNIX users who want such a
thing.

Banyak pengguna UNIX, terutama programmer berpengalaman, lebih memilih antarmuka berbasis perintah daripada GUI, sehingga hampir semua sistem UNIX mendukung sistem windowing.
disebut X Window System (juga dikenal sebagai X11) yang diproduksi di M.I.T. Sistem ini menangani manajemen jendela dasar, memungkinkan pengguna untuk membuat, menghapus, memindahkan,
dan mengubah ukuran jendela menggunakan mouse. Seringkali GUI lengkap, seperti Gnome atau
KDE, tersedia untuk dijalankan di atas X11, memberikan UNIX tampilan dan rasa sesuatu
seperti Macintosh atau Microsoft Windows, bagi para pengguna UNIX yang menginginkan
hal.

An interesting development that began taking place during the mid-1980s is
the growth of networks of personal computers running network operating systems and distributed operating systems (Tanenbaum and Van Steen, 2007). In a
network operating system, the users are aware of the existence of multiple computers and can log in to remote machines and copy files from one machine to another. Each machine runs its own local operating system and has its own local user
(or users)

Perkembangan menarik yang mulai terjadi pada pertengahan 1980-an adalah
pertumbuhan jaringan komputer pribadi yang menjalankan sistem operasi jaringan dan sistem operasi terdistribusi (Tanenbaum dan Van Steen, 2007). Di sebuah
sistem operasi jaringan, pengguna menyadari keberadaan beberapa komputer dan dapat masuk ke mesin jarak jauh dan menyalin file dari satu mesin ke mesin lainnya. Setiap mesin menjalankan sistem operasi lokalnya sendiri dan memiliki pengguna lokalnya sendiri
(atau pengguna)

Network operating systems are not fundamentally different from single-processor operating systems. They obviously need a network interface controller and
some low-level software to drive it, as well as programs to achieve remote login
and remote file access, but these additions do not change the essential structure of
the operating system

Sistem operasi jaringan pada dasarnya tidak berbeda dari sistem operasi prosesor tunggal. Mereka jelas membutuhkan pengontrol antarmuka jaringan dan
beberapa perangkat lunak tingkat rendah untuk menjalankannya, serta program untuk mencapai login jarak jauh
dan akses file jarak jauh, tetapi penambahan ini tidak mengubah struktur penting dari
sistem operasi

A distributed operating system, in contrast, is one that appears to its users as a
traditional uniprocessor system, even though it is actually composed of multiple
processors. The users should not be aware of where their programs are being run or
where their files are located; that should all be handled automatically and efficiently by the operating system.

Sebuah sistem operasi terdistribusi, sebaliknya, adalah salah satu yang muncul kepada penggunanya sebagai
sistem uniprosesor tradisional, meskipun sebenarnya terdiri dari beberapa
prosesor. Pengguna seharusnya tidak mengetahui di mana program mereka dijalankan atau
di mana file mereka berada; yang semuanya harus ditangani secara otomatis dan efisien oleh sistem operasi.

True distributed operating systems require more than just adding a little code
to a uniprocessor operating system, because distributed and centralized systems
differ in certain critical ways. Distributed systems, for example, often allow applications to run on several processors at the same time, thus requiring more complex
processor scheduling algorithms in order to optimize the amount of parallelism.

Sistem operasi terdistribusi sejati membutuhkan lebih dari sekadar menambahkan sedikit kode
ke sistem operasi uniprosesor, karena sistem terdistribusi dan terpusat
berbeda dalam cara-cara kritis tertentu. Sistem terdistribusi, misalnya, sering mengizinkan aplikasi untuk berjalan pada beberapa prosesor secara bersamaan, sehingga membutuhkan lebih banyak kompleks
algoritma penjadwalan prosesor untuk mengoptimalkan jumlah paralelisme.

Communication delays within the network often mean that these (and other)
algorithms must run with incomplete, outdated, or even incorrect information. This
situation differs radically from that in a single-processor system in which the operating system has complete information about the system state.

Keterlambatan komunikasi dalam jaringan sering berarti bahwa ini (dan lainnya)
algoritma harus berjalan dengan informasi yang tidak lengkap, usang, atau bahkan salah. Ini
situasi berbeda secara radikal dari sistem prosesor tunggal di mana sistem operasi memiliki informasi lengkap tentang status sistem.

1.2.5 The Fifth Generation (1990–Present): Mobile Computers
1.2.5 Generasi Kelima (1990–Sekarang): Komputer Seluler

Ever since detective Dick Tracy started talking to his ‘‘two-way radio wrist
watch’’ in the 1940s comic strip, people have craved a communication device they
could carry around wherever they went. The first real mobile phone appeared in
1946 and weighed some 40 kilos. You could take it wherever you went as long as
you had a car in which to carry it.

Sejak detektif Dick Tracy mulai berbicara dengan '' pergelangan tangan radio dua arahnya '
menonton '' di komik strip 1940-an, orang-orang mendambakan perangkat komunikasi mereka
bisa dibawa kemanapun mereka pergi. Ponsel asli pertama muncul di
1946 dan beratnya sekitar 40 kilogram. Anda bisa membawanya ke mana pun Anda pergi selama
Anda memiliki mobil untuk membawanya.

The first true handheld phone appeared in the 1970s and, at roughly one kilogram, was positively featherweight. It was affectionately known as ‘‘the brick.’’
Pretty soon everybody wanted one. Today, mobile phone penetration is close to
90% of the global population. We can make calls not just with our portable phones
and wrist watches, but soon with eyeglasses and other wearable items. Moreover,
the phone part is no longer that interesting. We receive email, surf the Web, text
our friends, play games, navigate around heavy traffic—and do not even think
twice about it.

Telepon genggam pertama yang benar muncul pada tahun 1970-an dan, dengan berat sekitar satu kilogram, secara positif memiliki kelas bulu. Itu dikenal sebagai '' batu bata. ''
Segera semua orang menginginkannya. Saat ini, penetrasi ponsel sudah dekat dengan
90% dari populasi dunia. Kami dapat melakukan panggilan tidak hanya dengan ponsel portabel kami
dan jam tangan, tetapi segera dengan kacamata dan barang-barang yang dapat dikenakan lainnya. Lebih-lebih lagi,
bagian telepon tidak lagi menarik. Kami menerima email, menjelajahi Web, SMS
teman-teman kita, bermain game, bernavigasi di lalu lintas padat—dan bahkan tidak berpikir
dua kali tentang itu.

While the idea of combining telephony and computing in a phone-like device
has been around since the 1970s also, the first real smartphone did not appear until
the mid-1990s when Nokia released the N9000, which literally combined two,
mostly separate devices: a phone and a PDA (Personal Digital Assistant). In 1997,
Ericsson coined the term smartphone for its GS88 ‘‘Penelope.’’

Sementara gagasan menggabungkan telepon dan komputasi dalam perangkat seperti telepon
telah ada sejak tahun 1970-an juga, smartphone asli pertama tidak muncul sampai
pertengahan 1990-an ketika Nokia merilis N9000, yang secara harfiah menggabungkan dua,
sebagian besar perangkat terpisah: telepon dan PDA (Personal Digital Assistant). Pada tahun 1997,
Ericsson menciptakan istilah smartphone untuk GS88-nya ''Penelope.''

Now that smartphones have become ubiquitous, the competition between the
various operating systems is fierce and the outcome is even less clear than in the
PC world. At the time of writing, Google’s Android is the dominant operating system with Apple’s iOS a clear second, but this was not always the case and all may
be different again in just a few years. If anything is clear in the world of smartphones, it is that it is not easy to stay king of the mountain for long.

Sekarang smartphone telah menjadi di mana-mana, persaingan antara
berbagai sistem operasi ganas dan hasilnya bahkan kurang jelas daripada di
Dunia PC. Pada saat penulisan, Android Google adalah sistem operasi yang dominan dengan iOS Apple yang jelas kedua, tetapi ini tidak selalu terjadi dan semua mungkin
menjadi berbeda lagi hanya dalam beberapa tahun. Jika ada yang jelas di dunia smartphone, tidak mudah untuk menjadi raja gunung untuk waktu yang lama.

After all, most smartphones in the first decade after their inception were running Symbian OS. It was the operating system of choice for popular brands like
Samsung, Sony Ericsson, Motorola, and especially Nokia. However, other operating systems like RIM’s Blackberry OS (introduced for smartphones in 2002) and
Apple’s iOS (released for the first iPhone in 2007) started eating into Symbian’s
market share. Many expected that RIM would dominate the business market, while
iOS would be the king of the consumer devices. Symbian’s market share plummeted. In 2011, Nokia ditched Symbian and announced it would focus on Windows Phone as its primary platform. For some time, Apple and RIM were the toast
of the town (although not nearly as dominant as Symbian had been), but it did not
take very long for Android, a Linux-based operating system released by Google in
2008, to overtake all its rivals

Lagi pula, sebagian besar smartphone dalam dekade pertama setelah peluncurannya menjalankan OS Symbian. Itu adalah sistem operasi pilihan untuk merek populer seperti
Samsung, Sony Ericsson, Motorola, dan terutama Nokia. Namun, sistem operasi lain seperti OS Blackberry RIM (diperkenalkan untuk smartphone pada tahun 2002) dan
Apple iOS (dirilis untuk iPhone pertama pada tahun 2007) mulai memakan Symbian's
saham. Banyak yang berharap RIM akan mendominasi pasar bisnis, sementara
iOS akan menjadi raja perangkat konsumen. Pangsa pasar Symbian anjlok. Pada tahun 2011, Nokia membuang Symbian dan mengumumkan akan fokus pada Windows Phone sebagai platform utamanya. Untuk beberapa waktu, Apple dan RIM bersulang
kota (walaupun tidak sedominan Symbian sebelumnya), tetapi tidak
butuh waktu sangat lama untuk Android, sistem operasi berbasis Linux yang dirilis oleh Google di
2008, untuk menyalip semua saingannya

For phone manufacturers, Android had the advantage that it was open source
and available under a permissive license. As a result, they could tinker with it and
adapt it to their own hardware with ease. Also, it has a huge community of developers writing apps, mostly in the familiar Java programming language. Even so,
the past years have shown that the dominance may not last, and Android’s competitors are eager to claw back some of its market share. We will look at Android in
detail in Sec. 10.8.

Untuk produsen ponsel, Android memiliki keunggulan karena bersifat open source
dan tersedia di bawah lisensi permisif. Akibatnya, mereka bisa mengotak-atiknya dan
menyesuaikannya dengan perangkat keras mereka sendiri dengan mudah. Juga, ia memiliki komunitas besar pengembang yang menulis aplikasi, sebagian besar dalam bahasa pemrograman Java yang sudah dikenal. Walaupun demikian,
beberapa tahun terakhir telah menunjukkan bahwa dominasi mungkin tidak bertahan lama, dan pesaing Android sangat ingin merebut kembali sebagian pangsa pasarnya. Kami akan melihat Android di
rinci di Sec. 10.8.

1.3 COMPUTER HARDWARE REVIEW
1.3 TINJAUAN PERANGKAT KERAS KOMPUTER

An operating system is intimately tied to the hardware of the computer it runs
on. It extends the computer’s instruction set and manages its resources. To work,
it must know a great deal about the hardware, at least about how the hardware appears to the programmer. For this reason, let us briefly review computer hardware
as found in modern personal computers. After that, we can start getting into the details of what operating systems do and how they work.

Sistem operasi terkait erat dengan perangkat keras komputer yang dijalankannya
pada. Ini memperluas set instruksi komputer dan mengelola sumber dayanya. Bekerja,
ia harus tahu banyak tentang perangkat keras, setidaknya tentang bagaimana perangkat keras itu tampak bagi programmer. Untuk alasan ini, mari kita tinjau secara singkat perangkat keras komputer
seperti yang ditemukan di komputer pribadi modern. Setelah itu, kita dapat mulai masuk ke detail tentang apa yang dilakukan sistem operasi dan bagaimana cara kerjanya.

Conceptually, a simple personal computer can be abstracted to a model resembling that of Fig. 1-6. The CPU, memory, and I/O devices are all connected by a
system bus and communicate with one another over it. Modern personal computers
have a more complicated structure, involving multiple buses, which we will look at
later. For the time being, this model will be sufficient. In the following sections,
we will briefly review these components and examine some of the hardware issues
that are of concern to operating system designers. Needless to say, this will be a
very compact summary. Many books have been written on the subject of computer
hardware and computer organization. Two well-known ones are by Tanenbaum
and Austin (2012) and Patterson and Hennessy (2013).

Secara konseptual, komputer pribadi sederhana dapat diabstraksikan menjadi model yang menyerupai Gambar 1-6. CPU, memori, dan perangkat I/O semuanya terhubung dengan a
sistem bus dan berkomunikasi satu sama lain di atasnya. Komputer pribadi modern
memiliki struktur yang lebih rumit, yang melibatkan banyak bus, yang akan kita lihat
nanti. Untuk saat ini, model ini akan cukup. Di bagian berikut,
kami akan meninjau secara singkat komponen-komponen ini dan memeriksa beberapa masalah perangkat keras
yang menjadi perhatian perancang sistem operasi. Tak perlu dikatakan, ini akan menjadi
ringkasan yang sangat kompak. Banyak buku telah ditulis tentang masalah komputer
perangkat keras dan organisasi komputer. Dua yang terkenal adalah oleh Tanenbaum
dan Austin (2012) dan Patterson dan Hennessy (2013).

The ‘‘brain’’ of the computer is the CPU. It fetches instructions from memory
and executes them. The basic cycle of every CPU is to fetch the first instruction
from memory, decode it to determine its type and operands, execute it, and then
fetch, decode, and execute subsequent instructions. The cycle is repeated until the
program finishes. In this way, programs are carried out.

''Otak'' komputer adalah CPU. Itu mengambil instruksi dari memori
dan mengeksekusi mereka. Siklus dasar setiap CPU adalah mengambil instruksi pertama
dari memori, decode untuk menentukan jenis dan operandnya, jalankan, dan kemudian
mengambil, mendekode, dan menjalankan instruksi selanjutnya. Siklus tersebut diulangi sampai
program selesai. Dengan cara ini, program dilakukan.

Each CPU has a specific set of instructions that it can execute. Thus an x86
processor cannot execute ARM programs and an ARM processor cannot execute
x86 programs. Because accessing memory to get an instruction or data word takes
much longer than executing an instruction, all CPUs contain some registers inside
to hold key variables and temporary results. Thus the instruction set generally contains instructions to load a word from memory into a register, and store a word
from a register into memory. Other instructions combine two operands from registers, memory, or both into a result, such as adding two words and storing the result
in a register or in memory

Setiap CPU memiliki serangkaian instruksi khusus yang dapat dieksekusi. Jadi x86
prosesor tidak dapat menjalankan program ARM dan prosesor ARM tidak dapat mengeksekusi
program x86. Karena mengakses memori untuk mendapatkan instruksi atau kata data membutuhkan
lebih lama dari mengeksekusi instruksi, semua CPU berisi beberapa register di dalamnya
untuk menahan variabel kunci dan hasil sementara. Jadi set instruksi umumnya berisi instruksi untuk memuat kata dari memori ke dalam register, dan menyimpan kata
dari register ke memori. Instruksi lain menggabungkan dua operan dari register, memori, atau keduanya menjadi hasil, seperti menambahkan dua kata dan menyimpan hasilnya
dalam register atau dalam memori

In addition to the general registers used to hold variables and temporary results, most computers have sev eral special registers that are visible to the programmer. One of these is the program counter, which contains the memory address of the next instruction to be fetched. After that instruction has been fetched,
the program counter is updated to point to its successor.

Selain register umum yang digunakan untuk menyimpan variabel dan hasil sementara, kebanyakan komputer memiliki beberapa register khusus yang dapat dilihat oleh programmer. Salah satunya adalah program counter, yang berisi alamat memori dari instruksi berikutnya yang akan diambil. Setelah instruksi itu diambil,
penghitung program diperbarui untuk menunjuk ke penggantinya.

Another register is the stack pointer, which points to the top of the current
stack in memory. The stack contains one frame for each procedure that has been
entered but not yet exited. A procedure’s stack frame holds those input parameters,
local variables, and temporary variables that are not kept in registers.

Register lain adalah penunjuk tumpukan, yang menunjuk ke atas arus
menumpuk di memori. Tumpukan berisi satu frame untuk setiap prosedur yang telah
masuk tapi belum keluar. Kerangka tumpukan prosedur menyimpan parameter input tersebut,
variabel lokal, dan variabel sementara yang tidak disimpan dalam register.

Yet another register is the PSW (Program Status Word). This register contains the condition code bits, which are set by comparison instructions, the CPU
priority, the mode (user or kernel), and various other control bits. User programs
may normally read the entire PSW but typically may write only some of its fields.
The PSW plays an important role in system calls and I/O.

Namun register lain adalah PSW (Program Status Word). Register ini berisi bit kode kondisi, yang diatur oleh instruksi perbandingan, CPU
prioritas, mode (pengguna atau kernel), dan berbagai bit kontrol lainnya. Program pengguna
biasanya dapat membaca seluruh PSW tetapi biasanya hanya dapat menulis beberapa bidangnya.
PSW memainkan peran penting dalam panggilan sistem dan I/O.

The operating system must be fully aware of all the registers. When time multiplexing the CPU, the operating system will often stop the running program to
(re)start another one. Every time it stops a running program, the operating system
must save all the registers so they can be restored when the program runs later.

Sistem operasi harus sepenuhnya menyadari semua register. Ketika waktu multiplexing CPU, sistem operasi akan sering menghentikan program yang sedang berjalan untuk
(kembali) mulai yang lain. Setiap kali menghentikan program yang sedang berjalan, sistem operasi
harus menyimpan semua register agar dapat dipulihkan saat program berjalan nanti.

To improve performance, CPU designers have long abandoned the simple
model of fetching, decoding, and executing one instruction at a time. Many modern
CPUs have facilities for executing more than one instruction at the same time. For
example, a CPU might have separate fetch, decode, and execute units, so that while
it is executing instruction n, it could also be decoding instruction n + 1 and fetching instruction n + 2. Such an organization is called a pipeline and is illustrated in
Fig. 1-7(a) for a pipeline with three stages. Longer pipelines are common. In most
pipeline designs, once an instruction has been fetched into the pipeline, it must be
executed, even if the preceding instruction was a conditional branch that was taken.
Pipelines cause compiler writers and operating system writers great headaches because they expose the complexities of the underlying machine to them and they
have to deal with them.

Untuk meningkatkan kinerja, desainer CPU telah lama meninggalkan yang sederhana
model pengambilan, decoding, dan eksekusi satu instruksi pada satu waktu. Banyak modern
CPU memiliki fasilitas untuk mengeksekusi lebih dari satu instruksi secara bersamaan. Untuk
misalnya, CPU mungkin memiliki unit pengambilan, dekode, dan eksekusi terpisah, sehingga saat
itu mengeksekusi instruksi n, bisa juga decoding instruksi n + 1 dan mengambil instruksi n + 2. Organisasi seperti itu disebut pipa dan diilustrasikan dalam
Gambar 1-7(a) untuk pipa dengan tiga tahap. Pipa yang lebih panjang adalah hal biasa. Di sebagian besar
desain pipa, setelah instruksi telah diambil ke dalam pipa, itu harus
dieksekusi, bahkan jika instruksi sebelumnya adalah cabang bersyarat yang diambil.
Pipeline menyebabkan penulis kompiler dan penulis sistem operasi sakit kepala karena mengekspos kompleksitas mesin yang mendasarinya kepada mereka dan mereka
harus berurusan dengan mereka.

Even more advanced than a pipeline design is a superscalar CPU, shown in
Fig. 1-7(b). In this design, multiple execution units are present, for example, one
for integer arithmetic, one for floating-point arithmetic, and one for Boolean operations. Two or more instructions are fetched at once, decoded, and dumped into a
holding buffer until they can be executed. As soon as an execution unit becomes
available, it looks in the holding buffer to see if there is an instruction it can handle, and if so, it removes the instruction from the buffer and executes it. An implication of this design is that program instructions are often executed out of order. For
the most part, it is up to the hardware to make sure the result produced is the same
one a sequential implementation would have produced, but an annoying amount of
the complexity is foisted onto the operating system, as we shall see.

Bahkan lebih canggih dari desain pipa adalah CPU superscalar, ditunjukkan pada
Gambar 1-7(b). Dalam desain ini, beberapa unit eksekusi hadir, misalnya, satu
untuk aritmatika bilangan bulat, satu untuk aritmatika titik-mengambang, dan satu untuk operasi Boolean. Dua atau lebih instruksi diambil sekaligus, didekode, dan dibuang ke a
menahan buffer sampai dapat dieksekusi. Segera setelah unit eksekusi menjadi
tersedia, itu terlihat di buffer holding untuk melihat apakah ada instruksi yang dapat ditangani, dan jika demikian, ia menghapus instruksi dari buffer dan mengeksekusinya. Implikasi dari desain ini adalah bahwa instruksi program sering kali dieksekusi secara tidak berurutan. Untuk
sebagian besar terserah perangkat keras untuk memastikan hasil yang dihasilkan sama
satu implementasi berurutan akan menghasilkan, tetapi jumlah yang mengganggu
kompleksitas dimasukkan ke sistem operasi, seperti yang akan kita lihat.

Most CPUs, except very simple ones used in embedded systems, have two
modes, kernel mode and user mode, as mentioned earlier. Usually, a bit in the PSW
controls the mode. When running in kernel mode, the CPU can execute every instruction in its instruction set and use every feature of the hardware. On desktop
and server machines, the operating system normally runs in kernel mode, giving it
access to the complete hardware. On most embedded systems, a small piece runs
in kernel mode, with the rest of the operating system running in user mode.

Sebagian besar CPU, kecuali yang sangat sederhana yang digunakan dalam sistem tertanam, memiliki dua
mode, mode kernel dan mode pengguna, seperti yang disebutkan sebelumnya. Biasanya, sedikit di PSW
mengontrol mode. Saat berjalan dalam mode kernel, CPU dapat mengeksekusi setiap instruksi dalam set instruksinya dan menggunakan setiap fitur perangkat keras. Di desktop
dan mesin server, sistem operasi biasanya berjalan dalam mode kernel, memberikannya
akses ke perangkat keras lengkap. Pada sebagian besar sistem tertanam, sebagian kecil berjalan
dalam mode kernel, dengan sistem operasi lainnya berjalan dalam mode pengguna.

User programs always run in user mode, which permits only a subset of the instructions to be executed and a subset of the features to be accessed. Generally, all
instructions involving I/O and memory protection are disallowed in user mode.
Setting the PSW mode bit to enter kernel mode is also forbidden, of course.

Program pengguna selalu berjalan dalam mode pengguna, yang memungkinkan hanya sebagian dari instruksi yang akan dieksekusi dan sebagian fitur yang akan diakses. Umumnya semua
instruksi yang melibatkan I/O dan perlindungan memori tidak diizinkan dalam mode pengguna.
Mengatur bit mode PSW untuk masuk ke mode kernel juga dilarang, tentu saja.

To obtain services from the operating system, a user program must make a system call, which traps into the kernel and invokes the operating system. The TRAP
instruction switches from user mode to kernel mode and starts the operating system. When the work has been completed, control is returned to the user program at
the instruction following the system call. We will explain the details of the system
call mechanism later in this chapter. For the time being, think of it as a special kind
of procedure call that has the additional property of switching from user mode to
kernel mode. As a note on typography, we will use the lower-case Helvetica font
to indicate system calls in running text, like this: read.

Untuk mendapatkan layanan dari sistem operasi, program pengguna harus membuat panggilan sistem, yang menjebak ke dalam kernel dan memanggil sistem operasi. Jebakan
instruksi beralih dari mode pengguna ke mode kernel dan memulai sistem operasi. Ketika pekerjaan telah selesai, kontrol dikembalikan ke program pengguna di
instruksi setelah panggilan sistem. Kami akan menjelaskan detail sistemnya
mekanisme panggilan nanti dalam bab ini. Untuk saat ini, anggap itu sebagai jenis khusus
panggilan prosedur yang memiliki properti tambahan untuk beralih dari mode pengguna ke
modus inti. Sebagai catatan tentang tipografi, kami akan menggunakan huruf kecil Helvetica font
untuk menunjukkan panggilan sistem dalam teks yang sedang berjalan, seperti ini: baca.

It is worth noting that computers have traps other than the instruction for executing a system call. Most of the other traps are caused by the hardware to warn
of an exceptional situation such as an attempt to divide by 0 or a floating-point
underflow. In all cases the operating system gets control and must decide what to
do. Sometimes the program must be terminated with an error. Other times the
error can be ignored (an underflowed number can be set to 0). Finally, when the
program has announced in advance that it wants to handle certain kinds of conditions, control can be passed back to the program to let it deal with the problem.

Perlu dicatat bahwa komputer memiliki jebakan selain instruksi untuk menjalankan panggilan sistem. Sebagian besar jebakan lain disebabkan oleh perangkat keras untuk memperingatkan
dari situasi luar biasa seperti upaya untuk membagi dengan 0 atau floating-point
arus bawah. Dalam semua kasus, sistem operasi mendapat kendali dan harus memutuskan apa yang harus
melakukan. Terkadang program harus dihentikan dengan kesalahan. Di lain waktu
kesalahan dapat diabaikan (angka underflow dapat diatur ke 0). Akhirnya, ketika
program telah mengumumkan sebelumnya bahwa ia ingin menangani jenis kondisi tertentu, kontrol dapat diteruskan kembali ke program untuk membiarkannya menangani masalah.

Multithreaded and Multicore Chips
Chip Multithread dan Multicore

Moore’s law states that the number of transistors on a chip doubles every 18
months. This ‘‘law’’ is not some kind of law of physics, like conservation of momentum, but is an observation by Intel cofounder Gordon Moore of how fast process engineers at the semiconductor companies are able to shrink their transistors.
Moore’s law has held for over three decades now and is expected to hold for at
least one more. After that, the number of atoms per transistor will become too
small and quantum mechanics will start to play a big role, preventing further
shrinkage of transistor sizes.

Hukum Moore menyatakan bahwa jumlah transistor pada sebuah chip berlipat ganda setiap 18
bulan. ''Hukum'' ini bukanlah semacam hukum fisika, seperti kekekalan momentum, tetapi merupakan pengamatan oleh salah satu pendiri Intel, Gordon Moore, tentang seberapa cepat insinyur proses di perusahaan semikonduktor mampu mengecilkan transistor mereka.
Hukum Moore telah berlaku selama lebih dari tiga dekade sekarang dan diperkirakan akan berlaku selama
setidaknya satu lagi. Setelah itu, jumlah atom per transistor akan menjadi terlalu
mekanika kecil dan kuantum akan mulai memainkan peran besar, mencegah lebih lanjut
penyusutan ukuran transistor.

The abundance of transistors is leading to a problem: what to do with all of
them? We saw one approach above: superscalar architectures, with multiple functional units. But as the number of transistors increases, even more is possible. One
obvious thing to do is put bigger caches on the CPU chip. That is definitely happening, but eventually the point of diminishing returns will be reached.

Kelimpahan transistor menyebabkan masalah: apa yang harus dilakukan dengan semua
mereka? Kami melihat satu pendekatan di atas: arsitektur superscalar, dengan beberapa unit fungsional. Tetapi karena jumlah transistor meningkat, lebih banyak lagi yang mungkin. Satu
hal yang jelas untuk dilakukan adalah meletakkan cache yang lebih besar pada chip CPU. Itu pasti terjadi, tetapi pada akhirnya titik hasil yang semakin berkurang akan tercapai.

The obvious next step is to replicate not only the functional units, but also
some of the control logic. The Intel Pentium 4 introduced this property, called
multithreading or hyperthreading (Intel’s name for it), to the x86 processor, and
several other CPU chips also have it—including the SPARC, the Power5, the Intel
Xeon, and the Intel Core family. To a first approximation, what it does is allow the
CPU to hold the state of two different threads and then switch back and forth on a
nanosecond time scale. (A thread is a kind of lightweight process, which, in turn,
is a running program; we will get into the details in Chap. 2.) For example, if one
of the processes needs to read a word from memory (which takes many clock
cycles), a multithreaded CPU can just switch to another thread. Multithreading
does not offer true parallelism. Only one process at a time is running, but
thread-switching time is reduced to the order of a nanosecond.

Langkah selanjutnya yang jelas adalah mereplikasi tidak hanya unit fungsional, tetapi juga
beberapa logika kontrol. Intel Pentium 4 memperkenalkan properti ini, yang disebut
multithreading atau hyperthreading (nama Intel untuk itu), ke prosesor x86, dan
beberapa chip CPU lainnya juga memilikinya—termasuk SPARC, Power5, Intel
Xeon, dan keluarga Intel Core. Untuk pendekatan pertama, apa yang dilakukannya adalah mengizinkan
CPU untuk menahan status dua utas yang berbeda dan kemudian beralih bolak-balik pada a
skala waktu nanodetik. (Utas adalah sejenis proses ringan, yang, pada gilirannya,
adalah program yang sedang berjalan; kita akan masuk ke rincian di Chap. 2.) Misalnya, jika salah satu
proses perlu membaca kata dari memori (yang membutuhkan banyak jam
siklus), CPU multithreaded hanya dapat beralih ke thread lain. Multithreading
tidak menawarkan paralelisme sejati. Hanya satu proses pada satu waktu yang berjalan, tapi
waktu thread-switching berkurang ke urutan nanodetik.

Multithreading has implications for the operating system because each thread
appears to the operating system as a separate CPU. Consider a system with two
actual CPUs, each with two threads. The operating system will see this as four
CPUs. If there is only enough work to keep two CPUs busy at a certain point in
time, it may inadvertently schedule two threads on the same CPU, with the other
CPU completely idle. This choice is far less efficient than using one thread on each
CPU

Multithreading memiliki implikasi untuk sistem operasi karena setiap thread
muncul ke sistem operasi sebagai CPU terpisah. Pertimbangkan sistem dengan dua
CPU sebenarnya, masing-masing dengan dua utas. Sistem operasi akan melihat ini sebagai empat
CPU. Jika hanya ada cukup pekerjaan untuk membuat dua CPU sibuk pada titik tertentu di
waktu, mungkin secara tidak sengaja menjadwalkan dua utas pada CPU yang sama, dengan yang lain
CPU benar-benar menganggur. Pilihan ini jauh kurang efisien daripada menggunakan satu utas pada masing-masing
CPU

Beyond multithreading, many CPU chips now hav e four, eight, or more complete processors or cores on them. The multicore chips of Fig. 1-8 effectively carry
four minichips on them, each with its own independent CPU. (The caches will be
explained below.) Some processors, like Intel Xeon Phi and the Tilera TilePro, already sport more than 60 cores on a single chip. Making use of such a multicore
chip will definitely require a multiprocessor operating system.

Selain multithreading, banyak chip CPU sekarang memiliki empat, delapan, atau lebih prosesor atau inti yang lengkap. Chip multicore pada Gambar 1-8 secara efektif membawa
empat minichip di dalamnya, masing-masing dengan CPU independennya sendiri. (Cache akan menjadi
dijelaskan di bawah.) Beberapa prosesor, seperti Intel Xeon Phi dan Tilera TilePro, sudah memiliki lebih dari 60 inti dalam satu chip. Memanfaatkan multicore seperti itu
chip pasti akan membutuhkan sistem operasi multiprosesor.

Incidentally, in terms of sheer numbers, nothing beats a modern GPU (Graphics Processing Unit). A GPU is a processor with, literally, thousands of tiny cores.
They are very good for many small computations done in parallel, like rendering
polygons in graphics applications. They are not so good at serial tasks. They are
also hard to program. While GPUs can be useful for operating systems (e.g., encryption or processing of network traffic), it is not likely that much of the operating
system itself will run on the GPUs.

Kebetulan, dalam hal jumlah, tidak ada yang mengalahkan GPU (Graphics Processing Unit) modern. GPU adalah prosesor dengan, secara harfiah, ribuan inti kecil.
Mereka sangat bagus untuk banyak perhitungan kecil yang dilakukan secara paralel, seperti rendering
poligon dalam aplikasi grafis. Mereka tidak begitu baik dalam tugas-tugas serial. Mereka
juga sulit untuk diprogram. Meskipun GPU dapat berguna untuk sistem operasi (misalnya, enkripsi atau pemrosesan lalu lintas jaringan), tidak mungkin sebagian besar operasi
sistem itu sendiri akan berjalan di GPU.

1.3.2 Memory
1.3.2 Memori

The second major component in any computer is the memory. Ideally, a memory should be extremely fast (faster than executing an instruction so that the CPU is
not held up by the memory), abundantly large, and dirt cheap. No current technology satisfies all of these goals, so a different approach is taken. The memory system is constructed as a hierarchy of layers, as shown in Fig. 1-9. The top layers
have higher speed, smaller capacity, and greater cost per bit than the lower ones,
often by factors of a billion or more

Komponen utama kedua di komputer manapun adalah memori. Idealnya, memori harus sangat cepat (lebih cepat daripada mengeksekusi instruksi sehingga CPU
tidak tertahan oleh memori), sangat besar, dan sangat murah. Tidak ada teknologi saat ini yang memenuhi semua tujuan ini, jadi diambil pendekatan yang berbeda. Sistem memori dibangun sebagai hierarki lapisan, seperti yang ditunjukkan pada Gambar 1-9. Lapisan atas
memiliki kecepatan lebih tinggi, kapasitas lebih kecil, dan biaya per bit lebih besar daripada yang lebih rendah,
seringkali dengan faktor satu miliar atau lebih

typically 32 × 32 bits on a 32-bit CPU and 64 × 64 bits on a 64-bit CPU. Less than
1 KB in both cases. Programs must manage the registers (i.e., decide what to keep
in them) themselves, in software.

biasanya 32 × 32 bit pada CPU 32-bit dan 64 × 64 bit pada CPU 64-bit. Kurang dari
1 KB dalam kedua kasus. Program harus mengelola register (yaitu, memutuskan apa yang harus disimpan
di dalamnya) sendiri, dalam perangkat lunak.

Next comes the cache memory, which is mostly controlled by the hardware.
Main memory is divided up into cache lines, typically 64 bytes, with addresses 0
to 63 in cache line 0, 64 to 127 in cache line 1, and so on. The most heavily used
cache lines are kept in a high-speed cache located inside or very close to the CPU.
When the program needs to read a memory word, the cache hardware checks to see
if the line needed is in the cache. If it is, called a cache hit, the request is satisfied
from the cache and no memory request is sent over the bus to the main memory.
Cache hits normally take about two clock cycles. Cache misses have to go to
memory, with a substantial time penalty. Cache memory is limited in size due to its
high cost. Some machines have two or even three levels of cache, each one slower
and bigger than the one before it.

Berikutnya adalah memori cache, yang sebagian besar dikendalikan oleh perangkat keras.
Memori utama dibagi menjadi baris cache, biasanya 64 byte, dengan alamat 0
ke 63 di baris cache 0, 64 hingga 127 di cache baris 1, dan seterusnya. Yang paling banyak digunakan
baris cache disimpan dalam cache berkecepatan tinggi yang terletak di dalam atau sangat dekat dengan CPU.
Ketika program perlu membaca kata memori, perangkat keras cache memeriksa untuk melihat
jika baris yang dibutuhkan ada di cache. Jika ya, disebut cache hit, permintaannya terpenuhi
dari cache dan tidak ada permintaan memori yang dikirim melalui bus ke memori utama.
Cache hits biasanya memakan waktu sekitar dua siklus clock. Cache rindu harus pergi ke
memori, dengan hukuman waktu yang substansial. Memori cache terbatas ukurannya karena
harga tinggi. Beberapa mesin memiliki dua atau bahkan tiga tingkat cache, masing-masing lebih lambat
dan lebih besar dari yang sebelumnya.

Caching plays a major role in many areas of computer science, not just caching
lines of RAM. Whenever a resource can be divided into pieces, some of which are
used much more heavily than others, caching is often used to improve performance. Operating systems use it all the time. For example, most operating systems
keep (pieces of) heavily used files in main memory to avoid having to fetch them
from the disk repeatedly. Similarly, the results of converting long path names like
/home/ast/projects/minix3/src/kernel/clock.c

Caching memainkan peran utama dalam banyak bidang ilmu komputer, bukan hanya caching
baris RAM. Setiap kali sumber daya dapat dibagi menjadi beberapa bagian, beberapa di antaranya adalah
digunakan jauh lebih berat daripada yang lain, caching sering digunakan untuk meningkatkan kinerja. Sistem operasi menggunakannya sepanjang waktu. Misalnya, sebagian besar sistem operasi
simpan (potongan) file yang banyak digunakan di memori utama untuk menghindari keharusan mengambilnya
dari disk berulang kali. Demikian pula, hasil konversi nama jalur panjang seperti
/home/ast/projects/minix3/src/kernel/clock.c

into the disk address where the file is located can be cached to avoid repeated
lookups. Finally, when the address of a Web page (URL) is converted to a network
address (IP address), the result can be cached for future use. Many other uses exist.

ke alamat disk tempat file berada dapat di-cache untuk menghindari pengulangan
pencarian. Akhirnya, ketika alamat halaman Web (URL) dikonversi ke jaringan
address (alamat IP), hasilnya dapat di-cache untuk digunakan di masa mendatang. Banyak kegunaan lain yang ada.

In any caching system, several questions come up fairly soon, including:
Dalam sistem caching apa pun, beberapa pertanyaan segera muncul, termasuk:

1. When to put a new item into the cache.
2. Which cache line to put the new item in.
3. Which item to remove from the cache when a slot is needed.
4. Where to put a newly evicted item in the larger memory.

1. Kapan harus memasukkan item baru ke dalam cache.
2. Baris cache mana untuk memasukkan item baru.
3. Item mana yang harus dihapus dari cache saat slot diperlukan.
4. Tempat meletakkan item yang baru dikeluarkan di memori yang lebih besar.

Not every question is relevant to every caching situation. For caching lines of main
memory in the CPU cache, a new item will generally be entered on every cache
miss. The cache line to use is generally computed by using some of the high-order
bits of the memory address referenced. For example, with 4096 cache lines of 64
bytes and 32 bit addresses, bits 6 through 17 might be used to specify the cache
line, with bits 0 to 5 the byte within the cache line. In this case, the item to remove
is the same one as the new data goes into, but in other systems it might not be.
Finally, when a cache line is rewritten to main memory (if it has been modified
since it was cached), the place in memory to rewrite it to is uniquely determined by
the address in question

Tidak setiap pertanyaan relevan dengan setiap situasi caching. Untuk caching baris main
memori dalam cache CPU, item baru umumnya akan dimasukkan pada setiap cache
merindukan. Garis cache yang digunakan umumnya dihitung dengan menggunakan beberapa perintah tingkat tinggi
bit alamat memori yang dirujuk. Misalnya, dengan 4096 baris cache 64
byte dan alamat 32 bit, bit 6 hingga 17 dapat digunakan untuk menentukan cache
baris, dengan bit 0 sampai 5 byte dalam baris cache. Dalam hal ini, item yang akan dihapus
sama dengan data baru yang masuk, tetapi di sistem lain mungkin tidak.
Akhirnya, ketika baris cache ditulis ulang ke memori utama (jika telah dimodifikasi
sejak di-cache), tempat di memori untuk menulis ulang ditentukan secara unik oleh
alamat yang dimaksud

Caches are such a good idea that modern CPUs have two of them. The first
level or L1 cache is always inside the CPU and usually feeds decoded instructions
into the CPU’s execution engine. Most chips have a second L1 cache for very
heavily used data words. The L1 caches are typically 16 KB each. In addition,
there is often a second cache, called the L2 cache, that holds several megabytes of
recently used memory words. The difference between the L1 and L2 caches lies in
the timing. Access to the L1 cache is done without any delay, whereas access to
the L2 cache involves a delay of one or two clock cycles.

Cache adalah ide yang bagus sehingga CPU modern memiliki dua di antaranya. Pertama
cache level atau L1 selalu berada di dalam CPU dan biasanya memberikan instruksi yang didekodekan
ke mesin eksekusi CPU. Sebagian besar chip memiliki cache L1 kedua untuk waktu yang sangat lama
kata-kata data yang banyak digunakan. Cache L1 biasanya masing-masing 16 KB. Sebagai tambahan,
sering ada cache kedua, yang disebut cache L2, yang menampung beberapa megabita
kata-kata memori yang baru-baru ini digunakan. Perbedaan antara cache L1 dan L2 terletak pada
waktunya. Akses ke cache L1 dilakukan tanpa penundaan, sedangkan akses ke
cache L2 melibatkan penundaan satu atau dua siklus clock.

On multicore chips, the designers have to decide where to place the caches. In
Fig. 1-8(a), a single L2 cache is shared by all the cores. This approach is used in
Intel multicore chips. In contrast, in Fig. 1-8(b), each core has its own L2 cache.
This approach is used by AMD. Each strategy has its pros and cons. For example,
the Intel shared L2 cache requires a more complicated cache controller but the
AMD way makes keeping the L2 caches consistent more difficult.

Pada chip multicore, perancang harus memutuskan di mana menempatkan cache. Di
Gambar 1-8(a), satu cache L2 digunakan bersama oleh semua inti. Pendekatan ini digunakan dalam
Chip multicore Intel. Sebaliknya, pada Gambar 1-8(b), setiap inti memiliki cache L2 sendiri.
Pendekatan ini digunakan oleh AMD. Setiap strategi memiliki pro dan kontra. Sebagai contoh,
cache L2 bersama Intel membutuhkan pengontrol cache yang lebih rumit tetapi
Cara AMD membuat cache L2 tetap konsisten menjadi lebih sulit.

Main memory comes next in the hierarchy of Fig. 1-9. This is the workhorse
of the memory system. Main memory is usually called RAM (Random Access
Memory). Old-timers sometimes call it core memory, because computers in the
1950s and 1960s used tiny magnetizable ferrite cores for main memory. They hav e
been gone for decades but the name persists. Currently, memories are hundreds of
megabytes to several gigabytes and growing rapidly. All CPU requests that cannot
be satisfied out of the cache go to main memory.

Memori utama muncul berikutnya dalam hierarki Gambar 1-9. Ini adalah pekerja keras
dari sistem memori. Memori utama biasanya disebut RAM (Random Access)
Penyimpanan). Orang tua terkadang menyebutnya memori inti, karena komputer di
1950-an dan 1960-an menggunakan inti ferit kecil yang dapat dimagnetisasi untuk memori utama. Mereka memiliki
telah hilang selama beberapa dekade tetapi namanya tetap ada. Saat ini, kenangan adalah ratusan
megabyte hingga beberapa gigabyte dan berkembang pesat. Semua permintaan CPU yang tidak bisa
puas keluar dari cache pergi ke memori utama.

In addition to the main memory, many computers have a small amount of nonvolatile random-access memory. Unlike RAM, nonvolatile memory does not lose
its contents when the power is switched off. ROM (Read Only Memory) is programmed at the factory and cannot be changed afterward. It is fast and inexpensive. On some computers, the bootstrap loader used to start the computer is contained in ROM. Also, some I/O cards come with ROM for handling low-level device control.

Selain memori utama, banyak komputer memiliki sejumlah kecil memori akses acak nonvolatile. Tidak seperti RAM, memori nonvolatile tidak hilang
isinya saat listrik dimatikan. ROM (Memori Hanya Baca) diprogram di pabrik dan tidak dapat diubah setelahnya. Ini cepat dan murah. Pada beberapa komputer, bootstrap loader yang digunakan untuk memulai komputer terdapat dalam ROM. Juga, beberapa kartu I/O dilengkapi dengan ROM untuk menangani kontrol perangkat tingkat rendah.

EEPROM (Electrically Erasable PROM) and flash memory are also nonvolatile, but in contrast to ROM can be erased and rewritten. However, writing
them takes orders of magnitude more time than writing RAM, so they are used in
the same way ROM is, only with the additional feature that it is now possible to
correct bugs in programs they hold by rewriting them in the field.

EEPROM (Electrically Erasable PROM) dan memori flash juga nonvolatile, tetapi berbeda dengan ROM yang dapat dihapus dan ditulis ulang. Namun, menulis
mereka membutuhkan waktu lebih lama daripada menulis RAM, jadi mereka digunakan dalam
ROM dengan cara yang sama, hanya dengan fitur tambahan yang sekarang dimungkinkan untuk
memperbaiki bug dalam program yang mereka pegang dengan menulis ulang di lapangan.

Flash memory is also commonly used as the storage medium in portable electronic devices. It serves as film in digital cameras and as the disk in portable music
players, to name just two uses. Flash memory is intermediate in speed between
RAM and disk. Also, unlike disk memory, if it is erased too many times, it wears
out.

Flash memory juga biasa digunakan sebagai media penyimpanan pada perangkat elektronik portabel. Ini berfungsi sebagai film di kamera digital dan sebagai disk dalam musik portabel
pemain, untuk menyebutkan hanya dua kegunaan. Memori flash memiliki kecepatan menengah antara
RAM dan disk. Juga, tidak seperti memori disk, jika terlalu sering dihapus, itu akan aus
keluar.


Yet another kind of memory is CMOS, which is volatile. Many computers use
CMOS memory to hold the current time and date. The CMOS memory and the
clock circuit that increments the time in it are powered by a small battery, so the
time is correctly updated, even when the computer is unplugged. The CMOS memory can also hold the configuration parameters, such as which disk to boot from.
CMOS is used because it draws so little power that the original factory-installed
battery often lasts for several years. However, when it begins to fail, the computer
can appear to have Alzheimer’s disease, forgetting things that it has known for
years, like which hard disk to boot from.

Namun jenis memori lain adalah CMOS, yang tidak stabil. Banyak komputer menggunakan
Memori CMOS untuk menyimpan waktu dan tanggal saat ini. Memori CMOS dan
rangkaian jam yang menambah waktu di dalamnya ditenagai oleh baterai kecil, jadi
waktu diperbarui dengan benar, bahkan ketika komputer dicabut. Memori CMOS juga dapat menyimpan parameter konfigurasi, seperti disk mana yang akan di-boot.
CMOS digunakan karena menggunakan daya yang sangat kecil sehingga yang dipasang di pabrik asli
baterai sering berlangsung selama beberapa tahun. Namun, ketika mulai gagal, komputer
tampaknya memiliki penyakit Alzheimer, melupakan hal-hal yang telah diketahuinya
tahun, seperti hard disk mana untuk boot.

1.3.3 Disks
1.3.3 Disk

Next in the hierarchy is magnetic disk (hard disk). Disk storage is two orders
of magnitude cheaper than RAM per bit and often two orders of magnitude larger
as well. The only problem is that the time to randomly access data on it is close to
three orders of magnitude slower. The reason is that a disk is a mechanical device,
as shown in Fig. 1-10.

Berikutnya dalam hirarki adalah magnetic disk (hard disk). Penyimpanan disk adalah dua pesanan
besarnya lebih murah daripada RAM per bit dan seringkali dua kali lipat lebih besar
demikian juga. Satu-satunya masalah adalah waktu untuk mengakses data secara acak di dekat
tiga kali lipat lebih lambat. Alasannya adalah bahwa disk adalah perangkat mekanis,
seperti yang ditunjukkan pada Gambar 1-10.

A disk consists of one or more metal platters that rotate at 5400, 7200, 10,800
RPM or more. A mechanical arm pivots over the platters from the corner, similar
to the pickup arm on an old 33-RPM phonograph for playing vinyl records
Information is written onto the disk in a series of concentric circles. At any giv en
arm position, each of the heads can read an annular region called a track. Together, all the tracks for a given arm position form a cylinder.

Sebuah piringan terdiri dari satu atau lebih pelat logam yang berputar pada 5400, 7200, 10,800
RPM atau lebih. Lengan mekanis berputar di atas piring-piring dari sudut, serupa
ke lengan pickup pada fonograf 33-RPM tua untuk memutar piringan hitam
Informasi ditulis ke disk dalam serangkaian lingkaran konsentris. Kapan saja
posisi lengan, masing-masing kepala dapat membaca daerah annular yang disebut trek. Bersama-sama, semua trek untuk posisi lengan tertentu membentuk silinder.

Each track is divided into some number of sectors, typically 512 bytes per sector. On modern disks, the outer cylinders contain more sectors than the inner ones.
Moving the arm from one cylinder to the next takes about 1 msec. Moving it to a
random cylinder typically takes 5 to 10 msec, depending on the drive. Once the
arm is on the correct track, the drive must wait for the needed sector to rotate under
the head, an additional delay of 5 msec to 10 msec, depending on the drive’s RPM.
Once the sector is under the head, reading or writing occurs at a rate of 50 MB/sec
on low-end disks to 160 MB/sec on faster ones.

Setiap track dibagi menjadi beberapa sektor, biasanya 512 byte per sektor. Pada disk modern, silinder luar berisi lebih banyak sektor daripada yang dalam.
Memindahkan lengan dari satu silinder ke silinder berikutnya membutuhkan waktu sekitar 1 mdtk. Memindahkannya ke
silinder acak biasanya membutuhkan waktu 5 sampai 10 msec, tergantung pada drive. sekali
lengan berada di jalur yang benar, drive harus menunggu sektor yang diperlukan berputar di bawah
kepala, penundaan tambahan dari 5 mdtk hingga 10 mdtk, tergantung pada RPM drive.
Setelah sektor berada di bawah kepala, membaca atau menulis terjadi pada kecepatan 50 MB/dtk
pada disk kelas bawah hingga 160 MB/detik pada disk yang lebih cepat.

Sometimes you will hear people talk about disks that are really not disks at all,
like SSDs, (Solid State Disks). SSDs do not have moving parts, do not contain
platters in the shape of disks, and store data in (Flash) memory. The only ways in
which they resemble disks is that they also store a lot of data which is not lost
when the power is off.

Terkadang Anda akan mendengar orang berbicara tentang disk yang sebenarnya bukan disk sama sekali,
seperti SSD, (Solid State Disk). SSD tidak memiliki bagian yang bergerak, tidak mengandung
piring-piring dalam bentuk disk, dan menyimpan data dalam memori (Flash). Satu-satunya cara masuk
yang menyerupai disk adalah mereka juga menyimpan banyak data yang tidak hilang
saat listrik mati.

Many computers support a scheme known as virtual memory, which we will
discuss at some length in Chap. 3. This scheme makes it possible to run programs
larger than physical memory by placing them on the disk and using main memory
as a kind of cache for the most heavily executed parts. This scheme requires remapping memory addresses on the fly to convert the address the program generated to the physical address in RAM where the word is located. This mapping is
done by a part of the CPU called the MMU (Memory Management Unit), as
shown in Fig. 1-6.

Banyak komputer mendukung skema yang dikenal sebagai memori virtual, yang akan kita
membahas panjang lebar di Bab. 3. Skema ini memungkinkan untuk menjalankan program
lebih besar dari memori fisik dengan menempatkannya pada disk dan menggunakan memori utama
sebagai semacam cache untuk bagian yang paling banyak dieksekusi. Skema ini membutuhkan pemetaan ulang alamat memori dengan cepat untuk mengubah alamat program yang dihasilkan ke alamat fisik di RAM tempat kata berada. pemetaan ini adalah
dilakukan oleh bagian dari CPU yang disebut MMU (Memory Management Unit), sebagai
ditunjukkan pada Gambar. 1-6.

The presence of caching and the MMU can have a major impact on performance. In a multiprogramming system, when switching from one program to
another, sometimes called a context switch, it may be necessary to flush all modified blocks from the cache and change the mapping registers in the MMU. Both of
these are expensive operations, and programmers try hard to avoid them. We will
see some of the implications of their tactics later.

Kehadiran caching dan MMU dapat berdampak besar pada kinerja. Dalam sistem multiprogramming, ketika beralih dari satu program ke
lain, kadang-kadang disebut sakelar konteks, mungkin perlu untuk menghapus semua blok yang dimodifikasi dari cache dan mengubah register pemetaan di MMU. Keduanya
ini adalah operasi yang mahal, dan pemrogram berusaha keras untuk menghindarinya. Kami akan
lihat beberapa implikasi dari taktik mereka nanti.

1.3.4 I/O Devices
1.3.4 Perangkat I/O

The CPU and memory are not the only resources that the operating system
must manage. I/O devices also interact heavily with the operating system. As we
saw in Fig. 1-6, I/O devices generally consist of two parts: a controller and the device itself. The controller is a chip or a set of chips that physically controls the device. It accepts commands from the operating system, for example, to read data
from the device, and carries them out.

CPU dan memori bukan satu-satunya sumber daya yang dimiliki sistem operasi
harus mengelola. Perangkat I/O juga banyak berinteraksi dengan sistem operasi. Seperti yang kita
dilihat pada Gambar 1-6, perangkat I/O umumnya terdiri dari dua bagian: pengontrol dan perangkat itu sendiri. Controller adalah sebuah chip atau satu set chip yang secara fisik mengontrol perangkat. Ia menerima perintah dari sistem operasi, misalnya, untuk membaca data
dari perangkat, dan melaksanakannya.

In many cases, the actual control of the device is complicated and detailed, so
it is the job of the controller to present a simpler (but still very complex) interface
to the operating system. For example, a disk controller might accept a command to
read sector 11,206 from disk 2. The controller then has to convert this linear sector
number to a cylinder, sector, and head. This conversion may be complicated by the
fact that outer cylinders have more sectors than inner ones and that some bad sectors have been remapped onto other ones. Then the controller has to determine
which cylinder the disk arm is on and give it a command to move in or out the requisite number of cylinders. It has to wait until the proper sector has rotated under
the head and then start reading and storing the bits as they come off the drive,
removing the preamble and computing the checksum. Finally, it has to assemble
the incoming bits into words and store them in memory. To do all this work, controllers often contain small embedded computers that are programmed to do their
work.

Dalam banyak kasus, kontrol perangkat yang sebenarnya rumit dan terperinci, jadi
itu adalah tugas pengontrol untuk menghadirkan antarmuka yang lebih sederhana (tetapi masih sangat kompleks)
ke sistem operasi. Misalnya, pengontrol disk mungkin menerima perintah untuk
baca sektor 11.206 dari disk 2. Pengontrol kemudian harus mengubah sektor linier ini
nomor ke silinder, sektor, dan kepala. Konversi ini mungkin rumit oleh
fakta bahwa silinder luar memiliki lebih banyak sektor daripada yang dalam dan bahwa beberapa sektor buruk telah dipetakan kembali ke yang lain. Kemudian pengontrol harus menentukan
silinder mana lengan disk berada dan berikan perintah untuk bergerak masuk atau keluar jumlah silinder yang diperlukan. Itu harus menunggu sampai sektor yang tepat diputar di bawah
kepala dan kemudian mulai membaca dan menyimpan bit saat keluar dari drive,
menghapus pembukaan dan menghitung checksum. Akhirnya, itu harus dirakit
bit yang masuk ke dalam kata-kata dan menyimpannya dalam memori. Untuk melakukan semua pekerjaan ini, pengontrol sering berisi komputer tertanam kecil yang diprogram untuk melakukan tugasnya
kerja.

The other piece is the actual device itself. Devices have fairly simple interfaces, both because they cannot do much and to make them standard. The latter is
needed so that any SAT A disk controller can handle any SAT A disk, for example.
SATA stands for Serial ATA and AT A in turn stands for AT Attachment. In case
you are curious what AT stands for, this was IBM’s second generation ‘‘Personal
Computer Advanced Technology’’ built around the then-extremely-potent 6-MHz
80286 processor that the company introduced in 1984. What we learn from this is
that the computer industry has a habit of continuously enhancing existing acronyms with new prefixes and suffixes. We also learned that an adjective like ‘‘advanced’’ should be used with great care, or you will look silly thirty years down the
line.

Bagian lainnya adalah perangkat itu sendiri. Perangkat memiliki antarmuka yang cukup sederhana, baik karena mereka tidak dapat berbuat banyak dan menjadikannya standar. Yang terakhir adalah
diperlukan agar setiap pengontrol disk SAT A dapat menangani disk SAT A, misalnya.
SATA adalah singkatan dari Serial ATA dan AT A pada gilirannya adalah singkatan dari AT Attachment. Dalam hal
Anda ingin tahu apa singkatan dari AT, ini adalah generasi kedua IBM '' Pribadi
Teknologi Canggih Komputer '' dibangun di sekitar 6-MHz yang sangat kuat saat itu
Prosesor 80286 yang diperkenalkan perusahaan pada tahun 1984. Apa yang kami pelajari dari ini adalah
bahwa industri komputer memiliki kebiasaan untuk terus meningkatkan akronim yang ada dengan awalan dan akhiran baru. Kami juga belajar bahwa kata sifat seperti ''lanjutan'' harus digunakan dengan sangat hati-hati, atau Anda akan terlihat konyol tiga puluh tahun ke depan.
garis.

SATA is currently the standard type of disk on many computers. Since the actual device interface is hidden behind the controller, all that the operating system
sees is the interface to the controller, which may be quite different from the interface to the device.

SATA saat ini merupakan jenis disk standar di banyak komputer. Karena antarmuka perangkat yang sebenarnya tersembunyi di balik pengontrol, semua itu adalah sistem operasi
lihat adalah antarmuka ke pengontrol, yang mungkin sangat berbeda dari antarmuka ke perangkat.

Because each type of controller is different, different software is needed to
control each one. The software that talks to a controller, giving it commands and
accepting responses, is called a device driver. Each controller manufacturer has to
supply a driver for each operating system it supports. Thus a scanner may come
with drivers for OS X, Windows 7, Windows 8, and Linux, for example.

Karena setiap jenis pengontrol berbeda, perangkat lunak yang berbeda diperlukan untuk
mengontrol masing-masing. Perangkat lunak yang berbicara dengan pengontrol, memberinya perintah dan
menerima tanggapan, disebut driver perangkat. Setiap produsen pengontrol harus
menyediakan driver untuk setiap sistem operasi yang didukungnya. Jadi pemindai mungkin datang
dengan driver untuk OS X, Windows 7, Windows 8, dan Linux, misalnya.

To be used, the driver has to be put into the operating system so it can run in
kernel mode. Drivers can actually run outside the kernel, and operating systems
like Linux and Windows nowadays do offer some support for doing so. The vast
majority of the drivers still run below the kernel boundary. Only very few current
systems, such as MINIX 3, run all drivers in user space. Drivers in user space must
be allowed to access the device in a controlled way, which is not straightforward.

Untuk menggunakannya, driver harus dimasukkan ke dalam sistem operasi agar dapat berjalan di
modus inti. Driver sebenarnya dapat berjalan di luar kernel, dan sistem operasi
seperti Linux dan Windows saat ini menawarkan beberapa dukungan untuk melakukannya. Yang luas
sebagian besar driver masih berjalan di bawah batas kernel. Hanya sangat sedikit saat ini
sistem, seperti MINIX 3, menjalankan semua driver di ruang pengguna. Pengemudi di ruang pengguna harus
diizinkan untuk mengakses perangkat dengan cara yang terkontrol, yang tidak mudah.

There are three ways the driver can be put into the kernel. The first way is to
relink the kernel with the new driver and then reboot the system. Many older UNIX
systems work like this. The second way is to make an entry in an operating system
file telling it that it needs the driver and then reboot the system. At boot time, the
operating system goes and finds the drivers it needs and loads them. Windows
works this way. The third way is for the operating system to be able to accept new
drivers while running and install them on the fly without the need to reboot. This
way used to be rare but is becoming much more common now. Hot-pluggable
devices, such as USB and IEEE 1394 devices (discussed below), always need dynamically loaded drivers

Ada tiga cara driver dapat dimasukkan ke dalam kernel. Cara pertama adalah
hubungkan kembali kernel dengan driver baru dan kemudian reboot sistem. Banyak UNIX yang lebih tua
sistem bekerja seperti ini. Cara kedua adalah membuat entri di sistem operasi
file yang mengatakan bahwa itu membutuhkan driver dan kemudian reboot sistem. Pada saat booting,
sistem operasi berjalan dan menemukan driver yang dibutuhkan dan memuatnya. jendela
bekerja dengan cara ini. Cara ketiga adalah agar sistem operasi dapat menerima yang baru
driver saat menjalankan dan menginstalnya dengan cepat tanpa perlu reboot. Ini
cara yang dulunya jarang tetapi sekarang menjadi jauh lebih umum. Hot-pluggable
perangkat, seperti perangkat USB dan IEEE 1394 (dibahas di bawah), selalu membutuhkan driver yang dimuat secara dinamis

Every controller has a small number of registers that are used to communicate
with it. For example, a minimal disk controller might have registers for specifying
the disk address, memory address, sector count, and direction (read or write). To
activate the controller, the driver gets a command from the operating system, then
translates it into the appropriate values to write into the device registers. The collection of all the device registers forms the I/O port space, a subject we will come
back to in Chap. 5.

Setiap pengontrol memiliki sejumlah kecil register yang digunakan untuk berkomunikasi
dengan itu. Misalnya, pengontrol disk minimal mungkin memiliki register untuk menentukan
alamat disk, alamat memori, jumlah sektor, dan arah (baca atau tulis). Ke
aktifkan pengontrol, pengemudi mendapat perintah dari sistem operasi, lalu
menerjemahkannya ke dalam nilai yang sesuai untuk ditulis ke dalam register perangkat. Kumpulan semua register perangkat membentuk ruang port I/O, subjek yang akan kita bahas
kembali ke dalam Bab. 5.

On some computers, the device registers are mapped into the operating system’s address space (the addresses it can use), so they can be read and written like
ordinary memory words. On such computers, no special I/O instructions are required and user programs can be kept away from the hardware by not putting these
memory addresses within their reach (e.g., by using base and limit registers). On
other computers, the device registers are put in a special I/O port space, with each
register having a port address. On these machines, special IN and OUT instructions
are available in kernel mode to allow drivers to read and write the registers. The
former scheme eliminates the need for special I/O instructions but uses up some of
the address space. The latter uses no address space but requires special instructions. Both systems are widely used

Pada beberapa komputer, register perangkat dipetakan ke dalam ruang alamat sistem operasi (alamat yang dapat digunakannya), sehingga dapat dibaca dan ditulis seperti
kata-kata memori biasa. Pada komputer seperti itu, tidak ada instruksi I/O khusus yang diperlukan dan program pengguna dapat dijauhkan dari perangkat keras dengan tidak meletakkan ini
alamat memori dalam jangkauan mereka (misalnya, dengan menggunakan register dasar dan batas). Pada
komputer lain, register perangkat diletakkan di ruang port I/O khusus, dengan masing-masing
mendaftar memiliki alamat port. Pada mesin ini, instruksi IN dan OUT khusus
tersedia dalam mode kernel untuk memungkinkan driver membaca dan menulis register. Itu
skema sebelumnya menghilangkan kebutuhan untuk instruksi I/O khusus tetapi menggunakan beberapa dari
ruang alamat. Yang terakhir tidak menggunakan ruang alamat tetapi memerlukan instruksi khusus. Kedua sistem banyak digunakan

Input and output can be done in three different ways. In the simplest method, a
user program issues a system call, which the kernel then translates into a procedure
call to the appropriate driver. The driver then starts the I/O and sits in a tight loop
continuously polling the device to see if it is done (usually there is some bit that indicates that the device is still busy). When the I/O has completed, the driver puts
the data (if any) where they are needed and returns. The operating system then returns control to the caller. This method is called busy waiting and has the disadvantage of tying up the CPU polling the device until it is finished.

Input dan output dapat dilakukan dengan tiga cara berbeda. Dalam metode yang paling sederhana,
program pengguna mengeluarkan panggilan sistem, yang kemudian diterjemahkan oleh kernel ke dalam prosedur
hubungi pengemudi yang sesuai. Pengemudi kemudian memulai I/O dan duduk dalam lingkaran yang ketat
terus melakukan polling perangkat untuk melihat apakah sudah selesai (biasanya ada beberapa bit yang menunjukkan bahwa perangkat masih sibuk). Ketika I/O telah selesai, driver menempatkan
data (jika ada) di mana mereka dibutuhkan dan dikembalikan. Sistem operasi kemudian mengembalikan kontrol ke pemanggil. Metode ini disebut sibuk menunggu dan memiliki kelemahan mengikat CPU polling perangkat sampai selesai.

The second method is for the driver to start the device and ask it to give an interrupt when it is finished. At that point the driver returns. The operating system
then blocks the caller if need be and looks for other work to do. When the controller detects the end of the transfer, it generates an interrupt to signal completion.

Metode kedua adalah driver untuk memulai perangkat dan memintanya untuk memberikan interupsi ketika selesai. Pada saat itu pengemudi kembali. Sistem operasi
kemudian memblokir penelepon jika perlu dan mencari pekerjaan lain yang harus dilakukan. Ketika pengontrol mendeteksi akhir transfer, itu menghasilkan interupsi untuk penyelesaian sinyal.

Interrupts are very important in operating systems, so let us examine the idea
more closely. In Fig. 1-11(a) we see a three-step process for I/O. In step 1, the
driver tells the controller what to do by writing into its device registers. The controller then starts the device. When the controller has finished reading or writing
the number of bytes it has been told to transfer, it signals the interrupt controller
chip using certain bus lines in step 2. If the interrupt controller is ready to accept
the interrupt (which it may not be if it is busy handling a higher-priority one), it asserts a pin on the CPU chip telling it, in step 3. In step 4, the interrupt controller
puts the number of the device on the bus so the CPU can read it and know which
device has just finished (many devices may be running at the same time).

Interupsi sangat penting dalam sistem operasi, jadi mari kita periksa idenya
lebih dekat. Pada Gambar 1-11(a) kita melihat proses tiga langkah untuk I/O. Pada langkah 1,
driver memberi tahu pengontrol apa yang harus dilakukan dengan menulis ke register perangkatnya. Pengontrol kemudian memulai perangkat. Ketika pengontrol selesai membaca atau menulis
jumlah byte yang telah diperintahkan untuk ditransfer, itu menandakan pengontrol interupsi
chip menggunakan jalur bus tertentu pada langkah 2. Jika pengontrol interupsi siap menerima
interupsi (yang mungkin tidak jika sedang sibuk menangani yang berprioritas lebih tinggi), ia menegaskan pin pada chip CPU yang memberitahukannya, pada langkah 3. Pada langkah 4, pengontrol interupsi
menempatkan nomor perangkat di bus sehingga CPU dapat membacanya dan mengetahui yang mana
perangkat baru saja selesai (banyak perangkat mungkin berjalan pada waktu yang sama).

Once the CPU has decided to take the interrupt, the program counter and PSW
are typically then pushed onto the current stack and the CPU switched into kernel
mode. The device number may be used as an index into part of memory to find the
address of the interrupt handler for this device. This part of memory is called the
interrupt vector. Once the interrupt handler (part of the driver for the interrupting
device) has started, it removes the stacked program counter and PSW and saves
them, then queries the device to learn its status. When the handler is all finished, it
returns to the previously running user program to the first instruction that was not
yet executed. These steps are shown in Fig. 1-11(b).

Setelah CPU memutuskan untuk mengambil interupsi, penghitung program dan PSW
biasanya kemudian didorong ke tumpukan saat ini dan CPU beralih ke kernel
mode. Nomor perangkat dapat digunakan sebagai indeks ke bagian memori untuk menemukan
alamat pengendali interupsi untuk perangkat ini. Bagian memori ini disebut
vektor interupsi. Setelah penangan interupsi (bagian dari driver untuk interupsi
perangkat) telah dimulai, akan menghapus penghitung program yang ditumpuk dan PSW dan menyimpan
mereka, lalu menanyakan perangkat untuk mempelajari statusnya. Ketika pawang sudah selesai, itu
kembali ke program pengguna yang berjalan sebelumnya ke instruksi pertama yang tidak
belum dieksekusi. Langkah-langkah ini ditunjukkan pada Gambar 1-11(b).

The third method for doing I/O makes use of special hardware: a DMA
(Direct Memory Access) chip that can control the flow of bits between memory
and some controller without constant CPU intervention. The CPU sets up the
DMA chip, telling it how many bytes to transfer, the device and memory addresses
involved, and the direction, and lets it go. When the DMA chip is done, it causes
an interrupt, which is handled as described above. DMA and I/O hardware in general will be discussed in more detail in Chap. 5.

Metode ketiga untuk melakukan I/O menggunakan perangkat keras khusus: DMA
(Direct Memory Access) chip yang dapat mengontrol aliran bit antar memori
dan beberapa pengontrol tanpa intervensi CPU yang konstan. CPU mengatur
Chip DMA, memberi tahu berapa banyak byte yang akan ditransfer, perangkat dan alamat memori
terlibat, dan arahnya, dan membiarkannya pergi. Ketika chip DMA selesai, itu menyebabkan
interupsi, yang ditangani seperti dijelaskan di atas. DMA dan perangkat keras I/O secara umum akan dibahas lebih detail pada Bab. 5.

Interrupts can (and often do) happen at highly inconvenient moments, for example, while another interrupt handler is running. For this reason, the CPU has a
way to disable interrupts and then reenable them later. While interrupts are disabled, any devices that finish continue to assert their interrupt signals, but the CPU
is not interrupted until interrupts are enabled again. If multiple devices finish
while interrupts are disabled, the interrupt controller decides which one to let
through first, usually based on static priorities assigned to each device. The
highest-priority device wins and gets to be serviced first. The others must wait.

Interupsi dapat (dan sering terjadi) terjadi pada saat yang sangat tidak nyaman, misalnya, saat penangan interupsi lain sedang berjalan. Untuk alasan ini, CPU memiliki
cara untuk menonaktifkan interupsi dan kemudian mengaktifkannya kembali nanti. Saat interupsi dinonaktifkan, perangkat apa pun yang selesai melanjutkan untuk menegaskan sinyal interupsinya, tetapi CPU
tidak terputus sampai interupsi diaktifkan kembali. Jika beberapa perangkat selesai
saat interupsi dinonaktifkan, pengontrol interupsi memutuskan mana yang akan dibiarkan
melalui pertama, biasanya berdasarkan prioritas statis yang ditetapkan untuk setiap perangkat. Itu
perangkat dengan prioritas tertinggi menang dan akan diservis terlebih dahulu. Yang lain harus menunggu.

1.3.5 Buses
1.3.5 Bus

The organization of Fig. 1-6 was used on minicomputers for years and also on
the original IBM PC. However, as processors and memories got faster, the ability
of a single bus (and certainly the IBM PC bus) to handle all the traffic was strained
to the breaking point. Something had to give. As a result, additional buses were
added, both for faster I/O devices and for CPU-to-memory traffic. As a consequence of this evolution, a large x86 system currently looks something like
Fig. 1-12.

Organisasi Gambar 1-6 digunakan pada komputer mini selama bertahun-tahun dan juga pada
PC IBM asli. Namun, karena prosesor dan memori menjadi lebih cepat, kemampuan
dari satu bus (dan tentu saja bus IBM PC) untuk menangani semua lalu lintas tegang
ke titik putus. Sesuatu harus diberikan. Akibatnya, bus tambahan adalah
ditambahkan, baik untuk perangkat I/O yang lebih cepat dan untuk lalu lintas CPU-ke-memori. Sebagai konsekuensi dari evolusi ini, sistem x86 besar saat ini terlihat seperti
Gambar 1-12.

This system has many buses (e.g., cache, memory, PCIe, PCI, USB, SATA, and
DMI), each with a different transfer rate and function. The operating system must
be aware of all of them for configuration and management. The main bus is the
PCIe (Peripheral Component Interconnect Express) bus.

Sistem ini memiliki banyak bus (misalnya, cache, memori, PCIe, PCI, USB, SATA, dan
DMI), masing-masing dengan kecepatan transfer dan fungsi yang berbeda. Sistem operasi harus
waspadai semuanya untuk konfigurasi dan manajemen. Bus utama adalah
Bus PCIe (Peripheral Component Interconnect Express).

The PCIe bus was invented by Intel as a successor to the older PCI bus, which
in turn was a replacement for the original ISA (Industry Standard Architecture)
bus. Capable of transferring tens of gigabits per second, PCIe is much faster than
its predecessors. It is also very different in nature. Up to its creation in 2004, most
buses were parallel and shared. A shared bus architecture means that multiple devices use the same wires to transfer data. Thus, when multiple devices have data to
send, you need an arbiter to determine who can use the bus. In contrast, PCIe
makes use of dedicated, point-to-point connections. A parallel bus architecture as
used in traditional PCI means that you send each word of data over multiple wires.
For instance, in regular PCI buses, a single 32-bit number is sent over 32 parallel
wires. In contrast to this, PCIe uses a serial bus architecture and sends all bits in
a message through a single connection, known as a lane, much like a network
packet. This is much simpler, because you do not have to ensure that all 32 bits
arrive at the destination at exactly the same time. Parallelism is still used, because
you can have multiple lanes in parallel. For instance, we may use 32 lanes to carry
32 messages in parallel. As the speed of peripheral devices like network cards and
graphics adapters increases rapidly, the PCIe standard is upgraded every 3–5 years.
For instance, 16 lanes of PCIe 2.0 offer 64 gigabits per second. Upgrading to PCIe
3.0 will give you twice that speed and PCIe 4.0 will double that again.

Bus PCIe ditemukan oleh Intel sebagai penerus bus PCI yang lebih tua, yang
pada gilirannya merupakan pengganti ISA asli (Arsitektur Standar Industri)
bis. Mampu mentransfer puluhan gigabit per detik, PCIe jauh lebih cepat daripada
para pendahulunya. Sifatnya juga sangat berbeda. Hingga pembuatannya pada tahun 2004, sebagian besar
bus paralel dan dibagi. Arsitektur bus bersama berarti bahwa beberapa perangkat menggunakan kabel yang sama untuk mentransfer data. Jadi, ketika beberapa perangkat memiliki data untuk
send, Anda memerlukan seorang arbiter untuk menentukan siapa yang dapat menggunakan bus. Sebaliknya, PCIe
memanfaatkan koneksi point-to-point khusus. Arsitektur bus paralel sebagai
digunakan dalam PCI tradisional berarti Anda mengirim setiap kata data melalui beberapa kabel.
Misalnya, dalam bus PCI biasa, satu nomor 32-bit dikirim melalui 32 paralel
kabel. Berbeda dengan ini, PCIe menggunakan arsitektur bus serial dan mengirimkan semua bit dalam
pesan melalui satu koneksi, yang dikenal sebagai jalur, seperti jaringan
paket. Ini jauh lebih sederhana, karena Anda tidak harus memastikan bahwa semua 32 bit
tiba di tempat tujuan pada waktu yang sama. Paralelisme masih digunakan, karena
Anda dapat memiliki beberapa jalur secara paralel. Misalnya, kami dapat menggunakan 32 jalur untuk membawa
32 pesan secara paralel. Seperti kecepatan perangkat periferal seperti kartu jaringan dan
adapter grafis meningkat pesat, standar PCIe ditingkatkan setiap 3-5 tahun.
Misalnya, 16 jalur PCIe 2.0 menawarkan 64 gigabit per detik. Memutakhirkan ke PCIe
3.0 akan memberi Anda kecepatan dua kali lipat dan PCIe 4.0 akan menggandakannya lagi.

Meanwhile, we still have many leg acy devices for the older PCI standard. As
we see in Fig. 1-12, these devices are hooked up to a separate hub processor. In
the future, when we consider PCI no longer merely old, but ancient, it is possible
that all PCI devices will attach to yet another hub that in turn connects them to the
main hub, creating a tree of buses.

Sementara itu, kami masih memiliki banyak perangkat lama untuk standar PCI yang lebih lama. Sebagai
kita lihat pada Gambar 1-12, perangkat ini terhubung ke prosesor hub yang terpisah. Di
masa depan, ketika kita menganggap PCI tidak lagi hanya tua, tetapi kuno, itu mungkin
bahwa semua perangkat PCI akan dilampirkan ke hub lain yang pada gilirannya menghubungkannya ke
hub utama, membuat pohon bus.

In this configuration, the CPU talks to memory over a fast DDR3 bus, to an external graphics device over PCIe and to all other devices via a hub over a DMI
(Direct Media Interface) bus. The hub in turn connects all the other devices,
using the Universal Serial Bus to talk to USB devices, the SATA bus to interact
with hard disks and DVD drives, and PCIe to transfer Ethernet frames. We hav e already mentioned the older PCI devices that use a traditional PCI bus.

Dalam konfigurasi ini, CPU berbicara ke memori melalui bus DDR3 cepat, ke perangkat grafis eksternal melalui PCIe dan ke semua perangkat lain melalui hub melalui DMI.
(Antarmuka Media Langsung) bus. Hub pada gilirannya menghubungkan semua perangkat lain,
menggunakan Universal Serial Bus untuk berbicara dengan perangkat USB, bus SATA untuk berinteraksi
dengan hard disk dan drive DVD, dan PCIe untuk mentransfer frame Ethernet. Kami telah menyebutkan perangkat PCI lama yang menggunakan bus PCI tradisional.

Moreover, each of the cores has a dedicated cache and a much larger cache that
is shared between them. Each of these caches introduces another bus.

Selain itu, masing-masing inti memiliki cache khusus dan cache yang jauh lebih besar yang
dibagi di antara mereka. Masing-masing cache ini memperkenalkan bus lain.

The USB (Universal Serial Bus) was invented to attach all the slow I/O devices, such as the keyboard and mouse, to the computer. Howev er, calling a modern USB 3.0 device humming along at 5 Gbps ‘‘slow’’ may not come naturally for
the generation that grew up with 8-Mbps ISA as the main bus in the first IBM PCs.
USB uses a small connector with four to eleven wires (depending on the version),
some of which supply electrical power to the USB devices or connect to ground.
USB is a centralized bus in which a root device polls all the I/O devices every 1
msec to see if they hav e any traffic. USB 1.0 could handle an aggregate load of 12
Mbps, USB 2.0 increased the speed to 480 Mbps, and USB 3.0 tops at no less than
5 Gbps. Any USB device can be connected to a computer and it will function immediately, without requiring a reboot, something pre-USB devices required, much
to the consternation of a generation of frustrated users.

USB (Universal Serial Bus) diciptakan untuk menghubungkan semua perangkat I/O yang lambat, seperti keyboard dan mouse, ke komputer. Namun, memanggil perangkat USB 3.0 modern dengan kecepatan 5 Gbps 'lambat' mungkin tidak datang secara alami untuk
generasi yang tumbuh dengan ISA 8-Mbps sebagai bus utama di PC IBM pertama.
USB menggunakan konektor kecil dengan empat hingga sebelas kabel (tergantung versinya),
beberapa di antaranya memasok daya listrik ke perangkat USB atau terhubung ke ground.
USB adalah bus terpusat di mana perangkat root melakukan polling semua perangkat I/O setiap 1
msec untuk melihat apakah mereka memiliki lalu lintas. USB 1.0 dapat menangani beban agregat 12
Mbps, USB 2.0 meningkatkan kecepatan menjadi 480 Mbps, dan USB 3.0 mencapai tidak kurang dari
5 Gbps. Perangkat USB apa pun dapat dihubungkan ke komputer dan akan segera berfungsi, tanpa memerlukan reboot, sesuatu yang diperlukan perangkat pra-USB, banyak
untuk kekhawatiran generasi pengguna frustrasi.

The SCSI (Small Computer System Interface) bus is a high-performance bus
intended for fast disks, scanners, and other devices needing considerable bandwidth. Nowadays, we find them mostly in servers and workstations. They can run
at up to 640 MB/sec.

Bus SCSI (Small Computer System Interface) adalah bus berkinerja tinggi
ditujukan untuk disk cepat, pemindai, dan perangkat lain yang membutuhkan bandwidth yang cukup besar. Saat ini, kami menemukan mereka sebagian besar di server dan workstation. Mereka bisa lari
hingga 640 MB/detik.

To work in an environment such as that of Fig. 1-12, the operating system has
to know what peripheral devices are connected to the computer and configure
them. This requirement led Intel and Microsoft to design a PC system called plug
and play, based on a similar concept first implemented in the Apple Macintosh.
Before plug and play, each I/O card had a fixed interrupt request level and fixed addresses for its I/O registers. For example, the keyboard was interrupt 1 and used
I/O addresses 0x60 to 0x64, the floppy disk controller was interrupt 6 and used I/O
addresses 0x3F0 to 0x3F7, and the printer was interrupt 7 and used I/O addresses
0x378 to 0x37A, and so on.

Untuk bekerja di lingkungan seperti Gambar 1-12, sistem operasi memiliki:
untuk mengetahui perangkat periferal apa yang terhubung ke komputer dan mengkonfigurasi
mereka. Persyaratan ini mendorong Intel dan Microsoft untuk merancang sistem PC yang disebut plug
dan bermain, berdasarkan konsep serupa yang pertama kali diterapkan di Apple Macintosh.
Sebelum plug and play, setiap kartu I/O memiliki tingkat permintaan interupsi tetap dan alamat tetap untuk register I/O-nya. Misalnya, keyboard interupsi 1 dan digunakan
Alamat I/O 0x60 hingga 0x64, pengontrol floppy disk diinterupsi 6 dan menggunakan I/O
alamat 0x3F0 hingga 0x3F7, dan printer diinterupsi 7 dan menggunakan alamat I/O
0x378 hingga 0x37A, dan seterusnya.

So far, so good. The trouble came in when the user bought a sound card and a
modem card and both happened to use, say, interrupt 4. They would conflict and
would not work together. The solution was to include DIP switches or jumpers on
ev ery I/O card and instruct the user to please set them to select an interrupt level
and I/O device addresses that did not conflict with any others in the user’s system.
Teenagers who devoted their lives to the intricacies of the PC hardware could
sometimes do this without making errors. Unfortunately, nobody else could, leading to chaos

Sejauh ini bagus. Masalah datang ketika pengguna membeli kartu suara dan
kartu modem dan keduanya kebetulan menggunakan, katakanlah, interupsi 4. Mereka akan konflik dan
tidak akan bekerja sama. Solusinya adalah dengan memasukkan sakelar atau jumper DIP
setiap kartu I/O dan menginstruksikan pengguna untuk menyetelnya untuk memilih tingkat interupsi
dan alamat perangkat I/O yang tidak bertentangan dengan yang lain di sistem pengguna.
Remaja yang mengabdikan hidup mereka untuk kerumitan perangkat keras PC bisa
terkadang melakukan ini tanpa membuat kesalahan. Sayangnya, tidak ada orang lain yang bisa, menyebabkan kekacauan

What plug and play does is have the system automatically collect information
about the I/O devices, centrally assign interrupt levels and I/O addresses, and then
tell each card what its numbers are. This work is closely related to booting the
computer, so let us look at that. It is not completely trivial.

Apa yang dilakukan plug and play adalah membuat sistem secara otomatis mengumpulkan informasi
tentang perangkat I/O, menetapkan tingkat interupsi dan alamat I/O secara terpusat, dan kemudian
beri tahu setiap kartu berapa nomornya. Pekerjaan ini terkait erat dengan booting
komputer, jadi mari kita lihat itu. Hal ini tidak sepenuhnya sepele.

1.3.6 booting the computer
1.3.6 mem-boot komputer

Very briefly, the boot process is as follows. Every PC contains a parentboard
(formerly called a motherboard before political correctness hit the computer industry). On the parentboard is a program called the system BIOS (Basic Input Output System). The BIOS contains low-level I/O software, including procedures to
read the keyboard, write to the screen, and do disk I/O, among other things. Nowadays, it is held in a flash RAM, which is nonvolatile but which can be updated by
the operating system when bugs are found in the BIOS.

Secara singkat, proses booting adalah sebagai berikut. Setiap PC berisi papan induk
(sebelumnya disebut motherboard sebelum kebenaran politik menghantam industri komputer). Di papan induk adalah program yang disebut sistem BIOS (Basic Input Output System). BIOS berisi perangkat lunak I/O tingkat rendah, termasuk prosedur untuk:
membaca keyboard, menulis ke layar, dan melakukan disk I/O, antara lain. Saat ini, disimpan dalam flash RAM, yang tidak mudah menguap tetapi dapat diperbarui oleh
sistem operasi ketika bug ditemukan di BIOS.

When the computer is booted, the BIOS is started. It first checks to see how
much RAM is installed and whether the keyboard and other basic devices are installed and responding correctly. It starts out by scanning the PCIe and PCI buses
to detect all the devices attached to them. If the devices present are different from
when the system was last booted, the new devices are configured.

Ketika komputer di-boot, BIOS dimulai. Ini pertama kali memeriksa untuk melihat caranya
banyak RAM yang terpasang dan apakah keyboard dan perangkat dasar lainnya dipasang dan merespons dengan benar. Ini dimulai dengan memindai bus PCIe dan PCI
untuk mendeteksi semua perangkat yang terpasang padanya. Jika perangkat yang ada berbeda dari
ketika sistem terakhir kali di-boot, perangkat baru dikonfigurasi.

The BIOS then determines the boot device by trying a list of devices stored in
the CMOS memory. The user can change this list by entering a BIOS configuration
program just after booting. Typically, an attempt is made to boot from a CD-ROM
(or sometimes USB) drive, if one is present. If that fails, the system boots from the
hard disk. The first sector from the boot device is read into memory and executed.
This sector contains a program that normally examines the partition table at the
end of the boot sector to determine which partition is active. Then a secondary boot
loader is read in from that partition. This loader reads in the operating system
from the active partition and starts it.

BIOS kemudian menentukan perangkat boot dengan mencoba daftar perangkat yang disimpan di
memori CMOS. Pengguna dapat mengubah daftar ini dengan memasukkan konfigurasi BIOS
program setelah boot. Biasanya, upaya dilakukan untuk boot dari CD-ROM
(atau terkadang USB), jika ada. Jika gagal, sistem akan melakukan boot dari
harddisk. Sektor pertama dari perangkat boot dibaca ke dalam memori dan dieksekusi.
Sektor ini berisi program yang biasanya memeriksa tabel partisi di
akhir sektor boot untuk menentukan partisi mana yang aktif. Kemudian boot sekunder
loader dibaca dari partisi itu. Loader ini membaca di sistem operasi
dari partisi aktif dan memulainya.

The operating system then queries the BIOS to get the configuration information. For each device, it checks to see if it has the device driver. If not, it asks
the user to insert a CD-ROM containing the driver (supplied by the device’s manufacturer) or to download it from the Internet. Once it has all the device drivers, the
operating system loads them into the kernel. Then it initializes its tables, creates
whatever background processes are needed, and starts up a login program or GUI

Sistem operasi kemudian menanyakan BIOS untuk mendapatkan informasi konfigurasi. Untuk setiap perangkat, ia akan memeriksa apakah ia memiliki driver perangkat. Jika tidak, ia bertanya
pengguna untuk memasukkan CD-ROM yang berisi driver (disediakan oleh produsen perangkat) atau untuk mengunduhnya dari Internet. Setelah memiliki semua driver perangkat,
sistem operasi memuatnya ke dalam kernel. Kemudian itu menginisialisasi tabelnya, membuat
proses latar belakang apa pun yang diperlukan, dan memulai program login atau GUI

1.4 THE OPERATING SYSTEM ZOO
1.4 SISTEM OPERASI KEBUN BINATANG

Operating systems have been around now for over half a century. During this
time, quite a variety of them have been developed, not all of them widely known.
In this section we will briefly touch upon nine of them. We will come back to
some of these different kinds of systems later in the book.

Sistem operasi telah ada selama lebih dari setengah abad. Selama ini
Saat ini, cukup beragam yang telah dikembangkan, tidak semuanya dikenal luas.
Pada bagian ini kita akan secara singkat menyentuh sembilan di antaranya. Kami akan kembali ke
beberapa jenis sistem yang berbeda ini nanti dalam buku ini.

1.4.1 Main Operating Systems
1.4.1 Sistem Operasi Utama

At the high end are the operating systems for mainframes, those room-sized
computers still found in major corporate data centers. These computers differ from
personal computers in terms of their I/O capacity. A mainframe with 1000 disks
and millions of gigabytes of data is not unusual; a personal computer with these
specifications would be the envy of its friends. Mainframes are also making something of a comeback as high-end Web servers, servers for large-scale electronic
commerce sites, and servers for business-to-business transactions.

Di kelas atas adalah sistem operasi untuk mainframe, yang berukuran ruangan itu
komputer masih ditemukan di pusat data perusahaan besar. Komputer ini berbeda dari
komputer pribadi dalam hal kapasitas I/O mereka. Sebuah mainframe dengan 1000 disk
dan jutaan gigabyte data tidak biasa; komputer pribadi dengan ini
spesifikasi akan membuat iri teman-temannya. Mainframe juga membuat comeback sebagai server Web kelas atas, server untuk elektronik skala besar
situs perdagangan, dan server untuk transaksi bisnis-ke-bisnis.

The operating systems for mainframes are heavily oriented toward processing
many jobs at once, most of which need prodigious amounts of I/O. They typically
offer three kinds of services: batch, transaction processing, and timesharing. A
batch system is one that processes routine jobs without any interactive user present.
Claims processing in an insurance company or sales reporting for a chain of stores
is typically done in batch mode. Transaction-processing systems handle large numbers of small requests, for example, check processing at a bank or airline reservations. Each unit of work is small, but the system must handle hundreds or thousands per second. Timesharing systems allow multiple remote users to run jobs on
the computer at once, such as querying a big database. These functions are closely
related; mainframe operating systems often perform all of them. An example
mainframe operating system is OS/390, a descendant of OS/360. However, mainframe operating systems are gradually being replaced by UNIX variants such as
Linux.

Sistem operasi untuk mainframe sangat berorientasi pada pemrosesan
banyak pekerjaan sekaligus, yang sebagian besar membutuhkan jumlah I/O yang luar biasa. Mereka biasanya
menawarkan tiga jenis layanan: batch, pemrosesan transaksi, dan pembagian waktu. SEBUAH
sistem batch adalah salah satu yang memproses pekerjaan rutin tanpa kehadiran pengguna interaktif.
Pemrosesan klaim di perusahaan asuransi atau pelaporan penjualan untuk rantai toko
biasanya dilakukan dalam mode batch. Sistem pemrosesan transaksi menangani sejumlah besar permintaan kecil, misalnya, pemrosesan cek di bank atau reservasi maskapai penerbangan. Setiap unit kerja kecil, tetapi sistem harus menangani ratusan atau ribuan per detik. Sistem pembagian waktu memungkinkan banyak pengguna jarak jauh untuk menjalankan pekerjaan di
komputer sekaligus, seperti query database besar. Fungsi-fungsi ini erat
terkait; sistem operasi mainframe sering melakukan semuanya. Sebuah contoh
sistem operasi mainframe adalah OS/390, turunan dari OS/360. Namun, sistem operasi mainframe secara bertahap digantikan oleh varian UNIX seperti:
Linux.