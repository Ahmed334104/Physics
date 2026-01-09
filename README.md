<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>فرضيات العلماء في النظرية الذرية | Atomic Theory Hypotheses</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        :root {
            --primary: #1a237e;
            --secondary: #4fc3f7;
            --accent: #ff6f00;
            --light: #f5f5f5;
            --dark: #0d1b2a;
            --success: #2e7d32;
            --card-bg: #ffffff;
            --shadow: 0 10px 20px rgba(0,0,0,0.1);
            --radius: 12px;
            --transition: all 0.3s ease;
        }
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #e4edf5 100%);
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
            padding-bottom: 40px;
        }
        header {
            background: linear-gradient(90deg, var(--primary) 0%, #283593 100%);
            color: white;
            padding: 2rem 1.5rem;
            text-align: center;
            border-bottom: 5px solid var(--accent);
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }
        header::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 30px 30px;
            opacity: 0.3;
            z-index: 0;
        }
        header h1, header h2 {
            position: relative;
            z-index: 1;
        }
        header h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            letter-spacing: 1px;
        }
        header h2 {
            font-size: 1.4rem;
            font-weight: 300;
            opacity: 0.9;
        }
        .language-toggle {
            position: absolute;
            top: 20px;
            left: 20px;
            z-index: 2;
        }
        .lang-btn {
            background: rgba(255,255,255,0.2);
            border: none;
            color: white;
            padding: 8px 16px;
            border-radius: 20px;
            cursor: pointer;
            font-weight: bold;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .lang-btn:hover {
            background: rgba(255,255,255,0.3);
        }
        .container {
            max-width: 1400px;
            margin: 30px auto;
            padding: 0 20px;
        }
        .filter-bar {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            justify-content: center;
            margin-bottom: 30px;
            padding: 15px;
            background: var(--card-bg);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
        }
        .filter-btn {
            padding: 8px 16px;
            border: 2px solid var(--primary);
            background: transparent;
            color: var(--primary);
            border-radius: 50px;
            cursor: pointer;
            font-weight: bold;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 0.85rem;
            white-space: nowrap;
        }
        .filter-btn:hover, .filter-btn.active {
            background: var(--primary);
            color: white;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(26, 35, 126, 0.3);
        }
        .filter-btn i {
            font-size: 0.9rem;
        }
        .scientist-cards {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 25px;
        }
        .card {
            background: var(--card-bg);
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            border-top: 5px solid var(--secondary);
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.6s forwards;
        }
        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.15);
        }
        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        .card-header {
            background: linear-gradient(90deg, var(--secondary) 0%, #29b6f6 100%);
            color: var(--dark);
            padding: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .card-header h3 {
            font-size: 1.4rem;
            margin-bottom: 5px;
        }
        .card-header .timeline {
            font-size: 0.8rem;
            background: rgba(0,0,0,0.1);
            padding: 4px 10px;
            border-radius: 20px;
            font-weight: bold;
        }
        .card-content {
            padding: 20px;
        }
        .card-content h4 {
            color: var(--primary);
            margin-bottom: 12px;
            font-size: 1.2rem;
            border-bottom: 2px dashed #e0e0e0;
            padding-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        .card-content h4 i {
            color: var(--accent);
        }
        .hypotheses-list {
            list-style-type: none;
        }
        .hypotheses-list li {
            padding: 10px 0;
            border-bottom: 1px solid #eee;
            position: relative;
            padding-right: 20px;
        }
        .hypotheses-list li:before {
            content: '•';
            color: var(--accent);
            font-weight: bold;
            font-size: 1.3rem;
            position: absolute;
            right: 0;
            top: 8px;
        }
        .hypotheses-list li:last-child {
            border-bottom: none;
        }
        .lang-ar {
            font-weight: bold;
            color: var(--primary);
            font-size: 0.95rem;
        }
        .lang-en {
            font-style: italic;
            color: #555;
            margin-top: 4px;
            font-size: 0.85rem;
            border-right: 2px solid #e0e0e0;
            padding-right: 8px;
        }
        .empty-state {
            grid-column: 1 / -1;
            text-align: center;
            padding: 50px 20px;
            background: var(--card-bg);
            border-radius: var(--radius);
            box-shadow: var(--shadow);
        }
        .empty-state i {
            font-size: 3rem;
            color: var(--secondary);
            margin-bottom: 15px;
        }
        .empty-state h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        footer {
            text-align: center;
            margin-top: 40px;
            padding: 20px;
            color: #666;
            font-size: 0.85rem;
        }
        .chemical-elements {
            display: flex;
            justify-content: center;
            gap: 8px;
            margin-top: 10px;
            flex-wrap: wrap;
        }
        .element {
            width: 35px;
            height: 35px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            font-weight: bold;
            border-radius: 6px;
            font-size: 0.75rem;
            box-shadow: 0 3px 6px rgba(0,0,0,0.1);
        }
        .timeline-bar {
            height: 4px;
            background: linear-gradient(90deg, #4CAF50, #2196F3, #FF9800, #E91E63);
            margin: 20px 0;
            border-radius: 2px;
            position: relative;
        }
        @media (max-width: 768px) {
            header h1 { font-size: 1.8rem; }
            header h2 { font-size: 1rem; }
            .scientist-cards { grid-template-columns: 1fr; }
            .filter-bar { flex-direction: column; align-items: center; }
            .filter-btn { width: 100%; justify-content: center; }
            .language-toggle { position: static; margin-bottom: 15px; display: flex; justify-content: center; }
            .card-header { flex-direction: column; text-align: center; gap: 10px; }
        }
    </style>
</head>
<body>
    <header>
        <div class="language-toggle">
            <button class="lang-btn" id="toggleLang">
                <i class="fas fa-language"></i> 
                <span>عربي / English</span>
            </button>
        </div>
        <h1>فرضيات العلماء في النظرية الذرية</h1>
        <h2>Atomic Theory Hypotheses</h2>
        <div class="chemical-elements">
            <div class="element">H</div>
            <div class="element">He</div>
            <div class="element">Li</div>
            <div class="element">Be</div>
            <div class="element">e⁻</div>
            <div class="element">p⁺</div>
            <div class="element">n⁰</div>
            <div class="element">α</div>
        </div>
    </header>

    <div class="container">
        <div class="timeline-bar"></div>
        
        <div class="filter-bar">
            <button class="filter-btn active" data-scientist="all">
                <i class="fas fa-atom"></i> جميع العلماء | All
            </button>
            <button class="filter-btn" data-scientist="Democritus">
                <i class="fas fa-history"></i> ديموقريطس | Democritus
            </button>
            <button class="filter-btn" data-scientist="Aristotle">
                <i class="fas fa-fire"></i> أرسطو | Aristotle
            </button>
            <button class="filter-btn" data-scientist="Dalton">
                <i class="fas fa-solid fa-circle"></i> دالتون | Dalton
            </button>
            <button class="filter-btn" data-scientist="Thomson">
                <i class="fas fa-bread-slice"></i> طومسون | Thomson
            </button>
            <button class="filter-btn" data-scientist="Rutherford">
                <i class="fas fa-sun"></i> رذرفورد | Rutherford
            </button>
            <button class="filter-btn" data-scientist="Bohr">
                <i class="fas fa-satellite"></i> بور | Bohr
            </button>
            <button class="filter-btn" data-scientist="Sommerfeld">
                <i class="fas fa-ellipsis"></i> زومرفيلد | Sommerfeld
            </button>
            <button class="filter-btn" data-scientist="DeBroglie">
                <i class="fas fa-wave-square"></i> دي برولي | De Broglie
            </button>
            <button class="filter-btn" data-scientist="Heisenberg">
                <i class="fas fa-question-circle"></i> هايزنبرغ | Heisenberg
            </button>
            <button class="filter-btn" data-scientist="Schrodinger">
                <i class="fas fa-cloud"></i> شرودنغر | Schrödinger
            </button>
            <button class="filter-btn" data-scientist="Maxwell">
                <i class="fas fa-radiation"></i> ماكسويل | Maxwell
            </button>
        </div>

        <div class="scientist-cards" id="cardsContainer">
            <!-- Cards will be generated by JavaScript -->
        </div>
    </div>

    <footer>
        <p>تم استخراج الفرضيات من كتاب "الكيمياء" | Hypotheses extracted from "Chemistry" book</p>
        <p>تصميم تفاعلي ثنائي اللغة | Bilingual Interactive Design</p>
        <div class="chemical-elements">
            <div class="element">Na</div>
            <div class="element">Cl</div>
            <div class="element">Au</div>
            <div class="element">Fe</div>
            <div class="element">C</div>
            <div class="element">O</div>
            <div class="element">U</div>
            <div class="element">Pb</div>
        </div>
    </footer>

    <script>
        // البيانات: فرضيات كل عالم من الكتاب
        const scientistsData = [
            {
                id: "Democritus",
                name: "ديموقريطس | Democritus",
                timeline: "400 ق.م | 400 BC",
                hypotheses: [
                    "المادة تتكون من وحدات غير قابلة للتجزئة تسمى 'الذرات' | Matter consists of indivisible units called 'atoms'",
                    "الذرة (atomos) تعني غير قابل للتقسيم | Atom (atomos) means indivisible",
                    "إذا قسمت المادة باستمرار ستصل إلى نقطة لا يمكن تقسيمها بعدها | If you keep dividing matter, you'll reach a point where it can't be divided further"
                ]
            },
            {
                id: "Aristotle",
                name: "أرسطو | Aristotle",
                timeline: "350 ق.م | 350 BC",
                hypotheses: [
                    "المادة تتكون من أربعة عناصر: الأرض، النار، الماء، الهواء | Matter consists of four elements: earth, fire, water, air",
                    "نظريته استمرت لمدة 2000 سنة على الرغم من خطئها | His theory persisted for 2000 years despite being wrong"
                ]
            },
            {
                id: "Dalton",
                name: "جون دالتون | John Dalton",
                timeline: "1800s",
                hypotheses: [
                    "الذرات كرات صلبة غير قابلة للتجزئة | Atoms are solid, indivisible spheres",
                    "جميع ذرات العنصر الواحد متطابقة في الحجم، الكتلة، الشكل | All atoms of an element are identical in size, mass, shape",
                    "ذرات العناصر المختلفة تختلف في الحجم، الكتلة، الخواص الكيميائية | Atoms of different elements differ in size, mass, chemical properties",
                    "الذرات تتحد لتكون المركبات بنسب محددة | Atoms combine to form compounds in fixed ratios"
                ]
            },
            {
                id: "Thomson",
                name: "ج.ج. طومسون | J.J. Thomson",
                timeline: "1890s",
                hypotheses: [
                    "اكتشف الإلكترون من خلال تجارب أنابيب أشعة الكاثود | Discovered electron through cathode ray experiments",
                    "الذرة كرة موجبة الشحنة موزعة فيها الإلكترونات بشكل منتظم | Atom is a positively charged sphere with uniformly distributed electrons",
                    "نموذج 'بودنج الخوخ' أو 'البطيخ' | 'Plum pudding' or 'watermelon' model",
                    "الإلكترونات جسيمات سالبة الشحنة | Electrons are negatively charged particles"
                ]
            },
            {
                id: "Rutherford",
                name: "إرنست رذرفورد | Ernest Rutherford",
                timeline: "1911",
                hypotheses: [
                    "معظم حجم الذرة فراغ | Most of the atom's volume is empty space",
                    "الشحنة الموجبة مركزة في نواة صغيرة جداً في المركز | Positive charge is concentrated in a very small nucleus at the center",
                    "الإلكترونات تدور حول النواة مثل الكواكب حول الشمس | Electrons revolve around the nucleus like planets around the sun",
                    "معظم كتلة الذرة متركزة في النواة | Most of the atom's mass is concentrated in the nucleus"
                ]
            },
            {
                id: "Bohr",
                name: "نيلز بور | Niels Bohr",
                timeline: "1913",
                hypotheses: [
                    "الإلكترونات تدور في مستويات طاقة محددة (مدارات) | Electrons orbit in specific energy levels (orbits)",
                    "لا تشع الإلكترونات طاقة أثناء وجودها في المدارات الثابتة | Electrons do not radiate energy while in stable orbits",
                    "تنتقل الإلكترونات بين المدارات بامتصاص أو إشعاع كم محدد من الطاقة | Electrons jump between orbits by absorbing/emitting quanta of energy",
                    "توجد سبعة مستويات طاقة رئيسية (K, L, M, N, O, P, Q) | There are seven principal energy levels"
                ]
            },
            {
                id: "Sommerfeld",
                name: "أرنولد زومرفيلد | Arnold Sommerfeld",
                timeline: "1916",
                hypotheses: [
                    "أضاف مدارات إهليلجية بجانب المدارات الدائرية | Added elliptical orbits alongside circular ones",
                    "كل مستوى طاقة رئيسي يحتوي على مستويات فرعية | Each principal energy level contains sublevels",
                    "أدخل عدد الكم الثانوي (l) لوصف شكل المدار | Introduced azimuthal quantum number (l) to describe orbital shape",
                    "سرعة الإلكترون تتغير حسب بعده عن النواة | Electron speed varies with distance from nucleus"
                ]
            },
            {
                id: "DeBroglie",
                name: "لويس دي برولي | Louis de Broglie",
                timeline: "1924",
                hypotheses: [
                    "الإلكترون له طبيعة مزدوجة: جسيمية وموجية | Electron has dual nature: particle and wave",
                    "كل جسم متحرك يصاحبه موجة مادية | Every moving body is accompanied by a matter wave",
                    "الطول الموجي = ثابت بلانك ÷ (الكتلة × السرعة) | Wavelength = Planck's constant ÷ (mass × velocity)",
                    "موجات المادة تختلف عن الموجات الكهرومغناطيسية | Matter waves differ from electromagnetic waves"
                ]
            },
            {
                id: "Heisenberg",
                name: "فيرنر هايزنبرغ | Werner Heisenberg",
                timeline: "1927",
                hypotheses: [
                    "مبدأ عدم التأكد: لا يمكن تحديد موقع وسرعة الإلكترون بدقة في نفس الوقت | Uncertainty principle: Cannot determine position and velocity of electron simultaneously",
                    "كلما زادت دقة تحديد الموقع قلت دقة تحديد السرعة والعكس | More precise position means less precise velocity and vice versa",
                    "يتم وصف الإلكترون بسحابة إلكترونية بدلاً من مدارات دقيقة | Electron described by electron cloud rather than precise orbits"
                ]
            },
            {
                id: "Schrodinger",
                name: "إرفين شرودنغر | Erwin Schrödinger",
                timeline: "1926",
                hypotheses: [
                    "معادلة شرودنغر الموجية تصف حركة الإلكترون الموجية | Schrödinger's wave equation describes electron's wave motion",
                    "تحدد المساحات الأكثر احتمالاً لوجود الإلكترون | Determines regions where electron is most likely to be found",
                    "السحابة الإلكترونية تمثل منطقة احتمال وجود الإلكترون | Electron cloud represents region of electron probability",
                    "المدار هو منطقة داخل السحابة الإلكترونية ذات احتمال عالي لوجود الإلكترون | Orbital is area within electron cloud with high electron probability"
                ]
            },
            {
                id: "Maxwell",
                name: "جيمس كليرك ماكسويل | James Clerk Maxwell",
                timeline: "1860s",
                hypotheses: [
                    "إذا تحرك إلكترون مشحون حول جسيم مضاد له في الشحنة، يفقد جزءاً من طاقته كإشعاع | If a charged electron moves around an oppositely charged particle, it loses energy as radiation",
                    "هذا الفقدان في الطاقة سيجعل الإلكترون يقع في النواة مما يتعارض مع ملاحظات الاستقرار الذري | This energy loss would cause electron to fall into nucleus, contradicting atomic stability",
                    "نظريته أظهرت عيباً في نموذج رذرفورد | His theory showed a flaw in Rutherford's model"
                ]
            }
        ];

        // توليد البطاقات
        const cardsContainer = document.getElementById('cardsContainer');
        const filterButtons = document.querySelectorAll('.filter-btn');
        const toggleLangBtn = document.getElementById('toggleLang');
        let currentLanguage = 'ar'; // ar or en

        function generateCards(scientistId = 'all') {
            cardsContainer.innerHTML = '';
            const filteredScientists = scientistId === 'all' 
                ? scientistsData 
                : scientistsData.filter(s => s.id === scientistId);

            if (filteredScientists.length === 0) {
                cardsContainer.innerHTML = `
                    <div class="empty-state">
                        <i class="fas fa-flask"></i>
                        <h3>لم يتم العثور على فرضيات | No Hypotheses Found</h3>
                        <p>الرجاء اختيار عالم آخر | Please select another scientist</p>
                    </div>
                `;
                return;
            }

            filteredScientists.forEach((scientist, index) => {
                const card = document.createElement('div');
                card.className = 'card';
                card.style.animationDelay = `${index * 0.1}s`;

                // إعداد النص حسب اللغة
                let nameDisplay = currentLanguage === 'ar' 
                    ? scientist.name.split(' | ')[0] 
                    : scientist.name.split(' | ')[1];
                
                let timelineDisplay = currentLanguage === 'ar'
                    ? scientist.timeline.split(' | ')[0]
                    : scientist.timeline.split(' | ')[1];

                let hypothesesList = '';
                scientist.hypotheses.forEach(hyp => {
                    const [ar, en] = hyp.split(' | ');
                    hypothesesList += `
                        <li>
                            <div class="lang-ar">${currentLanguage === 'ar' ? ar : en}</div>
                            <div class="lang-en">${currentLanguage === 'ar' ? en : ar}</div>
                        </li>
                    `;
                });

                // اختيار أيقونة خاصة بكل عالم
                let iconClass = 'fas fa-user';
                switch(scientist.id) {
                    case 'Democritus': iconClass = 'fas fa-history'; break;
                    case 'Aristotle': iconClass = 'fas fa-fire'; break;
                    case 'Dalton': iconClass = 'fas fa-circle'; break;
                    case 'Thomson': iconClass = 'fas fa-bread-slice'; break;
                    case 'Rutherford': iconClass = 'fas fa-sun'; break;
                    case 'Bohr': iconClass = 'fas fa-satellite'; break;
                    case 'Sommerfeld': iconClass = 'fas fa-ellipsis-h'; break;
                    case 'DeBroglie': iconClass = 'fas fa-wave-square'; break;
                    case 'Heisenberg': iconClass = 'fas fa-question-circle'; break;
                    case 'Schrodinger': iconClass = 'fas fa-cloud'; break;
                    case 'Maxwell': iconClass = 'fas fa-radiation'; break;
                }

                card.innerHTML = `
                    <div class="card-header">
                        <div>
                            <h3>${nameDisplay}</h3>
                            <div class="timeline">${timelineDisplay}</div>
                        </div>
                        <i class="${iconClass}" style="font-size: 1.8rem; opacity: 0.8;"></i>
                    </div>
                    <div class="card-content">
                        <h4><i class="fas fa-hypothesis"></i> الفرضيات | Hypotheses</h4>
                        <ul class="hypotheses-list">
                            ${hypothesesList}
                        </ul>
                    </div>
                `;
                cardsContainer.appendChild(card);
            });
        }

        // تفعيل فلترة العلماء
        filterButtons.forEach(button => {
            button.addEventListener('click', function() {
                filterButtons.forEach(btn => btn.classList.remove('active'));
                this.classList.add('active');
                const scientistId = this.getAttribute('data-scientist');
                generateCards(scientistId);
            });
        });

        // تبديل اللغة
        toggleLangBtn.addEventListener('click', function() {
            currentLanguage = currentLanguage === 'ar' ? 'en' : 'ar';
            const activeBtn = document.querySelector('.filter-btn.active');
            const scientistId = activeBtn.getAttribute('data-scientist');
            
            // تحديث نص زر التبديل
            const toggleText = currentLanguage === 'ar' ? 'عربي / English' : 'English / عربي';
            toggleLangBtn.innerHTML = `<i class="fas fa-language"></i> <span>${toggleText}</span>`;
            
            // تحديث العناوين
            document.querySelector('header h1').textContent = currentLanguage === 'ar' 
                ? 'فرضيات العلماء في النظرية الذرية' 
                : 'Atomic Theory Hypotheses';
            
            document.querySelector('header h2').textContent = currentLanguage === 'ar' 
                ? 'Atomic Theory Hypotheses' 
                : 'فرضيات العلماء في النظرية الذرية';
            
            // تحديث نص أزرار الفلترة
            const buttonTexts = {
                'all': ['جميع العلماء | All', 'All | جميع العلماء'],
                'Democritus': ['ديموقريطس | Democritus', 'Democritus | ديموقريطس'],
                'Aristotle': ['أرسطو | Aristotle', 'Aristotle | أرسطو'],
                'Dalton': ['دالتون | Dalton', 'Dalton | دالتون'],
                'Thomson': ['طومسون | Thomson', 'Thomson | طومسون'],
                'Rutherford': ['رذرفورد | Rutherford', 'Rutherford | رذرفورد'],
                'Bohr': ['بور | Bohr', 'Bohr | بور'],
                'Sommerfeld': ['زومرفيلد | Sommerfeld', 'Sommerfeld | زومرفيلد'],
                'DeBroglie': ['دي برولي | De Broglie', 'De Broglie | دي برولي'],
                'Heisenberg': ['هايزنبرغ | Heisenberg', 'Heisenberg | هايزنبرغ'],
                'Schrodinger': ['شرودنغر | Schrödinger', 'Schrödinger | شرودنغر'],
                'Maxwell': ['ماكسويل | Maxwell', 'Maxwell | ماكسويل']
            };
            
            filterButtons.forEach(btn => {
                const scientist = btn.getAttribute('data-scientist');
                const iconClass = btn.querySelector('i').className;
                const textIndex = currentLanguage === 'ar' ? 0 : 1;
                const text = buttonTexts[scientist][textIndex];
                btn.innerHTML = `<i class="${iconClass}"></i> ${text}`;
            });
            
            // تحديث الفوتر
            document.querySelectorAll('footer p')[0].textContent = currentLanguage === 'ar' 
                ? 'تم استخراج الفرضيات من كتاب "الكيمياء" | Hypotheses extracted from "Chemistry" book' 
                : 'Hypotheses extracted from "Chemistry" book | تم استخراج الفرضيات من كتاب "الكيمياء"';
            
            document.querySelectorAll('footer p')[1].textContent = currentLanguage === 'ar' 
                ? 'تصميم تفاعلي ثنائي اللغة | Bilingual Interactive Design' 
                : 'Bilingual Interactive Design | تصميم تفاعلي ثنائي اللغة';
            
            generateCards(scientistId);
        });

        // التهيئة الأولية
        generateCards('all');
    </script>
</body>
</html>
