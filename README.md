<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SIRAMIX | Smart Fertilization System</title>

<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{--green:#176b45;--dark:#103d2b;--light:#eaf5ed}
body{font-family:'Segoe UI',sans-serif;background:#f4f8f4;color:#263b30}
.layout{display:flex;min-height:100vh}
.sidebar{width:245px;background:var(--dark);color:white;padding:25px 18px;position:fixed;height:100vh;overflow-y:auto}
.logo{font-size:25px;font-weight:800;margin-bottom:35px}
.menu-title{color:#a6c6b2;font-size:11px;letter-spacing:2px;margin:20px 12px}
.nav-item{display:block;padding:13px;border-radius:9px;margin:5px 0;color:#d1e3d7;cursor:pointer;font-size:14px;text-decoration:none}
.nav-item:hover,.nav-item.active{background:#287b53;color:white}
.nav-link{border:1px solid #4d8063;margin-top:15px}
.main{margin-left:245px;width:calc(100% - 245px);padding:30px 38px}
.topbar{display:flex;justify-content:space-between;align-items:center;margin-bottom:30px;gap:12px}
.topbar h2{font-size:23px}
.topbar p{font-size:13px;color:#829087;margin-top:5px}
.status{background:#e2f5e8;color:#197644;padding:9px 15px;border-radius:20px;font-size:12px;font-weight:bold}
.hero{background:linear-gradient(120deg,#145b39,#31965c);color:white;padding:35px;border-radius:18px;margin-bottom:25px}
.hero h1{font-size:30px;margin-bottom:15px}
.hero p{line-height:1.8;font-size:14px;color:#e0f2e5}
.hero button{margin-top:20px;background:white;color:var(--green);border:0;padding:12px 20px;border-radius:8px;font-weight:bold;cursor:pointer}
.section{display:none}
.section.active{display:block}
.section-title{margin:25px 0 18px;font-size:20px}
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-bottom:22px}
.card,.panel{background:white;padding:22px;border-radius:13px;border:1px solid #e9eee9;margin-bottom:18px}
.card-icon{font-size:27px;margin-bottom:12px}
.card small{color:#829087;font-size:12px}
.value{font-size:26px;font-weight:bold;margin:8px 0}
.good{font-size:12px;color:#24834f}
.panel h3{margin-bottom:16px;font-size:16px}
.btn{background:var(--green);color:white;border:0;padding:11px 17px;border-radius:8px;cursor:pointer;font-weight:600}
.btn.secondary{background:#e6f3e9;color:var(--green)}
.btn.off{background:#dce4de;color:#425449}
.control-row{display:flex;justify-content:space-between;align-items:center;gap:15px;padding:16px 0;border-bottom:1px solid #edf0ed}
.control-row p{font-size:13px;color:#829087;margin-top:5px}
input,select{padding:10px;border:1px solid #dce5dd;border-radius:8px;width:100%}
.form-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-bottom:18px}
.field label{display:block;font-size:13px;font-weight:600;margin-bottom:7px}
.data-card{background:#f8fbf8;border:1px solid #e5eee7;border-radius:10px;padding:16px}
.data-card b{font-size:12px;color:#829087}
.data-card strong{display:block;font-size:23px;margin-top:7px}
.note{font-size:12px;color:#829087;line-height:1.6;margin:12px 0}
table{width:100%;border-collapse:collapse;font-size:13px}
th,td{text-align:left;padding:13px 9px;border-bottom:1px solid #edf0ed}
th{color:#829087}
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px}
.about-box{background:#eaf5ed;padding:22px;border-radius:12px}
.about-box h3{color:var(--green);margin-bottom:10px}
.about-box p{font-size:14px;line-height:1.8}
.notification{padding:15px;background:#eaf5ed;border-radius:9px;margin-bottom:12px;font-size:14px}
footer{text-align:center;color:#829087;padding:30px 10px;font-size:12px}

@media(max-width:900px){
.grid,.form-grid{grid-template-columns:repeat(2,1fr)}
}
@media(max-width:650px){
.layout{display:block}
.sidebar{width:100%;height:auto;position:relative;padding:15px}
.logo{margin-bottom:15px}
.menu-title{display:none}
.nav-list{display:flex;overflow-x:auto;gap:5px}
.nav-item{white-space:nowrap;padding:11px}
.main{margin:0;width:100%;padding:18px}
.grid,.form-grid,.about-grid{grid-template-columns:1fr}
.hero{padding:24px}
.hero h1{font-size:24px}
}
</style>
</head>

<body>
<div class="layout">

<aside class="sidebar">
<div class="logo">🌱 SIRAMIX</div>
<div class="menu-title">MENU UTAMA</div>

<nav class="nav-list">
<div class="nav-item active" onclick="showPage('home',this)">🏠 Beranda</div>
<div class="nav-item" onclick="showPage('dashboard',this)">📊 Dashboard</div>
<div class="nav-item" onclick="showPage('monitoring',this)">📡 Monitoring Sensor</div>
<div class="nav-item" onclick="showPage('pupuk',this)">🌿 Pemupukan</div>
<div class="nav-item" onclick="showPage('penyiraman',this)">💧 Penyiraman Air</div>
<div class="nav-item" onclick="showPage('riwayat',this)">📋 Riwayat</div>
<div class="nav-item" onclick="showPage('notifikasi',this)">🔔 Notifikasi</div>
<div class="nav-item" onclick="showPage('about',this)">ℹ️ Tentang Kami</div>
<a class="nav-item nav-link" href="https://chatgpt.com/" target="_blank">🤖 SIRAMIX AI (GPT) ↗</a>
</nav>
</aside>

<main class="main">

<div class="topbar">
<div>
<h2 id="pageTitle">Beranda</h2>
<p>Smart Automatic Fertilization System</p>
</div>
<div class="status">● SISTEM AKTIF</div>
</div>

<!-- BERANDA -->
<section class="section active" id="home">
<div class="hero">
<h1>Welcome to SIRAMIX 🌱</h1>
<p>SIRAMIX merupakan inovasi teknologi pertanian yang dirancang untuk mengoptimalkan proses pemupukan dan penyiraman air pada tanaman melalui sistem otomatis berbasis sensor dan mikrokontroler ESP32. Sistem ini membantu pemberian nutrisi dan air agar lebih terukur, efisien, dan tepat sasaran.</p>
<button onclick="showPage('dashboard',document.querySelectorAll('.nav-item')[1])">Buka Dashboard →</button>
</div>

<h2 class="section-title">Fitur Utama</h2>
<div class="grid">
<div class="card">
<div class="card-icon">🌱</div>
<h3>Pemupukan Otomatis</h3>
<p><small>Pengaturan pemberian pupuk berdasarkan kebutuhan tanaman.</small></p>
</div>
<div class="card">
<div class="card-icon">💧</div>
<h3>Penyiraman Otomatis</h3>
<p><small>Pengaturan penyiraman berdasarkan tingkat kelembapan tanah.</small></p>
</div>
<div class="card">
<div class="card-icon">📡</div>
<h3>Monitoring Sensor</h3>
<p><small>Pemantauan kondisi tanah melalui pembacaan sensor.</small></p>
</div>
<div class="card">
<div class="card-icon">🤖</div>
<h3>Analisis AI</h3>
<p><small>Salin data unsur hara untuk dianalisis melalui ChatGPT.</small></p>
</div>
</div>

<div class="panel">
<h3>Tujuan Inovasi</h3>
<p style="line-height:1.8;font-size:14px">Mengembangkan sistem pemupukan dan penyiraman otomatis yang membantu mengatur pemberian nutrisi serta air berdasarkan kondisi tanah dan kebutuhan tanaman sehingga penggunaan sumber daya menjadi lebih efisien dan terukur.</p>
</div>
</section>

<!-- DASHBOARD -->
<section class="section" id="dashboard">
<h2 class="section-title">Dashboard Monitoring</h2>

<div class="grid">
<div class="card">
<div class="card-icon">🌡️</div>
<small>Suhu Tanah</small>
<div class="value" id="temperature">28°C</div>
<div class="good">● Data simulasi</div>
</div>

<div class="card">
<div class="card-icon">💧</div>
<small>Kelembapan Tanah</small>
<div class="value" id="moisture">65%</div>
<div class="good">● Data simulasi</div>
</div>

<div class="card">
<div class="card-icon">🌿</div>
<small>Status Pemupukan</small>
<div class="value" id="fertStatus">OFF</div>
<div class="good">● Sistem siaga</div>
</div>

<div class="card">
<div class="card-icon">🚿</div>
<small>Status Penyiraman</small>
<div class="value" id="waterStatus">OFF</div>
<div class="good">● Sistem siaga</div>
</div>
</div>

<div class="panel">
<h3>Informasi Sistem</h3>
<p style="font-size:14px;line-height:1.8">Data pada versi ini masih berupa simulasi dan belum terhubung dengan ESP32 maupun sensor fisik.</p>
</div>
</section>

<!-- MONITORING SENSOR -->
<section class="section" id="monitoring">
<h2 class="section-title">Monitoring Sensor dan Unsur Hara</h2>

<div class="panel">
<h3>Masukkan Data Kondisi Tanah</h3>

<div class="form-grid">
<div class="field">
<label for="nitrogen">Nitrogen (N) — mg/kg</label>
<input id="nitrogen" type="number" value="45" min="0">
</div>
<div class="field">
<label for="phosphorus">Fosfor (P) — mg/kg</label>
<input id="phosphorus" type="number" value="30" min="0">
</div>
<div class="field">
<label for="potassium">Kalium (K) — mg/kg</label>
<input id="potassium" type="number" value="35" min="0">
</div>
<div class="field">
<label for="soilPH">pH Tanah</label>
<input id="soilPH" type="number" value="6.5" min="0" max="14" step="0.1">
</div>
<div class="field">
<label for="soilTemperature">Suhu Tanah (°C)</label>
<input id="soilTemperature" type="number" value="28">
</div>
<div class="field">
<label for="soilMoisture">Kelembapan Tanah (%)</label>
<input id="soilMoisture" type="number" value="65" min="0" max="100">
</div>
</div>

<div class="field" style="max-width:420px;margin-bottom:16px">
<label for="plantType">Jenis tanaman (opsional)</label>
<input id="plantType" type="text" placeholder="Contoh: cabai, jagung, padi">
</div>

<button class="btn" onclick="updateMonitoring()">Perbarui Data</button>
<p class="note">Nilai awal merupakan contoh simulasi.</p>
</div>

<div class="grid">
<div class="data-card"><b>NITROGEN (N)</b><strong><span id="showN">45</span> mg/kg</strong></div>
<div class="data-card"><b>FOSFOR (P)</b><strong><span id="showP">30</span> mg/kg</strong></div>
<div class="data-card"><b>KALIUM (K)</b><strong><span id="showK">35</span> mg/kg</strong></div>
<div class="data-card"><b>pH TANAH</b><strong id="showPH">6.5</strong></div>
<div class="data-card"><b>SUHU TANAH</b><strong><span id="showTemp">28</span> °C</strong></div>
<div class="data-card"><b>KELEMBAPAN TANAH</b><strong><span id="showMoisture">65</span>%</strong></div>
</div>

<div class="panel">
<h3>Salin Data untuk Analisis AI</h3>
<p style="font-size:14px;line-height:1.7;margin-bottom:15px">Tekan tombol untuk menyalin data monitoring beserta pertanyaan analisis. Buka ChatGPT, kemudian tempelkan teks yang sudah disalin.</p>
<button class="btn" onclick="copySoilData()">📋 Salin Data untuk AI</button>
<p id="copyStatus" class="note" aria-live="polite"></p>
<a href="https://chatgpt.com/" target="_blank" style="color:var(--green);font-weight:600">Buka ChatGPT ↗</a>
</div>
</section>

<!-- PEMUPUKAN -->
<section class="section" id="pupuk">
<h2 class="section-title">Kontrol Pemupukan Otomatis</h2>

<div class="panel">
<h3>Pengaturan Sistem Pemupukan</h3>

<div class="control-row">
<div><b>Mode Pemupukan</b><p>Pilih pengoperasian sistem</p></div>
<select id="fertMode" style="max-width:150px">
<option value="auto">Otomatis</option>
<option value="manual">Manual</option>
</select>
</div>

<div class="control-row">
<div><b>Status Pompa Pupuk</b><p id="fertText">Pompa dalam keadaan mati</p></div>
<button class="btn off" id="fertButton" onclick="toggleFert()">HIDUPKAN</button>
</div>

<div class="control-row">
<div><b>Pengaturan Takaran</b><p>Pengaturan volume sesuai rancangan alat</p></div>
<input type="number" id="dose" value="100" min="1" style="max-width:110px">
</div>

<br>
<button class="btn" onclick="saveSetting()">Simpan Pengaturan</button>
<p class="note">Kontrol pompa pada versi ini hanya simulasi.</p>
</div>
</section>

<!-- PENYIRAMAN AIR -->
<section class="section" id="penyiraman">
<h2 class="section-title">Kontrol Penyiraman Air Otomatis</h2>

<div class="panel">
<h3>Pengaturan Sistem Penyiraman</h3>

<div class="control-row">
<div>
<b>Mode Penyiraman</b>
<p>Pilih pengoperasian sistem penyiraman</p>
</div>
<select id="waterMode" style="max-width:150px" onchange="changeWaterMode()">
<option value="auto">Otomatis</option>
<option value="manual">Manual</option>
</select>
</div>

<div class="control-row">
<div>
<b>Status Pompa Air</b>
<p id="waterText">Pompa air dalam keadaan mati</p>
</div>
<button class="btn off" id="waterButton" onclick="toggleWater()">HIDUPKAN</button>
</div>

<div class="control-row">
<div>
<b>Batas Kelembapan Minimum</b>
<p>Pompa aktif jika kelembapan berada di bawah nilai ini</p>
</div>
<input type="number" id="moistureLimit" value="40" min="0" max="100" style="max-width:110px">
</div>

<div class="control-row">
<div>
<b>Durasi Penyiraman</b>
<p>Lama waktu penyiraman dalam detik</p>
</div>
<input type="number" id="waterDuration" value="30" min="1" style="max-width:110px">
</div>

<br>
<button class="btn" onclick="saveWaterSetting()">Simpan Pengaturan</button>

<p class="note">
Pada mode otomatis, sistem menggunakan nilai kelembapan tanah dari menu Monitoring Sensor sebagai dasar simulasi pengaktifan pompa air.
</p>
</div>

<div class="panel">
<h3>Informasi Kondisi Penyiraman</h3>

<div class="grid">
<div class="data-card">
<b>KELEMBAPAN TANAH SAAT INI</b>
<strong id="currentMoisture">65%</strong>
</div>

<div class="data-card">
<b>BATAS KELEMBAPAN</b>
<strong id="currentLimit">40%</strong>
</div>

<div class="data-card">
<b>REKOMENDASI SISTEM</b>
<strong id="waterRecommendation" style="font-size:17px">Belum perlu</strong>
</div>
</div>

<button class="btn secondary" onclick="checkWaterCondition()">Periksa Kondisi Tanah</button>
<p id="waterMessage" class="note">Tekan tombol untuk memeriksa kondisi kelembapan tanah.</p>
</div>
</section>

<!-- RIWAYAT -->
<section class="section" id="riwayat">
<h2 class="section-title">Riwayat Aktivitas</h2>
<div class="panel">
<h3>Catatan Aktivitas Sistem</h3>
<table>
<thead>
<tr>
<th>Waktu</th>
<th>Aktivitas</th>
<th>Status</th>
</tr>
</thead>
<tbody id="history">
<tr><td>-</td><td>Website dibuka</td><td>Simulasi</td></tr>
</tbody>
</table>
</div>
</section>

<!-- NOTIFIKASI -->
<section class="section" id="notifikasi">
<h2 class="section-title">Notifikasi Sistem</h2>
<div class="panel">
<div class="notification">🌱 Sistem SIRAMIX berhasil dibuka.</div>
<div class="notification">📡 Monitoring sensor tersedia dalam mode simulasi.</div>
<div class="notification">💧 Fitur pengaturan penyiraman air tersedia.</div>
<div class="notification">🧪 Menunggu koneksi perangkat ESP32.</div>
<div class="notification">🤖 Data unsur hara dapat disalin untuk dianalisis melalui ChatGPT.</div>
</div>
</section>

<!-- TENTANG KAMI -->
<section class="section" id="about">
<h2 class="section-title">Tentang SIRAMIX</h2>

<div class="hero">
<h1>SIRAMIX 🌿</h1>
<p>Smart Automatic Fertilization System untuk mendukung pertanian yang lebih modern, efisien, dan berkelanjutan.</p>
</div>

<div class="about-grid">
<div class="about-box">
<h3>Latar Belakang</h3>
<p>SIRAMIX dikembangkan untuk menjawab keterbatasan pemupukan dan penyiraman konvensional yang masih banyak bergantung pada perkiraan.</p>
</div>
<div class="about-box">
<h3>Tujuan</h3>
<p>Mengembangkan sistem pemupukan dan penyiraman otomatis yang mengintegrasikan AI untuk membantu mengatur pemberian nutrisi dan air sesuai kebutuhan tanaman.</p>
</div>
<div class="about-box">
<h3>Teknologi</h3>
<p>Sistem dirancang menggunakan ESP32, sensor, relay, pompa pupuk, pompa air, dan perangkat pendukung lainnya.</p>
</div>
<div class="about-box">
<h3>Manfaat</h3>
<p>Membantu meningkatkan efisiensi penggunaan air dan pupuk serta mendukung pertanian cerdas.</p>
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
function showPage(page,element){
document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
document.getElementById(page).classList.add('active');

document.querySelectorAll('.nav-item').forEach(n=>n.classList.remove('active'));
if(element)element.classList.add('active');

const titles={
home:'Beranda',
dashboard:'Dashboard Monitoring',
monitoring:'Monitoring Sensor',
pupuk:'Kontrol Pemupukan',
penyiraman:'Kontrol Penyiraman Air',
riwayat:'Riwayat Aktivitas',
notifikasi:'Notifikasi',
about:'Tentang SIRAMIX'
};

document.getElementById('pageTitle').innerText=titles[page];
}

let fertOn=false;
let waterOn=false;

function addHistory(activity,status){
const row=document.getElementById('history').insertRow(0);
row.insertCell(0).innerText=new Date().toLocaleString('id-ID');
row.insertCell(1).innerText=activity;
row.insertCell(2).innerText=status;
}

// PEMUPUKAN
function toggleFert(){
if(document.getElementById('fertMode').value!=='manual'){
alert('Pilih mode Manual terlebih dahulu.');
return;
}

fertOn=!fertOn;

document.getElementById('fertStatus').innerText=fertOn?'ON':'OFF';
document.getElementById('fertText').innerText=fertOn?'Pompa pupuk aktif (simulasi)':'Pompa dalam keadaan mati';

const btn=document.getElementById('fertButton');
btn.innerText=fertOn?'MATIKAN':'HIDUPKAN';
btn.classList.toggle('off',!fertOn);

addHistory('Aktivitas pemupukan',fertOn?'ON (simulasi)':'OFF (simulasi)');
}

function saveSetting(){
const dose=document.getElementById('dose').value;

if(!dose||Number(dose)<=0){
alert('Masukkan takaran yang valid.');
return;
}

alert('Pengaturan pemupukan berhasil disimpan (simulasi).');
addHistory('Pengaturan takaran pupuk: '+dose,'Tersimpan (simulasi)');
}

// PENYIRAMAN AIR
function toggleWater(){
if(document.getElementById('waterMode').value!=='manual'){
alert('Pilih mode Manual terlebih dahulu untuk mengontrol pompa air.');
return;
}

waterOn=!waterOn;
updateWaterDisplay();

addHistory('Aktivitas penyiraman air',waterOn?'Pompa ON (simulasi)':'Pompa OFF (simulasi)');
}

function updateWaterDisplay(){
document.getElementById('waterStatus').innerText=waterOn?'ON':'OFF';

document.getElementById('waterText').innerText=waterOn
?'Pompa air aktif (simulasi)'
:'Pompa air dalam keadaan mati';

const btn=document.getElementById('waterButton');
btn.innerText=waterOn?'MATIKAN':'HIDUPKAN';
btn.classList.toggle('off',!waterOn);
}

function changeWaterMode(){
const mode=document.getElementById('waterMode').value;

if(mode==='auto'){
document.getElementById('waterText').innerText='Mode otomatis: mengikuti kelembapan tanah';
checkWaterCondition();
}else{
document.getElementById('waterText').innerText='Mode manual: pompa dikendalikan pengguna';
}
}

function saveWaterSetting(){
const limit=Number(document.getElementById('moistureLimit').value);
const duration=Number(document.getElementById('waterDuration').value);

if(!Number.isFinite(limit)||limit<0||limit>100){
alert('Batas kelembapan harus berada pada rentang 0–100%.');
return;
}

if(!Number.isFinite(duration)||duration<=0){
alert('Masukkan durasi penyiraman yang valid.');
return;
}

document.getElementById('currentLimit').innerText=limit+'%';

alert('Pengaturan penyiraman berhasil disimpan (simulasi).');
addHistory('Pengaturan penyiraman: batas '+limit+'%, durasi '+duration+' detik','Tersimpan (simulasi)');

if(document.getElementById('waterMode').value==='auto'){
checkWaterCondition();
}
}

function checkWaterCondition(){
const moisture=Number(document.getElementById('soilMoisture').value);
const limit=Number(document.getElementById('moistureLimit').value);

if(!Number.isFinite(moisture)||!Number.isFinite(limit)||limit<0||limit>100){
alert('Periksa kembali data kelembapan dan batas kelembapan.');
return;
}

document.getElementById('currentMoisture').innerText=moisture+'%';
document.getElementById('currentLimit').innerText=limit+'%';

const recommendation=document.getElementById('waterRecommendation');
const message=document.getElementById('waterMessage');

if(moisture<limit){
recommendation.innerText='Perlu disiram';
message.innerText='Kelembapan tanah berada di bawah batas minimum. Sistem merekomendasikan penyiraman air.';

if(document.getElementById('waterMode').value==='auto'){
waterOn=true;
updateWaterDisplay();
addHistory('Penyiraman otomatis berdasarkan kelembapan','Pompa ON (simulasi)');
}
}else{
recommendation.innerText='Belum perlu';
message.innerText='Kelembapan tanah masih berada pada atau di atas batas minimum. Penyiraman belum diperlukan.';

if(document.getElementById('waterMode').value==='auto'&&waterOn){
waterOn=false;
updateWaterDisplay();
addHistory('Penyiraman otomatis dihentikan','Pompa OFF (simulasi)');
}
}
}

// MONITORING SENSOR
function readSoilData(){
const ids=['nitrogen','phosphorus','potassium','soilPH','soilTemperature','soilMoisture'];
const values={};

for(const id of ids){
const el=document.getElementById(id);

if(el.value===''||!Number.isFinite(Number(el.value))||Number(el.value)<0){
alert('Lengkapi semua data dengan angka yang valid dan tidak negatif.');
el.focus();
return null;
}

values[id]=el.value.trim();
}

if(Number(values.soilPH)>14){
alert('Nilai pH harus berada pada rentang 0–14.');
return null;
}

if(Number(values.soilMoisture)>100){
alert('Kelembapan harus berada pada rentang 0–100%.');
return null;
}

return values;
}

function updateMonitoring(){
const v=readSoilData();
if(!v)return;

document.getElementById('showN').innerText=v.nitrogen;
document.getElementById('showP').innerText=v.phosphorus;
document.getElementById('showK').innerText=v.potassium;
document.getElementById('showPH').innerText=v.soilPH;
document.getElementById('showTemp').innerText=v.soilTemperature;
document.getElementById('showMoisture').innerText=v.soilMoisture;

document.getElementById('temperature').innerText=v.soilTemperature+'°C';
document.getElementById('moisture').innerText=v.soilMoisture+'%';

addHistory('Pembaruan data monitoring','Berhasil (input pengguna)');

if(document.getElementById('waterMode').value==='auto'){
checkWaterCondition();
}

alert('Data monitoring berhasil diperbarui.');
}

// SALIN DATA UNTUK AI
async function copySoilData(){
const v=readSoilData();
if(!v)return;

const plant=document.getElementById('plantType').value.trim()||'Belum disebutkan';

const data=`DATA MONITORING TANAH SIRAMIX

Nitrogen (N): ${v.nitrogen} mg/kg
Fosfor (P): ${v.phosphorus} mg/kg
Kalium (K): ${v.potassium} mg/kg
pH tanah: ${v.soilPH}
Suhu tanah: ${v.soilTemperature} °C
Kelembapan tanah: ${v.soilMoisture}%
Jenis tanaman: ${plant}

Tolong analisis data tersebut dengan bahasa yang mudah dipahami:
1. Jelaskan arti setiap parameter.
2. Identifikasi kondisi unsur hara tanah.
3. Berikan saran umum pengelolaan tanah dan nutrisi.
4. Jelaskan kebutuhan penyiraman berdasarkan kelembapan tanah.
5. Pertimbangkan jenis tanaman dan fase pertumbuhannya.
6. Jangan menetapkan dosis pupuk secara pasti hanya dari angka ini.`;

try{
await navigator.clipboard.writeText(data);
document.getElementById('copyStatus').innerText='✓ Data berhasil disalin! Buka ChatGPT lalu tempelkan dengan Ctrl + V.';
}catch(error){
const area=document.createElement('textarea');
area.value=data;
document.body.appendChild(area);
area.select();
const copied=document.execCommand('copy');
area.remove();

document.getElementById('copyStatus').innerText=copied
?'✓ Data berhasil disalin! Buka ChatGPT lalu tempelkan dengan Ctrl + V.'
:'Gagal menyalin. Coba buka website melalui HTTPS atau localhost.';
}
}
</script>

</body>
</html>
