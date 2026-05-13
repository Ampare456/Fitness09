<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IRONCLUB — Fitness Membership System</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@300;400;500;600;700&family=Barlow+Condensed:wght@400;600;700&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<style>
:root {
  --bg: #0D0D0D;
  --surface: #141414;
  --card: #1A1A1A;
  --border: #2A2A2A;
  --accent: #E8FF00;
  --accent2: #FF4C00;
  --text: #F0F0F0;
  --muted: #666;
  --success: #00E676;
  --danger: #FF3D3D;
}
* { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior: smooth; }
body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Barlow', sans-serif;
  min-height: 100vh;
}

/* SCROLLBAR */
::-webkit-scrollbar { width: 4px; }
::-webkit-scrollbar-track { background: var(--bg); }
::-webkit-scrollbar-thumb { background: var(--accent); border-radius: 2px; }

/* LAYOUT */
.app { display: flex; min-height: 100vh; }

/* SIDEBAR */
.sidebar {
  width: 240px;
  background: var(--surface);
  border-right: 1px solid var(--border);
  display: flex;
  flex-direction: column;
  position: fixed;
  height: 100vh;
  z-index: 50;
}
.sidebar-logo {
  padding: 2rem 1.5rem;
  border-bottom: 1px solid var(--border);
}
.logo-text {
  font-family: 'Bebas Neue', cursive;
  font-size: 2rem;
  letter-spacing: 0.1em;
  color: var(--text);
}
.logo-text span { color: var(--accent); }
.logo-sub {
  font-size: 0.65rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--muted);
  margin-top: 2px;
}
.sidebar-nav {
  flex: 1;
  padding: 1.5rem 0;
  overflow-y: auto;
}
.nav-section {
  padding: 0.5rem 1.5rem;
  font-size: 0.6rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 0.3rem;
  margin-top: 1rem;
}
.nav-item {
  display: flex;
  align-items: center;
  gap: 0.8rem;
  padding: 0.75rem 1.5rem;
  cursor: pointer;
  transition: all 0.2s;
  border-left: 3px solid transparent;
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--muted);
}
.nav-item:hover { color: var(--text); background: rgba(232,255,0,0.04); }
.nav-item.active {
  color: var(--accent);
  border-left-color: var(--accent);
  background: rgba(232,255,0,0.06);
}
.nav-icon { font-size: 1.1rem; }
.sidebar-footer {
  padding: 1.5rem;
  border-top: 1px solid var(--border);
  font-size: 0.75rem;
  color: var(--muted);
}

/* MAIN */
.main {
  flex: 1;
  margin-left: 240px;
  padding: 2rem;
}

/* HEADER */
.page-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
}
.page-title {
  font-family: 'Bebas Neue', cursive;
  font-size: 2.2rem;
  letter-spacing: 0.05em;
}
.page-title span { color: var(--accent); }
.header-actions { display: flex; gap: 0.75rem; }

/* BUTTONS */
.btn {
  padding: 0.65rem 1.4rem;
  border: none;
  cursor: pointer;
  font-family: 'Barlow', sans-serif;
  font-size: 0.8rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
  transition: all 0.2s;
  border-radius: 2px;
}
.btn-primary { background: var(--accent); color: #000; }
.btn-primary:hover { background: #d4eb00; transform: translateY(-1px); }
.btn-danger { background: var(--danger); color: #fff; }
.btn-danger:hover { background: #e02828; }
.btn-ghost {
  background: transparent;
  color: var(--text);
  border: 1px solid var(--border);
}
.btn-ghost:hover { border-color: var(--accent); color: var(--accent); }
.btn-success { background: var(--success); color: #000; }
.btn-sm { padding: 0.4rem 0.9rem; font-size: 0.72rem; }

/* STATS ROW */
.stats-row {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
  margin-bottom: 2rem;
}
.stat-card {
  background: var(--card);
  border: 1px solid var(--border);
  padding: 1.25rem 1.5rem;
  border-radius: 4px;
  position: relative;
  overflow: hidden;
}
.stat-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 2px;
  background: var(--accent);
}
.stat-card.orange::before { background: var(--accent2); }
.stat-card.green::before { background: var(--success); }
.stat-card.red::before { background: var(--danger); }
.stat-label {
  font-size: 0.7rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 0.5rem;
}
.stat-num {
  font-family: 'Bebas Neue', cursive;
  font-size: 2.5rem;
  color: var(--text);
  line-height: 1;
}
.stat-sub { font-size: 0.75rem; color: var(--muted); margin-top: 0.3rem; }

/* VIEWS */
.view { display: none; }
.view.active { display: block; }

/* TABLE */
.table-container {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 4px;
  overflow: hidden;
}
.table-header {
  padding: 1.2rem 1.5rem;
  border-bottom: 1px solid var(--border);
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.table-title {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 0.85rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--muted);
}
.search-box {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 2px;
  padding: 0.5rem 1rem;
}
.search-box input {
  background: none;
  border: none;
  outline: none;
  color: var(--text);
  font-family: 'Barlow', sans-serif;
  font-size: 0.85rem;
  width: 200px;
}
.search-box input::placeholder { color: var(--muted); }
table { width: 100%; border-collapse: collapse; }
thead tr { border-bottom: 1px solid var(--border); }
th {
  padding: 0.9rem 1.5rem;
  text-align: left;
  font-size: 0.65rem;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--muted);
  font-weight: 600;
}
td { padding: 1rem 1.5rem; font-size: 0.88rem; border-bottom: 1px solid rgba(255,255,255,0.04); }
tr:last-child td { border-bottom: none; }
tr:hover td { background: rgba(255,255,255,0.02); }
.badge {
  display: inline-block;
  padding: 0.2rem 0.7rem;
  border-radius: 2px;
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}
.badge-active { background: rgba(0,230,118,0.15); color: var(--success); }
.badge-expired { background: rgba(255,61,61,0.15); color: var(--danger); }
.badge-pending { background: rgba(232,255,0,0.12); color: var(--accent); }
.member-info { display: flex; align-items: center; gap: 0.75rem; }
.avatar {
  width: 36px; height: 36px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: 'Bebas Neue', cursive;
  font-size: 1rem;
  font-weight: 700;
  flex-shrink: 0;
}
.avatar-name { font-weight: 500; }
.avatar-id { font-size: 0.75rem; color: var(--muted); }
.actions { display: flex; gap: 0.4rem; }

/* MODAL */
.modal-overlay {
  display: none;
  position: fixed; inset: 0;
  background: rgba(0,0,0,0.8);
  z-index: 200;
  align-items: center;
  justify-content: center;
  backdrop-filter: blur(4px);
}
.modal-overlay.open { display: flex; }
.modal {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 6px;
  width: 520px;
  max-height: 90vh;
  overflow-y: auto;
  animation: slideIn 0.25s ease;
}
.modal-lg { width: 700px; }
@keyframes slideIn {
  from { opacity: 0; transform: translateY(-20px); }
  to { opacity: 1; transform: translateY(0); }
}
.modal-header {
  padding: 1.5rem;
  border-bottom: 1px solid var(--border);
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.modal-title {
  font-family: 'Bebas Neue', cursive;
  font-size: 1.4rem;
  letter-spacing: 0.05em;
}
.modal-close {
  background: none;
  border: none;
  color: var(--muted);
  cursor: pointer;
  font-size: 1.4rem;
  line-height: 1;
  padding: 0.2rem;
  transition: color 0.2s;
}
.modal-close:hover { color: var(--text); }
.modal-body { padding: 1.5rem; }
.modal-footer {
  padding: 1.5rem;
  border-top: 1px solid var(--border);
  display: flex;
  justify-content: flex-end;
  gap: 0.75rem;
}

/* FORM */
.form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
.form-group { display: flex; flex-direction: column; gap: 0.4rem; }
.form-group.full { grid-column: span 2; }
label {
  font-size: 0.7rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--muted);
  font-weight: 600;
}
input, select, textarea {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: 2px;
  padding: 0.7rem 1rem;
  color: var(--text);
  font-family: 'Barlow', sans-serif;
  font-size: 0.88rem;
  outline: none;
  transition: border-color 0.2s;
  width: 100%;
}
input:focus, select:focus, textarea:focus { border-color: var(--accent); }
select option { background: var(--card); }
textarea { resize: vertical; min-height: 70px; }

/* QR MODAL */
.qr-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1rem 0;
}
.qr-wrap {
  background: #fff;
  padding: 1.5rem;
  border-radius: 4px;
  margin-bottom: 1.5rem;
}
#qrcode canvas, #qrcode img { display: block; }
.qr-member-name {
  font-family: 'Bebas Neue', cursive;
  font-size: 1.8rem;
  letter-spacing: 0.08em;
  margin-bottom: 0.3rem;
}
.qr-member-id {
  font-size: 0.75rem;
  letter-spacing: 0.2em;
  color: var(--muted);
  text-transform: uppercase;
}
.qr-plan {
  margin-top: 1rem;
  padding: 0.4rem 1.2rem;
  background: rgba(232,255,0,0.1);
  border: 1px solid rgba(232,255,0,0.3);
  color: var(--accent);
  font-size: 0.75rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  font-weight: 600;
  border-radius: 2px;
}

/* CHECKIN VIEW */
.checkin-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem;
}
.checkin-panel {
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 4px;
  padding: 1.5rem;
}
.panel-title {
  font-family: 'Barlow Condensed', sans-serif;
  font-size: 0.85rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 1.2rem;
  padding-bottom: 0.8rem;
  border-bottom: 1px solid var(--border);
}
.checkin-input-wrap {
  display: flex;
  gap: 0.75rem;
  margin-bottom: 1.5rem;
}
.checkin-input-wrap input { flex: 1; }
.checkin-result {
  display: none;
  background: var(--surface);
  border-radius: 4px;
  padding: 1.25rem;
  text-align: center;
  border: 1px solid var(--border);
}
.checkin-result.show { display: block; }
.checkin-success {
  color: var(--success);
  font-family: 'Bebas Neue', cursive;
  font-size: 1.4rem;
  letter-spacing: 0.08em;
  margin-bottom: 0.3rem;
}
.checkin-fail { color: var(--danger); }
.checkin-member-display {
  font-size: 1.1rem;
  font-weight: 600;
  margin: 0.5rem 0 0.2rem;
}
.checkin-time {
  font-size: 0.75rem;
  color: var(--muted);
}
.checkin-log {
  max-height: 340px;
  overflow-y: auto;
}
.log-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 0.75rem 0;
  border-bottom: 1px solid rgba(255,255,255,0.04);
  font-size: 0.85rem;
}
.log-item:last-child { border-bottom: none; }
.log-dot {
  width: 8px; height: 8px;
  border-radius: 50%;
  flex-shrink: 0;
}
.log-dot.in { background: var(--success); }
.log-dot.out { background: var(--accent2); }
.log-name { flex: 1; font-weight: 500; }
.log-time { color: var(--muted); font-size: 0.75rem; }

/* MEMBER DETAIL */
.detail-header {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-bottom: 1.5rem;
}
.detail-avatar {
  width: 70px; height: 70px;
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-family: 'Bebas Neue', cursive;
  font-size: 2rem;
  flex-shrink: 0;
}
.detail-name {
  font-family: 'Bebas Neue', cursive;
  font-size: 1.8rem;
  letter-spacing: 0.05em;
  line-height: 1;
}
.detail-id { font-size: 0.75rem; color: var(--muted); margin-top: 0.3rem; }
.detail-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.75rem;
  margin-bottom: 1.5rem;
}
.detail-item {
  background: var(--surface);
  padding: 0.8rem 1rem;
  border-radius: 2px;
}
.detail-label {
  font-size: 0.65rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 0.3rem;
}
.detail-val { font-size: 0.9rem; font-weight: 500; }
.history-list { max-height: 200px; overflow-y: auto; }
.history-item {
  display: flex;
  justify-content: space-between;
  padding: 0.6rem 0;
  border-bottom: 1px solid rgba(255,255,255,0.04);
  font-size: 0.82rem;
  color: var(--muted);
}
.history-item span:first-child { color: var(--success); }

/* TOAST */
.toast {
  position: fixed;
  bottom: 2rem; right: 2rem;
  background: var(--card);
  border: 1px solid var(--border);
  border-radius: 4px;
  padding: 1rem 1.5rem;
  display: flex;
  align-items: center;
  gap: 0.75rem;
  z-index: 999;
  transform: translateY(100px);
  opacity: 0;
  transition: all 0.3s;
  min-width: 260px;
}
.toast.show { transform: translateY(0); opacity: 1; }
.toast-icon { font-size: 1.2rem; }
.toast-text { font-size: 0.88rem; font-weight: 500; }
.toast-bar {
  position: absolute;
  bottom: 0; left: 0;
  height: 2px;
  background: var(--accent);
  animation: toastBar 3s linear forwards;
  border-radius: 0 0 4px 4px;
}
@keyframes toastBar { from { width: 100%; } to { width: 0%; } }

/* EMPTY STATE */
.empty-state {
  text-align: center;
  padding: 4rem 2rem;
  color: var(--muted);
}
.empty-icon { font-size: 3rem; margin-bottom: 1rem; opacity: 0.3; }
.empty-text { font-size: 0.9rem; }

/* RESPONSIVE */
@media (max-width: 900px) {
  .sidebar { width: 60px; }
  .sidebar-logo { padding: 1rem; }
  .logo-text, .logo-sub, .nav-section, .nav-item span:last-child { display: none; }
  .nav-item { padding: 0.9rem; justify-content: center; }
  .sidebar-footer { display: none; }
  .main { margin-left: 60px; }
  .stats-row { grid-template-columns: repeat(2,1fr); }
  .form-grid { grid-template-columns: 1fr; }
  .form-group.full { grid-column: span 1; }
  .checkin-grid { grid-template-columns: 1fr; }
  .modal { width: 95vw; }
}
</style>
</head>
<body>
<div class="app">

<!-- SIDEBAR -->
<aside class="sidebar">
  <div class="sidebar-logo">
    <div class="logo-text">IRON<span>CLUB</span></div>
    <div class="logo-sub">Fitness Management</div>
  </div>
  <nav class="sidebar-nav">
    <div class="nav-section">เมนูหลัก</div>
    <div class="nav-item active" onclick="showView('dashboard')">
      <span class="nav-icon">📊</span><span>Dashboard</span>
    </div>
    <div class="nav-item" onclick="showView('members')">
      <span class="nav-icon">👥</span><span>สมาชิก</span>
    </div>
    <div class="nav-item" onclick="showView('checkin')">
      <span class="nav-icon">✅</span><span>Check-in</span>
    </div>
    <div class="nav-section">รายงาน</div>
    <div class="nav-item" onclick="showView('history')">
      <span class="nav-icon">📋</span><span>ประวัติ</span>
    </div>
  </nav>
  <div class="sidebar-footer">v1.0 • IRONCLUB</div>
</aside>

<!-- MAIN -->
<main class="main">

  <!-- DASHBOARD -->
  <div class="view active" id="view-dashboard">
    <div class="page-header">
      <h1 class="page-title">DASH<span>BOARD</span></h1>
      <div class="header-actions">
        <button class="btn btn-primary" onclick="openAddMember()">+ เพิ่มสมาชิก</button>
      </div>
    </div>
    <div class="stats-row">
      <div class="stat-card">
        <div class="stat-label">สมาชิกทั้งหมด</div>
        <div class="stat-num" id="stat-total">0</div>
        <div class="stat-sub">คน</div>
      </div>
      <div class="stat-card green">
        <div class="stat-label">แพ็กเกจ Active</div>
        <div class="stat-num" id="stat-active">0</div>
        <div class="stat-sub">คน</div>
      </div>
      <div class="stat-card orange">
        <div class="stat-label">เช็คอินวันนี้</div>
        <div class="stat-num" id="stat-today">0</div>
        <div class="stat-sub">ครั้ง</div>
      </div>
      <div class="stat-card red">
        <div class="stat-label">หมดอายุ</div>
        <div class="stat-num" id="stat-expired">0</div>
        <div class="stat-sub">คน</div>
      </div>
    </div>
    <div class="table-container">
      <div class="table-header">
        <div class="table-title">เช็คอินล่าสุด</div>
      </div>
      <div id="recent-checkins">
        <div class="empty-state">
          <div class="empty-icon">🏋️</div>
          <div class="empty-text">ยังไม่มีการเช็คอินวันนี้</div>
        </div>
      </div>
    </div>
  </div>

  <!-- MEMBERS -->
  <div class="view" id="view-members">
    <div class="page-header">
      <h1 class="page-title">สมา<span>ชิก</span></h1>
      <div class="header-actions">
        <button class="btn btn-primary" onclick="openAddMember()">+ เพิ่มสมาชิก</button>
      </div>
    </div>
    <div class="table-container">
      <div class="table-header">
        <div class="table-title">รายชื่อสมาชิกทั้งหมด</div>
        <div class="search-box">
          <span>🔍</span>
          <input type="text" placeholder="ค้นหาชื่อ / รหัส..." id="search-input" oninput="renderMembers()">
        </div>
      </div>
      <div style="overflow-x:auto">
        <table>
          <thead>
            <tr>
              <th>สมาชิก</th>
              <th>เบอร์โทร</th>
              <th>แพ็กเกจ</th>
              <th>วันหมดอายุ</th>
              <th>สถานะ</th>
              <th>จัดการ</th>
            </tr>
          </thead>
          <tbody id="members-tbody"></tbody>
        </table>
      </div>
      <div id="members-empty" class="empty-state" style="display:none">
        <div class="empty-icon">👤</div>
        <div class="empty-text">ยังไม่มีสมาชิก กด "+ เพิ่มสมาชิก" เพื่อเริ่ม</div>
      </div>
    </div>
  </div>

  <!-- CHECKIN -->
  <div class="view" id="view-checkin">
    <div class="page-header">
      <h1 class="page-title">CHECK<span>-IN</span></h1>
    </div>
    <div class="checkin-grid">
      <div class="checkin-panel">
        <div class="panel-title">🔍 ค้นหาหรือกรอกรหัสสมาชิก</div>
        <div class="checkin-input-wrap">
          <input type="text" id="checkin-id" placeholder="กรอกรหัสสมาชิก เช่น IC-0001" onkeydown="if(event.key==='Enter')doCheckin()">
          <button class="btn btn-primary" onclick="doCheckin()">CHECK IN</button>
        </div>
        <div class="checkin-result" id="checkin-result"></div>
        <div style="margin-top:1.5rem">
          <div class="panel-title">หรือเลือกจากรายชื่อ</div>
          <div id="quick-member-list" style="max-height:260px;overflow-y:auto"></div>
        </div>
      </div>
      <div class="checkin-panel">
        <div class="panel-title">📋 ประวัติเช็คอินวันนี้</div>
        <div class="checkin-log" id="checkin-log">
          <div class="empty-state" style="padding:2rem">
            <div class="empty-icon">📭</div>
            <div class="empty-text">ยังไม่มีการเช็คอิน</div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- HISTORY -->
  <div class="view" id="view-history">
    <div class="page-header">
      <h1 class="page-title">ประ<span>วัติ</span></h1>
    </div>
    <div class="table-container">
      <div class="table-header">
        <div class="table-title">ประวัติเช็คอินทั้งหมด</div>
      </div>
      <div style="overflow-x:auto">
        <table>
          <thead>
            <tr><th>สมาชิก</th><th>รหัส</th><th>วันที่</th><th>เวลา</th><th>สถานะ</th></tr>
          </thead>
          <tbody id="history-tbody"></tbody>
        </table>
      </div>
      <div id="history-empty" class="empty-state" style="display:none">
        <div class="empty-icon">📋</div>
        <div class="empty-text">ยังไม่มีประวัติ</div>
      </div>
    </div>
  </div>

</main>
</div>

<!-- ADD/EDIT MEMBER MODAL -->
<div class="modal-overlay" id="modal-member">
  <div class="modal">
    <div class="modal-header">
      <div class="modal-title" id="modal-member-title">เพิ่มสมาชิกใหม่</div>
      <button class="modal-close" onclick="closeModal('modal-member')">✕</button>
    </div>
    <div class="modal-body">
      <div class="form-grid">
        <div class="form-group">
          <label>ชื่อ *</label>
          <input type="text" id="f-fname" placeholder="ชื่อจริง">
        </div>
        <div class="form-group">
          <label>นามสกุล *</label>
          <input type="text" id="f-lname" placeholder="นามสกุล">
        </div>
        <div class="form-group">
          <label>เบอร์โทร *</label>
          <input type="tel" id="f-phone" placeholder="08X-XXX-XXXX">
        </div>
        <div class="form-group">
          <label>อีเมล</label>
          <input type="email" id="f-email" placeholder="example@email.com">
        </div>
        <div class="form-group">
          <label>เพศ</label>
          <select id="f-gender">
            <option value="ชาย">ชาย</option>
            <option value="หญิง">หญิง</option>
            <option value="อื่นๆ">อื่นๆ</option>
          </select>
        </div>
        <div class="form-group">
          <label>วันเกิด</label>
          <input type="date" id="f-dob">
        </div>
        <div class="form-group">
          <label>แพ็กเกจ *</label>
          <select id="f-plan">
            <option value="รายเดือน">รายเดือน (฿800)</option>
            <option value="3 เดือน">3 เดือน (฿2,100)</option>
            <option value="6 เดือน">6 เดือน (฿3,600)</option>
            <option value="รายปี">รายปี (฿6,000)</option>
            <option value="รายครั้ง">รายครั้ง (฿100)</option>
          </select>
        </div>
        <div class="form-group">
          <label>วันเริ่มแพ็กเกจ</label>
          <input type="date" id="f-start">
        </div>
        <div class="form-group full">
          <label>หมายเหตุ</label>
          <textarea id="f-note" placeholder="ข้อมูลเพิ่มเติม..."></textarea>
        </div>
      </div>
    </div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeModal('modal-member')">ยกเลิก</button>
      <button class="btn btn-primary" onclick="saveMember()">บันทึก</button>
    </div>
  </div>
</div>

<!-- QR MODAL -->
<div class="modal-overlay" id="modal-qr">
  <div class="modal">
    <div class="modal-header">
      <div class="modal-title">QR Code สมาชิก</div>
      <button class="modal-close" onclick="closeModal('modal-qr')">✕</button>
    </div>
    <div class="modal-body">
      <div class="qr-container">
        <div class="qr-wrap"><div id="qrcode"></div></div>
        <div class="qr-member-name" id="qr-name"></div>
        <div class="qr-member-id" id="qr-id"></div>
        <div class="qr-plan" id="qr-plan"></div>
      </div>
    </div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeModal('modal-qr')">ปิด</button>
      <button class="btn btn-primary" onclick="printQR()">🖨 พิมพ์</button>
    </div>
  </div>
</div>

<!-- MEMBER DETAIL MODAL -->
<div class="modal-overlay" id="modal-detail">
  <div class="modal modal-lg">
    <div class="modal-header">
      <div class="modal-title">ข้อมูลสมาชิก</div>
      <button class="modal-close" onclick="closeModal('modal-detail')">✕</button>
    </div>
    <div class="modal-body" id="modal-detail-body"></div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeModal('modal-detail')">ปิด</button>
    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast">
  <span class="toast-icon" id="toast-icon">✅</span>
  <span class="toast-text" id="toast-text"></span>
  <div class="toast-bar" id="toast-bar"></div>
</div>

<script>
// ==================== STATE ====================
let members = JSON.parse(localStorage.getItem('ic-members') || '[]');
let checkins = JSON.parse(localStorage.getItem('ic-checkins') || '[]');
let editingId = null;

const PLAN_DAYS = {
  'รายเดือน': 30, '3 เดือน': 90,
  '6 เดือน': 180, 'รายปี': 365, 'รายครั้ง': 1
};
const AVATAR_COLORS = ['#E8FF00','#FF4C00','#00E676','#00BCD4','#FF80AB','#FFAB40'];

function save() {
  localStorage.setItem('ic-members', JSON.stringify(members));
  localStorage.setItem('ic-checkins', JSON.stringify(checkins));
}

// ==================== NAVIGATION ====================
function showView(v) {
  document.querySelectorAll('.view').forEach(el => el.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(el => el.classList.remove('active'));
  document.getElementById('view-' + v).classList.add('active');
  event.currentTarget.classList.add('active');
  if (v === 'members') renderMembers();
  if (v === 'dashboard') renderDashboard();
  if (v === 'checkin') renderCheckinView();
  if (v === 'history') renderHistory();
}

// ==================== UTILS ====================
function genId() {
  const n = members.length + 1;
  return 'IC-' + String(n).padStart(4, '0');
}
function getExpiry(start, plan) {
  const d = new Date(start);
  d.setDate(d.getDate() + (PLAN_DAYS[plan] || 30));
  return d.toISOString().split('T')[0];
}
function isActive(m) {
  if (m.plan === 'รายครั้ง') return false;
  return new Date(m.expiry) >= new Date();
}
function fmtDate(d) {
  if (!d) return '-';
  return new Date(d).toLocaleDateString('th-TH', { day:'2-digit', month:'short', year:'numeric' });
}
function fmtTime(d) {
  return new Date(d).toLocaleTimeString('th-TH', { hour:'2-digit', minute:'2-digit' });
}
function avatarColor(id) {
  const i = parseInt(id.replace('IC-','')) % AVATAR_COLORS.length;
  return AVATAR_COLORS[i];
}
function initials(name) {
  const parts = name.trim().split(' ');
  return parts.length > 1 ? (parts[0][0] + parts[1][0]).toUpperCase() : name.slice(0,2).toUpperCase();
}
function isToday(dateStr) {
  const d = new Date(dateStr);
  const t = new Date();
  return d.getFullYear() === t.getFullYear() && d.getMonth() === t.getMonth() && d.getDate() === t.getDate();
}

// ==================== TOAST ====================
let toastTimer;
function showToast(msg, icon = '✅') {
  clearTimeout(toastTimer);
  const t = document.getElementById('toast');
  const bar = document.getElementById('toast-bar');
  document.getElementById('toast-text').textContent = msg;
  document.getElementById('toast-icon').textContent = icon;
  bar.style.animation = 'none'; bar.offsetHeight;
  bar.style.animation = 'toastBar 3s linear forwards';
  t.classList.add('show');
  toastTimer = setTimeout(() => t.classList.remove('show'), 3200);
}

// ==================== DASHBOARD ====================
function renderDashboard() {
  const today = checkins.filter(c => isToday(c.time));
  const active = members.filter(isActive);
  const expired = members.filter(m => !isActive(m) && m.plan !== 'รายครั้ง');
  document.getElementById('stat-total').textContent = members.length;
  document.getElementById('stat-active').textContent = active.length;
  document.getElementById('stat-today').textContent = today.length;
  document.getElementById('stat-expired').textContent = expired.length;

  const rc = document.getElementById('recent-checkins');
  const todayList = [...today].reverse().slice(0, 8);
  if (!todayList.length) {
    rc.innerHTML = `<div class="empty-state"><div class="empty-icon">🏋️</div><div class="empty-text">ยังไม่มีการเช็คอินวันนี้</div></div>`;
    return;
  }
  rc.innerHTML = `<div style="overflow-x:auto"><table><thead><tr><th>สมาชิก</th><th>รหัส</th><th>เวลา</th><th>แพ็กเกจ</th></tr></thead><tbody>
    ${todayList.map(c => {
      const m = members.find(x => x.id === c.memberId);
      if (!m) return '';
      return `<tr>
        <td><div class="member-info">
          <div class="avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div>
          <div><div class="avatar-name">${m.name}</div></div>
        </div></td>
        <td style="color:var(--muted)">${m.id}</td>
        <td>${fmtTime(c.time)}</td>
        <td><span class="badge badge-active">${m.plan}</span></td>
      </tr>`;
    }).join('')}
  </tbody></table></div>`;
}

// ==================== MEMBERS ====================
function renderMembers() {
  const q = (document.getElementById('search-input')?.value || '').toLowerCase();
  const list = members.filter(m => !q || m.name.toLowerCase().includes(q) || m.id.toLowerCase().includes(q) || m.phone.includes(q));
  const tbody = document.getElementById('members-tbody');
  const empty = document.getElementById('members-empty');

  if (!list.length) {
    tbody.innerHTML = '';
    empty.style.display = 'block';
    return;
  }
  empty.style.display = 'none';

  tbody.innerHTML = list.map(m => {
    const active = isActive(m);
    const badge = m.plan === 'รายครั้ง' ? `<span class="badge badge-pending">รายครั้ง</span>`
      : active ? `<span class="badge badge-active">Active</span>`
      : `<span class="badge badge-expired">หมดอายุ</span>`;
    return `<tr>
      <td><div class="member-info">
        <div class="avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div>
        <div><div class="avatar-name">${m.name}</div><div class="avatar-id">${m.id}</div></div>
      </div></td>
      <td>${m.phone}</td>
      <td>${m.plan}</td>
      <td style="color:${active?'var(--text)':'var(--danger)'}">${m.plan === 'รายครั้ง' ? '-' : fmtDate(m.expiry)}</td>
      <td>${badge}</td>
      <td><div class="actions">
        <button class="btn btn-ghost btn-sm" onclick="viewMember('${m.id}')">ดู</button>
        <button class="btn btn-ghost btn-sm" onclick="showQR('${m.id}')">QR</button>
        <button class="btn btn-ghost btn-sm" onclick="editMember('${m.id}')">แก้ไข</button>
        <button class="btn btn-danger btn-sm" onclick="deleteMember('${m.id}')">ลบ</button>
      </div></td>
    </tr>`;
  }).join('');
}

// ==================== ADD/EDIT MEMBER ====================
function openAddMember() {
  editingId = null;
  document.getElementById('modal-member-title').textContent = 'เพิ่มสมาชิกใหม่';
  ['fname','lname','phone','email','note'].forEach(f => document.getElementById('f-'+f).value = '');
  document.getElementById('f-gender').value = 'ชาย';
  document.getElementById('f-plan').value = 'รายเดือน';
  document.getElementById('f-start').value = new Date().toISOString().split('T')[0];
  document.getElementById('f-dob').value = '';
  openModal('modal-member');
}

function editMember(id) {
  const m = members.find(x => x.id === id);
  if (!m) return;
  editingId = id;
  document.getElementById('modal-member-title').textContent = 'แก้ไขข้อมูลสมาชิก';
  const [fn, ...ln] = m.name.split(' ');
  document.getElementById('f-fname').value = fn;
  document.getElementById('f-lname').value = ln.join(' ');
  document.getElementById('f-phone').value = m.phone;
  document.getElementById('f-email').value = m.email || '';
  document.getElementById('f-gender').value = m.gender || 'ชาย';
  document.getElementById('f-dob').value = m.dob || '';
  document.getElementById('f-plan').value = m.plan;
  document.getElementById('f-start').value = m.start;
  document.getElementById('f-note').value = m.note || '';
  openModal('modal-member');
}

function saveMember() {
  const fn = document.getElementById('f-fname').value.trim();
  const ln = document.getElementById('f-lname').value.trim();
  const phone = document.getElementById('f-phone').value.trim();
  const plan = document.getElementById('f-plan').value;
  const start = document.getElementById('f-start').value || new Date().toISOString().split('T')[0];

  if (!fn || !ln || !phone) { showToast('กรุณากรอกข้อมูลที่จำเป็น', '⚠️'); return; }

  const name = fn + ' ' + ln;
  const expiry = getExpiry(start, plan);

  if (editingId) {
    const i = members.findIndex(x => x.id === editingId);
    members[i] = { ...members[i], name, phone, plan, start, expiry,
      email: document.getElementById('f-email').value,
      gender: document.getElementById('f-gender').value,
      dob: document.getElementById('f-dob').value,
      note: document.getElementById('f-note').value };
    showToast('อัปเดตข้อมูลสมาชิกแล้ว', '✏️');
  } else {
    members.push({
      id: genId(), name, phone, plan, start, expiry,
      email: document.getElementById('f-email').value,
      gender: document.getElementById('f-gender').value,
      dob: document.getElementById('f-dob').value,
      note: document.getElementById('f-note').value,
      joinDate: new Date().toISOString()
    });
    showToast('เพิ่มสมาชิกใหม่แล้ว! 🎉', '✅');
  }
  save(); closeModal('modal-member');
  renderMembers(); renderDashboard();
}

function deleteMember(id) {
  if (!confirm('ต้องการลบสมาชิกนี้?')) return;
  members = members.filter(m => m.id !== id);
  save(); renderMembers(); renderDashboard();
  showToast('ลบสมาชิกแล้ว', '🗑️');
}

// ==================== VIEW DETAIL ====================
function viewMember(id) {
  const m = members.find(x => x.id === id);
  if (!m) return;
  const mCheckins = checkins.filter(c => c.memberId === id);
  const body = document.getElementById('modal-detail-body');
  body.innerHTML = `
    <div class="detail-header">
      <div class="detail-avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div>
      <div>
        <div class="detail-name">${m.name}</div>
        <div class="detail-id">${m.id} · เข้าร่วม ${fmtDate(m.joinDate)}</div>
        <div style="margin-top:0.5rem">${isActive(m) ? '<span class="badge badge-active">Active</span>' : '<span class="badge badge-expired">หมดอายุ</span>'}</div>
      </div>
    </div>
    <div class="detail-grid">
      <div class="detail-item"><div class="detail-label">เบอร์โทร</div><div class="detail-val">${m.phone}</div></div>
      <div class="detail-item"><div class="detail-label">อีเมล</div><div class="detail-val">${m.email || '-'}</div></div>
      <div class="detail-item"><div class="detail-label">แพ็กเกจ</div><div class="detail-val">${m.plan}</div></div>
      <div class="detail-item"><div class="detail-label">วันหมดอายุ</div><div class="detail-val" style="color:${isActive(m)?'var(--success)':'var(--danger)'}">${m.plan==='รายครั้ง'?'-':fmtDate(m.expiry)}</div></div>
      <div class="detail-item"><div class="detail-label">เพศ</div><div class="detail-val">${m.gender || '-'}</div></div>
      <div class="detail-item"><div class="detail-label">เช็คอินทั้งหมด</div><div class="detail-val">${mCheckins.length} ครั้ง</div></div>
    </div>
    ${m.note ? `<div class="detail-item" style="margin-bottom:1rem"><div class="detail-label">หมายเหตุ</div><div class="detail-val">${m.note}</div></div>` : ''}
    <div style="font-size:0.7rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);margin-bottom:0.8rem">ประวัติเช็คอินล่าสุด</div>
    <div class="history-list">
      ${mCheckins.length ? [...mCheckins].reverse().slice(0,20).map(c =>
        `<div class="history-item"><span>✅ เช็คอิน</span><span>${fmtDate(c.time)} ${fmtTime(c.time)}</span></div>`
      ).join('') : '<div style="color:var(--muted);font-size:0.85rem">ยังไม่มีประวัติ</div>'}
    </div>
  `;
  openModal('modal-detail');
}

// ==================== QR CODE ====================
function showQR(id) {
  const m = members.find(x => x.id === id);
  if (!m) return;
  document.getElementById('qr-name').textContent = m.name;
  document.getElementById('qr-id').textContent = m.id;
  document.getElementById('qr-plan').textContent = '📦 ' + m.plan;
  const qrEl = document.getElementById('qrcode');
  qrEl.innerHTML = '';
  new QRCode(qrEl, {
    text: m.id,
    width: 200, height: 200,
    colorDark: '#000000',
    colorLight: '#ffffff',
    correctLevel: QRCode.CorrectLevel.H
  });
  openModal('modal-qr');
}

function printQR() {
  const qrEl = document.getElementById('qrcode');
  const name = document.getElementById('qr-name').textContent;
  const id = document.getElementById('qr-id').textContent;
  const canvas = qrEl.querySelector('canvas');
  if (!canvas) return;
  const win = window.open('', '_blank');
  win.document.write(`<html><head><title>QR - ${name}</title><style>
    body{font-family:sans-serif;text-align:center;padding:2rem;background:#fff}
    h2{font-size:1.5rem;margin-bottom:0.5rem}
    p{color:#666;font-size:0.9rem;margin-bottom:1rem}
    canvas{display:block;margin:0 auto}
    @media print{body{padding:0}}
  </style></head><body>
    <h2>${name}</h2><p>${id}</p>
    <img src="${canvas.toDataURL()}" style="width:200px;height:200px">
    <p style="margin-top:1rem;font-size:0.8rem;color:#999">IRONCLUB Fitness</p>
    <script>window.onload=()=>window.print()<\/script>
  </body></html>`);
  win.document.close();
}

// ==================== CHECK-IN ====================
function renderCheckinView() {
  // Quick list
  const ql = document.getElementById('quick-member-list');
  if (!members.length) {
    ql.innerHTML = `<div style="color:var(--muted);font-size:0.85rem;padding:0.5rem">ยังไม่มีสมาชิก</div>`;
  } else {
    ql.innerHTML = members.map(m => `
      <div style="display:flex;align-items:center;gap:0.75rem;padding:0.6rem;border-radius:2px;cursor:pointer;transition:background 0.2s"
        onmouseover="this.style.background='rgba(255,255,255,0.04)'" onmouseout="this.style.background='none'"
        onclick="quickCheckin('${m.id}')">
        <div class="avatar" style="background:${avatarColor(m.id)};color:#000;width:32px;height:32px;font-size:0.85rem">${initials(m.name)}</div>
        <div style="flex:1"><div style="font-size:0.88rem;font-weight:500">${m.name}</div><div style="font-size:0.72rem;color:var(--muted)">${m.id}</div></div>
        <span class="badge ${isActive(m)?'badge-active':'badge-expired'}" style="font-size:0.62rem">${isActive(m)?'Active':'หมด'}</span>
      </div>`).join('');
  }
  renderCheckinLog();
}

function quickCheckin(id) {
  document.getElementById('checkin-id').value = id;
  doCheckin();
}

function doCheckin() {
  const input = document.getElementById('checkin-id').value.trim().toUpperCase();
  const result = document.getElementById('checkin-result');
  if (!input) { showToast('กรุณากรอกรหัสสมาชิก', '⚠️'); return; }

  const m = members.find(x => x.id === input);
  if (!m) {
    result.className = 'checkin-result show';
    result.innerHTML = `<div class="checkin-success checkin-fail">❌ ไม่พบสมาชิก</div><div class="checkin-time">รหัส "${input}" ไม่มีในระบบ</div>`;
    showToast('ไม่พบสมาชิก', '❌');
    return;
  }
  if (!isActive(m) && m.plan !== 'รายครั้ง') {
    result.className = 'checkin-result show';
    result.innerHTML = `<div class="checkin-success checkin-fail">⚠️ แพ็กเกจหมดอายุ</div><div class="checkin-member-display">${m.name}</div><div class="checkin-time">หมดอายุเมื่อ ${fmtDate(m.expiry)}</div>`;
    showToast('แพ็กเกจของ ' + m.name + ' หมดอายุแล้ว', '⚠️');
    return;
  }

  const entry = { memberId: m.id, time: new Date().toISOString() };
  checkins.push(entry);
  save();

  result.className = 'checkin-result show';
  result.innerHTML = `
    <div class="checkin-success">✅ เช็คอินสำเร็จ!</div>
    <div class="checkin-member-display">${m.name}</div>
    <div class="checkin-time">${m.id} · ${new Date().toLocaleTimeString('th-TH')}</div>
    <div style="margin-top:0.8rem"><span class="badge badge-active">${m.plan}</span></div>`;
  showToast(m.name + ' เช็คอินแล้ว 💪', '✅');
  document.getElementById('checkin-id').value = '';
  renderCheckinLog();
  renderDashboard();
}

function renderCheckinLog() {
  const log = document.getElementById('checkin-log');
  const today = checkins.filter(c => isToday(c.time));
  if (!today.length) {
    log.innerHTML = `<div class="empty-state" style="padding:2rem"><div class="empty-icon">📭</div><div class="empty-text">ยังไม่มีการเช็คอิน</div></div>`;
    return;
  }
  log.innerHTML = [...today].reverse().map(c => {
    const m = members.find(x => x.id === c.memberId);
    if (!m) return '';
    return `<div class="log-item">
      <div class="log-dot in"></div>
      <div class="avatar" style="background:${avatarColor(m.id)};color:#000;width:28px;height:28px;font-size:0.75rem;flex-shrink:0">${initials(m.name)}</div>
      <div class="log-name">${m.name}</div>
      <div class="log-time">${fmtTime(c.time)}</div>
    </div>`;
  }).join('');
}

// ==================== HISTORY ====================
function renderHistory() {
  const tbody = document.getElementById('history-tbody');
  const empty = document.getElementById('history-empty');
  if (!checkins.length) { tbody.innerHTML = ''; empty.style.display = 'block'; return; }
  empty.style.display = 'none';
  tbody.innerHTML = [...checkins].reverse().map(c => {
    const m = members.find(x => x.id === c.memberId);
    if (!m) return '';
    return `<tr>
      <td><div class="member-info">
        <div class="avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div>
        <div class="avatar-name">${m.name}</div>
      </div></td>
      <td style="color:var(--muted)">${m.id}</td>
      <td>${fmtDate(c.time)}</td>
      <td>${fmtTime(c.time)}</td>
      <td><span class="badge badge-active">เช็คอิน</span></td>
    </tr>`;
  }).join('');
}

// ==================== MODAL ====================
function openModal(id) { document.getElementById(id).classList.add('open'); }
function closeModal(id) { document.getElementById(id).classList.remove('open'); }
document.querySelectorAll('.modal-overlay').forEach(o => {
  o.addEventListener('click', e => { if (e.target === o) o.classList.remove('open'); });
});

// ==================== INIT ====================
renderDashboard();

// Sample data if empty
if (!members.length) {
  const samples = [
    { name:'สมชาย ใจดี', phone:'081-234-5678', plan:'รายเดือน', gender:'ชาย' },
    { name:'สมหญิง สวยงาม', phone:'082-345-6789', plan:'3 เดือน', gender:'หญิง' },
    { name:'วิชัย กล้าแกร่ง', phone:'083-456-7890', plan:'รายปี', gender:'ชาย' },
  ];
  samples.forEach((s, i) => {
    const start = new Date(); start.setDate(start.getDate() - i * 10);
    const startStr = start.toISOString().split('T')[0];
    members.push({
      id: genId(), name: s.name, phone: s.phone, plan: s.plan,
      start: startStr, expiry: getExpiry(startStr, s.plan),
      gender: s.gender, email: '', dob: '', note: '',
      joinDate: start.toISOString()
    });
  });
  save(); renderDashboard();
}
</script>
</body>
</html>
