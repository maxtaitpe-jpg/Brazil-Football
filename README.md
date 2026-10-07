<html lang="zh-TW">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Brazil's All-Time XI (4-3-3)</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            text-align: center;
        }

        /* 4-3-3 球場範圍（無顏色，僅用黑線邊框） */
        .pitch {
            border: 2px solid #000;
            max-width: 650px;
            margin: 20px auto;
            padding: 30px 10px;
            display: flex;
            flex-direction: column;
            gap: 35px;
        }

        /* 每條線（前場、中場、後場、門將）排列 */
        .line {
            display: flex;
            justify-content: space-around;
            align-items: center;
        }

        /* 球員按鈕（純黑白外框） */
        .player-btn {
            background: #fff;
            color: #000;
            border: 1px solid #000;
            padding: 8px 12px;
            cursor: pointer;
        }

        /* 彈出視窗背景 */
        .modal-overlay {
            display: none; /* 預設隱藏 */
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            justify-content: center;
            align-items: center;
        }

        /* 彈出視窗本體（純白底黑字） */
        .modal-content {
            background-color: #fff;
            color: #000;
            border: 1px solid #000;
            padding: 20px;
            width: 80%;
            max-width: 400px;
            text-align: left;
            position: relative;
        }

        /* 關閉按鈕 */
        .close-btn {
            position: absolute;
            top: 10px;
            right: 15px;
            font-size: 20px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <h1>Brazil's All-Time XI (4-3-3)</h1>
    <p>點擊球員查看簡介</p>

    <!-- 4-3-3 陣型 -->
    <div class="pitch">
        <!-- 前鋒 (FW) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Ronaldinho', '11 / LW (左翼)', '1999–2013', '2002 世界盃冠軍', '「球場舞者」。將桑巴足球的靈巧、花式盤帶與創造力展現得淋漓盡致。')">11. Ronaldinho</button>
            <button class="player-btn" onclick="showInfo('Ronaldo', '9 / ST (中鋒)', '1994–2011', '1994, 2002 世界盃冠軍', '「外星人」。世界盃累積 15 顆進球，具備極致的爆發力與速度。')">9. Ronaldo</button>
            <button class="player-btn" onclick="showInfo('Pelé', '10 / RW (右翼)', '1957–1971', '1958, 1962, 1970 世界盃冠軍', '足球史上唯一的「球王」，生涯奪得三屆世界盃冠軍。')">10. Pelé</button>
        </div>

        <!-- 中場 (MF) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Zico', '8 / AM (攻擊中場)', '1976–1986', '1978 世界盃季軍', '「白貝利」。擁有極致的盤帶能力、視野與恐怖的自由球進球率。')">8. Zico</button>
            <button class="player-btn" onclick="showInfo('Didi', '6 / DM (防守中場)', '1952–1962', '1958, 1962 世界盃冠軍', '1958 年世界盃最佳球員，「落葉球」發明者，大腦級的中場大師。')">6. Didi</button>
            <button class="player-btn" onclick="showInfo('Rivaldo', '10 / AM (進攻中場)', '1993–2003', '2002 世界盃冠軍', '1999 年金球獎得主，左腳技術無解，遠射與倒掛金鉤能力極強。')">10. Rivaldo</button>
        </div>

        <!-- 後衛 (DF) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Roberto Carlos', '6 / LB (左後衛)', '1992–2006', '2002 世界盃冠軍', '以恐怖的爆發力與標誌性的「香蕉球」重砲自由球聞名。')">6. R. Carlos</button>
            <button class="player-btn" onclick="showInfo('Lúcio', '3 / CB (中後衛)', '2000–2011', '2002 世界盃冠軍', '身體素質強悍、空中對抗能力優異，且具備帶球向前突破的能力。')">3. Lúcio</button>
            <button class="player-btn" onclick="showInfo('Aldair', '4 / CB (中後衛)', '1989–2000', '1994 世界盃冠軍', '防守意識極佳，判斷準確且具備出色的出球技術。')">4. Aldair</button>
            <button class="player-btn" onclick="showInfo('Cafu', '2 / RB (右後衛)', '1990–2006', '1994, 2002 世界盃冠軍', '隊史出場紀錄保持人，體能充沛、助攻能力極強的現代右後衛始祖。')">2. Cafu</button>
        </div>

        <!-- 門將 (GK) -->
        <div class="line">
            <button class="player-btn" onclick="showInfo('Taffarel', '1 / GK (門將)', '1987–1998', '1994 世界盃冠軍', '巴西歷史上最穩定的門將，門前反應極快且擅長撲救十二碼點球。')">1. Taffarel</button>
        </div>
    </div>

    <!-- 點擊後跳出的無顏色彈窗 -->
    <div id="playerModal" class="modal-overlay">
        <div class="modal-content">
            <span class="close-btn" onclick="closeInfo()">&times;</span>
            <h2 id="modalName" style="margin-top:0;">球員名稱</h2>
            <p><strong>位置/背號：</strong> <span id="modalPos"></span></p>
            <p><strong>效力時期：</strong> <span id="modalYears"></span></p>
            <p><strong>國家隊榮譽：</strong> <span id="modalHonor"></span></p>
            <hr>
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

    <iframe width="560" height="315" src="https://www.youtube.com/embed/rn0ThwsRGmU?si=63WAoaZnpqhbeIsj" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

</body>
</html>
