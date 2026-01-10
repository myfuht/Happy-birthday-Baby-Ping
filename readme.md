<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>给萍萍的生日祝福 ✨</title>
    <style>
        /* 全局样式重置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "微软雅黑", "PingFang SC", sans-serif;
        }

        /* 页面背景：温柔粉紫渐变，加轻微的爱心纹理 */
        body {
            background: linear-gradient(135deg, #fdf2f8, #f3e8ff);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
        }

        /* 背景爱心小装饰（氛围感） */
        body::before, body::after {
            content: "❤️";
            font-size: 20px;
            position: absolute;
            opacity: 0.3;
            animation: float 6s ease-in-out infinite;
        }
        body::before {
            top: 10%;
            left: 15%;
            animation-delay: 0s;
        }
        body::after {
            bottom: 15%;
            right: 20%;
            animation-delay: 2s;
        }
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }

        /* 登录卡片：圆角+柔阴影，加蝴蝶结装饰 */
        .login-card {
            width: 450px;
            background: white;
            padding: 45px 35px;
            border-radius: 24px;
            box-shadow: 0 10px 30px rgba(236, 72, 153, 0.15);
            position: relative;
            text-align: center;
        }

        /* 顶部蝴蝶结+蛋糕装饰 */
        .login-card::before {
            content: "🎀";
            font-size: 45px;
            position: absolute;
            top: -25px;
            left: 50%;
            transform: translateX(-50%);
            background: white;
            padding: 0 15px;
        }

        /* 生日图片展示区域 */
        .birthday-img {
            width: 100%;
            height: 180px;
            margin-bottom: 25px;
            border-radius: 12px;
            overflow: hidden;
        }
        .birthday-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        /* 标题：专属昵称+生日祝福 */
        .login-title {
            color: #ec4899;
            font-size: 26px;
            margin-bottom: 8px;
        }
        .login-subtitle {
            color: #a855f7;
            font-size: 16px;
            margin-bottom: 35px;
            font-weight: normal;
        }

        /* 输入框组：温柔圆角+聚焦动效 */
        .input-group {
            margin-bottom: 20px;
            text-align: left;
        }
        .input-group label {
            display: block;
            margin-bottom: 8px;
            color: #6b7280;
            font-size: 14px;
        }
        .input-group input {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #fce7f3;
            border-radius: 12px;
            font-size: 15px;
            transition: all 0.3s ease;
        }
        /* 输入框聚焦：粉色边框+爱心小变化 */
        .input-group input:focus {
            outline: none;
            border-color: #ec4899;
            box-shadow: 0 0 0 4px rgba(236, 72, 153, 0.1);
        }

        /* 错误提示样式 */
        .error-tip {
            color: #ef4444;
            font-size: 12px;
            margin-top: 5px;
            display: none;
            text-align: center;
        }

        /* 登录按钮：渐变+hover动效 */
        .login-btn {
            width: 100%;
            padding: 14px;
            background: linear-gradient(90deg, #ec4899, #a855f7);
            color: white;
            border: none;
            border-radius: 12px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 10px;
        }
        .login-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(236, 72, 153, 0.2);
        }

        /* 祝福弹窗：登录后弹出 */
        .modal {
            display: none; /* 默认隐藏 */
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            justify-content: center;
            align-items: center;
            z-index: 999;
        }
        .modal-content {
            background: white;
            padding: 40px 30px;
            border-radius: 20px;
            width: 380px;
            text-align: center;
            animation: pop 0.5s ease;
        }
        @keyframes pop {
            0% { transform: scale(0.8); opacity: 0; }
            100% { transform: scale(1); opacity: 1; }
        }
        .modal-title {
            color: #ec4899;
            font-size: 24px;
            margin-bottom: 15px;
        }
        .modal-text {
            color: #6b7280;
            font-size: 16px;
            line-height: 1.6;
            margin-bottom: 20px;
        }
        .modal-btn {
            padding: 10px 25px;
            background: #a855f7;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 15px;
        }
    </style>
</head>
<body>
    <div class="login-card">
        <!-- 生日主题图片区域 -->
        <div class="birthday-img">
            <!-- 这里用了生日蛋糕的在线图片，你可以替换成萍萍的照片/你们的合照 -->
            <img src="https://picsum.photos/id/291/400/200" alt="给萍萍的生日祝福">
        </div>

        <h1 class="login-title">亲爱的萍萍🎂</h1>
        <h2 class="login-subtitle">生日快乐呀～输入专属口令解锁给你的祝福</h2>
        
        <div class="input-group">
            <label for="username">挚爱萍萍的专属账号 💌</label>
            <input type="text" id="username" placeholder="挚爱萍萍">
        </div>
        
        <div class="input-group">
            <label for="password">生日秘密口令 🔑</label>
            <input type="password" id="password" placeholder="输入5201314解锁祝福">
        </div>

        <!-- 错误提示 -->
        <div class="error-tip" id="errorTip">口令不对哦～再想想❤️</div>
        
        <button class="login-btn" onclick="checkLogin()">解锁生日祝福 ✨</button>
    </div>

    <!-- 祝福弹窗 -->
    <div class="modal" id="wishModal">
        <div class="modal-content">
            <h3 class="modal-title">我的萍萍生日快乐！🎊</h3>
            <p class="modal-text">
                愿我的萍萍永远开心，永远被爱～<br>
                5201314，我爱你一生一世，新的一岁我会一直陪着你 ❤️
            </p>
            <button class="modal-btn" onclick="closeModal()">爱你哟 💋</button>
        </div>
    </div>

    <script>
        // 验证账号密码并显示生日祝福弹窗
        function checkLogin() {
            const username = document.getElementById("username").value.trim();
            const password = document.getElementById("password").value.trim();
            const errorTip = document.getElementById("errorTip");
            
            // 隐藏错误提示
            errorTip.style.display = "none";

            // 验证账号：挚爱萍萍，密码：5201314
            if (username === "挚爱萍萍" && password === "5201314") {
                document.getElementById("wishModal").style.display = "flex";
            } else {
                // 显示错误提示
                errorTip.style.display = "block";
            }
        }

        // 关闭弹窗
        function closeModal() {
            document.getElementById("wishModal").style.display = "none";
            // 清空输入框
            document.getElementById("username").value = "";
            document.getElementById("password").value = "";
            // 隐藏错误提示
            document.getElementById("errorTip").style.display = "none";
        }
    </script>
</body>
</html>
