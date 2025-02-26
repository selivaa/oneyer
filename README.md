<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Anniversary 1 Tahun Jadian</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0; 
      padding: 0;
      background-color: black;
      color: white;
      text-align: center;
    }
    /* Halaman utama disembunyikan di awal */
    #mainContent.hidden {
      display: none;
    }
    /* Pop-up umum */
    .popup {
      display: none; /* Awalnya disembunyikan */
      position: fixed;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      background-color: white;
      color: black;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.5);
      z-index: 1000;
      max-width: 300px;
    }
    /* Tombol di dalam pop-up */
    .popup button {
      margin-top: 20px;
      padding: 10px 20px;
      font-size: 16px;
      background-color: #ff6f61;
      border: none;
      color: white;
      cursor: pointer;
    }
    /* Galeri foto */
    .gallery {
      margin-top: 20px;
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    .gallery img {
      margin: 10px;
      border-radius: 8px;
      width: 200px;
      height: 150px;
      object-fit: cover;
    }
    /* Letak iframe lagu */
    .audio-wrapper {
      margin-top: 20px;
    }
  </style>
</head>
<body>

  <!-- Audio baru dengan link dari Google Drive -->
  <audio src="Lagu.mp3" id="linkmp3" class="sembunyi" loop></audio>

  <!-- POP-UP 1 -->
  <div id="popup1" class="popup">
    <h2>Jalann jalann kee kotaa Pemalangg</h2>
    <p>Happy anniversary sayangg 💖</p>
    <button onclick="nextPopup(1)">Lanjut</button>
  </div>

  <!-- POP-UP 2 -->
  <div id="popup2" class="popup">
    <h2>Ikann nilaa ikann laut</h2>
    <p>Sudaa ayoo kitaa lanjutt 💕</p>
    <button onclick="nextPopup(2)">Lanjut</button>
  </div>

  <!-- POP-UP 3 -->
  <div id="popup3" class="popup">
    <h2>Uburr uburr ikann lelee</h2>
    <p>Udahh satuu tahunn leeee 🎉</p>
    <button onclick="nextPopup(3)">Lanjut</button>
  </div>

  <!-- POP-UP 4 -->
  <div id="popup4" class="popup">
    <h2>Halo Seng!!</h2>
    <p>Penasarann kann apaa isinyaa??</p>
    <button onclick="nextPopup(4)">Lanjut</button>
  </div>

  <!-- POP-UP 5 -->
  <div id="popup5" class="popup">
    <h2>Penasaran kaannn!</h2>
    <button onclick="startClickPopups()">Klik dongg!!</button>
  </div>

  <!-- POP-UP UNTUK KLIK ULANG (harus diklik 7 kali secara manual) -->
  <div id="clickPopup" class="popup">
    <h2>KLIKK DISINII</h2>
    <button onclick="handleClick()">KLIK</button>
  </div>

  <!-- POP-UP TERAKHIR -->
  <div id="finalPopup" class="popup">
    <h2>HAHAHAHA capee yaaaaaa klikk teruss eheheheh<br>yasudaa yangg kalii inii seriuss</h2>
    <button onclick="showMainPage()">DISINII 💗</button>
  </div>

  <!-- HALAMAN UTAMA -->
  <div id="mainContent" class="hidden">
    <h1>Happy 1st Anniversary! 💖</h1>
    <p>
      Terima kasih sayangg sudah bersamakuu selama satu tahun! Aku bersyukur bisa menjalani setiap hari bersamamu.  
      Kamu adalah cahaya dalam hidupku, dan aku ingin terus bersamamu selamanya. Kita telah melewati suka dan duka bersama.  
      Setiap tawa, tangisan, dan momen yang kita jalani semakin menguatkan cinta kita. Aku mencintaimu lebih dari kata-kata yang bisa menggambarkan.  
      Setiap detik bersamamu adalah anugerah. Hari ini adalah bukti bahwa cinta kita kuat dan akan terus tumbuh.
    </p>

    <h2>Galeri Foto Kita</h2>
    <div class="gallery">
      <img src="pst.jpg" alt="1 YEAR">
      <p>1. Chat kalo kita resmi jadian.<br></p>
      <img src="1.jpg" alt="Kenangan 1">
      <p>2. Pertama kali kita foto bareng cieeee.<br></p>
      <img src="2.jpg" alt="Kenangan 2">
      <p>3. Kita foto di bo waktu itu pake love" lagii hahahah.<br></p>
      <img src="3.jpg" alt="Kenangan 3">
      <p>4. Nahh ini foto tangan kita yang mungil hahahah.<br></p>
      <img src="4.jpg" alt="Kenangan 4">
      <p>5. Kita fotbar lagi tapi dikaca tetangga warung sama hujan"ann hahahaha.<br></p>
      <img src="5.jpg" alt="Kenangan 5">
      <p>6. Inii pass latihan upacara kita satu jadwal buat tugas ehehhe.<br></p>
      <img src="6.jpg" alt="Kenangan 6">
      <p>7. Nahh itu foto kita terahkir di kelas 11 sebelum kita liburan 💗.<br></p>
    </div>

    <div class="audio-wrapper">
      <iframe width="560" height="315" 
              src="" 
              frameborder="0" 
              allow="autoplay; encrypted-media" 
              allowfullscreen>
      </iframe>
    </div>
  </div>

  <script>
    let clickCount = 0;

    window.onload = function() {
      document.getElementById('mainContent').classList.add('hidden');
      document.getElementById('popup1').style.display = 'block';
    };

    function nextPopup(currentNum) {
      document.getElementById('popup' + currentNum).style.display = 'none';
      
      // Mulai audio jika belum berjalan
      let audio = document.getElementById('linkmp3');
      if (audio && audio.paused) {
        audio.play().catch(function(error) {
          console.log("Audio tidak bisa diputar otomatis: ", error);
        });
      }
      
      const nextNum = currentNum + 1;
      const nextEl = document.getElementById('popup' + nextNum);
      if (nextEl) {
        nextEl.style.display = 'block';
      }
    }

    function startClickPopups() {
      document.getElementById('popup5').style.display = 'none';
      clickCount = 0;
      document.getElementById('clickPopup').style.display = 'block';
    }

    function handleClick() {
      clickCount++;
      if (clickCount < 7) {
        // Tetap biarkan pop-up "KLIKK" muncul; pengguna harus klik lagi
      } else {
        document.getElementById('clickPopup').style.display = 'none';
        document.getElementById('finalPopup').style.display = 'block';
      }
    }

    function showMainPage() {
      document.getElementById('finalPopup').style.display = 'none';
      document.getElementById('mainContent').classList.remove('hidden');
    }
  </script>

</body>
</html>
