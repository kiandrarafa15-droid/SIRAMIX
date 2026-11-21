
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SIRAMIX | Smart Agriculture System</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700;800&family=Manrope:wght@400;500;600;700;800&display=swap');

:root {
  --green: #174f38;
  --green2: #246b4b;
  --lime: #b9e769;
  --bg: #f3f7f2;
  --white: #ffffff;
  --text: #20372b;
  --muted: #829187;
  --border: #e6ede7;
  --red: #e56b65;
  --yellow: #e9b84d;
  --shadow: 0 10px 30px rgba(29, 75, 49, .06);
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--bg);
  color: var(--text);
}

button, input, select {
  font: inherit;
}

button {
  cursor: pointer;
}

.app {
  display: flex;
  min-height: 100vh;
}

/* SIDEBAR */
.sidebar {
  width: 250px;
  background: var(--green);
  color: white;
  padding: 28px 18px;
  display: flex;
  flex-direction: column;
  flex-shrink: 0;
  min-height: 100vh;
}

.brand {
  display: flex;
  align-items: center;
  gap: 11px;
  padding: 0 10px;
  margin-bottom: 38px;
}

.brand-icon {
  width: 43px;
  height: 43px;
  border-radius: 14px;
  background: var(--lime);
  color: var(--green);
  display: grid;
  place-items: center;
  font-size: 23px;
}

.brand h2 {
  font-family: Manrope, sans-serif;
  font-size: 21px;
  letter-spacing: 1px;
}

.brand small {
  display: block;
  font-size: 10px;
  color: #b8d0c0;
  letter-spacing: 1.5px;
}

.nav-label {
  color: #9db9a7;
  font-size: 10px;
  font-weight: 800;
  letter-spacing: 1.5px;
  padding: 0 12px;
  margin: 12px 0;
}

.nav-menu {
  display: flex;
  flex-direction: column;
  gap: 6px;
}

.nav-item {
  border: none;
  background: transparent;
  color: #d0e0d5;
  display: flex;
  align-items: center;
  gap: 13px;
  padding: 13px 14px;
  border-radius: 12px;
  text-align: left;
  font-size: 13px;
  transition: .2s;
}

.nav-item:hover,
.nav-item.active {
  background: #ffffff1b;
  color: var(--lime);
}

.nav-icon {
  font-size: 18px;
  width: 22px;
  text-align: center;
}

.sidebar-bottom {
  margin-top: auto;
  background: #ffffff12;
  border: 1px solid #ffffff1c;
  padding: 15px;
  border-radius: 14px;
}

.sidebar-bottom p {
  font-size: 11px;
  color: #c2d8c9;
  line-height: 1.6;
}

.sidebar-bottom strong {
  display: block;
  color: var(--lime);
  font-size: 13px;
  margin-bottom: 5px;
}

/* MAIN */
.main {
  flex: 1;
  min-width: 0;
  padding: 28px 34px 45px;
}

.topbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 15px;
  margin-bottom: 28px;
}

.page-title h1 {
  font-family: Manrope, sans-serif;
  font-size: 25px;
  font-weight: 800;
}

.page-title p {
  color: var(--muted);
  font-size: 12px;
  margin-top: 5px;
}

.top-actions {
  display: flex;
  align-items: center;
  gap: 12px;
}

.date-label {
  background: white;
  border: 1px solid var(--border);
  padding: 10px 14px;
  border-radius: 11px;
  color: var(--muted);
  font-size: 12px;
}

.profile {
  width: 39px;
  height: 39px;
  border-radius: 50%;
  background: #dcebcf;
  color: var(--green);
  display: grid;
  place-items: center;
  font-weight: 800;
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

/* HERO */
.hero {
  background: linear-gradient(110deg, #174f38, #2e7651);
  color: white;
  padding: 29px 32px;
  border-radius: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  overflow: hidden;
  position: relative;
  margin-bottom: 23px;
}

.hero::after {
  content: "🌱";
  position: absolute;
  right: 10%;
  top: -35px;
  font-size: 150px;
  opacity: .12;
  transform: rotate(-15deg);
}

.hero-content {
  position: relative;
  z-index: 1;
}

.hero-tag {
  display: inline-block;
  color: var(--lime);
  background: #ffffff17;
  padding: 6px 10px;
  border-radius: 20px;
  font-size: 10px;
  font-weight: 800;
  letter-spacing: 1px;
  margin-bottom: 12px;
}

.hero h2 {
  font-family: Manrope, sans-serif;
  font-size: 25px;
  margin-bottom: 9px;
}

.hero p {
  font-size: 12px;
  color: #d2e5d8;
  max-width: 510px;
  line-height: 1.7;
}

.hero-button {
  position: relative;
  z-index: 1;
  border: none;
  background: var(--lime);
  color: var(--green);
  font-weight: 800;
  font-size: 12px;
  padding: 12px 17px;
  border-radius: 10px;
  white-space: nowrap;
}

/* CARDS */
.grid {
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  gap: 16px;
  margin-bottom: 22px;
}

.card {
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 19px;
  box-shadow: var(--shadow);
}

.metric-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 15px;
}

.metric-icon {
  width: 38px;
  height: 38px;
  display: grid;
  place-items: center;
  border-radius: 12px;
  background: #edf6e8;
  font-size: 19px;
}

.metric-name {
  font-size: 11px;
  color: var(--muted);
  font-weight: 700;
}

.metric-value {
  font-family: Manrope, sans-serif;
  font-size: 26px;
  font-weight: 800;
}

.metric-unit {
  font-size: 12px;
  color: var(--muted);
  font-weight: 500;
}

.metric-note {
  font-size: 10px;
  color: var(--muted);
  margin-top: 8px;
}

.section-heading {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
  margin: 26px 0 15px;
}

.section-heading h2 {
  font-family: Manrope, sans-serif;
  font-size: 16px;
}

.section-heading p {
  font-size: 11px;
  color: var(--muted);
  margin-top: 4px;
}

/* PANEL */
.two-column {
  display: grid;
  grid-template-columns: 1.4fr 1fr;
  gap: 17px;
}

.panel {
  background: white;
  border: 1px solid var(--border);
  border-radius: 16px;
  padding: 21px;
  box-shadow: var(--shadow);
  min-width: 0;
}

.panel h3 {
  font-family: Manrope, sans-serif;
  font-size: 14px;
  margin-bottom: 5px;
}

.panel-subtitle {
  color: var(--muted);
  font-size: 11px;
  margin-bottom: 19px;
}

.status-row {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
  padding: 12px 0;
  border-bottom: 1px solid var(--border);
}

.status-row:last-child {
  border-bottom: none;
}

.status-row span:first-child {
  font-size: 12px;
}

.status-pill {
  padding: 5px 9px;
  border-radius: 20px;
  background: #edf7e8;
  color: #4e8a47;
  font-size: 10px;
  font-weight: 800;
}

.status-pill.warning {
  background: #fff4dc;
  color: #b17d21;
}

.status-pill.danger {
  background: #ffeded;
  color: #c45c56;
}

/* FORM */
.form-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 15px;
}

.field {
  display: flex;
  flex-direction: column;
  gap: 7px;
}

.field label {
  font-size: 11px;
  color: #607267;
  font-weight: 700;
}

.field input,
.field select {
  width: 100%;
  border: 1px solid var(--border);
  border-radius: 10px;
  padding: 12px;
  outline: none;
  background: #fbfdfb;
  color: var(--text);
  font-size: 12px;
}

.field input:focus,
.field select:focus {
  border-color: #7ebd69;
  box-shadow: 0 0 0 3px #b9e76930;
}

.primary-btn,
.secondary-btn,
.danger-btn {
  border: none;
  border-radius: 10px;
  padding: 12px 17px;
  font-size: 12px;
  font-weight: 800;
  transition: .2s;
}

.primary-btn {
  background: var(--green);
  color: white;
}

.primary-btn:hover {
  background: var(--green2);
}

.secondary-btn {
  background: #edf5e8;
  color: var(--green);
}

.danger-btn {
  background: #ffeded;
  color: #bb5650;
}

.form-actions {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 20px;
}

/* MONITORING */
.monitor-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 15px;
}

.monitor-card {
  background: white;
  border: 1px solid var(--border);
  border-radius: 15px;
  padding: 18px;
}

.monitor-card .label {
  font-size: 11px;
  color: var(--muted);
}

.monitor-card .value {
  font-family: Manrope, sans-serif;
  font-size: 24px;
  font-weight: 800;
  margin: 8px 0;
}

.progress {
  width: 100%;
  height: 7px;
  background: #edf2ed;
  border-radius: 20px;
  overflow: hidden;
  margin-top: 12px;
}

.progress-bar {
  height: 100%;
  width: 0;
  background: #83bd65;
  border-radius: 20px;
  transition: width .3s;
}

/* CONTROL */
.control-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 17px;
}

.control-card {
  background: white;
  border: 1px solid var(--border);
  border-radius: 17px;
  padding: 22px;
  box-shadow: var(--shadow);
}

.control-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
  margin-bottom: 15px;
}

.control-header h3 {
  font-family: Manrope, sans-serif;
  font-size: 15px;
}

.control-icon {
  width: 42px;
  height: 42px;
  border-radius: 13px;
  background: #edf6e8;
  display: grid;
  place-items: center;
  font-size: 21px;
}

.control-description {
  color: var(--muted);
  font-size: 11px;
  line-height: 1.7;
  margin-bottom: 18px;
}

.control-status {
  background: #f5f8f4;
  border-radius: 12px;
  padding: 14px;
  margin: 14px 0;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
  font-size: 12px;
}

.switch-row {
  display: flex;
  align-items: center;
  gap: 9px;
  font-size: 11px;
  color: var(--muted);
  margin: 14px 0;
}

.switch-row input {
  accent-color: var(--green);
}

.control-buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 9px;
}

/* TABLE */
.table-wrap {
  width: 100%;
  overflow-x: auto;
}

table {
  width: 100%;
  border-collapse: collapse;
  min-width: 600px;
}

th, td {
  padding: 13px 12px;
  text-align: left;
  border-bottom: 1px solid var(--border);
  font-size: 11px;
}

th {
  color: var(--muted);
  font-weight: 800;
  background: #f8faf7;
}

td {
  color: #43584a;
}

/* NOTIFICATION */
.notification {
  display: flex;
  gap: 13px;
  padding: 15px 0;
  border-bottom: 1px solid var(--border);
}

.notification:last-child {
  border-bottom: none;
}

.notification-icon {
  width: 37px;
  height: 37px;
  flex-shrink: 0;
  border-radius: 11px;
  background: #edf6e8;
  display: grid;
  place-items: center;
}

.notification h4 {
  font-size: 12px;
  margin-bottom: 4px;
}

.notification p {
  font-size: 11px;
  color: var(--muted);
  line-height: 1.6;
}

/* ABOUT */
.about-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 18px;
}

.about-highlight {
  background: linear-gradient(135deg, #174f38, #367c52);
  color: white;
  border-radius: 17px;
  padding: 25px;
}

.about-highlight h2 {
  font-family: Manrope, sans-serif;
  font-size: 23px;
  margin-bottom: 12px;
}

.about-highlight p {
  font-size: 12px;
  line-height: 1.8;
  color: #d4e5d9;
}

.about-text {
  font-size: 12px;
  line-height: 1.9;
  color: #65766b;
}

.feature-list {
  display: grid;
  gap: 12px;
  margin-top: 17px;
}

.feature-item {
  display: flex;
  gap: 10px;
  font-size: 12px;
  align-items: center;
}

.feature-item span:first-child {
  width: 27px;
  height: 27px;
  background: #edf6e8;
  display: grid;
  place-items: center;
  border-radius: 8px;
}

/* EMPTY */
.empty {
  text-align: center;
  color: var(--muted);
  font-size: 12px;
  padding: 28px 10px;
}

.toast {
  position: fixed;
  bottom: 22px;
  right: 22px;
  background: var(--green);
  color: white;
  padding: 13px 18px;
  border-radius: 11px;
  font-size: 12px;
  box-shadow: var(--shadow);
  opacity: 0;
  transform: translateY(10px);
  pointer-events: none;
  transition: .25s;
  z-index: 99;
}

.toast.show {
  opacity: 1;
  transform: translateY(0);
}

.footer {
  text-align: center;
  font-size: 10px;
  color: #9aa99e;
  margin-top: 35px;
}

/* MOBILE */
.mobile-menu {
  display: none;
  border: none;
  background: var(--green);
  color: white;
  border-radius: 9px;
  padding: 9px 12px;
  font-size: 17px;
}

@media (max-width: 1050px) {
  .grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 800px) {
  .sidebar {
    position: fixed;
    z-index: 50;
    left: -260px;
    top: 0;
    height: 100vh;
    transition: .25s;
  }

  .sidebar.open {
    left: 0;
  }

  .main {
    padding: 20px 16px 35px;
    width: 100%;
  }

  .mobile-menu {
    display: block;
  }

  .two-column,
  .control-grid,
  .about-grid {
    grid-template-columns: 1fr;
  }

  .form-grid,
  .monitor-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .hero {
    padding: 24px;
  }

  .hero h2 {
    font-size: 21px;
  }
}

@media (max-width: 520px) {
  .topbar {
    align-items: flex-start;
  }

  .page-title h1 {
    font-size: 20px;
  }

  .date-label {
    display: none;
  }

  .grid {
    grid-template-columns: 1fr 1fr;
    gap: 10px;
  }

  .card {
    padding: 14px;
  }

  .metric-value {
    font-size: 21px;
  }

  .form-grid,
  .monitor-grid {
    grid-template-columns: 1fr;
  }

  .hero {
    display: block;
  }

  .hero-button {
    margin-top: 17px;
  }
}
</style>
</head>

<body>
<div class="app">

  <aside class="sidebar" id="sidebar">
    <div class="brand">
      <div class="brand-icon">🌱</div>
      <div>
        <h2>SIRAMIX</h2>
        <small>SMART AGRICULTURE</small>
      </div>
    </div>

    <div class="nav-label">MENU UTAMA</div>

    <nav class="nav-menu">
      <button class="nav-item active" data-page="beranda">
        <span class="nav-icon">⌂</span> Beranda
      </button>
      <button class="nav-item" data-page="dashboard">
        <span class="nav-icon">▦</span> Dashboard
      </button>
      <button class="nav-item" data-page="monitoring">
        <span class="nav-icon">◉</span> Monitoring Tanah
      </button>
      <button class="nav-item" data-page="pemupukan">
        <span class="nav-icon">♧</span> Pemupukan
      </button>
      <button class="nav-item" data-page="penyiraman">
        <span class="nav-icon">💧</span> Penyiraman
      </button>
    </nav>

    <div class="nav-label">LAINNYA</div>

    <nav class="nav-menu">
      <button class="nav-item" data-page="riwayat">
        <span class="nav-icon">◷</span> Riwayat Data
      </button>
      <button class="nav-item" data-page="notifikasi">
        <span class="nav-icon">♢</span> Notifikasi
      </button>
      <button class="nav-item" data-page="tentang">
        <span class="nav-icon">ⓘ</span> Tentang SIRAMIX
      </button>
    </nav>

    <div class="sidebar-bottom">
      <strong>🌿 SIRAMIX SYSTEM</strong>
      <p>Sistem pemantauan dan pengelolaan pertanian berbasis teknologi.</p>
    </div>
  </aside>

  <main class="main">

    <header class="topbar">
      <div style="display:flex;align-items:center;gap:13px">
        <button class="mobile-menu" id="mobileMenu">☰</button>
        <div class="page-title">
          <h1 id="pageHeading">Beranda</h1>
          <p>Sistem informasi pertanian cerdas SIRAMIX</p>
        </div>
      </div>

      <div class="top-actions">
        <div class="date-label" id="currentDate">Memuat tanggal...</div>
        <div class="profile">S</div>
      </div>
    </header>

    <!-- BERANDA -->
    <section class="page active" id="page-beranda">

      <div class="hero">
        <div class="hero-content">
          <span class="hero-tag">SMART FARMING TECHNOLOGY</span>
          <h2>Kelola Lahan Lebih Cerdas<br> Bersama SIRAMIX.</h2>
          <p>
            SIRAMIX merupakan sistem pertanian cerdas yang dirancang untuk
            membantu pemantauan kondisi tanah serta pengelolaan pemupukan
            dan penyiraman tanaman secara lebih terarah.
          </p>
          <button class="hero-button" onclick="goPage('dashboard')">
            Buka Dashboard →
          </button>
        </div>
      </div>

      <div class="grid">
        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Nitrogen (N)</span>
            <div class="metric-icon">🌿</div>
          </div>
          <div class="metric-value"><span id="homeN">0</span> <span class="metric-unit">mg/kg</span></div>
          <div class="metric-note">Data pengukuran terakhir</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Fosfor (P)</span>
            <div class="metric-icon">🧪</div>
          </div>
          <div class="metric-value"><span id="homeP">0</span> <span class="metric-unit">mg/kg</span></div>
          <div class="metric-note">Data pengukuran terakhir</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Kalium (K)</span>
            <div class="metric-icon">🌱</div>
          </div>
          <div class="metric-value"><span id="homeK">0</span> <span class="metric-unit">mg/kg</span></div>
          <div class="metric-note">Data pengukuran terakhir</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Kelembapan</span>
            <div class="metric-icon">💧</div>
          </div>
          <div class="metric-value"><span id="homeMoisture">0</span> <span class="metric-unit">%</span></div>
          <div class="metric-note">Kadar air tanah</div>
        </div>
      </div>

      <div class="two-column">
        <div class="panel">
          <h3>Ringkasan Sistem</h3>
          <p class="panel-subtitle">Status pengelolaan lahan berdasarkan data terakhir</p>

          <div class="status-row">
            <span>Monitoring tanah</span>
            <span class="status-pill" id="homeMonitorStatus">Belum ada data</span>
          </div>
          <div class="status-row">
            <span>Sistem pemupukan</span>
            <span class="status-pill" id="homeFertilizerStatus">Nonaktif</span>
          </div>
          <div class="status-row">
            <span>Sistem penyiraman</span>
            <span class="status-pill" id="homeWaterStatus">Nonaktif</span>
          </div>
        </div>

        <div class="panel">
          <h3>Informasi SIRAMIX</h3>
          <p class="panel-subtitle">Fungsi utama sistem</p>
          <div class="status-row">
            <span>🌱 Pemantauan unsur hara</span>
          </div>
          <div class="status-row">
            <span>💧 Pengelolaan kebutuhan air</span>
          </div>
          <div class="status-row">
            <span>⚙️ Pengaturan pemupukan</span>
          </div>
          <div class="status-row">
            <span>🤖 Bantuan analisis berbasis AI</span>
          </div>
        </div>
      </div>
    </section>

    <!-- DASHBOARD -->
    <section class="page" id="page-dashboard">

      <div class="section-heading">
        <div>
          <h2>Dashboard Pertanian</h2>
          <p>Ringkasan parameter kondisi tanah</p>
        </div>
        <button class="secondary-btn" onclick="goPage('monitoring')">Input Data +</button>
      </div>

      <div class="grid">
        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Nitrogen (N)</span>
            <div class="metric-icon">🌿</div>
          </div>
          <div class="metric-value"><span id="dashN">0</span> <span class="metric-unit">mg/kg</span></div>
          <div class="metric-note">Unsur hara nitrogen</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Fosfor (P)</span>
            <div class="metric-icon">🧪</div>
          </div>
          <div class="metric-value"><span id="dashP">0</span> <span class="metric-unit">mg/kg</span></div>
          <div class="metric-note">Unsur hara fosfor</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Kalium (K)</span>
            <div class="metric-icon">🌱</div>
          </div>
          <div class="metric-value"><span id="dashK">0</span> <span class="metric-unit">mg/kg</span></div>
          <div class="metric-note">Unsur hara kalium</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">pH Tanah</span>
            <div class="metric-icon">⚗️</div>
          </div>
          <div class="metric-value"><span id="dashPH">0</span></div>
          <div class="metric-note">Tingkat keasaman tanah</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Suhu Tanah</span>
            <div class="metric-icon">🌡️</div>
          </div>
          <div class="metric-value"><span id="dashTemp">0</span> <span class="metric-unit">°C</span></div>
          <div class="metric-note">Temperatur tanah</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Kelembapan</span>
            <div class="metric-icon">💧</div>
          </div>
          <div class="metric-value"><span id="dashMoisture">0</span> <span class="metric-unit">%</span></div>
          <div class="metric-note">Kadar air tanah</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Pemupukan</span>
            <div class="metric-icon">♧</div>
          </div>
          <div class="metric-value" style="font-size:19px" id="dashFertilizer">Nonaktif</div>
          <div class="metric-note">Status simulasi pemupukan</div>
        </div>

        <div class="card">
          <div class="metric-top">
            <span class="metric-name">Penyiraman</span>
            <div class="metric-icon">🚿</div>
          </div>
          <div class="metric-value" style="font-size:19px" id="dashWater">Nonaktif</div>
          <div class="metric-note">Status simulasi penyiraman</div>
        </div>
      </div>

      <div class="panel">
        <h3>Informasi Pembacaan</h3>
        <p class="panel-subtitle">Kondisi berdasarkan angka yang dimasukkan pengguna</p>
        <div id="dashboardAnalysis" class="about-text">
          Belum terdapat data pengukuran. Silakan masukkan data melalui menu Monitoring Tanah.
        </div>
      </div>
    </section>

    <!-- MONITORING -->
    <section class="page" id="page-monitoring">

      <div class="section-heading">
        <div>
          <h2>Monitoring Kondisi Tanah</h2>
          <p>Masukkan hasil pengukuran parameter tanah</p>
        </div>
      </div>

      <div class="panel">
        <h3>Input Data Pengukuran</h3>
        <p class="panel-subtitle">Masukkan angka sesuai hasil pembacaan sensor atau pengukuran lapangan</p>

        <form id="monitorForm">
          <div class="form-grid">
            <div class="field">
              <label for="inputN">Nitrogen (N) - mg/kg</label>
              <input id="inputN" type="number" min="0" step="any" placeholder="Contoh: 45" required>
            </div>

            <div class="field">
              <label for="inputP">Fosfor (P) - mg/kg</label>
              <input id="inputP" type="number" min="0" step="any" placeholder="Contoh: 30" required>
            </div>

            <div class="field">
              <label for="inputK">Kalium (K) - mg/kg</label>
              <input id="inputK" type="number" min="0" step="any" placeholder="Contoh: 50" required>
            </div>

            <div class="field">
              <label for="inputPH">pH Tanah</label>
              <input id="inputPH" type="number" min="0" max="14" step="0.1" placeholder="Contoh: 6.5" required>
            </div>

            <div class="field">
              <label for="inputTemp">Suhu Tanah (°C)</label>
              <input id="inputTemp" type="number" min="-20" max="100" step="0.1" placeholder="Contoh: 28" required>
            </div>

            <div class="field">
              <label for="inputMoisture">Kelembapan Tanah (%)</label>
              <input id="inputMoisture" type="number" min="0" max="100" step="any" placeholder="Contoh: 60" required>
            </div>
          </div>

          <div class="form-actions">
            <button type="submit" class="primary-btn">Simpan Data Monitoring</button>
            <button type="reset" class="secondary-btn">Reset Form</button>
          </div>
        </form>
      </div>

      <div class="section-heading">
        <div>
          <h2>Parameter Terukur</h2>
          <p>Nilai terbaru yang tersimpan pada sistem</p>
        </div>
      </div>

      <div class="monitor-grid">
        <div class="monitor-card">
          <div class="label">Nitrogen (N)</div>
          <div class="value" id="monitorN">0 mg/kg</div>
          <div class="progress"><div class="progress-bar" id="barN"></div></div>
        </div>
        <div class="monitor-card">
          <div class="label">Fosfor (P)</div>
          <div class="value" id="monitorP">0 mg/kg</div>
          <div class="progress"><div class="progress-bar" id="barP"></div></div>
        </div>
        <div class="monitor-card">
          <div class="label">Kalium (K)</div>
          <div class="value" id="monitorK">0 mg/kg</div>
          <div class="progress"><div class="progress-bar" id="barK"></div></div>
        </div>
        <div class="monitor-card">
          <div class="label">pH Tanah</div>
          <div class="value" id="monitorPH">0</div>
          <div class="progress"><div class="progress-bar" id="barPH"></div></div>
        </div>
        <div class="monitor-card">
          <div class="label">Suhu Tanah</div>
          <div class="value" id="monitorTemp">0 °C</div>
          <div class="progress"><div class="progress-bar" id="barTemp"></div></div>
        </div>
        <div class="monitor-card">
          <div class="label">Kelembapan Tanah</div>
          <div class="value" id="monitorMoisture">0%</div>
          <div class="progress"><div class="progress-bar" id="barMoisture"></div></div>
        </div>
      </div>

      <div class="section-heading">
        <div>
          <h2>Analisis Data dengan AI</h2>
          <p>Salin hasil monitoring untuk digunakan dalam konsultasi AI</p>
        </div>
      </div>

      <div class="panel">
        <h3>Asisten Analisis Pertanian</h3>
        <p class="panel-subtitle">
          Data dapat disalin dan digunakan sebagai konteks pertanyaan mengenai kondisi tanah.
        </p>
        <div class="form-actions">
          <button class="primary-btn" onclick="copySoilData()">Salin Data Monitoring</button>
          <button class="secondary-btn" onclick="openAI()">Buka ChatGPT ↗</button>
        </div>
        <p class="metric-note" style="margin-top:13px">
          Hasil analisis AI merupakan saran awal. Keputusan pemupukan dan penyiraman tetap perlu disesuaikan dengan jenis tanaman, fase pertumbuhan, kondisi lahan, dan rekomendasi agronomis.
        </p>
      </div>
    </section>

    <!-- PEMUPUKAN -->
    <section class="page" id="page-pemupukan">

      <div class="section-heading">
        <div>
          <h2>Pengelolaan Pemupukan</h2>
          <p>Pengaturan sistem pemupukan pada lahan pertanian</p>
        </div>
      </div>

      <div class="control-grid">

        <div class="control-card">
          <div class="control-header">
            <h3>Kontrol Pemupukan</h3>
            <div class="control-icon">🌿</div>
          </div>

          <p class="control-description">
            Atur status pemupukan secara manual atau gunakan mode otomatis sebagai simulasi pengendalian sistem.
          </p>

          <div class="control-status">
            <span>Status sistem</span>
            <strong id="fertilizerStatus">NONAKTIF</strong>
          </div>

          <div class="field">
            <label for="fertilizerMode">Mode pengoperasian</label>
            <select id="fertilizerMode">
              <option value="manual">Manual</option>
              <option value="automatic">Otomatis (simulasi)</option>
            </select>
          </div>

          <div class="field" style="margin-top:13px">
            <label for="fertilizerDose">Dosis pupuk (ml)</label>
            <input type="number" id="fertilizerDose" min="0.1" step="any" value="100">
          </div>

          <div class="control-buttons" style="margin-top:18px">
            <button class="primary-btn" id="fertilizerOn">Aktifkan</button>
            <button class="danger-btn" id="fertilizerOff">Matikan</button>
          </div>
        </div>

        <div class="control-card">
          <div class="control-header">
            <h3>Informasi Pemupukan</h3>
            <div class="control-icon">🧪</div>
          </div>

          <p class="control-description">
            Pemupukan perlu mempertimbangkan kandungan unsur hara tanah, jenis tanaman, kebutuhan nutrisi, dan fase pertumbuhan.
          </p>

          <div class="status-row">
            <span>Data N</span>
            <strong id="fertN">0 mg/kg</strong>
          </div>
          <div class="status-row">
            <span>Data P</span>
            <strong id="fertP">0 mg/kg</strong>
          </div>
          <div class="status-row">
            <span>Data K</span>
            <strong id="fertK">0 mg/kg</strong>
          </div>

          <div class="form-actions">
            <button class="secondary-btn" onclick="copySoilData()">Salin Data Tanah</button>
            <button class="secondary-btn" onclick="openAI()">Konsultasi AI ↗</button>
          </div>
        </div>

      </div>

      <div class="panel" style="margin-top:18px">
        <h3>Catatan Penggunaan</h3>
        <p class="about-text">
          Pengaturan pemupukan pada halaman ini hanya berupa simulasi antarmuka website.
          Sistem belum terhubung dengan pompa pupuk, sensor fisik, atau mikrokontroler.
          Penentuan dosis pupuk tidak dapat dilakukan hanya berdasarkan satu angka N, P, dan K;
          diperlukan informasi jenis tanaman, kondisi tanah, serta rekomendasi pemupukan yang sesuai.
        </p>
      </div>
    </section>

    <!-- PENYIRAMAN -->
    <section class="page" id="page-penyiraman">

      <div class="section-heading">
        <div>
          <h2>Pengelolaan Penyiraman</h2>
          <p>Pengaturan simulasi sistem penyiraman tanaman</p>
        </div>
      </div>

      <div class="control-grid">

        <div class="control-card">
          <div class="control-header">
            <h3>Kontrol Penyiraman</h3>
            <div class="control-icon">💧</div>
          </div>

          <p class="control-description">
            Sistem dapat diatur menggunakan mode manual atau mode otomatis berdasarkan nilai kelembapan tanah yang dimasukkan.
          </p>

          <div class="control-status">
            <span>Status pompa</span>
            <strong id="waterStatus">NONAKTIF</strong>
          </div>

          <div class="field">
            <label for="waterMode">Mode penyiraman</label>
            <select id="waterMode">
              <option value="manual">Manual</option>
              <option value="automatic">Otomatis (simulasi)</option>
            </select>
          </div>

          <div class="field" style="margin-top:13px">
            <label for="moistureThreshold">Batas kelembapan minimum (%)</label>
            <input type="number" id="moistureThreshold" min="1" max="99" value="40">
          </div>

          <div class="field" style="margin-top:13px">
            <label for="waterDuration">Durasi simulasi penyiraman (detik)</label>
            <input type="number" id="waterDuration" min="1" max="3600" value="10">
          </div>

          <div class="control-buttons" style="margin-top:18px">
            <button class="primary-btn" id="waterOn">Nyalakan Pompa</button>
            <button class="danger-btn" id="waterOff">Matikan Pompa</button>
          </div>
        </div>

        <div class="control-card">
          <div class="control-header">
            <h3>Kondisi Kelembapan Tanah</h3>
            <div class="control-icon">🌧️</div>
          </div>

          <p class="control-description">
            Nilai kelembapan digunakan sebagai dasar simulasi pengambilan keputusan penyiraman.
          </p>

          <div style="text-align:center;padding:15px 0">
            <div style="font-family:Manrope;font-size:43px;font-weight:800;color:var(--green)">
              <span id="waterMoisture">0</span><span style="font-size:17px">%</span>
            </div>
            <div class="metric-note">Kelembapan tanah terakhir</div>
          </div>

          <div class="progress" style="height:11px">
            <div class="progress-bar" id="waterProgress"></div>
          </div>

          <div class="status-row" style="margin-top:15px">
            <span>Batas minimum</span>
            <strong id="thresholdDisplay">40%</strong>
          </div>

          <div class="status-row">
            <span>Kondisi penyiraman</span>
            <strong id="waterRecommendation">Belum diketahui</strong>
          </div>
        </div>

      </div>

      <div class="panel" style="margin-top:18px">
        <h3>Prinsip Kerja Penyiraman Otomatis</h3>
        <p class="about-text">
          Pada konsep SIRAMIX, nilai kelembapan tanah menjadi salah satu dasar pengendalian penyiraman.
          Apabila nilai kelembapan berada di bawah batas yang ditentukan, sistem simulasi akan mengaktifkan pompa.
          Ketika durasi simulasi berakhir atau kelembapan telah mencapai batas yang ditetapkan, pompa simulasi akan dimatikan.
          Pada penerapan perangkat sebenarnya, pengendalian ini memerlukan sensor kelembapan, mikrokontroler,
          relay yang sesuai, pompa, sumber daya, dan instalasi perpipaan.
        </p>
      </div>
    </section>

    <!-- RIWAYAT -->
    <section class="page" id="page-riwayat">

      <div class="section-heading">
        <div>
          <h2>Riwayat Monitoring</h2>
          <p>Catatan data pengukuran yang telah disimpan</p>
        </div>
        <button class="danger-btn" onclick="clearHistory()">Hapus Riwayat</button>
      </div>

      <div class="panel">
        <div class="table-wrap">
          <table>
            <thead>
              <tr>
                <th>Waktu</th>
                <th>N</th>
                <th>P</th>
                <th>K</th>
                <th>pH</th>
                <th>Suhu</th>
                <th>Kelembapan</th>
              </tr>
            </thead>
            <tbody id="historyBody">
              <tr><td colspan="7" class="empty">Belum ada data monitoring.</td></tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- NOTIFIKASI -->
    <section class="page" id="page-notifikasi">

      <div class="section-heading">
        <div>
          <h2>Notifikasi Sistem</h2>
          <p>Informasi aktivitas dan perubahan status sistem</p>
        </div>
        <button class="secondary-btn" onclick="clearNotifications()">Bersihkan</button>
      </div>

      <div class="panel">
        <div id="notificationList">
          <div class="empty">Belum ada notifikasi.</div>
        </div>
      </div>
    </section>

    <!-- TENTANG -->
    <section class="page" id="page-tentang">

      <div class="section-heading">
        <div>
          <h2>Tentang SIRAMIX</h2>
          <p>Mengenal sistem pertanian cerdas</p>
        </div>
      </div>

      <div class="about-grid">
        <div class="about-highlight">
          <div style="font-size:35px;margin-bottom:14px">🌱</div>
          <h2>SIRAMIX</h2>
          <p>
            Smart Agriculture System merupakan konsep inovasi teknologi pertanian
            yang mengintegrasikan pemantauan kondisi tanah dengan pengelolaan
            pemupukan dan penyiraman tanaman.
          </p>
        </div>

        <div class="panel">
          <h3>Tujuan Pengembangan</h3>
          <p class="about-text">
            SIRAMIX dirancang untuk membantu pengguna memperoleh informasi kondisi tanah
            dan mengelola kegiatan budidaya secara lebih terarah. Sistem ini diharapkan
            dapat mendukung penggunaan air dan pupuk secara lebih efisien melalui
            pemantauan parameter tanah.
          </p>
        </div>
      </div>

      <div class="section-heading">
        <div>
          <h2>Fitur Utama</h2>
          <p>Komponen fungsi yang tersedia pada website</p>
        </div>
      </div>

      <div class="panel">
        <div class="feature-list">
          <div class="feature-item"><span>🌿</span> Pemantauan unsur hara N, P, dan K.</div>
          <div class="feature-item"><span>⚗️</span> Pemantauan pH tanah dan suhu tanah.</div>
          <div class="feature-item"><span>💧</span> Pemantauan kelembapan dan simulasi penyiraman.</div>
          <div class="feature-item"><span>♧</span> Pengaturan simulasi pemupukan.</div>
          <div class="feature-item"><span>🤖</span> Integrasi konsultasi melalui ChatGPT.</div>
          <div class="feature-item"><span>📊</span> Penyimpanan riwayat data monitoring.</div>
        </div>
      </div>

      <div class="panel" style="margin-top:18px">
        <h3>Catatan Pengembangan</h3>
        <p class="about-text">
          Website ini merupakan prototipe antarmuka SIRAMIX. Seluruh input, indikator,
          dan kontrol pompa pada versi ini berjalan sebagai simulasi di browser.
          Website belum melakukan komunikasi langsung dengan ESP32, sensor, relay,
          pompa, maupun perangkat keras lainnya. Integrasi perangkat memerlukan
          pengembangan sistem komunikasi dan pemrograman mikrokontroler tersendiri.
        </p>
      </div>
    </section>

    <div class="footer">
      © 2026 SIRAMIX — Smart Agriculture System
    </div>

  </main>
</div>

<div class="toast" id="toast">Berhasil!</div>

<script>
/* =========================
   DATA DAN PENYIMPANAN
========================= */

const defaultData = {
  n: 0,
  p: 0,
  k: 0,
  ph: 0,
  temp: 0,
  moisture: 0
};

let data = { ...defaultData };
let history = [];
let notifications = [];
let fertilizerActive = false;
let waterActive = false;
let waterTimer = null;

function loadStorage() {
  try {
    const savedData = localStorage.getItem("siramix_data");
    const savedHistory = localStorage.getItem("siramix_history");
    const savedNotifications = localStorage.getItem("siramix_notifications");

    if (savedData) data = { ...defaultData, ...JSON.parse(savedData) };
    if (savedHistory) history = JSON.parse(savedHistory);
    if (savedNotifications) notifications = JSON.parse(savedNotifications);
  } catch (error) {
    console.warn("Data penyimpanan tidak dapat dibaca.", error);
  }
}

function saveStorage() {
  try {
    localStorage.setItem("siramix_data", JSON.stringify(data));
    localStorage.setItem("siramix_history", JSON.stringify(history));
    localStorage.setItem("siramix_notifications", JSON.stringify(notifications));
  } catch (error) {
    showToast("Penyimpanan browser tidak tersedia.");
  }
}

/* =========================
   NAVIGASI
========================= */

const pageNames = {
  beranda: "Beranda",
  dashboard: "Dashboard",
  monitoring: "Monitoring Tanah",
  pemupukan: "Pemupukan",
  penyiraman: "Penyiraman",
  riwayat: "Riwayat Data",
  notifikasi: "Notifikasi",
  tentang: "Tentang SIRAMIX"
};

function goPage(page) {
  document.querySelectorAll(".page").forEach(item => {
    item.classList.remove("active");
  });

  document.querySelectorAll(".nav-item").forEach(item => {
    item.classList.remove("active");
  });

  const target = document.getElementById("page-" + page);
  if (target) target.classList.add("active");

  const nav = document.querySelector('[data-page="' + page + '"]');
  if (nav) nav.classList.add("active");

  document.getElementById("pageHeading").textContent =
    pageNames[page] || "SIRAMIX";

  document.getElementById("sidebar").classList.remove("open");

  if (page === "riwayat") renderHistory();
  if (page === "notifikasi") renderNotifications();
  if (page === "dashboard") updateDashboard();
}

document.querySelectorAll(".nav-item").forEach(button => {
  button.addEventListener("click", () => {
    goPage(button.dataset.page);
  });
});

document.getElementById("mobileMenu").addEventListener("click", () => {
  document.getElementById("sidebar").classList.toggle("open");
});

/* =========================
   TANGGAL DAN TOAST
========================= */

function updateDate() {
  const now = new Date();
  document.getElementById("currentDate").textContent =
    now.toLocaleDateString("id-ID", {
      day: "numeric",
      month: "long",
      year: "numeric"
    });
}

function showToast(message) {
  const toast = document.getElementById("toast");
  toast.textContent = message;
  toast.classList.add("show");

  setTimeout(() => {
    toast.classList.remove("show");
  }, 2600);
}

/* =========================
   NOTIFIKASI
========================= */

function addNotification(title, message, icon = "🔔") {
  notifications.unshift({
    title,
    message,
    icon,
    time: new Date().toLocaleString("id-ID")
  });

  notifications = notifications.slice(0, 50);
  saveStorage();
  renderNotifications();
}

function renderNotifications() {
  const container = document.getElementById("notificationList");

  if (!notifications.length) {
    container.innerHTML = '<div class="empty">Belum ada notifikasi.</div>';
    return;
  }

  container.innerHTML = notifications.map(item => `
    <div class="notification">
      <div class="notification-icon">${escapeHTML(item.icon)}</div>
      <div>
        <h4>${escapeHTML(item.title)}</h4>
        <p>${escapeHTML(item.message)}</p>
        <p style="margin-top:5px;font-size:10px">${escapeHTML(item.time)}</p>
      </div>
    </div>
  `).join("");
}

function clearNotifications() {
  notifications = [];
  saveStorage();
  renderNotifications();
  showToast("Notifikasi dibersihkan.");
}

/* =========================
   FUNGSI KEAMANAN TEKS
========================= */

function escapeHTML(value) {
  return String(value).replace(/[&<>"']/g, char => ({
    "&": "&amp;",
    "<": "&lt;",
    ">": "&gt;",
    '"': "&quot;",
    "'": "&#039;"
  })[char]);
}

/* =========================
   INPUT MONITORING
========================= */

document.getElementById("monitorForm").addEventListener("submit", function(event) {
  event.preventDefault();

  const nextData = {
    n: Number(document.getElementById("inputN").value),
    p: Number(document.getElementById("inputP").value),
    k: Number(document.getElementById("inputK").value),
    ph: Number(document.getElementById("inputPH").value),
    temp: Number(document.getElementById("inputTemp").value),
    moisture: Number(document.getElementById("inputMoisture").value)
  };

  if (Object.values(nextData).some(value => !Number.isFinite(value))) {
    showToast("Periksa kembali seluruh nilai input.");
    return;
  }

  if (nextData.n < 0 || nextData.p < 0 || nextData.k < 0 ||
      nextData.ph < 0 || nextData.ph > 14 ||
      nextData.moisture < 0 || nextData.moisture > 100 ||
      nextData.temp < -20 || nextData.temp > 100) {
    showToast("Ada nilai yang berada di luar batas input.");
    return;
  }

  data = nextData;

  history.unshift({
    ...data,
    time: new Date().toLocaleString("id-ID")
  });

  history = history.slice(0, 100);

  saveStorage();
  updateAll();

  addNotification(
    "Data monitoring diperbarui",
    "Data kondisi tanah terbaru berhasil disimpan.",
    "📊"
  );

  showToast("Data monitoring berhasil disimpan!");

  // Periksa kondisi penyiraman otomatis setelah data berubah.
  checkAutomaticWatering();
});

/* =========================
   UPDATE TAMPILAN
========================= */

function setText(id, value) {
  document.getElementById(id).textContent = value;
}

function setBar(id, percentage) {
  document.getElementById(id).style.width =
    Math.max(0, Math.min(100, percentage)) + "%";
}

function updateAll() {
  // Beranda
  setText("homeN", data.n);
  setText("homeP", data.p);
  setText("homeK", data.k);
  setText("homeMoisture", data.moisture);

  // Dashboard
  updateDashboard();

  // Monitoring
  setText("monitorN", data.n + " mg/kg");
  setText("monitorP", data.p + " mg/kg");
  setText("monitorK", data.k + " mg/kg");
  setText("monitorPH", data.ph);
  setText("monitorTemp", data.temp + " °C");
  setText("monitorMoisture", data.moisture + "%");

  setBar("barN", data.n / 2);
  setBar("barP", data.p / 2);
  setBar("barK", data.k / 2);
  setBar("barPH", data.ph / 14 * 100);
  setBar("barTemp", data.temp / 60 * 100);
  setBar("barMoisture", data.moisture);

  // Pemupukan
  setText("fertN", data.n + " mg/kg");
  setText("fertP", data.p + " mg/kg");
  setText("fertK", data.k + " mg/kg");

  // Penyiraman
  setText("waterMoisture", data.moisture);
  setBar("waterProgress", data.moisture);

  updateControlStatus();
  updateHomeStatus();
  updateWaterRecommendation();
}

function updateDashboard() {
  setText("dashN", data.n);
  setText("dashP", data.p);
  setText("dashK", data.k);
  setText("dashPH", data.ph);
  setText("dashTemp", data.temp);
  setText("dashMoisture", data.moisture);
  setText("dashFertilizer", fertilizerActive ? "Aktif" : "Nonaktif");
  setText("dashWater", waterActive ? "Aktif" : "Nonaktif");

  const analysis = document.getElementById("dashboardAnalysis");

  if (!history.length) {
    analysis.textContent =
      "Belum terdapat data pengukuran. Silakan masukkan data melalui menu Monitoring Tanah.";
    return;
  }

  let moistureText = data.moisture < 40
    ? "Nilai kelembapan berada di bawah 40%."
    : "Nilai kelembapan berada pada atau di atas 40%.";

  let phText = data.ph < 5.5
    ? "pH tanah tergolong asam berdasarkan nilai yang dimasukkan."
    : data.ph > 7.5
      ? "pH tanah tergolong basa berdasarkan nilai yang dimasukkan."
      : "pH tanah berada dalam kisaran 5,5–7,5.";

  analysis.textContent =
    "Data terakhir menunjukkan nitrogen sebesar " + data.n +
    " mg/kg, fosfor " + data.p +
    " mg/kg, kalium " + data.k +
    " mg/kg, pH " + data.ph +
    ", suhu " + data.temp +
    " °C, dan kelembapan " + data.moisture +
    "%. " + moistureText + " " + phText +
    " Interpretasi kecukupan unsur hara perlu disesuaikan dengan jenis tanaman dan hasil analisis tanah.";
}

function updateHomeStatus() {
  const hasData = history.length > 0;

  setText("homeMonitorStatus", hasData ? "Data tersedia" : "Belum ada data");
  setText("homeFertilizerStatus", fertilizerActive ? "Aktif" : "Nonaktif");
  setText("homeWaterStatus", waterActive ? "Aktif" : "Nonaktif");
}

function updateControlStatus() {
  setText("fertilizerStatus", fertilizerActive ? "AKTIF" : "NONAKTIF");
  setText("waterStatus", waterActive ? "AKTIF" : "NONAKTIF");

  document.getElementById("fertilizerStatus").style.color =
    fertilizerActive ? "#4e9a58" : "#829187";

  document.getElementById("waterStatus").style.color =
    waterActive ? "#4e9a58" : "#829187";

  updateDashboard();
  updateHomeStatus();
}

function updateWaterRecommendation() {
  const threshold = Number(document.getElementById("moistureThreshold").value) || 40;

  setText("thresholdDisplay", threshold + "%");

  let recommendation = "Kelembapan mencukupi";

  if (data.moisture < threshold) {
    recommendation = "Perlu penyiraman";
  }

  setText("waterRecommendation", recommendation);
}

/* =========================
   PEMUPUKAN
========================= */

document.getElementById("fertilizerOn").addEventListener("click", () => {
  const dose = Number(document.getElementById("fertilizerDose").value);

  if (!Number.isFinite(dose) || dose <= 0) {
    showToast("Masukkan dosis pupuk yang valid.");
    return;
  }

  fertilizerActive = true;
  updateControlStatus();

  addNotification(
    "Pemupukan diaktifkan",
    "Simulasi pemupukan aktif dengan pengaturan dosis " + dose + " ml.",
    "🌿"
  );

  showToast("Simulasi pemupukan diaktifkan.");
});

document.getElementById("fertilizerOff").addEventListener("click", () => {
  fertilizerActive = false;
  updateControlStatus();

  addNotification(
    "Pemupukan dimatikan",
    "Simulasi pemupukan telah dinonaktifkan.",
    "🛑"
  );

  showToast("Simulasi pemupukan dimatikan.");
});

/* =========================
   PENYIRAMAN
========================= */

function stopWaterTimer() {
  if (waterTimer) {
    clearTimeout(waterTimer);
    waterTimer = null;
  }
}

function activateWater(reason) {
  if (waterActive) return;

  waterActive = true;
  updateControlStatus();

  addNotification(
    "Pompa penyiraman aktif",
    reason,
    "💧"
  );

  showToast("Simulasi pompa aktif.");

  const duration = Number(document.getElementById("waterDuration").value);

  stopWaterTimer();

  if (Number.isFinite(duration) && duration > 0) {
    waterTimer = setTimeout(() => {
      waterActive = false;
      waterTimer = null;
      updateControlStatus();

      addNotification(
        "Pompa penyiraman berhenti",
        "Durasi simulasi penyiraman telah selesai.",
        "🛑"
      );

      showToast("Durasi simulasi selesai.");
    }, duration * 1000);
  }
}

function deactivateWater(reason) {
  stopWaterTimer();

  if (!waterActive) return;

  waterActive = false;
  updateControlStatus();

  addNotification(
    "Pompa penyiraman nonaktif",
    reason || "Simulasi pompa telah dimatikan.",
    "🛑"
  );

  showToast("Simulasi pompa dimatikan.");
}

function checkAutomaticWatering() {
  const mode = document.getElementById("waterMode").value;
  const threshold = Number(document.getElementById("moistureThreshold").value);

  if (mode !== "automatic") return;

  if (data.moisture < threshold && !waterActive) {
    const duration = Number(document.getElementById("waterDuration").value);

    if (!Number.isFinite(duration) || duration <= 0) {
      showToast("Atur durasi simulasi yang valid.");
      return;
    }

    activateWater(
      "Kelembapan tanah " + data.moisture +
      "% berada di bawah batas minimum " + threshold + "%."
    );
  } else if (data.moisture >= threshold && waterActive) {
    deactivateWater(
      "Kelembapan tanah telah mencapai atau melampaui batas minimum."
    );
  }
}

document.getElementById("waterOn").addEventListener("click", () => {
  if (document.getElementById("waterMode").value === "automatic") {
    showToast("Gunakan mode manual untuk menyalakan pompa langsung.");
    return;
  }

  const duration = Number(document.getElementById("waterDuration").value);

  if (!Number.isFinite(duration) || duration <= 0) {
    showToast("Masukkan durasi simulasi yang valid.");
    return;
  }

  activateWater("Pompa diaktifkan secara manual melalui website.");
});

document.getElementById("waterOff").addEventListener("click", () => {
  deactivateWater("Pompa dimatikan secara manual melalui website.");
});

document.getElementById("waterMode").addEventListener("change", () => {
  stopWaterTimer();
  waterActive = false;
  updateControlStatus();

  if (document.getElementById("waterMode").value === "automatic") {
    showToast("Mode otomatis simulasi diaktifkan.");
    checkAutomaticWatering();
  } else {
    showToast("Mode manual diaktifkan.");
  }
});

document.getElementById("moistureThreshold").addEventListener("input", () => {
  updateWaterRecommendation();
  checkAutomaticWatering();
});

document.getElementById("waterDuration").addEventListener("change", () => {
  const duration = Number(document.getElementById("waterDuration").value);

  if (!Number.isFinite(duration) || duration <= 0) {
    showToast("Durasi harus lebih dari 0 detik.");
  }
});

/* =========================
   RIWAYAT DATA
========================= */

function renderHistory() {
  const body = document.getElementById("historyBody");

  if (!history.length) {
    body.innerHTML =
      '<tr><td colspan="7" class="empty">Belum ada data monitoring.</td></tr>';
    return;
  }

  body.innerHTML = history.map(item => `
    <tr>
      <td>${escapeHTML(item.time)}</td>
      <td>${escapeHTML(item.n)}</td>
      <td>${escapeHTML(item.p)}</td>
      <td>${escapeHTML(item.k)}</td>
      <td>${escapeHTML(item.ph)}</td>
      <td>${escapeHTML(item.temp)} °C</td>
      <td>${escapeHTML(item.moisture)}%</td>
    </tr>
  `).join("");
}

function clearHistory() {
  if (!confirm("Yakin ingin menghapus seluruh riwayat monitoring?")) return;

  history = [];
  saveStorage();
  renderHistory();
  updateDashboard();
  updateHomeStatus();

  showToast("Riwayat berhasil dihapus.");
}

/* =========================
   SALIN DATA DAN CHATGPT
========================= */

function buildSoilPrompt() {
  return `Saya ingin menganalisis kondisi tanah pertanian berdasarkan data berikut:

Nitrogen (N): ${data.n} mg/kg
Fosfor (P): ${data.p} mg/kg
Kalium (K): ${data.k} mg/kg
pH tanah: ${data.ph}
Suhu tanah: ${data.temp} °C
Kelembapan tanah: ${data.moisture}%

Tolong bantu:
1. Jelaskan kondisi setiap parameter tanah.
2. Identifikasi parameter yang perlu diperhatikan.
3. Berikan saran pengelolaan tanah dan pemupukan berdasarkan data tersebut.
4. Jelaskan pertimbangan penyiraman berdasarkan kelembapan.
5. Sebutkan informasi tambahan yang diperlukan agar rekomendasi lebih akurat.

Jangan langsung menentukan dosis pupuk tanpa mengetahui jenis tanaman, fase pertumbuhan, satuan dan metode pengukuran, serta kondisi lahan.`;
}

async function copySoilData() {
  const prompt = buildSoilPrompt();

  try {
    await navigator.clipboard.writeText(prompt);
    showToast("Data monitoring berhasil disalin!");
  } catch (error) {
    const textarea = document.createElement("textarea");
    textarea.value = prompt;
    textarea.style.position = "fixed";
    textarea.style.opacity = "0";
    document.body.appendChild(textarea);
    textarea.select();

    try {
      document.execCommand("copy");
      showToast("Data monitoring berhasil disalin!");
    } catch (copyError) {
      showToast("Gagal menyalin. Silakan coba lagi.");
    }

    textarea.remove();
  }
}

function openAI() {
  window.open("https://chatgpt.com/", "_blank", "noopener,noreferrer");
}

/* =========================
   INISIALISASI
========================= */

loadStorage();
updateDate();
updateAll();
renderHistory();
renderNotifications();

</script>
</body>
</html>
