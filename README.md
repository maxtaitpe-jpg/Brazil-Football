<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basketball All-Time Starting Five</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            text-align: center;
            background-color: #ffffff;
        }

        /* 籃球場範圍 */
        .pitch {
            border: 2px solid #000;
            max-width: 500px;
            height: 450px;
            margin: 20px auto;
            padding: 20px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            position: relative;
            box-sizing: border-box;
        }

        /* 籃球場中線裝飾 */
        .pitch::after {
            content: "";
            position: absolute;
            top: 50%;
            left: 0;
            width: 100%;
            border-top: 1px dashed #ccc;
            z-index: 0;
        }

        /* 每一條戰術線 */
        .line {
            display: flex;
            justify-content: space-around;
            align-items: center;
            position: relative;
            z-index: 1;
        }

        /* 球員按鈕 */
        .player-btn {
            background: #fff;
            color: #000;
            border: 1px solid #000;
            padding: 8px 12px;
            cursor: pointer;
            font-size: 14px;
        }

        /* 陣型下方的影片容器 */
        .main-video {
            margin: 30px auto;
            max-width: 560px;
        }

        .main-video iframe {
            width: 100%;
            height: 315px;
            border: none;
        }

        /* 彈出視窗背景（覆蓋全螢幕） */
        .modal-overlay {
            display: none; /* 預設隱藏 */
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            background-color: rgba(0, 0, 0, 0.6); /* 灰色深色遮罩 */
            justify-content: center;
            align-items: center;
            z-index: 99999; /* 極高層級，防止被按鈕穿透 */
        }

        /* 彈出視窗本體（強制不透明白底） */
        .modal-content {
            background-color: #ffffff !important; /* 強制純白底不透明 */
            color: #000000;
            border: 2px solid #000000;
            padding: 25px;
            width: 85%;
            max-width: 400px;
            text-align: left;
            position: relative;
            box-shadow: 0px 10px 30px rgba(0, 0, 0, 0.5);
            z-index: 100000;
            box-sizing: border-box;
        }

        /* 關閉按鈕 */
        .close-btn {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 24px;
            cursor: pointer;
            font-weight: bold;
            line-height: 1;
        }
    </style>
</head>
<body>

    <h1>Basketball All-Time Starting Five</h1>
    <p>點擊球員查看簡介</p>

    <!-- 籃球場陣型排版 -->
    <div class="pitch">
        <!-- 頂端外線：控衛 (PG) 與 得分後衛 (SG) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Magic Johnson', '32 / PG (控球後衛)', '1979–1991, 1996', '5次總冠軍、3次FMVP、3次MVP', '歷史最佳控衛。以充滿想像力的傳球視野與 206 公分的身高主宰全場。')">32. Magic Johnson (PG)</button>
            <button class="player-btn" onclick="showInfo('Allen Iverson', '3 / SG (得分後衛)', '1996–2010', '例行賽 MVP、4次得分王', '「戰神」。擁有極致的運球過人和無解的得分能力，以小搏大的精神象徵。')">3. Allen Iverson (SG)</button>
        </div>

        <!-- 中間鋒線：小前鋒 (SF) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('LeBron James', '23 / SF (小前鋒)', '2003–現役', '4次總冠軍、4次FMVP、4次MVP', '「小皇帝」。擁有歷史級的身體素質、全能數據與統治力，聯盟常青樹。')">23. LeBron James (SF)</button>
        </div>

        <!-- 底部禁區：大前鋒 (PF) 與 中鋒 (C) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Tim Duncan', '21 / PF (大前鋒)', '1997–2016', '5次總冠軍、3次FMVP、2次MVP', '「石佛」。歷史第一大前鋒，球風穩健無華，攻守俱佳的馬刺隊魂。')">21. Tim Duncan (PF)</button>
            <button class="player-btn" onclick="showInfo('Hakeem Olajuwon', '34 / C (中鋒)', '1984–2002', '2次總冠軍、2次FMVP、1次MVP', '「大夢」。擁有夢幻步伐（Dream Shake），攻防兩端極具統治力的頂級中鋒。')">34. Hakeem Olajuwon (C)</button>
        </div>
    </div>

    <!-- 陣型正下方的影片區塊 -->
    <div class="main-video">
        <iframe src="https://www.youtube.com/embed/rn0ThwsRGmU?si=63WAoaZnpqhbeIsj" title="YouTube video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>

    <!-- 點擊後跳出的無顏色彈窗 -->
    <div id="playerModal" class="modal-overlay">
        <div class="modal-content">
            <span class="close-btn" onclick="closeInfo()">&times;</span>
            <h2 id="modalName" style="margin-top:0;">球員名稱</h2>
            <p><strong>位置/背號：</strong> <span id="modalPos"></span></p>
            <p><strong>活躍時期：</strong> <span id="modalYears"></span></p>
            <p><strong>生涯成就：</strong> <span id="modalHonor"></span></p>
            <hr style="border: 0; border-top: 1px solid #000; margin: 15px 0;">
            <p id="modalDesc">詳細介紹...</p>
        </div>
    </div>

    <script>
        function showInfo(name, pos, years, honor, desc) {
            document.getElementById('modalName').innerText = name;
            document.getElementById('modalPos').innerText = pos;
            document.getElementById('modalYears').innerText = years;
            document.getElementById('modalHonor').innerText = honor;
            document.getElementById('modalDesc').innerText = desc;
            
            document.getElementById('playerModal').style.display = 'flex';
        }

        function closeInfo() {
            document.getElementById('playerModal').style.display = 'none';
        }

        window.onclick = function(event) {
            let modal = document.getElementById('playerModal');
            if (event.target == modal) {
                closeInfo();
            }
        }
    </script>

</body>
</html>
