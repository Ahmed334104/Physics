<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>مستخرج المعلومات الفيزيائية - جميع الملفات</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* ===== أنماط موحدة لجميع الملفات ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary-gradient: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            --secondary-gradient: linear-gradient(135deg, #ff7e5f 0%, #feb47b 100%);
            --dark-bg: #0f172a;
            --card-bg: rgba(255, 255, 255, 0.08);
            --text-light: #f8fafc;
            --text-accent: #38bdf8;
            --border-glow: rgba(56, 189, 248, 0.4);
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            --code-bg: #1e293b;
            --radius: 20px;
            --transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.1);
        }

        body {
            background: var(--dark-bg);
            color: var(--text-light);
            min-height: 100vh;
            padding: 20px;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(37, 117, 252, 0.1) 0%, transparent 20%),
                radial-gradient(circle at 90% 80%, rgba(106, 17, 203, 0.1) 0%, transparent 20%);
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        /* ===== رأس الصفحة الرئيسية ===== */
        .main-header {
            text-align: center;
            padding: 50px 20px;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
            border-radius: 24px;
            background: var(--card-bg);
            backdrop-filter: blur(10px);
            border: 1px solid var(--border-glow);
            box-shadow: var(--shadow);
            animation: fadeInDown 1s ease;
        }

        .main-header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: var(--primary-gradient);
            opacity: 0.1;
            z-index: -1;
            animation: rotate 20s linear infinite;
        }

        .main-header h1 {
            font-size: 3.5rem;
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 15px;
            font-weight: 800;
            letter-spacing: -1px;
        }

        .main-subtitle {
            font-size: 1.4rem;
            opacity: 0.9;
            max-width: 900px;
            margin: 0 auto 30px;
            line-height: 1.6;
        }

        /* ===== قائمة التنقل بين الملفات ===== */
        .file-nav {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin: 30px 0;
        }

        .file-btn {
            padding: 15px 30px;
            border-radius: 50px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--text-light);
            border: 1px solid rgba(255, 255, 255, 0.2);
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
            backdrop-filter: blur(5px);
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .file-btn.active {
            background: var(--primary-gradient);
            border-color: transparent;
            box-shadow: 0 5px 20px rgba(106, 17, 203, 0.5);
        }

        .file-btn:hover:not(.active) {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(106, 17, 203, 0.3);
        }

        /* ===== أقسام الملفات ===== */
        .file-section {
            display: none;
            animation: fadeIn 0.8s ease;
            margin-bottom: 60px;
        }

        .file-section.active {
            display: block;
        }

        .file-header {
            text-align: center;
            margin-bottom: 40px;
            padding: 30px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: var(--radius);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .file-title {
            font-size: 2.5rem;
            color: var(--text-accent);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
        }

        .file-desc {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 800px;
            margin: 0 auto;
        }

        /* ===== أنماط مشتركة للمحتوى ===== */
        .section-title {
            font-size: 2rem;
            margin: 40px 0 25px;
            padding-bottom: 15px;
            border-bottom: 2px solid var(--border-glow);
            position: relative;
            color: var(--text-accent);
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -2px;
            right: 0;
            width: 100px;
            height: 2px;
            background: var(--secondary-gradient);
        }

        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .card {
            background: var(--card-bg);
            border-radius: var(--radius);
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
            backdrop-filter: blur(10px);
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 5px;
            background: var(--primary-gradient);
        }

        .card:hover {
            transform: translateY(-10px);
            border-color: var(--border-glow);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
        }

        .card-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--text-accent);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .card-title i {
            background: var(--primary-gradient);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-size: 1.8rem;
        }

        .card-content {
            line-height: 1.7;
            font-size: 1.05rem;
            opacity: 0.9;
        }

        .card-highlight {
            background: rgba(56, 189, 248, 0.1);
            border-right: 4px solid var(--text-accent);
            padding: 15px;
            border-radius: 0 10px 10px 0;
            margin: 20px 0;
            font-weight: 600;
        }

        .source-badge {
            display: inline-block;
            background: rgba(37, 117, 252, 0.2);
            color: #60a5fa;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            margin-top: 15px;
            font-weight: 600;
            border: 1px solid rgba(37, 117, 252, 0.3);
        }

        /* ===== أنماط خاصة بالقوانين ===== */
        .law-card {
            background: rgba(106, 17, 203, 0.1);
            border: 1px solid rgba(106, 17, 203, 0.3);
        }

        .law-card::before {
            background: var(--secondary-gradient);
        }

        .law-box {
            background: var(--code-bg);
            border-radius: 12px;
            padding: 20px;
            margin: 15px 0;
            border-left: 4px solid var(--text-accent);
            font-family: 'Consolas', 'Monaco', 'Courier New', monospace;
            font-size: 1.1rem;
            overflow-x: auto;
            white-space: nowrap;
        }

        .law-equation {
            color: #7dd3fc;
            font-weight: bold;
            margin: 10px 0;
            padding: 8px 0;
            border-bottom: 1px dashed rgba(125, 211, 252, 0.3);
        }

        .law-label {
            color: #fbbf24;
            font-weight: 600;
            margin-bottom: 8px;
            display: block;
        }

        .law-unicode {
            font-size: 1.2rem;
            letter-spacing: 0.5px;
        }

        /* ===== أنماط ASCII من ملف 5-6 ===== */
        .ascii-equation {
            font-family: 'Cascadia Code', 'Consolas', 'Monaco', monospace;
            background: rgba(0, 0, 0, 0.3);
            padding: 20px;
            border-radius: 10px;
            margin: 15px 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 1.1rem;
            color: #93c5fd;
            line-height: 1.8;
            white-space: pre;
            overflow-x: auto;
            position: relative;
        }

        /* ===== أنماط القوائم ===== */
        .card-list {
            list-style: none;
            padding-right: 20px;
        }

        .card-list li {
            margin-bottom: 12px;
            padding-right: 25px;
            position: relative;
            transition: var(--transition);
        }

        .card-list li:hover {
            transform: translateX(-5px);
            color: var(--text-accent);
        }

        .card-list li::before {
            content: "→";
            position: absolute;
            right: 0;
            color: var(--text-accent);
            font-weight: bold;
        }

        /* ===== أنماط التبديل بين اللغات ===== */
        .language-toggle {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin: 20px 0;
        }

        .lang-btn {
            padding: 10px 24px;
            border-radius: 50px;
            background: rgba(255, 255, 255, 0.1);
            color: var(--text-light);
            border: 1px solid rgba(255, 255, 255, 0.2);
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
            backdrop-filter: blur(5px);
        }

        .lang-btn.active {
            background: var(--primary-gradient);
            border-color: transparent;
            box-shadow: 0 5px 15px rgba(106, 17, 203, 0.4);
        }

        .lang-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(106, 17, 203, 0.3);
        }

        .lang-content {
            display: none;
        }

        .lang-content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        /* ===== أنماط الازدواج اللغوي ===== */
        .dual-text {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .arabic-text {
            background: rgba(240, 248, 255, 0.1);
            border-right: 4px solid var(--text-accent);
            padding: 15px;
            border-radius: 12px;
        }

        .english-text {
            background: rgba(255, 248, 240, 0.1);
            border-left: 4px solid #ff7e5f;
            padding: 15px;
            border-radius: 12px;
        }

        .item {
            margin-bottom: 15px;
            padding: 15px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 12px;
            border-right: 4px solid var(--text-accent);
            transition: var(--transition);
        }

        .item:hover {
            background: rgba(56, 189, 248, 0.1);
            transform: translateX(5px);
        }

        .item-title {
            font-weight: 700;
            color: var(--text-light);
            margin-bottom: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        /* ===== التذييل ===== */
        footer {
            text-align: center;
            padding: 40px 20px;
            margin-top: 60px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.95rem;
            opacity: 0.8;
        }

        /* ===== الأنيميشن ===== */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @keyframes rotate {
            from {
                transform: rotate(0deg);
            }
            to {
                transform: rotate(360deg);
            }
        }

        /* ===== التجاوب مع الشاشات المختلفة ===== */
        @media (max-width: 768px) {
            .main-header h1 {
                font-size: 2.5rem;
            }
            
            .file-title {
                font-size: 2rem;
            }
            
            .cards-container {
                grid-template-columns: 1fr;
            }
            
            .section-title {
                font-size: 1.8rem;
            }
            
            .file-nav {
                flex-direction: column;
                align-items: center;
            }
            
            .file-btn {
                width: 100%;
                max-width: 300px;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- رأس الصفحة الرئيسية -->
        <header class="main-header">
            <h1><i class="fas fa-atom"></i> مستخرج المعلومات الفيزيائية المتكامل</h1>
            <p class="main-subtitle">مجموعة شاملة لجميع الاستخدامات، التطبيقات، والقوانين الفيزيائية من الملفات التعليمية (1-8)</p>
            
            <!-- قائمة التنقل بين الملفات -->
            <div class="file-nav">
                <button class="file-btn active" data-file="file1">
                    <i class="fas fa-file-alt"></i> الملف 1-2
                </button>
                <button class="file-btn" data-file="file2">
                    <i class="fas fa-file-alt"></i> الملف 3-4
                </button>
                <button class="file-btn" data-file="file3">
                    <i class="fas fa-file-alt"></i> الملف 5-6
                </button>
                <button class="file-btn" data-file="file4">
                    <i class="fas fa-file-alt"></i> الملف 7-8
                </button>
            </div>
        </header>

        <!-- ===== ملف 1-2 ===== -->
        <section id="file1" class="file-section active">
            <div class="file-header">
                <h2 class="file-title"><i class="fas fa-bolt"></i> ملفات 1-2: أساسيات الكهرباء</h2>
                <p class="file-desc">استخراج المعلومات من ملفي "1فيزياء.pdf" و "2فيزياء معدل.pdf"</p>
            </div>

            <!-- اختيار اللغة لملف 1-2 -->
            <div class="language-toggle">
                <button class="lang-btn active" onclick="showLang('file1-ar')">العربية</button>
                <button class="lang-btn" onclick="showLang('file1-en')">English</button>
            </div>

            <!-- المحتوى العربي -->
            <div id="file1-ar" class="lang-content active">
                <h2 class="section-title"><i class="fas fa-plug"></i> الاستخدامات المذكورة</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-bolt"></i> استخدامات الكهرباء</h3>
                        <div class="card-content">
                            <div class="item">
                                <div class="item-title">النقل <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>استخدام الكهرباء كقوة محركة في وسائل النقل</p>
                            </div>
                            <div class="item">
                                <div class="item-title">التدفئة <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>استخدام الكهرباء في أنظمة التدفئة</p>
                            </div>
                            <div class="item">
                                <div class="item-title">الإضاءة <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>استخدام الكهرباء في الإضاءة المنزلية والعامة</p>
                            </div>
                            <div class="item">
                                <div class="item-title">الاتصالات <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>استخدام الكهرباء في أنظمة الاتصال</p>
                            </div>
                            <div class="item">
                                <div class="item-title">الحوسبة <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>استخدام الكهرباء في أجهزة الكمبيوتر والحوسبة</p>
                            </div>
                            <span class="source-badge">1فيزياء.pdf - صفحات مختلفة</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-flask"></i> التطبيقات المذكورة</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-microchip"></i> تطبيقات الكهرباء</h3>
                        <div class="card-content">
                            <div class="item">
                                <div class="item-title">البطارية (كومة فولتية) <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>اخترعها أليساندرو فولتا عام 1800، مصنوعة من طبقات متناوبة من الزنك والنحاس</p>
                            </div>
                            <div class="item">
                                <div class="item-title">المحرك الكهربائي <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>اخترعه مايكل فاراداي عام 1821</p>
                            </div>
                            <div class="item">
                                <div class="item-title">الكهرباء الحيوية <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>اكتشفها لويجي جالفاني عام 1791، تشرح كيفية نقل الخلايا العصبية للإشارات</p>
                            </div>
                            <div class="item">
                                <div class="item-title">مقياس الكهرباء الورقي الذهبي <span style="color: #38bdf8;">(من الملف 2)</span></div>
                                <p>أداة لقياس الشحنة الكهربائية</p>
                            </div>
                            <div class="item">
                                <div class="item-title">قضبان البرق <span style="color: #38bdf8;">(من الملف 2)</span></div>
                                <p>تستخدم الأسطح المدببة للحماية من الصواعق</p>
                            </div>
                            <div class="item">
                                <div class="item-title">قفص فاراداي <span style="color: #38bdf8;">(من الملف 2)</span></div>
                                <p>موصل مجوف يحمي من المجالات الكهربائية الخارجية</p>
                            </div>
                            <span class="source-badge">1فيزياء.pdf و 2فيزياء معدل.pdf</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-balance-scale"></i> القوانين المذكورة</h2>
                <div class="cards-container">
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-gavel"></i> قوانين الكهرباء</h3>
                        <div class="card-content">
                            <div class="item">
                                <div class="item-title">قانون كولوم <span style="color: #38bdf8;">(من الملف 2)</span></div>
                                <p>الشحنات المتشابهة تتنافر، والمختلفة تتجاذب</p>
                            </div>
                            <div class="item">
                                <div class="item-title">قانون التربيع العكسي للمجال الكهربائي <span style="color: #38bdf8;">(من الملف 2)</span></div>
                                <p>شدة المجال الكهربائي تتناسب عكسياً مع مربع المسافة (مشابه للجاذبية)</p>
                            </div>
                            <div class="item">
                                <div class="item-title">مبدأ حفظ الشحنة <span style="color: #38bdf8;">(من الملف 1)</span></div>
                                <p>الشحنة الكلية في نظام معزول تبقى ثابتة</p>
                            </div>
                            <span class="source-badge">1فيزياء.pdf و 2فيزياء معدل.pdf</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- المحتوى الإنجليزي -->
            <div id="file1-en" class="lang-content">
                <h2 class="section-title"><i class="fas fa-plug"></i> Uses Mentioned</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-bolt"></i> Electricity Uses</h3>
                        <div class="card-content">
                            <div class="item">
                                <div class="item-title">Transportation <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Electricity as a driving force in transportation</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Heating <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Using electricity in heating systems</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Lighting <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Using electricity in residential and public lighting</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Communications <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Using electricity in communication systems</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Computation <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Using electricity in computers and computing</p>
                            </div>
                            <span class="source-badge">1physics.pdf - various pages</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-flask"></i> Applications Mentioned</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-microchip"></i> Electricity Applications</h3>
                        <div class="card-content">
                            <div class="item">
                                <div class="item-title">Battery (Voltaic Pile) <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Invented by Alessandro Volta in 1800, made of alternating zinc and copper layers</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Electric Motor <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Invented by Michael Faraday in 1821</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Bioelectricity <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Discovered by Luigi Galvani in 1791, explains nerve signal transmission</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Gold-leaf electroscope <span style="color: #38bdf8;">(From File 2)</span></div>
                                <p>Instrument for measuring electric charge</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Lightning rods <span style="color: #38bdf8;">(From File 2)</span></div>
                                <p>Use pointed surfaces for lightning protection</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Faraday cage <span style="color: #38bdf8;">(From File 2)</span></div>
                                <p>Hollow conductor protecting from external electric fields</p>
                            </div>
                            <span class="source-badge">1physics.pdf and 2physics modified.pdf</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-balance-scale"></i> Laws Mentioned</h2>
                <div class="cards-container">
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-gavel"></i> Electricity Laws</h3>
                        <div class="card-content">
                            <div class="item">
                                <div class="item-title">Coulomb's Law <span style="color: #38bdf8;">(From File 2)</span></div>
                                <p>Like charges repel, unlike charges attract</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Inverse-square law for electric field <span style="color: #38bdf8;">(From File 2)</span></div>
                                <p>Electric field strength is inversely proportional to the square of the distance</p>
                            </div>
                            <div class="item">
                                <div class="item-title">Charge conservation principle <span style="color: #38bdf8;">(From File 1)</span></div>
                                <p>Total charge in an isolated system remains constant</p>
                            </div>
                            <span class="source-badge">1physics.pdf and 2physics modified.pdf</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===== ملف 3-4 ===== -->
        <section id="file2" class="file-section">
            <div class="file-header">
                <h2 class="file-title"><i class="fas fa-cogs"></i> ملفات 3-4: المقاومة والمكثف والمحث</h2>
                <p class="file-desc">استخراج المعلومات من ملفي "3فيزياء معدل.pdf" و "4فيزياء معدل.pdf"</p>
            </div>

            <!-- اختيار اللغة لملف 3-4 -->
            <div class="language-toggle">
                <button class="lang-btn active" onclick="showLang('file2-ar')">العربية</button>
                <button class="lang-btn" onclick="showLang('file2-en')">English</button>
            </div>

            <!-- المحتوى العربي -->
            <div id="file2-ar" class="lang-content active">
                <h2 class="section-title"><i class="fas fa-tools"></i> الاستخدامات</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-bolt"></i> استخدامات المقاومة</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>تقسيم الجهد (مثل مقياس الجهد)</li>
                                <li>الحماية: تقليل التيار في الدوائر الحساسة</li>
                            </ul>
                            <div class="card-highlight">يعتمد على: المقاومة الكهربائية وأنواعها</div>
                            <span class="source-badge">3فيزياء معدل.pdf - صفحة 22</span>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-cogs"></i> استخدامات المكثف</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>تمويج الجهد المستمر (تنعيم الجهد)</li>
                                <li>ترشيح إشارات التيار المتردد</li>
                            </ul>
                            <div class="card-highlight">يعتمد على: المكثف وتخزين الطاقة في مجال كهربائي</div>
                            <span class="source-badge">4فيزياء معدل.pdf - صفحة 28</span>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-magnet"></i> استخدامات المحث</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>المرشحات (مع المكثفات)</li>
                                <li>المحولات (نقل الطاقة بالحث)</li>
                            </ul>
                            <div class="card-highlight">يعتمد على: المحث وتخزين الطاقة في مجال مغناطيسي</div>
                            <span class="source-badge">4فيزياء معدل.pdf - صفحة 30</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-mobile-alt"></i> التطبيقات</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-lightbulb"></i> تطبيقات الحث الكهرومغناطيسي</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>محرك فاراداي (أول محرك كهربائي)</li>
                                <li>المولد الكهربائي (تحويل الطاقة الحركية إلى كهربائية)</li>
                            </ul>
                            <div class="card-highlight">يعتمد على: قانون فاراداي للحث الكهرومغناطيسي</div>
                            <span class="source-badge">3فيزياء معدل.pdf - صفحة 18</span>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-satellite-dish"></i> تطبيقات معادلات ماكسويل</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>انتشار الموجات الكهرومغناطيسية بسرعة الضوء</li>
                                <li>فهم الضوء كإشعاع كهرومغناطيسي</li>
                                <li>الاتصالات اللاسلكية</li>
                            </ul>
                            <div class="card-highlight">يعتمد على: معادلات ماكسويل للكهرومغناطيسية</div>
                            <span class="source-badge">3فيزياء معدل.pdf - صفحة 19</span>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-microchip"></i> تطبيقات قانون أوم</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>تصميم الأنظمة الكهربائية (أجهزة، هواتف، إضاءة)</li>
                                <li>حساب التيار والجهد والمقاومة في الدوائر</li>
                                <li>فهم تأثير الحرارة على المقاومة</li>
                            </ul>
                            <div class="card-highlight">يعتمد على: قانون أوم للدوائر الكهربائية</div>
                            <span class="source-badge">4فيزياء معدل.pdf - صفحة 26</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-calculator"></i> القوانين</h2>
                <div class="cards-container">
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-gavel"></i> قانون أوم</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <div class="law-equation law-unicode">
                                    V = I × R
                                </div>
                                <p>حيث:</p>
                                <p>V: الجهد بالفولت (Voltage)</p>
                                <p>I: التيار بالأمبير (Current)</p>
                                <p>R: المقاومة بالأوم (Resistance)</p>
                            </div>
                            <span class="source-badge">4فيزياء معدل.pdf - صفحة 23</span>
                        </div>
                    </div>
                    
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-magnet"></i> قانون الحث الذاتي</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <div class="law-equation law-unicode">
                                    V = L × (dI/dt)
                                </div>
                                <p>حيث:</p>
                                <p>V: الجهد المتولد بالفولت</p>
                                <p>L: معامل الحث الذاتي بالهنري (Inductance)</p>
                                <p>dI/dt: معدل تغير التيار مع الزمن</p>
                            </div>
                            <span class="source-badge">4فيزياء معدل.pdf - صفحة 29</span>
                        </div>
                    </div>
                    
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-charging-station"></i> قانون المكثف</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <div class="law-equation law-unicode">
                                    Q = V × C
                                </div>
                                <p>حيث:</p>
                                <p>Q: الشحنة المخزنة بالكولوم (Charge)</p>
                                <p>V: الجهد بالفولت (Voltage)</p>
                                <p>C: السعة بالفاراد (Capacitance)</p>
                            </div>
                            <span class="source-badge">4فيزياء معدل.pdf - صفحة 2</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- المحتوى الإنجليزي -->
            <div id="file2-en" class="lang-content">
                <h2 class="section-title"><i class="fas fa-tools"></i> Uses</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-bolt"></i> Resistor Uses</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>Voltage division (e.g., potentiometer)</li>
                                <li>Protection: Reduce current in sensitive circuits</li>
                            </ul>
                            <div class="card-highlight">Based on: Electrical resistance and its types</div>
                            <span class="source-badge">3physics_modified.pdf - Page 22</span>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-cogs"></i> Capacitor Uses</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>Smoothing DC voltage</li>
                                <li>Filtering AC signals</li>
                            </ul>
                            <div class="card-highlight">Based on: Capacitor and energy storage in electric field</div>
                            <span class="source-badge">4physics_modified.pdf - Page 28</span>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-magnet"></i> Inductor Uses</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>Filters (with capacitors)</li>
                                <li>Transformers (energy transfer via induction)</li>
                            </ul>
                            <div class="card-highlight">Based on: Inductor and energy storage in magnetic field</div>
                            <span class="source-badge">4physics_modified.pdf - Page 30</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-mobile-alt"></i> Applications</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-lightbulb"></i> Electromagnetic Induction Applications</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>Faraday's motor (first electric motor)</li>
                                <li>Electrical generator (kinetic to electrical energy conversion)</li>
                            </ul>
                            <div class="card-highlight">Based on: Faraday's Law of electromagnetic induction</div>
                            <span class="source-badge">3physics_modified.pdf - Page 18</span>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-satellite-dish"></i> Maxwell's Equations Applications</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>Propagation of electromagnetic waves at speed of light</li>
                                <li>Understanding light as electromagnetic radiation</li>
                                <li>Wireless communications</li>
                            </ul>
                            <div class="card-highlight">Based on: Maxwell's equations for electromagnetism</div>
                            <span class="source-badge">3physics_modified.pdf - Page 19</span>
                        </div>
                    </div>
                    
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-microchip"></i> Ohm's Law Applications</h3>
                        <div class="card-content">
                            <ul class="card-list">
                                <li>Designing electrical systems (appliances, phones, lighting)</li>
                                <li>Calculating current, voltage, resistance in circuits</li>
                                <li>Understanding temperature effect on resistance</li>
                            </ul>
                            <div class="card-highlight">Based on: Ohm's Law for electrical circuits</div>
                            <span class="source-badge">4physics_modified.pdf - Page 26</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-calculator"></i> Laws</h2>
                <div class="cards-container">
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-gavel"></i> Ohm's Law</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <div class="law-equation law-unicode">
                                    V = I × R
                                </div>
                                <p>Where:</p>
                                <p>V: Voltage (in Volts)</p>
                                <p>I: Current (in Amperes)</p>
                                <p>R: Resistance (in Ohms)</p>
                            </div>
                            <span class="source-badge">4physics_modified.pdf - Page 23</span>
                        </div>
                    </div>
                    
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-magnet"></i> Self-Inductance Law</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <div class="law-equation law-unicode">
                                    V = L × (dI/dt)
                                </div>
                                <p>Where:</p>
                                <p>V: Induced Voltage (in Volts)</p>
                                <p>L: Inductance (in Henries)</p>
                                <p>dI/dt: Rate of change of current over time</p>
                            </div>
                            <span class="source-badge">4physics_modified.pdf - Page 29</span>
                        </div>
                    </div>
                    
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-charging-station"></i> Capacitor Law</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <div class="law-equation law-unicode">
                                    Q = V × C
                                </div>
                                <p>Where:</p>
                                <p>Q: Stored Charge (in Coulombs)</p>
                                <p>V: Voltage (in Volts)</p>
                                <p>C: Capacitance (in Farads)</p>
                            </div>
                            <span class="source-badge">4physics_modified.pdf - Page 2</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- ===== ملف 5-6 ===== -->
        <section id="file3" class="file-section">
            <div class="file-header">
                <h2 class="file-title"><i class="fas fa-sitemap"></i> ملفات 5-6: قوانين كيرشوف وتأثيرات التيار</h2>
                <p class="file-desc">تحليل ملفي الفيزياء: قوانين كيرشوف وتأثيرات التيار الكهربائي</p>
            </div>

            <!-- المحتوى العربي (ملف 5-6 له تصميم خاص) -->
            <div class="cards-container">
                <div class="card">
                    <h2 class="card-title"><i class="fas fa-tools"></i> الاستخدامات (Uses)</h2>
                    <div class="card-content">
                        <div class="item">
                            <div class="item-title">تحليل الدوائر الكهربائية المعقدة</div>
                            <p>تحليل الدوائر الكهربائية المعقدة التي لا يمكن حلها بقانون أوم وحده</p>
                            <div class="card-highlight">[DEPENDS ON] ▸ Kirchhoff's Laws (File 5)</div>
                        </div>
                        <div class="item">
                            <div class="item-title">التسخين الكهربائي</div>
                            <p>تطبيقات التسخين مثل السخانات الكهربائية والمكاوي والأفران</p>
                            <div class="card-highlight">[DEPENDS ON] ▸ قانون جول للتأثير الحراري (الملف 6)</div>
                        </div>
                        <div class="item">
                            <div class="item-title">التحليل الكهربائي</div>
                            <p>تحليل المركبات الكيميائية كهربائياً مثل تحليل الماء وتنقية المعادن</p>
                            <div class="card-highlight">[DEPENDS ON] ▸ التأثير الكيميائي للتيار (الملف 6)</div>
                        </div>
                    </div>
                </div>

                <div class="card">
                    <h2 class="card-title"><i class="fas fa-mobile-alt"></i> التطبيقات (Applications)</h2>
                    <div class="card-content">
                        <div class="item">
                            <div class="item-title">الأجهزة الطبية (العلاج بالحرارة، الرنين المغناطيسي)</div>
                            <p>أجهزة العلاج بالحرارة الكهربائية وأجهزة التصوير بالرنين المغناطيسي</p>
                            <div class="card-highlight">[DEPENDS ON] ▸ التأثير الحراري والمغناطيسي (الملف 6)</div>
                        </div>
                        <div class="item">
                            <div class="item-title">المحركات والمولدات الكهربائية</div>
                            <p>تشغيل المحركات الكهربائية والمولدات الكهربائية</p>
                            <div class="card-highlight">[DEPENDS ON] ▸ التأثير المغناطيسي للتيار (الملف 6)</div>
                        </div>
                        <div class="item">
                            <div class="item-title">الطلاء الكهربائي</div>
                            <p>عملية الطلاء الكهربائي مثل الطلاء بالفضة أو المعادن الأخرى</p>
                            <div class="card-highlight">[DEPENDS ON] ▸ التحليل الكهربائي (الملف 6)</div>
                        </div>
                    </div>
                </div>
            </div>

            <h2 class="section-title"><i class="fas fa-balance-scale"></i> القوانين (Laws) - ASCII/Unicode Format</h2>
            <div class="cards-container">
                <div class="card law-card">
                    <h3 class="card-title"><i class="fas fa-bolt"></i> قانون كيرشوف الأول - حفظ التيار</h3>
                    <div class="ascii-equation">
                        ┌─────────────────────────────────────────┐
                        │  Kirchhoff's Current Law (KCL)         │
                        │                                         │
                        │  Σ I_in  =  Σ I_out                    │
                        │                                         │
                        │  حيث:                                  │
                        │  I_in  : التيارات الداخلة ← ●         │
                        │  I_out : التيارات الخارجة → ○         │
                        │                                         │
                        │  ∑I_in → [Node] → ∑I_out               │
                        └─────────────────────────────────────────┘
                    </div>
                    <p class="card-content">مجموع التيارات الداخلة إلى عقدة يساوي مجموع التيارات الخارجة منها. يعتمد على حفظ الشحنة.</p>
                    <span class="source-badge">File 5 - Pages 32-33</span>
                </div>
                
                <div class="card law-card">
                    <h3 class="card-title"><i class="fas fa-bolt"></i> قانون كيرشوف الثاني - حفظ الجهد</h3>
                    <div class="ascii-equation">
                        ┌─────────────────────────────────────────┐
                        │  Kirchhoff's Voltage Law (KVL)         │
                        │                                         │
                        │  Σ V = 0                               │
                        │                                         │
                        │  حول أي حلقة مغلقة:                   │
                        │                                         │
                        │  +V₁ - I₁R₁ - I₂R₂ + V₂ ... = 0        │
                        │                                         │
                        │  ▸ مع التيار: -IR ↓                    │
                        │  ▸ ضد التيار: +IR ↑                    │
                        └─────────────────────────────────────────┘
                    </div>
                    <p class="card-content">مجموع فروق الجهد حول أي حلقة مغلقة يساوي صفر. يعتمد على حفظ الطاقة.</p>
                    <span class="source-badge">File 5 - Pages 40-43</span>
                </div>
                
                <div class="card law-card">
                    <h3 class="card-title"><i class="fas fa-fire"></i> قانون جول - التأثير الحراري</h3>
                    <div class="ascii-equation">
                        ┌─────────────────────────────────────────┐
                        │  Joule's Law (Thermal Effect)          │
                        │                                         │
                        │  Q = I² × R × t                         │
                        │                                         │
                        │  حيث:                                  │
                        │  Q : الطاقة الحرارية (جول)            │
                        │  I : شدة التيار (أمبير)               │
                        │  R : المقاومة (أوم) Ω                  │
                        │  t : الزمن (ثانية)                     │
                        │                                         │
                        │  I → [R] → Heat (Q)                    │
                        └─────────────────────────────────────────┘
                    </div>
                    <p class="card-content">الطاقة الحرارية المتولدة في موصل تساوي مربع التيار مضروباً في المقاومة والزمن.</p>
                    <span class="source-badge">File 6 - Page 47</span>
                </div>
            </div>
        </section>

        <!-- ===== ملف 7-8 ===== -->
        <section id="file4" class="file-section">
            <div class="file-header">
                <h2 class="file-title"><i class="fas fa-wave-square"></i> ملفات 7-8: التيار المتردد والضوء والبصريات</h2>
                <p class="file-desc">استخراج شامل للاستخدامات، التطبيقات، والقوانين من ملفات الفيزياء المتعلقة بالتيار المتردد والضوء والبصريات</p>
            </div>

            <!-- اختيار اللغة لملف 7-8 -->
            <div class="language-toggle">
                <button class="lang-btn active" onclick="showLang('file4-ar')">العربية</button>
                <button class="lang-btn" onclick="showLang('file4-en')">English</button>
            </div>

            <!-- المحتوى العربي -->
            <div id="file4-ar" class="lang-content active">
                <h2 class="section-title"><i class="fas fa-plug"></i> الاستخدامات</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-bolt"></i> استخدامات التيار المستمر (DC)</h3>
                        <div class="card-content">
                            <p>تستخدم في:</p>
                            <ul class="card-list">
                                <li>الأجهزة الإلكترونية</li>
                                <li>أنظمة الشحن</li>
                                <li>أنظمة الطاقة المتجددة</li>
                            </ul>
                            <div class="card-highlight">المعتمد عليه: مصدر الطاقة الثابت والموثوق</div>
                            <span class="source-badge">7فيزياء معدل.pdf - الصفحة 61</span>
                        </div>
                    </div>
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-charging-station"></i> استخدامات التيار المتردد (AC)</h3>
                        <div class="card-content">
                            <p>تستخدم في:</p>
                            <ul class="card-list">
                                <li>شبكات الكهرباء</li>
                                <li>المحركات الكهربائية</li>
                                <li>أنظمة الإضاءة</li>
                            </ul>
                            <div class="card-highlight">المعتمد عليه: كفاءة النقل والتحويل عبر المحولات</div>
                            <span class="source-badge">7فيزياء معدل.pdf - الصفحة 62</span>
                        </div>
                    </div>
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-stethoscope"></i> الاستخدامات الطبية</h3>
                        <div class="card-content">
                            <p>تستخدم في:</p>
                            <ul class="card-list">
                                <li>أجهزة تخطيط القلب (ECG)</li>
                                <li>التصوير بالرنين المغناطيسي (MRI)</li>
                                <li>التحفيز الكهربائي للأعصاب والعضلات</li>
                            </ul>
                            <div class="card-highlight">المعتمد عليه: خصائص التيار الكهربائي وتأثيراته الفسيولوجية</div>
                            <span class="source-badge">7فيزياء معدل.pdf - الصفحة 63</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-microchip"></i> التطبيقات</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-solar-panel"></i> تطبيقات توليد التيار المتردد</h3>
                        <div class="card-content">
                            <p>تطبيقات في:</p>
                            <ul class="card-list">
                                <li>المولدات التقليدية (الوقود الأحفوري، الكهرومائية)</li>
                                <li>مصادر الطاقة المتجددة (الرياح، الشمسية باستخدام العواكس)</li>
                                <li>الأنظمة النووية</li>
                            </ul>
                            <div class="card-highlight">المعتمد عليه: التحويل الميكانيكي إلى طاقة كهربائية عبر الحث الكهرومغناطيسي</div>
                            <span class="source-badge">7فيزياء معدل.pdf - الصفحات 64-66</span>
                        </div>
                    </div>
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-satellite-dish"></i> تطبيقات المعاوقة (Impedance)</h3>
                        <div class="card-content">
                            <p>تطبيقات في:</p>
                            <ul class="card-list">
                                <li>تصميم الدوائر الكهربائية</li>
                                <li>تحسين أداء الأجهزة</li>
                                <li>أنظمة الطاقة الكهربائية</li>
                            </ul>
                            <div class="card-highlight">المعتمد عليه: تحليل الدوائر وتقليل فقدان الطاقة</div>
                            <span class="source-badge">7فيزياء معدل.pdf - الصفحات 70-71</span>
                        </div>
                    </div>
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-eye"></i> تطبيقات الأجهزة البصرية</h3>
                        <div class="card-content">
                            <p>تطبيقات في:</p>
                            <ul class="card-list">
                                <li>المجاهر الضوئية والإلكترونية (دراسة الخلايا والأنسجة)</li>
                                <li>التلسكوبات الكاسرة والعاكسة (الرصد الفلكي)</li>
                                <li>الأجهزة الطبية (المناظير الداخلية، منظار البطن)</li>
                            </ul>
                            <div class="card-highlight">المعتمد عليه: مبادئ انعكاس وانكسار الضوء والخصائص البصرية</div>
                            <span class="source-badge">تابع 8فيزياء معدل.pdf - الصفحات 106-110</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-calculator"></i> القوانين</h2>
                <div class="cards-container">
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-wave-square"></i> معادلة التيار المتردد</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <span class="law-label">الموجة الجيبية:</span>
                                <div class="law-equation law-unicode">
                                    V(t) = V<sub>max</sub> · sin(2πft)
                                </div>
                                <p>حيث:</p>
                                <p>V(t) = الجهد عند الزمن t</p>
                                <p>V<sub>max</sub> = أقصى جهد</p>
                                <p>f = التردد (هرتز)</p>
                                <p>t = الزمن (ثانية)</p>
                            </div>
                            <div class="card-highlight">تصف تغير الجهد مع الزمن في التيار المتردد</div>
                            <span class="source-badge">7فيزياء معدل.pdf - الصفحة 63</span>
                        </div>
                    </div>
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-resistance"></i> المعاوقة والمقاومة التفاعلية</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <span class="law-label">المقاومة التفاعلية السعوية:</span>
                                <div class="law-equation law-unicode">
                                    X<sub>C</sub> = 1 / (2πfC)
                                </div>
                                
                                <span class="law-label">المقاومة التفاعلية الحثية:</span>
                                <div class="law-equation law-unicode">
                                    X<sub>L</sub> = 2πfL
                                </div>
                                
                                <span class="law-label">المعاوقة الكلية:</span>
                                <div class="law-equation law-unicode">
                                    Z = R + j(X<sub>L</sub> - X<sub>C</sub>)
                                </div>
                                
                                <p>حيث:</p>
                                <p>X<sub>C</sub> = المقاومة التفاعلية للسعة (أوم)</p>
                                <p>X<sub>L</sub> = المقاومة التفاعلية للمحث (أوم)</p>
                                <p>R = المقاومة الأومية (أوم)</p>
                                <p>f = التردد (هرتز)</p>
                                <p>C = السعة (فاراد)</p>
                                <p>L = المحاثة (هنري)</p>
                                <p>j = الوحدة التخيلية (√-1)</p>
                            </div>
                            <span class="source-badge">7فيزياء معدل.pdf - الصفحات 68-69</span>
                        </div>
                    </div>
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-ruler"></i> قانون سنيل للانكسار</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <span class="law-label">قانون سنيل:</span>
                                <div class="law-equation law-unicode">
                                    n₁ · sin(θ₁) = n₂ · sin(θ₂)
                                </div>
                                
                                <span class="law-label">الزاوية الحرجة:</span>
                                <div class="law-equation law-unicode">
                                    sin(θ<sub>c</sub>) = n₂ / n₁
                                </div>
                                
                                <span class="law-label">معامل الانكسار:</span>
                                <div class="law-equation law-unicode">
                                    n = c / v
                                </div>
                                
                                <p>حيث:</p>
                                <p>n₁, n₂ = معاملي الانكسار للوسطين</p>
                                <p>θ₁ = زاوية السقوط</p>
                                <p>θ₂ = زاوية الانكسار</p>
                                <p>θ<sub>c</sub> = الزاوية الحرجة</p>
                                <p>c = سرعة الضوء في الفراغ (≈ 3×10⁸ م/ث)</p>
                                <p>v = سرعة الضوء في الوسط</p>
                            </div>
                            <span class="source-badge">8فيزياء معدل.pdf - الصفحات 98-99</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- المحتوى الإنجليزي -->
            <div id="file4-en" class="lang-content">
                <h2 class="section-title"><i class="fas fa-plug"></i> Uses</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-bolt"></i> Direct Current (DC) Uses</h3>
                        <div class="card-content">
                            <p>Used in:</p>
                            <ul class="card-list">
                                <li>Electronic devices</li>
                                <li>Charging systems</li>
                                <li>Renewable energy systems</li>
                            </ul>
                            <div class="card-highlight">Relies on: Stable and reliable power source</div>
                            <span class="source-badge">7physics adjusted.pdf - Page 61</span>
                        </div>
                    </div>
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-charging-station"></i> Alternating Current (AC) Uses</h3>
                        <div class="card-content">
                            <p>Used in:</p>
                            <ul class="card-list">
                                <li>Electrical grids</li>
                                <li>Electric motors</li>
                                <li>Lighting systems</li>
                            </ul>
                            <div class="card-highlight">Relies on: Efficient transmission and conversion via transformers</div>
                            <span class="source-badge">7physics adjusted.pdf - Page 62</span>
                        </div>
                    </div>
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-stethoscope"></i> Medical Uses</h3>
                        <div class="card-content">
                            <p>Used in:</p>
                            <ul class="card-list">
                                <li>Electrocardiogram (ECG) devices</li>
                                <li>Magnetic Resonance Imaging (MRI)</li>
                                <li>Electrical stimulation of nerves and muscles</li>
                            </ul>
                            <div class="card-highlight">Relies on: Electrical current properties and physiological effects</div>
                            <span class="source-badge">7physics adjusted.pdf - Page 63</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-microchip"></i> Applications</h2>
                <div class="cards-container">
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-solar-panel"></i> AC Generation Applications</h3>
                        <div class="card-content">
                            <p>Applications in:</p>
                            <ul class="card-list">
                                <li>Conventional generators (fossil fuels, hydroelectric)</li>
                                <li>Renewable sources (wind, solar with inverters)</li>
                                <li>Nuclear systems</li>
                            </ul>
                            <div class="card-highlight">Relies on: Mechanical to electrical energy conversion via electromagnetic induction</div>
                            <span class="source-badge">7physics adjusted.pdf - Pages 64-66</span>
                        </div>
                    </div>
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-satellite-dish"></i> Impedance Applications</h3>
                        <div class="card-content">
                            <p>Applications in:</p>
                            <ul class="card-list">
                                <li>Electrical circuit design</li>
                                <li>Device performance improvement</li>
                                <li>Power systems</li>
                            </ul>
                            <div class="card-highlight">Relies on: Circuit analysis and reducing energy losses</div>
                            <span class="source-badge">7physics adjusted.pdf - Pages 70-71</span>
                        </div>
                    </div>
                    <div class="card">
                        <h3 class="card-title"><i class="fas fa-eye"></i> Optical Devices Applications</h3>
                        <div class="card-content">
                            <p>Applications in:</p>
                            <ul class="card-list">
                                <li>Optical and electron microscopes (cell and tissue study)</li>
                                <li>Refracting and reflecting telescopes (astronomical observation)</li>
                                <li>Medical devices (endoscopes, laparoscopes)</li>
                            </ul>
                            <div class="card-highlight">Relies on: Principles of light reflection, refraction, and optical properties</div>
                            <span class="source-badge">Follow-up 8physics adjusted.pdf - Pages 106-110</span>
                        </div>
                    </div>
                </div>

                <h2 class="section-title"><i class="fas fa-calculator"></i> Laws</h2>
                <div class="cards-container">
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-wave-square"></i> Alternating Current Equation</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <span class="law-label">Sinusoidal Wave:</span>
                                <div class="law-equation law-unicode">
                                    V(t) = V<sub>max</sub> · sin(2πft)
                                </div>
                                <p>Where:</p>
                                <p>V(t) = Voltage at time t</p>
                                <p>V<sub>max</sub> = Maximum voltage</p>
                                <p>f = Frequency (Hz)</p>
                                <p>t = Time (seconds)</p>
                            </div>
                            <div class="card-highlight">Describes voltage variation over time in AC</div>
                            <span class="source-badge">7physics adjusted.pdf - Page 63</span>
                        </div>
                    </div>
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-resistance"></i> Impedance and Reactance</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <span class="law-label">Capacitive Reactance:</span>
                                <div class="law-equation law-unicode">
                                    X<sub>C</sub> = 1 / (2πfC)
                                </div>
                                
                                <span class="law-label">Inductive Reactance:</span>
                                <div class="law-equation law-unicode">
                                    X<sub>L</sub> = 2πfL
                                </div>
                                
                                <span class="law-label">Total Impedance:</span>
                                <div class="law-equation law-unicode">
                                    Z = R + j(X<sub>L</sub> - X<sub>C</sub>)
                                </div>
                                
                                <p>Where:</p>
                                <p>X<sub>C</sub> = Capacitive reactance (Ohms)</p>
                                <p>X<sub>L</sub> = Inductive reactance (Ohms)</p>
                                <p>R = Resistance (Ohms)</p>
                                <p>f = Frequency (Hz)</p>
                                <p>C = Capacitance (Farads)</p>
                                <p>L = Inductance (Henries)</p>
                                <p>j = Imaginary unit (√-1)</p>
                            </div>
                            <span class="source-badge">7physics adjusted.pdf - Pages 68-69</span>
                        </div>
                    </div>
                    <div class="card law-card">
                        <h3 class="card-title"><i class="fas fa-ruler"></i> Snell's Law of Refraction</h3>
                        <div class="card-content">
                            <div class="law-box">
                                <span class="law-label">Snell's Law:</span>
                                <div class="law-equation law-unicode">
                                    n₁ · sin(θ₁) = n₂ · sin(θ₂)
                                </div>
                                
                                <span class="law-label">Critical Angle:</span>
                                <div class="law-equation law-unicode">
                                    sin(θ<sub>c</sub>) = n₂ / n₁
                                </div>
                                
                                <span class="law-label">Refractive Index:</span>
                                <div class="law-equation law-unicode">
                                    n = c / v
                                </div>
                                
                                <p>Where:</p>
                                <p>n₁, n₂ = Refractive indices of the two media</p>
                                <p>θ₁ = Angle of incidence</p>
                                <p>θ₂ = Angle of refraction</p>
                                <p>θ<sub>c</sub> = Critical angle</p>
                                <p>c = Speed of light in vacuum (≈ 3×10⁸ m/s)</p>
                                <p>v = Speed of light in the medium</p>
                            </div>
                            <span class="source-badge">8physics adjusted.pdf - Pages 98-99</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <footer>
            <p>تم استخراج المعلومات من جميع ملفات الفيزياء: من الملف 1 إلى الملف 8</p>
            <p style="margin-top: 10px;"><i class="far fa-copyright"></i> 2025 - تصميم متكامل مع دمج جميع أنماط CSS | جميع الحقوق محفوظة</p>
        </footer>
    </div>

    <script>
        // التنقل بين الملفات
        document.addEventListener('DOMContentLoaded', function() {
            const fileBtns = document.querySelectorAll('.file-btn');
            const fileSections = document.querySelectorAll('.file-section');
            
            fileBtns.forEach(btn => {
                btn.addEventListener('click', function() {
                    // تحديث الأزرار النشطة
                    fileBtns.forEach(b => b.classList.remove('active'));
                    this.classList.add('active');
                    
                    // إظهار القسم المحدد
                    const fileId = this.getAttribute('data-file');
                    fileSections.forEach(section => {
                        section.classList.remove('active');
                    });
                    document.getElementById(fileId).classList.add('active');
                    
                    // التمرير إلى الأعلى
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                });
            });
            
            // وظيفة تبديل اللغة
            window.showLang = function(langId) {
                // إخفاء جميع محتويات اللغة وإظهار المحدد فقط
                const allLangContents = document.querySelectorAll('.lang-content');
                allLangContents.forEach(content => {
                    content.classList.remove('active');
                });
                
                // إزالة النشط من جميع أزرار اللغة
                const allLangBtns = document.querySelectorAll('.lang-btn');
                allLangBtns.forEach(btn => {
                    btn.classList.remove('active');
                });
                
                // إظهار محتوى اللغة المحدد
                document.getElementById(langId).classList.add('active');
                
                // جعل زر اللغة المحدد نشط
                event.target.classList.add('active');
            };
            
            // إضافة تأثيرات التمرير للبطاقات
            const observerOptions = {
                threshold: 0.1,
                rootMargin: '0px 0px -50px 0px'
            };
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }
                });
            }, observerOptions);
            
            // تطبيق التأثير على البطاقات
            document.querySelectorAll('.card').forEach(card => {
                card.style.opacity = '0';
                card.style.transform = 'translateY(20px)';
                card.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(card);
            });
            
            // تأثيرات التمرير للعناصر
            document.querySelectorAll('.item').forEach(item => {
                item.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateX(5px)';
                });
                item.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateX(0)';
                });
            });
        });
    </script>
</body>
</html>
