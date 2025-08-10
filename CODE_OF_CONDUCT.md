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

    .英雄内容p{
            font-size: 1.2rem;
            color: #fff;
    text-shadow:02px4px rgba(0，0，0，0.2)；
    边缘-底部：2.5rem；
        }

    .btn{
    显示：内联块；
    填料：0.8rem2rem；
    背景色：#ff6b6b；
            color: #fff;
    文字修饰：无；
    边界半径：30px；
    过渡：变换0.3s轻松，盒影0.3s轻松；
        }

    .btn：悬停{
    变换：translateY(-2px)；
    盒阴影：04px12pxrgba(255，107，107，0.3)；
        }

    /* 通用容器样式 */
    .container{
    最大宽度：1200px；
    页边距：0自动；
    填料：4rem2rem；
        }

    /* 标题通用样式 */
    .章节标题{
    font-size:2rem；
    文本对齐：居中；
    底边距：3rem；
    位置：相对；
        }

    .节标题：：在{之后
    内容：“”；
    位置：绝对；
    底部：-10px；
    左侧：50%；
    变换：translateX(-50%)；
    宽度：60px；
    高度：3px；
    背景色：#ff6b6b；
        }

    /* 关于我们 */
    .关于-内容{
    显示：网格；
    网格模板列：1fr1fr；
    间隙：3rem；
    对齐项：居中；
        }

    .About-img img{
    宽度：100%；
    边界半径：12px；
    盒阴影：04px12pxrgba(0，0，0，0.1)；
        }

    .关于文本{
    线高：1.8；
        }

    .关于文本p{
    边缘-底部：1.5rem；
    文本对齐：对齐；
        }

    @media(最大宽度：768px){
    .关于-内容{
    网格-模板-列：1fr；
            }
        }

    /* 成员介绍 */
    .members-grid{
    显示：网格；
    网格模板列：重复(自动拟合，最小值(220px，1fr))；
    间隙：2rem；
        }

    .会员卡{
    背景：#fff；
    边界半径：12px；
    填料：2rem；
    盒阴影：04px12pxrgba(0，0，0，0.08)；
    文本对齐：居中；
    过渡：变换0.3s轻松，盒影0.3s轻松；
        }

    .member-card:hover{
    变换：translateY(-5px)；
    盒阴影：06px18pxrgba(0，0，0，0.1)；
        }

    .会员卡img{
    宽度：120px；
    高度：120px；
    边界半径：50%；
    对象匹配：盖；
    边底：1rem；
    边框：4px实心#f9f9f9；
    盒阴影：02px8px rgba(0，0，0，0.1)；
        }

    .会员卡h3{
    边缘-底部：0.5rem；
    font-size:1.2rem；
        }

    .会员卡p{
    颜色：#666；
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

    .工作信息范围{
            color: #ff6b6b;
    font-weight:500；
        }

    /* 动态资讯 */
    .news-grid{
            display: grid;
    网格-模板-列：1fr；
            gap: 2rem;
        }

    .news-card{
            background: #fff;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease;
        }

    .news-card：悬停{
    变换：translateY(-3px)；
        }

    .news-card时间{
    显示：块；
    颜色：#999；
    边缘-底部：0.5rem；
    font-size:0.9rem；
        }

    .news-card h4{
    font-size:1.2rem；
    边底：1rem；
        }

    .news-card p{
    文本对齐：对齐；
    线高：1.6；
        }

    /* 周边商城 */
    .merch-grid{
    显示：网格；
    网格模板列：重复(自动拟合，最小值(200px，1fr))；
    间隙：2rem；
        }

    .merch-card{
    背景：#fff；
    边界半径：12px；
    填料：1.5rem；
    盒阴影：04px12pxrgba(0，0，0，0.08)；
    文本对齐：居中；
    过渡：转换0.3s轻松；
        }

    .merch-card：悬停{
    变换：translateY(-5px)；
        }

    .merch-card img{
    宽度：100%；
    边界半径：8px；
    边底：1rem；
        }

    .merch-card h4{
    边缘-底部：0.5rem；
        }

    .merch-card span{
    颜色：#ff6b6b；
    font-weight:500；
        }

/* 联系我们 */
.接触形式{
最大宽度：600px；
页边距：0自动；
        }

    .接触形式输入，
    .联系人表单文本区域{
    宽度：100%；
    填料：0.8rem；
    边缘-底部：1.5rem；
    边框：1px实心#ddd；
    边界半径：6px；
    调整大小：无；
        }

    .接触形式按钮{
    宽度：100%；
    填料：0.8rem；
    背景色：#ff6b6b；
    颜色：#fff；
    边框：无；
    边界半径：30px；
    光标：指针；
    过渡：转换0.3s轻松；
        }

    .联系人表单按钮：悬停{
    变换：translateY(-2px)；
        }

    /* 页脚 */
    页脚{
    背景色：#333；
    颜色：#fff；
            text-align: center;
    填料：2rem；
    margin-top:4rem；
        }

    .footer-social{
    显示：柔性；
    对齐-内容：居中；
    间隙：1.5rem；
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

    .英雄内容p{
    font-size:1rem；
            }
        }
    </style>
</头>
<身体>
<! -- 导航栏 -->
<NAV><NAV>
<div班级="导航容器">
<div class="导航徽标"><div"导航徽标"="导航徽标">
<！ --替换为女团徽标-->
<IMGsrc="ise-logo.png"alt="升起标志">
</div>
<<UL类UL类身体"导航菜单">>"导航菜单"ULclass="导航菜单">
<<锂><锂</一个></一个href=<一个href="#home">首页>><>首页</>首页></锂><//一个>></锂>><锂</一个></一个href=<一个href="#home">首页>><>首页</>首页></锂><//一个>></锂>
<<锂><锂</一个></一个href="#关于">关于我们><锂><锂</一个></锂>><锂</一个></一个href="#关于">关于我们><锂><锂</一个></锂>
<<锂><锂</一个></一个href="成员数">成员介绍><锂><一个href="成员数">成员介绍</一个></锂></一个></锂>><锂</一个></一个href="成员数">成员介绍><锂><一个href="成员数">成员介绍</一个></锂></一个></锂>
<<<<li><一个href="#个作品">作品展示</一个></一个href="#个作品">作品展示><锂><一个href="#个作品">作品展示</一个></锂>><一个href="#个作品">作品展示</一个></一个href="#个作品">作品展示><锂><一个href="#个作品">作品展示</一个></锂>>><一个href="#个作品">作品展示</一个></一个href="#个作品">作品展示><锂><一个href="#个作品">作品展示</一个></锂>><一个href="#个作品">作品展示</一个></一个href="#个作品">作品展示><锂><一个href="#个作品">作品展示</一个></锂>>
<<<<li><一个href="#news">动态资讯</一个></li><锂><一个href="#news">动态资讯</一个></锂>><一个href="#news">动态资讯</一个></li><锂><一个href="#新闻">动态资讯</一个></锂>><一个href="#news">动态资讯</一个></li><锂><一个href="#news">动态资讯</一个></锂>><一个href="#news">动态资讯</一个></li><锂><一个href="#新闻">动态资讯</一个></锂></一个></锂>
<<<<li><一个href="#merc">周边商城</一个></一个href="#merc">周边商城><li><一个href="#merc">周边商城</一个></li>><一个href="#merc">周边商城</一个></一个href="#merc">周边商城><li><一个href="#merc">周边商城</一个></li>><一个href="#merc">周边商城</一个></一个href="#merc">周边商城><li><一个href="#merc">周边商城</一个></li>><一个href="#merc">周边商城</一个></一个href="#merc">周边商城><li><一个href="#merc">周边商城</一个></li>
<<li><一个href="#contact">联系我们</一个></li><li><一个href="#contact">联系我们</一个></li>><一个href="#contact">联系我们</一个></li><li><一个href="#contact">联系我们</一个></li>
</</UL></UL>></UL>
<! -- 移动端菜单开关 -->
<<div class="导航切换"onClick="导航切换"><div onClick="导航切换"onClick="toggleMenu()">班级="导航切换"onClick="导航切换"><div onClick="导航切换"onClick="toggleMenu()">
<<跨度></跨度><跨度></跨度>></跨度><跨度></跨度>
<<跨度></跨度><跨度></跨度>></跨度><跨度></跨度>
<<跨度></跨度><跨度></跨度>></跨度><跨度></跨度>
</div>
</div>
</</nav对齐项：居中；</nav对齐项：居中；

<! -- 首页横幅 --><! -- 首页横幅 -->
<部分身份标识="主页"class="hero"><部分身份标识="主页"class="hero">
<<div class="英雄叠加"></div"英雄叠加"class="英雄叠加"></div><div class="英雄叠加"></div"英雄叠加"class="hero-overlay"></div><div class="英雄叠加"></div"英雄叠加"class="hero-overlay"></div>
<! -- 关于我们 -->
<部分身份标识="关于"班级="容器">
<h2class="section-title">关于我们
<<H1>奔赴热爱，闪耀舞台</H1>>奔赴热爱，闪耀舞台</H1><H1>奔赴热爱，闪耀舞台</H1>>奔赴热爱，闪耀舞台</H1><H1>奔赴热爱，闪耀舞台</H1>>奔赴热爱，闪耀舞台</H1><H1>奔赴热爱，闪耀舞台</H1>>奔赴热爱，闪耀舞台</H1>
<p>青春无畏，用汗水浇灌梦想|每一次舞台，都是成长的见证</p>
<<<<一个href一个href<<一个href一个href="#个作品"班级#个作品"班级="btn">查看最新作品</一个>"btn">查看最新作品</一个></一个>"#个作品"班级#个作品"班级="btn">查看最新作品</一个>"btn">查看最新作品</一个></一个><<一个href一个href="#个作品"班级#个作品"班级="btn">查看最新作品</一个>"btn">查看最新作品</一个></一个>"#个作品"班级#个作品"班级="btn">查看最新作品</一个>"btn">查看最新作品</一个></一个>
</div>
</</部分>></部分>></部分>></部分>>

<! -- 关于我们 -->
<部分身份标识="关于"班级="容器">
<h2class="section-title">关于我们</H2最大宽度：800px；
<div班级="关于内容">
<! -- 替换为女团合照 -->
<div班级="about-img">
<IMGsrc="eise-group.jpg"alt="生成组">
</div>
<<<<部分<节身份标识<<<<部分<节身份标识="成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器"><节身份标识="成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器"><节身份标识="成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器"><节身份标识="成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器">"成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器"><节身份标识="成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器"><节身份标识="成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器"><节身份标识="成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器">
<h2class="section-title">成员介绍<h2class="section-title">成员介绍<h2class="section-title">成员介绍
<<p.nav-容器{我们以"青春、热爱、突破"为理念，将流行音乐与多元风格融合，用独特的表演传递积极能量.</p>{我们以"青春、热爱、突破"为理念，将流行音乐与多元风格融合，用独特的表演传递积极能量.</p>
<p>从练习室的汗水到舞台上的光芒，每一步都离不开粉丝的支持--未来，我们将继续用作品回应期待，用舞台点燃热爱！</p>
<<<<<<div<div班级<<<<<<<<<div<div班级<<<<<<<<<div<div班级<<<<<<<<<<<div<div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡">"会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡">"会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡">"会员卡">="会员卡"><div班级="会会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">=<div班级<<<<<<<<div<div班级<<<<<<<<div<div班级<<<<<<<<<<div<div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡">"会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡">"会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡">"会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡"><div班级="会员卡"><div班级="会员卡">="会员卡"><div班级="会员卡">
<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<<IMG<img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1<img src="member1。JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.日本G"alt="成员1">="mem<img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member<img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"al<img src="memberR1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG<im<img src="member1.jpg"aLt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG<img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"al<<T="成员1"><src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"al<<T="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1。JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><<T="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Mem<IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.jpg"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><<T="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="成员ER1"><IMGsrc="member1.jpg"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1"><IMGsrc="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="成员1">
<<<<<<<<<<<<<H3>姓名1</H3><H3>>></H3><H3>>>姓名1</H3><H3>><H3>>>姓名1</H3><H3>>></H3><H3>>>姓名1</H3><H3>><H3>>

<! -- 成员介绍 --><! -- 成员介绍 -->
<部分<节身份标识="成员"班级="容器">="成员"class="container"><部分身份标识="成员"班级="容器">
<! -- 成员2：替换图片、姓名、简介 --><! -- 成员2：替换图片、姓名、简介 -->
<div班级="会员卡"><div班级="会员卡">
<IMGsrc="member2.jpg"alt="Member2"><IMGsrc="member2.jpg"alt="成员2">
<
<<IMG<img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="Member1"><img src="member1.JPG"alt="成员1">="member1.JPG"alt="Member1"><IMGsrc="member1.JPG"alt="Member1">
<<H3>姓名1</H3><H3>>
<<p>担当：主唱</p><p>担当：主唱</p>>担当：主唱</p><p>担当：主唱</p>
<<p>标签：治愈嗓音|舞台共情者</p><p>标签：治愈嗓音|舞台共情者</p>>标签：治愈嗓音|舞台共情者</p><p>标签：治愈嗓音|舞台共情者</p>
</div></div>
<! -- 成员2：替换图片、姓名、简介 --><! -- 成员2：替换图片、姓名、简介 -->
<<div班级="会员卡"><div班级="会员卡"><div班级="会员卡">
<<<<IMGsrc<<IMGsrc<<<<IMGsrc<<IMGsrc<<<<IMGsrc<<IMGsrc<<<<IMGsrc<<IMGsrc="member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2">"member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2">"member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2"><<IMGsrc="member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2">"member2.JPG"alt="成员2">IMGsrc="member2.jpgJPG"alt="成员2">"member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2">"member2.jpg"alt="成员2"><IMGsrc="member2.JPG"alt="成员2">"member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2"><<IMGsrc="member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2"><IMGsrc="member2.JPG"alt="成员2">"member2.jpg"alt="成员2">IMGsrc="member2.jpgJPG"alt="成员2">
H3
<<p>担当：主舞</p><p>担当：主舞</p>>担当：主舞</p><p>担当：主舞</p>
<<p>标签：力量舞者|表情管理大师</p><p>标签：力量舞者|表情管理大师</p>>标签：力量舞者|表情管理大师</p><p>标签：力量舞者|表情管理大师</p>
</div></div>
<! -- 成员3：替换图片、姓名、简介 --><!
<<div班级="会员卡"><div班级="会员卡"><div班级="会员卡">
<<<<IMGsrc<<IMGsrc<<<<IMGsrc<<IMGsrc="member3.JPG"alt<IMGsrc="member3.JPG"alt<IMGsrc="member3.JPG"alt"member3.JPG"alt<IMGsrc="member3.JPG"alt<IMGsrc="member3.jpg"alt<<IMGsrc="member3.JPG"alt<IMGsrc="member3.JPG"alt<IMGsrc="member3.jpg"alt"member3.JPG"alt<IMGsrc="member3.JPG"alt<IMGsrc="member3.jpg"alt"member3.JPG"alt<IMGsrc="member3.JPG"alt<IMGsrc="member3.JPG"alt"member3.JPG"alt<IMGsrc="member3.JPG"alt<IMGsrc="member3.jpg"alt<<IMGsrc="member3.JPG"alt<IMGsrc="member3.JPG"alt<IMGsrc="member3.jpg"alt"member3.JPG"alt<IMGsrc="member3.JPG"alt<IMGsrc="member3.jpg"alt
