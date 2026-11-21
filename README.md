
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#123d2b">
<meta name="description" content="SIRAMIX - Smart Automatic Fertilization System untuk pemantauan dan pengelolaan pertanian.">
<title>SIRAMIX | Smart Agriculture System</title>

<style>
:root {
  --green: #176b45;
  --green-dark: #103d2b;
  --green-light: #e8f5ec;
  --bg: #f4f8f5;
  --white: #ffffff;
  --text: #20372b;
  --muted: #829187;
  --border: #e5eee7;
  --orange: #e99b38;
  --red: #d85b5b;
  --shadow: 0 8px 25px rgba(25, 75, 48, .06);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Segoe UI", Arial, sans-serif;
  background: var(--bg);
  color: var(--text);
}

button, input, select {
  font: inherit;
}

button {
  cursor: pointer;
}

.layout {
  min-height: 100vh;
}

/* SIDEBAR */

.sidebar {
  position: fixed;
  inset: 0 auto 0 0;
  width: 250px;
  padding: 25px 18px;
  background: var(--green-dark);
  color: white;
  z-index: 20;
  overflow-y: auto;
}

.logo {
  display: flex;
  align-items: center;
  gap: 10px;
  font-size: 25px;
  font-weight: 800;
  margin-bottom: 8px;
}

.logo-icon {
  width: 42px;
  height: 42px;
  display: grid;
  place-items: center;
  border-radius: 13px;
  background: rgba(255,255,255,.13);
}

.logo-subtitle {
  color: #a9cbb6;
  font-size: 11px;
  margin: 0 0 35px 52px;
}

.menu-title {
  color: #9bbba7;
  font-size: 10px;
  letter-spacing: 2px;
  margin: 22px 12px 12px;
}

.nav-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 13px 14px;
  margin: 5px 0;
  border-radius: 10px;
  color: #d6e8dc;
  font-size: 13px;
  text-decoration: none;
  border: 0;
  background: transparent;
  width: 100%;
  text-align: left;
  transition: .2s;
}

.nav-item:hover,
.nav-item.active {
  background: #287b53;
  color: white;
}

.nav-icon {
  width: 22px;
  text-align: center;
  font-size: 17px;
}

.nav-link {
  border: 1px solid #4d8063;
  margin-top: 20px;
}

.sidebar-bottom {
  margin-top: 35px;
  padding: 15px;
  border-radius: 12px;
  background: rgba(255,255,255,.08);
  font-size: 11px;
  line-height: 1.7;
  color: #c5dfce;
}

/* MAIN */

.main {
  margin-left: 250px;
  padding: 28px 35px;
  min-height: 100vh;
}

.topbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  margin-bottom: 28px;
}

.topbar h2 {
  font-size: 23px;
}

.topbar p {
  color: var(--muted);
  font-size: 12px;
  margin-top: 5px;
}

.system-status {
  display: flex;
  align-items: center;
  gap: 8px;
  background: #e5f5e9;
  color: #187044;
  padding: 9px 14px;
  border-radius: 30px;
  font-size: 11px;
  font-weight: 700;
}

.status-dot {
  width: 8px;
  height: 8px;
  background: #35aa64;
  border-radius: 50%;
}

/* PAGE */

.page {
  display: none;
  animation: appear .25s ease;
}

.page.active {
  display: block;
}

@keyframes appear {
  from { opacity: 0; transform: translateY(5px); }
  to { opacity: 1; transform: translateY(0); }
}

.page-heading {
  margin: 25px 0 18px;
  font-size: 20px;
}

.hero {
  position: relative;
  overflow: hidden;
  padding: 38px;
  border-radius: 20px;
  background: linear-gradient(120deg, #104c31, #31935a);
  color: white;
  margin-bottom: 25px;
}

.hero::after {
  content: "🌿";
  position: absolute;
  right: 35px;
  bottom: -20px;
  font-size: 115px;
  opacity: .14;
}

.hero h1 {
  font-size: 30px;
  margin-bottom: 13px;
}

.hero p {
  max-width: 650px;
  color: #e0f2e5;
  font-size: 13px;
  line-height: 1.9;
}

.hero-button {
  margin-top: 20px;
  padding: 12px 19px;
  background: white;
  color: var(--green);
  border: none;
  border-radius: 9px;
  font-weight: 700;
}

/* CARDS */

.grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 16px;
  margin-bottom: 22px;
}

.card,
.panel {
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: 15px;
  padding: 21px;
  box-shadow: var(--shadow);
}

.card {
  transition: .2s;
}

.card:hover {
  transform: translateY(-3px);
}

.card-icon {
  width: 43px;
  height: 43px;
  display: grid;
  place-items: center;
  border-radius: 13px;
  background: var(--green-light);
  font-size: 21px;
  margin-bottom: 15px;
}

.card small {
  color: var(--muted);
  font-size: 11px;
}

.card h3 {
  font-size: 14px;
  margin-bottom: 7px;
}

.card p {
  font-size: 12px;
  line-height: 1.7;
  color: var(--muted);
}

.value {
  font-size: 27px;
  font-weight: 800;
  margin: 8px 0;
}

.card-status {
  font-size: 11px;
  color: var(--green);
}

/* PANEL */

.panel {
  margin-bottom: 18px;
}

.panel h3 {
  font-size: 15px;
  margin-bottom: 16px;
}

.panel-description {
  font-size: 13px;
  line-height: 1.8;
  color: #68796e;
}

.panel-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
  margin-bottom: 15px;
}

/* BUTTON */

.btn {
  border: 0;
  padding: 11px 17px;
  border-radius: 9px;
  background: var(--green);
  color: white;
  font-size: 12px;
  font-weight: 700;
  transition: .2s;
}

.btn:hover {
  background: #105436;
  transform: translateY(-1px);
}

.btn-light {
  background: #e8f5ec;
  color: var(--green);
}

.btn-light:hover {
  background: #d7ecdd;
}

.btn-danger {
  background: var(--red);
}

.btn-off {
  background: #e6ece7;
  color: #526257;
}

.btn-off:hover {
  background: #d8e2da;
}

/* FORM */

.form-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 15px;
  margin-bottom: 17px;
}

.field label {
  display: block;
  font-size: 12px;
  font-weight: 700;
  margin-bottom: 7px;
}

.field input,
.field select,
.control-input {
  width: 100%;
  padding: 11px;
  border: 1px solid #dce7de;
  border-radius: 9px;
  background: white;
  color: var(--text);
  outline: none;
  font-size: 13px;
}

.field input:focus,
.field select:focus,
.control-input:focus {
  border-color: var(--green);
  box-shadow: 0 0 0 3px rgba(23,107,69,.08);
}

.note {
  color: var(--muted);
  font-size: 11px;
  line-height: 1.7;
  margin-top: 13px;
}

.data-card {
  background: #f8fbf8;
  border: 1px solid var(--border);
  border-radius: 12px;
  padding: 17px;
}

.data-card b {
  display: block;
  color: var(--muted);
  font-size: 10px;
  letter-spacing: .5px;
}

.data-card strong {
  display: block;
  font-size: 22px;
  margin-top: 9px;
}

/* CONTROL */

.control-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 18px;
  padding: 15px 0;
  border-bottom: 1px solid #edf1ed;
}

.control-row:last-child {
  border-bottom: none;
}

.control-row b {
  font-size: 13px;
}

.control-row p {
  color: var(--muted);
  font-size: 11px;
  margin-top: 5px;
  line-height: 1.5;
}

.control-row select,
.control-row input {
  max-width: 155px;
}

/* PROGRESS */

.progress-track {
  height: 9px;
  background: #e8eee9;
  border-radius: 20px;
  overflow: hidden;
  margin-top: 12px;
}

.progress-fill {
  height: 100%;
  width: 65%;
  background: linear-gradient(90deg, #258452, #66bd7d);
  border-radius: 20px;
  transition: width .3s;
}

/* TABLE */

.table-wrap {
  overflow-x: auto;
}

table {
  width: 100%;
  border-collapse: collapse;
  min-width: 450px;
  font-size: 12px;
}

th, td {
  text-align: left;
  padding: 13px 10px;
  border-bottom: 1px solid #edf1ed;
}

th {
  color: var(--muted);
  font-size: 11px;
}

.tag {
  display: inline-block;
  padding: 5px 9px;
  border-radius: 20px;
  background: #e6f5e9;
  color: #187044;
  font-size: 10px;
  font-weight: 700;
}

/* NOTIFICATION */

.notification {
  padding: 14px;
  background: #f0f7f1;
  border: 1px solid #e2eee4;
  border-radius: 10px;
  font-size: 12px;
  margin-bottom: 10px;
  line-height: 1.7;
}

/* ABOUT */

.about-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 15px;
}

.about-box {
  padding: 22px;
  background: #eaf5ed;
  border-radius: 13px;
}

.about-box h3 {
  color: var(--green);
  font-size: 14px;
  margin-bottom: 10px;
}

.about-box p {
  font-size: 12px;
  line-height: 1.8;
  color: #536b5a;
}

footer {
  text-align: center;
  color: var(--muted);
  font-size: 11px;
  padding: 35px 10px 15px;
}

/* MOBILE */

@media(max-width:1000px) {
  .grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
  .main {
    padding: 25px;
  }
}

@media(max-width:650px) {
  .sidebar {
    position: relative;
    width: 100%;
    height: auto;
    padding: 15px;
  }

  .logo {
    font-size: 21px;
  }

  .logo-subtitle {
    margin-bottom: 15px;
  }

  .menu-title,
  .sidebar-bottom {
    display: none;
  }

  .nav-list {
    display: flex;
    overflow-x: auto;
    gap: 5px;
    padding-bottom: 5px;
  }

  .nav-item {
    width: auto;
    white-space: nowrap;
    flex-shrink: 0;
    padding: 11px 13px;
  }

  .main {
    margin: 0;
    padding: 18px 14px;
  }

  .topbar h2 {
    font-size: 19px;
  }

  .system-status {
    font-size: 9px;
    padding: 8px;
  }

  .hero {
    padding: 25px 20px;
  }

  .hero h1 {
    font-size: 24px;
  }

  .hero::after {
    font-size: 75px;
    right: 12px;
  }

  .grid,
  .form-grid,
  .about-grid {
    grid-template-columns: 1fr;
  }

  .card,
  .panel {
    padding: 17px;
  }

  .control-row {
    align-items: flex-start;
  }

  .control-row select,
  .control-row input {
    max-width: 125px;
  }
}
</style>
</head>

<body>

<div class="layout">

<!-- SIDEBAR -->
<aside class="sidebar">
  <div class="logo">
    <div class="logo-icon">🌱</div>
    SIRAMIX
  </div>
  <div class="logo-subtitle">SMART AGRICULTURE SYSTEM</div>

  <div class="menu-title">MENU UTAMA</div>

  <nav class="nav-list">
    <button class="nav-item active" data-page="home"><span class="nav-icon">⌂</span> Beranda</button>
    <button class="nav-item" data-page="dashboard"><span class="nav-icon">▦</span> Dashboard</button>
    <button class="nav-item" data-page="monitoring"><span class="nav-icon">◉</span> Monitoring Sensor</button>
    <button class="nav-item" data-page="pupuk"><span class="nav-icon">🌿</span> Pemupukan</button>
    <button class="nav-item" data-page="penyiraman"><span class="nav-icon">💧</span> Penyiraman Air</button>
    <button class="nav-item" data-page="riwayat"><span class="nav-icon">▤</span> Riwayat</button>
    <button class="nav-item" data-page="notifikasi"><span class="nav-icon">♧</span> Notifikasi</button>
    <button class="nav-item" data-page="about"><span class="nav-icon">ⓘ</span> Tentang Kami</button>
    <a class="nav-item nav-link" href="https://chatgpt.com/" target="_blank" rel="noopener noreferrer">
      <span class="nav-icon">🤖</span> SIRAMIX AI ↗
    </a>
  </nav>

  <div class="sidebar-bottom">
    <b>SIRAMIX SYSTEM</b><br>
    Mendukung pertanian yang lebih cerdas, efisien, dan berkelanjutan.
  </div>
</aside>

<!-- MAIN -->
<main class="main">

<header class="topbar">
  <div>
    <h2 id="pageTitle">Beranda</h2>
    <p>Smart Automatic Fertilization System</p>
  </div>
  <div class="system-status">
    <span class="status-dot"></span>
    MODE DEMONSTRASI
  </div>
</header>

<!-- BERANDA -->
<section class="page active" id="home">

  <div class="hero">
    <h1>Welcome to SIRAMIX 🌱</h1>
    <p>
      SIRAMIX merupakan inovasi teknologi pertanian yang mengintegrasikan
      pemantauan kondisi tanah, pengaturan pemupukan, dan penyiraman air
      secara otomatis. Sistem ini dirancang untuk membantu pengelolaan
      lahan melalui data sensor dan mikrokontroler ESP32 sehingga
      penggunaan air serta pupuk dapat dilakukan secara lebih terarah.
    </p>
    <button class="hero-button" data-go="dashboard">Buka Dashboard →</button>
  </div>

  <h2 class="page-heading">Fitur Utama</h2>

  <div class="grid">
    <div class="card">
      <div class="card-icon">🌱</div>
      <h3>Pemupukan Otomatis</h3>
      <p>Pengaturan pemberian pupuk berdasarkan kebutuhan dan kondisi tanah.</p>
    </div>

    <div class="card">
      <div class="card-icon">💧</div>
      <h3>Penyiraman Otomatis</h3>
      <p>Pengaturan penyiraman berdasarkan tingkat kelembapan tanah.</p>
    </div>

    <div class="card">
      <div class="card-icon">📡</div>
      <h3>Monitoring Sensor</h3>
      <p>Pemantauan unsur hara, suhu, pH, dan kelembapan tanah.</p>
    </div>

    <div class="card">
      <div class="card-icon">🤖</div>
      <h3>Analisis AI</h3>
      <p>Data kondisi tanah dapat disalin untuk memperoleh analisis melalui ChatGPT.</p>
    </div>

    <div class="card">
      <div class="card-icon">📋</div>
      <h3>Riwayat Aktivitas</h3>
      <p>Pencatatan aktivitas pemupukan dan penyiraman dalam sistem.</p>
    </div>

    <div class="card">
      <div class="card-icon">🔔</div>
      <h3>Notifikasi</h3>
      <p>Informasi mengenai kondisi dan aktivitas sistem.</p>
    </div>
  </div>

  <div class="panel">
    <h3>Tujuan Pengembangan</h3>
    <p class="panel-description">
      SIRAMIX dikembangkan untuk mendukung penerapan pertanian cerdas
      melalui pengelolaan air dan pupuk yang lebih terukur. Integrasi
      monitoring sensor dan sistem otomatis diharapkan dapat membantu
      pengguna menentukan tindakan berdasarkan kondisi lahan.
    </p>
  </div>
</section>

<!-- DASHBOARD -->
<section class="page" id="dashboard">
  <h2 class="page-heading">Dashboard Monitoring</h2>

  <div class="grid">
    <div class="card">
      <div class="card-icon">🌡️</div>
      <small>Suhu Tanah</small>
      <div class="value" id="dashTemp">28°C</div>
      <span class="card-status">Data demonstrasi</span>
    </div>

    <div class="card">
      <div class="card-icon">💧</div>
      <small>Kelembapan Tanah</small>
      <div class="value" id="dashMoisture">65%</div>
      <span class="card-status">Data demonstrasi</span>
    </div>

    <div class="card">
      <div class="card-icon">🌿</div>
      <small>Status Pemupukan</small>
      <div class="value" id="dashFert">OFF</div>
      <span class="card-status">Pompa pupuk</span>
    </div>

    <div class="card">
      <div class="card-icon">🚿</div>
      <small>Status Penyiraman</small>
      <div class="value" id="dashWater">OFF</div>
      <span class="card-status">Pompa air</span>
    </div>
  </div>

  <div class="panel">
    <h3>Kondisi Kelembapan Tanah</h3>
    <div class="panel-header">
      <span class="panel-description">Nilai kelembapan saat ini</span>
      <b id="dashMoistureLabel">65%</b>
    </div>
    <div class="progress-track">
      <div class="progress-fill" id="moistureBar"></div>
    </div>
    <p class="note">Nilai kelembapan merupakan data demonstrasi yang dapat diubah melalui menu Monitoring Sensor.</p>
  </div>

  <div class="panel">
    <h3>Informasi Sistem</h3>
    <p class="panel-description">
      Website ini merupakan antarmuka demonstrasi. Data dan tombol kontrol
      belum mengaktifkan perangkat fisik ESP32, sensor, relay, maupun pompa.
    </p>
  </div>
</section>

<!-- MONITORING -->
<section class="page" id="monitoring">
  <h2 class="page-heading">Monitoring Sensor dan Unsur Hara</h2>

  <div class="panel">
    <h3>Input Data Kondisi Tanah</h3>

    <div class="form-grid">
      <div class="field">
        <label for="nitrogen">Nitrogen (N) — mg/kg</label>
        <input id="nitrogen" type="number" min="0" step="any" value="45">
      </div>

      <div class="field">
        <label for="phosphorus">Fosfor (P) — mg/kg</label>
        <input id="phosphorus" type="number" min="0" step="any" value="30">
      </div>

      <div class="field">
        <label for="potassium">Kalium (K) — mg/kg</label>
        <input id="potassium" type="number" min="0" step="any" value="35">
      </div>

      <div class="field">
        <label for="soilPH">pH Tanah</label>
        <input id="soilPH" type="number" min="0" max="14" step="0.1" value="6.5">
      </div>

      <div class="field">
        <label for="soilTemperature">Suhu Tanah (°C)</label>
        <input id="soilTemperature" type="number" min="0" step="any" value="28">
      </div>

      <div class="field">
        <label for="soilMoisture">Kelembapan Tanah (%)</label>
        <input id="soilMoisture" type="number" min="0" max="100" step="any" value="65">
      </div>
    </div>

    <div class="field" style="max-width:400px;margin-bottom:17px">
      <label for="plantType">Jenis Tanaman</label>
      <input id="plantType" type="text" placeholder="Contoh: cabai, jagung, tomat">
    </div>

    <button class="btn" id="updateMonitoring">Perbarui Data</button>

    <p class="note">
      Data awal merupakan contoh demonstrasi. Masukkan hasil pengukuran
      tanah yang sebenarnya untuk memperoleh informasi yang lebih relevan.
    </p>
  </div>

  <h3 class="page-heading">Hasil Monitoring</h3>

  <div class="grid">
    <div class="data-card"><b>NITROGEN (N)</b><strong id="showN">45 mg/kg</strong></div>
    <div class="data-card"><b>FOSFOR (P)</b><strong id="showP">30 mg/kg</strong></div>
    <div class="data-card"><b>KALIUM (K)</b><strong id="showK">35 mg/kg</strong></div>
    <div class="data-card"><b>pH TANAH</b><strong id="showPH">6.5</strong></div>
    <div class="data-card"><b>SUHU TANAH</b><strong id="showTemp">28 °C</strong></div>
    <div class="data-card"><b>KELEMBAPAN</b><strong id="showMoisture">65%</strong></div>
  </div>

  <div class="panel">
    <h3>🤖 Analisis Data Menggunakan AI</h3>
    <p class="panel-description">
      Salin data monitoring beserta pertanyaan analisis. Setelah itu,
      buka ChatGPT dan tempelkan data tersebut untuk memperoleh penjelasan
      mengenai kondisi tanah, unsur hara, serta kebutuhan penyiraman.
    </p>
    <br>
    <button class="btn" id="copyAI">📋 Salin Data untuk AI</button>
    <p class="note" id="copyStatus" aria-live="polite"></p>
    <a href="https://chatgpt.com/" target="_blank" rel="noopener noreferrer" style="color:var(--green);font-size:12px;font-weight:bold">
      Buka ChatGPT ↗
    </a>
  </div>
</section>

<!-- PEMUPUKAN -->
<section class="page" id="pupuk">
  <h2 class="page-heading">Kontrol Pemupukan</h2>

  <div class="panel">
    <h3>Pengaturan Sistem Pemupukan</h3>

    <div class="control-row">
      <div>
        <b>Mode Pemupukan</b>
        <p>Pilih mode pengoperasian pompa pupuk.</p>
      </div>
      <select class="control-input" id="fertMode" style="max-width:150px">
        <option value="manual">Manual</option>
        <option value="auto">Otomatis</option>
      </select>
    </div>

    <div class="control-row">
      <div>
        <b>Status Pompa Pupuk</b>
        <p id="fertText">Pompa dalam keadaan mati.</p>
      </div>
      <button class="btn btn-off" id="fertButton">HIDUPKAN</button>
    </div>

    <div class="control-row">
      <div>
        <b>Takaran Pupuk</b>
        <p>Pengaturan volume pupuk sesuai rancangan alat.</p>
      </div>
      <input class="control-input" type="number" id="dose" min="1" value="100" style="max-width:150px">
    </div>

    <br>
    <button class="btn" id="saveFert">Simpan Pengaturan</button>

    <p class="note">
      Mode otomatis pada versi demonstrasi hanya menggambarkan status
      pengoperasian. Pengendalian pompa fisik membutuhkan koneksi ESP32 dan relay.
    </p>
  </div>
</section>

<!-- PENYIRAMAN -->
<section class="page" id="penyiraman">
  <h2 class="page-heading">Kontrol Penyiraman Air</h2>

  <div class="panel">
    <h3>Pengaturan Sistem Penyiraman</h3>

    <div class="control-row">
      <div>
        <b>Mode Penyiraman</b>
        <p>Pilih pengoperasian sistem penyiraman.</p>
      </div>
      <select class="control-input" id="waterMode" style="max-width:150px">
        <option value="auto">Otomatis</option>
        <option value="manual">Manual</option>
      </select>
    </div>

    <div class="control-row">
      <div>
        <b>Status Pompa Air</b>
        <p id="waterText">Pompa air dalam keadaan mati.</p>
      </div>
      <button class="btn btn-off" id="waterButton">HIDUPKAN</button>
    </div>

    <div class="control-row">
      <div>
        <b>Batas Kelembapan Minimum</b>
        <p>Pompa akan aktif jika kelembapan di bawah nilai ini.</p>
      </div>
      <input class="control-input" type="number" id="moistureLimit" min="0" max="100" value="40" style="max-width:150px">
    </div>

    <div class="control-row">
      <div>
        <b>Durasi Penyiraman</b>
        <p>Lama penyiraman dalam satu siklus (detik).</p>
      </div>
      <input class="control-input" type="number" id="waterDuration" min="1" value="30" style="max-width:150px">
    </div>

    <br>
    <button class="btn" id="saveWater">Simpan Pengaturan</button>

    <p class="note">
      Pada mode otomatis, sistem demonstrasi membandingkan kelembapan
      tanah dengan batas minimum yang telah ditentukan. Fitur ini belum
      mengaktifkan pompa air fisik.
    </p>
  </div>

  <div class="grid">
    <div class="card">
      <div class="card-icon">💧</div>
      <small>Kelembapan Saat Ini</small>
      <div class="value" id="waterCurrent">65%</div>
    </div>

    <div class="card">
      <div class="card-icon">🎯</div>
      <small>Batas Kelembapan</small>
      <div class="value" id="waterTarget">40%</div>
    </div>

    <div class="card">
      <div class="card-icon">🚿</div>
      <small>Rekomendasi Sistem</small>
      <div class="value" id="waterRecommendation" style="font-size:18px">Belum perlu</div>
    </div>
  </div>

  <div class="panel">
    <h3>Analisis Kondisi Penyiraman</h3>
    <p class="panel-description" id="waterMessage">
      Sistem menggunakan data kelembapan dari menu Monitoring Sensor.
    </p>
    <br>
    <button class="btn btn-light" id="checkWater">Periksa Kondisi Tanah</button>
  </div>
</section>

<!-- RIWAYAT -->
<section class="page" id="riwayat">
  <h2 class="page-heading">Riwayat Aktivitas</h2>

  <div class="panel">
    <div class="panel-header">
      <h3>Catatan Aktivitas Sistem</h3>
      <button class="btn btn-light" id="clearHistory">Hapus Riwayat</button>
    </div>

    <div class="table-wrap">
      <table>
        <thead>
          <tr>
            <th>Waktu</th>
            <th>Aktivitas</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody id="historyBody">
          <tr>
            <td>-</td>
            <td>Website dibuka</td>
            <td><span class="tag">Demonstrasi</span></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</section>

<!-- NOTIFIKASI -->
<section class="page" id="notifikasi">
  <h2 class="page-heading">Notifikasi Sistem</h2>

  <div class="panel">
    <h3>Informasi SIRAMIX</h3>
    <div id="notificationList">
      <div class="notification">🌱 Sistem SIRAMIX berhasil dibuka.</div>
      <div class="notification">📡 Monitoring sensor tersedia dalam mode demonstrasi.</div>
      <div class="notification">💧 Pengaturan penyiraman air tersedia.</div>
      <div class="notification">🌿 Pengaturan pemupukan tersedia.</div>
      <div class="notification">🤖 Data unsur hara dapat disalin untuk dianalisis melalui ChatGPT.</div>
    </div>
  </div>
</section>

<!-- TENTANG -->
<section class="page" id="about">
  <h2 class="page-heading">Tentang SIRAMIX</h2>

  <div class="hero">
    <h1>SIRAMIX 🌿</h1>
    <p>
      Smart Automatic Fertilization System merupakan inovasi yang
      mengintegrasikan pemantauan kondisi tanah, pemupukan, dan
      penyiraman untuk mendukung pertanian modern.
    </p>
  </div>

  <div class="about-grid">
    <div class="about-box">
      <h3>Latar Belakang</h3>
      <p>
        SIRAMIX dikembangkan untuk membantu mengatasi pengelolaan
        pemupukan dan penyiraman yang masih banyak dilakukan berdasarkan
        perkiraan tanpa pemantauan kondisi tanah secara terukur.
      </p>
    </div>

    <div class="about-box">
      <h3>Tujuan</h3>
      <p>
        Mengembangkan sistem pemupukan dan penyiraman otomatis yang
        membantu mengatur pemberian nutrisi serta air sesuai kondisi
        tanah dan kebutuhan tanaman.
      </p>
    </div>

    <div class="about-box">
      <h3>Teknologi</h3>
      <p>
        Sistem dirancang menggunakan mikrokontroler ESP32, sensor,
        relay, pompa air, pompa pupuk, serta perangkat pendukung lainnya.
      </p>
    </div>

    <div class="about-box">
      <h3>Manfaat</h3>
      <p>
        Membantu meningkatkan efisiensi penggunaan air dan pupuk,
        mendukung pemantauan lahan, serta mempermudah pengambilan
        keputusan dalam kegiatan budidaya tanaman.
      </p>
    </div>
  </div>
</section>

<footer>
  © 2026 SIRAMIX | Smart Automatic Fertilization System
  <br><br>
  Technology for Sustainable Agriculture 🌱
</footer>

</main>
</div>

<script>
"use strict";

/* UTILITAS */

const $ = (id) => document.getElementById(id);

function safeRead(key, fallback) {
  try {
    const value = localStorage.getItem(key);
    return value ? JSON.parse(value) : fallback;
  } catch (error) {
    return fallback;
  }
}

function safeSave(key, value) {
  try {
    localStorage.setItem(key, JSON.stringify(value));
  } catch (error) {
    console.warn("Penyimpanan browser tidak tersedia.");
  }
}

/* NAVIGASI */

const pageTitles = {
  home: "Beranda",
  dashboard: "Dashboard Monitoring",
  monitoring: "Monitoring Sensor",
  pupuk: "Kontrol Pemupukan",
  penyiraman: "Kontrol Penyiraman Air",
  riwayat: "Riwayat Aktivitas",
  notifikasi: "Notifikasi",
  about: "Tentang SIRAMIX"
};

function showPage(page) {
  document.querySelectorAll(".page").forEach(section => {
    section.classList.remove("active");
  });

  const target = $(page);
  if (!target) return;

  target.classList.add("active");

  document.querySelectorAll(".nav-item[data-page]").forEach(button => {
    button.classList.toggle("active", button.dataset.page === page);
  });

  $("pageTitle").textContent = pageTitles[page] || "SIRAMIX";
  window.scrollTo({ top: 0, behavior: "smooth" });
}

document.querySelectorAll("[data-page]").forEach(button => {
  button.addEventListener("click", () => {
    showPage(button.dataset.page);
  });
});

document.querySelectorAll("[data-go]").forEach(button => {
  button.addEventListener("click", () => {
    showPage(button.dataset.go);
  });
});

/* DATA MONITORING */

let soilData = {
  nitrogen: 45,
  phosphorus: 30,
  potassium: 35,
  soilPH: 6.5,
  soilTemperature: 28,
  soilMoisture: 65
};

function readSoilInputs() {
  const ids = [
    "nitrogen",
    "phosphorus",
    "potassium",
    "soilPH",
    "soilTemperature",
    "soilMoisture"
  ];

  const values = {};

  for (const id of ids) {
    const input = $(id);
    const value = input.value.trim();

    if (value === "" || !Number.isFinite(Number(value))) {
      alert("Lengkapi seluruh data dengan angka yang valid.");
      input.focus();
      return null;
    }

    values[id] = Number(value);

    if (values[id] < 0) {
      alert("Data tidak boleh bernilai negatif.");
      input.focus();
      return null;
    }
  }

  if (values.soilPH > 14) {
    alert("pH tanah harus berada pada rentang 0 sampai 14.");
    $("soilPH").focus();
    return null;
  }

  if (values.soilMoisture > 100) {
    alert("Kelembapan harus berada pada rentang 0 sampai 100%.");
    $("soilMoisture").focus();
    return null;
  }

  return values;
}

function renderSoilData() {
  $("showN").textContent = soilData.nitrogen + " mg/kg";
  $("showP").textContent = soilData.phosphorus + " mg/kg";
  $("showK").textContent = soilData.potassium + " mg/kg";
  $("showPH").textContent = soilData.soilPH;
  $("showTemp").textContent = soilData.soilTemperature + " °C";
  $("showMoisture").textContent = soilData.soilMoisture + "%";

  $("dashTemp").textContent = soilData.soilTemperature + "°C";
  $("dashMoisture").textContent = soilData.soilMoisture + "%";
  $("dashMoistureLabel").textContent = soilData.soilMoisture + "%";

  $("moistureBar").style.width = soilData.soilMoisture + "%";

  $("waterCurrent").textContent = soilData.soilMoisture + "%";

  safeSave("siramixSoilData", soilData);
  checkWaterCondition(false);
}

$("updateMonitoring").addEventListener("click", () => {
  const values = readSoilInputs();
  if (!values) return;

  soilData = values;
  renderSoilData();
  addHistory("Pembaruan data monitoring", "Berhasil");
  addNotification("📡 Data monitoring berhasil diperbarui.");

  alert("Data monitoring berhasil diperbarui.");
});

/* RIWAYAT DAN NOTIFIKASI */

let historyData = safeRead("siramixHistory", []);
let notificationData = safeRead("siramixNotifications", []);

function addHistory(activity, status) {
  historyData.unshift({
    time: new Date().toLocaleString("id-ID"),
    activity,
    status
  });

  historyData = historyData.slice(0, 100);
  safeSave("siramixHistory", historyData);
  renderHistory();
}

function renderHistory() {
  const body = $("historyBody");
  body.innerHTML = "";

  if (!historyData.length) {
    const row = body.insertRow();
    const cell = row.insertCell();
    cell.colSpan = 3;
    cell.textContent = "Belum ada aktivitas.";
    return;
  }

  historyData.forEach(item => {
    const row = body.insertRow();
    row.insertCell().textContent = item.time;
    row.insertCell().textContent = item.activity;

    const statusCell = row.insertCell();
    const tag = document.createElement("span");
    tag.className = "tag";
    tag.textContent = item.status;
    statusCell.appendChild(tag);
  });
}

function addNotification(message) {
  notificationData.unshift({
    time: new Date().toLocaleString("id-ID"),
    message
  });

  notificationData = notificationData.slice(0, 30);
  safeSave("siramixNotifications", notificationData);
  renderNotifications();
}

function renderNotifications() {
  const list = $("notificationList");
  list.innerHTML = "";

  if (!notificationData.length) {
    const empty = document.createElement("div");
    empty.className = "notification";
    empty.textContent = "Belum ada notifikasi.";
    list.appendChild(empty);
    return;
  }

  notificationData.forEach(item => {
    const box = document.createElement("div");
    box.className = "notification";
    box.textContent = item.time + " — " + item.message;
    list.appendChild(box);
  });
}

$("clearHistory").addEventListener("click", () => {
  if (!confirm("Hapus seluruh riwayat aktivitas?")) return;

  historyData = [];
  safeSave("siramixHistory", historyData);
  renderHistory();
});

/* PEMUPUKAN */

let fertOn = false;

function renderFert() {
  $("dashFert").textContent = fertOn ? "ON" : "OFF";
  $("fertText").textContent = fertOn
    ? "Pompa pupuk aktif (simulasi)."
    : "Pompa dalam keadaan mati.";

  $("fertButton").textContent = fertOn ? "MATIKAN" : "HIDUPKAN";
  $("fertButton").classList.toggle("btn-off", !fertOn);
}

$("fertButton").addEventListener("click", () => {
  if ($("fertMode").value === "auto") {
    alert("Mode otomatis dipilih. Kontrol manual tidak tersedia.");
    return;
  }

  fertOn = !fertOn;
  renderFert();

  const status = fertOn ? "ON (simulasi)" : "OFF (simulasi)";
  addHistory("Aktivitas pemupukan", status);
  addNotification("🌿 Status pompa pupuk berubah menjadi " + status + ".");
});

$("saveFert").addEventListener("click", () => {
  const dose = Number($("dose").value);

  if (!Number.isFinite(dose) || dose <= 0) {
    alert("Masukkan takaran pupuk yang valid.");
    return;
  }

  safeSave("siramixFertSetting", {
    mode: $("fertMode").value,
    dose
  });

  addHistory("Pengaturan takaran pupuk: " + dose, "Tersimpan");
  alert("Pengaturan pemupukan berhasil disimpan.");
});

/* PENYIRAMAN AIR */

let waterOn = false;
let waterSettings = {
  mode: "auto",
  limit: 40,
  duration: 30
};

function renderWater() {
  $("dashWater").textContent = waterOn ? "ON" : "OFF";

  $("waterText").textContent = waterOn
    ? "Pompa air aktif (simulasi)."
    : "Pompa air dalam keadaan mati.";

  $("waterButton").textContent = waterOn ? "MATIKAN" : "HIDUPKAN";
  $("waterButton").classList.toggle("btn-off", !waterOn);
}

function checkWaterCondition(record = true) {
  const moisture = soilData.soilMoisture;
  const limit = Number($("moistureLimit").value);

  $("waterCurrent").textContent = moisture + "%";
  $("waterTarget").textContent = limit + "%";

  if (!Number.isFinite(limit) || limit < 0 || limit > 100) {
    $("waterMessage").textContent = "Periksa kembali batas kelembapan.";
    return;
  }

  const needsWater = moisture < limit;

  if (needsWater) {
    $("waterRecommendation").textContent = "Perlu disiram";
    $("waterMessage").textContent =
      "Kelembapan tanah berada di bawah batas minimum. Sistem merekomendasikan penyiraman.";

    if ($("waterMode").value === "auto" && !waterOn) {
      waterOn = true;
      renderWater();

      if (record) {
        addHistory("Penyiraman otomatis", "ON (simulasi)");
        addNotification("💧 Kelembapan berada di bawah batas minimum.");
      }
    }
  } else {
    $("waterRecommendation").textContent = "Belum perlu";
    $("waterMessage").textContent =
      "Kelembapan tanah masih berada pada atau di atas batas minimum.";

    if ($("waterMode").value === "auto" && waterOn) {
      waterOn = false;
      renderWater();

      if (record) {
        addHistory("Penyiraman otomatis dihentikan", "OFF (simulasi)");
        addNotification("💧 Penyiraman dihentikan karena kelembapan mencukupi.");
      }
    }
  }
}

$("waterMode").addEventListener("change", () => {
  if ($("waterMode").value === "auto") {
    checkWaterCondition();
  } else {
    $("waterMessage").textContent =
      "Mode manual aktif. Pengguna dapat mengendalikan pompa melalui tombol.";
  }
});

$("waterButton").addEventListener("click", () => {
  if ($("waterMode").value !== "manual") {
    alert("Pilih mode Manual terlebih dahulu untuk mengontrol pompa.");
    return;
  }

  waterOn = !waterOn;
  renderWater();

  const status = waterOn ? "ON (simulasi)" : "OFF (simulasi)";
  addHistory("Aktivitas penyiraman air", status);
  addNotification("💧 Status pompa air berubah menjadi " + status + ".");
});

$("checkWater").addEventListener("click", () => {
  checkWaterCondition();
});

$("saveWater").addEventListener("click", () => {
  const limit = Number($("moistureLimit").value);
  const duration = Number($("waterDuration").value);

  if (!Number.isFinite(limit) || limit < 0 || limit > 100) {
    alert("Batas kelembapan harus berada pada rentang 0 sampai 100%.");
    return;
  }

  if (!Number.isFinite(duration) || duration <= 0) {
    alert("Durasi penyiraman harus lebih dari 0 detik.");
    return;
  }

  waterSettings = {
    mode: $("waterMode").value,
    limit,
    duration
  };

  safeSave("siramixWaterSetting", waterSettings);

  $("waterTarget").textContent = limit + "%";

  addHistory(
    "Pengaturan penyiraman: batas " + limit + "%, durasi " + duration + " detik",
    "Tersimpan"
  );

  addNotification("💧 Pengaturan penyiraman berhasil diperbarui.");

  alert("Pengaturan penyiraman berhasil disimpan.");

  if (waterSettings.mode === "auto") {
    checkWaterCondition();
  }
});

/* SALIN DATA UNTUK AI */

$("copyAI").addEventListener("click", async () => {
  const values = readSoilInputs();
  if (!values) return;

  const plant = $("plantType").value.trim() || "Belum disebutkan";

  const prompt = `DATA MONITORING TANAH SIRAMIX

Nitrogen (N): ${values.nitrogen} mg/kg
Fosfor (P): ${values.phosphorus} mg/kg
Kalium (K): ${values.potassium} mg/kg
pH tanah: ${values.soilPH}
Suhu tanah: ${values.soilTemperature} °C
Kelembapan tanah: ${values.soilMoisture}%
Jenis tanaman: ${plant}

Tolong analisis data tersebut dengan bahasa yang mudah dipahami:
1. Jelaskan kondisi setiap parameter tanah.
2. Jelaskan unsur hara yang perlu diperhatikan.
3. Berikan saran umum pengelolaan tanah dan pemupukan.
4. Analisis kebutuhan penyiraman berdasarkan kelembapan tanah.
5. Jelaskan informasi tambahan yang diperlukan sebelum menentukan dosis pupuk dan kebutuhan air.
6. Pertimbangkan jenis tanaman dan fase pertumbuhannya.
7. Jangan menentukan dosis pupuk secara pasti tanpa informasi pendukung yang memadai.`;

  const status = $("copyStatus");

  try {
    if (navigator.clipboard && window.isSecureContext) {
      await navigator.clipboard.writeText(prompt);
    } else {
      const area = document.createElement("textarea");
      area.value = prompt;
      area.style.position = "fixed";
      area.style.opacity = "0";
      document.body.appendChild(area);
      area.select();

      const success = document.execCommand("copy");
      area.remove();

      if (!success) throw new Error("Gagal menyalin");
    }

    status.textContent = "✓ Data berhasil disalin. Buka ChatGPT dan tempelkan teks tersebut.";
    addHistory("Menyalin data monitoring untuk AI", "Berhasil");
  } catch (error) {
    status.textContent = "Gagal menyalin data. Silakan coba kembali melalui browser HTTPS.";
  }
});

/* MEMUAT PENGATURAN TERSIMPAN */

function loadSavedData() {
  const savedSoil = safeRead("siramixSoilData", null);

  if (savedSoil && typeof savedSoil === "object") {
    soilData = { ...soilData, ...savedSoil };

    Object.keys(soilData).forEach(key => {
      if ($(key)) $(key).value = soilData[key];
    });
  }

  const savedWater = safeRead("siramixWaterSetting", null);

  if (savedWater) {
    waterSettings = { ...waterSettings, ...savedWater };
    $("waterMode").value = waterSettings.mode;
    $("moistureLimit").value = waterSettings.limit;
    $("waterDuration").value = waterSettings.duration;
  }

  const savedFert = safeRead("siramixFertSetting", null);

  if (savedFert) {
    $("fertMode").value = savedFert.mode || "manual";
    $("dose").value = savedFert.dose || 100;
  }

  renderSoilData();
  renderFert();
  renderWater();
  renderHistory();
  renderNotifications();
}

loadSavedData();
</script>

</body>
</html>
