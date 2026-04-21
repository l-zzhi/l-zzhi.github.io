<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
    <title>🌸 测测你是晟斗士中的哪一种 · 粉丝图鉴</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: system-ui, 'Segoe UI', 'Helvetica Neue', 'Noto Sans', sans-serif;
        }
        body {
            /* 背景图片 (您的图片) */
            background-image: url('https://s41.ax1x.com/2026/04/21/peg5TqU.jpg');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            background-color: #fad4e4;  /* 后备粉色 */
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 16px;
        }
        /* 主卡片 —— 大幅提高透明度，让背景图透出更清晰 */
        .test-container {
            max-width: 760px;
            width: 100%;
            background: rgba(255, 255, 255, 0.2);       /* 原为0.85，改为0.2 */
            backdrop-filter: blur(12px);                 /* 增强毛玻璃 */
            -webkit-backdrop-filter: blur(12px);
            border-radius: 36px;
            box-shadow: 0 20px 40px -8px rgba(180, 80, 120, 0.25);
            padding: 28px 24px;
            border: 1px solid rgba(255, 220, 230, 0.5);
        }
        h1 {
            display: flex;
            align-items: baseline;
            justify-content: space-between;
            font-weight: 650;
            font-size: 1.8rem;
            color: #832a4c;
            margin-bottom: 8px;
            padding-bottom: 16px;
            border-bottom: 2px solid rgba(251, 182, 206, 0.7);
        }
        h1 small {
            font-size: 1rem;
            font-weight: 500;
            color: #b95c7c;
        }
        .progress-container {
            display: flex;
            align-items: center;
            gap: 12px;
            margin: 12px 0 20px;
        }
        .progress-label {
            font-weight: 600;
            color: #832a4c;
            background: rgba(255, 224, 235, 0.6);
            padding: 5px 16px;
            border-radius: 30px;
            font-size: 0.9rem;
            backdrop-filter: blur(4px);
        }
        .progress-track {
            flex: 1;
            height: 8px;
            background: rgba(251, 196, 214, 0.6);
            border-radius: 20px;
            overflow: hidden;
        }
        .progress-fill {
            height: 100%;
            width: 4%;
            background: #d45c86;
            border-radius: 20px;
            transition: width 0.25s;
        }
        /* 题目卡片 —— 同样更透明 */
        .question-card {
            background: rgba(255, 240, 245, 0.35);      /* 原0.35左右，保持透感 */
            backdrop-filter: blur(8px);
            -webkit-backdrop-filter: blur(8px);
            border-radius: 32px;
            padding: 28px 24px;
            margin: 16px 0 24px;
            box-shadow: 0 8px 18px -6px rgba(180, 60, 100, 0.15);
            border: 1px solid rgba(251, 193, 212, 0.6);
        }
        .q-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 24px;
        }
        .q-num-badge {
            background: #e8749a;
            color: white;
            font-weight: 700;
            width: 42px;
            height: 42px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 30px;
            font-size: 1.2rem;
            box-shadow: 0 4px 6px rgba(200, 70, 110, 0.3);
        }
        .q-text {
            font-size: 1.45rem;
            font-weight: 700;
            line-height: 1.35;
            color: #63203a;
            flex: 1;
            text-shadow: 0 1px 3px rgba(255,255,255,0.5);
        }
        .options-list {
            display: flex;
            flex-direction: column;
            gap: 14px;
        }
        .option-item {
            display: flex;
            align-items: flex-start;
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(4px);
            -webkit-backdrop-filter: blur(4px);
            border-radius: 24px;
            padding: 16px 20px;
            border: 1.5px solid rgba(251, 182, 206, 0.8);
            box-shadow: 0 3px 0 #e9a5bc;
            cursor: pointer;
            transition: all 0.15s;
        }
        .option-item.selected {
            background: rgba(253, 227, 236, 0.9);
            border-color: #d45c86;
            box-shadow: 0 3px 0 #bc4e76;
        }
        .option-item input[type="radio"] {
            appearance: none;
            -webkit-appearance: none;
            width: 22px;
            height: 22px;
            border: 2px solid #e28fb0;
            border-radius: 50%;
            margin-right: 18px;
            margin-top: 2px;
            flex-shrink: 0;
            transition: 0.1s;
        }
        .option-item input[type="radio"]:checked {
            border-color: #bc4e76;
            background: #bc4e76;
            box-shadow: inset 0 0 0 5px white, 0 0 0 1px #bc4e76;
        }
        .opt-letter {
            font-weight: 800;
            font-size: 1.5rem;
            color: #a13b63;
            width: 32px;
            text-align: center;
            margin-right: 12px;
            flex-shrink: 0;
        }
        .opt-desc {
            font-size: 1.05rem;
            color: #4a2233;
            flex: 1;
            line-height: 1.4;
            font-weight: 500;
        }
        .nav-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 8px;
        }
        .nav-btn {
            background: rgba(255, 224, 235, 0.8);
            backdrop-filter: blur(4px);
            border: none;
            padding: 12px 28px;
            border-radius: 50px;
            font-weight: 600;
            font-size: 1.1rem;
            color: #832a4c;
            box-shadow: 0 4px 0 #e9a5bc;
            cursor: pointer;
            transition: 0.1s;
            border: 1px solid rgba(251, 193, 212, 0.8);
            min-width: 120px;
        }
        .nav-btn:disabled {
            opacity: 0.4;
            box-shadow: 0 2px 0 #e9a5bc;
            transform: translateY(2px);
            pointer-events: none;
        }
        .nav-btn:hover:not(:disabled) {
            background: rgba(251, 196, 214, 0.9);
            transform: translateY(-1px);
            box-shadow: 0 5px 0 #d989a8;
        }
        .nav-btn:active:not(:disabled) {
            transform: translateY(3px);
            box-shadow: 0 1px 0 #d989a8;
        }
        .submit-btn {
            background: #d45c86;
            color: white;
            box-shadow: 0 5px 0 #a63a62;
            border: none;
            padding: 14px 32px;
            font-size: 1.2rem;
        }
        .submit-btn:hover {
            background: #e0709a;
        }
        .reset-btn {
            background: transparent;
            border: none;
            color: #a13b63;
            text-decoration: underline;
            font-size: 1rem;
            font-weight: 500;
            padding: 8px 12px;
            cursor: pointer;
        }
        .action-group {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 20px 0 8px;
        }
        /* 结果面板 —— 同样提高透明度 */
        .result-panel {
            margin-top: 10px;
            background: rgba(255, 240, 245, 0.3);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-radius: 32px;
            padding: 28px 24px;
            border-left: 8px solid #d45c86;
            box-shadow: 0 8px 20px -6px rgba(180, 60, 100, 0.2);
        }
        .result-title {
            font-size: 1.9rem;
            font-weight: 700;
            color: #63203a;
            margin-bottom: 20px;
            text-align: center;
            text-shadow: 0 1px 4px rgba(255,255,255,0.6);
        }
        .chart-container {
            display: flex;
            justify-content: center;
            margin: 10px 0 20px;
        }
        canvas {
            max-width: 240px;
            width: 100%;
            height: auto;
            filter: drop-shadow(0 4px 8px rgba(0,0,0,0.1));
        }
        .legend-area {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 18px 30px;
            margin: 16px 0 10px;
        }
        .legend-item {
            display: flex;
            align-items: center;
            gap: 8px;
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(4px);
            padding: 5px 18px;
            border-radius: 40px;
            box-shadow: 0 2px 6px rgba(200,80,120,0.1);
        }
        .color-dot {
            width: 18px;
            height: 18px;
            border-radius: 18px;
        }
        .type-desc-box {
            margin-top: 20px;
        }
        .type-card {
            background: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(4px);
            border-radius: 24px;
            padding: 18px 20px;
            margin-bottom: 16px;
            box-shadow: 0 3px 10px rgba(190, 80, 120, 0.1);
            border: 1px solid rgba(251, 193, 212, 0.7);
        }
        .type-name {
            font-size: 1.5rem;
            font-weight: 700;
            color: #a13b63;
            margin-bottom: 6px;
        }
        .type-quote {
            font-style: italic;
            color: #b95c7c;
            margin: 8px 0;
            padding-left: 14px;
            border-left: 4px solid #e8749a;
        }
        .type-desc {
            color: #4a2233;
            line-height: 1.5;
        }
        .footer-note {
            font-size: 0.8rem;
            color: #b95c7c;
            text-align: center;
            margin-top: 24px;
            background: rgba(255,255,240,0.3);
            padding: 6px 12px;
            border-radius: 40px;
            backdrop-filter: blur(4px);
        }
        .hidden {
            display: none;
        }
        #quizSection { transition: opacity 0.2s; }
        @media (max-width: 500px) {
            .test-container { padding: 20px 16px; }
            h1 { font-size: 1.5rem; }
            .q-text { font-size: 1.25rem; }
            .opt-desc { font-size: 0.95rem; }
            .option-item { padding: 14px 16px; }
        }
    </style>
</head>
<body>
<div class="test-container">
    <h1>🌸 晟斗士·属性罗盘 <small id="pageIndicator">1/24</small></h1>
    
    <!-- 答题区域 (分页) -->
    <div id="quizSection">
        <div class="progress-container">
            <span class="progress-label" id="progressText">第1题</span>
            <div class="progress-track">
                <div class="progress-fill" id="progressFill" style="width: 4.16%;"></div>
            </div>
        </div>
        <div id="questionArea" class="question-card"></div>
        <div class="nav-row">
            <button class="nav-btn" id="prevBtn" disabled>← 上一题</button>
            <button class="nav-btn" id="nextBtn">下一题 →</button>
        </div>
        <div class="action-group">
            <button class="nav-btn submit-btn" id="submitBtn" style="display: none;">🔮 查看我的晟斗士属性</button>
            <button class="reset-btn" id="resetBtn">↻ 重新开始</button>
        </div>
    </div>

    <!-- 结果展示区域 (独立，已移除返回按钮) -->
    <div id="resultSection" class="result-panel" style="display: none;">
        <div class="result-title" id="resultMainTitle">✨ 你的晟斗士图鉴</div>
        <div class="chart-container">
            <canvas id="resultChart" width="240" height="240"></canvas>
        </div>
        <div class="legend-area" id="legendArea"></div>
        <div class="type-desc-box" id="typeDescriptions"></div>
        <!-- 已移除返回修改答案按钮 -->
    </div>
    <div class="footer-note">💗 每一份爱都有独特的形状 · 晟斗士图鉴</div>
</div>

<script>
    (function(){
        // ---------- 题库 (24题) 粉色主题，标签保留 ----------
        const questions = [
            { text: "当一天的疲惫缓缓落幕，你最想借由哪种方式为自己“回血”？", options: [
                { letter: "A", desc: "翻开过往的舞台影像，沉醉于他出众的容颜，为他极具魅力的舞台与悦耳的歌声而心潮澎湃。", tags: ["舞台粉","歌手粉","颜粉"] },
                { letter: "B", desc: "潜入超话浏览今日的动态，用签到、点赞、评论与转发，默默为他垒起坚实的数据。", tags: ["数据粉","氪金粉","安利粉"] },
                { letter: "C", desc: "穿梭于各个软件之间，寻觅他今日更新的踪迹，在陪伴中汲取温暖，将爱意化作创作。", tags: ["物料粉","女友粉","产出粉"] },
                { letter: "D", desc: "点开音乐软件，戴上耳机，在单曲循环他的歌声里寻得一片宁静。", tags: ["歌手粉","舞台粉","氪金粉"] }
            ]},
            { text: "如果要向一个不了解李晟的人安利她，你会首先选择哪一项？", options: [
                { letter: "A", desc: "介绍某部剧里很有魅力的角色，精细的演技。", tags: ["演员粉","安利粉","物料粉"] },
                { letter: "B", desc: "翻出某个采访里你觉得很有道理很哲学的话，让你从中学到/跟你一模一样的部分。", tags: ["访谈粉","安利粉","产出粉"] },
                { letter: "C", desc: "令人着迷的颜值，女神好伟大的一张脸。", tags: ["颜粉","女友粉","安利粉"] },
                { letter: "D", desc: "光彩四射的舞台，谁看谁爱上的满分爱豆。", tags: ["歌手粉","舞台粉","安利粉"] }
            ]},
            { text: "晚上躺在床上刷手机，你最可能在干什么？", options: [
                { letter: "A", desc: "凌晨零点抢超话首签，连签也不能断。", tags: ["数据粉","氪金粉","安利粉"] },
                { letter: "B", desc: "在各个软件寻找她的踪迹，到处搜索刷视频。", tags: ["产出粉","颜粉","物料粉"] },
                { letter: "C", desc: "打开那部看了无数遍的剧继续第n遍观看。", tags: ["演员粉","颜粉","妈粉"] },
                { letter: "D", desc: "听歌，好美妙动听悦耳的声音。", tags: ["歌手粉","舞台粉","数据粉"] }
            ]},
            { text: "她的新剧终于播出了，你的状态是：", options: [
                { letter: "A", desc: "疯狂截图她的绝美造型，发朋友圈发微博发给朋友猛夸。", tags: ["颜粉","物料粉","安利粉"] },
                { letter: "B", desc: "专心投入剧情，等结束后马上发长篇剧评夸演技。", tags: ["安利粉","演员粉","数据粉"] },
                { letter: "C", desc: "追剧进度完全靠刷社交平台，根本不打开播放器，专门在超话里存别人整理的高清cut和动图。", tags: ["物料粉","颜粉","产出粉"] },
                { letter: "D", desc: "对搭戏角色过敏，只要别的角色跟她有互动，就在屏幕前疯狂吃醋或代入。", tags: ["妈粉","女友粉","演员粉"] }
            ]},
            { text: "如果她毫无预兆地突然发动态（微博抖音小红书等），你的第一反应是：", options: [
                { letter: "A", desc: "疯狂点赞评论转发，立刻去评论区抢前排热评。", tags: ["安利粉","数据粉","女友粉"] },
                { letter: "B", desc: "赶紧点开大图，看看图文内容，夸赞美貌。", tags: ["颜粉","物料粉","产出粉"] },
                { letter: "C", desc: "马上截图发给同担并疯狂尖叫。", tags: ["安利粉","物料粉","颜粉"] },
                { letter: "D", desc: "仔细查看发表的文字或配文，开始逐字研究。", tags: ["产出粉","颜粉","数据粉"] }
            ]},
            { text: "她在工作（剧组综艺等）中遭遇了不公正的舆论抹黑，你会：", options: [
                { letter: "A", desc: "迅速整理时间线和逻辑图，发长文替她澄清。", tags: ["安利粉","妈粉","数据粉"] },
                { letter: "B", desc: "组织粉丝群，有条不紊地带话题、控评、做数据。", tags: ["数据粉","安利粉","产出粉"] },
                { letter: "C", desc: "气得睡不着觉，觉得全天下都在欺负我的宝贝。", tags: ["妈粉","女友粉","氪金粉"] },
                { letter: "D", desc: "根本不跟黑粉废话，直接熟练地举报。", tags: ["数据粉","妈粉","氪金粉"] }
            ]},
            { text: "她突然宣布要举办一场个人演唱会，你最期待的是：", options: [
                { letter: "A", desc: "演唱会舞台上的顶级舞美。", tags: ["走路粉","舞台粉","颜粉"] },
                { letter: "B", desc: "全开麦的歌声加上音响对你耳朵造成的冲击。", tags: ["舞台粉","歌手粉","颜粉"] },
                { letter: "C", desc: "演唱会上的新造型，太美了。", tags: ["妈粉","颜粉","安利粉"] },
                { letter: "D", desc: "一些能够触及你心底的talking。", tags: ["访谈粉","颜粉","舞台粉"] }
            ]},
            { text: "如果你的手机壁纸是她，那张图具体是什么样的她？", options: [
                { letter: "A", desc: "舞台上的她", tags: ["舞台粉","颜粉","女友粉"] },
                { letter: "B", desc: "生活中的她", tags: ["颜粉","女友粉","妈粉"] },
                { letter: "C", desc: "一套艺术图中的她", tags: ["颜粉","数据粉","氪金粉"] },
                { letter: "D", desc: "剧中的角色", tags: ["演员粉","颜粉","数据粉"] }
            ]},
            { text: "你手机相册里关于她的内容，占比最多的是：", options: [
                { letter: "A", desc: "各种活动的高清精修图和神级生图。", tags: ["颜粉","物料粉","舞台粉"] },
                { letter: "B", desc: "她的各种舞台的截图和动图。", tags: ["舞台粉","歌手粉","产出粉"] },
                { letter: "C", desc: "各种采访时的金句截图和表情包。", tags: ["访谈粉","安利粉","产出粉"] },
                { letter: "D", desc: "她日常生活中的随手拍和Vlog截图。", tags: ["物料粉","妈粉","女友粉"] }
            ]},
            { text: "你的手机内存又双叒叕报警了，必须清理一些东西，你会怎么删？", options: [
                { letter: "A", desc: "只保留最高清的生图和最绝的舞台直拍，糊图和旧物料全删。", tags: ["物料粉","颜粉","舞台粉"] },
                { letter: "B", desc: "删掉那些单纯的风景照或静图，保留有情节的Vlog和访谈片段。", tags: ["访谈粉","演员粉","妈粉"] },
                { letter: "C", desc: "把日常听的她的歌转存到云盘，手机里只留现场live版。", tags: ["歌手粉","舞台粉","产出粉"] },
                { letter: "D", desc: "根本舍不得删！直接去换一个内存大的新手机。", tags: ["氪金粉","物料粉","女友粉"] }
            ]},
            { text: "在所有关于她的“二创作品”中，哪种形式最轻易打动你的心？", options: [
                { letter: "A", desc: "用她绝美的图片配上极具氛围感BGM的混剪视频。", tags: ["颜粉","安利粉","女友粉"] },
                { letter: "B", desc: "把她不同时期的采访音频拼凑起来，剪辑成一段“心路历程”。", tags: ["访谈粉","安利粉","产出粉"] },
                { letter: "C", desc: "纯享版的舞台多机位切换混剪，展现舞台上的绝对实力与魅力。", tags: ["歌手粉","舞台粉","安利粉"] },
                { letter: "D", desc: "每一个剧中角色的混剪，每一个构成她一部分的碎片。", tags: ["演员粉","安利粉","产出粉"] }
            ]},
            { text: "如果她要出一本自传或者个人写真书，你最希望里面包含什么内容？", options: [
                { letter: "A", desc: "大量绝美未公开的高清照和时尚大片。", tags: ["颜粉","物料粉","氪金粉"] },
                { letter: "B", desc: "她亲笔写的内心独白和从业心路历程。", tags: ["访谈粉","演员粉","妈粉"] },
                { letter: "C", desc: "生活中的真实的她。", tags: ["物料粉","女友粉","产出粉"] },
                { letter: "D", desc: "详细记录她每一场经典舞台背后的排练日记。", tags: ["舞台粉","歌手粉","产出粉"] }
            ]},
            { text: "你觉得她对你来说，别人最不可替代的属于她的一部分是什么？", options: [
                { letter: "A", desc: "情绪的稳定剂。听到她开口唱歌的那个瞬间，世界就安静的只剩她的歌声。", tags: ["歌手粉","舞台粉","妈粉"] },
                { letter: "B", desc: "信仰的实体化。看着她一步一个脚印，这就是努力和坚持的意义。", tags: ["演员粉","舞台粉","妈粉"] },
                { letter: "C", desc: "灵感的来源。她的每一个眼神、每一场戏，每一个角色，都能唤醒你表达的欲望。", tags: ["舞台粉","演员粉","访谈粉"] },
                { letter: "D", desc: "伤痛的避难所。只要想到这个世界上有她的存在，就觉得所有痛都能被治愈。", tags: ["女友粉","妈粉","安利粉"] }
            ]},
            { text: "当你遇到现实生活中的挫折时，你通常会想起怎么样的“她”来治愈自己？", options: [
                { letter: "A", desc: "反复观看你最爱的几次现场，用磅礴的能量将负面情绪逐渐赶走。", tags: ["歌手粉","舞台粉","数据粉"] },
                { letter: "B", desc: "翻出她以前的采访，看她在日常生活中是如何调节自己情绪，面对生活的。", tags: ["访谈粉","演员粉","安利粉"] },
                { letter: "C", desc: "打开她的社交帐号，一条一条翻看她的动态来调节自己的情绪。", tags: ["物料粉","女友粉","产出粉"] },
                { letter: "D", desc: "脑海里回放她在某部剧中饰演的某个角色的台词，想起那个角色面对挫折是如果应对的。", tags: ["演员粉","产出粉","舞台粉"] }
            ]},
            { text: "你觉得她最迷人的瞬间是在什么时候？", options: [
                { letter: "A", desc: "聚光灯亮起，舞台中间那个掌控一切的她。", tags: ["舞台粉","歌手粉","颜粉"] },
                { letter: "B", desc: "采访时别人问她问题，她分析解剖问题，进行深度回答。", tags: ["访谈粉","演员粉","安利粉"] },
                { letter: "C", desc: "她完全沉浸在角色里，连眼神都变了的时候。", tags: ["演员粉","访谈粉","产出粉"] },
                { letter: "D", desc: "只要她出现在我的视线里，每一秒都迷人。", tags: ["女友粉","颜粉","妈粉"] }
            ]},
            { text: "如果可以和她一起度过一天，你会和她一起做什么？", options: [
                { letter: "A", desc: "她带你去了解她的关于某个地方的故事。", tags: ["访谈粉","女友粉","物料粉"] },
                { letter: "B", desc: "带她去某个地方，向她讲述你在那个地方的故事。", tags: ["产出粉","女友粉","访谈粉"] },
                { letter: "C", desc: "去她拍戏的片场，看她一天的工作是怎么样的。", tags: ["演员粉","物料粉","妈粉"] },
                { letter: "D", desc: "一起去海边/游乐场，然后一起做饭吃饭，一起聊天。", tags: ["女友粉","妈粉","物料粉"] }
            ]},
            { text: "在你的世界里，你觉得“她”和“你”是什么关系？", options: [
                { letter: "A", desc: "她是你一位远方的朋友。在你需要时会及时出现。", tags: ["女友粉","安利粉","物料粉"] },
                { letter: "B", desc: "她是你的“赛博女儿”。陪着她一路走来看着她越来越好，你内心很欣慰。", tags: ["妈粉","氪金粉","数据粉"] },
                { letter: "C", desc: "她是你的镜子。你透过她看到自己，并将她作为追随的方向。", tags: ["访谈粉","产出粉","演员粉"] },
                { letter: "D", desc: "她是远方的篝火，你是迷失的旅人。她为你指引方向。", tags: ["歌手粉","舞台粉","安利粉"] }
            ]},
            { text: "回顾你追她的这段时光，你觉得你获得的最大收获是：", options: [
                { letter: "A", desc: "认识了各种职业，天南海北的不同的朋友", tags: ["数据粉","氪金粉","安利粉"] },
                { letter: "B", desc: "学到了很多为人处世的哲理和清醒的价值观。", tags: ["访谈粉","演员粉","妈粉"] },
                { letter: "C", desc: "意外地开发了自己的画画/剪辑/写作技能。", tags: ["产出粉","舞台粉","演员粉"] },
                { letter: "D", desc: "找到了精神寄托，感觉她给了我一种陪伴的力量。", tags: ["女友粉","妈粉","物料粉"] }
            ]},
            { text: "在硕大的宇宙中…她对你的意义是什么？", options: [
                { letter: "A", desc: "在偌大的宇宙里，你用你的爱为她建造了一座只有她能看见的。", tags: ["女友粉","产出粉","访谈粉"] },
                { letter: "B", desc: "很多个行星聚在一起，使得你们一起更亮。", tags: ["数据粉","安利粉","氪金粉"] },
                { letter: "C", desc: "宇宙再大，也比不上她在你心里的份量大。", tags: ["颜粉","物料粉","走路粉"] },
                { letter: "D", desc: "你在宇宙中时时刻刻都能够想起的人。", tags: ["歌手粉","舞台粉","演员粉"] }
            ]},
            { text: "如果让你用一句话概括你对她的感情，会是：", options: [
                { letter: "A", desc: "她是你平淡生活里的那一束光。", tags: ["女友粉","产出粉","物料粉"] },
                { letter: "B", desc: "看着她一路走来，就像看着自己亲手养大的女儿。", tags: ["妈粉","氪金粉","数据粉"] },
                { letter: "C", desc: "她是一个值得被大众看到的优秀的演员，歌手，艺术家。", tags: ["安利粉","演员粉","访谈粉"] },
                { letter: "D", desc: "她像生活中一个知己朋友。", tags: ["访谈粉","女友粉","安利粉"] }
            ]},
            { text: "你觉得李晟好看吗？", options: [
                { letter: "A", desc: "这还用问？", tags: ["颜粉","女友粉","妈粉"] },
                { letter: "B", desc: "这简直是女神。", tags: ["颜粉","安利粉","物料粉"] },
                { letter: "C", desc: "好看。", tags: ["颜粉","舞台粉","演员粉"] },
                { letter: "D", desc: "超级好看。", tags: ["颜粉","歌手粉","氪金粉"] }
            ]},
            { text: "你爱李晟吗？", options: [ { letter: "A", desc: "爱。", tags: ["女友粉","妈粉","安利粉"] } ] },
            { text: "你会继续爱李晟吗？", options: [ { letter: "A", desc: "会。", tags: ["女友粉","妈粉","数据粉"] } ] },
            { text: "陪李晟去疯跑。", options: [ { letter: "A", desc: "好。", tags: ["女友粉","妈粉","物料粉"] } ] }
        ];

        const typeDescriptions = {
            "走路粉": { name:"🚶 走路粉", quote:"佛系随缘，云端漫游", desc:"你对TA的喜爱是松弛且自由的。不争不抢，不控评不打榜…你的爱没有KPI。" },
            "访谈粉": { name:"🎙️ 访谈粉", quote:"灵魂捕手，深度迷恋", desc:"你更沉迷于TA在访谈里展现的思想和灵魂。TA的某句话可能曾经深深治愈过你。" },
            "颜粉": { name:"✨ 颜粉", quote:"视觉动物，纯纯舔颜", desc:"入坑理由千千万，只有TA的脸是你的万有引力。内存里存满了TA的各种神图。" },
            "演员粉": { name:"🎬 演员粉", quote:"显微镜女孩，作品至上", desc:"你是拉片小能手，热衷于分析微表情、眼神变化。最好的追星方式就是用角色说话。" },
            "舞台粉": { name:"💃 舞台粉", quote:"舞台暴君，气场信徒", desc:"只有在舞台上发光的TA，才能让你彻底疯狂。台下的TA或许软萌，但台上的TA必须是大魔王。" },
            "歌手粉": { name:"🎤 歌手粉", quote:"听觉狂热，原声信徒", desc:"你对TA的声音有着近乎生理性的迷恋。TA的音色就是你的最强安眠药和兴奋剂。" },
            "数据粉": { name:"📊 数据粉", quote:"无情打投机，榜单卷王", desc:"你是饭圈里最硬核的“赛博包工头”。成就感来自于看到TA的名字变成榜首。" },
            "妈粉": { name:"🤱 妈粉", quote:"无私慈爱，满眼心疼", desc:"在TA面前自动激活了老母亲的DNA。你的爱里没有占有欲，只有沉甸甸的牵挂。" },
            "女友粉": { name:"💘 女友粉", quote:"极致双标，幻想狂徒", desc:"你的爱带着强烈的排他性。在心里已经和TA过了大半辈子。" },
            "物料粉": { name:"📦 物料粉", quote:"电子仓鼠，快乐永动机", desc:"你是追星界的档案馆馆长。手机里按日期分门别类存满了TA的物料。" },
            "产出粉": { name:"🎨 产出粉", quote:"为爱发电，造梦工匠", desc:"你把对TA的喜爱转化成了实实在在的作品。用双手为TA搭建了一个绚丽的乌托邦。" },
            "氪金粉": { name:"💰 氪金粉", quote:"真金白银，钞能力战士", desc:"爱TA，就给TA花钱。你的账单，就是最硬核的告白。" },
            "安利粉": { name:"📣 安利粉", quote:"赛博传销，人形扩音器", desc:"你的终极目标是让全世界都知道TA有多好！逢人就发TA的美图和直拍视频。" }
        };

        const totalQ = questions.length;
        let currentIndex = 0;
        let answers = new Array(totalQ).fill(null);
        
        const quizSection = document.getElementById('quizSection');
        const resultSection = document.getElementById('resultSection');
        const questionArea = document.getElementById('questionArea');
        const prevBtn = document.getElementById('prevBtn');
        const nextBtn = document.getElementById('nextBtn');
        const submitBtn = document.getElementById('submitBtn');
        const resetBtn = document.getElementById('resetBtn');
        const pageIndicator = document.getElementById('pageIndicator');
        const progressText = document.getElementById('progressText');
        const progressFill = document.getElementById('progressFill');

        function renderQuestion(index) {
            const q = questions[index];
            const selected = answers[index];
            let html = `<div class="q-header"><span class="q-num-badge">${index+1}</span><div class="q-text">${q.text}</div></div><div class="options-list">`;
            q.options.forEach((opt, optIdx) => {
                const isChecked = (selected && selected.letter === opt.letter);
                html += `<label class="option-item ${isChecked ? 'selected' : ''}">
                    <input type="radio" name="question" value="${opt.letter}" data-opt-index="${optIdx}" ${isChecked ? 'checked' : ''}>
                    <span class="opt-letter">${opt.letter}</span>
                    <span class="opt-desc">${opt.desc}</span>
                </label>`;
            });
            html += `</div>`;
            questionArea.innerHTML = html;
            document.querySelectorAll('input[name="question"]').forEach(radio => {
                radio.addEventListener('change', (e) => {
                    const optIndex = e.target.dataset.optIndex;
                    answers[currentIndex] = questions[currentIndex].options[optIndex];
                    document.querySelectorAll('.option-item').forEach(item => {
                        const inp = item.querySelector('input');
                        if (inp && inp.checked) item.classList.add('selected');
                        else item.classList.remove('selected');
                    });
                    updateNavAndProgress();
                });
            });
            updateNavAndProgress();
        }

        function updateNavAndProgress() {
            const cur = currentIndex + 1;
            pageIndicator.innerText = `${cur}/${totalQ}`;
            progressText.innerText = `第${cur}题`;
            progressFill.style.width = `${(cur / totalQ) * 100}%`;
            prevBtn.disabled = (currentIndex === 0);
            const isLast = (currentIndex === totalQ - 1);
            nextBtn.style.display = isLast ? 'none' : 'inline-block';
            submitBtn.style.display = isLast ? 'inline-block' : 'none';
        }

        function goToPage(newIdx) {
            if (newIdx < 0 || newIdx >= totalQ) return;
            currentIndex = newIdx;
            renderQuestion(currentIndex);
        }

        function calculateScores() {
            const map = new Map();
            answers.forEach(opt => { if(opt) opt.tags.forEach(t => map.set(t, (map.get(t)||0)+1)); });
            return Array.from(map.entries()).sort((a,b) => b[1]-a[1]);
        }

        function drawPieChart(topTags) {
            const canvas = document.getElementById('resultChart');
            const ctx = canvas.getContext('2d');
            const total = topTags.reduce((s, t) => s + t[1], 0);
            const colors = ['#e8749a', '#f6a5c1', '#fbc1d4'];
            let start = -Math.PI/2;
            ctx.clearRect(0,0,240,240);
            topTags.forEach((tag, i) => {
                const angle = (tag[1]/total) * 2 * Math.PI;
                ctx.beginPath();
                ctx.fillStyle = colors[i % colors.length];
                ctx.moveTo(120,120);
                ctx.arc(120,120,100, start, start+angle);
                ctx.closePath();
                ctx.fill();
                start += angle;
            });
            ctx.beginPath();
            ctx.fillStyle = '#fff0f5';
            ctx.arc(120,120,55,0,2*Math.PI);
            ctx.fill();
        }

        function showResult() {
            if (answers.some(a => a === null)) {
                alert('请完成所有题目后再查看结果～');
                const idx = answers.findIndex(a => a === null);
                if (idx !== -1) goToPage(idx);
                return;
            }
            const sorted = calculateScores();
            const top3 = sorted.slice(0,3);
            drawPieChart(top3);
            
            const legend = document.getElementById('legendArea');
            const colors = ['#e8749a', '#f6a5c1', '#fbc1d4'];
            legend.innerHTML = top3.map((t,i) => {
                const pct = ((t[1] / top3.reduce((s,x)=>s+x[1],0))*100).toFixed(1);
                return `<div class="legend-item"><span class="color-dot" style="background:${colors[i]}"></span> ${t[0]} ${pct}%</div>`;
            }).join('');
            
            const descBox = document.getElementById('typeDescriptions');
            descBox.innerHTML = top3.map(t => {
                const info = typeDescriptions[t[0]] || { name:t[0], quote:"独一无二", desc:"每一种喜欢都值得珍惜。" };
                return `<div class="type-card"><div class="type-name">${info.name}</div>
                    <div class="type-quote">“${info.quote}”</div>
                    <div class="type-desc">${info.desc}</div></div>`;
            }).join('');
            
            quizSection.style.display = 'none';
            resultSection.style.display = 'block';
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function resetAll() {
            if (confirm('重新开始？进度会丢失。')) {
                answers = new Array(totalQ).fill(null);
                currentIndex = 0;
                quizSection.style.display = 'block';
                resultSection.style.display = 'none';
                renderQuestion(0);
            }
        }

        prevBtn.addEventListener('click', () => { if (currentIndex>0) goToPage(currentIndex-1); });
        nextBtn.addEventListener('click', () => { if (currentIndex<totalQ-1) goToPage(currentIndex+1); });
        submitBtn.addEventListener('click', showResult);
        resetBtn.addEventListener('click', resetAll);
        
        renderQuestion(0);
    })();
</script>
</body>
</html>
