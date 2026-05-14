<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IRONCLUB PRO — Fitness Management</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@300;400;500;600;700&family=Barlow+Condensed:wght@400;600;700&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<style>
:root{--bg:#0D0D0D;--surface:#141414;--card:#1A1A1A;--border:#2A2A2A;--accent:#E8FF00;--accent2:#FF4C00;--text:#F0F0F0;--muted:#666;--success:#00E676;--danger:#FF3D3D;--info:#00B4D8;}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--bg);color:var(--text);font-family:'Barlow',sans-serif;min-height:100vh;}
::-webkit-scrollbar{width:4px;}::-webkit-scrollbar-track{background:var(--bg);}::-webkit-scrollbar-thumb{background:var(--accent);border-radius:2px;}
.app{display:flex;min-height:100vh;}

/* SIDEBAR */
.sidebar{width:240px;background:var(--surface);border-right:1px solid var(--border);display:flex;flex-direction:column;position:fixed;height:100vh;z-index:50;}
.sidebar-logo{padding:1.5rem;border-bottom:1px solid var(--border);}
.logo-text{font-family:'Bebas Neue',cursive;font-size:1.8rem;letter-spacing:0.1em;}
.logo-text span{color:var(--accent);}
.logo-badge{display:inline-block;background:var(--accent);color:#000;font-size:0.55rem;font-weight:700;letter-spacing:0.1em;padding:1px 5px;border-radius:2px;margin-left:4px;vertical-align:middle;}
.logo-sub{font-size:0.6rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--muted);margin-top:2px;}
.sidebar-nav{flex:1;padding:1rem 0;overflow-y:auto;}
.nav-section{padding:0.4rem 1.5rem;font-size:0.58rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--muted);margin-bottom:0.2rem;margin-top:0.8rem;}
.nav-item{display:flex;align-items:center;gap:0.75rem;padding:0.65rem 1.5rem;cursor:pointer;transition:all 0.2s;border-left:3px solid transparent;font-size:0.88rem;font-weight:500;color:var(--muted);}
.nav-item:hover{color:var(--text);background:rgba(232,255,0,0.04);}
.nav-item.active{color:var(--accent);border-left-color:var(--accent);background:rgba(232,255,0,0.06);}
.nav-icon{font-size:1rem;width:20px;text-align:center;}
.sidebar-footer{padding:1rem 1.5rem;border-top:1px solid var(--border);font-size:0.72rem;color:var(--muted);}

/* MAIN */
.main{flex:1;margin-left:240px;padding:2rem;}
.page-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:2rem;flex-wrap:wrap;gap:1rem;}
.page-title{font-family:'Bebas Neue',cursive;font-size:2rem;letter-spacing:0.05em;}
.page-title span{color:var(--accent);}
.header-actions{display:flex;gap:0.6rem;flex-wrap:wrap;}

/* BUTTONS */
.btn{padding:0.6rem 1.2rem;border:none;cursor:pointer;font-family:'Barlow',sans-serif;font-size:0.78rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;transition:all 0.2s;border-radius:2px;}
.btn-primary{background:var(--accent);color:#000;}
.btn-primary:hover{background:#d4eb00;transform:translateY(-1px);}
.btn-danger{background:var(--<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>IRONCLUB PRO — Fitness Management</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow:wght@300;400;500;600;700&family=Barlow+Condensed:wght@400;600;700&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<style>
:root{--bg:#0D0D0D;--surface:#141414;--card:#1A1A1A;--border:#2A2A2A;--accent:#E8FF00;--accent2:#FF4C00;--text:#F0F0F0;--muted:#666;--success:#00E676;--danger:#FF3D3D;--info:#00B4D8;}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{background:var(--bg);color:var(--text);font-family:'Barlow',sans-serif;min-height:100vh;}
::-webkit-scrollbar{width:4px;}::-webkit-scrollbar-track{background:var(--bg);}::-webkit-scrollbar-thumb{background:var(--accent);border-radius:2px;}
.app{display:flex;min-height:100vh;}

/* SIDEBAR */
.sidebar{width:240px;background:var(--surface);border-right:1px solid var(--border);display:flex;flex-direction:column;position:fixed;height:100vh;z-index:50;}
.sidebar-logo{padding:1.5rem;border-bottom:1px solid var(--border);}
.logo-text{font-family:'Bebas Neue',cursive;font-size:1.8rem;letter-spacing:0.1em;}
.logo-text span{color:var(--accent);}
.logo-badge{display:inline-block;background:var(--accent);color:#000;font-size:0.55rem;font-weight:700;letter-spacing:0.1em;padding:1px 5px;border-radius:2px;margin-left:4px;vertical-align:middle;}
.logo-sub{font-size:0.6rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--muted);margin-top:2px;}
.sidebar-nav{flex:1;padding:1rem 0;overflow-y:auto;}
.nav-section{padding:0.4rem 1.5rem;font-size:0.58rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--muted);margin-bottom:0.2rem;margin-top:0.8rem;}
.nav-item{display:flex;align-items:center;gap:0.75rem;padding:0.65rem 1.5rem;cursor:pointer;transition:all 0.2s;border-left:3px solid transparent;font-size:0.88rem;font-weight:500;color:var(--muted);}
.nav-item:hover{color:var(--text);background:rgba(232,255,0,0.04);}
.nav-item.active{color:var(--accent);border-left-color:var(--accent);background:rgba(232,255,0,0.06);}
.nav-icon{font-size:1rem;width:20px;text-align:center;}
.sidebar-footer{padding:1rem 1.5rem;border-top:1px solid var(--border);font-size:0.72rem;color:var(--muted);}

/* MAIN */
.main{flex:1;margin-left:240px;padding:2rem;}
.page-header{display:flex;justify-content:space-between;align-items:center;margin-bottom:2rem;flex-wrap:wrap;gap:1rem;}
.page-title{font-family:'Bebas Neue',cursive;font-size:2rem;letter-spacing:0.05em;}
.page-title span{color:var(--accent);}
.header-actions{display:flex;gap:0.6rem;flex-wrap:wrap;}

/* BUTTONS */
.btn{padding:0.6rem 1.2rem;border:none;cursor:pointer;font-family:'Barlow',sans-serif;font-size:0.78rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;transition:all 0.2s;border-radius:2px;}
.btn-primary{background:var(--accent);color:#000;}
.btn-primary:hover{background:#d4eb00;transform:translateY(-1px);}
.btn-danger{background:var(--danger);color:#fff;}
.btn-danger:hover{background:#e02828;}
.btn-ghost{background:transparent;color:var(--text);border:1px solid var(--border);}
.btn-ghost:hover{border-color:var(--accent);color:var(--accent);}
.btn-success{background:var(--success);color:#000;}
.btn-success:hover{background:#00cc6a;}
.btn-info{background:var(--info);color:#000;}
/* STATS */
.stats-row{display:grid;grid-template-columns:repeat(5,1fr);gap:0.8rem;margin-bottom:1.5rem;}
.stat-card{background:var(--card);border:1px solid var(--border);padding:1.1rem 1.2rem;border-radius:4px;position:relative;overflow:hidden;}
.stat-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:var(--accent);}
.stat-card.orange::before{background:var(--accent2);}
.stat-card.green::before{background:var(--success);}
.stat-card.red::before{background:var(--danger);}
.stat-card.blue::before{background:var(--info);}
.stat-label{font-size:0.65rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);margin-bottom:0.4rem;}
.stat-num{font-family:'Bebas Neue',cursive;font-size:2.2rem;color:var(--text);line-height:1;}
.stat-sub{font-size:0.7rem;color:var(--muted);margin-top:0.2rem;}

/* VIEW */
.view{display:none;}.view.active{display:block;}

/* TABLE */
.table-container{background:var(--card);border:1px solid var(--border);border-radius:4px;overflow:hidden;}
.table-header{padding:1rem 1.5rem;border-bottom:1px solid var(--border);display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:0.75rem;}
.table-title{font-family:'Barlow Condensed',sans-serif;font-size:0.82rem;font-weight:600;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);}
.search-box{display:flex;align-items:center;gap:0.5rem;background:var(--surface);border:1px solid var(--border);border-radius:2px;padding:0.45rem 0.9rem;}
.search-box input{background:none;border:none;outline:none;color:var(--text);font-family:'Barlow',sans-serif;font-size:0.83rem;width:180px;}
.search-box input::placeholder{color:var(--muted);}
table{width:100%;border-collapse:collapse;}
thead tr{border-bottom:1px solid var(--border);}
th{padding:0.8rem 1.2rem;text-align:left;font-size:0.62rem;letter-spacing:0.2em;text-transform:uppercase;color:var(--muted);font-weight:600;}
td{padding:0.85rem 1.2rem;font-size:0.85rem;border-bottom:1px solid rgba(255,255,255,0.04);}
tr:last-child td{border-bottom:none;}
tr:hover td{background:rgba(255,255,255,0.02);}
.badge{display:inline-block;padding:0.18rem 0.65rem;border-radius:2px;font-size:0.67rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;}
.badge-active{background:rgba(0,230,118,0.15);color:var(--success);}
.badge-expired{background:rgba(255,61,61,0.15);color:var(--danger);}
.badge-pending{background:rgba(232,255,0,0.12);color:var(--accent);}
.badge-paid{background:rgba(0,230,118,0.15);color:var(--success);}
.badge-unpaid{background:rgba(255,61,61,0.15);color:var(--danger);}
.member-info{display:flex;align-items:center;gap:0.7rem;}
.avatar{width:34px;height:34px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:'Bebas Neue',cursive;font-size:0.95rem;flex-shrink:0;}
.actions{display:flex;gap:0.3rem;flex-wrap:wrap;}

/* MODAL */
.modal-overlay{display:none;position:fixed;inset:0;background:rgba(0,0,0,0.82);z-index:200;align-items:center;justify-content:center;backdrop-filter:blur(4px);}
.modal-overlay.open{display:flex;}
.modal{background:var(--card);border:1px solid var(--border);border-radius:6px;width:540px;max-height:90vh;overflow-y:auto;animation:slideIn 0.25s ease;}
.modal-lg{width:720px;}
.modal-xl{width:860px;}
@keyframes slideIn{from{opacity:0;transform:translateY(-20px);}to{opacity:1;transform:translateY(0);}}
.modal-header{padding:1.3rem 1.5rem;border-bottom:1px solid var(--border);display:flex;justify-content:space-between;align-items:center;}
.modal-title{font-family:'Bebas Neue',cursive;font-size:1.3rem;letter-spacing:0.05em;}
.modal-close{background:none;border:none;color:var(--muted);cursor:pointer;font-size:1.3rem;padding:0.2rem;transition:color 0.2s;}
.modal-close:hover{color:var(--text);}
.modal-body{padding:1.5rem;}
.modal-footer{padding:1.3rem 1.5rem;border-top:1px solid var(--border);display:flex;justify-content:flex-end;gap:0.6rem;}

/* FORM */
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:0.9rem;}
.form-group{display:flex;flex-direction:column;gap:0.35rem;}
.form-group.full{grid-column:span 2;}
label{font-size:0.67rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);font-weight:600;}
input,select,textarea{background:var(--surface);border:1px solid var(--border);border-radius:2px;padding:0.65rem 0.9rem;color:var(--text);font-family:'Barlow',sans-serif;font-size:0.85rem;outline:none;transition:border-color 0.2s;width:100%;}
input:focus,select:focus,textarea:focus{border-color:var(--accent);}
select option{background:var(--card);}
textarea{resize:vertical;min-height:65px;}

/* QR */
.qr-container{display:flex;flex-direction:column;align-items:center;padding:0.5rem 0;}
.qr-wrap{background:#fff;padding:1.2rem;border-radius:4px;margin-bottom:1.2rem;}
.qr-member-name{font-family:'Bebas Neue',cursive;font-size:1.7rem;letter-spacing:0.08em;margin-bottom:0.2rem;}
.qr-member-id{font-size:0.72rem;letter-spacing:0.2em;color:var(--muted);text-transform:uppercase;}
.qr-plan{margin-top:0.8rem;padding:0.35rem 1rem;background:rgba(232,255,0,0.1);border:1px solid rgba(232,255,0,0.3);color:var(--accent);font-size:0.72rem;letter-spacing:0.15em;text-transform:uppercase;font-weight:600;border-radius:2px;}

/* CHECKIN */
.checkin-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;}
.checkin-panel{background:var(--card);border:1px solid var(--border);border-radius:4px;padding:1.5rem;}
.panel-title{font-family:'Barlow Condensed',sans-serif;font-size:0.82rem;font-weight:600;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);margin-bottom:1rem;padding-bottom:0.75rem;border-bottom:1px solid var(--border);}
.checkin-result{display:none;background:var(--surface);border-radius:4px;padding:1.2rem;text-align:center;border:1px solid var(--border);margin-bottom:1.2rem;}
.checkin-result.show{display:block;}
.checkin-success{color:var(--success);font-family:'Bebas Neue',cursive;font-size:1.3rem;letter-spacing:0.08em;margin-bottom:0.3rem;}
.checkin-fail{color:var(--danger);}
.checkin-member-display{font-size:1rem;font-weight:600;margin:0.4rem 0 0.2rem;}
.checkin-time{font-size:0.72rem;color:var(--muted);}
.log-item{display:flex;align-items:center;gap:0.75rem;padding:0.6rem 0;border-bottom:1px solid rgba(255,255,255,0.04);font-size:0.83rem;}
.log-item:last-child{border-bottom:none;}
.log-dot{width:7px;height:7px;border-radius:50%;flex-shrink:0;}
.log-dot.in{background:var(--success);}

/* PAYMENT */
.pay-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;margin-bottom:1.5rem;}
.pay-card{background:var(--surface);border:1px solid var(--border);border-radius:4px;padding:1.2rem;cursor:pointer;transition:all 0.2s;text-align:center;}
.pay-card:hover,.pay-card.selected{border-color:var(--accent);background:rgba(232,255,0,0.05);}
.pay-icon{font-size:2rem;margin-bottom:0.5rem;}
.pay-name{font-weight:600;font-size:0.9rem;}
.pay-desc{font-size:0.75rem;color:var(--muted);margin-top:0.2rem;}
.payment-summary{background:var(--surface);border-radius:4px;padding:1.2rem;margin-bottom:1rem;}
.pay-row{display:flex;justify-content:space-between;padding:0.4rem 0;font-size:0.88rem;}
.pay-row.total{border-top:1px solid var(--border);margin-top:0.4rem;padding-top:0.8rem;font-weight:700;font-size:1rem;color:var(--accent);}
.promptpay-qr{text-align:center;padding:1rem;}
.promptpay-num{font-family:'Bebas Neue',cursive;font-size:1.5rem;letter-spacing:0.1em;color:var(--accent);margin:0.5rem 0;}

/* LINE NOTIFY */
.line-setup{background:var(--surface);border:1px solid var(--border);border-radius:4px;padding:1.5rem;margin-bottom:1rem;}
.line-status{display:flex;align-items:center;gap:0.75rem;margin-bottom:1rem;}
.line-dot{width:10px;height:10px;border-radius:50%;background:var(--danger);}
.line-dot.connected{background:var(--success);}
.line-steps{list-style:none;counter-reset:step;}
.line-steps li{counter-increment:step;padding:0.75rem 0;border-bottom:1px solid rgba(255,255,255,0.05);display:flex;gap:1rem;align-items:flex-start;font-size:0.88rem;color:var(--muted);}
.line-steps li::before{content:counter(step);width:22px;height:22px;background:var(--accent);color:#000;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:0.7rem;font-weight:700;flex-shrink:0;}
.line-steps li:last-child{border-bottom:none;}
.notify-log{max-height:200px;overflow-y:auto;}
.notify-item{display:flex;justify-content:space-between;padding:0.5rem 0;border-bottom:1px solid rgba(255,255,255,0.04);font-size:0.82rem;}
.notify-item:last-child{border-bottom:none;}

/* DETAIL */
.detail-header{display:flex;align-items:center;gap:1.2rem;margin-bottom:1.2rem;}
.detail-avatar{width:64px;height:64px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-family:'Bebas Neue',cursive;font-size:1.8rem;flex-shrink:0;}
.detail-name{font-family:'Bebas Neue',cursive;font-size:1.7rem;letter-spacing:0.05em;line-height:1;}
.detail-grid{display:grid;grid-template-columns:1fr 1fr;gap:0.65rem;margin-bottom:1.2rem;}
.detail-item{background:var(--surface);padding:0.7rem 0.9rem;border-radius:2px;}
.detail-label{font-size:0.62rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);margin-bottom:0.25rem;}
.detail-val{font-size:0.88rem;font-weight:500;}
.history-list{max-height:180px;overflow-y:auto;}
.history-item{display:flex;justify-content:space-between;padding:0.5rem 0;border-bottom:1px solid rgba(255,255,255,0.04);font-size:0.8rem;color:var(--muted);}
.history-item span:first-child{color:var(--success);}

/* TABS */
.tabs{display:flex;gap:0;border-bottom:1px solid var(--border);margin-bottom:1.5rem;}
.tab{padding:0.65rem 1.2rem;cursor:pointer;font-size:0.8rem;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;color:var(--muted);border-bottom:2px solid transparent;transition:all 0.2s;}
.tab.active{color:var(--accent);border-bottom-color:var(--accent);}
.tab-content{display:none;}.tab-content.active{display:block;}

/* REPORT */
.report-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1rem;margin-bottom:1.5rem;}
.report-card{background:var(--surface);border:1px solid var(--border);border-radius:4px;padding:1.2rem;}
.report-title{font-size:0.7rem;letter-spacing:0.15em;text-transform:uppercase;color:var(--muted);margin-bottom:0.75rem;}
.report-list{list-style:none;}
.report-item{display:flex;justify-content:space-between;padding:0.4rem 0;font-size:0.83rem;border-bottom:1px solid rgba(255,255,255,0.04);}
.report-item:last-child{border-bottom:none;}
.report-val{font-weight:600;color:var(--accent);}

/* TOAST */
.toast{position:fixed;bottom:2rem;right:2rem;background:var(--card);border:1px solid var(--border);border-radius:4px;padding:0.9rem 1.3rem;display:flex;align-items:center;gap:0.7rem;z-index:999;transform:translateY(100px);opacity:0;transition:all 0.3s;min-width:240px;}
.toast.show{transform:translateY(0);opacity:1;}
.toast-bar{position:absolute;bottom:0;left:0;height:2px;background:var(--accent);animation:toastBar 3s linear forwards;border-radius:0 0 4px 4px;}
@keyframes toastBar{from{width:100%;}to{width:0%;}}

/* EMPTY */
.empty-state{text-align:center;padding:3rem 2rem;color:var(--muted);}
.empty-icon{font-size:2.5rem;margin-bottom:0.8rem;opacity:0.3;}

/* EXPIRY ALERT */
.alert-bar{background:rgba(255,76,0,0.1);border:1px solid rgba(255,76,0,0.3);border-radius:4px;padding:0.8rem 1.2rem;margin-bottom:1.2rem;display:flex;align-items:center;justify-content:space-between;font-size:0.85rem;}
.alert-bar strong{color:var(--accent2);}

@media(max-width:1100px){.stats-row{grid-template-columns:repeat(3,1fr);}}
@media(max-width:900px){
  .sidebar{width:56px;}
  .sidebar-logo,.nav-section,.sidebar-footer{display:none;}
  .logo-text,.logo-badge{display:none;}
  .nav-item{padding:0.8rem;justify-content:center;}
  .nav-item span:last-child{display:none;}
  .main{margin-left:56px;}
  .stats-row{grid-template-columns:repeat(2,1fr);}
  .checkin-grid{grid-template-columns:1fr;}
  .form-grid{grid-template-columns:1fr;}
  .form-group.full{grid-column:span 1;}
  .modal,.modal-lg,.modal-xl{width:95vw;}
  .report-grid{grid-template-columns:1fr;}
}
</style>
</head>
<body>
<div class="app">

<!-- SIDEBAR -->
<aside class="sidebar">
  <div class="sidebar-logo">
    <div class="logo-text">IRON<span>CLUB</span><span class="logo-badge">PRO</span></div>
    <div class="logo-sub">Fitness Management</div>
  </div>
  <nav class="sidebar-nav">
    <div class="nav-section">หลัก</div>
    <div class="nav-item active" onclick="showView('dashboard',this)"><span class="nav-icon">📊</span><span>Dashboard</span></div>
    <div class="nav-item" onclick="showView('members',this)"><span class="nav-icon">👥</span><span>สมาชิก</span></div>
    <div class="nav-item" onclick="showView('checkin',this)"><span class="nav-icon">✅</span><span>Check-in</span></div>
    <div class="nav-section">การเงิน</div>
    <div class="nav-item" onclick="showView('payments',this)"><span class="nav-icon">💳</span><span>ชำระเงิน</span></div>
    <div class="nav-item" onclick="showView('report',this)"><span class="nav-icon">📈</span><span>รายงาน</span></div>
    <div class="nav-section">ระบบ</div>
    <div class="nav-item" onclick="showView('notify',this)"><span class="nav-icon">🔔</span><span>Line แจ้งเตือน</span></div>
    <div class="nav-item" onclick="showView('history',this)"><span class="nav-icon">📋</span><span>ประวัติ</span></div>
    <div class="nav-item" onclick="showView('settings',this)"><span class="nav-icon">⚙️</span><span>ตั้งค่า</span></div>
  </nav>
  <div class="sidebar-footer">v2.0 PRO · IRONCLUB</div>
</aside>

<main class="main">

<!-- ========== DASHBOARD ========== -->
<div class="view active" id="view-dashboard">
  <div class="page-header">
    <h1 class="page-title">DASH<span>BOARD</span></h1>
    <div class="header-actions">
      <button class="btn btn-ghost" onclick="exportExcel()">📥 Export Excel</button>
      <button class="btn btn-primary" onclick="openAddMember()">+ เพิ่มสมาชิก</button>
    </div>
  </div>
  <div id="expiry-alert"></div>
  <div class="stats-row">
    <div class="stat-card"><div class="stat-label">สมาชิกทั้งหมด</div><div class="stat-num" id="s-total">0</div><div class="stat-sub">คน</div></div>
    <div class="stat-card green"><div class="stat-label">Active</div><div class="stat-num" id="s-active">0</div><div class="stat-sub">คน</div></div>
    <div class="stat-card orange"><div class="stat-label">เช็คอินวันนี้</div><div class="stat-num" id="s-today">0</div><div class="stat-sub">ครั้ง</div></div>
    <div class="stat-card red"><div class="stat-label">หมดอายุ</div><div class="stat-num" id="s-expired">0</div><div class="stat-sub">คน</div></div>
    <div class="stat-card blue"><div class="stat-label">รายได้เดือนนี้</div><div class="stat-num" id="s-revenue">0</div><div class="stat-sub">บาท</div></div>
  </div>
  <div class="table-container">
    <div class="table-header"><div class="table-title">เช็คอินล่าสุดวันนี้</div></div>
    <div id="recent-checkins"></div>
  </div>
</div>

<!-- ========== MEMBERS ========== -->
<div class="view" id="view-members">
  <div class="page-header">
    <h1 class="page-title">สมา<span>ชิก</span></h1>
    <div class="header-actions">
      <button class="btn btn-ghost" onclick="exportExcel()">📥 Excel</button>
      <button class="btn btn-primary" onclick="openAddMember()">+ เพิ่มสมาชิก</button>
    </div>
  </div>
  <div class="table-container">
    <div class="table-header">
      <div class="table-title">รายชื่อสมาชิก (<span id="member-count">0</span> คน)</div>
      <div style="display:flex;gap:0.5rem;align-items:center">
        <select id="filter-status" onchange="renderMembers()" style="width:120px;padding:0.4rem 0.6rem;font-size:0.78rem;">
          <option value="">ทั้งหมด</option>
          <option value="active">Active</option>
          <option value="expired">หมดอายุ</option>
        </select>
        <div class="search-box"><span>🔍</span><input type="text" placeholder="ค้นหา..." id="search-input" oninput="renderMembers()"></div>
      </div>
    </div>
    <div style="overflow-x:auto">
      <table><thead><tr><th>สมาชิก</th><th>เบอร์โทร</th><th>แพ็กเกจ</th><th>วันหมดอายุ</th><th>การชำระ</th><th>สถานะ</th><th>จัดการ</th></tr></thead>
      <tbody id="members-tbody"></tbody></table>
    </div>
    <div id="members-empty" class="empty-state" style="display:none"><div class="empty-icon">👤</div><div>ยังไม่มีสมาชิก</div></div>
  </div>
</div>

<!-- ========== CHECKIN ========== -->
<div class="view" id="view-checkin">
  <div class="page-header"><h1 class="page-title">CHECK<span>-IN</span></h1></div>
  <div class="checkin-grid">
    <div class="checkin-panel">
      <div class="panel-title">🔍 สแกน QR หรือกรอกรหัสสมาชิก</div>
      <div class="checkin-result" id="checkin-result"></div>
      <div style="display:flex;gap:0.6rem;margin-bottom:1.2rem;">
        <input type="text" id="checkin-id" placeholder="IC-0001 หรือกด Enter" onkeydown="if(event.key==='Enter')doCheckin()" style="flex:1;">
        <button class="btn btn-primary" onclick="doCheckin()">CHECK IN</button>
      </div>
      <div class="panel-title">รายชื่อสมาชิก</div>
      <input type="text" id="ci-search" placeholder="ค้นหาสมาชิก..." oninput="renderQuickList()" style="margin-bottom:0.75rem;">
      <div id="quick-member-list" style="max-height:300px;overflow-y:auto;"></div>
    </div>
    <div class="checkin-panel">
      <div class="panel-title">📋 เช็คอินวันนี้ (<span id="ci-count">0</span> ครั้ง)</div>
      <div id="checkin-log" style="max-height:420px;overflow-y:auto;"></div>
    </div>
  </div>
</div>

<!-- ========== PAYMENTS ========== -->
<div class="view" id="view-payments">
  <div class="page-header">
    <h1 class="page-title">ชำระ<span>เงิน</span></h1>
    <div class="header-actions">
      <button class="btn btn-ghost" onclick="exportPaymentExcel()">📥 Export</button>
      <button class="btn btn-primary" onclick="openPayModal()">+ บันทึกชำระเงิน</button>
    </div>
  </div>
  <div class="stats-row" style="grid-template-columns:repeat(3,1fr);">
    <div class="stat-card green"><div class="stat-label">รายได้เดือนนี้</div><div class="stat-num" id="p-month">0</div><div class="stat-sub">บาท</div></div>
    <div class="stat-card"><div class="stat-label">รายได้ทั้งหมด</div><div class="stat-num" id="p-total">0</div><div class="stat-sub">บาท</div></div>
    <div class="stat-card red"><div class="stat-label">ค้างชำระ</div><div class="stat-num" id="p-pending">0</div><div class="stat-sub">คน</div></div>
  </div>
  <div class="table-container">
    <div class="table-header"><div class="table-title">ประวัติการชำระเงิน</div></div>
    <div style="overflow-x:auto">
      <table><thead><tr><th>สมาชิก</th><th>แพ็กเกจ</th><th>จำนวน</th><th>วิธีชำระ</th><th>วันที่</th><th>สถานะ</th></tr></thead>
      <tbody id="pay-tbody"></tbody></table>
    </div>
    <div id="pay-empty" class="empty-state" style="display:none"><div class="empty-icon">💳</div><div>ยังไม่มีรายการ</div></div>
  </div>
</div>

<!-- ========== REPORT ========== -->
<div class="view" id="view-report">
  <div class="page-header">
    <h1 class="page-title">รา<span>ยงาน</span></h1>
    <div class="header-actions">
      <button class="btn btn-ghost" onclick="exportReportExcel()">📥 Export รายงาน</button>
    </div>
  </div>
  <div class="report-grid">
    <div class="report-card">
      <div class="report-title">📦 แพ็กเกจยอดนิยม</div>
      <ul class="report-list" id="rpt-plans"></ul>
    </div>
    <div class="report-card">
      <div class="report-title">📅 เช็คอินรายเดือน (ล่าสุด)</div>
      <ul class="report-list" id="rpt-monthly"></ul>
    </div>
    <div class="report-card">
      <div class="report-title">💰 รายได้รายแพ็กเกจ</div>
      <ul class="report-list" id="rpt-revenue"></ul>
    </div>
  </div>
  <div class="table-container">
    <div class="table-header"><div class="table-title">สมาชิกที่ใกล้หมดอายุ (30 วัน)</div></div>
    <div style="overflow-x:auto">
      <table><thead><tr><th>สมาชิก</th><th>แพ็กเกจ</th><th>วันหมดอายุ</th><th>เหลือ</th><th>แจ้งเตือน</th></tr></thead>
      <tbody id="rpt-expiry-tbody"></tbody></table>
    </div>
    <div id="rpt-expiry-empty" class="empty-state" style="display:none"><div class="empty-icon">✅</div><div>ไม่มีสมาชิกที่ใกล้หมดอายุ</div></div>
  </div>
</div>

<!-- ========== LINE NOTIFY ========== -->
<div class="view" id="view-notify">
  <div class="page-header"><h1 class="page-title">LINE <span>แจ้งเตือน</span></h1></div>
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;">
    <div>
      <div class="line-setup">
        <div class="line-status">
          <div class="line-dot" id="line-dot"></div>
          <span id="line-status-text">ยังไม่ได้เชื่อมต่อ</span>
        </div>
        <div class="form-group" style="margin-bottom:1rem;">
          <label>Line Notify Token</label>
          <input type="password" id="line-token" placeholder="วาง token ที่นี่..." oninput="saveLineToken()">
        </div>
        <div style="display:flex;gap:0.6rem;">
          <button class="btn btn-success btn-sm" onclick="testLineNotify()">🧪 ทดสอบส่ง</button>
          <button class="btn btn-ghost btn-sm" onclick="window.open('https://notify-bot.line.me/th/','_blank')">🔗 ขอ Token</button>
        </div>
      </div>
      <div class="table-container">
        <div class="table-header"><div class="table-title">⚙️ ตั้งค่าแจ้งเตือนอัตโนมัติ</div></div>
        <div style="padding:1.2rem;">
          <div style="display:flex;flex-direction:column;gap:0.8rem;">
            <label style="display:flex;align-items:center;gap:0.75rem;cursor:pointer;font-size:0.88rem;text-transform:none;letter-spacing:0;">
              <input type="checkbox" id="notif-checkin" style="width:16px;height:16px;accent-color:var(--accent);">
              <span>แจ้งเตือนทุกครั้งที่มีการ Check-in</span>
            </label>
            <label style="display:flex;align-items:center;gap:0.75rem;cursor:pointer;font-size:0.88rem;text-transform:none;letter-spacing:0;">
              <input type="checkbox" id="notif-expiry" style="width:16px;height:16px;accent-color:var(--accent);">
              <span>แจ้งเตือนเมื่อแพ็กเกจหมดอายุใน 7 วัน</span>
            </label>
            <label style="display:flex;align-items:center;gap:0.75rem;cursor:pointer;font-size:0.88rem;text-transform:none;letter-spacing:0;">
              <input type="checkbox" id="notif-newmember" style="width:16px;height:16px;accent-color:var(--accent);">
              <span>แจ้งเตือนเมื่อมีสมาชิกใหม่</span>
            </label>
            <label style="display:flex;align-items:center;gap:0.75rem;cursor:pointer;font-size:0.88rem;text-transform:none;letter-spacing:0;">
              <input type="checkbox" id="notif-payment" style="width:16px;height:16px;accent-color:var(--accent);">
              <span>แจ้งเตือนเมื่อรับชำระเงิน</span>
            </label>
          </div>
          <button class="btn btn-primary btn-sm" style="margin-top:1rem;" onclick="saveNotifSettings()">บันทึกตั้งค่า</button>
        </div>
      </div>
    </div>
    <div class="table-container" style="align-self:start;">
      <div class="table-header"><div class="table-title">📨 ประวัติการแจ้งเตือน</div></div>
      <div style="padding:1rem;">
        <div class="notify-log" id="notify-log">
          <div class="empty-state" style="padding:1.5rem"><div class="empty-icon">📭</div><div>ยังไม่มีการแจ้งเตือน</div></div>
        </div>
      </div>
    </div>
  </div>
  <div style="margin-top:1.5rem;">
    <div class="table-container">
      <div class="table-header"><div class="table-title">📤 ส่งข้อความหาสมาชิก</div></div>
      <div style="padding:1.2rem;display:grid;grid-template-columns:1fr 1fr;gap:1rem;">
        <div class="form-group">
          <label>เลือกสมาชิก</label>
          <select id="line-member-select"><option value="all">ทุกคน (Broadcast)</option></select>
        </div>
        <div class="form-group">
          <label>ประเภทข้อความ</label>
          <select id="line-msg-type" onchange="fillLineTemplate()">
            <option value="custom">กำหนดเอง</option>
            <option value="expiry">แจ้งหมดอายุ</option>
            <option value="promo">โปรโมชัน</option>
            <option value="holiday">วันหยุด</option>
          </select>
        </div>
        <div class="form-group full" style="grid-column:span 2;">
          <label>ข้อความ</label>
          <textarea id="line-msg" rows="4" placeholder="พิมพ์ข้อความ..."></textarea>
        </div>
        <div style="grid-column:span 2;display:flex;justify-content:flex-end;">
          <button class="btn btn-success" onclick="sendLineMsg()">📤 ส่งข้อความ</button>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- ========== HISTORY ========== -->
<div class="view" id="view-history">
  <div class="page-header">
    <h1 class="page-title">ประ<span>วัติ</span></h1>
    <div class="header-actions">
      <button class="btn btn-ghost" onclick="exportHistoryExcel()">📥 Export</button>
    </div>
  </div>
  <div class="table-container">
    <div class="table-header">
      <div class="table-title">ประวัติเช็คอินทั้งหมด</div>
      <div style="display:flex;gap:0.5rem;">
        <input type="date" id="hist-from" style="width:140px;padding:0.4rem 0.6rem;font-size:0.78rem;" onchange="renderHistory()">
        <input type="date" id="hist-to" style="width:140px;padding:0.4rem 0.6rem;font-size:0.78rem;" onchange="renderHistory()">
      </div>
    </div>
    <div style="overflow-x:auto">
      <table><thead><tr><th>สมาชิก</th><th>รหัส</th><th>แพ็กเกจ</th><th>วันที่</th><th>เวลา</th></tr></thead>
      <tbody id="history-tbody"></tbody></table>
    </div>
    <div id="history-empty" class="empty-state" style="display:none"><div class="empty-icon">📋</div><div>ยังไม่มีประวัติ</div></div>
  </div>
</div>

<!-- ========== SETTINGS ========== -->
<div class="view" id="view-settings">
  <div class="page-header"><h1 class="page-title">ตั้ง<span>ค่า</span></h1></div>
  <div style="display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;">
    <div class="table-container">
      <div class="table-header"><div class="table-title">🏋️ ข้อมูลยิม</div></div>
      <div style="padding:1.2rem;display:flex;flex-direction:column;gap:0.9rem;">
        <div class="form-group"><label>ชื่อยิม</label><input type="text" id="set-gymname" placeholder="IRONCLUB Fitness"></div>
        <div class="form-group"><label>เบอร์โทร</label><input type="text" id="set-phone" placeholder="02-XXX-XXXX"></div>
        <div class="form-group"><label>ที่อยู่</label><textarea id="set-address" rows="2" placeholder="ที่อยู่ยิม"></textarea></div>
        <div class="form-group"><label>เลข PromptPay</label><input type="text" id="set-promptpay" placeholder="0XX-XXX-XXXX"></div>
        <button class="btn btn-primary btn-sm" onclick="saveSettings()">บันทึกการตั้งค่า</button>
      </div>
    </div>
    <div class="table-container">
      <div class="table-header"><div class="table-title">💰 ราคาแพ็กเกจ</div></div>
      <div style="padding:1.2rem;display:flex;flex-direction:column;gap:0.75rem;">
        <div class="form-group"><label>รายเดือน (บาท)</label><input type="number" id="price-monthly" value="800"></div>
        <div class="form-group"><label>3 เดือน (บาท)</label><input type="number" id="price-3m" value="2100"></div>
        <div class="form-group"><label>6 เดือน (บาท)</label><input type="number" id="price-6m" value="3600"></div>
        <div class="form-group"><label>รายปี (บาท)</label><input type="number" id="price-yearly" value="6000"></div>
        <div class="form-group"><label>รายครั้ง (บาท)</label><input type="number" id="price-once" value="100"></div>
        <button class="btn btn-primary btn-sm" onclick="savePrices()">บันทึกราคา</button>
      </div>
    </div>
    <div class="table-container">
      <div class="table-header"><div class="table-title">🗄️ จัดการข้อมูล</div></div>
      <div style="padding:1.2rem;display:flex;flex-direction:column;gap:0.75rem;">
        <button class="btn btn-ghost" onclick="exportBackup()">📦 Export Backup (JSON)</button>
        <div class="form-group"><label>Import Backup</label><input type="file" id="import-file" accept=".json" onchange="importBackup(event)" style="padding:0.4rem;"></div>
        <hr style="border-color:var(--border);">
        <button class="btn btn-danger btn-sm" onclick="clearAllData()">🗑️ ล้างข้อมูลทั้งหมด</button>
      </div>
    </div>
  </div>
</div>

</main>
</div>

<!-- ========== MODALS ========== -->

<!-- ADD/EDIT MEMBER -->
<div class="modal-overlay" id="modal-member">
  <div class="modal">
    <div class="modal-header">
      <div class="modal-title" id="mm-title">เพิ่มสมาชิก</div>
      <button class="modal-close" onclick="closeModal('modal-member')">✕</button>
    </div>
    <div class="modal-body">
      <div class="form-grid">
        <div class="form-group"><label>ชื่อ *</label><input type="text" id="f-fname" placeholder="ชื่อจริง"></div>
        <div class="form-group"><label>นามสกุล *</label><input type="text" id="f-lname" placeholder="นามสกุล"></div>
        <div class="form-group"><label>เบอร์โทร *</label><input type="tel" id="f-phone" placeholder="08X-XXX-XXXX"></div>
        <div class="form-group"><label>อีเมล</label><input type="email" id="f-email" placeholder="email@example.com"></div>
        <div class="form-group"><label>เพศ</label><select id="f-gender"><option>ชาย</option><option>หญิง</option><option>อื่นๆ</option></select></div>
        <div class="form-group"><label>วันเกิด</label><input type="date" id="f-dob"></div>
        <div class="form-group"><label>แพ็กเกจ *</label>
          <select id="f-plan" onchange="updatePlanPrice()">
            <option value="รายเดือน">รายเดือน</option>
            <option value="3 เดือน">3 เดือน</option>
            <option value="6 เดือน">6 เดือน</option>
            <option value="รายปี">รายปี</option>
            <option value="รายครั้ง">รายครั้ง</option>
          </select>
        </div>
        <div class="form-group"><label>ราคา (บาท)</label><input type="number" id="f-price" placeholder="800"></div>
        <div class="form-group"><label>วันเริ่ม</label><input type="date" id="f-start"></div>
        <div class="form-group"><label>สถานะชำระเงิน</label><select id="f-paystatus"><option value="paid">ชำระแล้ว</option><option value="unpaid">ค้างชำระ</option></select></div>
        <div class="form-group full"><label>หมายเหตุ</label><textarea id="f-note" placeholder="ข้อมูลเพิ่มเติม..."></textarea></div>
      </div>
    </div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeModal('modal-member')">ยกเลิก</button>
      <button class="btn btn-primary" onclick="saveMember()">บันทึก</button>
    </div>
  </div>
</div>

<!-- QR CODE -->
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
      <button class="btn btn-primary" onclick="printQR()">🖨 พิมพ์ QR</button>
    </div>
  </div>
</div>

<!-- PAYMENT -->
<div class="modal-overlay" id="modal-pay">
  <div class="modal modal-lg">
    <div class="modal-header">
      <div class="modal-title">บันทึกชำระเงิน</div>
      <button class="modal-close" onclick="closeModal('modal-pay')">✕</button>
    </div>
    <div class="modal-body">
      <div class="form-grid" style="margin-bottom:1.2rem;">
        <div class="form-group"><label>สมาชิก *</label>
          <select id="pay-member"><option value="">-- เลือกสมาชิก --</option></select>
        </div>
        <div class="form-group"><label>แพ็กเกจ</label>
          <select id="pay-plan" onchange="updatePayAmount()">
            <option value="รายเดือน">รายเดือน</option>
            <option value="3 เดือน">3 เดือน</option>
            <option value="6 เดือน">6 เดือน</option>
            <option value="รายปี">รายปี</option>
            <option value="รายครั้ง">รายครั้ง</option>
          </select>
        </div>
        <div class="form-group"><label>จำนวนเงิน (บาท)</label><input type="number" id="pay-amount" placeholder="800"></div>
        <div class="form-group"><label>วันที่ชำระ</label><input type="date" id="pay-date"></div>
      </div>
      <div class="panel-title" style="margin-bottom:0.8rem;">วิธีชำระเงิน</div>
      <div class="pay-grid">
        <div class="pay-card selected" id="paymethod-cash" onclick="selectPayMethod('cash')"><div class="pay-icon">💵</div><div class="pay-name">เงินสด</div><div class="pay-desc">รับเงินหน้าร้าน</div></div>
        <div class="pay-card" id="paymethod-transfer" onclick="selectPayMethod('transfer')"><div class="pay-icon">🏦</div><div class="pay-name">โอนเงิน</div><div class="pay-desc">โอนผ่านธนาคาร</div></div>
        <div class="pay-card" id="paymethod-promptpay" onclick="selectPayMethod('promptpay')"><div class="pay-icon">📱</div><div class="pay-name">PromptPay</div><div class="pay-desc">QR PromptPay</div></div>
        <div class="pay-card" id="paymethod-card" onclick="selectPayMethod('card')"><div class="pay-icon">💳</div><div class="pay-name">บัตรเครดิต</div><div class="pay-desc">Visa / Master</div></div>
      </div>
      <div id="promptpay-section" style="display:none;">
        <div class="promptpay-qr">
          <div id="pp-qr"></div>
          <div class="promptpay-num" id="pp-number"></div>
          <div style="font-size:0.78rem;color:var(--muted);">สแกนเพื่อโอนเงิน</div>
        </div>
      </div>
      <div class="payment-summary">
        <div class="pay-row"><span>แพ็กเกจ</span><span id="ps-plan">-</span></div>
        <div class="pay-row"><span>วิธีชำระ</span><span id="ps-method">เงินสด</span></div>
        <div class="pay-row total"><span>ยอดรวม</span><span id="ps-total">฿0</span></div>
      </div>
      <div class="form-group"><label>หมายเหตุ</label><input type="text" id="pay-note" placeholder="ข้อมูลเพิ่มเติม..."></div>
    </div>
    <div class="modal-footer">
      <button class="btn btn-ghost" onclick="closeModal('modal-pay')">ยกเลิก</button>
      <button class="btn btn-success" onclick="savePayment()">✅ ยืนยันชำระเงิน</button>
    </div>
  </div>
</div>

<!-- MEMBER DETAIL -->
<div class="modal-overlay" id="modal-detail">
  <div class="modal modal-xl">
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
  <span id="toast-icon">✅</span>
  <span id="toast-text"></span>
  <div class="toast-bar" id="toast-bar"></div>
</div>

<script>
// ============================================================
// STATE
// ============================================================
let members  = JSON.parse(localStorage.getItem('ic-members')  || '[]');
let checkins = JSON.parse(localStorage.getItem('ic-checkins') || '[]');
let payments = JSON.parse(localStorage.getItem('ic-payments') || '[]');
let notifLog = JSON.parse(localStorage.getItem('ic-notiflog') || '[]');
let settings = JSON.parse(localStorage.getItem('ic-settings') || '{}');
let prices   = JSON.parse(localStorage.getItem('ic-prices')   || '{"รายเดือน":800,"3 เดือน":2100,"6 เดือน":3600,"รายปี":6000,"รายครั้ง":100}');
let lineToken= localStorage.getItem('ic-linetoken') || '';
let notifSettings = JSON.parse(localStorage.getItem('ic-notifsettings') || '{"checkin":false,"expiry":true,"newmember":true,"payment":true}');
let editingId = null;
let payMethod = 'cash';

const PLAN_DAYS = {'รายเดือน':30,'3 เดือน':90,'6 เดือน':180,'รายปี':365,'รายครั้ง':1};
const COLORS = ['#E8FF00','#FF4C00','#00E676','#00B4D8','#FF80AB','#FFAB40','#CE93D8','#80CBC4'];

function save(){
  localStorage.setItem('ic-members',  JSON.stringify(members));
  localStorage.setItem('ic-checkins', JSON.stringify(checkins));
  localStorage.setItem('ic-payments', JSON.stringify(payments));
  localStorage.setItem('ic-notiflog', JSON.stringify(notifLog));
}

// ============================================================
// UTILS
// ============================================================
function genId(){ return 'IC-'+String(members.length+1).padStart(4,'0'); }
function getExpiry(start,plan){ const d=new Date(start); d.setDate(d.getDate()+(PLAN_DAYS[plan]||30)); return d.toISOString().split('T')[0]; }
function isActive(m){ if(m.plan==='รายครั้ง') return false; return new Date(m.expiry)>=new Date(); }
function daysLeft(m){ if(m.plan==='รายครั้ง') return null; const d=Math.ceil((new Date(m.expiry)-new Date())/(1000*60*60*24)); return d; }
function fmtDate(d){ if(!d) return '-'; return new Date(d).toLocaleDateString('th-TH',{day:'2-digit',month:'short',year:'numeric'}); }
function fmtTime(d){ return new Date(d).toLocaleTimeString('th-TH',{hour:'2-digit',minute:'2-digit'}); }
function isToday(d){ const t=new Date(),x=new Date(d); return t.getFullYear()===x.getFullYear()&&t.getMonth()===x.getMonth()&&t.getDate()===x.getDate(); }
function isThisMonth(d){ const t=new Date(),x=new Date(d); return t.getFullYear()===x.getFullYear()&&t.getMonth()===x.getMonth(); }
function avatarColor(id){ return COLORS[parseInt((id||'IC-0').replace('IC-',''))%COLORS.length]; }
function initials(name){ const p=name.trim().split(' '); return p.length>1?(p[0][0]+p[1][0]).toUpperCase():name.slice(0,2).toUpperCase(); }
function fmtMoney(n){ return Number(n).toLocaleString('th-TH'); }

// ============================================================
// TOAST
// ============================================================
let toastTimer;
function showToast(msg,icon='✅'){
  clearTimeout(toastTimer);
  const b=document.getElementById('toast-bar');
  document.getElementById('toast-text').textContent=msg;
  document.getElementById('toast-icon').textContent=icon;
  b.style.animation='none'; b.offsetHeight; b.style.animation='toastBar 3s linear forwards';
  document.getElementById('toast').classList.add('show');
  toastTimer=setTimeout(()=>document.getElementById('toast').classList.remove('show'),3200);
}

// ============================================================
// NAVIGATION
// ============================================================
function showView(v,el){
  document.querySelectorAll('.view').forEach(x=>x.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(x=>x.classList.remove('active'));
  document.getElementById('view-'+v).classList.add('active');
  if(el) el.classList.add('active');
  const fn={dashboard:renderDashboard,members:renderMembers,checkin:renderCheckinView,
            payments:renderPayments,report:renderReport,notify:renderNotify,
            history:renderHistory,settings:loadSettings};
  if(fn[v]) fn[v]();
}

// ============================================================
// DASHBOARD
// ============================================================
function renderDashboard(){
  const active=members.filter(isActive);
  const expired=members.filter(m=>!isActive(m)&&m.plan!=='รายครั้ง');
  const todayCI=checkins.filter(c=>isToday(c.time));
  const monthRev=payments.filter(p=>isThisMonth(p.date)&&p.status==='paid').reduce((a,p)=>a+Number(p.amount),0);

  document.getElementById('s-total').textContent=members.length;
  document.getElementById('s-active').textContent=active.length;
  document.getElementById('s-today').textContent=todayCI.length;
  document.getElementById('s-expired').textContent=expired.length;
  document.getElementById('s-revenue').textContent=fmtMoney(monthRev);

  // expiry alert
  const soon=members.filter(m=>{ const d=daysLeft(m); return d!==null&&d>=0&&d<=7; });
  const alertEl=document.getElementById('expiry-alert');
  alertEl.innerHTML=soon.length?`<div class="alert-bar">⚠️ มีสมาชิก <strong>${soon.length} คน</strong> ที่แพ็กเกจจะหมดอายุใน 7 วัน — <a href="#" onclick="showView('report',null)" style="color:var(--accent)">ดูรายชื่อ</a></div>`:'';

  // recent
  const rc=document.getElementById('recent-checkins');
  const list=[...todayCI].reverse().slice(0,10);
  if(!list.length){ rc.innerHTML=`<div class="empty-state"><div class="empty-icon">🏋️</div><div>ยังไม่มีการเช็คอินวันนี้</div></div>`; return; }
  rc.innerHTML=`<div style="overflow-x:auto"><table><thead><tr><th>สมาชิก</th><th>รหัส</th><th>เวลา</th><th>แพ็กเกจ</th></tr></thead><tbody>
    ${list.map(c=>{const m=members.find(x=>x.id===c.memberId);if(!m)return'';return`<tr>
      <td><div class="member-info"><div class="avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div><div>${m.name}</div></div></td>
      <td style="color:var(--muted)">${m.id}</td><td>${fmtTime(c.time)}</td>
      <td><span class="badge badge-active">${m.plan}</span></td></tr>`;}).join('')}
  </tbody></table></div>`;
}

// ============================================================
// MEMBERS
// ============================================================
function renderMembers(){
  const q=(document.getElementById('search-input')?.value||'').toLowerCase();
  const fs=document.getElementById('filter-status')?.value||'';
  let list=members.filter(m=>{
    if(fs==='active'&&!isActive(m)) return false;
    if(fs==='expired'&&(isActive(m)||m.plan==='รายครั้ง')) return false;
    return !q||m.name.toLowerCase().includes(q)||m.id.toLowerCase().includes(q)||m.phone.includes(q);
  });
  document.getElementById('member-count').textContent=list.length;
  const tbody=document.getElementById('members-tbody');
  const empty=document.getElementById('members-empty');
  if(!list.length){ tbody.innerHTML=''; empty.style.display='block'; return; }
  empty.style.display='none';
  tbody.innerHTML=list.map(m=>{
    const active=isActive(m);
    const dl=daysLeft(m);
    const expiryColor=dl!==null&&dl<=7?'var(--danger)':active?'var(--text)':'var(--danger)';
    return `<tr>
      <td><div class="member-info"><div class="avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div>
      <div><div style="font-weight:500">${m.name}</div><div style="font-size:0.72rem;color:var(--muted)">${m.id}</div></div></div></td>
      <td>${m.phone}</td><td>${m.plan}</td>
      <td style="color:${expiryColor}">${m.plan==='รายครั้ง'?'-':fmtDate(m.expiry)+(dl!==null&&dl>=0&&dl<=7?` <span style="color:var(--danger);font-size:0.7rem">(${dl}วัน)</span>`:'')}</td>
      <td><span class="badge ${m.payStatus==='paid'?'badge-paid':'badge-unpaid'}">${m.payStatus==='paid'?'ชำระแล้ว':'ค้างชำระ'}</span></td>
      <td><span class="badge ${active?'badge-active':'badge-expired'}">${m.plan==='รายครั้ง'?'รายครั้ง':active?'Active':'หมดอายุ'}</span></td>
      <td><div class="actions">
        <button class="btn btn-ghost btn-sm" onclick="viewMember('${m.id}')">ดู</button>
        <button class="btn btn-ghost btn-sm" onclick="showQR('${m.id}')">QR</button>
        <button class="btn btn-ghost btn-sm" onclick="editMember('${m.id}')">แก้ไข</button>
        <button class="btn btn-danger btn-sm" onclick="deleteMember('${m.id}')">ลบ</button>
      </div></td></tr>`;
  }).join('');
}

// ============================================================
// ADD/EDIT MEMBER
// ============================================================
function openAddMember(){
  editingId=null;
  document.getElementById('mm-title').textContent='เพิ่มสมาชิกใหม่';
  ['fname','lname','phone','email','note'].forEach(f=>document.getElementById('f-'+f).value='');
  document.getElementById('f-gender').value='ชาย';
  document.getElementById('f-plan').value='รายเดือน';
  document.getElementById('f-start').value=new Date().toISOString().split('T')[0];
  document.getElementById('f-dob').value='';
  document.getElementById('f-paystatus').value='paid';
  updatePlanPrice();
  openModal('modal-member');
}
function updatePlanPrice(){
  const plan=document.getElementById('f-plan').value;
  document.getElementById('f-price').value=prices[plan]||0;
}
function editMember(id){
  const m=members.find(x=>x.id===id);
  if(!m) return;
  editingId=id;
  document.getElementById('mm-title').textContent='แก้ไขข้อมูลสมาชิก';
  const [fn,...ln]=m.name.split(' ');
  document.getElementById('f-fname').value=fn;
  document.getElementById('f-lname').value=ln.join(' ');
  document.getElementById('f-phone').value=m.phone;
  document.getElementById('f-email').value=m.email||'';
  document.getElementById('f-gender').value=m.gender||'ชาย';
  document.getElementById('f-dob').value=m.dob||'';
  document.getElementById('f-plan').value=m.plan;
  document.getElementById('f-price').value=m.price||prices[m.plan]||0;
  document.getElementById('f-start').value=m.start;
  document.getElementById('f-paystatus').value=m.payStatus||'paid';
  document.getElementById('f-note').value=m.note||'';
  openModal('modal-member');
}
function saveMember(){
  const fn=document.getElementById('f-fname').value.trim();
  const ln=document.getElementById('f-lname').value.trim();
  const phone=document.getElementById('f-phone').value.trim();
  const plan=document.getElementById('f-plan').value;
  const start=document.getElementById('f-start').value||new Date().toISOString().split('T')[0];
  const price=Number(document.getElementById('f-price').value)||prices[plan];
  const payStatus=document.getElementById('f-paystatus').value;
  if(!fn||!ln||!phone){ showToast('กรุณากรอกข้อมูลที่จำเป็น','⚠️'); return; }
  const name=fn+' '+ln;
  const expiry=getExpiry(start,plan);
  if(editingId){
    const i=members.findIndex(x=>x.id===editingId);
    members[i]={...members[i],name,phone,plan,start,expiry,price,payStatus,
      email:document.getElementById('f-email').value,
      gender:document.getElementById('f-gender').value,
      dob:document.getElementById('f-dob').value,
      note:document.getElementById('f-note').value};
    showToast('อัปเดตข้อมูลแล้ว','✏️');
  } else {
    const newM={id:genId(),name,phone,plan,start,expiry,price,payStatus,
      email:document.getElementById('f-email').value,
      gender:document.getElementById('f-gender').value,
      dob:document.getElementById('f-dob').value,
      note:document.getElementById('f-note').value,
      joinDate:new Date().toISOString()};
    members.push(newM);
    if(payStatus==='paid'){
      payments.push({id:'PAY-'+Date.now(),memberId:newM.id,memberName:name,plan,amount:price,method:'เงินสด',date:new Date().toISOString(),status:'paid',note:'ชำระตอนสมัคร'});
    }
    showToast('เพิ่มสมาชิกใหม่แล้ว! 🎉','✅');
    if(notifSettings.newmember) sendLineNotification(`🏋️ สมาชิกใหม่!\nชื่อ: ${name}\nแพ็กเกจ: ${plan}\nรหัส: ${newM.id}`);
  }
  save(); closeModal('modal-member'); renderMembers(); renderDashboard();
}
function deleteMember(id){
  if(!confirm('ต้องการลบสมาชิกนี้?')) return;
  members=members.filter(m=>m.id!==id); save(); renderMembers(); renderDashboard();
  showToast('ลบสมาชิกแล้ว','🗑️');
}

// ============================================================
// MEMBER DETAIL
// ============================================================
function viewMember(id){
  const m=members.find(x=>x.id===id);
  if(!m) return;
  const mCI=checkins.filter(c=>c.memberId===id);
  const mPay=payments.filter(p=>p.memberId===id);
  const totalPaid=mPay.filter(p=>p.status==='paid').reduce((a,p)=>a+Number(p.amount),0);
  document.getElementById('modal-detail-body').innerHTML=`
    <div class="detail-header">
      <div class="detail-avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div>
      <div><div class="detail-name">${m.name}</div>
      <div style="font-size:0.72rem;color:var(--muted);margin-top:0.2rem">${m.id} · เข้าร่วม ${fmtDate(m.joinDate)}</div>
      <div style="margin-top:0.4rem">${isActive(m)?'<span class="badge badge-active">Active</span>':'<span class="badge badge-expired">หมดอายุ</span>'}</div></div>
    </div>
    <div class="detail-grid">
      <div class="detail-item"><div class="detail-label">เบอร์โทร</div><div class="detail-val">${m.phone}</div></div>
      <div class="detail-item"><div class="detail-label">อีเมล</div><div class="detail-val">${m.email||'-'}</div></div>
      <div class="detail-item"><div class="detail-label">แพ็กเกจ</div><div class="detail-val">${m.plan}</div></div>
      <div class="detail-item"><div class="detail-label">วันหมดอายุ</div><div class="detail-val" style="color:${isActive(m)?'var(--success)':'var(--danger)'}">${m.plan==='รายครั้ง'?'-':fmtDate(m.expiry)}</div></div>
      <div class="detail-item"><div class="detail-label">เช็คอินทั้งหมด</div><div class="detail-val">${mCI.length} ครั้ง</div></div>
      <div class="detail-item"><div class="detail-label">ชำระทั้งหมด</div><div class="detail-val" style="color:var(--accent)">฿${fmtMoney(totalPaid)}</div></div>
    </div>
    ${m.note?`<div class="detail-item" style="margin-bottom:1rem"><div class="detail-label">หมายเหตุ</div><div class="detail-val">${m.note}</div></div>`:''}
    <div class="tabs">
      <div class="tab active" onclick="switchTab(event,'tab-ci')">ประวัติเช็คอิน (${mCI.length})</div>
      <div class="tab" onclick="switchTab(event,'tab-pay')">ประวัติชำระเงิน (${mPay.length})</div>
    </div>
    <div class="tab-content active" id="tab-ci">
      <div class="history-list">${mCI.length?[...mCI].reverse().slice(0,20).map(c=>`<div class="history-item"><span>✅ เช็คอิน</span><span>${fmtDate(c.time)} ${fmtTime(c.time)}</span></div>`).join(''):'<div style="color:var(--muted);font-size:0.85rem">ยังไม่มีประวัติ</div>'}</div>
    </div>
    <div class="tab-content" id="tab-pay">
      <div class="history-list">${mPay.length?[...mPay].reverse().map(p=>`<div class="history-item"><span style="color:var(--accent)">฿${fmtMoney(p.amount)}</span><span>${p.method} · ${fmtDate(p.date)}</span></div>`).join(''):'<div style="color:var(--muted);font-size:0.85rem">ยังไม่มีประวัติ</div>'}</div>
    </div>`;
  openModal('modal-detail');
}
function switchTab(e,id){
  const modal=e.target.closest('.modal-body');
  modal.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
  modal.querySelectorAll('.tab-content').forEach(t=>t.classList.remove('active'));
  e.target.classList.add('active');
  document.getElementById(id).classList.add('active');
}

// ============================================================
// QR CODE
// ============================================================
function showQR(id){
  const m=members.find(x=>x.id===id);
  if(!m) return;
  document.getElementById('qr-name').textContent=m.name;
  document.getElementById('qr-id').textContent=m.id;
  document.getElementById('qr-plan').textContent='📦 '+m.plan+(m.plan!=='รายครั้ง'?' · หมด '+fmtDate(m.expiry):'');
  const qrEl=document.getElementById('qrcode');
  qrEl.innerHTML='';
  new QRCode(qrEl,{text:m.id,width:200,height:200,colorDark:'#000000',colorLight:'#ffffff',correctLevel:QRCode.CorrectLevel.H});
  openModal('modal-qr');
}
function printQR(){
  const canvas=document.getElementById('qrcode').querySelector('canvas');
  if(!canvas) return;
  const name=document.getElementById('qr-name').textContent;
  const id=document.getElementById('qr-id').textContent;
  const plan=document.getElementById('qr-plan').textContent;
  const gym=settings.gymname||'IRONCLUB Fitness';
  const w=window.open('','_blank');
  w.document.write(`<html><head><title>QR ${name}</title><style>
    body{font-family:sans-serif;text-align:center;padding:2rem;background:#fff;}
    h2{font-size:1.4rem;margin-bottom:4px;}p{color:#666;font-size:0.85rem;}
    .plan{display:inline-block;background:#f0f0f0;padding:4px 12px;border-radius:4px;font-size:0.8rem;margin-top:8px;}
    @media print{body{padding:0;}}
  </style></head><body>
    <h2>${name}</h2><p>${id}</p>
    <img src="${canvas.toDataURL()}" style="width:200px;height:200px;display:block;margin:12px auto;">
    <div class="plan">${plan}</div>
    <p style="margin-top:1rem;font-size:0.75rem;color:#aaa;">${gym}</p>
    <script>window.onload=()=>window.print()<\/script>
  </body></html>`);
  w.document.close();
}

// ============================================================
// CHECK-IN
// ============================================================
function renderCheckinView(){
  renderQuickList();
  renderCheckinLog();
}
function renderQuickList(){
  const q=(document.getElementById('ci-search')?.value||'').toLowerCase();
  const ql=document.getElementById('quick-member-list');
  const list=members.filter(m=>!q||m.name.toLowerCase().includes(q)||m.id.toLowerCase().includes(q));
  if(!list.length){ ql.innerHTML=`<div style="color:var(--muted);font-size:0.85rem;padding:0.5rem">ไม่พบสมาชิก</div>`; return; }
  ql.innerHTML=list.map(m=>`
    <div style="display:flex;align-items:center;gap:0.65rem;padding:0.55rem;border-radius:2px;cursor:pointer;transition:background 0.15s"
      onmouseover="this.style.background='rgba(255,255,255,0.04)'" onmouseout="this.style.background='none'"
      onclick="quickCheckin('${m.id}')">
      <div class="avatar" style="background:${avatarColor(m.id)};color:#000;width:30px;height:30px;font-size:0.8rem">${initials(m.name)}</div>
      <div style="flex:1"><div style="font-size:0.85rem;font-weight:500">${m.name}</div><div style="font-size:0.7rem;color:var(--muted)">${m.id}</div></div>
      <span class="badge ${isActive(m)?'badge-active':'badge-expired'}" style="font-size:0.6rem">${isActive(m)?'Active':'หมด'}</span>
    </div>`).join('');
}
function quickCheckin(id){ document.getElementById('checkin-id').value=id; doCheckin(); }
function doCheckin(){
  const input=document.getElementById('checkin-id').value.trim().toUpperCase();
  const result=document.getElementById('checkin-result');
  if(!input){ showToast('กรุณากรอกรหัสสมาชิก','⚠️'); return; }
  const m=members.find(x=>x.id===input);
  if(!m){
    result.className='checkin-result show';
    result.innerHTML=`<div class="checkin-success checkin-fail">❌ ไม่พบสมาชิก</div><div class="checkin-time">รหัส "${input}" ไม่มีในระบบ</div>`;
    return;
  }
  if(!isActive(m)&&m.plan!=='รายครั้ง'){
    result.className='checkin-result show';
    result.innerHTML=`<div class="checkin-success checkin-fail">⚠️ แพ็กเกจหมดอายุ</div><div class="checkin-member-display">${m.name}</div><div class="checkin-time">หมดอายุ ${fmtDate(m.expiry)}</div>`;
    showToast('แพ็กเกจของ '+m.name+' หมดอายุแล้ว','⚠️'); return;
  }
  checkins.push({memberId:m.id,time:new Date().toISOString()});
  save();
  result.className='checkin-result show';
  result.innerHTML=`<div class="checkin-success">✅ เช็คอินสำเร็จ!</div>
    <div class="checkin-member-display">${m.name}</div>
    <div class="checkin-time">${m.id} · ${new Date().toLocaleTimeString('th-TH')}</div>
    <div style="margin-top:0.6rem"><span class="badge badge-active">${m.plan}</span></div>`;
  showToast(m.name+' เช็คอินแล้ว 💪','✅');
  document.getElementById('checkin-id').value='';
  const cnt=checkins.filter(c=>isToday(c.time)).length;
  document.getElementById('ci-count').textContent=cnt;
  renderCheckinLog(); renderDashboard();
  if(notifSettings.checkin) sendLineNotification(`✅ Check-in!\n${m.name} (${m.id})\nเวลา: ${new Date().toLocaleTimeString('th-TH')}`);
}
function renderCheckinLog(){
  const log=document.getElementById('checkin-log');
  const today=[...checkins.filter(c=>isToday(c.time))].reverse();
  document.getElementById('ci-count').textContent=today.length;
  if(!today.length){ log.innerHTML=`<div class="empty-state" style="padding:2rem"><div class="empty-icon">📭</div><div>ยังไม่มีการเช็คอิน</div></div>`; return; }
  log.innerHTML=today.map(c=>{
    const m=members.find(x=>x.id===c.memberId);
    if(!m) return '';
    return `<div class="log-item">
      <div class="log-dot in"></div>
      <div class="avatar" style="background:${avatarColor(m.id)};color:#000;width:26px;height:26px;font-size:0.72rem;flex-shrink:0">${initials(m.name)}</div>
      <div style="flex:1;font-weight:500">${m.name}</div>
      <div style="font-size:0.72rem;color:var(--muted)">${fmtTime(c.time)}</div>
    </div>`;
  }).join('');
}

// ============================================================
// PAYMENTS
// ============================================================
function renderPayments(){
  const monthPay=payments.filter(p=>isThisMonth(p.date)&&p.status==='paid').reduce((a,p)=>a+Number(p.amount),0);
  const totalPay=payments.filter(p=>p.status==='paid').reduce((a,p)=>a+Number(p.amount),0);
  const unpaidMembers=members.filter(m=>m.payStatus==='unpaid').length;
  document.getElementById('p-month').textContent=fmtMoney(monthPay);
  document.getElementById('p-total').textContent=fmtMoney(totalPay);
  document.getElementById('p-pending').textContent=unpaidMembers;
  const tbody=document.getElementById('pay-tbody');
  const empty=document.getElementById('pay-empty');
  if(!payments.length){ tbody.innerHTML=''; empty.style.display='block'; return; }
  empty.style.display='none';
  tbody.innerHTML=[...payments].reverse().map(p=>`<tr>
    <td><div class="member-info"><div class="avatar" style="background:${avatarColor(p.memberId||'')};color:#000;width:28px;height:28px;font-size:0.75rem">${initials(p.memberName||'?')}</div><div>${p.memberName||'-'}</div></div></td>
    <td>${p.plan}</td>
    <td style="color:var(--accent);font-weight:600">฿${fmtMoney(p.amount)}</td>
    <td>${p.method}</td>
    <td>${fmtDate(p.date)}</td>
    <td><span class="badge ${p.status==='paid'?'badge-paid':'badge-unpaid'}">${p.status==='paid'?'ชำระแล้ว':'รอชำระ'}</span></td>
  </tr>`).join('');
}
function openPayModal(){
  const sel=document.getElementById('pay-member');
  sel.innerHTML='<option value="">-- เลือกสมาชิก --</option>'+members.map(m=>`<option value="${m.id}">${m.name} (${m.id})</option>`).join('');
  document.getElementById('pay-plan').value='รายเดือน';
  document.getElementById('pay-date').value=new Date().toISOString().split('T')[0];
  document.getElementById('pay-note').value='';
  payMethod='cash';
  updatePayAmount();
  selectPayMethod('cash');
  document.querySelectorAll('.pay-card').forEach(c=>c.classList.remove('selected'));
  document.getElementById('paymethod-cash').classList.add('selected');
  openModal('modal-pay');
}
function updatePayAmount(){
  const plan=document.getElementById('pay-plan')?.value;
  if(plan){
    document.getElementById('pay-amount').value=prices[plan]||0;
    document.getElementById('ps-plan').textContent=plan;
    document.getElementById('ps-total').textContent='฿'+fmtMoney(prices[plan]||0);
  }
}
function selectPayMethod(m){
  payMethod=m;
  document.querySelectorAll('.pay-card').forEach(c=>c.classList.remove('selected'));
  document.getElementById('paymethod-'+m).classList.add('selected');
  const mNames={cash:'เงินสด',transfer:'โอนเงิน',promptpay:'PromptPay',card:'บัตรเครดิต'};
  document.getElementById('ps-method').textContent=mNames[m];
  const ppSection=document.getElementById('promptpay-section');
  if(m==='promptpay'){
    ppSection.style.display='block';
    const pp=settings.promptpay||'กรุณาตั้งค่าเลข PromptPay ใน Settings';
    document.getElementById('pp-number').textContent=pp;
    const ppEl=document.getElementById('pp-qr');
    ppEl.innerHTML='';
    if(settings.promptpay){
      new QRCode(ppEl,{text:'promptpay:'+settings.promptpay,width:160,height:160,colorDark:'#000',colorLight:'#fff',correctLevel:QRCode.CorrectLevel.H});
    }
  } else { ppSection.style.display='none'; }
}
function savePayment(){
  const memberId=document.getElementById('pay-member').value;
  const plan=document.getElementById('pay-plan').value;
  const amount=Number(document.getElementById('pay-amount').value);
  const date=document.getElementById('pay-date').value||new Date().toISOString();
  const note=document.getElementById('pay-note').value;
  if(!memberId){ showToast('กรุณาเลือกสมาชิก','⚠️'); return; }
  const m=members.find(x=>x.id===memberId);
  const mNames={cash:'เงินสด',transfer:'โอนเงิน',promptpay:'PromptPay',card:'บัตรเครดิต'};
  payments.push({id:'PAY-'+Date.now(),memberId,memberName:m?.name||'',plan,amount,method:mNames[payMethod],date:new Date(date).toISOString(),status:'paid',note});
  if(m){ const i=members.findIndex(x=>x.id===memberId); members[i].payStatus='paid'; }
  save(); closeModal('modal-pay'); renderPayments(); renderDashboard();
  showToast('บันทึกการชำระเงินแล้ว 💰','💳');
  if(notifSettings.payment) sendLineNotification(`💰 รับชำระเงิน!\n${m?.name} - ${plan}\nจำนวน: ฿${fmtMoney(amount)}\nวิธี: ${mNames[payMethod]}`);
}

// ============================================================
// REPORT
// ============================================================
function renderReport(){
  // Plans
  const planCount={};
  members.forEach(m=>{ planCount[m.plan]=(planCount[m.plan]||0)+1; });
  document.getElementById('rpt-plans').innerHTML=Object.entries(planCount).sort((a,b)=>b[1]-a[1]).map(([k,v])=>
    `<li class="report-item"><span>${k}</span><span class="report-val">${v} คน</span></li>`).join('');

  // Monthly checkins (last 6 months)
  const monthCI={};
  checkins.forEach(c=>{
    const d=new Date(c.time);
    const k=`${d.getFullYear()}-${String(d.getMonth()+1).padStart(2,'0')}`;
    monthCI[k]=(monthCI[k]||0)+1;
  });
  const sortedMonths=Object.entries(monthCI).sort((a,b)=>b[0].localeCompare(a[0])).slice(0,6);
  document.getElementById('rpt-monthly').innerHTML=sortedMonths.map(([k,v])=>
    `<li class="report-item"><span>${k}</span><span class="report-val">${v} ครั้ง</span></li>`).join('')||'<li class="report-item" style="color:var(--muted)">ยังไม่มีข้อมูล</li>';

  // Revenue by plan
  const planRev={};
  payments.filter(p=>p.status==='paid').forEach(p=>{ planRev[p.plan]=(planRev[p.plan]||0)+Number(p.amount); });
  document.getElementById('rpt-revenue').innerHTML=Object.entries(planRev).sort((a,b)=>b[1]-a[1]).map(([k,v])=>
    `<li class="report-item"><span>${k}</span><span class="report-val">฿${fmtMoney(v)}</span></li>`).join('')||'<li class="report-item" style="color:var(--muted)">ยังไม่มีข้อมูล</li>';

  // Expiring soon
  const soon=members.filter(m=>{ const d=daysLeft(m); return d!==null&&d>=0&&d<=30; }).sort((a,b)=>daysLeft(a)-daysLeft(b));
  const tbody=document.getElementById('rpt-expiry-tbody');
  document.getElementById('rpt-expiry-empty').style.display=soon.length?'none':'block';
  tbody.innerHTML=soon.map(m=>{
    const d=daysLeft(m);
    return `<tr>
      <td><div class="member-info"><div class="avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div><div>${m.name}</div></div></td>
      <td>${m.plan}</td><td>${fmtDate(m.expiry)}</td>
      <td style="color:${d<=7?'var(--danger)':'var(--accent)'};font-weight:600">${d} วัน</td>
      <td><button class="btn btn-ghost btn-sm" onclick="sendExpiryNotif('${m.id}')">📤 แจ้งเตือน Line</button></td>
    </tr>`;
  }).join('');
}
function sendExpiryNotif(id){
  const m=members.find(x=>x.id===id);
  if(!m) return;
  sendLineNotification(`⚠️ แจ้งเตือนหมดอายุ\n${m.name} (${m.id})\nแพ็กเกจ: ${m.plan}\nหมดอายุ: ${fmtDate(m.expiry)}\nเหลือ: ${daysLeft(m)} วัน`);
  showToast('ส่งแจ้งเตือนแล้ว','📤');
}

// ============================================================
// LINE NOTIFY
// ============================================================
function renderNotify(){
  // Load token
  if(lineToken) document.getElementById('line-token').value=lineToken;
  updateLineStatus();
  // Load notif settings
  document.getElementById('notif-checkin').checked=notifSettings.checkin;
  document.getElementById('notif-expiry').checked=notifSettings.expiry;
  document.getElementById('notif-newmember').checked=notifSettings.newmember;
  document.getElementById('notif-payment').checked=notifSettings.payment;
  // Member select
  const sel=document.getElementById('line-member-select');
  sel.innerHTML='<option value="all">ทุกคน (Broadcast)</option>'+members.map(m=>`<option value="${m.id}">${m.name}</option>`).join('');
  renderNotifLog();
}
function saveLineToken(){
  lineToken=document.getElementById('line-token').value.trim();
  localStorage.setItem('ic-linetoken',lineToken);
  updateLineStatus();
}
function updateLineStatus(){
  const dot=document.getElementById('line-dot');
  const txt=document.getElementById('line-status-text');
  if(lineToken){ dot.className='line-dot connected'; txt.textContent='เชื่อมต่อแล้ว'; }
  else { dot.className='line-dot'; txt.textContent='ยังไม่ได้เชื่อมต่อ'; }
}
function saveNotifSettings(){
  notifSettings={
    checkin:document.getElementById('notif-checkin').checked,
    expiry:document.getElementById('notif-expiry').checked,
    newmember:document.getElementById('notif-newmember').checked,
    payment:document.getElementById('notif-payment').checked
  };
  localStorage.setItem('ic-notifsettings',JSON.stringify(notifSettings));
  showToast('บันทึกตั้งค่าแจ้งเตือนแล้ว','🔔');
}
async function sendLineNotification(msg){
  if(!lineToken) return false;
  const entry={msg,time:new Date().toISOString(),status:'sending'};
  notifLog.unshift(entry);
  save();
  try{
    await fetch('https://notify-api.line.me/api/notify',{
      method:'POST',
      headers:{'Authorization':'Bearer '+lineToken,'Content-Type':'application/x-www-form-urlencoded'},
      body:'message='+encodeURIComponent('\n'+msg)
    });
    entry.status='sent';
  } catch(e){ entry.status='failed (CORS - use server)'; }
  save(); renderNotifLog(); return true;
}
async function testLineNotify(){
  if(!lineToken){ showToast('กรุณาใส่ Line Notify Token ก่อน','⚠️'); return; }
  const ok=await sendLineNotification(`🏋️ ทดสอบระบบ IRONCLUB PRO\nเวลา: ${new Date().toLocaleString('th-TH')}\nระบบทำงานปกติ ✅`);
  showToast(ok?'ส่งข้อความทดสอบแล้ว':'ไม่มี Token','📤');
}
function sendLineMsg(){
  const msg=document.getElementById('line-msg').value.trim();
  if(!msg){ showToast('กรุณาพิมพ์ข้อความ','⚠️'); return; }
  sendLineNotification(msg);
  showToast('ส่งข้อความแล้ว','📤');
  document.getElementById('line-msg').value='';
}
function fillLineTemplate(){
  const type=document.getElementById('line-msg-type').value;
  const gym=settings.gymname||'IRONCLUB Fitness';
  const tpls={
    expiry:`⚠️ แจ้งเตือนจาก ${gym}\nแพ็กเกจของท่านกำลังจะหมดอายุ\nสนใจต่ออายุสมาชิก กรุณาติดต่อเจ้าหน้าที่`,
    promo:`🎉 โปรโมชันพิเศษ ${gym}!\n[ใส่รายละเอียดโปรโมชัน]\nสนใจติดต่อ: ${settings.phone||''}`,
    holiday:`🌟 ${gym}\nหยุดให้บริการวันที่ [วันที่]\nขออภัยในความไม่สะดวก`
  };
  if(tpls[type]) document.getElementById('line-msg').value=tpls[type];
}
function renderNotifLog(){
  const el=document.getElementById('notify-log');
  if(!notifLog.length){ el.innerHTML=`<div class="empty-state" style="padding:1.5rem"><div class="empty-icon">📭</div><div>ยังไม่มีการแจ้งเตือน</div></div>`; return; }
  el.innerHTML=notifLog.slice(0,20).map(n=>`
    <div class="notify-item">
      <span style="flex:1;font-size:0.8rem;color:var(--text)">${n.msg.split('\n')[0]}</span>
      <span style="font-size:0.7rem;color:${n.status==='sent'?'var(--success)':'var(--muted)'}">${n.status==='sent'?'✅':n.status} · ${fmtTime(n.time)}</span>
    </div>`).join('');
}

// ============================================================
// HISTORY
// ============================================================
function renderHistory(){
  const from=document.getElementById('hist-from')?.value;
  const to=document.getElementById('hist-to')?.value;
  let list=checkins;
  if(from) list=list.filter(c=>new Date(c.time)>=new Date(from));
  if(to) list=list.filter(c=>new Date(c.time)<=new Date(to+'T23:59:59'));
  const tbody=document.getElementById('history-tbody');
  const empty=document.getElementById('history-empty');
  if(!list.length){ tbody.innerHTML=''; empty.style.display='block'; return; }
  empty.style.display='none';
  tbody.innerHTML=[...list].reverse().map(c=>{
    const m=members.find(x=>x.id===c.memberId);
    if(!m) return '';
    return `<tr>
      <td><div class="member-info"><div class="avatar" style="background:${avatarColor(m.id)};color:#000">${initials(m.name)}</div><div>${m.name}</div></div></td>
      <td style="color:var(--muted)">${m.id}</td><td>${m.plan}</td>
      <td>${fmtDate(c.time)}</td><td>${fmtTime(c.time)}</td></tr>`;
  }).join('');
}

// ============================================================
// SETTINGS
// ============================================================
function loadSettings(){
  document.getElementById('set-gymname').value=settings.gymname||'';
  document.getElementById('set-phone').value=settings.phone||'';
  document.getElementById('set-address').value=settings.address||'';
  document.getElementById('set-promptpay').value=settings.promptpay||'';
  document.getElementById('price-monthly').value=prices['รายเดือน']||800;
  document.getElementById('price-3m').value=prices['3 เดือน']||2100;
  document.getElementById('price-6m').value=prices['6 เดือน']||3600;
  document.getElementById('price-yearly').value=prices['รายปี']||6000;
  document.getElementById('price-once').value=prices['รายครั้ง']||100;
}
function saveSettings(){
  settings={
    gymname:document.getElementById('set-gymname').value,
    phone:document.getElementById('set-phone').value,
    address:document.getElementById('set-address').value,
    promptpay:document.getElementById('set-promptpay').value
  };
  localStorage.setItem('ic-settings',JSON.stringify(settings));
  showToast('บันทึกการตั้งค่าแล้ว','⚙️');
}
function savePrices(){
  prices={'รายเดือน':Number(document.getElementById('price-monthly').value),
    '3 เดือน':Number(document.getElementById('price-3m').value),
    '6 เดือน':Number(document.getElementById('price-6m').value),
    'รายปี':Number(document.getElementById('price-yearly').value),
    'รายครั้ง':Number(document.getElementById('price-once').value)};
  localStorage.setItem('ic-prices',JSON.stringify(prices));
  showToast('บันทึกราคาแพ็กเกจแล้ว','💰');
}

// ============================================================
// EXCEL EXPORT
// ============================================================
function exportExcel(){
  const ws=XLSX.utils.json_to_sheet(members.map(m=>({
    'รหัสสมาชิก':m.id,'ชื่อ-นามสกุล':m.name,'เบอร์โทร':m.phone,'อีเมล':m.email||'',
    'เพศ':m.gender||'','วันเกิด':m.dob||'','แพ็กเกจ':m.plan,'วันเริ่ม':m.start,
    'วันหมดอายุ':m.expiry,'สถานะ':isActive(m)?'Active':'หมดอายุ',
    'ชำระเงิน':m.payStatus==='paid'?'ชำระแล้ว':'ค้างชำระ','หมายเหตุ':m.note||''
  })));
  const wb=XLSX.utils.book_new();
  XLSX.utils.book_append_sheet(wb,ws,'สมาชิก');
  XLSX.writeFile(wb,`ironclub-members-${new Date().toISOString().split('T')[0]}.xlsx`);
  showToast('Export Excel สำเร็จ','📥');
}
function exportPaymentExcel(){
  const ws=XLSX.utils.json_to_sheet(payments.map(p=>({
    'รหัสการชำระ':p.id,'สมาชิก':p.memberName,'แพ็กเกจ':p.plan,
    'จำนวน (บาท)':p.amount,'วิธีชำระ':p.method,'วันที่':fmtDate(p.date),
    'สถานะ':p.status==='paid'?'ชำระแล้ว':'รอชำระ','หมายเหตุ':p.note||''
  })));
  const wb=XLSX.utils.book_new();
  XLSX.utils.book_append_sheet(wb,ws,'การชำระเงิน');
  XLSX.writeFile(wb,`ironclub-payments-${new Date().toISOString().split('T')[0]}.xlsx`);
  showToast('Export Excel สำเร็จ','📥');
}
function exportHistoryExcel(){
  const ws=XLSX.utils.json_to_sheet(checkins.map(c=>{
    const m=members.find(x=>x.id===c.memberId);
    return {'สมาชิก':m?.name||'','รหัส':c.memberId,'แพ็กเกจ':m?.plan||'','วันที่':fmtDate(c.time),'เวลา':fmtTime(c.time)};
  }));
  const wb=XLSX.utils.book_new();
  XLSX.utils.book_append_sheet(wb,ws,'ประวัติเช็คอิน');
  XLSX.writeFile(wb,`ironclub-checkin-${new Date().toISOString().split('T')[0]}.xlsx`);
  showToast('Export Excel สำเร็จ','📥');
}
function exportReportExcel(){
  const wb=XLSX.utils.book_new();
  const s1=XLSX.utils.json_to_sheet(members.map(m=>({
    'ชื่อ':m.name,'แพ็กเกจ':m.plan,'สถานะ':isActive(m)?'Active':'หมดอายุ','วันหมดอายุ':m.expiry,'เช็คอิน':checkins.filter(c=>c.memberId===m.id).length,'ชำระ':m.payStatus
  })));
  const s2=XLSX.utils.json_to_sheet(payments.map(p=>({'สมาชิก':p.memberName,'แพ็กเกจ':p.plan,'จำนวน':p.amount,'วิธี':p.method,'วันที่':fmtDate(p.date)})));
  XLSX.utils.book_append_sheet(wb,s1,'สมาชิก');
  XLSX.utils.book_append_sheet(wb,s2,'การชำระเงิน');
  XLSX.writeFile(wb,`ironclub-report-${new Date().toISOString().split('T')[0]}.xlsx`);
  showToast('Export รายงานสำเร็จ','📊');
}

// ============================================================
// BACKUP
// ============================================================
function exportBackup(){
  const data={members,checkins,payments,settings,prices,notifSettings,exportDate:new Date().toISOString()};
  const blob=new Blob([JSON.stringify(data,null,2)],{type:'application/json'});
  const a=document.createElement('a'); a.href=URL.createObjectURL(blob);
  a.download=`ironclub-backup-${new Date().toISOString().split('T')[0]}.json`; a.click();
  showToast('Export Backup สำเร็จ','📦');
}
function importBackup(e){
  const file=e.target.files[0]; if(!file) return;
  const reader=new FileReader();
  reader.onload=ev=>{
    try{
      const data=JSON.parse(ev.target.result);
      if(data.members) members=data.members;
      if(data.checkins) checkins=data.checkins;
      if(data.payments) payments=data.payments;
      if(data.settings) settings=data.settings;
      if(data.prices) prices=data.prices;
      save();
      localStorage.setItem('ic-settings',JSON.stringify(settings));
      localStorage.setItem('ic-prices',JSON.stringify(prices));
      showToast('Import Backup สำเร็จ','📦');
      renderDashboard();
    } catch{ showToast('ไฟล์ไม่ถูกต้อง','❌'); }
  };
  reader.readAsText(file);
}
function clearAllData(){
  if(!confirm('⚠️ ต้องการล้างข้อมูลทั้งหมด? ไม่สามารถกู้คืนได้!')) return;
  members=[]; checkins=[]; payments=[]; notifLog=[];
  save(); renderDashboard(); showToast('ล้างข้อมูลทั้งหมดแล้ว','🗑️');
}

// ============================================================
// MODAL
// ============================================================
function openModal(id){ document.getElementById(id).classList.add('open'); }
function closeModal(id){ document.getElementById(id).classList.remove('open'); }
document.querySelectorAll('.modal-overlay').forEach(o=>{
  o.addEventListener('click',e=>{ if(e.target===o) o.classList.remove('open'); });
});

// ============================================================
// INIT
// ============================================================
renderDashboard();
if(!members.length){
  const samples=[
    {name:'สมชาย ใจดี',phone:'081-234-5678',plan:'รายเดือน',gender:'ชาย',payStatus:'paid'},
    {name:'สมหญิง สวยงาม',phone:'082-345-6789',plan:'3 เดือน',gender:'หญิง',payStatus:'paid'},
    {name:'วิชัย กล้าแกร่ง',phone:'083-456-7890',plan:'รายปี',gender:'ชาย',payStatus:'paid'},
    {name:'มินตรา ดีใจ',phone:'084-567-8901',plan:'6 เดือน',gender:'หญิง',payStatus:'unpaid'},
  ];
  samples.forEach((s,i)=>{
    const start=new Date(); start.setDate(start.getDate()-i*8);
    const startStr=start.toISOString().split('T')[0];
    const m={id:genId(),name:s.name,phone:s.phone,plan:s.plan,start:startStr,
      expiry:getExpiry(startStr,s.plan),gender:s.gender,email:'',dob:'',note:'',
      payStatus:s.payStatus,price:prices[s.plan],joinDate:start.toISOString()};
    members.push(m);
    if(s.payStatus==='paid'){
      payments.push({id:'PAY-'+i,memberId:m.id,memberName:m.name,plan:m.plan,amount:prices[m.plan],method:'เงินสด',date:start.toISOString(),status:'paid',note:''});
    }
  });
  save(); renderDashboard();
}
</script>
</body>
</html>
