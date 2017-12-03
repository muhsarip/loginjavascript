## Belajar Membuat Login dengan Javascript

Belajar bikin website, ngga harus pake PHP melulu. ada yang namanye Javascript. Nah ini nih yang lagi booming
<div style="text-align:center;width:100%">
<img src="https://im4.ezgif.com/tmp/ezgif-4-e0d07617d7.gif" style="width:100%;height:auto"/>
	</div> <br>
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
<h1>Login Form</h1>
<form id="form-login">
  <div class="form-group">
    <label for="email">Email address:</label>
    <input type="email" class="form-control" id="email">
  </div>
  <div class="form-group">
    <label for="pwd">Password:</label>
    <input type="password" class="form-control" id="password">
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
  <h1>Login Form</h1>
  <form id="form-login">
    <div class="form-group">
      <label for="email">Email address:</label>
      <input type="email" class="form-control" id="email">
    </div>
    <div class="form-group">
      <label for="pwd">Password:</label>
      <input type="password" class="form-control" id="password">
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
<script type="text/javascript">
  .... kode javascript
</script>
```
jadi, mari kita mulai tulis javascript di file index.html yang udah dibuat.

Perhatikan ada tag ```</body>```
pasteini 
```
<script type="text/javascript">
  .... kode javascript
</script>
```
sebelum ```</body>```

jadi beigni : 

```
  <script type="text/javascript">
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
      <input type="password" class="form-control" id="password">
    </div>
```

dan ini adalah button submit nya : 

```
    <button type="submit" class="btn btn-default">LOGIN</button>
```


Jadi ada TIGA element, ada input email, input password dan button LOGIN

alur LOGIN nya adalah, ketika user mengklik button LOGIN, maka sistem akan mengecek VALUE INPUT EMAIL dan VALUE INPUT PASSWORD, apakah cocok dengan yang ada di sistem, ketika cocok, maka keluar alert dengan isi pesan :" LOGIN BERHASIL".

jika tidak, maka keluar alert dengan isi pesan "LOGIN GAGAL, CHECK EMAIL DAN PASSWORD ANDA"

mari kita buat event js ketika user mengklik button LOGIN (ingat sisipkan ini diantara  ```` <script type="text/javascript"></script> ```):
```
$('#form-login').on("submit",function(e){
	e.preventDefault();
})
```
di atas adalah event js yang akan berjalan, ketika form login di klik LOGIN, karena klik login sama saja dengan menjalankan event submit 

lanjut... mari kita definisiin varibale input email dan variable input password , seperti ini : 

```
$('#form-login').on("submit",function(e){
	e.preventDefault();
    var email = $('#email').val();
    var password = $('#password').val();
})
```

lalu buat lah kondisional dengan IF , kita buat dlu variable email dan password admin :
```
$('#form-login').on("submit",function(e){
	e.preventDefault();
    var email = $('#email').val();
    var password = $('#password').val();
    
    var email_admin ="admin@admin.com";
    var password_admin = "123456";
})
```
mudah bukan bkin variablenya? jadi email admin adalah admin@admin.com dan passwordnya adalah 123456

mari kita buat konidisonal IF nya :
```
$('#form-login').on("submit",function(e){
	e.preventDefault();
    var email = $('#email').val();
    var password = $('#password').val();
    
    var email_admin ="admin@admin.com";
    var password_admin = "123456";
    
    if(email == email_admin && password == password_admin){
    	alert("LOGIN BERHASIL");
    }else{
    	alert("LOGIN GAGAL, CHECK EMAIL DAN PASSWORD ANDA");
    }
    
})
```
Nah, pada IF ini, jika  email yg diketik user sama dengan isi varibale email_admin, dan password yang diketik user sama dengan isi variabel password_admin , maka login BERHASIL, jika tidak sama salah satunya atau dua-duanya, maka login GAGAL.

sampai disini sudah selesai , jadi ini kode lengkapnya :
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
  <h1>Login Form</h1>
  <form id="form-login">
    <div class="form-group">
      <label for="email">Email address:</label>
      <input type="email" class="form-control" id="email">
    </div>
    <div class="form-group">
      <label for="pwd">Password:</label>
      <input type="password" class="form-control" id="password">
    </div>
    <div class="checkbox">
      <label><input type="checkbox"> Remember me</label>
    </div>
    <button type="submit" class="btn btn-default">LOGIN</button>
  </form>
</div>
<script type="text/javascript">
$('#form-login').on("submit",function(e){
	e.preventDefault();
    var email = $('#email').val();
    var password = $('#password').val();
    
    var email_admin ="admin@admin.com";
    var password_admin = "123456";
    
    if(email == email_admin && password == password_admin){
    	alert("LOGIN BERHASIL");
    }else{
    	alert("LOGIN GAGAL, CHECK EMAIL DAN PASSWORD ANDA");
    }
    
})
</script>
</body>
</html>
```
