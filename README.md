<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>SARAオプチャ専用　　チーム分け！</title>
  <link href="https://fonts.googleapis.com/css2?family=Kaisei+Decol:wght@700&family=Zen+Maru+Gothic:wght@400;700&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Zen Maru Gothic', 'Kaisei Decol', sans-serif;
      background: linear-gradient(135deg, #e0c3fc 0%, #8ec5fc 100%);
      min-height: 100vh;
      margin: 0;
      padding: 0;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .container {
      background: rgba(255, 255, 255, 0.93);
      border-radius: 24px;
      box-shadow: 0 6px 36px rgba(160, 120, 180, 0.18);
      max-width: 430px;
      width: 96vw;
      margin: 48px 0 24px 0;
      padding: 2.5em 2em 1.5em 2em;
      animation: fadeIn 1s;
    }
    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(24px);}
      to { opacity: 1; transform: translateY(0);}
    }
    .clock-wrap {
      display: flex;
      justify-content: flex-end;
      margin-bottom: 0.3em;
    }
    .digital-clock {
      font-family: 'Kaisei Decol', 'Zen Maru Gothic', monospace;
      font-size: 1.1em;
      color: #fff;
      background: linear-gradient(90deg, #d1b2ff 60%, #f9eaff 100%);
      box-shadow: 0 2px 6px rgba(160, 120, 180, 0.09);
      border-radius: 14px;
      padding: 0.22em 1em 0.22em 0.92em;
      letter-spacing: 0.16em;
      border: 2px solid #e3c6ff;
      display: inline-block;
      min-width: 94px;
      text-align: center;
      margin-top: 0.5em;
      margin-bottom: 0.1em;
      position: relative;
      z-index: 2;
      box-sizing: border-box;
      transition: background 0.3s;
      font-weight: 700;
      text-shadow: 0 1px 2px #cbb6e9, 0 0px 3px #fff7;
    }
    h1 {
      font-family: 'Kaisei Decol', cursive;
      font-size: 2em;
      color: #a25cff;
      margin-bottom: 0.5em;
      letter-spacing: 0.02em;
      text-align: center;
    }
    h2 {
      font-size: 1.1em;
      color: #5b41a9;
      margin: 1.8em 0 0.7em;
      letter-spacing: 0.01em;
    }
    ul.participants {
      list-style: none;
      padding: 0;
      margin: 0 0 1em 0;
      display: flex;
      flex-wrap: wrap;
      gap: 0.7em 1.2em;
    }
    ul.participants li {
      flex: 1 1 40%;
    }
    label {
      display: flex;
      align-items: center;
      font-size: 1.07em;
      padding: 0.28em 0.6em 0.28em 0.2em;
      border-radius: 16px;
      transition: background 0.2s;
      cursor: pointer;
      position: relative;
    }
    label input[type="checkbox"] {
      accent-color: #a25cff;
      margin-right: 0.6em;
      transform: scale(1.2);
    }
    label:hover {
      background: #f3e6fd;
    }
    .team-count-wrap {
      margin: 1em 0 1.5em 0;
      font-size: 1.1em;
      color: #6a50b2;
      text-align: left;
    }
    input[type="number"] {
      width: 48px;
      padding: 0.2em 0.3em;
      border-radius: 8px;
      border: 1.2px solid #e5d2fa;
      font-size: 1em;
      margin-left: 0.5em;
      background: #faf8ff;
    }
    .btns {
      display: flex;
      gap: 1em;
      margin-bottom: 1em;
    }
    button {
      font-family: inherit;
      font-size: 1.07em;
      padding: 0.48em 1.2em;
      border: none;
      border-radius: 1.4em;
      background: linear-gradient(90deg, #b385f7 0%, #a8e5ff 100%);
      color: #fff;
      font-weight: 700;
      letter-spacing: 0.05em;
      box-shadow: 0 2px 10px rgba(160, 120, 180, 0.08);
      cursor: pointer;
      transition: background 0.14s, transform 0.1s;
    }
    button:hover {
      background: linear-gradient(90deg, #9f6bf7 0%, #7ed0fc 100%);
      transform: translateY(-2px) scale(1.03);
    }
    hr {
      border: none;
      border-top: 1.5px dashed #d9bcf7;
      margin: 1.5em 0;
    }
    .result {
      margin-top: 1.5em;
      display: flex;
      flex-wrap: wrap;
      gap: 1.5em 1em;
      justify-content: center;
    }
    .team-card {
      background: linear-gradient(120deg, #f5eeff 70%, #e3f6ff 100%);
      border-radius: 18px;
      box-shadow: 0 1px 6px rgba(160, 120, 180, 0.07);
      padding: 1em 1.1em 0.7em 1.1em;
      min-width: 120px;
      flex: 1 1 140px;
      max-width: 180px;
      text-align: center;
      animation: fadeInTeam 0.5s;
    }
    @keyframes fadeInTeam {
      from { opacity: 0; transform: scale(0.95);}
      to { opacity: 1; transform: scale(1);}
    }
    .team-card strong {
      color: #a25cff;
      letter-spacing: 0.04em;
      font-size: 1.14em;
    }
    .team-card ul {
      list-style: none;
      padding: 0.2em 0 0 0;
      margin: 0;
    }
    .team-card li {
      color: #473a6b;
      font-size: 1.09em;
      margin-bottom: 0.2em;
      padding: 0.1em 0;
    }
    @media (max-width: 500px) {
      .container { padding: 1.1em 0.4em;}
      .digital-clock { font-size: 0.95em; min-width: 74px; padding-left: 0.7em;}
      .team-card { min-width: 100px; max-width: 99vw;}
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="clock-wrap">
      <span class="digital-clock" id="digital-clock"></span>
    </div>
    <div class="title-bg-wrap">
  <img src="image.png" alt="ペチャウサイラスト" class="title-bg-img">
    <h1>SARAオプチャ専用<br>
      チーム分け！</h1>
    </div>
    <h2>メンバーリスト</h2>
    <ul class="participants" id="participants-list">
      <li><label><input type="checkbox" value="さら">さら</label></li>
      <li><label><input type="checkbox" value="ひろ">ひろ</label></li>
      <li><label><input type="checkbox" value="あきとん">あきとん</label></li>
      <li><label><input type="checkbox" value="みやび">みやび</label></li>
      <li><label><input type="checkbox" value="ぴーなっつ">ぴーなっつ</label></li>
      <li><label><input type="checkbox" value="SK">SK</label></li>
      <li><label><input type="checkbox" value="とうえい">とうえい</label></li>
      <li><label><input type="checkbox" value="しゃけ">しゃけ</label></li>
      <li><label><input type="checkbox" value="じぇいず">じぇいず</label></li>
      <li><label><input type="checkbox" value="ちい">ちい</label></li>
      <li><label><input type="checkbox" value="まっつん">まっつん</label></li>
      <li><label><input type="checkbox" value="まみーご">まみーご</label></li>
      <li><label><input type="checkbox" value="むちょ">むちょ</label></li>
      <li><label><input type="checkbox" value="やま">やま</label></li>
      <li><label><input type="checkbox" value="バナナ">バナナ</label></li>
      <li><label><input type="checkbox" value="ファンタ">ファンタ</label></li>
      <li><label><input type="checkbox" value="ボウ">ボウ</label></li>
      <li><label><input type="checkbox" value="ぺちゃうさ">ぺちゃうさ</label></li>
      <li><label><input type="checkbox" value="ちゃぶ">ちゃぶ</label></li>
      <li><label><input type="checkbox" value="シュガー">シュガー</label></li>
      <li><label><input type="checkbox" value="とん">とん</label></li>
      <li><label><input type="checkbox" value="ぽんずのしゅけ">ぽんずのしゅけ</label></li>
      <li><label><input type="checkbox" value="ちゃま">ちゃま</label></li>
      <li><label><input type="checkbox" value="まの">まの</label></li>
      <li><label><input type="checkbox" value="けん">けん</label></li>
      <li><label><input type="checkbox" value="五条">五条</label></li>
      <li><label><input type="checkbox" value="ぼんど">ぼんど</label></li>
      <li><label><input type="checkbox" value="とき">とき>とき>とｋ>と</li>
      <li><label><input type="checkbox" value="新メンバー用">新メンバー用</label></li>
    </ul>
    <div class="team-count-wrap">
      チーム数:
      <input type="number" id="team-count" min="2" value="2">
    </div>
    <div class="btns">
      <button onclick="splitTeams()">チーム分け！</button>
      <button onclick="resetAll()">リセット</button>
    </div>
    <hr>
    <div id="result" class="result"></div>
  </div>

  <script>
    // デジタル時計の表示
    function updateClock() {
      const clock = document.getElementById('digital-clock');
      const now = new Date();
      const h = String(now.getHours()).padStart(2, '0');
      const m = String(now.getMinutes()).padStart(2, '0');
      const s = String(now.getSeconds()).padStart(2, '0');
      clock.textContent = `${h}:${m}:${s}`;
    }
    setInterval(updateClock, 1000);
    updateClock();

    function shuffle(array) {
      const arr = array.slice();
      for (let i = arr.length - 1; i > 0; i--) {
        const j = Math.floor(Math.random() * (i + 1));
        [arr[i], arr[j]] = [arr[j], arr[i]];
      }
      return arr;
    }

    function splitTeams() {
      const checkboxes = document.querySelectorAll('#participants-list input[type="checkbox"]');
      const selected = [];
      checkboxes.forEach(cb => { if (cb.checked) selected.push(cb.value); });
      const teamCount = parseInt(document.getElementById('team-count').value, 10);

      if (selected.length < teamCount) {
        alert("チーム数より多い人数を選択してください！");
        return;
      }
      if (teamCount < 2) {
        alert("チーム数は2以上にしてください！");
        return;
      }

      const teams = Array.from({ length: teamCount }, () => []);
      const shuffled = shuffle(selected);
      shuffled.forEach((name, idx) => {
        teams[idx % teamCount].push(name);
      });

      const resultDiv = document.getElementById("result");
      resultDiv.innerHTML = '';
      teams.forEach((team, i) => {
        const teamDiv = document.createElement("div");
        teamDiv.className = "team-card";
        teamDiv.innerHTML = `<strong>チーム${i+1}</strong><ul>${team.map(name => `<li>${name}</li>`).join('')}</ul>`;
        resultDiv.appendChild(teamDiv);
      });
    }

    function resetAll() {
      document.querySelectorAll('#participants-list input[type="checkbox"]').forEach(cb => cb.checked = false);
      document.getElementById('team-count').value = 2;
      document.getElementById('result').innerHTML = '';
    }
  </script>
</body>
</html>
