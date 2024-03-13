Screenshot JMeter GUI sebelum profiling dan optimization
- /all-student
![image1.png](img_readme%2Fimage1.png)
- /all-student-name
![image2.png](img_readme%2Fimage2.png)
- /highest-gpa
![image3.png](img_readme%2Fimage3.png)

Screenshot JMeter CLI sebelum optimization
- /all-student
![image4.png](img_readme%2Fimage4.png)
- /all-student-name
![image5.png](img_readme%2Fimage5.png)
- /highest-gpa
![image6.png](img_readme%2Fimage6.png)

Screenshot JMeter CLI setelah optimization
- /all-student
![image7.png](img_readme%2Fimage7.png)
- /all-student-name
![image8.png](img_readme%2Fimage8.png)
- /highest-gpa
![image9.png](img_readme%2Fimage9.png)

### Kesimpulan
Modifikasi pada kode yang telah dilakukan pada metode getAllStudentsWithCourse, JoinStudentNames, dan findStudentWithHighestGPA telah memberikan peningkatan performance yang signifikan, hal tersebut dapat dilihat dari perbedaan latency dari setiap before dan after test plan yang memiliki peningkatan performance seperti get request pada /all-student dari -+85794 ms menjadi -+3467 ms, get request /all-student-name dari -+3624 ms menjadi -+212 ms, dan get request /highest-gpa dari -+34 ms menjadi -+10 ms pada sebagian besar thread.

# Refleksi

1. JMeter dengan Intellij Profiler memiliki kelebihan yang berbeda, JMeter bagus digunakan untuk melakukan performance testing sebuah aplikasi yang mampu menggunakan multiple threads, memberikan simulasi multiple user yang melakukan akses terhadap aplikasi untuk melakukan pengukuran metrik performa seperti response time, throughput, dan concurrency yang bagus digunakan untuk mendeteksi scalability dari sebuah aplikasi, sedangkan intellij profiler memberikan analisa insight yang mendalam terhadap kodingan aplikasi yang memudahkan para developer untuk menemukan memory leaks, algoritma yang tidak efisien, dan performance issue yang terjadi pada kodingan.
2. Proses profiling membantu mendeteksi bottleneck pada kodingan seperti method-method yang memakan waktu lama untuk dilakukan peninjauan ulang. Profiling membantu untuk memonitor penggunaan seperti CPU dan memori. Profiling juga membantu dalam melacak alokasi memori dan penggunaan memori pada waktu tertentu.
3. Ya, Intellij profiler sangat efektif dalam membantu menganalisa dan mengidentifikasi bottleneck yang ada di dalam kodingan saya, intellij profiler memberikan tampilan insight seperti flame graph, call tree, method list, timeline, dan events yang membantu dalam proses analisa dan identifikasi bottleneck dari sebuah kodingan.
4. Tantangan saat melakukan testing dan profiling adalah melakukan interpretasi dari data yang diberikan dari testing performance, hal ini akan semakin sulit jika kompleksitas dari aplikasi meningkat, hal yang dilakukan untuk menghadapi tantangan ini adalah menggunakan visualization tools untuk melihat data performance yang lebih detail dan jelas untuk memberikan interpretasi yang lebih baik terhadap performance kodingan.
5. Benefit yang bisa didapatkan dari menggunakan profiler dari Intellij adalah terintegrasinya profiler dengan fitur-fitur yang ada di intellij, seperti navigasi kode dan debugging. Hal ini mempermudah proses analisa dari kode saat menggunakan intellij.
6. Hal yang dapat dilakukan untuk mengatasi situasi tersebut adalah melakukan review ulang terhadap metodologi yang digunakan untuk melakukan profiling dengan intellij profiler dan performance testing dengan JMeter. Test scenario yang dilakukan harus dipastikan memiliki konfigurasi dan environment yang konsisten untuk mencegah hasil yang berbeda dari kedua metode tersebut.
7. Hal yang pertama saya lakukan adalah mencari hotspots, yaitu berupa critical section dari kode yang di mana jika dilakukan improvement akan berkontribusi signifikan terhadap overall performance dari aplikasi. Perubahan pada fungsionalitas aplikasi dapat dicegah dengan membuat automated tests yang memastikan kodingan tetap berjalan sesuai fungsi yang telah dibuat sebelumnya, apabila fungsionalitas telah berubah, tentunya hal itu akan terdeteksi dari gagalnya sebuah automated test seperti unit testing.