# GrassXD

Program yang berguna untuk membantu anda mencari point grass

# Daftar Isi

- [GrassXD](#grassxd)
- [Daftar Isi](#daftar-isi)
- [Pendaftaran](#pendaftaran)
- [Peringatan dan catatan](#peringatan-dan-catatan)
- [Tentang Proxy](#tentang-proxy)
- [Tentang config.json](#tentang-configjson)
- [Cara Menggunakan](#cara-menggunakan)
- [Kode Javascript untuk mendapatkan data](#kode-javascript-untuk-mendapatkan-data)
  - [Kode untuk mendapatkan userid](#kode-untuk-mendapatkan-userid)
  - [Kode untuk mendapatkan token](#kode-untuk-mendapatkan-token)
- [Error yang mungkin terjadi](#error-yang-mungkin-terjadi)
- [Forum Diskusi](#forum-diskusi)
- [Dukung](#dukung)
- [Terima kasih](#terima-kasih)

# Pendaftaran

Jika anda belum mendaftar grass, silahkan memakai url berikut : [Klik disini](https://app.getgrass.io/register/?referralCode=9hUjGgcGTPW5Aqn)

# Peringatan dan catatan

Semua hal/risiko ditanggung oleh pengguna !

Program ini hanya mendukung 1 akun saja.

# Tentang Proxy

Untuk proxy sekarang saya sedang melakukan percobaan dengan beberapa situs berikut

[Situs pertama](https://app.nstproxy.com/register?i=YhCRDQ), 

Untuk format yang digunakan mengikuti contoh format berikut

Contoh format

```
http://host:port
socks5://host:port
http://user:password@host:port
socks5://user:password@host:port
```

# Tentang config.json

Berikut penjelasan isi dari file config.json 

| key           | value                   | deskripsi                                                                                                                 |
| ------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| interval_ping | integer / angka positif | jumlah delay setiap ping ke server, satuan : detik <br> dari extensi sendiri memiliki jumlah delay 2 menit atau 120 detik |

# Cara Menggunakan

1. Pastikan komputer kalian sudah terinstall python dan git
   
2. Buka terminal di perangkat anda (CMD/Powershell/Terminal)

3. Klone repository ini. Anda bisa menggunakan perintah dibawah
   ```shell
   git clone https://github.com/akasakaid/grassxd.git
   ```

4. Masuk kedalam folder grassxd
   ```shell
   cd grassxd
   ```

5. Kemudian install library yang dibutuhkan.
   ```shell
   python -m pip install -r requirements.txt
   ```

6. Isi proxy kalian ke file proxies.txt sesuai contoh yang telah saya berikan [Tentang Proxy](#tentang-proxy). Jika kalian tidak mengisi file `proxies.txt` maka akan otomatis menggunakan ip publik kalian.

7. Jalankan file `setup.py` terlebih dahulu, kalian akan diberi inputan untuk memasukklan email dan password dari akun grass kalian untuk mendapatkan autentikasi (id dan token).
   
   ```shell
   python setup.py
   ```

   Jika kalian mengalami error / yang lain, silahkan ambil userid dan token akun kalian secara manual. Lihat [Kode Javascript untuk mendapatkan data](#kode-javascript-untuk-mendapatkan-data)

8. Jalankan file `main.py` 
   
   ```shell
   python main.py
   ```

# Kode Javascript untuk mendapatkan data

## Kode untuk mendapatkan userid

Pastikan kalian sudah masuk ke dalam website grass.

Kalian bisa menggunakan kode javascript dibawah dengan cara mempastenya di menu console di fitur dev tool / dev option di aplikasi browser yang kalian pakai.

Berikut kode javascript untuk mendapatkan userid

```javascript
copy(JSON.parse(localStorage.getItem("userId")))
```

Jika muncul peringatan "Warning: Don’t paste code into the DevTools Console that you don’t " saat mempaste kode javascript diatas ketik `allow pasting` kemudian enter terlebih dahulu

Kode diatas sudah otomatis membuat userid tercopy ke clipboard jadi kalian tinggal mempastenya ke file `userid.txt`

## Kode untuk mendapatkan token

Berikut kode javascript untuk mendapatkan token

```javascript
copy(JSON.parse(localStorage.getItem("accessToken")))
```

Jika muncul peringatan "Warning: Don’t paste code into the DevTools Console that you don’t " saat mempaste kode javascript diatas ketik `allow pasting` kemudian enter terlebih dahulu

Kode diatas sudah otomatis membuat token tercopy ke clipboard jadi kalian tinggal mempastenya ke file `token.txt`

# Error yang mungkin terjadi

Berikut beberapa error yang mungkin terjadi dan solusi 

---
Pesan error : Cannot write to closing transport

Kenapa bisa terjadi ? Pesan error itu tampil / keluar ketika program ingin mengirim data yang seharusnya dikirim tetapi koneksi ke server telah tertutup. Kemungkinan terutup oleh proxy yang anda pakai atau dari server telah menutup koneksi anda.

Solusi ? Coba di kurangi interval ping di dalam file `config.json`. Secara default adalah 120 (detik), coba di kurangi menjadi 60 (detik) atau lebih kecil lagi. Jika masih terjadi kemungkinan proxy yang anda gunakan jelek.

Apa yang terjadi jika tidak di hentikan atau tidak di perbaiki? Ini hanya spekulasi saya saja, yang terjadi mungkin point yang anda dapatkan sedikit.


# Forum Diskusi

Jika kalian memiliki pertanyaan silahkan bertanya di [disini](https://t.me/sdsproject_chat)

# Dukung

Jika kalian suka dengan project yang saya buat, kalian bisa membelikan saya kopi melalui website dibawah

- Indonesian [Trakteer.id](https://trakteer.id/fawwazthoerif/tip)
  
- Ton Adress : `UQBDK-6ed0f2kX63hX4LB1rsLcnhx--zthwT_6g25a0Qakvb`

# Terima kasih