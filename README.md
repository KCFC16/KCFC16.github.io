
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Yixin · 个人主页</title>
    <!-- Google Fonts & 现代字体方案 -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <!-- Font Awesome 6 (免费图标库) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, sans-serif;
            background: linear-gradient(145deg, #f4f7fc 0%, #e9eef4 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 2rem 1.5rem;
            color: #1a2c3e;
        }

        /* 主卡片 - 现代玻璃质感 + 精致阴影 */
        .profile-card {
            max-width: 860px;
            width: 100%;
            background: rgba(255, 255, 255, 0.96);
            backdrop-filter: blur(2px);
            border-radius: 2.5rem;
            box-shadow: 0 20px 40px -12px rgba(0, 0, 0, 0.15), 0 4px 18px rgba(0, 0, 0, 0.05);
            overflow: hidden;
            transition: transform 0.25s ease, box-shadow 0.3s ease;
        }

        .profile-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 28px 48px -15px rgba(0, 0, 0, 0.2);
        }

        /* 内边距区域 */
        .card-inner {
            padding: 2.5rem 2.2rem;
        }

        /* 头部区域：头像 + 基本信息 */
        .hero {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 2rem;
            margin-bottom: 2.2rem;
            padding-bottom: 1.5rem;
            border-bottom: 2px solid rgba(100, 116, 139, 0.15);
        }

        /* 自定义头像 (纯样式/首字母) */
        .avatar {
            width: 108px;
            height: 108px;
            background: linear-gradient(135deg, #2c7da0, #1f5068);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 12px 22px -8px rgba(28, 78, 100, 0.3);
            transition: all 0.2s;
        }

        .avatar span {
            font-size: 3.2rem;
            font-weight: 600;
            color: white;
            letter-spacing: 1px;
            text-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .title-section h1 {
            font-size: 2.6rem;
            font-weight: 700;
            background: linear-gradient(125deg, #1f5068, #2c7da0);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: -0.5px;
            margin-bottom: 0.3rem;
        }

        .university {
            font-size: 1.25rem;
            font-weight: 500;
            color: #2c5f7a;
            background: #eef2f8;
            display: inline-block;
            padding: 0.25rem 1rem;
            border-radius: 40px;
            backdrop-filter: blur(2px);
            margin-top: 0.25rem;
        }

        .university i {
            margin-right: 8px;
            font-size: 0.95rem;
            color: #2c7da0;
        }

        .location-badge {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            background: transparent;
            font-size: 0.85rem;
            color: #4b6b82;
            margin-top: 0.6rem;
            font-weight: 400;
        }

        /* 简介小语 */
        .mini-bio {
            margin: 1.5rem 0 1rem 0;
            font-size: 1rem;
            line-height: 1.5;
            color: #2c4458;
            background: #f8fafd;
            padding: 0.8rem 1.2rem;
            border-radius: 1.5rem;
            border-left: 4px solid #2c7da0;
            font-weight: 450;
        }

        /* 三个要点区域 (优雅陈列) */
        .highlights {
            margin: 2rem 0 2rem 0;
            display: flex;
            flex-direction: column;
            gap: 1.2rem;
        }

        .info-item {
            display: flex;
            align-items: center;
            gap: 1.2rem;
            background: #ffffff;
            padding: 1rem 1.4rem;
            border-radius: 1.8rem;
            transition: all 0.2s ease;
            border: 1px solid rgba(44, 125, 160, 0.2);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.02);
        }

        .info-item:hover {
            border-color: #2c7da0;
            background: #fefefe;
            transform: translateX(5px);
            box-shadow: 0 8px 20px -12px rgba(44, 125, 160, 0.25);
        }

        .item-emoji {
            font-size: 2.2rem;
            min-width: 54px;
            text-align: center;
            background: #eef3f8;
            width: 54px;
            height: 54px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 30px;
            transition: 0.2s;
        }

        .item-content {
            flex: 1;
            font-size: 1.08rem;
            line-height: 1.45;
            color: #1e2f3c;
            font-weight: 500;
        }

        .item-content strong {
            font-weight: 700;
            color: #155f7c;
            background: linear-gradient(120deg, #e2f0f8, transparent);
            padding: 0 0.2rem;
        }

        .highlight-detail {
            font-weight: 400;
            color: #2c3f4f;
        }

        /* 社交区域 & 联系 */
        .social-links {
            margin-top: 2.5rem;
            padding-top: 1.5rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            gap: 1rem;
            border-top: 2px solid rgba(100, 116, 139, 0.15);
        }

        .social-icons {
            display: flex;
            gap: 1.2rem;
        }

        .social-icons a {
            background: #edf2f7;
            width: 42px;
            height: 42px;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            color: #2c5f7a;
            font-size: 1.3rem;
            transition: all 0.2s ease;
            text-decoration: none;
        }

        .social-icons a:hover {
            background: #2c7da0;
            color: white;
            transform: translateY(-3px);
        }

        .contact-email {
            font-size: 0.85rem;
            background: #eef2f6;
            padding: 0.5rem 1rem;
            border-radius: 40px;
            color: #1f5068;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .contact-email i {
            font-size: 0.9rem;
        }

        .footer-note {
            text-align: center;
            font-size: 0.7rem;
            color: #7f8c9a;
            margin-top: 2rem;
            padding-top: 1rem;
            letter-spacing: 0.3px;
        }

        /* 移动端优化 */
        @media (max-width: 650px) {
            .card-inner {
                padding: 1.8rem;
            }
            .hero {
                flex-direction: column;
                align-items: center;
                text-align: center;
                gap: 1rem;
            }
            .title-section h1 {
                font-size: 2.1rem;
            }
            .info-item {
                padding: 0.9rem 1rem;
                gap: 0.9rem;
            }
            .item-emoji {
                min-width: 46px;
                width: 46px;
                height: 46px;
                font-size: 1.8rem;
            }
            .item-content {
                font-size: 0.96rem;
            }
            .social-links {
                flex-direction: column;
                align-items: center;
            }
        }

        /* 按钮及交互细节 */
        a, button {
            cursor: pointer;
        }

        /* 自定义强调 */
        .tag {
            font-weight: 600;
        }
    </style>
</head>
<body>
    <div class="profile-card">
        <div class="card-inner">
            <!-- 头部： 头像/姓名/学校 -->
            <div class="hero">
                <div class="avatar">
                    <span>YX</span>
                </div>
                <div class="title-section">
                    <h1>Yixin</h1>
                    <div class="university">
                        <i class="fas fa-graduation-cap"></i> Fuzhou University
                    </div>
                    <div class="location-badge">
                        <i class="fas fa-map-marker-alt"></i> Fuzhou, China
                        <i class="fas fa-code-branch" style="margin-left: 10px;"></i> 创新 · 进取
                    </div>
                </div>
            </div>

            <!-- 简短介绍行 (体现个性) -->
            <div class="mini-bio">
                <i class="fas fa-feather-alt" style="margin-right: 8px; color: #2c7da0;"></i> 
                Building digital solutions with curiosity & passion. 热爱技术与创造，乐于探索前沿领域。
            </div>

            <!-- 三大核心条目：完全对应原始需求 (🔭 📚 ⚡) 并预留自定义空间 -->
            <div class="highlights">
                <!-- 1. 工作状态 -->
                <div class="info-item">
                    <div class="item-emoji">🔭</div>
                    <div class="item-content">
                        <span class="highlight-detail">I’m working as </span>
                        <strong>Full-stack Developer & Research Assistant</strong>
                        <span class="highlight-detail"> @ AI Lab / 初创科技团队 — 专注于智能Web应用与数据分析工具。</span>
                    </div>
                </div>
                <!-- 2. 学习内容 -->
                <div class="info-item">
                    <div class="item-emoji">📚</div>
                    <div class="item-content">
                        <span class="highlight-detail">I'm currently learning </span>
                        <strong>MLOps · 云原生架构 (K8s/Docker)  &  Rust</strong>
                        <span class="highlight-detail"> — 构建可扩展、可信赖的智能系统。</span>
                    </div>
                </div>
                <!-- 3. 空闲时光 -->
                <div class="info-item">
                    <div class="item-emoji">⚡</div>
                    <div class="item-content">
                        <span class="highlight-detail">In my free time I </span>
                        <strong>contribute to open source · 打羽毛球 & 摄影</strong>
                        <span class="highlight-detail"> —— 保持好奇，保持快门，拍下代码之外的瞬间。</span>
                    </div>
                </div>
            </div>

            <!-- 社交 & 联系信息 (占位，便于用户替换为自己真实的链接) -->
            <div class="social-links">
                <div class="social-icons">
                    <a href="#" target="_blank" aria-label="GitHub">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="#" target="_blank" aria-label="LinkedIn">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                    <a href="#" target="_blank" aria-label="Twitter / X">
                        <i class="fab fa-twitter"></i>
                    </a>
                    <a href="#" target="_blank" aria-label="个人博客">
                        <i class="fas fa-blog"></i>
                    </a>
                </div>
                <div class="contact-email">
                    <i class="far fa-envelope"></i> 
                    yixin@fzu.edu · 联系交流
                </div>
            </div>

            <!-- 底部装饰 -->
            <div class="footer-note">
                <i class="far fa-smile-wink"></i> 可随意编辑文本、替换链接 — 保持真实，展现自我
            </div>
        </div>
    </div>

    <!-- 以下是供用户轻松编辑的注释区域 (仅视觉提示，实际不影响显示)  
         您可以随时修改:
         - 姓名「Yixin」, 学校「Fuzhou University」
         - 三个主要模块内容: 工作描述/ 学习内容/ 空闲爱好 (直接修改 .item-content 中的文字即可)
         - 社交链接: 将 # 替换为真实的GitHub/Linkedin等个人主页
         - 邮箱: 把yixin@fzu.edu改为您常用邮箱
    -->
</body>
</html>
