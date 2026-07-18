<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>Buat Adek Salsa ❤️</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        love: '#ff4d6d',
                        soft: '#ffccd5',
                        darklove: '#c9184a',
                        tenang: '#800040',
                        lembut: '#ffe0e6'
                    },
                    fontFamily: {
                        romantis: ['Dancing Script', 'cursive'],
                        utama: ['Poppins', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; touch-action: pan-y; }
        html, body { height: 100%; }
        body {
            background: linear-gradient(160deg, #fff0f5, #ffdde1, #ffb3c1);
            background-size: 300% 300%;
            animation: gerakLatar 12s ease infinite;
            font-family: 'Poppins', sans-serif;
            text-align: center;
            padding: env(safe-area-inset-top) env(safe-area-inset-right) env(safe-area-inset-bottom) env(safe-area-inset-left);
        }
        @keyframes gerakLatar {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .hati { animation: denyut 1.1s infinite; }
        @keyframes denyut {
            0%,100% { transform: scale(1); }
            50% { transform: scale(1.2); }
        }

        /* === 1. LAYAR MASUK SANDI === */
        .layar-sandi {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            background: linear-gradient(160deg, #fff0f5, #ffdde1, #ffb3c1);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            padding: 20px;
            transition: opacity 0.5s ease, transform 0.5s ease;
            overflow-y: auto;
        }
        .layar-sandi.sembunyi {
            opacity: 0; transform: translateY(-100%);
            pointer-events: none;
        }
        .kotak-sandi {
            background: rgba(255,255,255,0.85);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 35px 25px;
            width: 90%; max-width: 360px;
            box-shadow: 0 12px 35px rgba(201,24,74,0.25);
            border: 1px solid rgba(255,255,255,0.9);
        }
        .input-sandi {
            width: 100%; padding: 14px 15px;
            border: 2px solid #ffccd5; border-radius: 12px;
            font-size: 18px; text-align: center;
            margin: 18px 0; outline: none;
            transition: 0.3s; background: rgba(255,255,255,0.9);
        }
        .input-sandi:focus { border-color: #ff4d6d; box-shadow: 0 0 10px rgba(255,77,109,0.4); }
        .tombol-masuk {
            background: linear-gradient(135deg, #ff4d6d, #c9184a);
            color: white; border: none; border-radius: 12px;
            padding: 14px 25px; font-size: 16px; font-weight: 600;
            width: 100%; cursor: pointer; transition: 0.3s;
        }
        .tombol-masuk:hover { transform: translateY(-2px); box-shadow: 0 5px 15px rgba(255,77,109,0.4); }
        .pesan-salah { color: #c9184a; font-size: 13px; margin-top: 12px; display: none; }

        /* === 2. LAYAR TARIK TALI === */
        .layar-tarik {
            position: fixed;
            top: 0; left: 0;
            width: 100%; height: 100%;
            z-index: 999;
            display: none;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: linear-gradient(160deg, #fff0f5, #ffdde1, #ffb3c1);
            transition: opacity 0.6s ease, transform 0.6s ease;
            overflow-y: auto;
        }
        .layar-tarik.tampil { display: flex; }
        .layar-tarik.sembunyi { opacity: 0; transform: translateY(-100%); pointer-events: none; }
        .tali {
            width: 3px; height: 230px;
            background: linear-gradient(180deg, #ff4d6d, #c9184a);
            border-radius: 3px; position: relative; margin-bottom: 20px;
        }
        .tali::after {
            content: ''; position: absolute; bottom: 0; left: 50%;
            transform: translateX(-50%); width: 12px; height: 12px;
            background: #c9184a; border-radius: 50%;
        }
        .pegangan { cursor: grab; user-select: none; margin-top: -10px; transition: transform 0.1s ease; }
        .pegangan:active { cursor: grabbing; }
        .nama-salsa {
            font-family: 'Dancing Script', cursive; font-size: 32px;
            color: #c9184a; margin-bottom: 15px; font-weight: 700;
        }
        .petunjuk { font-size: 14px; color: #800040; margin-top: 25px; font-weight: 500; }

        /* === 3. ISI UTAMA === */
        #isiWeb { display: none; width: 100%; height: 100%; overflow-y: auto; padding-bottom: 100px; }
        .partikel {
            position: fixed; animation: jatuh 12s infinite ease-in;
            opacity: 0; pointer-events: none;
        }
        @keyframes jatuh {
            0% { transform: translateY(-15px) rotate(0deg); opacity: 1; }
            100% { transform: translateY(105vh) rotate(360deg); opacity: 0; }
        }
        .kotak {
            background: rgba(255,255,255,0.78); backdrop-filter: blur(15px);
            border-radius: 20px; padding: 24px 20px; margin: 12px 16px;
            box-shadow: 0 8px 25px rgba(201,24,74,0.2); border: 1px solid rgba(255,255,255,0.9);
            text-align: justify;
        }
        .angka { font-size: 28px; font-weight: 700; color: #c9184a; }
        .label { font-size: 13px; color: #800040; opacity: 0.8; }
        .tombol-menu {
            background: linear-gradient(135deg, #ff4d6d, #c9184a);
            color: white; border: none; border-radius: 50px;
            padding: 12px 14px; font-size: 12px; margin: 4px;
            cursor: pointer; transition: 0.25s;
            box-shadow: 0 4px 12px rgba(255,77,109,0.35);
        }
        .tombol-menu.aktif { background: #800040; box-shadow: 0 0 20px rgba(201,24,74,0.5); }
        .halaman { display: none; padding: 0 10px; }
        .halaman.aktif { display: block; }
        h2 { font-family: 'Dancing Script', cursive; color: #c9184a; font-size: 24px; margin-bottom: 12px; text-align: center; }
        p { font-size: 14px; color: #552233; line-height: 1.9; }
        .titik { color: #ff4d6d; font-weight: bold; }
        .garis-pemisah {
            width: 70%; height: 2px;
            background: linear-gradient(90deg, transparent, #ff4d6d, transparent);
            margin: 18px auto;
        }
        .menu-bawah {
            position: fixed; bottom: 15px; left: 0; right: 0;
            padding: 10px; background: rgba(255,255,255,0.3);
            backdrop-filter: blur(8px); z-index: 10;
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
</head>
<body>

    <!-- TAG AUDIO RAHASIA UNTUK MUSIK OTOMATIS -->
    <audio id="musikBackground" autoplay muted loop>
        <source src="musik-kamu.mp3" type="audio/mpeg">
    </audio>

    <!-- LANGKAH 1: MASUKKAN SANDI -->
    <div id="layarSandi" class="layar-sandi">
        <div class="kotak-sandi">
            <i class="fa fa-heart text-5xl text-love hati mb-4"></i>
            <h2 class="text-2xl mb-2">Hanya Untuk Wanita tersayang ❤️</h2>
            <p class="text-sm text-darklove mb-4">Masukkan sandi rahasia ini untuk membuka pesan yang Abang buat dengan sepenuh hati</p>
            <input type="password" id="inputSandi" class="input-sandi" placeholder="Masukkan sandi..." maxlength="6" autocomplete="off">
            <button class="tombol-masuk" onclick="cekSandi()">Buka Pesan Abang</button>
            <p id="pesanSalah" class="pesan-salah"><i class="fa fa-exclamation-circle mr-1"></i> Sandi salah sayang, coba lagi ya😘</p>
        </div>
    </div>

    <!-- LANGKAH 2: TARIK TALI KHUSUS SALSA -->
    <div id="layarTarik" class="layar-tarik">
        <div class="nama-salsa">Hai Adek sayang ❤️</div>
        <p class="text-sm text-darklove mb-4">Tarik hati ini turun sampai habis ya... ada pesan panjang yang Abang siapkan buat kamu</p>
        <div class="tali"></div>
        <div id="pegangan" class="pegangan">
            <i class="fa fa-heart text-5xl text-love hati"></i>
        </div>
        <p class="petunjuk">Tarik terus sampai mentok ke bawah ya sayang</p>
    </div>

    <!-- LANGKAH 3: ISI PESAN UTAMA -->
    <div id="isiWeb">
        <div id="wadah-partikel" class="fixed inset-0"></div>

        <div id="utama" class="halaman aktif">
            <div class="pt-9">
                <i class="fa fa-heart text-6xl text-love hati drop-shadow-md"></i>
                <h1 class="text-3xl font-romantis text-darklove mt-4">Buat Adek Kesayangan Abang ❤️</h1>
                <p class="text-sm text-darklove mt-2">Abang takkan pernah lupa hari pertama kita saling mengenal dan menyayangi</p>
                <p class="text-lg font-bold text-love mt-1">27 November 2025</p>
            </div>

            <div class="kotak mt-5">
                <h2>Waktu yang Kita Lewati Bersama</h2>
                <div class="grid grid-cols-4 gap-2 mt-4">
                    <div class="text-center"><p class="angka" id="hari">0</p><p class="label">Hari</p></div>
                    <div class="text-center"><p class="angka" id="jam">0</p><p class="label">Jam</p></div>
                    <div class="text-center"><p class="angka" id="menit">0</p><p class="label">Menit</p></div>
                    <div class="text-center"><p class="angka" id="detik">0</p><p class="label">Detik</p></div>
                </div>
                <div class="garis-pemisah"></div>
                <p class="text-sm text-darklove italic mt-2 text-center">
                    Waktu ini akan terus berjalan, takkan pernah berhenti meskipun halaman ini ditutup, atau berbulan-bulan lagi Adek tidak membukanya. Begitu pula rasa sayang dan kenangan Abang buat Salsa, takkan pernah pudar atau hilang dimakan waktu. Setiap detik yang berlalu adalah bukti bahwa Abang masih ingat, masih peduli, dan masih menyayangi Adek persis seperti perasaan Abang di hari pertama itu.
                </p>
            </div>
            <div class="kotak mt-2">
                <p id="pesan-harian" class="text-sm font-medium text-tenang text-center"></p>
            </div>
        </div>

        <div id="pesan" class="halaman pt-9">
            <div class="kotak">
                <h2>Pesan Tulus Sepenuh Hati Dari Abang Buat Salsa</h2>
                <p>
                    Hai Adek Salsa sayang...<br><br>
                    Mungkin sekarang kita sudah tidak ada status yang mengikat kita berdua, tidak ada kata "pacar" atau "kita" seperti dulu lagi. Tapi Abang ingin Adek tahu satu hal yang paling penting dan paling benar: <span class="titik">di dalam hati Abang yang paling dalam, Salsa tetaplah Adek kesayangan Abang, tak berubah sedikitpun, tak berkurang sedikitpun rasa sayang ini.</span><br><br>
                    Hari tanggal <span class="titik">27 November 2025</span> itu adalah hari yang sangat indah dan berharga yang pernah Abang miliki seumur hidup. Di hari itu, dunia Abang terasa lebih berwarna, lebih hangat, dan lebih bermakna karena akhirnya Abang bisa mengenal, mendekat, dan menyayangi wanita sebaik kamu. Semua cerita, tawa lepas, tangis yang kita usap bersama, obrolan panjang sampai larut malam, janji-janji kecil, dan momen-momen sederhana yang kita lalui berdua, semuanya tersimpan rapi, utuh, dan takkan pernah Abang hapus atau ganti dengan apapun.<br><br>
                    Terima kasih banyak ya Adekku... Terima kasih sudah pernah hadir di hidup Abang yang dulu mungkin terasa biasa saja. Terima kasih sudah mau mendengarkan semua cerita Abang, sudah mau sabar menghadapi segala kurangnya Abang, sudah mau mengerti dan mencintai Abang apa adanya. Walaupun sekarang jalan kita berdua sudah berbeda arah, Abang tidak pernah menyesal memilih kamu, dan Abang sangat bangga pernah menjadi bagian dari perjalanan hidupmu.<br><br>
                    Abang tidak meminta untuk kembali seperti dulu, tidak meminta kamu menunggu, atau meminta hal lain yang memberatkan hati kamu. <span class="titik">Abang tak tahu kapan bisa kembali bersamamu, tapi Abang yakin kalau jodoh takkan pernah lari kemana pun.</span> Satu-satunya harapan dan doa Abang cuma satu: semoga Salsa selalu bahagia, selalu sehat, selalu tersenyum lebar, dan semoga segala hal baik, keberuntungan, dan kasih sayang yang tulus selalu menyertai langkahmu dimanapun kamu berada dan apapun yang kamu jalani nanti. Kalau nanti dunia terasa jahat, kalau kamu lelah, sedih, atau cuma butuh teman cerita, ingatlah satu hal: Abang tetap ada di sini, untukmu, kapanpun itu ❤️
                </p>
            </div>
        </div>

        <div id="janji" class="halaman pt-9">
            <div class="kotak">
                <h2>Janji Abang Yang Takkan Pernah Berubah</h2>
                <p class="text-left">
                    <span class="titik">❤️</span> Abang takkan pernah melupakan wajah, suara, tawa, dan semua hal tentang Salsa<br>
                    <span class="titik">❤️</span> Panggilan "Adek" itu khusus Abang pakai hanya untuk kamu seorang<br>
                    <span class="titik">❤️</span> Abang akan selalu mendukung semua impian dan cita-cita Salsa dari jauh<br>
                    <span class="titik">❤️</span> Rasa sayang Abang takkan berubah meski status kita sudah berbeda<br>
                    <span class="titik">❤️</span> Abang takkan pernah menyakiti atau bicara buruk tentang Salsa dimanapun<br>
                    <span class="titik">❤️</span> Kalau dunia tak baik sama kamu, ingat Abang selalu ada untuk lindungi kamu<br>
                    <span class="titik">❤️</span> Abang bangga dan bersyukur pernah dicintai oleh wanita sebaik Salsa<br>
                    <span class="titik">❤️</span> Abang akan selalu berdoa semoga kamu bertemu orang yang bisa mencintaimu lebih baik dari Abang, dan bisa menjagamu seperti yang Abang inginkan<br>
                    <span class="titik">❤️</span> Sampai kapanpun, kamu tetap Adek yang paling berharga di hidup Abang<br>
                </p>
                <div class="garis-pemisah"></div>
                <p class="text-center mt-2 italic">
                    "Abang mungkin tak bisa lagi memelukmu secara langsung, tapi doa Abang akan selalu memelukmu di setiap hembusan napas Abang"<br>
                    <span class="font-bold">— Abang yang takkan pernah berhenti menyayangimu, Salsa</span>
                </p>
            </div>
        </div>

        <div id="kenangan" class="halaman pt-9">
            <div class="kotak">
                <h2>Kenangan Indah Abang & Salsa</h2>
                <p>
                    Setiap hal kecil yang kita lalui bersama, entah itu sekadar bertukar pesan singkat, berbagi cerita lucu, saling menghibur saat sedang sedih, atau sekadar diam bersama tanpa banyak bicara, semuanya adalah harta paling berharga yang Abang miliki. Tidak ada yang bisa menggantikan rasa hangat saat Abang memanggilmu "Adek", atau saat kamu menyapa Abang dengan sebutan "Abang".<br><br>
                    Mungkin sekarang kita harus berjalan sendiri-sendiri, mengejar kebahagiaan kita masing-masing. Tapi Abang ingin kamu paham satu hal: rasa sayang yang tulus itu tidak harus selalu memiliki, bukan? Kadang mencintai juga berarti merelakan, mendoakan, dan berharap orang yang kita sayangi mendapatkan yang paling indah, meskipun itu bukan kita yang menemani nanti.<br><br>
                    Dimanapun kamu berada nanti, senyum kamu adalah hal yang paling Abang harapkan. Jangan pernah merasa sendirian ya, karena di sini ada Abang yang selalu mengingatmu dengan penuh kasih sayang dan rasa syukur. Semoga nanti kalau kita berpapasan lagi, kita berdua sudah menjadi orang yang lebih kuat, lebih bahagia, dan tetap saling mendoakan seperti sekarang ❤️
                </p>
            </div>
        </div>

        <div class="menu-bawah text-center">
            <button class="tombol-menu aktif" onclick="bukaHalaman('utama', this)"><i class="fa fa-home mr-1"></i> Utama</button>
            <button class="tombol-menu" onclick="bukaHalaman('pesan', this)"><i class="fa fa-heart mr-1"></i> Pesan</button>
            <button class="tombol-menu" onclick="bukaHalaman('janji', this)"><i class="fa fa-handshake-o mr-1"></i> Janji</button>
            <button class="tombol-menu" onclick="bukaHalaman('kenangan', this)"><i class="fa fa-book mr-1"></i> Kenangan</button>
        </div>
    </div>

    <script>
        // === LOGIK JAVASCRIPT UNTUK AKTIVASI AUDIO OTOMATIS ===
        const musik = document.getElementById('musikBackground');
        
        function hidupkanSuara() {
            musik.muted = false;
            musik.play().catch(e => console.log("Autoplay diblokir browser"));
        }
        
        // Pemicu suara aktif begitu ada interaksi ketikan sandi atau klik tombol masuk
        document.getElementById('inputSandi').addEventListener('focus', hidupkanSuara);
        document.getElementById('inputSandi').addEventListener('input', hidupkanSuara);

        // === LANGKAH 1: CEK SANDI ===
        const sandiBenar = "120208";
        function cekSandi() {
            hidupkanSuara(); // Pastikan musik bersuara saat tombol ditekan
            const input = document.getElementById('inputSandi').value.trim();
            const pesanSalah = document.getElementById('pesanSalah');
            if (input === sandiBenar) {
                document.getElementById('layarSandi').classList.add('sembunyi');
                setTimeout(()=> document.getElementById('layarTarik').classList.add('tampil'), 500);
            } else {
                pesanSalah.style.display = 'block';
                document.getElementById('inputSandi').value = '';
            }
        }
        document.getElementById('inputSandi').addEventListener('keypress', e=> { if(e.key==='Enter') cekSandi(); });

        // === LANGKAH 2: TARIK TALI ===
        const pegangan = document.getElementById('pegangan');
        const layarTarik = document.getElementById('layarTarik');
        const isiWeb = document.getElementById('isiWeb');
        let yAwal = 0, ySekarang = 0, ditarik = false;
        const BATAS_TARIK = 190;

        function mulaiTarik(e) { 
            hidupkanSuara(); // Pengaman jika suara belum aktif saat masuk
            ditarik = true; 
            yAwal = e.touches ? e.touches[0].clientY : e.clientY; 
        }
        function lagiTarik(e) {
            if (!ditarik) return;
            ySekarang = e.touches ? e.touches[0].clientY : e.clientY;
            const jarak = ySekarang - yAwal;
            if (jarak > 0) pegangan.style.transform = `translateY(${jarak}px)`;
            if (jarak >= BATAS_TARIK) bukaIsiWeb();
        }
        function lepasTarik() {
            if (!ditarik) return; ditarik = false;
            const jarak = ySekarang - yAwal;
            if (jarak < BATAS_TARIK) pegangan.style.transform = 'translateY(0)';
        }
        function bukaIsiWeb() {
            layarTarik.classList.add('sembunyi');
            setTimeout(()=>{
                isiWeb.style.display = 'block';
                tampilPesan(); hitungWaktu();
                setInterval(hitungWaktu, 1000);
                setInterval(buatPartikel, 700);
            }, 600);
            pegangan.removeEventListener('mousedown', mulaiTarik);
            document.removeEventListener('mousemove', lagiTarik);
            document.removeEventListener('mouseup', lepasTarik);
            pegangan.removeEventListener('touchstart', mulaiTarik);
            document.removeEventListener('touchmove', lagiTarik);
            document.removeEventListener('touchend', lepasTarik);
        }
        pegangan.addEventListener('mousedown', mulaiTarik);
        document.addEventListener('mousemove', lagiTarik);
        document.addEventListener('mouseup', lepasTarik);
        pegangan.addEventListener('touchstart', mulaiTarik);
        document.addEventListener('touchmove', lagiTarik);
        document.addEventListener('touchend', lepasTarik);

        // === FUNGSI UTAMA ===
        const tanggalMulai = new Date('2025-11-27T00:00:00');
        const daftarPesan = [
            "Abang selalu sayang sama Salsa, kapanpun dan dimanapun ❤️",
            "Semoga hari ini Adek senyum terus, jangan lupa makan dan istirahat ya",
            "Kenangan kita takkan pernah hilang, tetap indah di hati Abang",
            "Salsa adalah hal terindah yang pernah terjadi di hidup Abang",
            "Setiap doa Abang selalu Abang selipkan nama Salsa di dalamnya",
            "Tetap semangat kejar cita-citamu ya Adek, Abang dukung terus",
            "Terima kasih sudah pernah berikan cinta yang tulus buat Abang",
            "Tak ada yang bisa menggantikan posisi Salsa di hati Abang selamanya"
        ];
        function tampilPesan() {
            const hariIni = new Date().toDateString();
            let simpan = localStorage.getItem('pesanTgl');
            let idx = localStorage.getItem('pesanIdx');
            if (simpan !== hariIni || idx === null) {
                idx = Math.floor(Math.random() * daftarPesan.length);
                localStorage.setItem('pesanTgl', hariIni);
                localStorage.setItem('pesanIdx', idx);
            }
            document.getElementById('pesan-harian').innerText = daftarPesan[idx];
        }
        function hitungWaktu() {
            const sekarang = new Date();
            const selisih = sekarang - tanggalMulai;
            document.getElementById('hari').innerText = Math.floor(selisih/(1000*60*60*24));
            document.getElementById('jam').innerText = Math.floor((selisih%(1000*60*60*24))/(1000*60*60));
            document.getElementById('menit').innerText = Math.floor((selisih%(1000*60*60))/(1000*60));
            document.getElementById('detik').innerText = Math.floor((selisih%(1000*60))/1000);
        }
        function bukaHalaman(id, btn) {
            document.querySelectorAll('.halaman').forEach(h=>h.classList.remove('aktif'));
            document.querySelectorAll('.tombol-menu').forEach(t=>t.classList.remove('aktif'));
            document.getElementById(id).classList.add('aktif');
            btn.classList.add('aktif');
        }
        function buatPartikel() {
            const p = document.createElement('div');
            p.innerText = ['❤️','💕','💖','✨','🌹','💓'][Math.floor(Math.random()*6)];
            p.classList.add('partikel');
            p.style.left = Math.random()*100+'vw';
            p.style.fontSize = (Math.random()*12+14)+'px';
            document.getElementById('wadah-partikel').appendChild(p);
            setTimeout(()=>p.remove(),13000);
        }
    </script>
</body>
</html>
