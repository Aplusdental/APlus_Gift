<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMC - ميدالية NFC الذكية</title>

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Tajawal:wght@300;400;500;700;900&display=swap" rel="stylesheet">

    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        emerald: { 850: '#064e3b', 900: '#022c22', 950: '#011e17' },
                        gold: { 100: '#fef3c7', 300: '#fde047', 400: '#facc15', 500: '#eab308', 600: '#ca8a04', 700: '#a16207' }
                    },
                    fontFamily: { tajawal: ['Tajawal', 'sans-serif'], amiri: ['Amiri', 'serif'] }
                }
            }
        }
    </script>

    <style>
        html, body {
            direction: rtl;
            text-align: right;
        }
        body {
            font-family: 'Tajawal', sans-serif;
            background-color: #011e17;
            background-image: radial-gradient(circle at 50% 0%, #064e3b 0%, #011e17 75%);
            min-height: 100vh;
        }
        .font-quran { font-family: 'Amiri', serif; }
        .islamic-pattern {
            background-color: #011e17;
            background-image: radial-gradient(#ca8a04 0.5px, transparent 0.5px), radial-gradient(#ca8a04 0.5px, #011e17 0.5px);
            background-size: 20px 20px;
            opacity: 0.05;
        }
        .glass-card {
            background: rgba(6, 78, 59, 0.35);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(202, 138, 4, 0.2);
        }
        .gold-border-glow { box-shadow: 0 0 15px rgba(202, 138, 4, 0.15); }
        .gold-gradient-text {
            background: linear-gradient(135deg, #fef3c7 0%, #facc15 50%, #ca8a04 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .gold-gradient-bg { background: linear-gradient(135deg, #d97706 0%, #ca8a04 50%, #a16207 100%); }
        .toast-slide-up { animation: slideUp 0.3s ease-out forwards; }
        @keyframes slideUp { from { transform: translateY(100%); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
    </style>
</head>
<body class="text-right text-white">
    <!-- حط محتوى تصميم الكروت والتفاصيل هنا -->
</body>
</html>
