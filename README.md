</body>
</html>
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aesthetic Photobooth</title>
    <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* CSS yang sama seperti sebelumnya, dengan penambahan untuk elemen baru */
        body {
            font-family: 'Roboto', sans-serif;
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
            font-family: 'Pacifico', cursive;
            font-size: 2.5em;
            margin: 0;
            color: #FFF;
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
            background-color: #FFF;
            border-radius: 10px;
            margin: 20px auto;
            max-width: 800px;
        }
        
        .button {
            background-color: #FFB6C1;
            color: #FFF;
            padding: 15px 30px;
            border: none;
            border-radius: 5px;
            font-size: 1.2em;
            cursor: pointer;
            font-family: 'Pacifico', cursive;
            transition: background-color 0.3s;
        }
        
        .button:hover {
            background-color: #AEC6CF;
        }
        
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            padding: 20px;
        }
        
        .gallery img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        
        .gallery img:hover {
            transform: scale(1.05);
        }
        
        #camera-section {
            margin: 20px 0;
        }
        
        #video {
            width: 80%;
            max-width: 600px;
            border: 2px solid #FFB6C1;
            border-radius: 10px;
        }
        
        #canvas {
            display: none; /* Awalnya tersembunyi */
            width: 80%;
            max-width: 600px;
            border: 2px solid #FFB6C1;
            border-radius: 10px;
            margin-top: 20px;
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
        <p>"Abadikan momen bahagia mu dengan gaya"</p>
        <nav>
            <a href="#home">Beranda</a>
            <a href="#gallery">Galeri</a>
            <a href="#camera">Ambil Foto</a>
        </nav>
    </header>
    
    <section id="home" class="main-content">
        <h2>Selamat Datang di Layanan Photobooth Kami!</h2>
        <p>Kami menyediakan layanan photobooth yang menyenangkan. Coba ambil foto langsung di sini!</p>
        <a href="#camera">
            <button class="button">Mulai Ambil Foto</button>
        </a>
    </section>
    
    <section id="camera" class="main-content">
        <h2>Ambil Foto atau Upload</h2>
        <p>Izinkan akses kamera untuk mengambil foto. Anda juga bisa upload dari galeri dan pilih frame.</p>
        
        <div id="camera-section">
            <video id="video" autoplay></video>
            <canvas id="canvas" width="640" height="480"></canvas> <!-- Canvas untuk editing -->
            <button id="startCamera" class="button">Hidupkan Kamera</button>
            <button id="capture" class="button" disabled>Ambil Foto</button>
            <input type="file" id="upload" accept="image/*">
            <select id="frameSelect" class="button">
                <option value="">Pilih Frame</option>
                <option value="frame1.png">Frame 1 (Bingkai Bunga)</option>
                <option value="frame2.png">Frame 2 (Bingkai Hati)</option>
                <option value="frame3.png">Frame 3 (Bingkai Sederhana)</option>
            </select>
            <button id="applyFrame" class="button" disabled>Terapkan Frame</button>
            <button id="download" class="button" disabled>Download Foto</button>
        </div>
    </section>
    
    <section id="gallery" class="main-content">
        <h2>Galeri Foto Kami</h2>
        <div class="gallery">
            <img src="placeholder1.jpg" alt="Foto Photobooth 1">
            <img src="placeholder2.jpg" alt="Foto Photobooth 2">
            <img src="placeholder3.jpg" alt="Foto Photobooth 3">
            <img src="placeholder4.jpg" alt="Foto Photobooth 4">
        </div>
    </section>
    
    <footer>
        <p>&copy; 2023 Aesthetic Photobooth. Semua hak cipta dilindungi.</p>
    </footer>
    
    <script>
        const video = document.getElementById('video');
        const canvas = document.getElementById('canvas');
        const context = canvas.getContext('2d');
        const startCameraBtn = document.getElementById('startCamera');
        const captureBtn = document.getElementById('capture');
        const uploadInput = document.getElementById('upload');
        const frameSelect = document.getElementById('frameSelect');
        const applyFrameBtn = document.getElementById('applyFrame');
        const downloadBtn = document.getElementById('download');
        
        // Hidupkan kamera
        startCameraBtn.addEventListener('click', async () => {
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ video: true });
                video.srcObject = stream;
                captureBtn.disabled = false;
            } catch (err) {
                alert('Akses kamera ditolak. Pastikan izin diberikan.');
            }
        });
        
        // Ambil foto dari kamera
        captureBtn.addEventListener('click', () => {
            context.drawImage(video, 0, 0, canvas.width, canvas.height);
            video.style.display = 'none'; // Sembunyikan video setelah capture
            canvas.style.display = 'block'; // Tampilkan canvas
            applyFrameBtn.disabled = false;
            downloadBtn.disabled = false;
        });
        
        // Upload foto
        uploadInput.addEventListener('change', (event) => {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = (e) => {
                    const img = new Image();
                    img.onload = () => {
                        context.drawImage(img, 0, 0, canvas.width, canvas.height);
                        canvas.style.display = 'block';
                        applyFrameBtn.disabled = false;
                        downloadBtn.disabled = false;
                    };
                    img.src = e.target.result;
                };
                reader.readAsDataURL(file);
            }
        });
        
        // Terapkan frame
        applyFrameBtn.addEventListener('click', async () => {
            const frameSrc = frameSelect.value; // Ambil frame yang dipilih
            if (frameSrc) {
                const frameImg = new Image();
                frameImg.onload = () => {
                    context.drawImage(frameImg, 0, 0, canvas.width, canvas.height); // Overlay frame
                };
                frameImg.src = frameSrc; // Pastikan frame gambar ada di folder yang sama
                downloadBtn.disabled = false;
            } else {
                alert('Pilih frame terlebih dahulu!');
            }
        });
        
        // Download foto
        downloadBtn.addEventListener('click', () => {
            const link = document.createElement('a');
            link.download = 'foto-photobooth.png';
            link.href = canvas.toDataURL();
            link.click();
        });
    </script>
</body>
</html>
