# ping-volleyball-website
<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>治平高中排球社</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Microsoft JhengHei', sans-serif;
        }
        
        :root {
            --primary: #1e5799;
            --secondary: #e74c3c;
            --light: #f8f9fa;
            --dark: #2c3e50;
            --accent: #3498db;
        }
        
        body {
            background-color: #f5f7fa;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* 導航列 */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 2rem;
        }
        
        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: var(--primary);
        }
        
        /* 主視覺區域 */
        .hero {
            background: linear-gradient(135deg, var(--primary) 0%, #2980b9 100%);
            color: white;
            padding: 5rem 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--secondary);
            color: white;
            padding: 0.8rem 2rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .btn:hover {
            background-color: #c0392b;
            transform: translateY(-3px);
        }
        
        /* 內容區塊 */
        .section {
            padding: 5rem 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--primary);
            margin: 1rem auto;
            border-radius: 2px;
        }
        
        .about {
            background-color: white;
        }
        
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }
        
        .about-text h3 {
            color: var(--primary);
            margin-bottom: 1rem;
        }
        
        .about-features {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1.5rem;
        }
        
        .feature {
            background-color: var(--light);
            padding: 1.5rem;
            border-radius: 8px;
            border-left: 4px solid var(--accent);
        }
        
        .feature h4 {
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        /* 活動資訊 */
        .activities {
            background-color: var(--light);
        }
        
        .activity-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .activity-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s;
        }
        
        .activity-card:hover {
            transform: translateY(-10px);
        }
        
        .card-header {
            background-color: var(--primary);
            color: white;
            padding: 1.5rem;
            text-align: center;
        }
        
        .card-body {
            padding: 1.5rem;
        }
        
        .card-body ul {
            list-style: none;
        }
        
        .card-body li {
            margin-bottom: 0.8rem;
            padding-left: 1.5rem;
            position: relative;
        }
        
        .card-body li::before {
            content: "●";
            color: var(--primary);
            position: absolute;
            left: 0;
        }
        
        /* 聯絡我們 */
        .contact {
            background-color: white;
        }
        
        .contact-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
        }
        
        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }
        
        .contact-item {
            display: flex;
            align-items: flex-start;
            gap: 1rem;
        }
        
        .contact-icon {
            font-size: 1.5rem;
            color: var(--primary);
            min-width: 30px;
        }
        
        .ig-link {
            display: inline-flex;
            align-items: center;
            background: linear-gradient(45deg, #405DE6, #5851DB, #833AB4, #C13584, #E1306C, #FD1D1D);
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            margin-top: 10px;
            transition: transform 0.3s;
        }
        
        .ig-link:hover {
            transform: translateY(-3px);
        }
        
        .ig-link i {
            margin-right: 8px;
            font-size: 1.2rem;
        }
        
        /* 頁尾 */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 3rem 0 1.5rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            margin-bottom: 1.5rem;
            position: relative;
            padding-bottom: 0.5rem;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background-color: var(--primary);
        }
        
        .footer-links {
            list-style: none;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: rgba(255, 255, 255, 0.8);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: rgba(255, 255, 255, 0.7);
        }
        
        /* 響應式設計 */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .about-features {
                grid-template-columns: 1fr;
            }
            
            .contact-content {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- 導航列 -->
    <header>
        <div class="container">
            <nav>
                <a href="#" class="logo">治平高中排球社</a>
                <ul class="nav-links">
                    <li><a href="#about">關於我們</a></li>
                    <li><a href="#activities">活動資訊</a></li>
                    <li><a href="#contact">聯絡我們</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- 主視覺區域 -->
    <section class="hero">
        <div class="container">
            <h1>治平高中排球社</h1>
            <p>2024年創立 • 歡迎所有對排球有興趣的同學加入！</p>
            <a href="#contact" class="btn">立即加入</a>
        </div>
    </section>

    <!-- 關於我們 -->
    <section id="about" class="section about">
        <div class="container">
            <h2 class="section-title">關於我們</h2>
            <div class="about-content">
                <div class="about-text">
                    <h3>我們的使命</h3>
                    <p>治平高中排球社成立於2024年，致力於推廣排球運動，提供一個友善的環境，讓所有對排球有興趣的同學都能找到歸屬感。</p>
                    <p>我們相信排球不僅是一項運動，更是建立友誼、培養團隊精神的橋樑。</p>
                </div>
                <div class="about-features">
                    <div class="feature">
                        <h4>社團時間</h4>
                        <p>每週三下午第一到第三節課</p>
                    </div>
                    <div class="feature">
                        <h4>額外活動</h4>
                        <p>有空可以下午1點去中原大學打排球</p>
                    </div>
                    <div class="feature">
                        <h4>加入方式</h4>
                        <p>想報名可以到普三信班級找社長報名</p>
                    </div>
                    <div class="feature">
                        <h4>關注我們</h4>
                        <p>追蹤我們的IG帳號，獲取最新消息</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 活動資訊 -->
    <section id="activities" class="section activities">
        <div class="container">
            <h2 class="section-title">活動資訊</h2>
            <div class="activity-cards">
                <div class="activity-card">
                    <div class="card-header">
                        <h3>社團例行活動</h3>
                    </div>
                    <div class="card-body">
                        <ul>
                            <li>時間：每週三下午第一到第三節課</li>
                            <li>地點：治平高中體育館</li>
                            <li>內容：基礎訓練、分組練習、友誼賽</li>
                            <li>適合對象：所有社團成員</li>
                        </ul>
                    </div>
                </div>
                <div class="activity-card">
                    <div class="card-header">
                        <h3>校外練習</h3>
                    </div>
                    <div class="card-body">
                        <ul>
                            <li>時間：有空時下午1點</li>
                            <li>地點：中原大學排球場</li>
                            <li>內容：自由練習、交流賽</li>
                            <li>適合對象：所有對排球有興趣者</li>
                        </ul>
                    </div>
                </div>
                <div class="activity-card">
                    <div class="card-header">
                        <h3>未來規劃</h3>
                    </div>
                    <div class="card-body">
                        <ul>
                            <li>參加校際排球比賽</li>
                            <li>與其他學校排球社交流</li>
                            <li>舉辦校內排球比賽</li>
                            <li>排球技巧講座</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 聯絡我們 -->
    <section id="contact" class="section contact">
        <div class="container">
            <h2 class="section-title">聯絡我們</h2>
            <div class="contact-content">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <div>
                            <h3>加入方式</h3>
                            <p>請到普三信班級找社長報名</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">⏰</div>
                        <div>
                            <h3>社團時間</h3>
                            <p>每週三下午第一到第三節課</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">🏐</div>
                        <div>
                            <h3>額外活動</h3>
                            <p>有空可以下午1點去中原大學打排球</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📱</div>
                        <div>
                            <h3>社群媒體</h3>
                            <p>追蹤我們的IG帳號</p>
                            <a href="https://www.instagram.com/cpshs__volleyball/" class="ig-link" target="_blank">
                                <i class="fab fa-instagram"></i> cpshs__volleyball
                            </a>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <h3>想了解更多？</h3>
                    <p>歡迎直接到普三信班級找社長詢問，或追蹤我們的IG帳號獲取最新消息！</p>
                    <p>我們期待你的加入，一起享受排球的樂趣！</p>
                </div>
            </div>
        </div>
    </section>

    <!-- 頁尾 -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>治平高中排球社</h3>
                    <p>2024年創立，歡迎所有對排球有興趣的同學加入！</p>
                </div>
                <div class="footer-column">
                    <h3>快速連結</h3>
                    <ul class="footer-links">
                        <li><a href="#about">關於我們</a></li>
                        <li><a href="#activities">活動資訊</a></li>
                        <li><a href="#contact">聯絡我們</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>聯絡資訊</h3>
                    <ul class="footer-links">
                        <li>社團時間：每週三下午</li>
                        <li>報名地點：普三信班級</li>
                        <li>額外活動：中原大學排球場</li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2024 治平高中排球社</p>
            </div>
        </div>
    </footer>
</body>
</html>
