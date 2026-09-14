<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مركز العناية بالأسنان - NFC Smart Card</title>
    
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        medical: { 800: '#0f4c81', 900: '#0b3254', 950: '#071e34' },
                        cyanGlow: { 300: '#67e8f9', 400: '#22d3ee', 500: '#06b6d4' }
                    },
                    fontFamily: { tajawal: ['Tajawal', 'sans-serif'] }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #071e34;
            background-image: radial-gradient(circle at 50% 0%, #0f4c81 0%, #071e34 80%);
            min-height: 100vh;
        }
        .dental-pattern {
            background-color: #071e34;
            background-image: radial-gradient(#22d3ee 0.5px, transparent 0.5px), radial-gradient(#22d3ee 0.5px, #071e34 0.5px);
            background-size: 24px 24px;
            opacity: 0.04;
        }
        .glass-card {
            background: rgba(15, 76, 129, 0.3);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            border: 1px solid rgba(34, 211, 238, 0.25);
        }
        .cyan-border-glow { box-shadow: 0 0 15px rgba(34, 211, 238, 0.2); }
        .cyan-gradient-text {
            background: linear-gradient(135deg, #ffffff 0%, #67e8f9 50%, #06b6d4 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .cyan-gradient-bg { background: linear-gradient(135deg, #22d3ee 0%, #0284c7 100%); }
        .toast-slide-up { animation: slideUp 0.3s ease-out forwards; }
        @keyframes slideUp { from { transform: translateY(100%); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
    </style>
</head>
<body class="text-slate-100 relative pb-12 selection:bg-cyanGlow-400 selection:text-slate-900">

    <div class="fixed inset-0 dental-pattern pointer-events-none z-0"></div>

    <!-- Public View Container -->
    <div class="relative z-10 max-w-md mx-auto px-4 pt-8 pb-20">

        <!-- Top Status Indicator -->
        <div class="flex justify-between items-center mb-6">
            <div class="flex items-center gap-2">
                <span class="w-2.5 h-2.5 rounded-full bg-cyanGlow-400 animate-pulse"></span>
                <span class="text-xs font-medium text-cyanGlow-300/90 tracking-wider">بطاقة العيادة الذكية NFC</span>
            </div>
            <span class="text-[10px] bg-medical-900/80 text-cyanGlow-300 border border-cyanGlow-400/30 px-2.5 py-1 rounded-full font-bold">احجز موعدك</span>
        </div>

        <!-- Main Clinic Header -->
        <div class="text-center mb-6">
            <div class="relative inline-block mb-3">
                <div id="logoContainer" class="w-24 h-24 rounded-full glass-card border-2 border-cyanGlow-400/50 flex items-center justify-center mx-auto cyan-border-glow relative z-10 overflow-hidden p-1">
                    <i id="defaultIcon" class="fa-solid fa-tooth text-4xl text-cyanGlow-400"></i>
                    <img id="customLogoImg" src="" alt="Clinic Logo" class="w-full h-full object-cover rounded-full hidden">
                </div>
                <div class="absolute -inset-1 rounded-full bg-cyanGlow-400/10 blur-sm"></div>
            </div>
            
            <h1 id="displayTitle" class="text-2xl font-bold cyan-gradient-text mb-1">عيادة الأسنان المتخصصة</h1>
            <p id="displaySubtitle" class="text-xs text-cyan-200/80">ابتسامتك المشرقة تبدأ من هنا - أحدث تكنولوجيا طب الأسنان</p>
            
            <div class="mt-4 p-3 rounded-xl glass-card border border-cyanGlow-400/20 max-w-xs mx-auto">
                <p class="text-xs text-cyanGlow-300 leading-relaxed font-medium">
                    <i class="fa-solid fa-clock text-cyanGlow-400 ml-1"></i> مواعيد العمل: يومياً من 2 ظهراً حتى 10 مساءً
                </p>
            </div>
        </div>

        <!-- Book Appointment Call To Action -->
        <div class="mb-6">
            <a id="btnBooking" href="#" target="_blank" class="cyan-gradient-bg text-slate-950 rounded-2xl p-4 font-bold transition-all flex items-center justify-between group shadow-lg shadow-cyanGlow-500/20 active:scale-95">
                <div class="flex items-center gap-3">
                    <div class="w-11 h-11 rounded-xl bg-slate-950/20 text-slate-950 flex items-center justify-center text-xl group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-calendar-check"></i>
                    </div>
                    <div class="text-right">
                        <span class="text-sm font-black block">احجز موعد الكشف الآن</span>
                        <span class="text-[11px] text-slate-800 font-medium">حجز مباشر عبر الواتساب مع موظف الاستقبال</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-left text-slate-950 text-sm group-hover:-translate-x-1 transition-transform"></i>
            </a>
        </div>

        <!-- Services Grid -->
        <div class="space-y-3 mb-6">
            <h2 class="text-xs font-bold text-cyanGlow-400 uppercase tracking-wider px-1 flex items-center gap-1.5">
                <i class="fa-solid fa-kit-medical text-cyanGlow-300"></i> خدمات العيادة
            </h2>
            
            <div class="grid grid-cols-2 gap-2.5 text-xs">
                <div class="glass-card rounded-xl p-3 flex items-center gap-2.5">
                    <i class="fa-solid fa-wand-magic-sparkles text-cyanGlow-400 text-base"></i>
                    <span>تبييض بالليزر</span>
                </div>
                <div class="glass-card rounded-xl p-3 flex items-center gap-2.5">
                    <i class="fa-solid fa-gem text-cyanGlow-400 text-base"></i>
                    <span>تجميل وابتسامة هوليوود</span>
                </div>
                <div class="glass-card rounded-xl p-3 flex items-center gap-2.5">
                    <i class="fa-solid fa-tooth text-cyanGlow-400 text-base"></i>
                    <span>زراعة وتقويم الأسنان</span>
                </div>
                <div class="glass-card rounded-xl p-3 flex items-center gap-2.5">
                    <i class="fa-solid fa-shield-halved text-cyanGlow-400 text-base"></i>
                    <span>علاج الجذور والعصب</span>
                </div>
            </div>
        </div>

        <!-- Branches Locations Section -->
        <div class="space-y-3 mb-6">
            <h2 class="text-xs font-bold text-cyanGlow-400 uppercase tracking-wider px-1 flex items-center gap-1.5">
                <i class="fa-solid fa-location-dot text-red-400"></i> موقع العيادة والفروع
            </h2>
            
            <div class="grid grid-cols-2 gap-2.5">
                <!-- Branch 1 -->
                <a id="btnLocKafr" href="https://maps.google.com" target="_blank" class="glass-card rounded-xl p-3 flex flex-col items-center justify-center gap-2 hover:bg-medical-800/50 hover:border-cyanGlow-400/50 transition-all group text-center">
                    <div class="w-10 h-10 rounded-full bg-red-500/20 text-red-400 flex items-center justify-center text-lg group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-hospital-user"></i>
                    </div>
                    <div>
                        <span class="text-xs font-bold text-slate-100 block">الفرع الرئيسي</span>
                        <span class="text-[10px] text-cyan-300/70">فتح الموقع بالخريطة <i class="fa-solid fa-arrow-up-right-from-square text-[9px] ml-0.5"></i></span>
                    </div>
                </a>

                <!-- Branch 2 -->
                <a id="btnLocFifth" href="https://maps.google.com" target="_blank" class="glass-card rounded-xl p-3 flex flex-col items-center justify-center gap-2 hover:bg-medical-800/50 hover:border-cyanGlow-400/50 transition-all group text-center">
                    <div class="w-10 h-10 rounded-full bg-cyanGlow-500/20 text-cyanGlow-400 flex items-center justify-center text-lg group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-building-user"></i>
                    </div>
                    <div>
                        <span class="text-xs font-bold text-slate-100 block">الفرع الثاني</span>
                        <span class="text-[10px] text-cyan-300/70">فتح الموقع بالخريطة <i class="fa-solid fa-arrow-up-right-from-square text-[9px] ml-0.5"></i></span>
                    </div>
                </a>
            </div>
        </div>

        <!-- Google Reviews Button Section -->
        <div class="mb-6">
            <a id="btnReview" href="https://g.page" target="_blank" class="glass-card rounded-2xl p-4 border border-cyanGlow-400/30 hover:bg-medical-800/40 transition-all flex items-center justify-between group">
                <div class="flex items-center gap-3">
                    <div class="w-11 h-11 rounded-xl bg-amber-500/20 text-amber-400 flex items-center justify-center text-xl group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-star"></i>
                    </div>
                    <div class="text-right">
                        <div class="flex items-center gap-1 text-amber-400 text-xs mb-0.5">
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                            <i class="fa-solid fa-star"></i>
                        </div>
                        <span class="text-xs font-bold text-slate-100 block">اراء وتقييمات المرضى</span>
                        <span class="text-[10px] text-cyan-300/70">شاركنا تجربتك وتقييمك للعيادة على جوجل</span>
                    </div>
                </div>
                <i class="fa-solid fa-chevron-left text-cyanGlow-400 text-sm group-hover:-translate-x-1 transition-transform"></i>
            </a>
        </div>

        <!-- Social Links -->
        <div class="space-y-3 mb-6">
            <h2 class="text-xs font-bold text-cyanGlow-400 uppercase tracking-wider px-1">تواصل مع العيادة</h2>
            
            <div class="grid grid-cols-3 gap-2.5">
                <!-- WhatsApp -->
                <a id="btnWhatsapp" href="#" target="_blank" class="glass-card rounded-xl p-3 flex flex-col items-center justify-center gap-2 hover:bg-medical-800/40 hover:border-emerald-500/50 transition-all group">
                    <div class="w-10 h-10 rounded-full bg-emerald-600/20 text-emerald-400 flex items-center justify-center text-xl group-hover:scale-110 transition-transform">
                        <i class="fa-brands fa-whatsapp"></i>
                    </div>
                    <span class="text-xs font-medium text-slate-200 flex items-center gap-1">
                        واتساب العيادة
                    </span>
                </a>

                <!-- Phone Direct Call -->
                <a id="btnPhone" href="#" class="glass-card rounded-xl p-3 flex flex-col items-center justify-center gap-2 hover:bg-medical-800/40 hover:border-cyanGlow-400/50 transition-all group">
                    <div class="w-10 h-10 rounded-full bg-cyanGlow-500/20 text-cyanGlow-400 flex items-center justify-center text-lg group-hover:scale-110 transition-transform">
                        <i class="fa-solid fa-phone"></i>
                    </div>
                    <span class="text-xs font-medium text-slate-200 flex items-center gap-1">
                        اتصال مباشر
                    </span>
                </a>

                <!-- Facebook -->
                <a id="btnFacebook" href="#" target="_blank" class="glass-card rounded-xl p-3 flex flex-col items-center justify-center gap-2 hover:bg-medical-800/40 hover:border-blue-500/50 transition-all group">
                    <div class="w-10 h-10 rounded-full bg-blue-500/20 text-blue-400 flex items-center justify-center text-lg group-hover:scale-110 transition-transform">
                        <i class="fa-brands fa-facebook-f"></i>
                    </div>
                    <span class="text-xs font-medium text-slate-200 flex items-center gap-1">
                        فيسبوك
                    </span>
                </a>
            </div>
        </div>

        <!-- Quick Share Action -->
        <div>
            <button type="button" onclick="shareLink(event)" class="w-full glass-card hover:bg-medical-800/50 text-cyanGlow-300 font-bold rounded-xl py-3 px-4 flex items-center justify-center gap-2 text-xs border border-cyanGlow-400/40 active:scale-95 transition-all">
                <i class="fa-solid fa-share-nodes text-sm"></i>
                <span>مشاركة كارت العيادة الذكي</span>
            </button>
        </div>

        <!-- Footer & Admin Trigger -->
        <div class="text-center mt-10 relative">
            <p class="text-[11px] text-cyan-300/40">جميع الحقوق محفوظة © عيادة الأسنان المتخصصة</p>
            
            <!-- Secret Admin Lock Icon -->
            <button type="button" onclick="openAdminLogin(event)" class="mt-4 text-medical-800 hover:text-cyanGlow-400 text-xs transition-colors p-2" title="دخول لوحة تحكم العيادة">
                <i class="fa-solid fa-lock"></i>
            </button>
        </div>

    </div>

    <!-- Admin Login Modal -->
    <div id="loginModal" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden">
        <div class="glass-card bg-medical-950 border border-cyanGlow-400/40 rounded-2xl w-full max-w-xs p-5 space-y-4 text-right">
            <div class="flex justify-between items-center border-b border-medical-800 pb-3">
                <h3 class="text-sm font-bold text-cyanGlow-400 flex items-center gap-2">
                    <i class="fa-solid fa-user-shield"></i> لوحة إدارة العيادة
                </h3>
                <button type="button" onclick="closeAdminLogin(event)" class="text-slate-400 hover:text-white"><i class="fa-solid fa-xmark"></i></button>
            </div>
            
            <div>
                <label class="block text-cyan-200 text-xs mb-1">كلمة السر</label>
                <input type="password" id="adminPasswordInput" placeholder="أدخل كلمة السر..." class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2.5 text-slate-100 text-xs focus:outline-none focus:border-cyanGlow-400">
            </div>

            <button type="button" onclick="verifyAdminPass(event)" class="w-full cyan-gradient-bg text-slate-950 font-bold py-2.5 rounded-lg text-xs">دخول اللوحة</button>
        </div>
    </div>

    <!-- Admin Control Panel Modal -->
    <div id="adminPanelModal" class="fixed inset-0 bg-black/90 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden">
        <div class="glass-card bg-medical-950 border border-cyanGlow-400/50 rounded-2xl w-full max-w-md p-5 space-y-4 text-right max-h-[90vh] overflow-y-auto">
            <div class="flex justify-between items-center border-b border-medical-800 pb-3">
                <h3 class="text-base font-bold text-cyanGlow-400 flex items-center gap-2">
                    <i class="fa-solid fa-sliders"></i> التحكم في بيانات العيادة
                </h3>
                <button type="button" onclick="closeAdminPanel(event)" class="text-slate-400 hover:text-white"><i class="fa-solid fa-xmark text-lg"></i></button>
            </div>

            <div class="space-y-3 text-xs">
                <div>
                    <label class="block text-cyan-200 mb-1 flex items-center gap-1.5"><i class="fa-solid fa-image text-cyanGlow-400"></i> شعار العيادة (اللوجو)</label>
                    <input type="file" id="inputLogoFile" accept="image/*" class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2 text-slate-100 text-xs file:mr-2 file:py-1 file:px-2 file:rounded-md file:border-0 file:text-xs file:font-semibold file:bg-cyanGlow-400 file:text-slate-950">
                    <button type="button" onclick="resetLogo(event)" class="text-[10px] text-red-400 hover:underline mt-1 block">استعادة الشعار الافتراضي</button>
                </div>

                <div>
                    <label class="block text-cyan-200 mb-1">اسم العيادة / الطبيب</label>
                    <input type="text" id="inputTitle" placeholder="اتركه فارغاً للإبقاء على الحالي" class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2.5 text-slate-100 focus:outline-none focus:border-cyanGlow-400">
                </div>

                <div class="border-t border-medical-800 pt-2">
                    <label class="block text-cyan-200 mb-1 flex items-center gap-1.5"><i class="fa-solid fa-map-location-dot text-red-400"></i> رابط خرائط الفرع الرئيسي</label>
                    <input type="text" id="inputKafrLoc" placeholder="رابط Google Maps للعيادة" class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2.5 text-slate-100 focus:outline-none focus:border-cyanGlow-400 text-left dir-ltr">
                </div>

                <div>
                    <label class="block text-cyan-200 mb-1 flex items-center gap-1.5"><i class="fa-solid fa-map-location-dot text-cyanGlow-400"></i> رابط خرائط الفرع الثاني</label>
                    <input type="text" id="inputFifthLoc" placeholder="رابط Google Maps للفرع الثاني" class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2.5 text-slate-100 focus:outline-none focus:border-cyanGlow-400 text-left dir-ltr">
                </div>

                <div>
                    <label class="block text-cyan-200 mb-1 flex items-center gap-1.5"><i class="fa-solid fa-star text-amber-400"></i> رابط تقييم جوجل (Google Review)</label>
                    <input type="text" id="inputReviewUrl" placeholder="رابط التقييم" class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2.5 text-slate-100 focus:outline-none focus:border-cyanGlow-400 text-left dir-ltr">
                </div>

                <div class="border-t border-medical-800 pt-2">
                    <label class="block text-cyan-200 mb-1 flex items-center gap-1.5"><i class="fa-brands fa-whatsapp text-emerald-400"></i> رقم الواتساب للحجز (2010XXXXXXXX)</label>
                    <input type="text" id="inputWhatsapp" placeholder="مثال: 201012345678" class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2.5 text-slate-100 focus:outline-none focus:border-cyanGlow-400 text-left dir-ltr">
                </div>

                <div>
                    <label class="block text-cyan-200 mb-1 flex items-center gap-1.5"><i class="fa-brands fa-facebook text-blue-400"></i> رابط صفحة الفيسبوك</label>
                    <input type="text" id="inputFacebook" placeholder="رابط الصفحة" class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2.5 text-slate-100 focus:outline-none focus:border-cyanGlow-400 text-left dir-ltr">
                </div>

                <div class="border-t border-medical-800 pt-3 mt-2">
                    <label class="block text-cyan-200 mb-1 flex items-center gap-1.5"><i class="fa-solid fa-key text-cyanGlow-400"></i> تغيير كلمة سر اللوحة</label>
                    <input type="password" id="inputNewPassword" placeholder="كلمة سر جديدة (اختياري)..." class="w-full bg-medical-900/60 border border-medical-800 rounded-lg p-2.5 text-slate-100 focus:outline-none focus:border-cyanGlow-400">
                </div>
            </div>

            <div class="flex gap-2 pt-3">
                <button type="button" onclick="saveAdminSettings(event)" class="flex-1 cyan-gradient-bg text-slate-950 font-bold py-2.5 rounded-lg text-xs shadow-md">حفظ وتحديث التغييرات</button>
                <button type="button" onclick="closeAdminPanel(event)" class="px-4 bg-medical-900 text-slate-300 rounded-lg text-xs hover:bg-medical-800">إلغاء</button>
            </div>
        </div>
    </div>

    <!-- Toast Notification -->
    <div id="toast" class="fixed bottom-4 left-1/2 -translate-x-1/2 bg-cyanGlow-400 text-slate-950 px-4 py-2 rounded-full font-bold text-xs shadow-lg hidden z-50 flex items-center gap-2">
        <i class="fa-solid fa-check-circle"></i>
        <span id="toastMsg">تم التحديث بنجاح</span>
    </div>

    <script>
        // Default Dental Clinic Config
        const defaultConfig = {
            title: "عيادة الأسنان المتخصصة",
            subtitle: "ابتسامتك المشرقة تبدأ من هنا - أحدث تكنولوجيا طب الأسنان",
            kafrLoc: "https://maps.google.com",
            fifthLoc: "https://maps.google.com",
            reviewUrl: "https://g.page",
            whatsapp: "201000000000",
            facebook: "https://facebook.com",
            logoBase64: "",
            adminPass: "dental2026"
        };

        let currentConfig = Object.assign({}, defaultConfig);

        function loadConfig() {
            const saved = localStorage.getItem('dental_nfc_global_config');
            if (saved) {
                try {
                    const parsed = JSON.parse(saved);
                    currentConfig = Object.assign({}, defaultConfig, parsed);
                } catch(e) {}
            }
            applyConfigToUI();
        }

        function applyConfigToUI() {
            document.getElementById('displayTitle').innerText = currentConfig.title;
            
            // Logo Image
            const defaultIcon = document.getElementById('defaultIcon');
            const customLogoImg = document.getElementById('customLogoImg');

            if (currentConfig.logoBase64) {
                customLogoImg.src = currentConfig.logoBase64;
                customLogoImg.classList.remove('hidden');
                defaultIcon.classList.add('hidden');
            } else {
                customLogoImg.classList.add('hidden');
                defaultIcon.classList.remove('hidden');
            }

            // Branches & Reviews Links
            document.getElementById('btnLocKafr').href = currentConfig.kafrLoc || '#';
            document.getElementById('btnLocFifth').href = currentConfig.fifthLoc || '#';
            document.getElementById('btnReview').href = currentConfig.reviewUrl || '#';

            // Contact Links
            const cleanWa = currentConfig.whatsapp ? currentConfig.whatsapp.replace(/[^0-9]/g, '') : '';
            document.getElementById('btnWhatsapp').href = cleanWa ? `https://wa.me/${cleanWa}` : '#';
            document.getElementById('btnBooking').href = cleanWa ? `https://wa.me/${cleanWa}?text=${encodeURIComponent('مرحباً، أرغب في حجز موعد للكشف في العيادة')}` : '#';
            document.getElementById('btnPhone').href = cleanWa ? `tel:+${cleanWa}` : '#';
            document.getElementById('btnFacebook').href = currentConfig.facebook || '#';
        }

        // Admin Actions
        function openAdminLogin(e) {
            if (e) e.preventDefault();
            document.getElementById('adminPasswordInput').value = '';
            document.getElementById('loginModal').classList.remove('hidden');
        }

        function closeAdminLogin(e) {
            if (e) e.preventDefault();
            document.getElementById('loginModal').classList.add('hidden');
        }

        function verifyAdminPass(e) {
            if (e) e.preventDefault();
            const inputPass = document.getElementById('adminPasswordInput').value;
            if (inputPass === currentConfig.adminPass) {
                closeAdminLogin();
                populateAdminFields();
                document.getElementById('adminPanelModal').classList.remove('hidden');
            } else {
                showToast("كلمة السر غير صحيحة!");
            }
        }

        function closeAdminPanel(e) {
            if (e) e.preventDefault();
            document.getElementById('adminPanelModal').classList.add('hidden');
        }

        function populateAdminFields() {
            document.getElementById('inputTitle').value = currentConfig.title;
            document.getElementById('inputKafrLoc').value = currentConfig.kafrLoc;
            document.getElementById('inputFifthLoc').value = currentConfig.fifthLoc;
            document.getElementById('inputReviewUrl').value = currentConfig.reviewUrl;
            document.getElementById('inputWhatsapp').value = currentConfig.whatsapp;
            document.getElementById('inputFacebook').value = currentConfig.facebook;
            document.getElementById('inputNewPassword').value = '';
        }

        function resetLogo(e) {
            if (e) e.preventDefault();
            currentConfig.logoBase64 = "";
            document.getElementById('inputLogoFile').value = "";
            showToast("تم إزالة اللوجو المخصص");
        }

        function saveAdminSettings(e) {
            if (e) e.preventDefault();

            const fileInput = document.getElementById('inputLogoFile');
            const newPass = document.getElementById('inputNewPassword').value.trim();

            const performSave = (logoData) => {
                const titleVal = document.getElementById('inputTitle').value.trim();
                const kafrVal = document.getElementById('inputKafrLoc').value.trim();
                const fifthVal = document.getElementById('inputFifthLoc').value.trim();
                const revVal = document.getElementById('inputReviewUrl').value.trim();
                const waVal = document.getElementById('inputWhatsapp').value.trim();
                const fbVal = document.getElementById('inputFacebook').value.trim();

                if (titleVal !== "") currentConfig.title = titleVal;
                if (kafrVal !== "") currentConfig.kafrLoc = kafrVal;
                if (fifthVal !== "") currentConfig.fifthLoc = fifthVal;
                if (revVal !== "") currentConfig.reviewUrl = revVal;
                if (waVal !== "") currentConfig.whatsapp = waVal;
                if (fbVal !== "") currentConfig.facebook = fbVal;
                
                if (logoData !== null) {
                    currentConfig.logoBase64 = logoData;
                }

                if (newPass !== "") {
                    currentConfig.adminPass = newPass;
                }

                localStorage.setItem('dental_nfc_global_config', JSON.stringify(currentConfig));
                applyConfigToUI();
                closeAdminPanel();
                showToast("تم حفظ وتحديث التغييرات بنجاح!");
            };

            if (fileInput.files && fileInput.files[0]) {
                const reader = new FileReader();
                reader.onload = function(evt) {
                    performSave(evt.target.result);
                };
                reader.readAsDataURL(fileInput.files[0]);
            } else {
                performSave(null);
            }
        }

        function shareLink(e) {
            if (e) e.preventDefault();
            if (navigator.share) {
                navigator.share({
                    title: currentConfig.title,
                    text: 'تفضل بزيارة كارت عيادة الأسنان للحجز والمعلومات',
                    url: window.location.href,
                }).catch(() => {});
            } else {
                navigator.clipboard.writeText(window.location.href);
                showToast("تم نسخ رابط العيادة للحافظة");
            }
        }

        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMsg').innerText = msg;
            toast.classList.remove('hidden');
            toast.classList.add('toast-slide-up');
            setTimeout(() => { toast.classList.add('hidden'); }, 2500);
        }

        window.onload = loadConfig;
    </script>
</body>
</html>
