<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- 网站标题 -->
    <title>Arise 女团 - 奔赴热爱，闪耀舞台</title>
    <!-- 引入字体图标（可选） -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.2/font/bootstrap-icons.min.css">
    <!-- 自定义CSS样式 -->
    <style>
        /* 全局样式重置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Noto Sans SC', sans-serif;
        }

        body {
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
        }

        /* 导航栏样式 */
        nav {
            position: fixed;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
            z-index: 999;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 2rem;
        }

        .nav-logo img {
            height: 40px;
        }

        .nav-menu {
            list-style: none;
            display: flex;
            gap: 2rem;
        }

        .nav-menu li a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
        }

        .nav-menu li a:hover {
            color: #ff6b6b;
        }

        /* 响应式导航：移动端隐藏菜单 */
        .nav-toggle {
            display: none;
            flex-direction: column;
            justify-content: space-between;
            width: 28px;
            height: 20px;
            cursor: pointer;
        }

        .nav-toggle span {
            height: 3px;
            background: #333;
            border-radius: 2px;
            transition: all 0.3s ease;
        }

        @media (max-width: 768px) {
            .nav-menu {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 60px;
                left: 0;
                width: 100%;
                background: #fff;
                box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
                padding: 1rem 2rem;
                gap: 1rem;
            }

            .nav-menu.active {
                display: flex;
            }

            .nav-toggle {
                display: flex;
            }
        }

        /* 首页横幅样式 */
        .hero {
            height: 100vh;
            background: url('arise-hero.jpg') center/cover no-repeat;
            /* 替换为实际背景图 */
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
        }

        .hero-overlay {
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.3);
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            padding: 0 2rem;
        }

        .hero-content img {
            width: 300px;
            margin-bottom: 2rem;
            /* 女团logo */
        }

        .hero-content h1 {
            font-size: 3rem;
            color: #fff;
            text-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
            margin-bottom: 1.5rem;
        }

        .hero-content p {
            font-size: 1.2rem;
            color: #fff;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
            margin-bottom: 2.5rem;
        }

        .btn {
            display: inline-block;
            padding: 0.8rem 2rem;
            background-color: #ff6b6b;
            color: #fff;
            text-decoration: none;
            border-radius: 30px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(255, 107, 107, 0.3);
        }

        /* 通用容器样式 */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        /* 标题通用样式 */
        .section-title {
            font-size: 2rem;
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background-color: #ff6b6b;
        }

        /* 关于我们 */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-img img {
            width: 100%;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        .about-text {
            line-height: 1.8;
        }

        .about-text p {
            margin-bottom: 1.5rem;
            text-align: justify;
        }

        @media (max-width: 768px) {
            .about-content {
                grid-template-columns: 1fr;
            }
        }

        /* 成员介绍 */
        .members-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 2rem;
        }

        .member-card {
            background: #fff;
            border-radius: 12px;
            padding: 2rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            text-align: center;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .member-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 18px rgba(0, 0, 0, 0.1);
        }

        .member-card img {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 1rem;
            border: 4px solid #f9f9f9;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }

        .member-card h3 {
            margin-bottom: 0.5rem;
            font-size: 1.2rem;
        }

        .member-card p {
            color: #666;
        }

        /* 作品展示 */
        .works-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .work-card {
            background: #fff;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease;
        }

        .work-card:hover {
            transform: translateY(-3px);
        }

        .work-card img {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 1rem;
        }

        .work-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .work-info h4 {
            font-size: 1.1rem;
        }

        .work-info span {
            color: #ff6b6b;
            font-weight: 500;
        }

        /* 动态资讯 */
        .news-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 2rem;
        }

        .news-card {
            background: #fff;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease;
        }

        .news-card:hover {
            transform: translateY(-3px);
        }

        .news-card time {
            display: block;
            color: #999;
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
        }

        .news-card h4 {
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }

        .news-card p {
            text-align: justify;
            line-height: 1.6;
        }

        /* 周边商城 */
        .merch-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
        }

        .merch-card {
            background: #fff;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            text-align: center;
            transition: transform 0.3s ease;
        }

        .merch-card:hover {
            transform: translateY(-5px);
        }

        .merch-card img {
            width: 100%;
            border-radius: 8px;
            margin-bottom: 1rem;
        }

        .merch-card h4 {
            margin-bottom: 0.5rem;
        }

        .merch-card span {
            color: #ff6b6b;
            font-weight: 500;
        }

        /* 联系我们 */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .contact-form input,
        .contact-form textarea {
            width: 100%;
            padding: 0.8rem;
            margin-bottom: 1.5rem;
            border: 1px solid #ddd;
            border-radius: 6px;
            resize: none;
        }

        .contact-form button {
            width: 100%;
            padding: 0.8rem;
            background-color: #ff6b6b;
            color: #fff;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .contact-form button:hover {
            transform: translateY(-2px);
        }

        /* 页脚 */
        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 2rem;
            margin-top: 4rem;
        }

        .footer-social {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 1rem;
        }

        .footer-social a {
            color: #fff;
            font-size: 1.2rem;
            transition: color 0.3s ease;
        }

        .footer-social a:hover {
            color: #ff6b6b;
        }

        /* 响应式适配 */
        @media (max-width: 576px) {
            .hero-content h1 {
                font-size: 2rem;
            }

            .hero-content p {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏 -->
    <nav>
        <div class="nav-container">
            <div class="nav-logo">
                <!-- 替换为女团logo -->
                <img src="arise-logo.png" alt="Arise Logo">
            </div>
            <ul class="nav-menu">
                <li><a href="#home">首页</a></li>
                <li><a href="#about">关于我们</a></li>
                <li><a href="#members">成员介绍</a></li>
                <li><a href="#works">作品展示</a></li>
                <li><a href="#news">动态资讯</a></li>
                <li><a href="#merch">周边商城</a></li>
                <li><a href="#contact">联系我们</a></li>
            </ul>
            <!-- 移动端菜单开关 -->
            <div class="nav-toggle" onclick="toggleMenu()">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- 首页横幅 -->
    <section id="home" class="hero">
        <div class="hero-overlay"></div>
        <div class="hero-content">
            <!-- 替换为女团logo -->
            <img src="arise-logo.png" alt="Arise Logo">
            <h1>奔赴热爱，闪耀舞台</h1>
            <p>青春无畏，用汗水浇灌梦想 | 每一次舞台，都是成长的见证</p>
            <a href="#works" class="btn">查看最新作品</a>
        </div>
    </section>

    <!-- 关于我们 -->
    <section id="about" class="container">
        <h2 class="section-title">关于我们</h2>
        <div class="about-content">
            <!-- 替换为女团合照 -->
            <div class="about-img">
                <img src="arise-group.jpg" alt="Arise Group">
            </div>
            <div class="about-text">
                <p>Arise 女团成立于[成立年份]，由一群热爱舞台、追逐梦想的女孩组成。</p>
                <p>我们以「青春、热爱、突破」为理念，将流行音乐与多元风格融合，用独特的表演传递积极能量。</p>
                <p>从练习室的汗水到舞台上的光芒，每一步都离不开粉丝的支持——未来，我们将继续用作品回应期待，用舞台点燃热爱！</p>
            </div>
        </div>
    </section>

    <!-- 成员介绍 -->
    <section id="members" class="container">
        <h2 class="section-title">成员介绍</h2>
        <div class="members-grid">
            <!-- 成员1：替换图片、姓名、简介 -->
            <div class="member-card">
                <img src="member1.jpg" alt="Member 1">
                <h3>姓名1</h3>
                <p>担当：主唱</p>
                <p>标签：治愈嗓音 | 舞台共情者</p>
            </div>
            <!-- 成员2：替换图片、姓名、简介 -->
            <div class="member-card">
                <img src="member2.jpg" alt="Member 2">
                <h3>姓名2</h3>
                <p>担当：主舞</p>
                <p>标签：力量舞者 | 表情管理大师</p>
            </div>
            <!-- 成员3：替换图片、姓名、简介 -->
            <div class="member-card">
                <img src="member3.jpg" alt
