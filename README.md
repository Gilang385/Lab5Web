# Lab5Web
# Membuat script untuk melakukan validasi pada isian form.
## Langkah-Langkah Membuat Form Validasi
1. Buat File HTML
Buat file HTML baru, misalnya `form_validation.html`. Buka file ini di editor teks seperti VSCode.

2. Struktur Dasar HTML
Buat struktur dasar HTML dengan `<!DOCTYPE html>`, `<html>`, `<head>`, dan` <body>`. Tambahkan judul pada elemen `<title>` di bagian `<head>`.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation</title>
</head>
<body>
````
Membuat Formulir Input
Di dalam elemen `<body>`, tambahkan form dengan beberapa elemen input (`name`, `email`, dan `password`). Setiap input diberi `name` dan `required` untuk menandakan bahwa mereka wajib diisi. Form juga diberi atribut `onsubmit="return validateForm()"`, yang menghubungkan form dengan fungsi JavaScript bernama validateForm.
```html
    <h2>Form Registrasi</h2>
    <form name="registrationForm" onsubmit="return validateForm()">
        Nama: <input type="text" name="name" required><br><br>
        Email: <input type="email" name="email" required><br><br>
        Password: <input type="password" name="password" required><br><br>
        <input type="submit" value="Submit">
    </form>
```
Penjelasan Kode:
- `name="registrationForm"`: Memberi nama pada form agar mudah diakses di JavaScript.
- `onsubmit="return validateForm()"`: Menjalankan fungsi `validateForm()` setiap kali form akan disubmit. Jika fungsi ini mengembalikan false, form tidak akan dikirim.
- `required`: Menandai bahwa input harus diisi sebelum bisa disubmit.

4. Menambahkan Script JavaScript untuk Validasi Form
Tambahkan skrip JavaScript di bagian bawah sebelum penutup tag `<body>` untuk memvalidasi input form.
```html
    <script>
        function validateForm() {
            // Mendapatkan nilai dari setiap input form
            let name = document.forms["registrationForm"]["name"].value;
            let email = document.forms["registrationForm"]["email"].value;
            let password = document.forms["registrationForm"]["password"].value;
            
            // Memvalidasi apakah kolom "Nama" kosong
            if (name === "") {
                alert("Nama harus diisi.");
                return false; // Menghentikan pengiriman form jika kosong
            }

            // Memvalidasi apakah kolom "Email" kosong
            if (email === "") {
                alert("Email harus diisi.");
                return false; // Menghentikan pengiriman form jika kosong
            }

            // Memvalidasi apakah kolom "Password" kosong
            if (password === "") {
                alert("Password harus diisi.");
                return false; // Menghentikan pengiriman form jika kosong
            }

            return true; // Jika semua validasi lolos, form dapat dikirim
        }
    </script>
</body>
</html>

```
Penjelasan Kode:

- `function validateForm()`: Fungsi yang akan dijalankan ketika form disubmit. Fungsi ini mengecek tiap input untuk memastikan tidak ada yang kosong.
- `let name = document.forms["registrationForm"]["name"].value;`: Mengambil nilai dari input `name` pada form `registrationForm`.
- `if (name === "")`: Mengecek apakah input `name` kosong. Jika kosong, fungsi menampilkan alert dan mengembalikan `false`, sehingga form tidak dikirim.
- `alert("Nama harus diisi.");`: Menampilkan pesan jika input name kosong.
- `return false;`: Mencegah pengiriman form saat ada kolom kosong.
- `return true;`: Mengizinkan pengiriman form jika semua input terisi.

Ringkasan
1. Membuat struktur HTML dan form.
2. Menghubungkan form dengan fungsi validasi JavaScript menggunakan onsubmit.
3. Memvalidasi input menggunakan JavaScript dan menampilkan pesan kesalahan jika ada kolom yang kosong.

Ketika form disubmit, JavaScript akan memeriksa tiap kolom input. Jika semua kolom terisi, form dikirim. Jika ada yang kosong, muncul alert yang memberi tahu pengguna untuk mengisi kolom tersebut.

FULL CODE
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Form Validation</title>
</head>
<body>
    <h2>Form Registrasi</h2>
    <form name="registrationForm" onsubmit="return validateForm()">
        Nama    : <input type="text" name="name" required><br><br>
        Email   : <input type="email" name="email" required><br><br>
        Password: <input type="password" name="password" required><br><br>
        <input type="submit" value="Submit">
    </form>

    <script>
        function validateForm() {
            let name = document.forms["registrationForm"]["name"].value;
            let email = document.forms["registrationForm"]["email"].value;
            let password = document.forms["registrationForm"]["password"].value;
            
            if (name === "") {
                alert("Nama harus diisi.");
                return false;
            }
            if (email === "") {
                alert("Email harus diisi.");
                return false;
            }
            if (password === "") {
                alert("Password harus diisi.");
                return false;
            }
            return true; // Jika semua validasi lolos
        }
    </script>
</body>
</html>
```

Hasil gambar
![image](https://github.com/user-attachments/assets/747e23f9-e929-414c-bf56-a4081b6b34db)
