# Driver-Violation-in-Jakarta-Polytechnic-State
In this era, technology is developing so rapidly. More and more new inventions and technological developments that already exist which have a variety of positive impacts and help overcome problems that are often experienced by humans. In this case, the use of technology is used to take action against motorists who break the rules.

# 1. Planning and Implementation
Four machine learning models were developed, each with special abilities. the capacity to identify a vehicle's type through pictures and videos, determine whether the driver is wearing a helmet, identify a vehicle's license plate and take a photo of it to identify the letters and numbers, and calculate the speed of the driver's car on the highway. This methodology can be used by security forces to evaluate violations that take place in their assigned territory. The talk starts with developing application systems and application programs.

# 2. How the app works?
The following is a picture of the camera used and installed in a place at the Politeknik Negeri Jakarta
<p>
  <img src = 

Cara kerja program aplikasi digambarkan dengan menggunakan diagram flowchart. Flowchart diagram menggambarkan urutan proses secara mendetail dan hubungan antara suatu proses dengan proses lainnya dalam suatu sistem.

Gambar 3. 1 Cara kerja model machine learning deteksi pelanggaran di
Politeknik Negeri Jakarta




Gambar 3.1 merupakan flowchart yang menggambarkan proses berjalannya model dalam menentukan klasifikasi tugas yang akan dijalankan. Sistem dimulai ketika dataset dimasukkan ke model yang ingin kita cari sebagai contoh. Sistem mengetahui terlebih dahulu jenis kendaraan yang ada di tempat kejadian lalu plat nomor kendaraan yang kebetulan menggunakan jalan tersebut, dan terakhir mengecek dengan hasil inputan dari kamera yang ada di tempat kejadian, apakah ada pelanggaran yang terjadi di jalan tersebut seperti melewati batas kecepatan untuk semua jenis kendaraan maupun wajib pemakaian helm bagi pengendara motor yang menggunakan jalan tersebut. Sistem melakukan input satu – satu untuk setiap model yang diujikannya lalu model akan diuji dengan footage yang didapat dari kamera tempat kejadian. Dan pada akhirnya, akan keluar hasil analisa yang dibuat oleh model baik dalam bentuk foto maupun video tergantung dari kemampuan  model dalam menerima objek ujinya.
1.      Deteksi Jenis Kendaraan

Gambar 3. 2 Diagram Alur Model deteksi Jenis Kendaraan




Gambar 3.2 merupakan flowchart yang menggambarkan proses Deteksi Jenis Kendaraan dilakukan di google collaboratory. Di google collaboratory. akan dimasukkan dataset, library dan foto/video inputan dari kamera pengawas.
Setelah memasukkan 3 item tersebut, callbacks akan dipanggil. Lalu, mengatur direktori untuk memastikan bahwa direktorinya telah  mengarahkan ke dataset yang diinginkan. Pemanggilan callback untuk memastikan agar data yang akan dilatih kelak tidak mencapai 98%. Karena jika sampai 98%, maka model machine learning memiliki kecenderungan dalam menilai target dengan hasil yang tidak tepat sesuai dengan aturan main confusion matrix.
Lalu membaca dan mengatur dataset dalam hal ini adalah melakukan edit terhadap dataset yang sudah ada. Edit dilakukan pada dataset untuk membagi kelas (kelas jenis kendaraan) yang berisi gambar – gambar untuk dimasukkan sebagai data training dan data validation. Setelah membaca dan mengatur dataset. Akan dilanjutkan dengan setting, compile dan pelatihan model machine learning. Di tahap ini, setting akan dilakukan kepada arsitektur convolutional neural network (CNN), melakukan compile dan mengatur berapa lama model akan dilatih. Dan diakhiri dengan menampilkan grafik dari hasil latih model machine learning.
Setelah langkah menampilkan grafik hasil latih model machine learning. Yolov5 akan dipanggil untuk melatih kembali model yang sudah dibuat sebelumnya. memanggil requirement.txt untuk mendenial error yang seharusnya tidak muncul, memasukkan model uji berupa video untuk dimasukkan analisa model deteksi jenis kendaraan. Dan terakhir mengunduh file video yang sudah dilatih kembali oleh yolov5.



2.      Deteksi Penggunaan Helm

Gambar 3. 3 Diagram Alur Model deteksi Penggunaan Helm Gambar 3.3 merupakan flowchart yang menggambarkan proses
Diagram deteksi penggunaan Helm akan dijelaskan melalui 2 jalur yakni jalur
Roboflow dan jalur Google Collaboratory. Jalur dari kedua ini berakhir di saat dataset dari roboflow melakukan export di google collaboratory dan berlanjut dari tahap tersebut sampai trained weights digunakan untuk melatih kembali model machine learning untuk dicari gambar dari berbagai kelas (helmet, no_helmet, no helmet) yang mana model yang yakin akan kebenarannya diatas 40%
A.        Roboflow
Pada tahap ini dataset dibuat di platform roboflow. Di roboflow,  pencarian dataset yang ideal dari berbagai macam sumber yang mana di roboflow akan dilakukan tahap annotate pada gambar dan generate dataset. Setelah semuanya tuntas, dataset akan di export menuju google collaboratory melalui baris kode yang dibuat oleh roboflow.



B.       Google Collaboratory
Di google collaboratory, dilakukan pengunduhan dependencies, melakukan import library yang akan digunakan memasukkan repository yolov5, memilih runtime GPU. Mengunduh dependencies, melakukan import library dan memasukkan yolov5 untuk mendukung kebutuhan model machine learning. Memasukkan yolov5 agar kemampuan melakukan object deteksi menjadi jauh lebih baik.
Setelah pada jalur Roboflow menyelesaikan tugasnya untuk melakukan export dataset yang di edit. Model akan dimasukkan ke dalam direktori yolov5. Di direktori ini, model dilatih kembali, menghasilkan sebuah grafik analisis model, dan mendapatkan trained weights. Trained weights digunakan untuk mendeteksi sebuah file yang berisi gambar yang telah latih lalu untuk dilatih kembali. setelah selesai dilatih oleh Trained weights. Model yang sudah dilatih dengan Trained Weights akan mendeteksi gambar yang ada di sebuah folder dan menampilkan gambar di layar oleh model yang memiliki tingkat keyakinan benar di atas 40%. Selesai

3.     Deteksi Pembacaan Plat Nomor

Gambar 3. 4 Diagram Alur Model deteksi Pembacaan Plat Nomor




Deteksi dan Pembacaan plat nomor dikerjakan di kaggle bukan google collaboratory seperti sebelumnya. Pengerjaan dimulai pada pengambilan dataset yang mana terintegrasi dengan file .xml. File .xml adalah sebuah file yang berisi informasi untuk koordinat bounding box untuk file foto baik untuk foto berformat .jpg maupun .PNG. Setelah mendapatkan dataset yang terintegrasi dengan file .xml tadi.
Dilanjutkan dengan pengerjaan di code editor yang dipunyai oleh kaggle itu sendiri. Di code editor kaggle sendiri. Dilakukan instalasi Imutils dan melakukan import library yang diperlukan terlebih dahulu. Install imutils dilakukan untuk mendukung proses contour yang akan dilakukan di kaggle code editor. Di tahap selanjutnya, dilakukan pemanggilan path gambar yang akan diuji.
Untuk pengujian model deteksi plat nomor, diperlukan beberapa tahapan agar model pada akhirnya dapat membaca tulisan di plat nomor mobil. Dimulai dari mengubah warna gambar target menjadi warna abu – abu secara keseluruhan, dilanjutkan dengan mengubah proses filter noise dan edge detection.
Proses filter noise dilakukan untuk mengurangi noise yang terjadi dan edge detection/deteksi tepi digunakan untuk mengidentifikasi titik-titik dalam gambar digital di mana kecerahan gambar berubah tajam atau, lebih formal, dan memiliki diskontinuitas. Metode yang digunakan di di deteksi tepi kali ini adalah metode canny. Penggunaan metode canny ini dikarenakan metode ini mampu mendeteksi diskontinuitas yang jauh lebih banyak dibanding dengan metode deteksi tepi yang lain, seperti metode sobel, prewit dan robert yang kurang efektif dalam melakukan pendeteksian tepi dibanding metode canny. Setelah dilakukan proses deteksi tepi dan proses mengurangi proses mengurangi noise, maka gambar target menjadi gambar yang memiliki kontur dan berwarna dasar hitam pekat. masuk ke bagian implementasi          kontur/contour. Penggunaan kontur/contour untuk mendeteksi kontur/contour yang ada pada gambar target. Penggunaan deteksi tepi dengan metode canny untuk




mencari kontur/contour yang dapat terdeteksi dengan baik oleh sistem pada gambar target. Keluaran dari proses ini adalah didapatkannya lokasi plat nomor berada dalam bentuk matriks.
Langkah selanjutnya dilakukan masking dan pembacaan plat nomor yang dibantu oleh library easyOCR. Gambar target akan dimasking di koordinat lokasi plat nomor dan rentang wilayah yang ditentukan. Keluaran dari hasil ini adalah gambar target hanya menunjukkan bagian plat nomor saja dan di sekelilingnya luar dari plat nomor, warna menjadi hitam. Setelah mendapatkan visual lempeng plat nomor, sistem diminta untuk menunjukkan hasil lempengan plat nomor dengan sistem menunjukkan gambar kerat yang menunjukkan lempengan plat nomor, lalu gambar keratan tersebut diberi warna abu – abu secara keseluruhan. Gambar keratan diberi warna abu – abu secara keseluruhan untuk mendukung library easyOCR untuk membaca dan memberikan keluaran hasil dari bacaannya. Setelah hasil pembacaan plat nomor didapatkan, tampilan akan kembali ke gambar target seperti di awal dengan perbedaan yang mana adanya bounding box dan hasil bacaan plat nomor yang muncul di gambar target tersebut.
4.   Deteksi Kecepatan para pengendara


Gambar 3. 5 Diagram Alur Model deteksi kecepatan para pengendara Deteksi kecepatan pengendara sama seperti deteksi plat nomor
pengendara dilakukan di kaggle. Inputan yang dibutuhkan dalam proses




coding di bagian ini adalah melakukan instalasi ubuntu package (libgtk2.0 – dev), import library yang dibutuhkan, video uji dan cascade. Cascade adalah sebuah file yang berisi bounding box tapi untuk file video. File cascade ini berbentuk .xml.
Di code editor, Kecepatan didefinisikan untuk objek kendaraan, lalu mendefinisikan pelacakan untuk menentukan target mana di video tersebut untuk diketahui kecepatan dari kendaraan dan terakhir menghapus pelacakan karena bukan di dalam wilayah pelacakan yang sudah ditentukan sebelumnya lewat file cascade tadi. Terakhir, adanya sebuah baris kode untuk mengunduh hasil dari analisis model diinputkan video uji.
Setelah dilakukan pendefinisian kecepatan, pelacakan, dan penghapusan. Program akan dijalankan, lalu mengunduh file output.avi yang di dalam keluaran video tersebut sudah terdapat hasil analisa dari program yang sudah dijalankan sebelumnya.

Realisasi dan Visualisasi Model
Realisasi dan Visualisasi Model akan berfokus ke arah bagaimana masing – masing model dibangun, bagaimana setiap foto atau video dari berbagai macam dataset digunakan, dan output dari masing – masing model machine learning dipresentasikan baik dalam bentuk foto maupun dalam bentuk video.
Realisasi dan Visualisasi Model deteksi Jenis Kendaraan
Membangun model machine learning
Pada bagian ini. Akan dijelaskan kode yang harus ada untuk pengembangan model agar model dapat menjalankan tugas yang diinginkan.

Gambar 3. 8 Kode untuk dapat mengambil dataset dari Google Drive Kode diatas digunakan untuk mengimport file dari Google Drive
untuk dimasukkan ke dalam Google Collaboratory


Gambar 3. 9 Kode untuk ambil dataset, unzip, dan mengarahkan
direktori


Kode diatas digunakan untuk mengarahkan direktori google collab dalam mengambil data, lalu melakukan unzip dan terakhir mengarahkan direktori google untuk melatih secara spesifik model di direktori yang diinginkan 






Gambar 3. 10 Kode untuk mengatur pembagian kelas dan diaturnya gambar - gambar yang ada di dataset

Kode ini berguna untuk mengedit gambar di dalam dataset dan memasukkan gambar – gambar tersebut menjadi kelas kelas tertentu
Gambar 3. 11 Pelatihan Model

Terlihat arsitektur convolutional neural network (cnn) digunakan dalam model. model.compile digunakan untuk setup loss, optimizer dan metrics. history = model.fit digunakan untuk melatih model







Gambar 3. 12 Memanggil yolov5
Kode untuk memanggil yolov5 dari direktori github, hal ini diperlukan untuk memasukkan yolov5 ke dalam model

Gambar 3. 13 Mengunduh package yolov5 yang ada di file
requirements.txt
Penggunaan package ini untuk mengunduh library yang dibutuhkan oleh yolov5


Gambar 3. 14 Kode untuk memasukkan alat untuk diuji

Kode ini digunakan untuk memasukkan inputan video ke dalam google collaboratory untuk dianalisa oleh model






Gambar 3. 15 Memanggil file detect.py untuk mendeteksi objek yang ada
di video
Memanggil file detect.py untuk mendeteksi objek yang ada di video



Gambar 3. 16 Mengunduh Video yang sudah dilatih oleh model

Di tahap ini, hasil analisa bisa di unduh untuk kita lihat kemampuan model dalam menganalisis video yang sudah dimasukkan.

Mengolah dataset untuk menjadi hasil data
Pada bagian ini. Akan dijelaskan asal dataset yang digunakan model machine learning untuk belajar memahami sehingga model dapat bekerja dengan yang diinginkan.
Dataset yang dipakai adalah sebuah kumpulan foto yang berformat .jpg. dataset ini didapatkan secara gratis dari kaggle yang juga sebagai penyedia footage berupa foto dan video dalam berbagai macam format.
Dataset yang sudah didapatkan, lalu disimpan ke dalam google drive dengan nama folder dataset.zip

Gambar 3. 17 dataset jenis kendaraan di Google drive




Di google collab, dilakukan tindakan autentikasi sebelum mendapatkan akses dari google drive untuk dapat secara otomatis mengunduh dataset. melakukan pengaturan tempat penyimpanan dataset dan mengatur direktori yang ada file datasetnya seperti berikut:


Gambar 3. 18 Kode agar dataset dapat digunakan


Setelah dataset berhasil dimasukkan , maka dataset akan diolah oleh model untuk dianalisa dan diberikan hasil dari analisisnya. 

Output model machine learning
Pada bagian ini. Akan ditunjukkan hasil dari kerja               model machine learning dalam bentuk sebuah footage foto.
Output dari hasil model ini berupa video dan akan disajikan di laporan ini sebagai footage foto.





Gambar 3. 19 Deteksi Jenis Kendaraan Bus di PNJ
(1)

Gambar 3. 20 Deteksi Jenis Kendaraan Mobil di PNJ
(2)


Gambar 3. 21 Deteksi Jenis Kendaraan Motor di PNJ
(3)


Gambar 3. 22 Deteksi Jenis Kendaraan di PNJ(4)



Kumpulan gambar diatas adalah footage yang berasal dari model.

Realisasi dan Visualisasi Model deteksi Helm Pengendara
Membangun model machine learning
Pada bagian ini. Dijelaskan kode yang harus ada untuk pengembangan model agar model dapat menjalankan tugas yang diinginkan.





Gambar 3. 23 Kode untuk memastikan             bahwa runtime yang dipakai
adalah GPU




Gambar 3. 24 Memanggil yolov5


Kode diatas ini adalah kode untuk memastikan bahwa runtime yang berjalan sedang menggunakan GPU lalu memanggil yolov5 sebagai library untuk mendeteksi objek.


Gambar 3. 25 Menginstal dependencies

Penginstalan dependencies digunakan untuk mengunduh beberapa library yang diperlukan oleh model

Gambar 3. 26 Memanggil dataset dari roboflow
Kode diatas untuk memanggil dataset dari roboflow yang mana roboflow sendiri digunakan untuk tempat penyimpanan dataset untuk dilatih oleh model.








Gambar 3. 27 Arsitektur yolov5 dalam bentuk kode


Berikut	adalah	bentuk	arsitektur	dari	yolov5	jika diimplementasikan dalam bentuk kode








Gambar 3. 28 Melakukan pelatihan model terhadap dataset

Kode ini digunakan untuk melatih model di google collaboratory

Gambar 3. 29 Melakukan pelatihan kembali dengan trained weights
Di sini trained weights yang sudah didapatkan dari pelatihan sebelumnya digunakan untuk melatih kembali agar mendapatkan model mendapatkan akurasi yang jauh lebih baik.
Mengolah dataset untuk menjadi hasil data
Pada bagian ini, Dijelaskan asal dataset yang digunakan model machine learning untuk belajar memahami sehingga model dapat bekerja dengan yang diinginkan.
Dataset yang dipakai adalah sebuah kumpulan foto yang berformat .jpg. dataset ini didapatkan secara gratis dari roboflow yang juga sebagai penyedia footage berupa foto dan video dalam berbagai macam format.





Gambar 3. 30 Contoh gambar yang di Annotated        dengan kelas helmet

Gambar 3. 31 Contoh gambar yang di Annotated  dengan kelas no helmet




Diatas merupakan gambar yang sedang dalam proses Annotated di roboflow. Untuk gambar 3.30. selain terlihat gambar 2 orang yang menggunakan helm, terlihat juga kotak berwarna hijau ke kuning – kuningan yang dilabelkan sebagai helmet. Begitu pula di gambar 3.31, tidak terlihat seorang wanita, tetapi juga terlihat kotak berwarna ungu yang dilabelkan sebagai no helmet


Gambar 3. 32 File yang berisi kelas dan posisi bounding box untuk gambar yang sudah di annotated

File diatas merupakan koordinat dari kotak yang sudah dibahas sebelumnya. Angka satu itu menandakan kelas dari label pada gambar tersebut sedangkan untuk angka – angka desimal dimaksudkan sebagai posisi kotak yang dibahas sebelumnya berada.



	


	




Diroboflow, dilakukan annotated gambar agar gambar dapat dibaca oleh model yang dibuat. Annotated  gambar yang dilakukan di roboflow adalah dengan memberikan sebuah kotak pada gambar agar model machine learning  dapat   mengetahui dengan persis objek yang mana yang dideteksi beserta koordinat dari kotak yang ada di gambar tersebut. Koordinat kotak yang dimaksud akan dimasukkan oleh sistem roboflow dalam format yang diinginkan oleh usernya. dalam kasus ini, penyimpan file – file tersebut dalam bentuk .txt
Setelah dataset yang diperlukan sudah melalui proses annotated gambar. Dataset akan dimasuk ke generated untuk dilakukan pembagian set folder menjadi tiga bagian yaitu,
Training Set 69%
Validation Set 19%
Testing Set 11%


Gambar 3. 33 Pembagian set untuk dataset di Roboflow
Dalam kasus ini, pembagian dataset dipecah menjadi 25:7:4 untuk menghindari terjadi Overfitting pada saat melatih model machine learning.







Gambar 3. 34 Proses Preprocessing



Gambar 3. 35 Proses Augmentation





proses data augmentasi dan preprocessing data. Di dua tahap ini, diberikan keluasaan oleh roboflow dalam memilih metode yang akan dipakai pada setiap proses di bagian data augmentasi dan preprocessing data. Dalam hal ini, pengaturan hanya dilakukan mengatur dua proses  tersebut seperti pada gambar di atas.


Gambar 3. 36 Melakukan Generate di Roboflow

Ini adalah tahap akhir sebelum gambar bisa digunakan sebagai dataset di google collab. Di tahap ini, roboflow memberikan banyak pilihan ukuran versi yang bisa digunakan.






Gambar 3. 37 Export kode untuk Google Collab
Setelah gambar selesai diatur. Dilakukan generate gambar yang nantinya untuk bisa dikerjakan di google collab. Dilakukan export file dataset tersebut dalam bentuk kode agar bisa dipanggil ke dalam google collab.

Gambar 3. 38 Export kode di Google Collab
Berikut adalah hasil export kode di Google Collab.

Output model machine learning
Pada bagian ini. Akan ditunjukkan hasil dari kerja model machine learning dalam bentuk footage foto.





Gambar 3. 39 Deteksi Helm(1)

Gambar 3. 40 Deteksi Helm di PNJ(1)


Gambar 3. 41 Deteksi Helm(1)


Gambar 3. 42 Deteksi Helm di PNJ(2)


Kumpulan gambar diatas adalah footage yang berasal dari model.

Realisasi dan Visualisasi Model deteksi Plat Nomor Kendaraan
Membangun model machine learning
Pada bagian ini. Akan dijelaskan kode yang harus ada untuk pengembangan model agar model dapat menjalankan tugas yang diinginkan.


Gambar 3. 43 Memanggil Imutils

Library Imutils digunakan untuk mendukung model dalam   memanipulasi gambar baik untuk melakukan translation, rotation, resizing, dan skeletonization






Gambar 3. 44 Memanggil Gambar untuk diubah seutuhnya menjadi
warna abu - abu
Gambar dimasukkan ke dalam kode untuk diolah. Pengolahan gambar diawali dengan mengubah gambar tersebut menjadi abu – abu

Gambar 3. 45 Gambar di filter dan dicari tepinya
Pada gambar diatas, gambar yang sudah diubah menjadi abu – abu. Di tahap ini, gambar di filter dengan noise reduction dan edge detection untuk menghasilkan gambar yang berkontur dengan dominasi warna hitam.

Gambar 3. 46 Kode untuk mengetahui dugaan plat nomor berada

Kode diatas digunakan untuk mengetahui letak yang diduga tempat plat nomor berada
	
	








Gambar 3. 47 Kode untuk memanggil kontur dan masking
Kode ini di atas digunakan untuk memanggil kontur dan memulai proses masking.

Gambar 3. 48 Kode untuk melakukan masking dengan tujuan mencari lempengan plat nomor lalu gambar dikerat

Kode di atas digunakan untuk melakukan masking dengan tujuan mencari lempengan plat nomor lalu gambar dikerat.
Gambar 3. 49 Kode agar model dapat membaca tulisan atau angka yang terdapat di lempengan plat nomor

Kode di atas digunakan oleh model untuk dapat membaca tulisan atau angka yang terdapat di lempengan plat nomor






Gambar 3. 50 Kode untuk menampilkan hasil bacaan berbarengan dengan foto inputan untuk dideteksi plat nomornya

Kode diatas digunakan untuk menampilkan hasil bacaan berbarengan dengan foto inputan untuk dideteksi plat nomornya

Mengolah dataset untuk menjadi hasil data
Pada bagian ini. Akan dijelaskan asal dataset yang digunakan model machine learning untuk belajar memahami sehingga model dapat bekerja dengan yang diinginkan.
Dataset plat nomor didapatkan dari kaggle lalu dimasukkan ke dalam code editor kaggle dengan menginput dataset yang diinginkan di ujung kanan tampilan browser

Gambar 3. 51 Proses mencari dataset di kaggle

Gambar diatas adalah tampilan di kaggle untuk mencari
dataset







Gambar 3. 52 Direktori model plat nomor di kaggle
Dataset siap digunakan di kaggle code editor

Output model machine learning

Pada bagian ini. Akan ditunjukkan hasil dari kerja           model machine learning dalam bentuk footage foto.



Gambar 3. 53 Mobil (1)

Gambar 3. 54 Mobil (2)


Gambar 3. 55 Mobil (3)


Gambar 3. 56 Plat Nomor (1)


Gambar 3. 57 Plat Nomor (2)


Gambar 3. 58 Mobil (4)


Kumpulan gambar diatas adalah footage yang berasal dari model.





Realisasi dan Visualisasi Model deteksi Kecepatan Kendaraan
Membangun model machine learning
Pada bagian ini. Akan dijelaskan kode yang harus ada untuk pengembangan model agar model dapat menjalankan tugas yang diinginkan.


Gambar 3. 59 Kode untuk menginstall opencv di kaggle

Opencv digunakan untuk mendeteksi objek yang ada di sebuah gambar maupun video


Gambar 3. 60 Menginstall ubuntu package
Penginstalan ubuntu package untuk membantu model dalam mendeteksi kecepatan.

Gambar 3. 61 Algoritma Kecepatan



Pada gambar ini ditujukan algoritma kecepatan yang digunakan untuk mendeteksi kecepatan pada kendaraan bermotor

Mengolah dataset untuk menjadi hasil data
Pada bagian ini. Akan dijelaskan asal dataset yang digunakan model machine learning untuk belajar memahami sehingga model dapat bekerja dengan yang diinginkan.
Sama seperti cara mencari datasetnya deteksi plat nomor dengan cara mencari lalu menambahkan dataset langsung di kaggle code editornya langsung dan dapat langsung digunakan untuk menjadi bahan untuk model machine learning .






Gambar 3. 62 Proses mencari dataset di kaggle

Terlihat gambar pop – up untuk memilih dataset yang diinginkan. Disini juga bisa menggunakan dataset sendiri jika sudah di unduh ke kaggle sebelumnya


Gambar 3. 63 Direktori model kecepatan kendaraan di kaggle Gambar ini menunjukkan bahwa dataset berhasil dimasukkan ke dalam input di kaggle
Output model machine learning
Pada bagian ini.  Akan ditunjukkan hasil dari kerja         model machine learning dalam bentuk footage foto.
Output dari hasil model ini berupa video dan akan disajikan di laporan ini sebagai footage foto





Gambar 3. 64 Model Kecepatan

Gambar 3. 65 Model Kecepatan di PNJ


Gambar - gambar diatas adalah footage yang berasal dari model.
