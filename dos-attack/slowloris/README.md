# slowloris.py - Slowloris sederhana dalam Python

## Apa itu Slowloris?

Slowloris pada dasarnya adalah serangan HTTP Denial of Service yang mempengaruhi server berulir. Cara kerjanya seperti ini:

Kami mulai membuat banyak permintaan HTTP.

Kami mengirim header secara berkala (setiap ~15 detik) untuk menjaga koneksi tetap terbuka.

Kami tidak pernah menutup koneksi kecuali server melakukannya. Jika server menutup koneksi, kami membuat koneksi baru dan terus melakukan hal yang sama.

Ini menghabiskan pool thread server dan server tidak dapat membalas permintaan lainnya.

## Sitasi

Jika kamu menemukan karya ini berguna, harap sitasi sebagai

```bibtex
@article{gkbrkslowloris,
  title = "Slowloris",
  author = "Gokberk Yaltirakli",
  journal = "github.com",
  year = "2015",
  url = "https://github.com/gkbrk/slowloris"
}
```

## Cara menginstal dan menjalankan?

Kamu bisa mengkloning repo git atau menginstal menggunakan pip. Begini cara menjalankannya.

```
sudo pip3 install slowloris
```

```
slowloris example.com
```

Hanya itu yang diperlukan untuk menginstal dan menjalankan slowloris.py.

Jika kamu ingin mengkloning menggunakan git alih-alih pip, begini caranya.

```
git clone https://github.com/gkbrk/slowloris.git`
```

```
cd slowloris
```

```
python3 slowloris.py example.com
```

### Dukungan proxy SOCKS5

Namun, jika kamu berencana menggunakan opsi `-x` untuk menggunakan proxy SOCKS5 untuk terhubung daripada koneksi langsung melalui alamat IP-mu, kamu perlu menginstal library `PySocks` (atau implementasi lain dari library `socks`) juga. [`PySocks`](https://github.com/Anorov/PySocks) adalah fork dari [`SocksiPy`](http://socksipy.sourceforge.net/) oleh pengguna GitHub @Anorov dan dapat dengan mudah diinstal dengan menambahkan `PySocks` ke perintah `pip` di atas atau menjalankannya lagi seperti ini:

```
sudo pip3 install PySocks
```

Kamu kemudian bisa menggunakan opsi `-x` untuk mengaktifkan dukungan SOCKS5 dan opsi `--proxy-host` dan `--proxy-port` untuk menentukan host dan port proxy SOCKS5, jika berbeda dari standar `127.0.0.1:8080`.

## Opsi konfigurasi

Mungkin untuk memodifikasi perilaku slowloris dengan argumen baris perintah. Untuk mendapatkan dokumen bantuan terbaru, cukup jalankan
`slowloris -h`.

- -p, --port
- - Port server web, biasanya 80
- -s, --sockets
- - Jumlah soket yang digunakan dalam pengujian
- -v, --verbose
- - Meningkatkan logging (output di terminal)
- -ua, --randuseragents
- - Mengacak user-agents dengan setiap permintaan
- -x, --useproxy
- - Gunakan proxy SOCKS5 untuk terhubung
- --https
- - Gunakan HTTPS untuk permintaan
- --sleeptime
- - Waktu tidur antara setiap header yang dikirim

## Lisensi

Kode ini dilisensikan di bawah Lisensi MIT.
