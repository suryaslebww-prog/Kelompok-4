<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pesan Rahasia</title>

  <style>
    body{
      margin:0;
      padding:0;
      height:100vh;
      display:flex;
      justify-content:center;
      align-items:center;
      background:linear-gradient(135deg,#6a11cb,#2575fc);
      font-family:Arial, sans-serif;
    }

    .container{
      background:white;
      width:90%;
      max-width:500px;
      padding:35px;
      border-radius:20px;
      text-align:center;
      box-shadow:0 10px 25px rgba(0,0,0,0.2);
    }

    h1{
      color:#5a189a;
      margin-bottom:10px;
    }

    p{
      color:#555;
      margin-bottom:20px;
    }

    textarea, input{
      width:100%;
      padding:14px;
      margin-top:10px;
      border:2px solid #ccc;
      border-radius:12px;
      font-size:16px;
      outline:none;
      box-sizing:border-box;
    }

    textarea:focus, input:focus{
      border-color:#6a11cb;
    }

    .hasil{
      margin-top:25px;
      background:#f3f0ff;
      padding:20px;
      border-radius:15px;
      min-height:60px;
      font-size:22px;
      word-wrap:break-word;
      color:#5a189a;
      font-weight:bold;
    }

    button{
      margin-top:15px;
      padding:12px 25px;
      border:none;
      border-radius:12px;
      background:#6a11cb;
      color:white;
      font-size:16px;
      cursor:pointer;
      transition:0.3s;
    }

    button:hover{
      background:#4c0f94;
      transform:scale(1.05);
    }

    .emoji{
      font-size:55px;
      margin-bottom:10px;
    }

  </style>
</head>

<body>

  <div class="container">

    <div class="emoji">🔐💌</div>

    <h1>Pesan Rahasia</h1>

    <p>
      Tulis pesan rahasia untuk temanmu!
    </p>

    <!-- Input Pesan -->
    <textarea id="pesan" rows="4" placeholder="Tulis pesan rahasia di sini..."></textarea>

    <!-- Hasil Kode -->
    <div class="hasil" id="hasil">
      🔒 Pesan terenkripsi akan muncul di sini
    </div>

    <!-- Kata Kunci -->
    <input type="password" id="kunci" placeholder="Masukkan kata kunci">

    <button onclick="bukaPesan()">Buka Pesan</button>

  </div>

  <script>

    const pesanInput = document.getElementById("pesan");
    const hasil = document.getElementById("hasil");

    // Kata kunci rahasia
    const passwordBenar = "rahasia123";

    // Mengubah pesan jadi emoji/kode
    pesanInput.addEventListener("input", function(){

      let teks = pesanInput.value;

      let kode = "";

      for(let i = 0; i < teks.length; i++){
        kode += "🔒";
      }

      hasil.innerHTML = kode || "🔒 Pesan terenkripsi akan muncul di sini";
    });

    // Membuka pesan asli
    function bukaPesan(){

      const password = document.getElementById("kunci").value;

      if(password === passwordBenar){

        hasil.innerHTML = "💌 " + pesanInput.value;

      }else{

        alert("❌ Kata kunci salah!");

      }

    }

  </script>

</body>
</html>
