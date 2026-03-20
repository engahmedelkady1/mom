<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>عيد سعيد يا أمي</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(180deg, #2b1634, #060816);
      color: #fff;
      font-family: Tahoma, Arial, sans-serif;
      text-align: center;
      overflow: hidden;
      position: relative;
    }
    .container {
      position: relative;
      z-index: 2;
      width: min(92vw, 700px);
      padding: 30px 22px 36px;
      background: rgba(255,255,255,.08);
      border: 1px solid rgba(255,255,255,.14);
      border-radius: 28px;
      backdrop-filter: blur(10px);
      box-shadow: 0 10px 35px rgba(0,0,0,.28);
    }
    .badge {
      display: inline-block;
      margin-bottom: 14px;
      padding: 8px 18px;
      border-radius: 999px;
      background: rgba(244,114,182,.12);
      border: 1px solid rgba(244,114,182,.35);
      color: #f9a8d4;
      font-weight: 700;
    }
    h1 {
      margin: 0 0 10px;
      font-size: clamp(2rem, 5vw, 3rem);
      line-height: 1.5;
    }
    p {
      margin: 0 0 18px;
      color: rgba(255,255,255,.9);
      font-size: 1.05rem;
      line-height: 1.9;
    }
    button {
      border: none;
      padding: 14px 28px;
      margin: 8px;
      border-radius: 14px;
      font-size: 1.05rem;
      font-weight: 700;
      cursor: pointer;
      box-shadow: 0 8px 18px rgba(0,0,0,.18);
      transition: transform .15s ease;
    }
    button:hover { transform: translateY(-1px); }
    #yes { background: #ec4899; color: #fff; }
    #no { background: #ef4444; color: #fff; position: relative; }
    #msg, #submsg {
      display: none;
      line-height: 2;
    }
    #msg {
      margin-top: 20px;
      font-size: 1.35rem;
      font-weight: 700;
      color: #f9a8d4;
    }
    #submsg {
      margin-top: 12px;
      font-size: 1rem;
      color: #fff;
    }
    .moon {
      position: absolute;
      top: 35px;
      left: 45px;
      width: 86px;
      height: 86px;
      border-radius: 50%;
      background: #fde68a;
      box-shadow: 0 0 28px rgba(253,224,71,.35);
    }
    .moon::after {
      content: "";
      position: absolute;
      width: 86px;
      height: 86px;
      border-radius: 50%;
      background: #2b1634;
      left: 22px;
      top: 6px;
    }
    .star {
      position: absolute;
      width: 3px;
      height: 3px;
      background: #fff;
      border-radius: 50%;
      animation: twinkle 2.4s infinite ease-in-out;
    }
    @keyframes twinkle {
      0%, 100% { opacity: .2; transform: scale(1); }
      50% { opacity: 1; transform: scale(1.9); }
    }
    .float-item {
      position: absolute;
      bottom: -30px;
      pointer-events: none;
      animation: floatUp linear forwards;
    }
    @keyframes floatUp {
      0% { transform: translateY(0) scale(.8); opacity: 0; }
      15% { opacity: 1; }
      100% { transform: translateY(-110vh) scale(1.35) rotate(8deg); opacity: 0; }
    }
    .footer {
      margin-top: 16px;
      color: rgba(255,255,255,.65);
      font-size: .92rem;
    }
  </style>
</head>
<body>
  <div class="moon"></div>

  <div class="container">
    <div class="badge">💖 تهنئة عيد خاصة</div>
    <h1>ماما، هتفضلي أجمل نعمة في كل عيد؟</h1>
    <p>العيد يحلو بوجودك، ودفء البيت لا يكتمل إلا بك، وعندي لك رسالة صغيرة محملة بكل الحب 🌙</p>

    <div id="buttons">
      <button id="yes">طبعًا 💖</button>
      <button id="no">لا</button>
    </div>

    <div id="msg">عيدك مبارك يا أمي الحبيبة ❤️<br>أنتِ أجمل هدية من ربنا، وأحن قلب في الدنيا كلها</div>
    <div id="submsg">ربنا يحفظك لي، ويملأ أيامك فرحًا وطمأنينة، ويجعل كل عيد وأنتِ بخير وسعادة لا تنتهي ✨</div>

    <div class="footer">من ابنك بكل الحب والامتنان</div>
  </div>

  <script>
    for (let i = 0; i < 50; i++) {
      const s = document.createElement('div');
      s.className = 'star';
      s.style.right = Math.random() * 100 + 'vw';
      s.style.top = Math.random() * 100 + 'vh';
      s.style.animationDelay = Math.random() * 2.5 + 's';
      s.style.animationDuration = (1.8 + Math.random() * 2.5) + 's';
      document.body.appendChild(s);
    }

    const no = document.getElementById('no');
    const yes = document.getElementById('yes');
    const msg = document.getElementById('msg');
    const submsg = document.getElementById('submsg');
    const buttons = document.getElementById('buttons');

    function moveNo() {
      no.style.position = 'fixed';
      no.style.left = Math.random() * (window.innerWidth - 100) + 'px';
      no.style.top = Math.random() * (window.innerHeight - 60) + 'px';
    }

    function launchItems() {
      for (let i = 0; i < 28; i++) {
        const el = document.createElement('div');
        el.className = 'float-item';
        el.textContent = Math.random() > 0.5 ? '💖' : '✨';
        el.style.left = Math.random() * 100 + 'vw';
        el.style.fontSize = (20 + Math.random() * 18) + 'px';
        el.style.animationDuration = (3 + Math.random() * 2.4) + 's';
        document.body.appendChild(el);
        setTimeout(() => el.remove(), 6000);
      }
    }

    no.addEventListener('mouseover', moveNo);
    no.addEventListener('click', moveNo);

    yes.addEventListener('click', () => {
      buttons.style.display = 'none';
      msg.style.display = 'block';
      submsg.style.display = 'block';
      launchItems();

      try {
        const audio = new Audio('https://cdn.pixabay.com/download/audio/2021/10/26/audio_36aa77ef06.mp3?filename=beautiful-piano-11831.mp3');
        audio.volume = 0.25;
        audio.play().catch(() => {});
      } catch (e) {}
    });
  </script>
</body>
</html>
