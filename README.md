# my-site25
מינדי &amp; מנחם הספירה לאחור!!!!!!
[gemini-code-1780943676518.html](https://github.com/user-attachments/files/28725781/gemini-code-1780943676518.html)
<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>הספירה לאחור | מנחם & מינדי</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Assistant:wght@300;400;600&family=Playfair+Display+SC:wght@700&family=Frank+Ruhl+Libre:wght@300;500;700;900&display=swap');

        :root {
            --gold-light: #F9F1CC;
            --gold-main: #D4AF37;
            --gold-dark: #AA8C2C;
            --bg-dark: #0a0a0a;
            --bg-panel: rgba(20, 20, 20, 0.7);
            --glass-border: rgba(212, 175, 55, 0.3);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Assistant', sans-serif;
            background-color: var(--bg-dark);
            color: #fff;
            overflow-x: hidden;
            min-height: 100vh;
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            transition: background-image 1s ease;
        }

        /* Overlay to keep text readable if background image is changed */
        .site-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: radial-gradient(circle at 50% 0%, rgba(42, 37, 21, 0.8) 0%, rgba(10, 10, 10, 0.95) 80%);
            z-index: 0;
            pointer-events: none;
        }

        /* Floating Particles */
        .particles {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            background: radial-gradient(circle, var(--gold-light) 0%, transparent 70%);
            border-radius: 50%;
            opacity: 0.4;
            animation: float 10s infinite ease-in-out alternate;
        }

        @keyframes float {
            0% { transform: translateY(0) translateX(0) scale(1); opacity: 0.2; }
            100% { transform: translateY(-100px) translateX(50px) scale(1.5); opacity: 0.6; }
        }

        /* Hero Section */
        .hero {
            position: relative;
            z-index: 2;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 60px 20px 20px;
            text-align: center;
        }

        .image-wrapper {
            position: relative;
            width: 100%;
            max-width: 600px;
            border-radius: 200px 200px 10px 10px;
            padding: 10px;
            background: linear-gradient(135deg, var(--gold-main), transparent, var(--gold-dark));
            box-shadow: 0 20px 50px rgba(212, 175, 55, 0.15);
            animation: glow 4s infinite alternate;
        }

        @keyframes glow {
            0% { box-shadow: 0 20px 50px rgba(212, 175, 55, 0.1); }
            100% { box-shadow: 0 20px 80px rgba(212, 175, 55, 0.4); }
        }

        .hero img {
            width: 100%;
            border-radius: 190px 190px 8px 8px;
            display: block;
            filter: contrast(1.05) brightness(0.95);
        }

        h1 {
            font-family: 'Frank Ruhl Libre', serif;
            font-size: 4rem;
            font-weight: 900;
            margin-top: 30px;
            background: linear-gradient(to right, #BF953F, #FCF6BA, #B38728, #FBF5B7, #AA771C);
            -webkit-background-clip: text;
            color: transparent;
            text-shadow: 0px 4px 20px rgba(212, 175, 55, 0.2);
            letter-spacing: 2px;
        }

        /* Live Countdown */
        .countdown-container {
            display: flex;
            gap: 20px;
            margin: 30px 0 50px;
            justify-content: center;
        }

        .time-box {
            background: var(--bg-panel);
            backdrop-filter: blur(15px);
            border: 1px solid var(--glass-border);
            border-radius: 15px;
            padding: 20px 25px;
            min-width: 100px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .time-box span {
            display: block;
            font-family: 'Playfair Display SC', serif;
            font-size: 3.5rem;
            color: var(--gold-light);
            line-height: 1;
            text-shadow: 0 0 10px rgba(212, 175, 55, 0.5);
        }

        .time-box label {
            font-size: 1.1rem;
            color: #aaa;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-top: 10px;
            display: block;
        }

        /* 12 Days Grid */
        .container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto 80px;
            padding: 0 20px;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
        }

        .cube {
            background: var(--bg-panel);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.05);
            height: 180px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            border-radius: 20px;
            cursor: pointer;
            transition: all 0.5s cubic-bezier(0.25, 1, 0.5, 1);
            position: relative;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
        }

        .cube::before {
            content: '';
            position: absolute;
            top: 0; left: -100%; width: 50%; height: 100%;
            background: linear-gradient(to right, transparent, rgba(212, 175, 55, 0.2), transparent);
            transform: skewX(-25deg);
            transition: 0.7s;
        }

        .cube:hover:not(.locked) {
            transform: translateY(-10px) scale(1.03);
            border-color: var(--gold-main);
            box-shadow: 0 15px 30px rgba(212, 175, 55, 0.2), inset 0 0 20px rgba(212, 175, 55, 0.1);
        }

        .cube:hover:not(.locked)::before {
            left: 200%;
        }

        .cube-number {
            font-family: 'Frank Ruhl Libre', serif;
            font-size: 4rem;
            color: rgba(255, 255, 255, 0.1);
            -webkit-text-stroke: 1px var(--gold-main);
            transition: 0.4s;
        }

        .cube:hover:not(.locked) .cube-number {
            color: var(--gold-light);
            text-shadow: 0 0 15px rgba(212, 175, 55, 0.6);
            -webkit-text-stroke: 0px;
        }

        .cube-text {
            font-size: 1rem;
            color: #888;
            margin-top: 10px;
            letter-spacing: 2px;
            transition: 0.4s;
        }

        .cube:hover:not(.locked) .cube-text {
            color: var(--gold-main);
        }

        /* Locked Cube Style */
        .cube.locked {
            opacity: 0.3;
            cursor: not-allowed;
            filter: grayscale(100%);
            border: 1px solid rgba(255, 255, 255, 0.02);
            box-shadow: none;
        }
        
        .cube.locked .cube-text::after {
            content: ' (נעול)';
            font-size: 0.8rem;
        }

        /* Modals */
        .modal-overlay {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.4s ease, visibility 0.4s ease;
            z-index: 1000;
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-content {
            background: radial-gradient(circle at center, #1a1a1a, #050505);
            padding: 60px 50px;
            border-radius: 20px;
            max-width: 700px;
            width: 90%;
            text-align: center;
            border: 1px solid var(--gold-dark);
            box-shadow: 0 0 60px rgba(212, 175, 55, 0.15);
            transform: scale(0.8) translateY(30px);
            opacity: 0;
            transition: all 0.5s cubic-bezier(0.16, 1, 0.3, 1);
            position: relative;
        }

        .modal-overlay.active .modal-content {
            transform: scale(1) translateY(0);
            opacity: 1;
        }

        .close-btn {
            position: absolute;
            top: 20px; right: 25px;
            font-size: 2.5rem;
            cursor: pointer;
            color: #666;
            transition: 0.3s;
            line-height: 1;
        }

        .close-btn:hover {
            color: var(--gold-main);
            transform: rotate(90deg);
        }

        .modal-text {
            font-family: 'Frank Ruhl Libre', serif;
            font-size: 2.5rem;
            line-height: 1.3;
            color: var(--gold-light);
            text-shadow: 0 2px 10px rgba(0,0,0,0.5);
            margin-top: 20px;
        }

        .modal-day {
            font-family: 'Assistant', sans-serif;
            font-size: 1.2rem;
            color: var(--gold-dark);
            letter-spacing: 4px;
            text-transform: uppercase;
            border-bottom: 1px solid rgba(212, 175, 55, 0.2);
            padding-bottom: 15px;
            display: inline-block;
        }

        /* Admin Trigger & Panel */
        .admin-trigger {
            position: fixed;
            bottom: 15px;
            left: 15px;
            font-size: 1.2rem;
            color: rgba(255, 255, 255, 0.03);
            cursor: pointer;
            z-index: 9999;
            transition: 0.3s;
            user-select: none;
        }

        .admin-trigger:hover {
            color: rgba(255, 255, 255, 0.3);
        }

        .admin-panel-content {
            text-align: right;
            padding: 40px;
        }

        .admin-panel-content h2 {
            color: var(--gold-main);
            margin-bottom: 20px;
            text-align: center;
        }

        .admin-input-group {
            margin-bottom: 20px;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        /* סגנון כפתור העלאת קובץ בעיצוב יוקרתי */
        .file-upload-wrapper {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .admin-input-group input[type="file"] {
            background: #222;
            color: #fff;
            padding: 10px;
            border-radius: 8px;
            border: 1px solid #444;
            font-family: inherit;
            flex-grow: 1;
            cursor: pointer;
        }

        .btn {
            background: linear-gradient(135deg, var(--gold-main), var(--gold-dark));
            color: #fff;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: 600;
            transition: 0.3s;
        }

        .btn:hover {
            box-shadow: 0 0 15px rgba(212, 175, 55, 0.5);
        }

        .btn-danger {
            background: linear-gradient(135deg, #a83232, #7a1f1f);
            margin-top: 20px;
            width: 100%;
            font-size: 1.3rem;
        }

        .btn-danger:disabled {
            background: #444;
            color: #888;
            cursor: not-allowed;
            box-shadow: none;
        }

        .status-text {
            text-align: center;
            margin-top: 15px;
            color: #aaa;
            font-weight: 600;
        }

    </style>
</head>
<body>

    <div class="site-overlay"></div>
    <div class="particles" id="particles"></div>

    <div class="admin-trigger" id="admin-trigger">⚙️</div>

    <header class="hero">
        <div class="image-wrapper">
            <img src="image_9801e4.jpg" alt="מנחם ומינדי">
        </div>
        <h1>מנחם & מינדי</h1>
        
        <div class="countdown-container">
            <div class="time-box">
                <span id="days">12</span>
                <label>ימים</label>
            </div>
            <div class="time-box">
                <span id="hours">00</span>
                <label>שעות</label>
            </div>
            <div class="time-box">
                <span id="minutes">00</span>
                <label>דקות</label>
            </div>
            <div class="time-box">
                <span id="seconds">00</span>
                <label>שניות</label>
            </div>
        </div>
    </header>

    <div class="container">
        <div class="grid" id="cubes-container">
            </div>
    </div>

    <div class="modal-overlay" id="punchline-modal">
        <div class="modal-content">
            <span class="close-btn" id="close-punchline">&times;</span>
            <div class="modal-day" id="modal-day-title">יום 0</div>
            <div class="modal-text" id="modal-text-content">טקסט</div>
        </div>
    </div>

    <div class="modal-overlay" id="admin-modal">
        <div class="modal-content admin-panel-content">
            <span class="close-btn" id="close-admin">&times;</span>
            <h2>ניהול מאחורי הקלעים</h2>
            
            <div class="admin-input-group">
                <label>החלף תמונת רקע לכל האתר (העלאת קובץ תמונה מהמחשב):</label>
                <div class="file-upload-wrapper">
                    <input type="file" id="bg-file-input" accept="image/*">
                    <button class="btn" id="save-bg-btn">שמור רקע</button>
                </div>
            </div>

            <hr style="border-color:#333; margin: 30px 0;">

            <button class="btn btn-danger" id="start-countdown-btn">🚀 התחל ספירה לאחור עכשיו!</button>
            <div class="status-text" id="admin-status"></div>
        </div>
    </div>

    <script>
        // --- מערכת משפטים מורחבת (12 ימים) ---
        const punchlines = {
            12: "שתים עשרה ימים! ההתרגשות מתחילה רשמית עכשיו, פותחים יומנים.",
            11: "אחד עשר ימים. זה הזמן להפסיק לדחות סידורים של הרגע האחרון.",
            10: "זה השלב שבו מתחילים לתרגל חיוכים למצלמה. השרירים הולכים לעבוד קשה!",
            9: "תשעה ימים! דיאטת טרום-החופה בוטלה רשמית, עוברים לתזונת אדרנלין.",
            8: "שמונה ימים! יאללה, להכניס להילוך גבוה, החליפות מוכנות?",
            7: "שבוע בדיוק! זמן מצוין לבדוק שוב שהטבעת אכן בטוחה ולא נכנסה לכביסה.",
            6: "שישה ימים! מינדי כבר סגרה הכל לפני חודשיים, מנחם רק מתחיל לעכל.",
            5: "חמישה ימים של טירוף חושים. חלומות על סידורי הושבה הופכים למציאות.",
            4: "ארבעה ימים! אפשר להפסיק לרענן את תחזית מזג האוויר. יהיה מושלם.",
            3: "שלושה ימים! הפלייליסט של החתונה כבר מנגן בלופ בראש.",
            2: "מחרתיים! הפרפרים בבטן כבר מזמן הפכו ללהקת ציפורים שלמה.",
            1: "מחר זה קורה!! החופה מחכה, בניין עדי עד, מתרגשים איתכם ברמות על!"
        };

        // --- ניהול נתונים מקומיים (LocalStorage) ---
        let isCountdownStarted = localStorage.getItem('weddingCountdownStarted') === 'true';
        let countdownStartTime = parseInt(localStorage.getItem('weddingStartTime')) || 0;
        let customBgData = localStorage.getItem('weddingBgData'); // שמירת ה-Base64 של התמונה

        // טעינת רקע מותאם אישית אם קיים בזיכרון
        if (customBgData) {
            document.body.style.backgroundImage = `url('${customBgData}')`;
        }

        // --- יצירת 12 הקוביות הפוך (12 עד 1) ---
        const gridContainer = document.getElementById('cubes-container');
        const now = Date.now();
        const daysPassed = isCountdownStarted ? Math.floor((now - countdownStartTime) / (1000 * 60 * 60 * 24)) : -1;

        for (let i = 12; i >= 1; i--) {
            const cube = document.createElement('div');
            cube.className = 'cube';
            
            // יום 12 נפתח מיד עם הלחיצה (יום 0 לפעילות הספירה), יום 11 אחרי יממה וכו'
            const isUnlocked = isCountdownStarted && ((12 - i) <= daysPassed);
            
            if (!isUnlocked) {
                cube.classList.add('locked');
            }

            cube.innerHTML = `
                <span class="cube-number">${i}</span>
                <span class="cube-text">לחשוף את הסוד</span>
            `;
            
            cube.addEventListener('click', () => {
                if (isUnlocked) {
                    openPunchlineModal(i);
                }
            });
            
            gridContainer.appendChild(cube);
        }

        // --- מערכת שעון ספירה לאחור ---
        const updateCountdown = () => {
            if (!isCountdownStarted) {
                document.getElementById("days").innerText = "12";
                return;
            }

            const targetDate = countdownStartTime + (12 * 24 * 60 * 60 * 1000);
            const currentTime = Date.now();
            const distance = targetDate - currentTime;

            if (distance < 0) {
                document.getElementById("days").innerText = "00";
                document.getElementById("hours").innerText = "00";
                document.getElementById("minutes").innerText = "00";
                document.getElementById("seconds").innerText = "00";
                return;
            }

            const days = Math.floor(distance / (1000 * 60 * 60 * 24));
            const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((distance % (1000 * 60)) / 1000);

            document.getElementById("days").innerText = days < 10 ? '0' + days : days;
            document.getElementById("hours").innerText = hours < 10 ? '0' + hours : hours;
            document.getElementById("minutes").innerText = minutes < 10 ? '0' + minutes : minutes;
            document.getElementById("seconds").innerText = seconds < 10 ? '0' + seconds : seconds;
        };

        setInterval(updateCountdown, 1000);
        updateCountdown();

        // --- מודל פאנצ'ים (Punchline Modal) ---
        const punchlineModal = document.getElementById('punchline-modal');
        const modalDayTitle = document.getElementById('modal-day-title');
        const modalTextContent = document.getElementById('modal-text-content');
        
        function openPunchlineModal(dayIndex) {
            modalDayTitle.innerText = `— נותרו ${dayIndex} ימים —`;
            modalTextContent.innerHTML = punchlines[dayIndex];
            punchlineModal.classList.add('active');
        }

        document.getElementById('close-punchline').addEventListener('click', () => {
            punchlineModal.classList.remove('active');
        });

        // --- מנגנון ניהול סודי ---
        const adminTrigger = document.getElementById('admin-trigger');
        const adminModal = document.getElementById('admin-modal');
        const bgFileInput = document.getElementById('bg-file-input');
        const saveBgBtn = document.getElementById('save-bg-btn');
        const startBtn = document.getElementById('start-countdown-btn');
        const adminStatus = document.getElementById('admin-status');

        adminTrigger.addEventListener('click', () => {
            const password = prompt("הכנס קוד גישה למערכת:");
            if (password === "1234") {
                adminModal.classList.add('active');
                
                if (isCountdownStarted) {
                    startBtn.disabled = true;
                    startBtn.innerText = "✅ הספירה לאחור פועלת!";
                    adminStatus.innerText = "הספירה הופעלה בהצלחה ולא ניתנת לכיבוי. קוביות נפתחות אוטומטית לפי הקצב.";
                }
            } else if (password !== null) {
                alert("קוד שגוי.");
            }
        });

        document.getElementById('close-admin').addEventListener('click', () => {
            adminModal.classList.remove('active');
        });

        // לוגיקת עיבוד והעלאת קובץ תמונה מהמחשב
        saveBgBtn.addEventListener('click', () => {
            const file = bgFileInput.files[0];
            if (file) {
                // הגבלת נפח אופציונלית כדי למנוע קריסה של הזיכרון המקומי
                if (file.size > 3.5 * 1024 * 1024) {
                    alert("הקובץ גדול מדי! אנא העלה תמונה קטנה מ-3.5MB כדי שהדפדפן יוכל לשמור אותה בצורה יציבה.");
                    return;
                }

                const reader = new FileReader();
                reader.onload = function(e) {
                    const base64String = e.target.result;
                    localStorage.setItem('weddingBgData', base64String);
                    document.body.style.backgroundImage = `url('${base64String}')`;
                    alert("תמונת הרקע הועלתה והתעדכנה באתר בהצלחה!");
                };
                reader.readAsDataURL(file);
            } else {
                alert("אנא בחר קובץ תמונה מהמחשב לפני לחיצה על שמירה.");
            }
        });

        // הפעלת ספירה לאחור ללא דרך חזרה
        startBtn.addEventListener('click', () => {
            if (confirm("האם אתה בטוח לחלוטין? ברגע שהספירה מתחילה, לא ניתן לכבות אותה! יום 12 ייפתח מיד, וכל 24 שעות בדיוק תיפתח הקובייה הבאה אוטומטית.")) {
                localStorage.setItem('weddingCountdownStarted', 'true');
                localStorage.setItem('weddingStartTime', Date.now().toString());
                alert("הספירה לאחור הופעלה בזה הרגע!");
                location.reload();
            }
        });

        // --- חלקיקים מרחפים ---
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 30; i++) {
            let particle = document.createElement('div');
            particle.classList.add('particle');
            let size = Math.random() * 8 + 2;
            particle.style.width = `${size}px`;
            particle.style.height = `${size}px`;
            particle.style.left = `${Math.random() * 100}vw`;
            particle.style.top = `${Math.random() * 100}vh`;
            particle.style.animationDuration = `${Math.random() * 5 + 5}s`;
            particle.style.animationDelay = `${Math.random() * 5}s`;
            particlesContainer.appendChild(particle);
        }
    </script>
</body>
</html>
