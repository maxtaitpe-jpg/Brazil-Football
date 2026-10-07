<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Brazil's All-Time XI (4-3-3)</title>
    
    <!-- 足球 Favicon -->
    <link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>⚽</text></svg>">

    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #1a202c;
            color: #fff;
            text-align: center;
            margin: 0;
            padding: 20px;
        }

        h1 {
            color: #ffdf00; /* 巴西黃 */
            margin-bottom: 5px;
        }

        .subtitle {
            color: #a0aec0;
            margin-bottom: 25px;
        }

        /* 4-3-3 綠色球場 Container */
        .pitch {
            background-color: #276749;
            border: 4px solid #fff;
            border-radius: 12px;
            max-width: 650px;
            margin: 0 auto;
            padding: 30px 10px;
            display: flex;
            flex-direction: column;
            gap: 35px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5);
        }

        /* 每條線（前場、中場、後場、門將）排列 */
        .line {
            display: flex;
            justify-content: space-around;
            align-items: center;
        }

        /* 可點擊的球員卡片按鈕 */
        .player-btn {
            background-color: #fff;
            color: #1a202c;
            border: 2px solid #ffdf00;
            border-radius: 20px;
            padding: 8px 14px;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.2s;
        }

        .player-btn:hover {
            transform: scale(1.1);
            background-color: #ffdf00;
        }

        /* 彈出視窗 (Modal) 背景遮罩 */
        .modal-overlay {
            display: none; /* 預設隱藏 */
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }

        /* 彈出視窗本體 */
        .modal-content {
            background-color: #ffffff;
            color: #2d3748;
            padding: 25px;
            border-radius: 12px;
            width: 85%;
            max-width: 400px;
            text-align: left;
            position: relative;
            box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        }

        .modal-content h2 {
            margin-top: 0;
            color: #009c3b; /* 巴西綠 */
        }

        /* 關閉按鈕 */
        .close-btn {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 24px;
            font-weight: bold;
            cursor: pointer;
            color: #a0aec0;
        }

        .close-btn:hover {
            color: #000;
        }
    </style>
</head>
<body>

    <h1>🇧🇷 巴西歷代最佳 11 人</h1>
    <p class="subtitle">點擊球員名字可查看個人詳細介紹 (4-3-3 陣型)</p>

    <!-- 4-3-3 足球場 -->
    <div class="pitch">
        <!-- 前鋒 (FW) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Ronaldinho', '11 / LW (左翼)', '🏆 2002 世界盃冠軍', '「球場舞者」。將桑巴足球的靈巧、花式盤帶與創造力展現得淋漓盡致，2002 年對陣英格蘭的超遠自由球破門為其代表作。')">11. Ronaldinho</button>
            <button class="player-btn" onclick="showInfo('Ronaldo', '9 / ST (中鋒)', '🏆 1994, 2002 世界盃冠軍', '「外星人」。世界盃累積 15 顆進球，具備極致的爆發力、速度與鐘擺過人技術，是現代中鋒的終極形態。')">9. Ronaldo</button>
            <button class="player-btn" onclick="showInfo('Pelé', '10 / RW (右翼)', '🏆 1958, 1962, 1970 世界盃冠軍', '足球史上唯一的「球王」，生涯奪得三屆世界盃冠軍。兼具完美的身體素質、射門技巧與球場智慧，足球運動的象徵。')">10. Pelé</button>
        </div>

        <!-- 中場 (MF) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Zico', '8 / AM (攻擊中場)', '🥉 1978 世界盃季軍', '「白貝利」。擁有極致的盤帶能力、視野與恐怖的自由球進球率，是 1980 年代全美麗足球（Joga Bonito）的靈魂人物。')">8. Zico</button>
            <button class="player-btn" onclick="showInfo('Didi', '6 / DM (防守中場)', '🏆 1958, 1962 世界盃冠軍', '1958 年世界盃最佳球員，「落葉球」發明者。大腦級的中場大師，掌握整支球隊的攻守節奏。')">6. Didi</button>
            <button class="player-btn" onclick="showInfo('Rivaldo', '10 / AM (進攻中場)', '🏆 2002 世界盃冠軍', '1999 年金球獎得主。左腳技術無解，遠射與倒掛金鉤能力極強，在 2002 年世界盃與羅納度組成可怕的進球機器。')">10. Rivaldo</button>
        </div>

        <!-- 後衛 (DF) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Roberto Carlos', '6 / LB (左後衛)', '🏆 2002 世界盃冠軍', '以恐怖的爆發力與標誌性的「香蕉球」重砲自由球聞名，邊路助攻極具威脅，被公認為足球史上最強左後衛之一。')">6. R. Carlos</button>
            <button class="player-btn" onclick="showInfo('Lúcio', '3 / CB (中後衛)', '🏆 2002 世界盃冠軍', '身體素質強悍、空中對抗能力優異，且具備極強帶球向前突破的能力，是 2002 年「五星巴西」不可或缺的後防屏障。')">3. Lúcio</button>
            <button class="player-btn" onclick="showInfo('Aldair', '4 / CB (中後衛)', '🏆 1994 世界盃冠軍', '防守意識極佳，判斷準確且具備出色的出球技術，是 1990 年代巴西國家隊最值得信賴的中後衛。')">4. Aldair</button>
            <button class="player-btn" onclick="showInfo('Cafu', '2 / RB (右後衛)', '🏆 1994, 2002 世界盃冠軍', '隊史出場紀錄保持人（142場）。體能充沛、助攻能力極強的現代右後衛始祖，也是唯一一位連續三屆踢進世界盃決賽的球員。')">2. Cafu</button>
        </div>

        <!-- 門將 (GK) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Taffarel', '1 / GK (門將)', '🏆 1994 世界盃冠軍', '巴西歷史上最穩定的門將，門前反應極快且擅長撲救十二碼點球，是 1994 年巴西奪冠的核心功臣。')">1. Taffarel</button>
        </div>
    </div>

    <!-- 點擊後跳出的彈窗 (Modal) -->
    <div id="playerModal" class="modal-overlay">
        <div class="modal-content">
            <span class="close-btn" onclick="closeInfo()">&times;</span>
            <h2 id="modalName">球員名稱</h2>
            <p><strong>位置/背號：</strong> <span id="modalPos"></span></p>
            <p><strong>國家隊榮譽：</strong> <span id="modalHonor"></span></p>
            <hr style="border: 0; border-top: 1px solid #eee; margin: 15px 0;">
            <p id="modalDesc">詳細介紹...</p>
        </div>
    </div>

    <!-- 簡單的 JS 控制邏輯 -->
    <script>
        // 開啟並填入球員資料
        function showInfo(name, pos, honor, desc) {
            document.getElementById('modalName').innerText = name;
            document.getElementById('modalPos').innerText = pos;
            document.getElementById('modalHonor').innerText = honor;
            document.getElementById('modalDesc').innerText = desc;
            
            document.getElementById('playerModal').style.display = 'flex';
        }

        // 關閉彈窗
        function closeInfo() {
            document.getElementById('playerModal').style.display = 'none';
        }

        // 點擊背景空白處也能關閉彈窗
        window.onclick = function(event) {
            let modal = document.getElementById('playerModal');
            if (event.target == modal) {
                closeInfo();
            }
        }
    </script>

</body>
</html>
