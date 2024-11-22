# books

A new Flutter project.

## Getting Started

Soal 1
![alt text](images/soal1.png)

Soal 2
![alt text](images/soal2.png)

Soal 3

result = value.body.toString().substring(0, 450);
Substring(start, end) mengambil karakter dari indeks start sampai end-1.
Menghasilkan teks mulai dari karakter pertama (indeks 0) hingga karakter ke-450 (indeks 449).

Method catchError digunakan untuk menangani error pada operasi asinkron (seperti Future).

![alt text](images/ScreenRecording2024-11-15030725-ezgif.com-video-to-gif-converter.gif)

Soal 4

Langkah 1 mendefinisikan tiga fungsi asinkron (async) yang masing-masing mengembalikan nilai integer setelah penundaan tiga detik.
Langkah 2 adalah fungsi Future asinkron yang mengumpulkan nilai dari tiga fungsi (returnOneAsync, returnTwoAsync, dan returnThreeAsync) secara berurutan, menambahkannya ke variabel total, dan akhirnya memperbarui nilai result di dalam metode setState
![alt text](images/ScreenRecording2024-11-15031856-ezgif.com-video-to-gif-converter.gif)

Soal 5

Langkah 2 menggunakan Completer untuk mengelola nilai yang akan diselesaikan di masa depan. Completer di sini berfungsi untuk memisahkan inisialisasi Future dari penyelesaiannya, memungkinkan fungsi lain untuk menyelesaikan Future pada waktu tertentu.
![alt text](images/20241114-2029-18.4682397-ezgif.com-video-to-gif-converter.gif)

Soal 6

Penambahan mekanisme untuk menangani error. Dengan adanya blok try-catch, jika terjadi error dalam calculate, maka completer akan menyelesaikan Future dengan error melalui completeError, bukan dengan nilai normal.
![alt text](images/20241114-2029-18.4682397-ezgif.com-video-to-gif-converter.gif)

Soal 7
![alt text](images/soal7.gif)

Soal 8
![alt text](images/soal8.gif)
FutureGroup digunakan untuk menambahkan Future secara dinamis satu per satu dan dapat ditutup dengan close(). Cocok jika jumlah atau daftar Future tidak diketahui di awal. Sedangkan future.wait digunakan untuk menjalankan banyak Future sekaligus dalam satu daftar yang sudah tetap. Sederhana dan lebih cocok jika semua Future sudah diketahui sebelumnya.

Soal 9
![alt text](images/soal9.gif)

Soal 10
![alt text](images/soal10.gif)
returnError() hanya menghasilkan Future yang gagal dengan melemparkan error tanpa menangani kesalahan.
handleError() memanggil returnError() dan menangani error menggunakan try-catch, lalu memperbarui UI dengan setState dan menjalankan tugas cleanup di blok finally.

Soal 11
![alt text](images/soal11.gif)

Soal 12
![alt text](images/soal11.gif)

browser
![alt text](<images/Screenshot 2024-11-22 070652.png>)
Browser bis mendapat koordinat GPS karena saya memberti izin lokasi pada browser dan laptop saya memiliki GPS

Soal 13
![alt text](images/soal13.gif)
Sebelumnya:
- UI mengandalkan pembaruan manual menggunakan setState untuk mengganti CircularProgressIndicator dengan lokasi ketika data tersedia. 
- Loading hanya muncul jika kode secara eksplisit diatur untuk memperbarui myPosition.

Sekarang:
- Menggunakan FutureBuilder, UI secara otomatis diperbarui ketika status Future (dalam hal ini, getPosition()) berubah.
- Tidak perlu menggunakan setState secara manual untuk mengatur nilai variabel atau memperbarui widget.
- Loading (CircularProgressIndicator) muncul secara otomatis ketika FutureBuilder mendeteksi bahwa data sedang diproses.

Soal 14
![alt text](images/soal14.gif)
Pada kode baru, jika terjadi error selama eksekusi Future (misalnya, jika layanan lokasi dimatikan atau izin lokasi ditolak), error akan terdeteksi melalui snapshot.hasError.
