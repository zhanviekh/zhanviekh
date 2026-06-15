<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>فروشگاه لباس کودک ژانویه کوچولو</title>
    
    <!-- فونت‌های فارسی گوگل -->
    <link href="https://fonts.googleapis.com/css2?family=Lalezar&family=Vazirmatn:wght@300;400;700;900&display=swap" rel="stylesheet">
    
    <!-- آیکون‌ها -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- استایل‌ها -->
    <style>
        :root {
            --color-cream: #FDFBF7;
            --color-sky-blue: #A2D2FF;
            --color-soft-pink: #FFC8DD;
            --color-bright-pink: #FFAFCC;
            --color-yellow: #FFF9B0;
            --color-green: #B0E57C;
            --color-text: #4A4A4A;
            --color-dark: #2D3436;
            --shadow-soft: 0 10px 30px rgba(162, 210, 255, 0.3);
            --shadow-hover: 0 15px 40px rgba(255, 175, 204, 0.4);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Vazirmatn', sans-serif;
        }

        body {
            background-color: var(--color-cream);
            color: var(--color-text);
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: 'Lalezar', cursive;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* --- دکمه‌های عمومی --- */
        .btn {
            display: inline-block;
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            cursor: pointer;
            border: none;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }

        .btn-primary {
            background: linear-gradient(45deg, var(--color-sky-blue), var(--color-soft-pink));
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 8px 25px rgba(162, 210, 255, 0.6);
        }

        /* --- هدر و ناوبری --- */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            padding: 15px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(253, 251, 247, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 20px rgba(0,0,0,0.05);
            transition: all 0.3s ease;
        }

        .logo {
            font-size: 1.8rem;
            color: var(--color-bright-pink);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            color: var(--color-sky-blue);
        }

        nav ul {
            display: flex;
            gap: 25px;
            list-style: none;
        }

        nav a {
            font-weight: 700;
            color: var(--color-text);
            transition: color 0.3s;
        }

        nav a:hover {
            color: var(--color-sky-blue);
        }

        .mobile-menu-btn {
            display: none;
            font-size: 1.5rem;
            color: var(--color-text);
        }

        /* --- بخش Hero (3D Background) --- */
        #hero {
            position: relative;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            overflow: hidden;
            padding-top: 60px;
        }

        #canvas-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            background: radial-gradient(circle at center, #fff5f5 0%, #eefcff 100%);
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.75);
            border-radius: 30px;
            backdrop-filter: blur(5px);
            border: 2px solid rgba(255, 255, 255, 0.8);
            box-shadow: var(--shadow-soft);
            animation: fadeInUp 1s ease-out;
        }

        .hero-title {
            font-size: 3.5rem;
            color: var(--color-dark);
            margin-bottom: 10px;
            text-shadow: 2px 2px 0px var(--color-yellow);
        }

        .hero-slogan {
            font-size: 1.5rem;
            color: #666;
            margin-bottom: 30px;
        }

        /* --- بخش محصولات --- */
        #products {
            padding: 80px 5%;
            background-color: #fff;
            position: relative;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            color: var(--color-dark);
            margin-bottom: 50px;
            position: relative;
        }

        .section-title::after {
            content: '★';
            display: block;
            color: var(--color-yellow);
            font-size: 1.5rem;
            margin-top: 10px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            perspective: 1000px;
        }

        .product-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275), box-shadow 0.4s;
            border: 1px solid #f0f0f0;
            position: relative;
            transform-style: preserve-3d;
        }

        .product-card:hover {
            transform: translateY(-10px) rotateX(5deg);
            box-shadow: var(--shadow-hover);
        }

        .product-image-container {
            height: 280px; /* کمی بلندتر برای نمایش بهتر لباس */
            overflow: hidden;
            background: #f9f9f9;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }

        .product-image-container img {
            width: 100%;
            height: 100%;
            object-fit: cover; /* یا contain اگر می‌خواهید کل لباس دیده شود */
            transition: transform 0.5s;
        }

        .product-card:hover .product-image-container img {
            transform: scale(1.1);
        }

        .product-info {
            padding: 20px;
            text-align: center;
            background: white;
            border-radius: 20px 20px 0 0;
            transform: translateZ(20px);
        }

        .product-name {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 10px;
            color: var(--color-dark);
        }

        .product-price {
            color: var(--color-bright-pink);
            font-size: 1.4rem;
            font-weight: 800;
            margin-bottom: 15px;
        }

        .product-actions {
            display: flex;
            justify-content: center;
            gap: 10px;
        }

        .btn-sm {
            padding: 8px 15px;
            font-size: 0.9rem;
            border-radius: 15px;
        }

        .btn-outline {
            border: 2px solid var(--color-sky-blue);
            color: var(--color-sky-blue);
            background: transparent;
        }

        .btn-outline:hover {
            background: var(--color-sky-blue);
            color: white;
        }

        /* --- بخش جایزه و جشنواره (جدید) --- */
        #promo-section {
            padding: 60px 5%;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 99%, #fecfef 100%);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .promo-card {
            background: rgba(255, 255, 255, 0.9);
            border-radius: 30px;
            padding: 40px 20px;
            max-width: 800px;
            margin: 0 auto;
            box-shadow: 0 20px 50px rgba(0,0,0,0.1);
            border: 4px dashed #ffafcc;
            position: relative;
            z-index: 2;
        }

        .promo-icon {
            font-size: 4rem;
            color: #ff6b6b;
            animation: bounce 2s infinite;
            margin-bottom: 20px;
        }

        .promo-title {
            font-size: 2.2rem;
            color: var(--color-dark);
            margin-bottom: 15px;
        }

        .promo-text {
            font-size: 1.3rem;
            color: #555;
            line-height: 1.8;
        }

        .promo-highlight {
            background: var(--color-yellow);
            padding: 2px 10px;
            border-radius: 5px;
            font-weight: 900;
            color: var(--color-dark);
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
            40% {transform: translateY(-20px);}
            60% {transform: translateY(-10px);}
        }

        /* --- بخش چرا ما (مزایا) --- */
        #why-us {
            padding: 80px 5%;
            background: linear-gradient(180deg, #fff 0%, var(--color-yellow) 100%);
            text-align: center;
        }

        .benefits-toggle-card {
            background: white;
            padding: 40px;
            border-radius: 30px;
            box-shadow: var(--shadow-soft);
            max-width: 800px;
            margin: 0 auto;
            cursor: pointer;
            transition: transform 0.3s;
            border: 3px dashed var(--color-sky-blue);
        }

        .benefits-toggle-card:hover {
            transform: scale(1.02);
        }

        .benefits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 20px;
            margin-top: 40px;
            max-height: 0;
            overflow: hidden;
            opacity: 0;
            transition: all 0.8s ease;
        }

        .benefits-grid.active {
            max-height: 2000px;
            opacity: 1;
        }

        .benefit-item {
            background: white;
            padding: 15px;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            font-weight: bold;
            color: var(--color-text);
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .benefit-item i {
            color: var(--color-green);
        }

        /* --- بخش تماس و آدرس --- */
        #contact {
            padding: 80px 5%;
            background: #fff;
        }

        .contact-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .contact-card {
            background: var(--color-cream);
            padding: 30px;
            border-radius: 25px;
            text-align: center;
            border: 1px solid #eee;
            transition: transform 0.3s;
        }

        .contact-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-soft);
        }

        .contact-icon {
            font-size: 3rem;
            margin-bottom: 20px;
            display: inline-block;
        }

        .icon-phone { color: #3498db; }
        .icon-eitaa { color: #43a047; }
        .icon-rubika { color: #e91e63; }
        .icon-insta { color: #e1306c; }

        .contact-info h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
        }

        .contact-info p {
            font-size: 1.2rem;
            color: #666;
        }

        .address-card {
            background: linear-gradient(135deg, var(--color-sky-blue), var(--color-soft-pink));
            color: white;
            grid-column: 1 / -1;
            text-align: center;
            padding: 40px;
            border-radius: 25px;
            margin-top: 20px;
        }

        .address-card p {
            color: white;
            font-size: 1.3rem;
            margin-top: 15px;
        }

        /* --- فوتر --- */
        footer {
            background-color: var(--color-dark);
            color: white;
            text-align: center;
            padding: 30px;
            margin-top: 50px;
        }

        .footer-socials {
            margin-bottom: 20px;
        }

        .footer-socials a {
            font-size: 1.5rem;
            margin: 0 10px;
            color: #ccc;
            transition: color 0.3s;
        }

        .footer-socials a:hover {
            color: var(--color-sky-blue);
        }

        /* --- انیمیشن‌ها --- */
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* --- مدیا کوئری‌ها --- */
        @media (max-width: 768px) {
            .hero-title { font-size: 2.5rem; }
            nav ul { display: none; }
            .mobile-menu-btn { display: block; }
            
            nav.active ul {
                display: flex;
                flex-direction: column;
                position: absolute;
                top: 70px;
                left: 0;
                width: 100%;
                background: white;
                padding: 20px;
                box-shadow: 0 5px 10px rgba(0,0,0,0.1);
            }
            .promo-title { font-size: 1.5rem; }
            .promo-text { font-size: 1rem; }
        }
    </style>
</head>
<body>

    <!-- کانتینر Three.js برای پس‌زمینه سه‌بعدی -->
    <div id="canvas-container"></div>

    <!-- هدر سایت -->
    <header>
        <div class="logo">
            <i class="fa-solid fa-cloud-meatball"></i>
            ژانویه کوچولو
        </div>
        <nav id="navbar">
            <ul>
                <li><a href="#hero">خانه</a></li>
                <li><a href="#products">محصولات</a></li>
                <li><a href="#promo-section">جشنواره</a></li>
                <li><a href="#why-us">مزایا</a></li>
                <li><a href="#contact">تماس با ما</a></li>
            </ul>
        </nav>
        <div class="mobile-menu-btn" onclick="toggleMenu()">
            <i class="fa-solid fa-bars"></i>
        </div>
    </header>

    <!-- بخش اصلی (Hero) -->
    <section id="hero">
        <div class="hero-content">
            <h1 class="hero-title">ژانویه کوچولو</h1>
            <p class="hero-slogan">دنیای لباس‌های شیک برای کوچولوهای دوست‌داشتنی</p>
            <a href="#products" class="btn btn-primary">مشاهده محصولات</a>
        </div>
    </section>

    <!-- بخش محصولات -->
    <section id="products">
        <h2 class="section-title">قیمت‌های عجیب غریب</h2>
        <div class="products-grid" id="product-container">
            <!-- محصولات توسط جاوااسکریپت پر می‌شوند -->
        </div>
    </section>

    <!-- بخش جایزه و جشنواره (جدید) -->
    <section id="promo-section">
        <div class="promo-card">
            <i class="fa-solid fa-gift promo-icon"></i>
            <h2 class="promo-title">جشنواره جایزه بزرگ</h2>
            <p class="promo-text">
                هرکس در مجموع <span class="promo-highlight">۱۰ خرید</span> انجام دهد، از طرف 
                <span style="color:var(--color-bright-pink); font-weight:bold;">گالری ژانویه کوچولو</span> 
                یک لباس به انتخاب خودش <br> کاملاً <span class="promo-highlight">رایگان</span> هدیه می‌گیرد!
            </p>
        </div>
    </section>

    <!-- بخش چرا ما -->
    <section id="why-us">
        <h2 class="section-title" style="color: var(--color-dark);">چرا از ژانویه کوچولو خرید کنیم؟</h2>
        
        <div class="benefits-toggle-card" onclick="toggleBenefits()">
            <i class="fa-solid fa-hand-holding-heart" style="font-size: 3rem; color: var(--color-bright-pink); margin-bottom: 20px;"></i>
            <h3 style="font-size: 1.8rem;">برای دیدن ۲۰ مزیت فوق‌العاده کلیک کنید!</h3>
            <p style="margin-top: 10px; color: #777;">(روی این کارت کلیک کنید)</p>
        </div>

        <div class="benefits-grid" id="benefits-list">
            <!-- لیست مزایا -->
        </div>
    </section>

    <!-- بخش تماس و آدرس -->
    <section id="contact">
        <h2 class="section-title">ارتباط با ما</h2>
        <div class="contact-container">
            
            <!-- تماس تلفنی -->
            <div class="contact-card">
                <div class="contact-icon icon-phone">
                    <i class="fa-solid fa-phone-volume"></i>
                </div>
                <div class="contact-info">
                    <h3>تماس تلفنی</h3>
                    <p dir="ltr">09926274950</p>
                </div>
            </div>

            <!-- ایتا -->
            <div class="contact-card">
                <div class="contact-icon icon-eitaa">
                    <i class="fa-brands fa-whatsapp" style="color:#43a047"></i> <!-- نماد جایگزین -->
                </div>
                <div class="contact-info">
                    <h3>پیام در ایتا</h3>
                    <p dir="ltr">09926274950</p>
                </div>
            </div>

            <!-- روبیکا -->
            <div class="contact-card">
                <div class="contact-icon icon-rubika">
                    <i class="fa-solid fa-paper-plane"></i>
                </div>
                <div class="contact-info">
                    <h3>ارتباط در روبیکا</h3>
                    <p dir="ltr">09926274950</p>
                </div>
            </div>

            <!-- اینستاگرام -->
            <div class="contact-card">
                <div class="contact-icon icon-insta">
                    <i class="fa-brands fa-instagram"></i>
                </div>
                <div class="contact-info">
                    <h3>اینستاگرام</h3>
                    <p>@zhanvie_kh</p>
                </div>
            </div>

            <!-- آدرس -->
            <div class="address-card">
                <i class="fa-solid fa-map-location-dot" style="font-size: 3rem; margin-bottom: 10px;"></i>
                <h3>آدرس فروشگاه</h3>
                <p>روبه‌روی درمانگاه مادر، انتهای پاساژ، شهرستان سرخه</p>
            </div>

        </div>
    </section>

    <!-- فوتر -->
    <footer>
        <div class="footer-socials">
            <a href="#"><i class="fa-brands fa-instagram"></i></a>
            <a href="#"><i class="fa-brands fa-telegram"></i></a>
            <a href="#"><i class="fa-brands fa-whatsapp"></i></a>
        </div>
        <p>© ۱۴۰۳ فروشگاه لباس کودک ژانویه کوچولو. تمامی حقوق محفوظ است.</p>
        <p style="font-size: 0.8rem; margin-top: 10px; opacity: 0.7;">طراحی شده با عشق برای کودکان</p>
    </footer>

    <!-- کتابخانه Three.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

    <!-- جاوااسکریپت اصلی -->
    <script>
        // --- داده‌های جدید محصولات (با قیمت ثابت ۲۳۵,۰۰۰) ---
        const products = [
            { 
                id: 1, 
                name: "تی‌شرت تابستانی سامر", 
                price: "235,000", 
                image: "https://z-cdn-media.chatglm.cn/files/35155a6d-b011-4841-9dd9-9e79747a66e2.png?auth_key=1881481706-35d5c87ce08e4d70bc6ea0e78948327c-0-b19af96ac3b7c2f809d5cee42d98561e" 
            },
            { 
                id: 2, 
                name: "ست شلوارک طوسی و آبی", 
                price: "235,000", 
                image: "https://z-cdn-media.chatglm.cn/files/516ab5c4-418a-4610-a18c-3786b623a0f3.png?auth_key=1881481706-c5cc6511939e4ec9baa8b705ec44f224-0-016d971594f23fc8a7936fbd3c269dd9" 
            },
            { 
                id: 3, 
                name: "تیشرت دیزل با طرح بسکتبال", 
                price: "235,000", 
                image: "https://z-cdn-media.chatglm.cn/files/c38a379a-d83f-4dae-b327-1e9f38333b3f.png?auth_key=1881481706-888f42b932ba480e85d0efad0852ec67-0-89f2eed12fd6f47c938c7ff68dd344f8" 
            },
            { 
                id: 4, 
                name: "هودی زرد ویکتری", 
                price: "235,000", 
                image: "https://z-cdn-media.chatglm.cn/files/02b95ec3-8011-4ebb-9fc5-cb6c4257529f.png?auth_key=1881481706-c44538499bb44d27bc055664bf722b7a-0-1a04feb35122e7eadabe451eff6edd51" 
            },
            { 
                id: 5, 
                name: "ست شلوارک مشکی، کرم و کاکائویی", 
                price: "235,000", 
                image: "https://z-cdn-media.chatglm.cn/files/08e29aae-06b9-425f-8c6b-d0b5dd8b609a.png?auth_key=1881481706-6c98a4aa50854016baa5a83ff0f360e6-0-6e8c5bfef102adf3a2a2d9b3e30f6ca3" 
            },
            { 
                id: 6, 
                name: "شلوارک قرمز و شلوار کرم ببی‌لند", 
                price: "235,000", 
                image: "https://z-cdn-media.chatglm.cn/files/808a21c0-739a-4ca1-a068-5d13dc9ac7e7.png?auth_key=1881481706-eaef44f989d743c9924f139c97b93ccf-0-605372cc0117bc368c2dbc7a7bf854d4" 
            },
            { 
                id: 7, 
                name: "شلوارک‌های طرح گل رز", 
                price: "235,000", 
                image: "https://z-cdn-media.chatglm.cn/files/12cc7b74-cedb-44ae-b2aa-84eae69db7b8.png?auth_key=1881481706-1c6e5022756249129f262e8714e191cd-0-4cde390eeb478a1816ea54d27e7754a0" 
            }
        ];

        // --- رندر کردن محصولات ---
        const productContainer = document.getElementById('product-container');
        products.forEach(product => {
            const card = document.createElement('div');
            card.className = 'product-card';
            card.innerHTML = `
                <div class="product-image-container">
                    <img src="${product.image}" alt="${product.name}">
                </div>
                <div class="product-info">
                    <h3 class="product-name">${product.name}</h3>
                    <div class="product-price">${product.price} تومان</div>
                    <div class="product-actions">
                        <button class="btn btn-sm btn-outline">مشاهده</button>
                        <button class="btn btn-sm btn-primary" onclick="addToCart('${product.name}')">خرید</button>
                    </div>
                </div>
            `;
            productContainer.appendChild(card);
        });

        // --- لیست مزایا ---
        const benefits = [
            "قیمت‌های اقتصادی", "کیفیت بالا", "تنوع زیاد محصولات", "ارسال سریع", 
            "پشتیبانی پاسخگو", "پارچه‌های نرم و راحت", "مناسب پوست حساس کودکان", "طرح‌های به‌روز",
            "خرید آسان", "بسته‌بندی زیبا", "ضمانت رضایت مشتری", "محصولات خاص و متفاوت",
            "تخفیف‌های دوره‌ای", "تنوع رنگ‌بندی", "مناسب تمام سنین کودک", "ثبت سفارش سریع",
            "بروزرسانی مداوم محصولات", "تجربه خرید لذت‌بخش", "اعتماد مشتریان", "فروشگاه تخصصی لباس کودک"
        ];

        const benefitsList = document.getElementById('benefits-list');
        benefits.forEach((text, index) => {
            const item = document.createElement('div');
            item.className = 'benefit-item';
            item.innerHTML = `<i class="fa-solid fa-star"></i> ${text}`;
            benefitsList.appendChild(item);
        });

        // --- لاجیک باز و بسته شدن مزایا ---
        let isBenefitsOpen = false;
        function toggleBenefits() {
            isBenefitsOpen = !isBenefitsOpen;
            const list = document.getElementById('benefits-list');
            if (isBenefitsOpen) {
                list.classList.add('active');
                // انیمیشن آبشاری آیتم‌ها
                const items = document.querySelectorAll('.benefit-item');
                items.forEach((item, idx) => {
                    setTimeout(() => {
                        item.style.opacity = '1';
                        item.style.transform = 'translateY(0)';
                    }, idx * 100);
                });
            } else {
                list.classList.remove('active');
                const items = document.querySelectorAll('.benefit-item');
                items.forEach(item => {
                    item.style.opacity = '0';
                    item.style.transform = 'translateY(20px)';
                });
            }
        }

        // --- موبایل منو ---
        function toggleMenu() {
            document.getElementById('navbar').classList.toggle('active');
        }

        // --- خرید (شبیه‌سازی) ---
        function addToCart(productName) {
            // ایجاد یک پیام تست (Toast) ساده
            const toast = document.createElement('div');
            toast.textContent = `"${productName}" به سبد خرید اضافه شد! 🎈`;
            toast.style.position = 'fixed';
            toast.style.bottom = '20px';
            toast.style.left = '50%';
            toast.style.transform = 'translateX(-50%)';
            toast.style.background = '#4CAF50';
            toast.style.color = 'white';
            toast.style.padding = '15px 30px';
            toast.style.borderRadius = '50px';
            toast.style.boxShadow = '0 5px 15px rgba(0,0,0,0.2)';
            toast.style.zIndex = '2000';
            toast.style.animation = 'fadeInUp 0.5s ease';
            document.body.appendChild(toast);
            
            setTimeout(() => {
                toast.style.opacity = '0';
                setTimeout(() => toast.remove(), 500);
            }, 3000);
        }

        // --- Three.js Scene Setup (Background 3D) ---
        function initThreeJS() {
            const container = document.getElementById('canvas-container');
            const scene = new THREE.Scene();
            
            // دوربین
            const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
            camera.position.z = 5;

            // رندر کننده
            const renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });
            renderer.setSize(window.innerWidth, window.innerHeight);
            renderer.setPixelRatio(window.devicePixelRatio);
            container.appendChild(renderer.domElement);

            // نورپردازی
            const ambientLight = new THREE.AmbientLight(0xffffff, 0.6);
            scene.add(ambientLight);

            const directionalLight = new THREE.DirectionalLight(0xffffff, 0.8);
            directionalLight.position.set(5, 10, 7);
            scene.add(directionalLight);

            // ایجاد اشیاء (ابزارها و اشکال کودکانه شناور)
            const objects = [];
            
            // هندسه‌ها
            const geometries = [
                new THREE.IcosahedronGeometry(0.5, 0), // اسباب بازی چندوجهی
                new THREE.TorusGeometry(0.4, 0.15, 16, 100), // حلقه
                new THREE.SphereGeometry(0.4, 32, 32), // بادکنک
                new THREE.ConeGeometry(0.4, 0.8, 32), // کلاه
                new THREE.BoxGeometry(0.5, 0.5, 0.5) // جعبه هدیه
            ];

            // رنگ‌ها از پالت درخواستی
            const colors = [0xA2D2FF, 0xFFC8DD, 0xFFAFCC, 0xFFF9B0, 0xB0E57C];

            // ایجاد ۲۵ جسم شناور تصادفی
            for (let i = 0; i < 25; i++) {
                const geom = geometries[Math.floor(Math.random() * geometries.length)];
                const mat = new THREE.MeshStandardMaterial({ 
                    color: colors[Math.floor(Math.random() * colors.length)],
                    roughness: 0.4,
                    metalness: 0.1
                });
                const mesh = new THREE.Mesh(geom, mat);

                // موقعیت تصادفی
                mesh.position.x = (Math.random() - 0.5) * 15;
                mesh.position.y = (Math.random() - 0.5) * 10;
                mesh.position.z = (Math.random() - 0.5) * 5 - 2; 

                // چرخش تصادفی اولیه
                mesh.rotation.x = Math.random() * Math.PI;
                mesh.rotation.y = Math.random() * Math.PI;

                // ذخیره اطلاعات سرعت چرخش برای انیمیشن
                mesh.userData = {
                    rotSpeedX: (Math.random() - 0.5) * 0.02,
                    rotSpeedY: (Math.random() - 0.5) * 0.02,
                    floatSpeed: Math.random() * 0.01 + 0.005,
                    initialY: mesh.position.y
                };

                scene.add(mesh);
                objects.push(mesh);
            }

            // تعامل با موس (Parallax)
            let mouseX = 0;
            let mouseY = 0;
            let targetX = 0;
            let targetY = 0;

            const windowHalfX = window.innerWidth / 2;
            const windowHalfY = window.innerHeight / 2;

            document.addEventListener('mousemove', (event) => {
                mouseX = (event.clientX - windowHalfX) * 0.001;
                mouseY = (event.clientY - windowHalfY) * 0.001;
            });

            // انیمیشن لوپ
            const clock = new THREE.Clock();

            function animate() {
                requestAnimationFrame(animate);
                
                const elapsedTime = clock.getElapsedTime();

                targetX = mouseX * 2;
                targetY = mouseY * 2;

                // چرخش نرم دوربین بر اساس موس
                camera.rotation.y += 0.05 * (targetX - camera.rotation.y);
                camera.rotation.x += 0.05 * (targetY - camera.rotation.x);

                // انیمیشن اشیاء
                objects.forEach((obj) => {
                    obj.rotation.x += obj.userData.rotSpeedX;
                    obj.rotation.y += obj.userData.rotSpeedY;
                    
                    // حرکت شناور (Sine wave)
                    obj.position.y = obj.userData.initialY + Math.sin(elapsedTime * 2 + obj.position.x) * 0.2;
                });

                renderer.render(scene, camera);
            }

            animate();

            // هندل کردن تغییر سایز پنجره
            window.addEventListener('resize', () => {
                camera.aspect = window.innerWidth / window.innerHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(window.innerWidth, window.innerHeight);
            });
        }

        // راه‌اندازی صحنه سه‌بعدی پس از لود صفحه
        window.addEventListener('load', initThreeJS);

        // Intersection Observer برای انیمیشن اسکرول
        const observerOptions = {
            threshold: 0.2
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        // اعمال انیمیشن اولیه به کارت‌های محصول
        document.querySelectorAll('.product-card').forEach((card, index) => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(50px)';
            card.style.transition = `all 0.6s ease ${index * 0.1}s`;
            observer.observe(card);
        });

    </script>
</body>
</html>
