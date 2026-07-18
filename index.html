<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Mind Dlink — Liquid Glass Demo</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#eef0ff;
    --ink-dim:rgba(238,240,255,.68);
    --ink-faint:rgba(238,240,255,.45);
    --brand:#7c6cff;
    --brand-2:#4fc3ff;
    --gold:#f2c46d;
    --card:rgba(255,255,255,.055);
    --card-line:rgba(255,255,255,.12);
    --radius:22px;
    --page-bg:#0b0b1e;
    --grid-line:rgba(255,255,255,.045);
    --stat-bg:rgba(255,255,255,.045);
    --stat-line:rgba(255,255,255,.08);
    /* Độ "dim" của liquid blur — 0 = trong suốt như kính sạch, 1 = mờ đục hẳn.
       Đây là biến trung tâm mà JS đọc lại để dựng config cho thư viện.
       Đặt thấp để kính trong, dễ đọc chữ menu/pill phía dưới. */
    --lg-dim:.18;
  }
  *{margin:0;padding:0;box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{
    font-family:'Be Vietnam Pro',system-ui,sans-serif;
    background:var(--page-bg);
    color:var(--ink);
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
    transition:background .5s ease, color .5s ease;
  }

  /* ===== THEME SÁNG ===== */
  body.theme-light{
    --ink:#151327;
    --ink-dim:rgba(21,19,39,.66);
    --ink-faint:rgba(21,19,39,.42);
    --card:rgba(255,255,255,.5);
    --card-line:rgba(21,19,39,.1);
    --page-bg:#eef0fb;
    --grid-line:rgba(21,19,39,.05);
    --stat-bg:rgba(255,255,255,.55);
    --stat-line:rgba(21,19,39,.08);
  }

  /* ===== ROOT (LiquidGlass root) ===== */
  #root{position:relative;min-height:100vh}

  /* Nền: phải là con của root để shader "nhìn thấy".
     position:fixed => nền đứng yên, không cuộn theo nội dung,
     để lộ rõ glassmorphism khi card/nav trôi ngang qua. */
  .bg{
    position:fixed;inset:0;z-index:0;pointer-events:none;
    background:
      radial-gradient(900px 600px at 12% -5%, rgba(124,108,255,.55), transparent 60%),
      radial-gradient(800px 560px at 88% 8%, rgba(79,195,255,.38), transparent 60%),
      radial-gradient(700px 700px at 75% 62%, rgba(255,110,199,.22), transparent 60%),
      radial-gradient(760px 640px at 15% 90%, rgba(94,234,212,.16), transparent 60%),
      linear-gradient(180deg,#101034 0%, #0b0b1e 55%, #0d0a24 100%);
    transition:opacity .5s ease;
  }
  body.theme-light .bg{
    background:
      radial-gradient(900px 600px at 12% -5%, rgba(124,108,255,.28), transparent 60%),
      radial-gradient(800px 560px at 88% 8%, rgba(79,195,255,.22), transparent 60%),
      radial-gradient(700px 700px at 75% 62%, rgba(255,110,199,.16), transparent 60%),
      radial-gradient(760px 640px at 15% 90%, rgba(94,234,212,.14), transparent 60%),
      linear-gradient(180deg,#f5f6ff 0%, #eef0fb 55%, #eee9fb 100%);
  }
  .bg::before{ /* lưới mờ tạo chi tiết cho khúc xạ */
    content:"";position:absolute;inset:0;
    background-image:
      linear-gradient(var(--grid-line) 1px, transparent 1px),
      linear-gradient(90deg, var(--grid-line) 1px, transparent 1px);
    background-size:56px 56px;
    mask-image:radial-gradient(1200px 800px at 50% 0%, #000 30%, transparent 75%);
  }
  .bg .orb{position:absolute;border-radius:50%;filter:blur(2px);opacity:.9}
  .bg .o1{width:130px;height:130px;top:150px;left:6%;
    background:radial-gradient(circle at 32% 30%, #b7aaff, #6a57f0 60%, #3a2fae)}
  .bg .o2{width:80px;height:80px;top:430px;right:10%;
    background:radial-gradient(circle at 32% 30%, #9fe2ff, #38a8ee 60%, #1e6fb3)}
  .bg .o3{width:56px;height:56px;top:70px;right:28%;
    background:radial-gradient(circle at 32% 30%, #ffd9a8, #f2a94d 65%, #b26e1e)}

  /* ===== NỘI DUNG ===== */
  .content{position:relative;z-index:1}
  .wrap{max-width:1080px;margin:0 auto;padding:0 22px}
  section{padding:72px 0}

  .eyebrow{
    font-size:12px;font-weight:700;letter-spacing:.22em;text-transform:uppercase;
    color:var(--brand-2);margin-bottom:14px;
  }
  h1{font-size:clamp(34px,5.4vw,58px);font-weight:800;line-height:1.12;letter-spacing:-.02em}
  h2{font-size:clamp(24px,3.4vw,34px);font-weight:800;letter-spacing:-.015em;margin-bottom:10px}
  .sub{color:var(--ink-dim);font-size:16px;line-height:1.65;max-width:560px}

  /* ===== HERO ===== */
  .hero{padding:170px 0 60px}
  .hero h1 .grad{
    background:linear-gradient(92deg,#b7aaff 0%, #7c6cff 45%, #4fc3ff 100%);
    -webkit-background-clip:text;background-clip:text;color:transparent;
  }
  .hero .sub{margin:20px 0 30px}
  .cta-row{display:flex;flex-wrap:wrap;gap:12px;align-items:center}
  .btn{
    display:inline-flex;align-items:center;gap:8px;
    padding:13px 24px;border-radius:999px;font-weight:600;font-size:15px;
    text-decoration:none;color:var(--ink);border:1px solid var(--card-line);
    background:var(--card);backdrop-filter:blur(10px);-webkit-backdrop-filter:blur(10px);
    transition:transform .15s ease, background .15s ease;
  }
  .btn:hover{transform:translateY(-2px);background:rgba(255,255,255,.1)}
  .btn.primary{
    border:none;color:#fff;
    background:linear-gradient(92deg,#7c6cff,#5a8bff);
    box-shadow:0 8px 28px rgba(124,108,255,.45);
  }
  .badges{display:flex;flex-wrap:wrap;gap:10px;margin-top:26px}
  .chip{
    font-size:13px;font-weight:500;color:var(--ink-dim);
    padding:8px 14px;border-radius:999px;
    background:rgba(255,255,255,.04);border:1px solid rgba(255,255,255,.09);
  }
  .chip b{color:var(--ink);font-weight:600}

  /* ===== BẢNG ĐIỀU KHIỂN (mock) ===== */
  .dash{
    margin-top:56px;border-radius:26px;overflow:hidden;
    border:1px solid var(--card-line);
    background:linear-gradient(180deg, rgba(255,255,255,.08), rgba(255,255,255,.03));
    backdrop-filter:blur(18px);-webkit-backdrop-filter:blur(18px);
    box-shadow:0 30px 80px rgba(0,0,0,.45);
  }
  .dash-top{
    display:flex;align-items:center;gap:10px;
    padding:14px 18px;border-bottom:1px solid rgba(255,255,255,.08);
    font-weight:600;font-size:14px;
  }
  .dot{width:10px;height:10px;border-radius:50%}
  .dash-body{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;padding:18px}
  .stat{
    padding:16px;border-radius:16px;
    background:var(--stat-bg);border:1px solid var(--stat-line);
  }
  .stat .k{font-size:12px;color:var(--ink-faint);font-weight:600;letter-spacing:.04em;text-transform:uppercase}
  .stat .v{font-size:28px;font-weight:800;margin:4px 0 2px}
  .stat .d{font-size:12.5px;color:#7ee2b8;font-weight:600}

  /* ===== WORKFLOW ===== */
  .flow{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;margin-top:34px}
  .card{
    padding:24px;border-radius:var(--radius);
    background:var(--card);border:1px solid var(--card-line);
    backdrop-filter:blur(14px);-webkit-backdrop-filter:blur(14px);
  }
  .card .ic{
    width:42px;height:42px;border-radius:12px;display:grid;place-items:center;
    background:rgba(124,108,255,.18);color:#b7aaff;font-size:19px;margin-bottom:14px;
  }
  .card h3{font-size:16.5px;font-weight:700;margin-bottom:6px}
  .card p{font-size:14px;color:var(--ink-dim);line-height:1.6}

  /* ===== BẢNG GIÁ ===== */
  .plans{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;margin-top:38px;align-items:stretch}
  .plan{
    position:relative;padding:28px 24px;border-radius:26px;display:flex;flex-direction:column;
    background:var(--card);border:1px solid var(--card-line);
    backdrop-filter:blur(14px);-webkit-backdrop-filter:blur(14px);
  }
  .plan.rec{
    background:linear-gradient(180deg, rgba(124,108,255,.22), rgba(124,108,255,.06));
    border:1px solid rgba(158,142,255,.45);
    box-shadow:0 20px 60px rgba(124,108,255,.28);
  }
  .plan.gold{border:1px solid rgba(242,196,109,.35)}
  .plan .tag{font-size:11px;font-weight:700;letter-spacing:.18em;text-transform:uppercase;color:var(--brand-2)}
  .plan.gold .tag{color:var(--gold)}
  .plan h3{font-size:24px;font-weight:800;margin:6px 0 2px}
  .plan .for{font-size:13px;color:var(--ink-faint)}
  .price{font-size:30px;font-weight:800;margin:16px 0 18px}
  .price small{font-size:14px;font-weight:500;color:var(--ink-faint)}
  .plan ul{list-style:none;font-size:14px;color:var(--ink-dim);display:grid;gap:9px;margin-bottom:24px}
  .plan li::before{content:"✓";color:#7ee2b8;font-weight:700;margin-right:9px}
  .plan li.lock{color:var(--ink-faint)}
  .plan li.lock::before{content:"◇";color:var(--gold)}
  .plan .btn{justify-content:center;margin-top:auto}
  .rec-flag{
    position:absolute;top:-12px;right:20px;font-size:11.5px;font-weight:700;
    padding:5px 12px;border-radius:999px;color:#fff;
    background:linear-gradient(92deg,#7c6cff,#5a8bff);
  }

  /* ===== THANH TOÁN ===== */
  .steps{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-top:34px}
  .step{
    text-align:center;padding:26px 16px;border-radius:var(--radius);
    background:var(--card);border:1px solid var(--card-line);
    backdrop-filter:blur(14px);-webkit-backdrop-filter:blur(14px);
  }
  .step .n{
    width:30px;height:30px;margin:0 auto 12px;border-radius:10px;
    display:grid;place-items:center;font-size:13.5px;font-weight:700;color:#fff;
    background:linear-gradient(135deg,#7c6cff,#5a8bff);
  }
  .step h4{font-size:15px;font-weight:700;margin-bottom:5px}
  .step p{font-size:13px;color:var(--ink-dim);line-height:1.55}

  /* ===== FAQ + LIÊN HỆ ===== */
  .faq{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-top:30px}
  .faq .card h3{font-size:15px}
  .contact{
    margin-top:60px;display:flex;flex-wrap:wrap;gap:20px;align-items:center;justify-content:space-between;
    padding:30px;border-radius:26px;
    background:linear-gradient(92deg, rgba(124,108,255,.2), rgba(79,195,255,.12));
    border:1px solid rgba(158,142,255,.3);
  }
  .contact h2{margin-bottom:6px}
  .contact p{font-size:14px;color:var(--ink-dim)}

  footer{
    padding:36px 0 130px;border-top:1px solid rgba(255,255,255,.07);
    font-size:13px;color:var(--ink-faint);text-align:center;
  }

  /* ===== GLASS ELEMENTS (con trực tiếp của #root) ===== */
  /* Viên nang chính — co theo nội dung (giống tab bar iOS 26 trong ảnh
     mẫu), KHÔNG kéo full-width nữa. Không có background riêng: màu
     đến hoàn toàn từ canvas WebGL (hoặc .css-glass fallback theo theme). */
  .lg-nav{
    position:fixed;top:16px;left:50%;transform:translateX(-50%);
    z-index:52;
    display:inline-flex;align-items:center;gap:26px;
    padding:10px 14px 10px 10px;border-radius:999px;color:var(--ink);
    transition:transform .35s ease, opacity .35s ease;
    width:max-content;
  }
  /* Nav trượt ẩn lên trên khi cuộn xuống, trượt về khi cuộn lên (sliding nav) */
  .lg-nav.nav-hidden{transform:translateX(-50%) translateY(-160%);opacity:0}
  .lg-nav .logo{display:flex;align-items:center;gap:9px;font-weight:800;font-size:15px;white-space:nowrap}
  .lg-nav .logo .m{
    width:28px;height:28px;border-radius:9px;display:grid;place-items:center;
    background:linear-gradient(135deg,#7c6cff,#4fc3ff);color:#fff;font-size:13px;font-weight:800;
  }
  .lg-nav nav{display:flex;gap:18px}
  .lg-nav nav a{
    position:relative;z-index:2; /* đứng trên canvas WebGL của indicator */
    font-size:13.5px;font-weight:500;color:var(--ink-dim);text-decoration:none;
    white-space:nowrap;padding:6px 2px;
  }
  .lg-nav nav a:hover,.lg-nav nav a.active{color:var(--ink)}

  /* Viên bi glass trượt bên trong nav — indicator, không phải khung
     chứa text. Kích thước/vị trí do JS tính theo link đang hover,
     transition mượt để tạo cảm giác "chảy" (liquid) từ tab này sang
     tab khác, đúng như thanh tab bar iOS trong ảnh mẫu. */
  .lg-tab-indicator{
    position:fixed;top:0;left:0;z-index:51; /* dưới nav (52) — nav sẽ
       khúc xạ/hiện thị nó qua lớp kính trong suốt của nav phía trên */
    width:0;height:0;border-radius:999px;
    pointer-events:none;opacity:0;
    transition:opacity .2s ease, left .32s cubic-bezier(.34,1.4,.4,1),
      top .32s cubic-bezier(.34,1.4,.4,1), width .32s cubic-bezier(.34,1.4,.4,1),
      height .32s cubic-bezier(.34,1.4,.4,1);
  }
  .lg-tab-indicator.visible{opacity:1}

  /* Viên nang phụ — tách biệt bên phải viên nang chính, cùng khoảng
     cách top để trông như một cụm, đúng bố cục tab-bar + search rời
     trong ảnh mẫu iOS. */
  .lg-actions{
    position:fixed;top:16px;right:16px;z-index:50;
    display:inline-flex;align-items:center;gap:10px;
    padding:8px 10px;border-radius:999px;color:var(--ink);
    transition:transform .35s ease, opacity .35s ease;
  }
  .lg-actions.nav-hidden{transform:translateY(-160%);opacity:0}
  .lg-actions .join{
    font-size:13px;font-weight:700;color:#fff;text-decoration:none;
    padding:8px 16px;border-radius:999px;white-space:nowrap;
    background:linear-gradient(92deg,#7c6cff,#5a8bff);
  }

  .lg-pill{
    position:fixed;right:26px;bottom:26px;z-index:50;cursor:grab;
    display:flex;align-items:center;gap:10px;
    padding:14px 20px;border-radius:999px;user-select:none;touch-action:none;
    white-space:nowrap;
  }
  .lg-pill:active{cursor:grabbing}
  .lg-pill .qr{
    width:26px;height:26px;border-radius:7px;display:grid;place-items:center;
    background:#fff;color:#d6262e;font-size:10px;font-weight:800;
  }
  .lg-pill span{font-size:13.5px;font-weight:700}
  .lg-pill small{display:block;font-size:11px;font-weight:500;color:var(--ink-dim)}

  /* Nút chuyển sáng/tối — nằm bên trong nav kính, không phải glass riêng
     (tránh chồng lấn với nav full-width) */
  .theme-toggle{
    width:34px;height:34px;border-radius:10px;border:1px solid var(--card-line);
    background:var(--card);color:var(--ink);font-size:15px;
    display:grid;place-items:center;cursor:pointer;flex:none;
  }
  .theme-toggle:hover{filter:brightness(1.15)}

  /* Fallback CSS-glass nếu WebGL/CDN không chạy */
  /* Fallback CSS-glass nếu WebGL/CDN không chạy (vd mở bằng file:// và
     trình duyệt chặn import module từ CDN). Phải đọc theo biến theme
     --card/--card-line, KHÔNG hard-code trắng, nếu không nav sẽ giữ
     màu tối kể cả khi đã bật theme sáng ("ngược màu"). */
  .css-glass{
    background:var(--card);
    border:1px solid var(--card-line);
    backdrop-filter:blur(22px) saturate(1.6);
    -webkit-backdrop-filter:blur(22px) saturate(1.6);
    box-shadow:0 12px 40px rgba(0,0,0,.28);
  }
  body.theme-light .css-glass{box-shadow:0 12px 34px rgba(21,19,39,.14)}

  #lg-status{
    position:fixed;left:14px;bottom:14px;z-index:60;
    font-size:11px;color:var(--ink-faint);
    background:rgba(0,0,0,.35);padding:5px 10px;border-radius:8px;
    backdrop-filter:blur(6px);
  }

  @media (max-width:860px){
    .dash-body,.flow,.plans{grid-template-columns:1fr}
    .steps{grid-template-columns:1fr 1fr}
    .faq{grid-template-columns:1fr}
    .lg-nav nav{display:none}
    .hero{padding-top:130px}
    .theme-toggle{width:32px;height:32px;font-size:14px}
    .lg-pill small{display:none}
    .lg-actions .join{padding:7px 12px;font-size:12px}
  }
  @media (prefers-reduced-motion:reduce){
    *{transition:none!important;animation:none!important}
  }
</style>
</head>
<body>
<div id="root">

  <!-- Nền (con của root để glass khúc xạ được) -->
  <div class="bg">
    <div class="orb o1"></div>
    <div class="orb o2"></div>
    <div class="orb o3"></div>
  </div>

  <!-- ===== NỘI DUNG TRANG ===== -->
  <div class="content">
    <div class="wrap">

      <header class="hero" id="top">
        <div class="eyebrow">Mind Dlink</div>
        <h1>Lưu link, quản lý tri thức<br>và nâng cấp bằng <span class="grad">VietQR</span></h1>
        <p class="sub">Mind Dlink giúp bạn gom, tìm và khai thác lại mọi đường dẫn quan trọng — có AI tóm tắt, gắn tag và đồng bộ theo tài khoản.</p>
        <div class="cta-row">
          <a class="btn primary" href="#plans">Bắt đầu miễn phí →</a>
          <a class="btn" href="#plans">Xem gói dịch vụ</a>
          <a class="btn" href="#top">⇣ Tải extension Chrome/Edge</a>
        </div>
        <div class="badges">
          <div class="chip"><b>QR</b> VietQR</div>
          <div class="chip">✓ Không tự động trừ tiền</div>
          <div class="chip">⇣ Dữ liệu thuộc về bạn</div>
          <div class="chip">↗ Dễ nâng cấp, dễ gia hạn</div>
        </div>

        <div class="dash">
          <div class="dash-top">
            <span class="dot" style="background:#7c6cff"></span>
            <span class="dot" style="background:#4fc3ff"></span>
            <span class="dot" style="background:#7ee2b8"></span>
            Bảng điều khiển Mind Dlink
          </div>
          <div class="dash-body">
            <div class="stat"><div class="k">Tổng link</div><div class="v">1.248</div><div class="d">+128 link tuần này</div></div>
            <div class="stat"><div class="k">AI tóm tắt</div><div class="v">342</div><div class="d">+86 tóm tắt mới</div></div>
            <div class="stat"><div class="k">Bộ sưu tập</div><div class="v">26</div><div class="d">+4 bộ sưu tập mới</div></div>
          </div>
        </div>
      </header>

      <section id="features">
        <div class="eyebrow">Workflow</div>
        <h2>Từ link rời rạc đến kho tri thức có ngữ cảnh</h2>
        <p class="sub">Mind Dlink thay thế việc lưu link thủ công bằng một workflow có AI hỗ trợ.</p>
        <div class="flow">
          <div class="card"><div class="ic">🔍</div><h3>Khó tìm lại</h3><p>Bookmark cũ nằm rải rác nhiều nơi, mỗi trình duyệt một kiểu.</p></div>
          <div class="card"><div class="ic">🏷️</div><h3>Thiếu ngữ cảnh</h3><p>Không nhớ vì sao đã lưu link, lưu xong rồi bỏ quên.</p></div>
          <div class="card"><div class="ic">✨</div><h3>Giải pháp</h3><p>AI tóm tắt nội dung, gợi ý tag và tự động phân loại để tìm lại trong vài giây.</p></div>
        </div>
      </section>

      <section id="plans">
        <div class="eyebrow">Gói dịch vụ</div>
        <h2>Chọn gói vừa đủ cho cách bạn làm việc</h2>
        <p class="sub">Thanh toán đơn giản, không tự động gia hạn. Nâng cấp hoặc hạ cấp bất cứ lúc nào.</p>
        <div class="plans">
          <div class="plan">
            <div class="tag">Bắt đầu ngay</div>
            <h3>Free</h3><div class="for">Thử và lưu cơ bản</div>
            <div class="price">0đ <small>/ tháng</small></div>
            <ul>
              <li>1.500 link trong kho</li>
              <li>100 lượt AI mỗi tháng</li>
              <li>100 MB dung lượng tệp</li>
              <li>Cloud Sync theo tài khoản</li>
              <li>Backup và khôi phục dữ liệu</li>
              <li class="lock">Kho cá nhân (từ Gold)</li>
              <li class="lock">Bảo vệ trẻ em (từ Gold)</li>
            </ul>
            <a class="btn" href="#top">Bắt đầu miễn phí</a>
          </div>
          <div class="plan rec">
            <div class="rec-flag">Đề xuất</div>
            <div class="tag">Đề xuất</div>
            <h3>Silver</h3><div class="for">Cá nhân dùng thường xuyên</div>
            <div class="price">50.000đ <small>/ tháng</small></div>
            <ul>
              <li>5.000 link trong kho</li>
              <li>1.000 lượt AI mỗi tháng</li>
              <li>2 GB dung lượng tệp</li>
              <li>AI tóm tắt nội dung link</li>
              <li>Gợi ý tag & tìm kiếm thông minh</li>
              <li>Lịch sử phiên bản, hỗ trợ ưu tiên</li>
              <li class="lock">Kho cá nhân (từ Gold)</li>
            </ul>
            <a class="btn primary" href="#pay">Chọn Silver</a>
          </div>
          <div class="plan gold">
            <div class="tag">Gói dịch vụ</div>
            <h3>Gold</h3><div class="for">Kho cá nhân, bảo mật và gia đình</div>
            <div class="price">80.000đ <small>/ tháng</small></div>
            <ul>
              <li>8.000 link trong kho</li>
              <li>2.000 lượt AI mỗi tháng</li>
              <li>4 GB dung lượng tệp</li>
              <li>Kho cá nhân & Kho bảo mật</li>
              <li>Quản lý link an toàn & Bảo vệ trẻ em</li>
              <li>Lịch sử phiên bản, hỗ trợ ưu tiên</li>
            </ul>
            <a class="btn" href="#pay">Đăng ký Gold</a>
          </div>
        </div>
      </section>

      <section id="pay">
        <div class="eyebrow">Thanh toán</div>
        <h2>Thanh toán VietQR/payOS minh bạch</h2>
        <p class="sub">Không tự động gia hạn, không lưu secret ở frontend. Kích hoạt gói sau khi giao dịch được xác nhận.</p>
        <div class="steps">
          <div class="step"><div class="n">1</div><h4>Nhập email</h4><p>Dùng email tài khoản Mind Dlink.</p></div>
          <div class="step"><div class="n">2</div><h4>Quét VietQR</h4><p>Tạo QR qua Edge Function.</p></div>
          <div class="step"><div class="n">3</div><h4>Xác nhận</h4><p>Webhook hoặc admin xác nhận thủ công.</p></div>
          <div class="step"><div class="n">4</div><h4>Kích hoạt</h4><p>Cập nhật hạn mức theo gói.</p></div>
        </div>

        <div class="faq">
          <div class="card"><h3>Mind Dlink có tự động trừ tiền không?</h3><p>Không. Thanh toán là một lần theo chu kỳ công bố.</p></div>
          <div class="card"><h3>Nếu Supabase lỗi thì sao?</h3><p>Trang public dùng nội dung fallback để không bị trắng.</p></div>
        </div>

        <div class="contact">
          <div>
            <div class="eyebrow" style="margin-bottom:6px">Liên hệ</div>
            <h2>Cần tư vấn gói dịch vụ hoặc hỗ trợ thanh toán?</h2>
            <p>Gửi thông tin qua form, Mind Dlink sẽ phản hồi theo nội dung bạn cần hỗ trợ.</p>
          </div>
          <a class="btn primary" href="#top">Gửi liên hệ</a>
        </div>
      </section>

      <footer>© 2026 Mind Dlink · Lưu link, quản lý tri thức và tìm lại nhanh hơn. · Demo Liquid Glass UI</footer>
    </div>
  </div>

  <!-- ===== GLASS: con trực tiếp của #root ===== -->

  <!-- Viên bi glass trượt bên trong nav, đè lên mục đang hover/active
       (giống ảnh mẫu iOS: highlight tròn trượt qua Home/New/Radio/Library).
       Đặt TRƯỚC nav trong DOM để nav (và chữ menu) luôn vẽ đè lên trên nó.
       Phải là con trực tiếp của #root — không nest trong .lg-nav — vì
       thư viện từ chối glass lồng nhau. JS định vị nó theo toạ độ thật
       của link đang được trỏ tới. -->
  <div class="lg-tab-indicator" id="glassTabIndicator"></div>

  <!-- Viên nang chính: logo + menu, gọn ở giữa như tab bar iOS 26 -->
  <header class="lg-nav" id="glassNav">
    <div class="logo"><span class="m">ML</span> Mind Dlink</div>
    <nav id="navLinks">
      <a href="#features" data-tab>Tính năng</a>
      <a href="#plans" data-tab>Bảng giá</a>
      <a href="#pay" data-tab>Thanh toán</a>
      <a href="#pay" data-tab>FAQ</a>
    </nav>
  </header>

  <!-- Viên nang phụ: tách riêng bên phải, như nút Search cạnh tab bar -->
  <div class="lg-actions" id="glassActions">
    <button class="theme-toggle" id="glassTheme" title="Chuyển giao diện sáng / tối" aria-label="Chuyển giao diện sáng / tối">🌙</button>
    <a class="join" href="#plans">Đăng ký</a>
  </div>

  <div class="lg-pill" id="glassPill" title="Kéo thả tôi thử xem!">
    <div class="qr">QR</div>
    <div><span>Nâng cấp bằng VietQR</span><small>Kéo viên thuỷ tinh này đi khắp trang</small></div>
  </div>

</div>

<div id="lg-status">Đang nạp hiệu ứng liquid glass…</div>

<script type="module">
  const status = document.getElementById('lg-status');
  const nav       = document.getElementById('glassNav');
  const actions   = document.getElementById('glassActions');
  const pill      = document.getElementById('glassPill');
  const indicator = document.getElementById('glassTabIndicator');
  const tabs      = [...document.querySelectorAll('#navLinks a[data-tab]')];
  const themeBtn  = document.getElementById('glassTheme'); // nút thường, nằm trong viên nang actions

  // Đọc độ "dim" hiện tại từ CSS (biến --lg-dim) — người dùng có thể
  // chỉnh biến này trong :root để làm liquid blur mờ đục hơn/trong hơn.
  const readDim = () => parseFloat(
    getComputedStyle(document.documentElement).getPropertyValue('--lg-dim')
  ) || 0.18;

  // Dựng config kính "nhám" (frosted) theo đúng tinh thần doc ybouane:
  // nhám thật = blurAmount CAO + saturation CAO để bù màu bị rửa trôi
  // bởi blur, kết hợp refraction/chromAberration THẤP để mặt kính
  // phẳng mịn như sương mờ, không lồi/vân cầu vồng như kính trong.
  // dim vẫn là núm chỉnh trung tâm: dim cao → nhám dày hơn.
  const buildConfig = (dim, base) => ({
    ...base,
    blurAmount: +(base.blurBase + dim * base.blurRange).toFixed(3),
    refraction: +(base.refBase - dim * base.refFalloff).toFixed(3),
  });

  // saturation & tintStrength theo doc: boost màu để bù "rửa trôi" do
  // blur mạnh — đây là thứ tạo cảm giác nhám thật thay vì chỉ mờ.
  const NAV_BASE = { blurBase:.5, blurRange:.35, refBase:.22, refFalloff:.1,
    chromAberration:.012, edgeHighlight:.09, cornerRadius:999, zRadius:26,
    saturation:.35, tintStrength:.06, shadowOpacity:.24, shadowSpread:16 };
  const ACTIONS_BASE = { blurBase:.5, blurRange:.35, refBase:.22, refFalloff:.1,
    chromAberration:.012, edgeHighlight:.09, cornerRadius:999, zRadius:26,
    saturation:.35, tintStrength:.06, shadowOpacity:.24, shadowSpread:16 };
  const PILL_BASE = { blurBase:.4, blurRange:.28, refBase:.5, refFalloff:.1,
    chromAberration:.03, edgeHighlight:.1, specular:.22, cornerRadius:999, zRadius:30,
    saturation:.3, tintStrength:.05,
    floating:true, button:true, shadowOpacity:.3, shadowSpread:18 };
  // Viên bi indicator: kính rõ hơn 1 chút để nổi bật là điểm nhấn đang
  // "chảy" theo con trỏ, refraction cao hơn nav để có cảm giác thấu
  // kính thật (không cần nhám dày như nav — nó nhỏ và di chuyển liên tục).
  const INDICATOR_BASE = { blurBase:.28, blurRange:.22, refBase:.62, refFalloff:.1,
    chromAberration:.05, edgeHighlight:.14, specular:.28, cornerRadius:999, zRadius:24,
    saturation:.28, tintStrength:.08, shadowOpacity:.22, shadowSpread:10 };

  const fallback = (msg) => {
    [nav, actions, pill, indicator].forEach(el => el.classList.add('css-glass'));
    status.textContent = msg;
    setTimeout(() => status.remove(), 4000);
  };

  let instance = null;

  const applyConfigs = () => {
    const dim = readDim();
    nav.dataset.config       = JSON.stringify(buildConfig(dim, NAV_BASE));
    actions.dataset.config   = JSON.stringify(buildConfig(dim, ACTIONS_BASE));
    pill.dataset.config      = JSON.stringify(buildConfig(dim, PILL_BASE));
    indicator.dataset.config = JSON.stringify(buildConfig(dim, INDICATOR_BASE));
  };

  try {
    const { LiquidGlass } = await import('https://cdn.jsdelivr.net/npm/@ybouane/liquidglass/dist/index.js');

    // Đợi webfont sẵn sàng trước khi init (yêu cầu của thư viện)
    await document.fonts.ready;

    applyConfigs();

    instance = await LiquidGlass.init({
      root: document.getElementById('root'),
      glassElements: [indicator, nav, actions, pill], // indicator trước nav: nav vẽ đè lên trên
    });

    status.textContent = 'Liquid glass (WebGL) đang chạy ✓';
    setTimeout(() => status.remove(), 3500);

  } catch (err) {
    console.warn('LiquidGlass không nạp được, dùng CSS glass fallback:', err);
    fallback('Không nạp được WebGL/CDN — đang dùng CSS glass fallback (mở file trực tiếp bằng "Mở bằng trình duyệt" hoặc dùng local server sẽ chạy WebGL đầy đủ)');
  }

  // ===== Viên bi glass trượt theo tab đang hover (giống ảnh mẫu iOS) =====
  // Định vị bằng toạ độ màn hình thật (getBoundingClientRect) vì cả
  // indicator lẫn nav đều position:fixed — không cần cộng trừ offset
  // cuộn trang.
  const TRANSITION_MS = 340; // khớp với CSS transition ở trên, +buffer nhỏ

  const moveIndicatorTo = (el) => {
    const r = el.getBoundingClientRect();
    const padX = 10, padY = 5; // viên bi rộng hơn chữ một chút, như ảnh mẫu
    indicator.style.left   = (r.left - padX) + 'px';
    indicator.style.top    = (r.top - padY) + 'px';
    indicator.style.width  = (r.width  + padX * 2) + 'px';
    indicator.style.height = (r.height + padY * 2) + 'px';
    indicator.classList.add('visible');

    // Indicator đang "chảy" bằng CSS transition trong ~340ms — thư viện
    // không tự biết vị trí đổi mỗi frame, nên phải tự bơm markChanged()
    // liên tục trong suốt thời gian đó để canvas WebGL bám theo đúng vị trí.
    const start = performance.now();
    const pump = (now) => {
      if (!instance) return;
      instance.markChanged(indicator);
      if (now - start < TRANSITION_MS) requestAnimationFrame(pump);
    };
    requestAnimationFrame(pump);
  };

  const hideIndicator = () => {
    indicator.classList.remove('visible');
    if (instance) instance.markChanged(indicator);
  };

  tabs.forEach(a => {
    a.addEventListener('mouseenter', () => moveIndicatorTo(a));
    a.addEventListener('focus', () => moveIndicatorTo(a));
  });
  nav.querySelector('nav').addEventListener('mouseleave', hideIndicator);

  // Nếu cửa sổ đổi kích thước trong lúc đang hiện indicator, toạ độ cũ
  // sẽ sai — đơn giản là ẩn đi, người dùng hover lại sẽ tự đúng vị trí.
  addEventListener('resize', hideIndicator);

  // ===== Sliding nav: ẩn khi cuộn xuống, hiện lại khi cuộn lên =====
  let lastY = window.scrollY;
  let ticking = false;
  const SHOW_AT_TOP = 40; // luôn hiện khi còn gần đầu trang

  const onScroll = () => {
    const y = window.scrollY;
    const goingDown = y > lastY;

    if (y <= SHOW_AT_TOP) {
      nav.classList.remove('nav-hidden');
      actions.classList.remove('nav-hidden');
    } else if (goingDown) {
      nav.classList.add('nav-hidden');
      actions.classList.add('nav-hidden');
    } else {
      nav.classList.remove('nav-hidden');
      actions.classList.remove('nav-hidden');
    }
    lastY = y;

    // Kính vẫn cần biết nội dung phía sau đã đổi (nền fixed + trôi qua card khác)
    if (instance) instance.markChanged();
    ticking = false;
  };

  addEventListener('scroll', () => {
    if (ticking) return;
    ticking = true;
    requestAnimationFrame(onScroll);
  }, { passive: true });

  // ===== Toggle sáng / tối =====
  themeBtn.addEventListener('click', () => {
    const isLight = document.body.classList.toggle('theme-light');
    themeBtn.textContent = isLight ? '☀️' : '🌙';
    // Nền vừa đổi màu (CSS transition) — báo cho thư viện biết
    // phải rasterize + render lại các glass để khúc xạ đúng theme mới.
    if (instance) {
      setTimeout(() => instance.markChanged(), 60);
      setTimeout(() => instance.markChanged(), 400); // sau khi transition nền xong
    }
  });
</script>
</body>
</html>
