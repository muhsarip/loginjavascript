## Belajar Membuat Login dengan Javascript

Belajar bikin website, ngga harus pake PHP melulu. ada yang namanye Javascript. Nah ini nih yang lagi booming

Yang dibutuhin :
1. editor : sublime, notepad++ atau vscode
2. kopi


### STEP 1 : Karena kita mau tampilan login yang kece, kita pake bootstrap. Buat file index.html , paste kode ini :

```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Bootstrap Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.0/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
</head>
<body>

<div class="container-fluid">
  <h1>My First Bootstrap Page</h1>
  <p>This is some text.</p> 
</div>

</body>
</html>
```
### STEP 2 : Buat form input usernamae dan password

lagi-lagi , kita pake element boostrap, seperti ini
```
<form id="form-login">
  <div class="form-group">
    <label for="email">Email address:</label>
    <input type="email" class="form-control" id="email">
  </div>
  <div class="form-group">
    <label for="pwd">Password:</label>
    <input type="password" class="form-control" id="pwd">
  </div>
  <div class="checkbox">
    <label><input type="checkbox"> Remember me</label>
  </div>
  <button type="submit" class="btn btn-default">LOGIN</button>
</form>
```

copy koding diatas, paste kan di sini

```
<div class="container-fluid">
  paste disini
</div>
```

terus jadi begini lengkapnya :
```
<!DOCTYPE html>
<html lang="en">
<head>
  <title>Bootstrap Example</title>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.0/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
</head>
<body>

<div class="container-fluid">
  <form id="form-login">
    <div class="form-group">
      <label for="email">Email address:</label>
      <input type="email" class="form-control" id="email">
    </div>
    <div class="form-group">
      <label for="pwd">Password:</label>
      <input type="password" class="form-control" id="pwd">
    </div>
    <div class="checkbox">
      <label><input type="checkbox"> Remember me</label>
    </div>
    <button type="submit" class="btn btn-default">LOGIN</button>
  </form>
</div>

</body>
</html>
```

nah , sekarang halaman login form nya sudah jadi 

### STEP 3 : Membuat logika login dengan javascriptnya

Sebelum lebih jauh, mari pahami penggunaan javascipt,  javascript selalu berada dalam tag buka dan tutup sepeteri di bawah ini :
```
<script type="text/javscript">
  .... kode javascript
</script>
```
jadi, mari kita mulai tulis javascript di file index.html yang udah dibuat.

Perhatikan ada tag ```</body>```
pasteini 
```
<script type="text/javscript">
  .... kode javascript
</script>
```
sebelum ```</body>```

jadi beigni : 

```
  <script type="text/javscript">
    .... kode javascript
  </script>
</body
```

lanjut, kita tadi sudah buat form input login, terdapat dua input , ini input buat username/email :
```
	<div class="form-group">
      <label for="email">Email address:</label>
      <input type="email" class="form-control" id="email">
    </div>
```
 ini input buat password :
```
    <div class="form-group">
      <label for="pwd">Password:</label>
      <input type="password" class="form-control" id="pwd">
    </div>
```

dan ini adalah button submit nya : 

```
    <button type="submit" class="btn btn-default">LOGIN</button>
```


Jadi ada TIGA element, ada input email, input password dan button LOGIN

alur LOGIN nya adalah, ketika user mengklik button LOGIN, maka sistem akan mengecek VALUE INPUT EMAIL dan VALUE INPUT PASSWORD, apakah cocok dengan yang ada di sistem, ketika cocok, maka keluar alert dengan isi pesan :" LOGIN BERHASIL".

jika tidak, maka keluar alert dengan isi pesan "LOGIN GAGAL, CHECK EMAIL DAN PASSWORD ANDA"

mari kita buat event js ketika user mengklik button LOGIN (ingat sisipkan ini diantara  ```` <script type="text/javscript"></script> ```):
```
$('#form-login').on("submit",function(e){
	e.preventDefault();
})
```
di atas adalah event js yang akan berjalan, ketika form login di klik LOGIN, karena klik login sama saja dengan menjalankan event submit 
















