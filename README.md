<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AMB - صيانة عمرو عمارة</title>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Cairo', sans-serif; }
        :root {
            --primary: #0A2342;
            --secondary: #2B6CB0;
            --bg: #F7FAFC;
            --white: #FFFFFF;
            --text: #1A202C;
            --gray: #718096;
            --success: #48BB78;
            --warning: #ED8936;
            --danger: #F56565;
        }
        body { background: var(--bg); color: var(--text); max-width: 450px; margin: 0 auto; }
       .screen { display: none; min-height: 100vh; padding-bottom: 80px; }
       .screen.active { display: block; animation: fadeIn 0.3s; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        /* Splash Screen */
        #splash { background: var(--primary); color: var(--white); display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; }
        #splash.active { display: flex; }
       .logo { font-size: 60px; font-weight: 700; margin-bottom: 10px; }
       .logo span { color: var(--secondary); }
       .splash-text { font-size: 18px; margin: 10px 0; }
       .loading-dots { display: flex; gap: 8px; margin-top: 40px; }
       .loading-dots span { width: 10px; height: 10px; background: var(--white); border-radius: 50%; animation: bounce 1.4s infinite; }
       .loading-dots span:nth-child(2) { animation-delay: 0.2s; }
       .loading-dots span:nth-child(3) { animation-delay: 0.4s; }
        @keyframes bounce { 0%, 80%, 100% { transform: scale(0); } 40% { transform: scale(1); } }

        /* Header */
       .header { background: var(--white); padding: 15px 20px; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 4px rgba(0,0,0,0.05); }
       .header-title { font-size: 18px; font-weight: 600; }
       .header-icon { font-size: 22px; color: var(--primary); cursor: pointer; }

        /* Home */
       .welcome-card { background: var(--primary); color: var(--white); margin: 20px; padding: 20px; border-radius: 16px; }
       .welcome-card h2 { font-size: 22px; margin-bottom: 5px; }
       .services-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; padding: 0 20px; margin-top: 20px; }
       .service-card { background: var(--white); padding: 20px; border-radius: 12px; text-align: center; box-shadow: 0 2px 8px rgba(0,0,0,0.08); cursor: pointer; }
       .service-card i { font-size: 32px; color: var(--secondary); margin-bottom: 10px; }
       .service-card p { font-weight: 600; font-size: 14px; }
       .discount-card { background: var(--primary); color: var(--white); margin: 20px; padding: 20px; border-radius: 16px; display: flex; justify-content: space-between; align-items: center; }
       .discount-code { background: var(--white); color: var(--primary); padding: 8px 15px; border-radius: 8px; font-weight: 700; }

        /* Form */
       .form-container { padding: 20px; }
       .stepper { display: flex; justify-content: space-between; margin-bottom: 30px; }
       .step { text-align: center; flex: 1; position: relative; }
       .step::after { content: ''; position: absolute; top: 15px; right: -50%; width: 100%; height: 2px; background: #E2E8F0; z-index: -1; }
       .step:last-child::after { display: none; }
       .step-circle { width: 30px; height: 30px; border-radius: 50%; background: #E2E8F0; margin: 0 auto 8px; display: flex; align-items: center; justify-content: center; font-weight: 600; }
       .step.active.step-circle { background: var(--secondary); color: var(--white); }
       .step.done.step-circle { background: var(--success); color: var(--white); }
       .form-group { margin-bottom: 20px; }
       .form-group label { display: block; margin-bottom: 8px; font-weight: 600; font-size: 14px; }
       .form-group input,.form-group select,.form-group textarea { width: 100%; padding: 12px 15px; border: 1px solid #E2E8F0; border-radius: 10px; font-size: 15px; }
       .device-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; }
       .device-option { border: 2px solid #E2E8F0; border-radius: 10px; padding: 15px 10px; text-align: center; cursor: pointer; }
       .device-option.selected { border-color: var(--secondary); background: #EBF8FF; }
       .device-option i { font-size: 28px; color: var(--secondary); margin-bottom: 5px; }
       .btn { width: 100%; padding: 15px; background: var(--secondary); color: var(--white); border: none; border-radius: 12px; font-size: 16px; font-weight: 600; cursor: pointer; }

        /* Orders */
       .tabs { display: flex; background: var(--white); margin: 20px; border-radius: 12px; padding: 5px; }
       .tab { flex: 1; padding: 10px; text-align: center; border-radius: 8px; cursor: pointer; font-weight: 600; font-size: 14px; }
       .tab.active { background: var(--secondary); color: var(--white); }
       .order-card { background: var(--white); margin: 0 20px 15px; padding: 15px; border-radius: 12px; box-shadow: 0 2px 8px rgba(0,0,0,0.05); }
       .order-header { display: flex; justify-content: space-between; margin-bottom: 10px; }
       .status { padding: 4px 12px; border-radius: 20px; font-size: 12px; font-weight: 600; }
       .status.ongoing { background: #FEF5E7; color: var(--warning); }
       .status.done { background: #E6FFFA; color: var(--success); }
       .status.cancelled { background: #FFF5F5; color: var(--danger); }

        /* Bottom Nav */
       .bottom-nav { position: fixed; bottom: 0; width: 100%; max-width: 450px; background: var(--white); display: flex; justify-content: space-around; padding: 10px 0; box-shadow: 0 -2px 10px rgba(0,0,0,0.08); }
       .nav-item { text-align: center; color: var(--gray); cursor: pointer; }
       .nav-item.active { color: var(--secondary); }
       .nav-item i { font-size: 22px; display: block; margin-bottom: 4px; }
       .nav-item span { font-size: 11px; font-weight: 600; }

        /* Sidebar */
       .sidebar { position: fixed; top: 0; right: -100%; width: 80%; max-width: 350px; height: 100vh; background: var(--primary); color: var(--white); z-index: 1000; transition: 0.3s; overflow-y: auto; }
       .sidebar.active { right: 0; }
       .sidebar-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100vh; background: rgba(0,0,0,0.5); display: none; z-index: 999; }
       .sidebar-overlay.active { display: block; }
       .sidebar-profile { padding: 30px 20px; text-align: center; border-bottom: 1px solid rgba(255,255,255,0.1); }
       .sidebar-profile img { width: 70px; height: 70px; border-radius: 50%; margin-bottom: 10px; }
       .sidebar-menu { padding: 20px 0; }
       .menu-item { padding: 15px 25px; display: flex; align-items: center; gap: 15px; cursor: pointer; }
       .menu-item:hover { background: rgba(255,255,255,0.1); }

       .features { padding: 20px; }
       .features-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; }
       .feature-item { background: var(--white); padding: 15px; border-radius: 12px; text-align: center; }
       .feature-item i { font-size: 28px; color: var(--secondary); margin-bottom: 8px; }
    </style>
</head>
<body>
    <!-- Splash Screen -->
    <div id="splash" class="screen active">
        <div class="logo">AMB</div>
        <div class="splash-text">صيانة عمرو عمارة</div>
        <div style="font-size: 14px; opacity: 0.8;">صيانة الثلاجات والغسالات</div>
        <div class="loading-dots"><span></span><span></span></div>
        <div style="margin-top: 20px; font-size: 14px;">جاري التحميل...</div>
    </div>

    <!-- Home Screen -->
    <div id="home" class="screen">
        <div class="header">
            <i class="fas fa-bars header-icon" onclick="toggleSidebar()"></i>
            <div class="header-title">القاهرة، مصر <i class="fas fa-map-marker-alt"></i></div>
            <i class="fas fa-bell header-icon"></i>
        </div>

        <div class="welcome-card">
            <h2>👋 أهلاً بك</h2>
            <p>نحن هنا لخدمتك في أي وقت</p>
        </div>

        <h3 style="padding: 0 20px; margin-top: 20px;">الخدمات</h3>
        <div class="services-grid">
            <div class="service-card" onclick="showScreen('new-order')">
                <i class="fas fa-tools"></i>
                <p>طلب صيانة</p>
                <small>اطلب فني الآن</small>
            </div>
            <div class="service-card" onclick="showScreen('track')">
                <i class="fas fa-map-marked-alt"></i>
                <p>متابعة الطلب</p>
                <small>تتبع حالة طلبك</small>
            </div>
            <div class="service-card">
                <i class="fab fa-whatsapp"></i>
                <p>واتساب</p>
                <small>تواصل معنا</small>
            </div>
            <div class="service-card">
                <i class="fas fa-phone"></i>
                <p>اتصل بنا</p>
                <small>خدمة العملاء</small>
            </div>
        </div>

        <div class="discount-card">
            <div>
                <h3>خصم 20%</h3>
                <p style="font-size: 13px; opacity: 0.9;">على أول طلب صيانة</p>
            </div>
            <div class="discount-code">AMB20</div>
        </div>

        <div class="features">
            <h3 style="margin-bottom: 15px;">مميزات التطبيق</h3>
            <div class="features-grid">
                <div class="feature-item"><i class="fas fa-map-marker-alt"></i><p>تتبع مباشر لموقع الفني</p></div>
                <div class="feature-item"><i class="fas fa-clock"></i><p>تقدير وقت الوصول بدقة</p></div>
                <div class="feature-item"><i class="fas fa-bell"></i><p>إشعارات فورية لحالة الطلب</p></div>
                <div class="feature-item"><i class="fas fa-headset"></i><p>دعم فني على مدار الساعة</p></div>
            </div>
        </div>
    </div>

    <!-- New Order Screen -->
    <div id="new-order" class="screen">
        <div class="header">
            <i class="fas fa-arrow-right header-icon" onclick="showScreen('home')"></i>
            <div class="header-title">طلب صيانة</div>
            <div></div>
        </div>

        <div class="form-container">
            <div class="stepper">
                <div class="step active"><div class="step-circle">1</div><small>بيانات الطلب</small></div>
                <div class="step"><div class="step-circle">2</div><small>تحديد العطل</small></div>
                <div class="step"><div class="step-circle">3</div><small>تأكيد الطلب</small></div>
            </div>

            <h3>بيانات العميل</h3>
            <div class="form-group">
                <label>الاسم الكامل</label>
                <input type="text" placeholder="ادخل اسمك بالكامل">
            </div>
            <div class="form-group">
                <label>رقم الهاتف</label>
                <input type="tel" placeholder="ادخل رقم هاتفك">
            </div>
            <div class="form-group">
                <label>العنوان</label>
                <input type="text" placeholder="ادخل عنوانك بالتفصيل">
            </div>

            <h3 style="margin-top: 25px;">نوع الجهاز</h3>
            <div class="device-grid">
                <div class="device-option selected" onclick="selectDevice(this)">
                    <i class="fas fa-th-large"></i>
                    <p>ثلاجة</p>
                </div>
                <div class="device-option" onclick="selectDevice(this)">
                    <i class="fas fa-soap"></i>
                    <p>غسالة</p>
                </div>
                <div class="device-option" onclick="selectDevice(this)">
                    <i class="fas fa-snowflake"></i>
                    <p>ديب فريزر</p>
                </div>
            </div>

            <div class="form-group" style="margin-top: 20px;">
                <label>نوع العطل</label>
                <select><option>اختر نوع العطل</option><option>لا تبرد</option><option>صوت عالي</option><option>تسريب مياه</option></select>
            </div>

            <div class="form-group">
                <label>وصف العطل (اختياري)</label>
                <textarea rows="3" placeholder="اكتب وصف مختصر عن العطل"></textarea>
            </div>

            <button class="btn" onclick="showScreen('track')">التالي</button>
        </div>
    </div>

    <!-- Track Order Screen -->
    <div id="track" class="screen">
        <div class="header">
            <i class="fas fa-arrow-right header-icon" onclick="showScreen('home')"></i>
            <div class="header-title">متابعة الطلب</div>
            <div></div>
        </div>

        <div style="padding: 20px;">
            <div class="order-card">
                <div style="display: flex; justify-content: space-between; margin-bottom: 15px;">
                    <div>
                        <p style="font-size: 13px; color: var(--gray);">رقم الطلب</p>
                        <h3>#1258</h3>
                    </div>
                    <div style="text-align: left;">
                        <p style="font-size: 13px; color: var(--gray);">حالة الطلب</p>
                        <h3 style="color: var(--warning);">جاري التوجه إليك</h3>
                    </div>
                <div style="display: flex; align-items: center; gap: 15px;">
                    <img src="https://i.pravatar.cc/60" style="width: 50px; height: 50px; border-radius: 50%;">
                    <div>
                        <p style="font-weight: 600;">أحمد محمد</p>
                        <p style="font-size: 13px; color: var(--gray);">⭐ 4.9</p>
                    </div>
                </div>
            </div>

            <div style="background: #E2E8F0; height: 200px; border-radius: 12px; margin: 20px 0; display: flex; align-items: center; justify-content: center; color: var(--gray);">
                <i class="fas fa-map-marked-alt" style="font-size: 40px;"></i>
                <p style="margin-right: 10px;">متبقي 15 دقيقة</p>
            </div>

            <button class="btn"><i class="fas fa-phone"></i> تواصل مع الفني</button>
        </div>
    </div>

    <!-- Orders Screen -->
    <div id="orders" class="screen">
        <div class="header">
            <i class="fas fa-arrow-right header-icon" onclick="showScreen('home')"></i>
            <div class="header-title">طلباتي</div>
            <div></div>
        </div>

        <div class="tabs">
            <div class="tab active">الكل</div>
            <div class="tab">جارية</div>
            <div class="tab">مكتملة</div>
            <div class="tab">ملغية</div>
        </div>

        <div class="order-card">
            <div class="order-header">
                <span>#1258</span>
                <span class="status ongoing">جاري التوجه</span>
            </div>
            <p style="font-weight: 600;">ثلاجة - لا تبرد من الأسفل</p>
            <p style="font-size: 13px; color: var(--gray); margin-top: 5px;"><i class="far fa-clock"></i> 21 يونيو 2024 - 02:30 م</p>
        </div>

        <div class="order-card">
            <div class="order-header">
                <span>#1256</span>
                <span class="status done">مكتمل</span>
            </div>
            <p style="font-weight: 600;">غسالة - لا تشطف الملابس</p>
            <p style="font-size: 13px; color: var(--gray); margin-top: 5px;"><i class="far fa-clock"></i> 18 يونيو 2024 - 11:00 ص</p>
        </div>
    </div>

    <!-- Sidebar -->
    <div class="sidebar-overlay" onclick="toggleSidebar()"></div>
    <div class="sidebar">
        <div class="sidebar-profile">
            <img src="https://i.pravatar.cc/100" alt="profile">
            <h3>أحمد محمد</h3>
            <p style="opacity: 0.8; font-size: 14px;">010 1234 5678</p>
        </div>
        <div class="sidebar-menu">
            <div class="menu-item" onclick="showScreen('home'); toggleSidebar();"><i class="fas fa-home"></i><span>الرئيسية</span></div>
            <div class="menu-item" onclick="showScreen('new-order'); toggleSidebar();"><i class="fas fa-plus-circle"></i><span>طلب صيانة</span></div>
            <div class="menu-item" onclick="showScreen('orders'); toggleSidebar();"><i class="fas fa-list"></i><span>طلباتي</span></div>
            <div class="menu-item"><i class="fas fa-tag"></i><span>العروض والخصومات</span></div>
            <div class="menu-item"><i class="fas fa-comments"></i><span>الدردشة</span></div>
            <div class="menu-item"><i class="fas fa-star"></i><span>تقييم الخدمة</span></div>
            <div class="menu-item"><i class="fas fa-question-circle"></i><span>الأسئلة الشائعة</span></div>
            <div class="menu-item"><i class="fas fa-cog"></i><span>الإعدادات</span></div>
            <div class="menu-item" style="color: #FC8181;"><i class="fas fa-sign-out-alt"></i><span>تسجيل خروج</span></div>
        </div>
    </div>

    <!-- Bottom Nav -->
    <div class="bottom-nav">
        <div class="nav-item" onclick="showScreen('home')">
            <i class="fas fa-home"></i><span>الرئيسية</span>
        </div>
        <div class="nav-item" onclick="showScreen('orders')">
            <i class="fas fa-clipboard-list"></i><span>الطلبات</span>
        </div>
        <div class="nav-item">
            <i class="fas fa-comments"></i><span>الدردشة</span>
        </div>
        <div class="nav-item">
            <i class="fas fa-user"></i><span>الحساب</span>
        </div>
    </div>

    <script>
        // Show splash then home
        setTimeout(() => { showScreen('home'); }, 2000);

        function showScreen(id) {
            document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
            document.getElementById(id).classList.add('active');

            // Update bottom nav
            document.querySelectorAll('.nav-item').forEach(n => n.classList.remove('active'));
            if(id === 'home') document.querySelectorAll('.nav-item')[0].classList.add('active');
            if(id === 'orders') document.querySelectorAll('.nav-item')[1].classList.add('active');
        }

        function toggleSidebar() {
            document.querySelector('.sidebar').classList.toggle('active');
            document.querySelector('.sidebar-overlay').classList.toggle('active');
        }

        function selectDevice(el) {
            document.querySelectorAll('.device-option').forEach(d => d.classList.remove('selected'));
            el.classList.add('selected');
        }
    </script>
</body>
</html>
