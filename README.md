<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>شركة بن لسود للزراعة والتجارة | Binlaswad</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- مكتبة لحفظ البطاقة كصورة -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Inter:wght@300;400;500;600;700&family=Noto+Kufi+Arabic:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'brand-dark': '#1c1c22',
                        'brand-surface': '#26262e',
                        'brand-surface-light': '#32323c',
                        'brand-red': '#cc1a1a',
                        'brand-red-light': '#e83333',
                        'brand-green': '#1a7a3a',
                        'brand-green-light': '#22a84e',
                        'brand-gold': '#c9a84c',
                        'brand-gold-light': '#e0c56d',
                        'whatsapp-green': '#25D366',
                    }
                }
            }
        }
    </script>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: 'Inter', 'Noto Kufi Arabic', sans-serif;
            background: #1c1c22;
            color: #ffffff;
            overflow-x: hidden;
        }

        .font-serif-display { font-family: 'Instrument Serif', serif; }
        .font-arabic { font-family: 'Noto Kufi Arabic', sans-serif; }

        .logo-img { border-radius: 50%; object-fit: contain; }

        .logo-glow { position: relative; }
        .logo-glow::after {
            content: '';
            position: absolute;
            inset: -4px;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(204,26,26,0.15), transparent 70%);
            opacity: 0;
            transition: opacity 0.4s ease;
            pointer-events: none;
        }
        .logo-glow:hover::after { opacity: 1; }

        .bg-grid {
            background-image:
                linear-gradient(rgba(255,255,255,0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(255,255,255,0.03) 1px, transparent 1px);
            background-size: 60px 60px;
        }

        .noise-overlay::before {
            content: '';
            position: fixed;
            inset: 0;
            background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
            opacity: 0.04;
            z-index: 0;
            pointer-events: none;
        }

        .business-card {
            width: 560px;
            max-width: 92vw;
            aspect-ratio: 1.75 / 1;
            background: linear-gradient(145deg, #faf8f4, #f0ece4);
            border-radius: 16px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 4px 6px rgba(0,0,0,0.25), 0 20px 60px rgba(0,0,0,0.35), 0 0 80px rgba(201, 168, 76, 0.06);
            transition: transform 0.6s cubic-bezier(0.16, 1, 0.3, 1), box-shadow 0.6s ease;
        }

        @media (min-width: 768px) {
            .business-card:hover {
                transform: perspective(1000px) rotateY(-3deg) rotateX(2deg) translateY(-8px) scale(1.02);
                box-shadow: 0 8px 12px rgba(0,0,0,0.3), 0 30px 80px rgba(0,0,0,0.45), 0 0 120px rgba(201, 168, 76, 0.12);
            }
        }

        .card-stripe { position: absolute; top: 0; right: 0; width: 6px; height: 100%; background: linear-gradient(to bottom, #cc1a1a, #1a7a3a); }
        @media (min-width: 768px) { .card-stripe { width: 8px; } }
        .card-stripe-gold { position: absolute; top: 0; right: 6px; width: 2px; height: 100%; background: #c9a84c; }
        @media (min-width: 768px) { .card-stripe-gold { right: 8px; width: 3px; } }
        .card-pattern { position: absolute; bottom: 0; left: 0; right: 0; height: 40%; background: repeating-linear-gradient(-45deg, transparent, transparent 8px, rgba(0,0,0,0.015) 8px, rgba(0,0,0,0.015) 9px); }

        .brand-badge { display: inline-flex; align-items: center; gap: 3px; padding: 2px 6px; border-radius: 3px; font-size: 6px; font-weight: 700; letter-spacing: 0.06em; text-transform: uppercase; line-height: 1.4; }
        @media (min-width: 768px) { .brand-badge { gap: 4px; padding: 3px 8px; font-size: 8px; letter-spacing: 0.08em; } }
        .badge-shineray { background: #cc1a1a; color: white; }
        .badge-daishin { background: #1a1a1a; color: white; }
        .badge-robin { background: #c62828; color: white; }
        .badge-tanaka { background: #e65100; color: white; }
        .badge-fuji { background: #1565c0; color: white; }

        .qr-code { width: 56px; height: 56px; background: white; border-radius: 5px; padding: 3px; display: grid; grid-template-columns: repeat(11, 1fr); grid-template-rows: repeat(11, 1fr); gap: 1px; }
        @media (min-width: 768px) { .qr-code { width: 72px; height: 72px; padding: 4px; border-radius: 6px; } }
        .qr-cell { border-radius: 1px; }
        .qr-dark { background: #3a3a3a; }
        .qr-light { background: transparent; }

        .glow-red { position: absolute; width: 200px; height: 200px; background: radial-gradient(circle, rgba(204,26,26,0.1), transparent 70%); border-radius: 50%; filter: blur(60px); pointer-events: none; }
        .glow-green { position: absolute; width: 180px; height: 180px; background: radial-gradient(circle, rgba(26,122,58,0.08), transparent 70%); border-radius: 50%; filter: blur(60px); pointer-events: none; }
        .glow-gold { position: absolute; width: 160px; height: 160px; background: radial-gradient(circle, rgba(201,168,76,0.08), transparent 70%); border-radius: 50%; filter: blur(50px); pointer-events: none; }
        @media (min-width: 768px) { .glow-red { width: 300px; height: 300px; } .glow-green { width: 250px; height: 250px; } .glow-gold { width: 200px; height: 200px; } }

        @keyframes float { 0%, 100% { transform: translateY(0px); } 50% { transform: translateY(-12px); } }
        @keyframes fadeInUp { from { opacity: 0; transform: translateY(30px); } to { opacity: 1; transform: translateY(0); } }
        @keyframes logoReveal { 0% { opacity: 0; transform: scale(0.6) rotate(-10deg); } 60% { transform: scale(1.05) rotate(2deg); } 100% { opacity: 1; transform: scale(1) rotate(0deg); } }
        @keyframes pulse-ring { 0% { transform: scale(0.9); opacity: 0.4; } 100% { transform: scale(1.5); opacity: 0; } }
        @keyframes shimmer { 0% { background-position: -200% center; } 100% { background-position: 200% center; } }

        .animate-float { animation: float 6s ease-in-out infinite; }
        .animate-fade-up { animation: fadeInUp 1s cubic-bezier(0.16, 1, 0.3, 1) forwards; }
        .animate-logo-reveal { animation: logoReveal 1.2s cubic-bezier(0.16, 1, 0.3, 1) forwards; }

        .delay-200 { animation-delay: 200ms; }
        .delay-400 { animation-delay: 400ms; }
        .delay-600 { animation-delay: 600ms; }
        .delay-800 { animation-delay: 800ms; }
        .delay-1000 { animation-delay: 1000ms; }

        .reveal { opacity: 0; transform: translateY(2rem); filter: blur(4px); transition: all 700ms ease-out; }
        .reveal.active { opacity: 1; transform: translateY(0); filter: blur(0); }

        .contact-item { transition: all 0.3s ease; }
        .contact-item:hover { transform: translateY(-4px); }
        .contact-item:hover .contact-icon { transform: scale(1.1); }

        .nav-glass { background: rgba(28, 28, 34, 0.8); backdrop-filter: blur(16px); -webkit-backdrop-filter: blur(16px); border: 1px solid rgba(255,255,255,0.07); }

        .nav-link { position: relative; color: rgba(255,255,255,0.5); transition: color 0.3s ease; }
        .nav-link:hover { color: #ffffff; }
        .nav-link::after { content: ''; position: absolute; bottom: -4px; right: 0; width: 0; height: 1px; background: #c9a84c; transition: width 0.3s ease; }
        .nav-link:hover::after { width: 100%; }

        .mobile-menu { position: fixed; inset: 0; z-index: 100; background: rgba(28, 28, 34, 0.98); backdrop-filter: blur(20px); -webkit-backdrop-filter: blur(20px); display: flex; flex-direction: column; align-items: center; justify-content: center; gap: 2rem; opacity: 0; pointer-events: none; transition: opacity 0.4s ease; }
        .mobile-menu.open { opacity: 1; pointer-events: all; }
        .mobile-menu a { color: rgba(255,255,255,0.7); font-size: 1.25rem; font-weight: 500; font-family: 'Noto Kufi Arabic', sans-serif; transition: color 0.3s ease; text-decoration: none; }
        .mobile-menu a:hover { color: #c9a84c; }

        .hero-logo-ring { position: absolute; inset: -10px; border-radius: 50%; border: 1px solid rgba(204,26,26,0.15); animation: pulse-ring 3s ease-out infinite; }
        .hero-logo-ring:nth-child(2) { animation-delay: 1s; }
        .hero-logo-ring:nth-child(3) { animation-delay: 2s; }
        @media (min-width: 768px) { .hero-logo-ring { inset: -12px; } }

        ::-webkit-scrollbar { width: 6px; }
        ::-webkit-scrollbar-track { background: #1c1c22; }
        ::-webkit-scrollbar-thumb { background: rgba(201,168,76,0.3); border-radius: 3px; }
        ::-webkit-scrollbar-thumb:hover { background: rgba(201,168,76,0.5); }

        .toast { position: fixed; bottom: 24px; left: 50%; transform: translateX(-50%) translateY(100px); background: rgba(26, 122, 58, 0.95); color: white; padding: 10px 24px; border-radius: 12px; font-size: 13px; font-weight: 500; z-index: 9999; backdrop-filter: blur(10px); border: 1px solid rgba(255,255,255,0.1); transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1), opacity 0.4s ease; opacity: 0; pointer-events: none; white-space: nowrap; max-width: 90vw; text-align: center; }
        .toast.show { transform: translateX(-50%) translateY(0); opacity: 1; }

        .name-line { width: 30px; height: 1.5px; background: linear-gradient(to right, #cc1a1a, #c9a84c); border-radius: 2px; }
        @media (min-width: 768px) { .name-line { width: 40px; height: 2px; } }

        .hero-company-name { position: relative; display: inline-block; }
        .hero-company-name::after { content: ''; position: absolute; bottom: -8px; left: 50%; transform: translateX(-50%); width: 60px; height: 2px; background: linear-gradient(to right, transparent, #c9a84c, transparent); border-radius: 2px; }

        .brand-card { position: relative; overflow: hidden; }
        .brand-card img.brand-logo { transition: transform 0.6s cubic-bezier(0.16, 1, 0.3, 1), filter 0.6s ease; }
        .brand-card:hover img.brand-logo { transform: scale(1.08); }

        /* Catalog shimmer */
        .catalog-shimmer {
            background: linear-gradient(90deg, transparent 0%, rgba(201,168,76,0.08) 50%, transparent 100%);
            background-size: 200% 100%;
            animation: shimmer 3s ease-in-out infinite;
        }
    </style>
</head>
<body class="noise-overlay bg-grid">

    <!-- Toast -->
    <div id="toast" class="toast">✓ تم نسخ المعلومات</div>

    <!-- Mobile Menu -->
    <div id="mobileMenu" class="mobile-menu">
        <button onclick="toggleMobileMenu()" class="absolute top-6 left-6 text-white/60 hover:text-white transition-colors">
            <i data-lucide="x" class="w-6 h-6"></i>
        </button>
        <a href="#home" onclick="toggleMobileMenu()">الرئيسية</a>
        <a href="#card" onclick="toggleMobileMenu()">البطاقة</a>
        <a href="#catalog" onclick="toggleMobileMenu()">الكاتالوج</a>
        <a href="#contact" onclick="toggleMobileMenu()">تواصل</a>
        <a href="#brands" onclick="toggleMobileMenu()">العلامات</a>
    </div>

    <!-- Navigation -->
    <nav class="fixed top-0 left-0 right-0 z-50 py-4 md:py-5 px-4 md:px-6">
        <div class="max-w-7xl mx-auto flex items-center justify-between">
            <div class="nav-glass rounded-full px-4 py-2 md:px-6 md:py-2.5 flex items-center gap-4 md:gap-5">
                <a href="#" class="flex items-center gap-2">
                    <img src="https://z-cdn-media.chatglm.cn/files/0c93625e-a572-40b8-84a3-30aa83997b59.png?auth_key=1878940382-5c01bfe1be3b4a4d80d8dc7d36005971-0-b0f72ef1e77a04ebdfeda671afcf8ca3" alt="شعار بن لسود" class="w-7 h-7 md:w-8 md:h-8 logo-img">
                    <div class="flex flex-col leading-tight">
                        <span class="text-white font-semibold text-[10px] md:text-sm tracking-wide">BINLASWAD</span>
                        <span class="text-white/40 text-[7px] md:text-[9px] font-arabic hidden sm:block">شركة بن لسود للزراعة والتجارة</span>
                    </div>
                </a>
                <div class="hidden md:flex items-center gap-5 text-sm">
                    <a href="#home" class="nav-link">الرئيسية</a>
                    <a href="#card" class="nav-link">البطاقة</a>
                    <a href="#catalog" class="nav-link">الكاتالوج</a>
                    <a href="#contact" class="nav-link">تواصل</a>
                    <a href="#brands" class="nav-link">العلامات</a>
                </div>
            </div>
            <div class="flex items-center gap-2">
                <div class="nav-glass rounded-full px-3 py-2 md:px-4 md:py-2.5 flex items-center gap-2 md:gap-3">
                    <a href="https://wa.me/966591668398" target="_blank" class="text-[10px] md:text-xs font-medium text-white/60 hover:text-[#25D366] transition-colors flex items-center gap-1 md:gap-1.5 no-underline">
                        <i data-lucide="message-circle" class="w-3.5 h-3.5"></i>
                        <span class="hidden sm:inline">واتساب</span>
                    </a>
                </div>
                <button onclick="toggleMobileMenu()" class="md:hidden nav-glass rounded-full w-10 h-10 flex items-center justify-center text-white/60 hover:text-white transition-colors cursor-pointer">
                    <i data-lucide="menu" class="w-5 h-5"></i>
                </button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="relative min-h-screen flex items-center justify-center overflow-hidden">
        <div class="glow-red" style="top: 10%; left: 5%;"></div>
        <div class="glow-green" style="bottom: 15%; right: 10%;"></div>
        <div class="glow-gold" style="top: 40%; left: 50%; transform: translateX(-50%);"></div>

        <div class="relative z-10 text-center px-5 pt-20 md:pt-24">
            <div class="animate-logo-reveal opacity-0 mb-6 md:mb-8 flex justify-center">
                <div class="relative inline-block logo-glow">
                    <div class="hero-logo-ring"></div>
                    <div class="hero-logo-ring"></div>
                    <div class="hero-logo-ring"></div>
                    <img src="https://z-cdn-media.chatglm.cn/files/0c93625e-a572-40b8-84a3-30aa83997b59.png?auth_key=1878940382-5c01bfe1be3b4a4d80d8dc7d36005971-0-b0f72ef1e77a04ebdfeda671afcf8ca3" alt="شعار بن لسود" class="w-20 h-20 md:w-28 md:h-28 logo-img relative z-10">
                </div>
            </div>

            <div class="animate-fade-up opacity-0 mb-4 md:mb-6">
                <span class="inline-flex items-center gap-2 px-3 py-1.5 md:px-4 md:py-2 rounded-full border border-white/10 bg-white/[0.04] text-[8px] md:text-[10px] font-medium uppercase tracking-widest text-white/50">
                    <span class="w-1.5 h-1.5 rounded-full bg-brand-red animate-pulse"></span>
                    Business Card
                </span>
            </div>

            <h1 class="animate-fade-up opacity-0 delay-200 text-4xl md:text-7xl lg:text-8xl font-bold mb-4 md:mb-5 leading-[0.95] tracking-tight" dir="ltr">
                <span class="text-white">Binlaswad</span> <span class="text-brand-gold-light/90 font-serif-display italic font-normal">Company</span>
            </h1>

            <p class="animate-fade-up opacity-0 delay-300 font-serif-display text-2xl md:text-4xl lg:text-5xl text-white/90 italic mb-3 md:mb-4 leading-tight" dir="ltr">
                ABDULKARIM BAQAHIZAL
            </p>

            <p class="animate-fade-up opacity-0 delay-400 font-arabic text-lg md:text-2xl lg:text-3xl font-bold text-brand-gold-light/85 mb-6 md:mb-8 leading-relaxed">
                <span class="hero-company-name">شركة بن لسود للزراعة والتجارة</span>
            </p>

            <p class="animate-fade-up opacity-0 delay-600 text-white/45 text-xs md:text-base max-w-sm md:max-w-lg mx-auto mb-8 md:mb-12 font-arabic leading-relaxed">
                شريككم الموثوق في المعدات والمحركات
            </p>

            <div class="animate-fade-up opacity-0 delay-800 flex flex-wrap items-center justify-center gap-3 md:gap-4">
                <a href="#card" class="group inline-flex items-center gap-2 px-5 py-3 md:px-7 md:py-3.5 bg-brand-gold text-[#1c1c22] rounded-full text-[10px] md:text-xs font-semibold uppercase tracking-wide hover:bg-brand-gold-light transition-all duration-300 hover:shadow-[0_0_30px_rgba(201,168,76,0.3)]">
                    عرض البطاقة
                    <i data-lucide="arrow-down" class="w-3 h-3 md:w-3.5 md:h-3.5 group-hover:translate-y-0.5 transition-transform"></i>
                </a>
                <a href="#catalog" class="inline-flex items-center gap-2 px-5 py-3 md:px-7 md:py-3.5 border border-white/10 rounded-full text-[10px] md:text-xs font-medium uppercase tracking-wide text-white/60 hover:text-white hover:border-white/20 transition-all duration-300">
                    الكاتالوج
                    <i data-lucide="book-open" class="w-3 h-3 md:w-3.5 md:h-3.5"></i>
                </a>
            </div>
        </div>

        <div class="absolute bottom-6 md:bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2 animate-fade-up opacity-0 delay-1000">
            <span class="text-[8px] md:text-[9px] uppercase tracking-widest text-white/20">Scroll</span>
            <div class="w-px h-6 md:h-8 bg-gradient-to-b from-white/20 to-transparent"></div>
        </div>
    </section>

    <!-- Business Card Section -->
    <section id="card" class="relative py-16 md:py-32 px-4 md:px-6">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-10 md:mb-16 reveal">
                <span class="text-[9px] md:text-[10px] font-medium uppercase tracking-widest text-brand-gold/60 mb-3 md:mb-4 block">Business Card</span>
                <h2 class="font-serif-display text-3xl md:text-5xl lg:text-6xl font-normal italic text-white mb-3 md:mb-4" dir="ltr">Business Card</h2>
                <p class="text-white/45 text-xs md:text-sm max-w-xs md:max-w-md mx-auto">مرر الماوس فوق البطاقة للتفاعل — اضغط لنسخ المعلومات</p>
            </div>

            <div class="flex justify-center reveal" style="transition-delay: 200ms;">
                <div class="animate-float" style="animation-delay: -2s;">
                    <div class="business-card cursor-pointer" onclick="copyCardInfo()">
                        <div class="card-stripe"></div>
                        <div class="card-stripe-gold"></div>
                        <div class="card-pattern"></div>
                        <div class="relative z-10 h-full flex flex-col justify-between p-4 pr-5 md:p-7 md:pr-10" dir="ltr">
                            <div class="flex items-start justify-between">
                                <div>
                                    <div class="flex items-center gap-2 md:gap-2.5">
                                        <img src="https://z-cdn-media.chatglm.cn/files/0c93625e-a572-40b8-84a3-30aa83997b59.png?auth_key=1878940382-5c01bfe1be3b4a4d80d8dc7d36005971-0-b0f72ef1e77a04ebdfeda671afcf8ca3" alt="Logo" class="w-7 h-7 md:w-9 md:h-9 logo-img shadow-md">
                                        <div>
                                            <h3 class="text-[#2a2a2a] font-bold text-[9px] md:text-[13px] tracking-wide leading-tight">BINLASWAD Company</h3>
                                            <p class="text-[#888] text-[4.5px] md:text-[6.5px] font-medium uppercase tracking-[0.08em] md:tracking-[0.12em]">Agricultural & Commercial Co.</p>
                                        </div>
                                    </div>
                                    <!-- الكتابة العربية وترجمتها الإنجليزية بخط أصغر -->
                                    <p class="text-[#777] text-[5px] md:text-[7px] font-medium mt-0.5 md:mt-1" dir="rtl">شركة بن لسود للزراعة والتجارة</p>
                                    <p class="text-[#999] text-[4px] md:text-[5.5px] font-medium mt-0.5" dir="ltr">Binlaswad Agricultural & Commercial Co.</p>
                                </div>
                                <div class="qr-code shadow-sm border border-gray-200 flex-shrink-0" id="qrCode"></div>
                            </div>
                            
                            <!-- قسم الاسم والرقم والايميل -->
                            <div class="flex flex-col items-center my-1 md:my-0">
                                <div class="name-line mb-1 md:mb-1.5"></div>
                                <h2 class="text-[#1a1a1a] font-bold text-[11px] md:text-[16px] tracking-wide leading-tight" dir="rtl">عبدالكريم باقحيزل</h2>
                                <p class="text-[#555] text-[7px] md:text-[10px] font-semibold tracking-[0.2em] md:tracking-[0.25em] uppercase mt-0.5">ABDULKARIM BAQAHIZAL</p>
                                <div class="name-line mt-1 md:mt-1.5"></div>
                                
                                <!-- رقم الهاتف -->
                                <div class="flex items-center gap-1 mt-1.5 md:mt-2">
                                    <span class="text-brand-red text-[7px] md:text-[10px]">✆</span>
                                    <span class="text-[#2a2a2a] font-bold text-[8px] md:text-[12px] tracking-[0.1em] md:tracking-[0.15em]" dir="ltr">+966 59 166 8398</span>
                                </div>

                                <!-- البريد الإلكتروني -->
                                <div class="flex items-center gap-1 mt-0.5 md:mt-1">
                                    <span class="text-brand-green text-[7px] md:text-[10px]">✉</span>
                                    <span class="text-[#2a2a2a] font-semibold text-[7px] md:text-[11px] tracking-[0.05em] md:tracking-[0.1em]" dir="ltr">abdulkariimhssan@gmail.com</span>
                                </div>
                            </div>

                            <div class="flex flex-wrap gap-1 md:gap-1.5 mb-1 md:mb-2 justify-center items-center">
                                <span class="brand-badge badge-shineray">SHINERAY</span>
                                <span class="brand-badge badge-daishin"><span class="w-1 h-1 md:w-1.5 md:h-1.5 rounded-sm bg-red-500"></span>DaiSHIN</span>
                                <span class="brand-badge badge-robin">Robin SUBARU</span>
                                <span class="brand-badge badge-tanaka">TANAKA</span>
                                <span class="brand-badge badge-fuji">FUJI DELUXE</span>
                            </div>
                            
                            <div class="flex items-end justify-between">
                                <div class="space-y-0.5 md:space-y-1">
                                    <div class="space-y-0.5 text-[5.5px] md:text-[7.5px] text-[#555]">
                                        <div class="flex items-center gap-1 md:gap-1.5"><span class="text-brand-gold">⌂</span><span>Saudi Arabia</span></div>
                                    </div>
                                </div>
                                <div class="flex flex-col items-end gap-0.5 md:gap-1">
                                    <div class="flex gap-0.5">
                                        <div class="w-4 md:w-6 h-0.5 bg-brand-red rounded-full"></div>
                                        <div class="w-3 md:w-4 h-0.5 bg-brand-green rounded-full"></div>
                                        <div class="w-1.5 md:w-2 h-0.5 bg-brand-gold rounded-full"></div>
                                    </div>
                                    <p class="text-[4px] md:text-[6px] text-[#aaa] uppercase tracking-[0.15em] md:tracking-[0.2em]">Est. Saudi Arabia</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <p class="text-center text-white/25 text-[9px] md:text-[10px] mt-6 md:mt-8 reveal" style="transition-delay: 400ms;"><i data-lucide="mouse-pointer-click" class="w-3 h-3 inline-block mb-0.5"></i> اضغط على البطاقة لنسخ معلومات التواصل</p>
        </div>
    </section>

    <!-- ★ Catalog Section ★ -->
    <section id="catalog" class="relative py-16 md:py-32 px-4 md:px-6">
        <!-- Background glow -->
        <div class="absolute inset-0 overflow-hidden pointer-events-none">
            <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[400px] h-[400px] md:w-[600px] md:h-[600px] bg-brand-gold/[0.04] rounded-full blur-[100px]"></div>
        </div>

        <div class="max-w-4xl mx-auto relative z-10">
            <div class="reveal">
                <div class="relative rounded-3xl border border-white/[0.08] bg-[#26262e] overflow-hidden">
                    <!-- Shimmer top border -->
                    <div class="h-px catalog-shimmer"></div>

                    <div class="p-8 md:p-14 text-center">
                        <!-- Icon -->
                        <div class="w-16 h-16 md:w-20 md:h-20 mx-auto mb-6 md:mb-8 rounded-2xl bg-brand-gold/10 border border-brand-gold/20 flex items-center justify-center">
                            <i data-lucide="book-open" class="w-7 h-7 md:w-9 md:h-9 text-brand-gold-light"></i>
                        </div>

                        <!-- Label -->
                        <span class="text-[9px] md:text-[10px] font-medium uppercase tracking-widest text-brand-gold/60 mb-4 md:mb-5 block">Product Catalogs</span>

                        <!-- Title -->
                        <h2 class="font-arabic text-3xl md:text-5xl font-bold mb-3 md:mb-4">الكاتالوج</h2>

                        <!-- Description -->
                        <p class="text-white/45 text-sm md:text-base max-w-lg mx-auto mb-8 md:mb-10 font-arabic leading-relaxed">
                            تصفح كاتالوجات منتجاتنا الكاملة — محركات، معدات زراعية، وقطع غيار من أرقى العلامات العالمية
                        </p>

                        <!-- CTA Buttons -->
                        <div class="flex flex-col sm:flex-row items-center justify-center gap-3 md:gap-4">
                            <a href="https://drive.google.com/file/d/1d000IApFfoIUzGODhVQqqrLCNYfOiZbc/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"
                               class="group inline-flex items-center gap-3 px-8 py-4 md:px-10 md:py-5 bg-brand-gold text-[#1c1c22] rounded-full text-xs md:text-sm font-semibold uppercase tracking-wide hover:bg-brand-gold-light transition-all duration-300 hover:shadow-[0_0_40px_rgba(201,168,76,0.3)] no-underline">
                                <i data-lucide="eye" class="w-4 h-4 md:w-5 md:h-5 group-hover:scale-110 transition-transform"></i>
                                الكاتالوج الأول
                                <i data-lucide="external-link" class="w-3.5 h-3.5 md:w-4 md:h-4 group-hover:translate-x-1 transition-transform"></i>
                            </a>

                            <a href="https://drive.google.com/file/d/1bTutJmWzQL73g6B2sFGtPBnjpHZMrUpj/view?usp=drivesdk" target="_blank" rel="noopener noreferrer"
                               class="group inline-flex items-center gap-3 px-8 py-4 md:px-10 md:py-5 border border-brand-gold/30 text-brand-gold-light rounded-full text-xs md:text-sm font-semibold uppercase tracking-wide hover:bg-brand-gold/10 transition-all duration-300 no-underline">
                                <i data-lucide="eye" class="w-4 h-4 md:w-5 md:h-5 group-hover:scale-110 transition-transform"></i>
                                الكاتالوج الثاني
                                <i data-lucide="external-link" class="w-3.5 h-3.5 md:w-4 md:h-4 group-hover:translate-x-1 transition-transform"></i>
                            </a>
                        </div>

                        <!-- Helper text -->
                        <p class="text-white/20 text-[10px] md:text-xs mt-4 md:mt-5 flex items-center justify-center gap-1.5">
                            <i data-lucide="file-text" class="w-3 h-3"></i>
                            ملفات PDF — تفتح في نافذة جديدة
                        </p>
                    </div>

                    <!-- Decorative catalog pages -->
                    <div class="absolute top-6 right-6 md:top-10 md:right-10 opacity-[0.03] pointer-events-none" dir="ltr">
                        <svg width="80" height="100" viewBox="0 0 80 100" fill="none">
                            <rect x="10" y="0" width="50" height="70" rx="4" stroke="white" stroke-width="2"/>
                            <rect x="20" y="10" width="50" height="70" rx="4" stroke="white" stroke-width="2"/>
                            <line x1="30" y1="25" x2="60" y2="25" stroke="white" stroke-width="2"/>
                            <line x1="30" y1="35" x2="55" y2="35" stroke="white" stroke-width="2"/>
                            <line x1="30" y1="45" x2="50" y2="45" stroke="white" stroke-width="2"/>
                        </svg>
                    </div>
                    <div class="absolute bottom-6 left-6 md:bottom-10 md:left-10 opacity-[0.03] pointer-events-none" dir="ltr">
                        <svg width="60" height="80" viewBox="0 0 60 80" fill="none">
                            <rect x="5" y="5" width="40" height="55" rx="3" stroke="white" stroke-width="2"/>
                            <rect x="15" y="15" width="40" height="55" rx="3" stroke="white" stroke-width="2"/>
                        </svg>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="relative py-16 md:py-32 px-4 md:px-6">
        <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[300px] h-[300px] md:w-[500px] md:h-[500px] bg-brand-gold/[0.03] rounded-full blur-[120px] pointer-events-none"></div>

        <div class="max-w-5xl mx-auto relative z-10">
            <div class="text-center mb-10 md:mb-16 reveal">
                <span class="text-[9px] md:text-[10px] font-medium uppercase tracking-widest text-brand-gold/60 mb-3 md:mb-4 block">Get In Touch</span>
                <h2 class="font-arabic text-2xl md:text-5xl font-bold mb-3 md:mb-4">تواصل معنا</h2>
                <p class="text-white/45 text-xs md:text-sm max-w-xs md:max-w-md mx-auto">نسعد بتواصلكم معنا للاستفسار عن منتجاتنا وخدماتنا</p>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-3 md:gap-4 reveal" style="transition-delay: 200ms;">
                
                <!-- الهاتف -->
                <div class="contact-item group p-5 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 text-center cursor-pointer" onclick="copyToClipboard('+966 59 166 8398')">
                    <div class="contact-icon w-11 h-11 md:w-12 md:h-12 mx-auto mb-3 md:mb-4 rounded-xl bg-brand-red/10 border border-brand-red/20 flex items-center justify-center transition-transform duration-300">
                        <i data-lucide="phone" class="w-5 h-5 text-brand-red-light"></i>
                    </div>
                    <h3 class="text-white font-semibold text-sm mb-1 font-arabic">الهاتف</h3>
                    <p class="text-white/45 text-xs" dir="ltr">+966 59 166 8398</p>
                    <p class="text-white/20 text-[8px] md:text-[9px] mt-2 group-hover:text-brand-gold/60 transition-colors">اضغط للنسخ</p>
                </div>

                <!-- الواتساب -->
                <a href="https://wa.me/966591668398" target="_blank" rel="noopener noreferrer" class="contact-item group p-5 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 text-center cursor-pointer no-underline block">
                    <div class="contact-icon w-11 h-11 md:w-12 md:h-12 mx-auto mb-3 md:mb-4 rounded-xl bg-[#25D366]/10 border border-[#25D366]/20 flex items-center justify-center transition-transform duration-300">
                        <i data-lucide="message-circle" class="w-5 h-5 text-[#25D366]"></i>
                    </div>
                    <h3 class="text-white font-semibold text-sm mb-1 font-arabic">واتساب</h3>
                    <p class="text-white/45 text-xs" dir="ltr">+966 59 166 8398</p>
                    <p class="text-white/20 text-[8px] md:text-[9px] mt-2 group-hover:text-[#25D366]/60 transition-colors flex items-center justify-center gap-1"><i data-lucide="external-link" class="w-3 h-3"></i> تواصل الآن</p>
                </a>

                <!-- البريد الإلكتروني -->
                <div class="contact-item group p-5 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 text-center cursor-pointer" onclick="copyToClipboard('abdulkariimhssan@gmail.com')">
                    <div class="contact-icon w-11 h-11 md:w-12 md:h-12 mx-auto mb-3 md:mb-4 rounded-xl bg-brand-green/10 border border-brand-green/20 flex items-center justify-center transition-transform duration-300">
                        <i data-lucide="mail" class="w-5 h-5 text-brand-green-light"></i>
                    </div>
                    <h3 class="text-white font-semibold text-sm mb-1 font-arabic">البريد الإلكتروني</h3>
                    <p class="text-white/45 text-[9px] md:text-xs" dir="ltr">abdulkariimhssan@gmail.com</p>
                    <p class="text-white/20 text-[8px] md:text-[9px] mt-2 group-hover:text-brand-gold/60 transition-colors">اضغط للنسخ</p>
                </div>

                <!-- الموقع -->
                <a href="https://maps.app.goo.gl/xUvaExEeZWgK2W3f6" target="_blank" rel="noopener noreferrer" class="contact-item group p-5 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 text-center cursor-pointer no-underline block">
                    <div class="contact-icon w-11 h-11 md:w-12 md:h-12 mx-auto mb-3 md:mb-4 rounded-xl bg-brand-gold/10 border border-brand-gold/20 flex items-center justify-center transition-transform duration-300">
                        <i data-lucide="map-pin" class="w-5 h-5 text-brand-gold-light"></i>
                    </div>
                    <h3 class="text-white font-semibold text-sm mb-1 font-arabic">الموقع</h3>
                    <p class="text-white/45 text-xs">المملكة العربية السعودية</p>
                    <p class="text-white/20 text-[8px] md:text-[9px] mt-2 group-hover:text-brand-gold/60 transition-colors flex items-center justify-center gap-1"><i data-lucide="external-link" class="w-3 h-3"></i> افتح في الخريطة</p>
                </a>

            </div>
        </div>
    </section>

    <!-- Brands Section -->
    <section id="brands" class="relative py-16 md:py-32 px-4 md:px-6">
        <div class="max-w-6xl mx-auto">
            <div class="text-center mb-10 md:mb-16 reveal">
                <span class="text-[9px] md:text-[10px] font-medium uppercase tracking-widest text-brand-gold/60 mb-3 md:mb-4 block">Our Partners</span>
                <h2 class="font-arabic text-2xl md:text-5xl font-bold mb-3 md:mb-4">العلامات التجارية</h2>
                <p class="text-white/45 text-xs md:text-sm max-w-xs md:max-w-md mx-auto">نحن وكلاء حصريون لأكبر العلامات العالمية في المعدات والمحركات</p>
            </div>
            <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-3 md:gap-4 reveal" style="transition-delay: 200ms;">
                <div class="brand-card group relative p-4 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 cursor-pointer overflow-hidden flex flex-col items-center justify-center text-center">
                    <div class="absolute inset-0 bg-gradient-to-b from-red-500/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                    <div class="relative z-10 flex flex-col items-center justify-center flex-1">
                        <div class="w-full h-16 md:h-24 flex items-center justify-center mb-3 md:mb-4"><img src="https://z-cdn-media.chatglm.cn/files/16f75c65-2e2e-4464-8a80-331740527b60.png?auth_key=1878954810-44e3206c59204bc08c9f6460afb6cb9c-0-ea1dc066e191454108785a62b5088336" alt="SHINERAY Logo" class="brand-logo max-h-full max-w-full object-contain"></div>
                        <h3 class="text-white font-semibold text-[11px] md:text-sm mb-0.5">SHINERAY</h3>
                        <p class="text-white/30 text-[7px] md:text-[9px] uppercase tracking-wider">Motorcycles</p>
                    </div>
                </div>
                <div class="brand-card group relative p-4 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 cursor-pointer overflow-hidden flex flex-col items-center justify-center text-center">
                    <div class="absolute inset-0 bg-gradient-to-b from-yellow-500/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                    <div class="relative z-10 flex flex-col items-center justify-center flex-1">
                        <div class="w-full h-16 md:h-24 flex items-center justify-center mb-3 md:mb-4"><img src="https://z-cdn-media.chatglm.cn/files/029c747c-7e10-45ca-af0b-9b25cebac529.png?auth_key=1878954810-1ae4f1e2d3bf491299dfe1fcfd15c340-0-f31a780966bd1a2ac3f83accc3f283a6" alt="DaiSHIN Logo" class="brand-logo max-h-full max-w-full object-contain"></div>
                        <h3 class="text-white font-semibold text-[11px] md:text-sm mb-0.5">DaiSHIN</h3>
                        <p class="text-white/30 text-[7px] md:text-[9px] uppercase tracking-wider">by HONDA</p>
                    </div>
                </div>
                <div class="brand-card group relative p-4 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 cursor-pointer overflow-hidden flex flex-col items-center justify-center text-center">
                    <div class="absolute inset-0 bg-gradient-to-b from-red-600/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                    <div class="relative z-10 flex flex-col items-center justify-center flex-1">
                        <div class="w-full h-16 md:h-24 flex items-center justify-center mb-3 md:mb-4"><img src="https://z-cdn-media.chatglm.cn/files/d9d546a7-80ef-40c8-ad77-03f15b1b45ac.png?auth_key=1878957164-5ba60e32325941bdbaac94726ee78662-0-f07442e6bc3a6ecbd948bfd2a0e10db5" alt="Robin SUBARU Logo" class="brand-logo max-h-full max-w-full object-contain"></div>
                        <h3 class="text-white font-semibold text-[11px] md:text-sm mb-0.5">Robin SUBARU</h3>
                        <p class="text-white/30 text-[7px] md:text-[9px] uppercase tracking-wider">Engines</p>
                    </div>
                </div>
                <div class="brand-card group relative p-4 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 cursor-pointer overflow-hidden flex flex-col items-center justify-center text-center">
                    <div class="absolute inset-0 bg-gradient-to-b from-orange-500/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                    <div class="relative z-10 flex flex-col items-center justify-center flex-1">
                        <div class="w-full h-16 md:h-24 flex items-center justify-center mb-3 md:mb-4"><img src="https://z-cdn-media.chatglm.cn/files/826fe5eb-1937-4ab7-8d29-65614c5c0a57.png?auth_key=1878957164-7eb3966024214562b359e06ce8f9d74e-0-a1c7f7e031a38218d026e8d24e5f4475" alt="Tanaka Logo" class="brand-logo max-h-full max-w-full object-contain"></div>
                        <h3 class="text-white font-semibold text-[11px] md:text-sm mb-0.5">Tanaka</h3>
                        <p class="text-white/30 text-[7px] md:text-[9px] uppercase tracking-wider">Power Equip.</p>
                    </div>
                </div>
                <div class="brand-card group relative p-4 md:p-6 rounded-2xl border border-white/[0.08] bg-[#26262e] hover:bg-[#32323c] transition-all duration-500 cursor-pointer overflow-hidden flex flex-col items-center justify-center text-center col-span-2 sm:col-span-1">
                    <div class="absolute inset-0 bg-gradient-to-b from-blue-500/5 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
                    <div class="relative z-10 flex flex-col items-center justify-center flex-1">
                        <div class="w-full h-16 md:h-24 flex items-center justify-center mb-3 md:mb-4 bg-white/90 rounded-lg p-1.5 md:p-2"><img src="https://z-cdn-media.chatglm.cn/files/dc721975-8bb9-4a30-962f-06dfe5de359b.jpg?auth_key=1878957164-0f9fa5eb9fdd45d695c0240aae2cc47e-0-2424b6fa513c5d4c4baea5a0c3578ec6" alt="FUJI DELUXE Logo" class="brand-logo max-h-full max-w-full object-contain"></div>
                        <h3 class="text-white font-semibold text-[11px] md:text-sm mb-0.5">FUJI DELUXE</h3>
                        <p class="text-white/30 text-[7px] md:text-[9px] uppercase tracking-wider">Generators</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="border-t border-white/[0.08] py-6 md:py-8 px-4 md:px-6">
        <div class="max-w-7xl mx-auto flex flex-col items-center gap-4 md:flex-row md:justify-between">
            <div class="flex items-center gap-2.5">
                <img src="https://z-cdn-media.chatglm.cn/files/0c93625e-a572-40b8-84a3-30aa83997b59.png?auth_key=1878940382-5c01bfe1be3b4a4d80d8dc7d36005971-0-b0f72ef1e77a04ebdfeda671afcf8ca3" alt="شعار بن لسود" class="w-6 h-6 logo-img">
                <div class="flex flex-col leading-tight">
                    <span class="text-white/45 text-[10px] md:text-xs font-arabic">شركة بن لسود للزراعة والتجارة</span>
                    <span class="text-white/25 text-[8px] md:text-[10px]">Binlaswad Agricultural & Commercial Co.</span>
                </div>
            </div>
            <p class="text-white/25 text-[10px] md:text-xs">© 2025 Binlaswad Agricultural & Commercial Co.</p>
            <div class="flex items-center gap-4">
                <a href="https://wa.me/966591668398" target="_blank" class="text-white/30 hover:text-[#25D366] transition-colors"><i data-lucide="message-circle" class="w-4 h-4"></i></a>
                <a href="#" class="text-white/30 hover:text-white transition-colors"><i data-lucide="twitter" class="w-4 h-4"></i></a>
                <a href="#" class="text-white/30 hover:text-white transition-colors"><i data-lucide="instagram" class="w-4 h-4"></i></a>
                <a href="#" class="text-white/30 hover:text-white transition-colors"><i data-lucide="linkedin" class="w-4 h-4"></i></a>
            </div>
        </div>
    </footer>

    <script>
        lucide.createIcons();

        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('open');
            document.body.style.overflow = menu.classList.contains('open') ? 'hidden' : '';
        }

        function generateQR() {
            const qr = document.getElementById('qrCode');
            const pattern = [1,1,1,0,1,0,1,0,1,1,1,1,0,1,0,0,1,0,0,1,0,1,1,1,0,1,0,1,0,1,1,1,0,0,0,0,1,1,0,0,0,0,0,1,0,1,1,0,0,1,1,0,1,0,0,1,0,0,1,1,0,0,1,0,1,1,1,0,0,1,1,0,1,1,1,0,0,0,0,1,0,0,0,0,0,0,1,1,1,0,0,1,0,1,0,1,1,1,0,1,1,1,0,1,0,1,0,1,0,1,0,1,0,1,1,1,0,1,1,0,0,1,1,1];
            pattern.forEach(cell => { const div = document.createElement('div'); div.className = `qr-cell ${cell ? 'qr-dark' : 'qr-light'}`; qr.appendChild(div); });
        }
        generateQR();

        const revealElements = document.querySelectorAll('.reveal');
        const revealObserver = new IntersectionObserver((entries) => { entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add('active'); }); }, { threshold: 0.1 });
        revealElements.forEach(el => revealObserver.observe(el));

        function showToast(message) { const toast = document.getElementById('toast'); toast.textContent = '✓ ' + message; toast.classList.add('show'); setTimeout(() => toast.classList.remove('show'), 2500); }

        function copyToClipboard(text) { navigator.clipboard.writeText(text).then(() => { showToast('تم نسخ: ' + text); }).catch(() => { showToast('تم النسخ'); }); }

        function copyCardInfo() {
            const info = `عبدالكريم باقحيزل - ABDULKARIM BAQAHIZAL\nشركة بن لسود للزراعة والتجارة\nBinlaswad Agricultural & Commercial Co.\n\nPhone: +966 59 166 8398\nWhatsApp: https://wa.me/966591668398\nEmail: abdulkariimhssan@gmail.com\nLocation: Saudi Arabia\nMap: https://maps.app.goo.gl/xUvaExEeZWgK2W3f6\n\nCatalog 1: https://drive.google.com/file/d/1d000IApFfoIUzGODhVQqqrLCNYfOiZbc/view\nCatalog 2: https://drive.google.com/file/d/1bTutJmWzQL73g6B2sFGtPBnjpHZMrUpj/view\n\nBrands: SHINERAY | DaiSHIN | Robin SUBARU | Tanaka | FUJI DELUXE`;
            navigator.clipboard.writeText(info).then(() => { showToast('تم نسخ معلومات البطاقة'); }).catch(() => { showToast('تم نسخ المعلومات'); });
        }

        function downloadCard() {
            const card = document.querySelector('.business-card');
            showToast('جاري تحضير البطاقة للتحميل...');
            
            html2canvas(card, {
                scale: 2,
                useCORS: true,
                backgroundColor: null
            }).then(canvas => {
                const link = document.createElement('a');
                link.download = 'Binlaswad-Card.png';
                link.href = canvas.toDataURL();
                link.click();
                showToast('تم تحميل البطاقة بنجاح!');
            }).catch(() => {
                showToast('حدث خطأ أثناء التحميل');
            });
        }

        function shareCard() {
            if (navigator.share) { navigator.share({ title: 'شركة بن لسود للزراعة والتجارة', text: 'عبدالكريم باقحيزل - Binlaswad', url: window.location.href }); }
            else { navigator.clipboard.writeText(window.location.href).then(() => { showToast('تم نسخ رابط الموقع'); }); }
        }

        document.querySelectorAll('a[href^="#"]').forEach(anchor => { anchor.addEventListener('click', function(e) { e.preventDefault(); const target = document.querySelector(this.getAttribute('href')); if (target) target.scrollIntoView({ behavior: 'smooth', block: 'start' }); }); });

        const card = document.querySelector('.business-card');
        if (card && window.matchMedia('(min-width: 768px)').matches) {
            card.addEventListener('mousemove', (e) => { const rect = card.getBoundingClientRect(); const x = (e.clientX - rect.left) / rect.width - 0.5; const y = (e.clientY - rect.top) / rect.height - 0.5; card.style.transform = `perspective(1000px) rotateY(${x * -8}deg) rotateX(${y * 8}deg) scale(1.02)`; });
            card.addEventListener('mouseleave', () => { card.style.transform = 'perspective(1000px) rotateY(0deg) rotateX(0deg) scale(1)'; });
        }
    </script>
</body>
</html>
