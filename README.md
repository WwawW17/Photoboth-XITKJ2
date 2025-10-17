# Photoboth-XITKJ2-KelompokBiru


<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aesthetic Photobooth</title>
    <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Roboto:wght@400;700&display=swap" rel="stylesheet"> <!-- Font lucu dan mudah dibaca -->
    <style>
        /* Tema warna pastel: Pink lembut (#FFB6C1), Biru muda (#AEC6CF), Putih (#FFF) */
        body {
            font-family: 'Roboto', sans-serif; /* Font mudah dibaca */
            background-color: #AEC6CF; /* Biru muda pastel */
            color: #333;
            margin: 0;
            padding: 0;
            text-align: center;
        }
        
        header {
            background-color: #FFB6C1; /* Pink lembut */
            padding: 20px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        header h1 {
            font-family: 'Pacifico', cursive; /* Font lucu untuk judul */
            font-size: 2.5em;
            margin: 0;
            color: #FFF; /* Putih untuk kontras */
        }
        
        header p {
            font-size: 1.2em;
            color: #FFF;
        }
        
        nav a {
            color: #FFF;
            text-decoration: none;
            margin: 0 15px;
            font-weight: bold;
        }
        
        nav a:hover {
            text-decoration: underline;
        }
        
        .main-content {
            padding: 50px 20px;
            background-color: #FFF; /* Latar putih untuk konten utama */
            border-radius: 10px;
            margin: 20px auto;
            max-width: 800px;
        }
        
        .main-content h2 {
            font-family: 'Pacifico', cursive;
            color: #FFB6C1; /* Pink lembut untuk aksen */
        }
        
        .button {
            background-color: #FFB6C1; /* Pink lembut */
            color: #FFF;
            padding: 15px 30px;
            border: none;
            border-radius: 5px;
            font-size: 1.2em;
            cursor: pointer;
            font-family: 'Pacifico', cursive; /* Font lucu */
            transition: background-color 0.3s; /* Efek hover sederhana */
        }
        
        .button:hover {
            background-color: #AEC6CF; /* Ganti ke biru muda saat hover */
        }
        
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); /* Grid responsif */
            gap: 15px;
            padding: 20px;
        }
        
        .gallery img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Efek bayangan untuk visual ceria */
            transition: transform 0.3s; /* Efek zoom saat hover */
        }
        
        .gallery img:hover {
            transform: scale(1.05); /* Zoom sedikit saat hover */
        }
        
        footer {
            background-color: #FFB6C1;
            padding: 10px;
            color: #FFF;
            font-size: 0.9em;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Aesthetic Photobooth</h1>
        <p>"Abadikan momen bahagia mu dengan gaya"</p> <!-- Slogan -->
        <nav>
            <a href="#home">Beranda</a>
            <a href="#gallery">Galeri</a>
        </nav>
    </header>
    
    <section id="home" class="main-content">
        <h2>Selamat Datang di Layanan Photobooth Kami!</h2>
        <p>Kami menyediakan layanan photobooth yang menyenangkan untuk acara-acara spesial seperti pernikahan, ulang tahun, atau gathering. Dengan gaya aesthetic dan tema ceria, kami membantu Anda mengabadikan momen bahagia secara unik dan instagramable.</p>
        <p>Manfaatkan website ini untuk melihat portofolio kami dan promosikan layanan kami tanpa batas waktu!</p>
        <a href="#gallery">
            <button class="button">Mulai</button> <!-- Tombol ajakan -->
        </a>
    </section>
    
    <section id="gallery" class="main-content">
        <h2>Galeri Foto Kami</h2>
        <p>Ini adalah kumpulan foto hasil photobooth kami. Klik atau zoom untuk melihat detail!</p>
        <div class="gallery">
            <!-- Ganti src gambar dengan foto asli Anda. Pastikan gambar ada di folder yang sama -->
            <img src="placeholder1.jpg" alt="Foto Photobooth 1">
            <img src="placeholder2.jpg" alt="Foto Photobooth 2">
            <img src="placeholder3.jpg" alt="Foto Photobooth 3">
            <img src="placeholder4.jpg" alt="Foto Photobooth 4">
            <!-- Tambahkan lebih banyak gambar jika diperlukan, misal: <img src="foto5.jpg" alt="Deskripsi"> -->
        </div>
    </section>
    
    <footer>
        <p>&copy; 2023 Aesthetic Photobooth. Semua hak cipta dilindungi.</p>
    </footer>
    
    <script>
        // JavaScript sederhana untuk efek alert saat tombol diklik (opsional)
        document.querySelector('.button').addEventListener('click', function() {
            alert('Anda akan melihat galeri kami!'); // Bisa dihapus jika tidak diperlukan
        });
    </script>
</body>
</html>
