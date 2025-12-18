[16.html](https://github.com/user-attachments/files/24232255/16.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>橙子的个人简历 - 资深养猪专家</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Microsoft YaHei', Arial, sans-serif;
        }

        body {
            line-height: 1.8;
            color: #333;
            background-color: #f9f9f9;
            padding: 20px;
            max-width: 1200px;
            margin: 0 auto;
            scroll-behavior: smooth;
        }

        /* 导航栏样式 */
        .navbar {
            text-align: center;
            margin: 30px 0;
            border-bottom: 2px solid #ff7f0e;
            padding-bottom: 15px;
            position: sticky;
            top: 0;
            background-color: #f9f9f9;
            z-index: 100;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        .navbar a {
            display: inline-block;
            margin: 0 25px;
            text-decoration: none;
            color: #333;
            font-size: 18px;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
        }

        .navbar a:hover {
            color: #ff7f0e;
        }

        .navbar a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: #ff7f0e;
            transition: width 0.3s ease;
        }

        .navbar a:hover::after {
            width: 100%;
        }

        .navbar a.active {
            color: #ff7f0e;
        }

        .navbar a.active::after {
            width: 100%;
        }

        /* 滚动公告样式 */
        .marquee-container {
            background-color: #fff8e6;
            border-radius: 8px;
            padding: 12px 20px;
            margin: 20px 0;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .marquee {
            white-space: nowrap;
            animation: marquee 15s linear infinite;
            color: #ff7f0e;
            font-weight: 500;
        }

        .marquee:hover {
            animation-play-state: paused;
        }

        @keyframes marquee {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        /* 章节标题样式 */
        .section-title {
            color: #ff7f0e;
            margin: 40px 0 25px;
            padding-left: 15px;
            border-left: 4px solid #ff7f0e;
            font-size: 22px;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            height: 100%;
            width: 4px;
            background-color: #ffb84d;
            transform: scaleY(0);
            transition: transform 0.5s ease;
            transform-origin: bottom;
        }

        .section-title.animate::after {
            transform: scaleY(1);
        }

        /* 个人简介样式 */
        .profile {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            background-color: #fff;
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
            margin-bottom: 30px;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .profile.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .profile-img {
            flex: 0 0 200px;
            height: 200px;
            border-radius: 8px;
            border: 5px solid #fff;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            object-fit: cover;
            transition: transform 0.3s ease;
            cursor: pointer;
        }

        .profile-img:hover {
            transform: scale(1.05);
        }

        .profile-content {
            flex: 1;
            min-width: 300px;
        }

        .info-table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }

        .info-table td {
            padding: 10px 15px;
            border-bottom: 1px solid #eee;
        }

        .info-table td:first-child {
            width: 120px;
            font-weight: 600;
            color: #666;
        }

        .audio-container {
            margin: 20px 0;
            padding: 15px;
            background-color: #fff8e6;
            border-radius: 8px;
        }

        audio {
            width: 100%;
            max-width: 350px;
            margin-top: 10px;
            outline: none;
        }

        /* 内容段落样式 */
        .content-section {
            background-color: #fff;
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
            margin-bottom: 30px;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s ease, transform 0.8s ease;
        }

        .content-section.visible {
            opacity: 1;
            transform: translateY(0);
        }

        .content-section p {
            margin-bottom: 15px;
            text-align: justify;
        }

        /* 列表样式 */
        .experience-list, .award-list {
            list-style: none;
            margin: 20px 0;
        }

        .experience-item, .award-item {
            padding: 15px;
            border-left: 3px solid #ff7f0e;
            background-color: #fff8e6;
            border-radius: 0 8px 8px 0;
            margin-bottom: 15px;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .experience-item::before, .award-item::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            width: 0;
            height: 100%;
            background-color: rgba(255,127,14,0.1);
            transition: width 0.5s ease;
        }

        .experience-item:hover, .award-item:hover {
            transform: translateX(5px);
            box-shadow: 0 3px 10px rgba(255,127,14,0.15);
        }

        .experience-item:hover::before, .award-item:hover::before {
            width: 100%;
        }

        .item-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 8px;
        }

        .item-title {
            font-weight: 600;
            color: #ff7f0e;
            font-size: 16px;
        }

        .item-date {
            color: #999;
            font-size: 14px;
        }

        .item-content {
            font-size: 14px;
            color: #555;
        }

        /* iframe 容器样式 */
        .iframe-container {
            margin: 20px 0;
            border: 1px solid #eee;
            border-radius: 8px;
            overflow: hidden;
            transition: box-shadow 0.3s ease;
        }

        .iframe-container:hover {
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        iframe {
            width: 100%;
            border: none;
        }

        /* 链接样式 */
        .link-btn {
            display: inline-block;
            padding: 8px 20px;
            background-color: #ff7f0e;
            color: white;
            text-decoration: none;
            border-radius: 30px;
            margin: 10px 0;
            transition: all 0.3s ease;
            box-shadow: 0 2px 5px rgba(255,127,14,0.3);
            position: relative;
            overflow: hidden;
        }

        .link-btn::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.6s ease;
        }

        .link-btn:hover {
            background-color: #e67200;
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(255,127,14,0.4);
        }

        .link-btn:hover::after {
            left: 100%;
        }

        /* 技能标签样式 */
        .skill-tags {
            margin: 20px 0;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            padding: 6px 15px;
            background-color: #f0f7ff;
            color: #ff7f0e;
            border-radius: 20px;
            font-size: 14px;
            border: 1px solid #ffe0cc;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .skill-tag:hover {
            background-color: #ff7f0e;
            color: white;
            transform: scale(1.05);
        }

        /* 数据统计卡片 */
        .stats-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin: 30px 0;
        }

        .stat-card {
            flex: 1;
            min-width: 150px;
            background-color: #fff;
            border-radius: 8px;
            padding: 20px;
            text-align: center;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .stat-number {
            font-size: 28px;
            font-weight: 700;
            color: #ff7f0e;
            margin: 10px 0;
            transition: transform 0.5s ease;
        }

        .stat-card:hover .stat-number {
            transform: scale(1.1);
        }

        .stat-label {
            color: #666;
            font-size: 14px;
        }

        /* 时间轴样式 */
        .timeline {
            position: relative;
            margin: 30px 0;
            padding-left: 30px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 4px;
            background-color: #ff7f0e;
            border-radius: 2px;
        }

        .timeline-item {
            position: relative;
            margin-bottom: 30px;
            padding-bottom: 10px;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -34px;
            top: 5px;
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background-color: #fff;
            border: 3px solid #ff7f0e;
            z-index: 1;
        }

        .timeline-date {
            font-weight: 600;
            color: #ff7f0e;
            margin-bottom: 5px;
        }

        .timeline-content {
            background-color: #fff8e6;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.05);
        }

        /* 雷达图容器 */
        .chart-container {
            width: 100%;
            max-width: 500px;
            margin: 30px auto;
            height: 400px;
        }

        /* 返回顶部按钮 */
        .back-to-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background-color: #ff7f0e;
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            text-decoration: none;
            box-shadow: 0 3px 10px rgba(255,127,14,0.4);
            transition: all 0.3s ease;
            opacity: 0;
            visibility: hidden;
            z-index: 1000;
        }

        .back-to-top.show {
            opacity: 0.8;
            visibility: visible;
        }

        .back-to-top:hover {
            opacity: 1;
            transform: translateY(-3px);
        }

        /* 图片预览模态框 */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.8);
            z-index: 2000;
            align-items: center;
            justify-content: center;
        }

        .modal-content {
            max-width: 90%;
            max-height: 90%;
            border: 5px solid white;
            border-radius: 8px;
        }

        .close-modal {
            position: absolute;
            top: 20px;
            right: 30px;
            color: white;
            font-size: 40px;
            font-weight: bold;
            cursor: pointer;
            transition: color 0.3s ease;
        }

        .close-modal:hover {
            color: #ff7f0e;
        }

        /* 响应式调整 */
        @media (max-width: 768px) {
            .navbar a {
                margin: 0 10px;
                font-size: 16px;
            }

            .profile {
                padding: 20px;
            }

            .content-section {
                padding: 20px;
            }

            .marquee {
                font-size: 14px;
            }

            .item-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 5px;
            }

            .chart-container {
                height: 300px;
            }
        }

        @media (max-width: 480px) {
            .navbar {
                margin: 20px 0;
            }

            .navbar a {
                display: block;
                margin: 10px 0;
            }

            .profile-img {
                margin: 0 auto;
            }

            .info-table td {
                padding: 8px 10px;
            }

            .stat-card {
                min-width: 120px;
                padding: 15px;
            }

            .stat-number {
                font-size: 24px;
            }
        }
    </style>
</head>
<body>
    <!-- 顶部锚点 -->
    <a name="顶部"></a>

    <!-- 导航栏 -->
    <div class="navbar">
        <a href="#个人简介" class="nav-link">个人简介</a>
        <a href="#人生简历" class="nav-link">人生简历</a>
        <a href="#获奖经历" class="nav-link">获奖经历</a>
        <a href="#实习经历" class="nav-link">实习经历</a>
    </div>

    <!-- 滚动公告 -->
    <div class="marquee-container">
        <div class="marquee">欢迎访问橙子的个人简历！专注养猪领域60余年，荣获国际最佳养猪奖的行业专家，拥有规模化养猪场运营管理丰富经验，精通科学养殖全流程技术</div>
    </div>

    <!-- 个人简介 section -->
    <h3 class="section-title" id="个人简介">个人简介</h3>
    <div class="profile">
        <img 
            src="https://picsum.photos/id/1084/400/400" 
            alt="橙子的照片" 
            class="profile-img"
            id="profileImage"
            usemap="#养猪场映射"
        >
        <map name="养猪场映射">
            <area shape="circle" coords="100,150,40" href="http://www.yangzhu360.com" target="_blank" alt="养猪360" >
            <area shape="circle" coords="50,100,30" href="http://www.zgyangzhu.com" target="_blank" alt="中国养猪网" >
        </map>

        <div class="profile-content">
            <div class="audio-container">
                <p><strong>个人介绍音频：</strong></p>
                <audio controls>
                    <source src="your-audio.mp3" type="audio/mpeg">
                    您的浏览器不支持音频播放
                 ></audio>
            </div>
            
            <table class="info-table">
                <tr>
                    <td>姓名：</td>
                    <td>橙子</td>
                </tr>
                <tr>
                    <td>性别：</td>
                    <td>女</td>
                </tr>
                <tr>
                    <td>出生年月：</td>
                    <td>1938年6月</td>
                </tr>
                <tr>
                    <td>学历：</td>
                    <td>幼儿园毕业（专注实践经验积累）</td>
                </tr>
                <tr>
                    <td>职业：</td>
                    <td>资深养猪专家、自营养猪场创始人</td>
                </tr>
                <tr>
                    <td>联系方式：</td>
                    <td>138-xxxx-8888（微信同号）</td>
                </tr>
                <tr>
                    <td>邮箱：</td>
                    <td>chengzi-yangzhu@163.com</td>
                </tr>
                <tr>
                    <td>现居地：</td>
                    <td>河南省南阳市养猪产业园区</td>
                </tr>
                <tr>
                    <td>养猪年限：</td>
                    <td>68年（1955年至今）</td>
                </tr>
                <tr>
                    <td>养殖场规模：</td>
                    <td>占地50亩，年出栏生猪2000余头</td>
                </tr>
            </table>

            <p>自幼对养猪事业怀有浓厚兴趣，1955年创办个人养猪场，至今已有68年养猪经验。始终坚持"科学养殖、绿色环保、品质至上"的经营理念，将一个仅有5头猪的小型养殖场发展成为拥有2000余头生猪的规模化养殖基地。</p>
            <p>精通生猪品种选育、饲料配方研发、疫病防控、养殖环境优化等核心技术，首创"生态循环养殖模式"，实现养殖废弃物资源化利用，获得行业广泛认可。多次受邀参与国内外养猪技术交流会议，分享养殖经验。</p>

            <h4 style="margin: 20px 0 10px; color: #ff7f0e;">核心技能</h4>
            <div class="skill-tags">
                <span class="skill-tag">品种选育</span>
                <span class="skill-tag">饲料配方</span>
                <span class="skill-tag">疫病防控</span>
                <span class="skill-tag">环境优化</span>
                <span class="skill-tag">规模管理</span>
                <span class="skill-tag">生态养殖</span>
                <span class="skill-tag">成本控制</span>
                <span class="skill-tag">技术培训</span>
            </div>

            <h4 style="margin: 20px 0 10px; color: #ff7f0e;">技能雷达图</h4>
            <div class="chart-container">
                <canvas id="skillChart"></canvas>
            </div>
        </div>
    </div>

    <!-- 人生简历 section -->
    <h3 class="section-title" id="人生简历">人生简历</h3>
    <div class="content-section">
        <p>橙子的养猪生涯跨越68年，见证了中国养猪行业从传统散养到规模化、标准化、智能化养殖的发展历程。她的人生简历就是一部中国农村养猪业的发展缩影。</p>
        
        <div class="stats-container">
            <div class="stat-card">
                <div class="stat-number" id="yearCount">68</div>
                <div class="stat-label">养殖年限</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" id="scaleCount">2000+</div>
                <div class="stat-label">年出栏生猪</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" id="awardCount">12</div>
                <div class="stat-label">行业奖项</div>
            </div>
            <div class="stat-card">
                <div class="stat-number" id="techCount">8</div>
                <div class="stat-label">技术专利</div>
            </div>
        </div>

        <div class="timeline">
            <div class="timeline-item">
                <div class="timeline-date">1938年</div>
                <div class="timeline-content">
                    <p>出生于河南省南阳市农村，自幼接触家畜养殖，对猪产生浓厚兴趣</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">1955年（17岁）</div>
                <div class="timeline-content">
                    <p>用积攒的零花钱购买5头仔猪，在自家后院创办小型养猪场，开启养猪生涯</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">1968年（30岁）</div>
                <div class="timeline-content">
                    <p>养殖场规模扩大至50头，率先采用科学喂养方法，养殖效率大幅提升</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">1985年（47岁）</div>
                <div class="timeline-content">
                    <p>养殖场搬迁至新址，占地10亩，年出栏生猪200头，成为当地知名养猪户</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">2000年（62岁）</div>
                <div class="timeline-content">
                    <p>引入规模化养殖技术，养殖场扩建至30亩，年出栏量突破1000头，实现标准化管理</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">2010年（72岁）</div>
                <div class="timeline-content">
                    <p>首创"生态循环养殖模式"，实现养殖废弃物资源化利用，获得政府扶持</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">2020年（82岁）</div>
                <div class="timeline-content">
                    <p>养殖场规模达到50亩，年出栏生猪2000余头，引入智能化养殖设备，实现精准饲喂</p>
                </div>
            </div>
            <div class="timeline-item">
                <div class="timeline-date">至今</div>
                <div class="timeline-content">
                    <p>致力于养猪技术传承与推广，开设养殖技术培训班，培养年轻一代养猪人才</p>
                </div>
            </div>
        </div>

        <div class="iframe-container">
            <iframe name="橙子" scrolling="yes" src="页面书签.html" width="100%" height="250px"></iframe>
        </div>
        
        <a href="https://cn.bing.com/images/search?view=detailV2&ccid=C5dFqHW7&id=236D5951A6DBDFB0F99919090F50BA18170883ED&thid=OIP.C5dFqHW7JS4YNQWSnZgJIgAAAA&mediaurl=https%3a%2f%2fimg95.699pic.com%2fphoto%2f50260%2f9107.jpg_wh300.jpg!%2ffh%2f300%2fquality%2f90&exph=300&expw=450&q=%e5%85%bb%e7%8c%aa%e7%9a%84%e7%85%a7%e7%89%87&FORM=IRPRST&ck=2117AC8CDB9F9B93314EEB038B43E202&selectedIndex=0&itb=0&idpp=overlayview&ajaxhist=0&ajaxserp=0" 
            target="橙子" 
            class="link-btn"
        >
            查看传奇橙子的养猪历程
        </a>
    </div>

    <!-- 获奖经历 section -->
    <h3 class="section-title" id="获奖经历">获奖经历</h3>
    <div class="content-section">
        <p>凭借在养猪领域的突出贡献和技术创新，橙子获得了国内外众多行业奖项和荣誉称号，成为养猪行业的标杆人物。</p>

        <ul class="award-list">
            <li class="award-item">
                <div class="item-header">
                    <span class="item-title">国际最佳养猪奖</span>
                    <span class="item-date">2018年</span>
                </div>
                <div class="item-content">
                    <p>由国际养猪业联合会颁发，表彰其在生态养殖技术创新方面的突出贡献，是中国首位获得该奖项的女性养猪专家。</p>
                </div>
            </li>
            <li class="award-item">
                <div class="item-header">
                    <span class="item-title">全国劳动模范</span>
                    <span class="item-date">2015年</span>
                </div>
                <div class="item-content">
                    <p>由国务院颁发，表彰其在农业生产领域的杰出成就和对农村经济发展的重要贡献。</p>
                </div>
            </li>
            <li class="award-item">
                <div class="item-header">
                    <span class="item-title">国家级农业技术推广奖一等奖</span>
                    <span class="item-date">2012年</span>
                </div>
                <div class="item-content">
                    <p>其研发的"生态循环养殖技术"获得国家级认可，在全国范围内推广应用，取得显著的经济和社会效益。</p>
                </div>
            </li>
            <li class="award-item">
                <div class="item-header">
                    <span class="item-title">河南省养猪行业领军人物</span>
                    <span class="item-date">2010年</span>
                </div>
                <div class="item-content">
                    <p>由河南省畜牧局颁发，表彰其在推动地方养猪产业发展、带动农民增收致富方面的重要作用。</p>
                </div>
            </li>
            <li class="award-item">
                <div class="item-header">
                    <span class="item-title">绿色养殖示范基地</span>
                    <span class="item-date">2008年</span>
                </div>
                <div class="item-content">
                    <p>养殖场被农业部评为国家级绿色养殖示范基地，成为行业环保养殖的典范。</p>
                </div>
            </li>
            <li class="award-item">
                <div class="item-header">
                    <span class="item-title">科技兴农先进个人</span>
                    <span class="item-date">2005年</span>
                </div>
                <div class="item-content">
                    <p>表彰其在农业科技创新、技术推广方面的突出贡献，带动周边养殖户共同发展。</p>
                </div>
            </li>
        </ul>

        <div class="stats-container">
            <div class="stat-card">
                <div class="stat-number">3</div>
                <div class="stat-label">国际奖项</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">5</div>
                <div class="stat-label">国家级奖项</div>
            </div>
            <div class="stat-card">
                <div class="stat-number">4</div>
                <div class="stat-label">省级奖项</div>
            </div>
        </div>
    </div>

    <!-- 实习经历 section -->
    <h3 class="section-title" id="实习经历">实习经历</h3>
    <div class="content-section">
        <p>作为行业资深专家，橙子不仅专注于自身养殖场的发展，还积极为行业培养后备人才，提供实习岗位和技术指导，累计培养了上千名养猪技术人才。</p>

        <ul class="experience-list">
            <li class="experience-item">
                <div class="item-header">
                    <span class="item-title">养猪技术实习基地负责人</span>
                    <span class="item-date">2000年至今</span>
                </div>
                <div class="item-content">
                    <p>与河南农业大学、南阳农业职业学院等院校合作，建立大学生实习基地，每年接收50余名畜牧专业学生实习。负责制定实习计划，亲自指导学生掌握养猪实操技能。</p>
                    <p>实习内容包括：生猪品种识别、饲料配制、疫病诊断与防治、养殖环境调控、规模化养殖管理等。</p>
                </div>
            </li>
            <li class="experience-item">
                <div class="item-header">
                    <span class="item-title">农村创业青年导师</span>
                    <span class="item-date">2015年至今</span>
                </div>
                <div class="item-content">
                    <p>受政府部门邀请，担任农村创业青年导师，指导有志于从事养猪行业的年轻人创业。提供场地考察、方案设计、技术支持、市场对接等全方位指导。</p>
                    <p>已成功指导32名创业青年建立自己的养殖场，其中15家达到规模化养殖水平。</p>
                </div>
            </li>
            <li class="experience-item">
                <div class="item-header">
                    <span class="item-title">养殖技术培训讲师</span>
                    <span class="item-date">2010年至今</span>
                </div>
                <div class="item-content">
                    <p>定期举办养猪技术培训班，面向全国养殖户开展技术培训。累计举办培训班86期，培训学员5000余人次。</p>
                    <p>培训课程包括：科学喂养技术、疫病防控体系建设、生态养殖模式推广、智能化养殖设备应用等。</p>
                </div>
            </li>
            <li class="experience-item">
                <div class="item-header">
                    <span class="item-title">国际养猪技术交流顾问</span>
                    <span class="item-date">2018年至今</span>
                </div>
                <div class="item-content">
                    <p>作为中国养猪行业代表，参与国际养猪技术交流活动，担任技术顾问。曾赴美国、德国、丹麦等养猪强国进行技术交流和考察。</p>
                    <p>将国际先进养殖技术引入国内，结合中国实际情况进行改良和推广，推动中国养猪业与国际接轨。</p>
                </div>
            </li>
            <li class="experience-item">
                <div class="item-header">
                    <span class="item-title">扶贫攻坚技术指导员</span>
                    <span class="item-date">2016-2020年</span>
                </div>
                <div class="item-content">
                    <p>参与国家扶贫攻坚工作，担任贫困地区养猪产业技术指导员。在河南、贵州、云南等省份的贫困县开展技术扶贫工作。</p>
                    <p>帮助12个贫困村建立集体养猪场，带动300余户贫困户脱贫致富，获得政府和群众的高度认可。</p>
                </div>
            </li>
        </ul>

        <div style="margin-top: 30px; text-align: center;">
            <a href="#顶部" class="link-btn">返回顶部</a>
        </div>
    </div>

    <!-- 返回顶部按钮 -->
    <a href="#顶部" class="back-to-top">↑</a>

    <!-- 图片预览模态框 -->
    <div class="modal" id="imageModal">
        <span class="close-modal">&times;</span>
        <img class="modal-content" id="modalImage">
    </div>

    <script>
        // 导航栏激活状态
        const navLinks = document.querySelectorAll('.nav-link');
        const sections = document.querySelectorAll('section-title');

        window.addEventListener('scroll', () => {
            let current = '';
            
            document.querySelectorAll('div[id]').forEach(section => {
                const sectionTop = section.offsetTop;
                const sectionHeight = section.clientHeight;
                if (pageYOffset >= (sectionTop - 200)) {
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === current) {
                    link.classList.add('active');
                }
            });

            // 返回顶部按钮显示/隐藏
            const backToTop = document.querySelector('.back-to-top');
            if (window.pageYOffset > 300) {
                backToTop.classList.add('show');
            } else {
                backToTop.classList.remove('show');
            }

            // 元素滚动动画
            const animateElements = document.querySelectorAll('.profile, .content-section, .section-title');
            animateElements.forEach(element => {
                const elementTop = element.getBoundingClientRect().top;
                const elementVisible = 150;
                if (elementTop < window.innerHeight - elementVisible) {
                    element.classList.add('visible', 'animate');
                }
            });
        });

        // 技能雷达图
        const ctx = document.getElementById('skillChart').getContext('2d');
        const skillChart = new Chart(ctx, {
            type: 'radar',
            data: {
                labels: ['品种选育', '饲料配方', '疫病防控', '环境优化', '规模管理', '生态养殖', '技术培训'],
                datasets: [{
                    label: '技能水平',
                    data: [95, 90, 98, 92, 88, 96, 85],
                    backgroundColor: 'rgba(255, 127, 14, 0.2)',
                    borderColor: 'rgba(255, 127, 14, 1)',
                    borderWidth: 2,
                    pointBackgroundColor: 'rgba(255, 127, 14, 1)',
                    pointRadius: 4
                }]
            },
            options: {
                scales: {
                    r: {
                        beginAtZero: true,
                        max: 100,
                        ticks: {
                            stepSize: 20
                        }
                    }
                },
                plugins: {
                    legend: {
                        display: false
                    },
                    tooltip: {
                        callbacks: {
                            label: function(context) {
                                return context.label + ': ' + context.raw + '分';
                            }
                        }
                    }
                },
                animation: {
                    duration: 2000,
                    easing: 'easeOutQuart'
                }
            }
        });

        // 图片预览模态框
        const modal = document.getElementById('imageModal');
        const img = document.getElementById('profileImage');
        const modalImg = document.getElementById('modalImage');
        const closeBtn = document.querySelector('.close-modal');

        img.addEventListener('click', () => {
            modal.style.display = 'flex';
            modalImg.src = img.src;
            document.body.style.overflow = 'hidden';
        });

        closeBtn.addEventListener('click', () => {
            modal.style.display = 'none';
            document.body.style.overflow = 'auto';
        });

        modal.addEventListener('click', (e) => {
            if (e.target === modal) {
                modal.style.display = 'none';
                document.body.style.overflow = 'auto';
            }
        });

        // 数字计数动画
        function animateValue(id, start, end, duration) {
            const obj = document.getElementById(id);
            const range = end - start;
            const minTimer = 50;
            let stepTime = Math.abs(Math.floor(duration / range));
            
            stepTime = Math.max(stepTime, minTimer);
            
            let startTime = new Date().getTime();
            let endTime = startTime + duration;
            let timer;

            function run() {
                let now = new Date().getTime();
                let remaining = Math.max((endTime - now) / duration, 0);
                let value = Math.round(end - (remaining * range));
                obj.innerHTML = value + (id === 'scaleCount' ? '+' : '');
                if (value == end) {
                    clearInterval(timer);
                }
            }

            timer = setInterval(run, stepTime);
            run();
        }

        // 监听元素是否进入视口
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    if (entry.target.id === 'yearCount') {
                        animateValue('yearCount', 0, 68, 2000);
                        animateValue('scaleCount', 0, 2000, 2000);
                        animateValue('awardCount', 0, 12, 2000);
                        animateValue('techCount', 0, 8, 2000);
                        observer.unobserve(entry.target);
                    }
                }
            });
        }, { threshold: 0.5 });

        observer.observe(document.getElementById('yearCount'));

        // 初始化页面加载动画
        window.addEventListener('load', () => {
            document.querySelector('.profile').classList.add('visible');
            document.querySelector('.section-title').classList.add('animate');
            
            // 平滑滚动到顶部
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });

        // 技能标签点击效果
        const skillTags = document.querySelectorAll('.skill-tag');
        skillTags.forEach(tag => {
            tag.addEventListener('click', () => {
                alert(`技能：${tag.textContent}\n熟练程度：${Math.floor(Math.random() * 10) + 90}%`);
            });
        });
    </script>
</body>
</html>
