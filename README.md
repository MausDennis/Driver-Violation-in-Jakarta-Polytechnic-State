# Driver-Violation-in-Jakarta-Polytechnic-State
In this era, technology is developing so rapidly. More and more new inventions and technological developments that already exist which have a variety of positive impacts and help overcome problems that are often experienced by humans. In this case, the use of technology is used to take action against motorists who break the rules.

# 1. Planning and Implementation
Four machine learning models were developed, each with special abilities. the capacity to identify a vehicle's type through pictures and videos, determine whether the driver is wearing a helmet, identify a vehicle's license plate and take a photo of it to identify the letters and numbers, and calculate the speed of the driver's car on the highway. This methodology can be used by security forces to evaluate violations that take place in their assigned territory. The talk starts with developing application systems and application programs.

# 2. How the app works?
The following is a picture of the camera used and installed in a place at the Politeknik Negeri Jakarta
<p>
  <img src = 

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
