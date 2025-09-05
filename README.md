<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ArmadaKita - Sewa Kendaraan</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
    <!-- CSS (Cascading Style Sheets) untuk Styling -->
    <style>
        /* General Styling */
        :root {
            --primary-color: #007bff;
            --secondary-color: #1a3a5a;
            --background-color: #f4f7f6;
            --card-background: #ffffff;
            --text-color: #333;
            --light-text-color: #666;
            --success-color: #28a745;
        }
        body {
            font-family: 'Inter', sans-serif;
            margin: 0;
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        .hidden {
            display: none !important;
        }
        .button {
            display: inline-block;
            background-color: var(--primary-color);
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            text-decoration: none;
            font-size: 16px;
            font-weight: 600;
            transition: background-color 0.3s ease, transform 0.2s ease;
        }
        .button:hover {
            background-color: #0056b3;
            transform: translateY(-2px);
        }
        h1, h2, h3 {
            color: var(--secondary-color);
        }
        /* Header */
        header {
            background-color: var(--card-background);
            padding: 15px 30px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
        }
        .logo {
            font-size: 24px;
            font-weight: 700;
            color: var(--secondary-color);
            cursor: pointer;
        }
        /* Page Sections */
        .page {
            padding: 20px 0;
        }
        /* --- Homepage --- */
        .hero {
            text-align: center;
            padding: 60px 20px;
            background: linear-gradient(rgba(233, 242, 255, 0.95), rgba(209, 227, 255, 0.95)), url('https://www.toptal.com/designers/subtlepatterns/uploads/transport.png');
            border-radius: 12px;
        }
        .hero h1 {
            font-size: 2.5rem;
        }
        .category-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin: 40px 0;
        }
        .category-card {
            background-color: var(--card-background);
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
            width: 160px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: transform 0.2s, box-shadow 0.2s;
            border: 1px solid #eee;
        }
        .category-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 16px rgba(0,0,0,0.12);
        }
        .category-card .icon {
            font-size: 48px;
            margin-bottom: 15px;
        }
        .vehicle-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }
        .vehicle-card {
            background-color: var(--card-background);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0,0,0,0.08);
            display: flex;
            flex-direction: column;
            transition: transform 0.3s;
        }
        .vehicle-card:hover {
             transform: translateY(-5px);
        }
        .vehicle-card img {
            width: 100%;
            height: 220px;
            object-fit: cover;
        }
        .vehicle-card-content {
            padding: 20px;
            flex-grow: 1;
        }
        .vehicle-card-content .category {
            font-size: 14px;
            color: var(--light-text-color);
        }
        .vehicle-card-content h3 {
            margin: 5px 0 10px 0;
        }
        .vehicle-card-content .price {
            font-size: 1.2rem;
            font-weight: 600;
            color: var(--primary-color);
            margin-bottom: 15px;
        }
        .vehicle-card-content .button {
            width: 100%;
        }
        /* --- Detail Page --- */
        .back-button {
            margin-bottom: 20px;
            background-color: #6c757d;
        }
        .back-button:hover {
             background-color: #5a6268;
        }
        .detail-layout {
            display: grid;
            grid-template-columns: 1fr;
            gap: 40px;
            background-color: var(--card-background);
            padding: 30px;
            border-radius: 12px;
        }
        @media (min-width: 768px) {
            .detail-layout {
                grid-template-columns: 1fr 1fr;
            }
        }
        #detail-image {
            width: 100%;
            border-radius: 8px;
            max-height: 500px;
            object-fit: cover;
        }
        #detail-specs {
            list-style: none;
            padding: 0;
        }
        #detail-specs li {
            display: flex;
            justify-content: space-between;
            padding: 10px 5px;
            border-bottom: 1px solid #eee;
        }
        #detail-specs li:last-child {
            border-bottom: none;
        }
        #detail-specs li span:first-child {
            font-weight: 600;
            color: var(--light-text-color);
        }
        #sewa-button {
            width: 100%;
            padding: 15px;
            font-size: 18px;
            margin-top: 20px;
            background-color: var(--success-color);
        }
        #sewa-button:hover {
            background-color: #218838;
        }
        /* --- Booking Page --- */
        .booking-form {
            background-color: var(--card-background);
            padding: 30px;
            border-radius: 12px;
            max-width: 600px;
            margin: 20px auto;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        .form-group {
            margin-bottom: 20px;
        }
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
        }
        .form-group input, .form-group select {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 8px;
            box-sizing: border-box;
            font-size: 16px;
        }
        .price-details {
            background-color: #e9f2ff;
            padding: 20px;
            border-radius: 8px;
            margin-top: 20px;
        }
         .price-details div {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-size: 16px;
        }      
        .price-details .total {
            font-weight: 700;
            font-size: 20px;
            margin-top: 10px;
            padding-top: 10px;
            border-top: 1px solid #ccc;
        }
    </style>
</head>
<body>
    <header>
        <div class="logo" onclick="showPage('home')">ArmadaKita</div>
        <nav>
            <a href="#" class="button" onclick="showPage('home')">Beranda</a>
        </nav>
    </header>
    <main class="container">
        <!-- ====================== HALAMAN 1: BERANDA (HOMEPAGE) ====================== -->
        <section id="home-page" class="page">
            <div class="hero">
                <h1>Solusi Penyewaan Kendaraan Terlengkap</h1>
                <p>Dari mobil harian hingga alat berat, kami siap melayani kebutuhan personal maupun proyek besar Anda.</p>
            </div>
            <h2 style="text-align: center; margin-top: 40px;">Pilih Kategori Armada</h2>
            <div class="category-grid">
                <div class="category-card" onclick="filterVehicles('Mobil')"><span class="icon">🚗</span> Mobil</div>
                <div class="category-card" onclick="filterVehicles('Alat Berat')"><span class="icon">🏗️</span> Alat Berat</div>
                <div class="category-card" onclick="filterVehicles('Armada Laut')"><span class="icon">🚤</span> Armada Laut</div>
                <div class="category-card" onclick="filterVehicles('Truk')"><span class="icon">🚚</span> Truk</div>
                <div class="category-card" onclick="filterVehicles('Semua')"><span class="icon">🔄</span> Semua</div>
            </div>
            <section id="armada-tersedia-section" class="hidden">
                <h2 style="text-align: center; margin-top: 40px;">Armada Tersedia</h2>
                <div id="vehicle-list" class="vehicle-grid">
                    <!-- Kendaraan akan dimasukkan di sini oleh JavaScript -->
                </div>
            </section>
        </section>
        <!-- ====================== HALAMAN 2: DETAIL KENDARAAN ====================== -->
        <section id="detail-page" class="page hidden">
             <button class="button back-button" onclick="showPage('home')">&larr; Kembali ke Daftar</button>
             <div class="detail-layout">
                <div>
                    <img id="detail-image" src="https://placehold.co/600x400/e2e8f0/adb5bd?text=Gambar+Kendaraan" alt="Gambar Kendaraan">
                </div>
                <div>
                    <p id="detail-category" class="category"></p>
                    <h2 id="detail-name" style="margin-top:0; font-size: 32px;">Nama Kendaraan</h2>
                    <div style="background-color: #f0f0f0; padding: 15px; border-radius: 8px; margin-bottom: 20px;">
                        <p style="margin: 0;">Ketersediaan: <strong id="detail-availability" style="color: var(--success-color);"></strong></p>
                        <p style="margin: 10px 0 0 0; font-size: 24px; font-weight: bold; color: var(--primary-color);" id="detail-price"></p>
                    </div>                   
                    <h3>Spesifikasi Detail</h3>
                    <ul id="detail-specs">
                        <!-- Spesifikasi akan dimasukkan di sini oleh JavaScript -->
                    </ul>
                    <button id="sewa-button" class="button">Sewa Sekarang</button>
                </div>
            </div>
        </section>
        <!-- ====================== HALAMAN 3: PENYEWAAN (BOOKING) ====================== -->
        <section id="booking-page" class="page hidden">
            <button class="button back-button" onclick="showPage('detail')">&larr; Kembali ke Detail</button>
            <div class="booking-form">
                <h2>Formulir Penyewaan</h2>
                <p>Anda akan menyewa: <strong id="booking-vehicle-name"></strong></p>
                <div class="form-group">
                    <label for="start-date">Tanggal Mulai Sewa</label>
                    <input type="date" id="start-date" required>
                </div>
                <div class="form-group">
                    <label for="duration">Durasi Sewa (hari)</label>
                    <input type="number" id="duration" value="1" min="1" required>
                </div>
                <div class="form-group">
                    <label for="region">Region/Lokasi Proyek</label>
                    <select id="region">
                        <option value="0">Cilegon (Tanpa Biaya Tambahan)</option>
                        <option value="150000">Serang (+ Rp 150.000)</option>
                        <option value="500000">Jakarta (+ Rp 500.000)</option>
                    </select>
                </div>
                <div class="price-details">
                    <h3>Rincian Biaya</h3>
                    <div><span>Harga Sewa per Hari</span><span id="price-per-day">Rp 0</span></div>
                    <div><span>Durasi</span><span id="price-duration">1 Hari</span></div>
                    <div><span>Biaya Pengantaran</span><span id="price-region">Rp 0</span></div>
                    <hr>
                    <div class="total"><span>Total Pembayaran</span><span id="price-total">Rp 0</span></div>
                </div>
                 <button class="button" style="width: 100%; margin-top: 20px; padding: 15px; background-color: var(--success-color);">Ajukan Sewa & Bayar</button>
            </div>
        </section>
    </main>
    <!-- JavaScript untuk fungsionalitas -->
    <script>
        // ====================== DATABASE SEMENTARA ======================
        const vehiclesDB = [
            {
                id: 1, category: "Mobil", name: "Toyota Avanza G TSS",
                image: "https://placehold.co/600x400/e2e8f0/adb5bd?text=Avanza",
                availability: 8, price_per_day: 350000,
                specs: { "Mesin": "1300cc, Bensin", "Transmisi": "Manual", "Kapasitas": "7 Penumpang", "Fitur": "AC, Bluetooth Audio" }
            },
            {
                id: 2, category: "Alat Berat", name: "Bulldozer Komatsu D85ESS-2",
                image: "https://placehold.co/600x400/e2e8f0/adb5bd?text=Bulldozer",
                availability: 3, price_per_day: 2500000,
                specs: { "Mesin": "Komatsu SAA6D125E-5", "Berat Operasi": "28 Ton", "Bahan Bakar": "Solar", "Kelengkapan": "Termasuk Operator" }
            },
            {
                id: 3, category: "Armada Laut", name: "Speedboat Yamaha 242X",
                image: "https://placehold.co/600x400/e2e8f0/adb5bd?text=Speedboat",
                availability: 2, price_per_day: 4000000,
                specs: { "Mesin": "Twin 1.8L Yamaha Marine", "Kapasitas": "12 Penumpang", "Panjang": "7.4 Meter", "Fitur": "GPS, Audio System" }
            },
            {
                id: 4, category: "Truk", name: "Hino Dutro Cargo 110 SDR",
                image: "https://placehold.co/600x400/e2e8f0/adb5bd?text=Truk+Hino",
                availability: 5, price_per_day: 850000,
                specs: { "Tipe": "Light Duty Truck", "Kapasitas Angkut": "4 Ton", "Bahan Bakar": "Solar", "Transmisi": "Manual" }
            }
        ];
        // ====================== STATE MANAGEMENT ======================
        let currentVehicleId = null;
        // ====================== DOM ELEMENTS ======================
        const pages = document.querySelectorAll('.page');
        const vehicleListContainer = document.getElementById('vehicle-list');
        // ====================== FUNCTIONS ======================
        // Fungsi untuk menampilkan halaman tertentu
        function showPage(pageName) {
            pages.forEach(page => {
                if (page.id === `${pageName}-page`) {
                    page.classList.remove('hidden');
                } else {
                    page.classList.add('hidden');
                }
            });
            window.scrollTo(0, 0); // Selalu scroll ke atas
        }
        // Fungsi untuk merender daftar kendaraan di homepage
        function renderVehicleList(filter = 'Semua') {
            vehicleListContainer.innerHTML = ''; // Kosongkan daftar
            const filteredVehicles = (filter === 'Semua') ? vehiclesDB : vehiclesDB.filter(v => v.category === filter);
            if(filteredVehicles.length === 0) {
                vehicleListContainer.innerHTML = `<p>Tidak ada kendaraan dalam kategori ini.</p>`;
                return;
            }
            filteredVehicles.forEach(vehicle => {
                const card = document.createElement('div');
                card.className = 'vehicle-card';
                card.innerHTML = `
                    <img src="${vehicle.image}" alt="${vehicle.name}" onerror="this.src='https://placehold.co/600x400/e2e8f0/adb5bd?text=Gambar+Rusak'">
                    <div class="vehicle-card-content">
                        <p class="category">${vehicle.category}</p>
                        <h3>${vehicle.name}</h3>
                        <p class="price">Rp ${vehicle.price_per_day.toLocaleString('id-ID')} / hari</p>
                        <button class="button" onclick="viewDetail(${vehicle.id})">Lihat Detail</button>
                    </div>
                `;
                vehicleListContainer.appendChild(card);
            });
        }
        // Fungsi untuk memfilter kendaraan berdasarkan kategori
        function filterVehicles(category) {
            document.getElementById('armada-tersedia-section').classList.remove('hidden');
            renderVehicleList(category);
        }
        // Fungsi untuk menampilkan halaman detail kendaraan
        function viewDetail(vehicleId) {
            currentVehicleId = vehicleId;
            const vehicle = vehiclesDB.find(v => v.id === vehicleId);
           document.getElementById('detail-name').innerText = vehicle.name;
            document.getElementById('detail-category').innerText = vehicle.category;
            document.getElementById('detail-image').src = vehicle.image;
            document.getElementById('detail-availability').innerText = `${vehicle.availability} Unit Tersedia`;
            document.getElementById('detail-price').innerText = `Rp ${vehicle.price_per_day.toLocaleString('id-ID')} / hari`;    
            const specsList = document.getElementById('detail-specs');
            specsList.innerHTML = '';
            for (const [key, value] of Object.entries(vehicle.specs)) {
                specsList.innerHTML += `<li><span>${key}</span> <span>${value}</span></li>`;
            }
            document.getElementById('sewa-button').onclick = () => viewBooking(vehicleId);
            showPage('detail');
        }
        // Fungsi untuk menampilkan halaman booking dan setup kalkulator harga
        function viewBooking(vehicleId) {
            currentVehicleId = vehicleId;
            const vehicle = vehiclesDB.find(v => v.id === vehicleId);   
            document.getElementById('booking-vehicle-name').innerText = vehicle.name;
            const durationInput = document.getElementById('duration');
            const regionSelect = document.getElementById('region');
            const calculatePrice = () => {
                const duration = parseInt(durationInput.value) || 1;
                const regionFee = parseInt(regionSelect.value) || 0;
                const basePrice = vehicle.price_per_day * duration;
                const totalPrice = basePrice + regionFee;                
                document.getElementById('price-per-day').innerText = `Rp ${vehicle.price_per_day.toLocaleString('id-ID')}`;
                document.getElementById('price-duration').innerText = `${duration} Hari`;
                document.getElementById('price-region').innerText = `Rp ${regionFee.toLocaleString('id-ID')}`;
                document.getElementById('price-total').innerText = `Rp ${totalPrice.toLocaleString('id-ID')}`;
            };          
            durationInput.oninput = calculatePrice;
            regionSelect.onchange = calculatePrice;           
            calculatePrice(); // Hitung harga awal
            showPage('booking');
        }
        // ====================== INITIALIZATION ======================
        document.addEventListener('DOMContentLoaded', () => {
            // Set tanggal minimum untuk input tanggal adalah hari ini
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('start-date').setAttribute('min', today);
            // Tidak merender list saat awal load
            // renderVehicleList(); 
            showPage('home'); // Tampilkan homepage
        });
    </script>

</body>
</html>

