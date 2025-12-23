<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>GEN X INTERNATIONAL</title>
    <style>
        :root { --glitch-red: #ff0000; }
        body, html { background: #000; margin: 0; padding: 0; width: 100%; height: 100%; display: flex; justify-content: center; align-items: center; overflow: hidden; font-family: 'Impact', sans-serif; color: #fff; }
        
        #google_translate_element { position: absolute; top: 10px; right: 10px; z-index: 120; transform: scale(0.8); transform-origin: top right; }

        #loader { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #000; z-index: 1000; display: flex; flex-direction: column; justify-content: center; align-items: center; transition: opacity 0.8s; }
        #progress-bar { width: 0%; height: 2px; background: var(--glitch-red); box-shadow: 0 0 15px var(--glitch-red); transition: width 0.1s; }

        .stage { position: relative; width: 100vw; height: 100vh; opacity: 0; transition: opacity 1.5s; display: flex; flex-direction: column; justify-content: center; align-items: center; }
        
        /* THE DRAGONS */
        .main-img { width: 100%; height: 100%; object-fit: cover; animation: breathe 8s infinite ease-in-out; filter: brightness(0.6); position: absolute; top: 0; left: 0; z-index: 1; }
        @keyframes breathe { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.05); } }

        h1 { position: relative; z-index: 10; font-size: 12vw; text-shadow: 0 0 20px #000, 2px 2px 5px #ff0000; letter-spacing: 4px; text-align: center; margin: 0; pointer-events: none; }

        .ticker-wrap { position: absolute; bottom: 0; width: 100%; overflow: hidden; background: rgba(0, 0, 0, 0.8); border-top: 1px solid var(--glitch-red); padding: 12px 0; z-index: 150; }
        .ticker { display: inline-block; white-space: nowrap; animation: ticker 25s linear infinite; font-size: 16px; letter-spacing: 2px; color: #ff0000; }
        @keyframes ticker { 0% { transform: translateX(100%); } 100% { transform: translateX(-100%); } }

        .overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.98); z-index: 200; display: none; justify-content: center; align-items: center; backdrop-filter: blur(10px); }
        .card { background: #000; border: 2px solid var(--glitch-red); padding: 30px; width: 85%; max-width: 400px; text-align: center; box-shadow: 0 0 40px rgba(255,0,0,0.5); }
        .card input { width: 100%; padding: 15px; margin-bottom: 15px; background: #111; border: 1px solid #444; color: #fff; box-sizing: border-box; }
        .submit-btn { width: 100%; padding: 15px; background: var(--glitch-red); color: #fff; border: none; font-weight: bold; font-size: 18px; cursor: pointer; }

        .social-bar { position: absolute; bottom: 80px; display: flex; gap: 10px; z-index: 100; }
        .social-icon { background: #000; color: #fff; padding: 10px 20px; border: 1px solid #fff; font-size: 12px; text-decoration: none; cursor: pointer; }
        #audio-ui { position: absolute; top: 15px; left: 15px; z-index: 110; font-size: 10px; color: #ff0000; font-family: monospace; }

        .lightning { position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: #fff; opacity: 0; pointer-events: none; z-index: 5; }
        .flash-active { animation: flash 0.1s linear; }
        @keyframes flash { 0%, 100% { opacity: 0; } 50% { opacity: 0.3; } }
    </style>
</head>
<body>

    <div id="google_translate_element"></div>
    <audio id="bg-track" loop><source src="masterofpuppets.mp3" type="audio/mpeg"></audio>
    <div id="audio-ui">[ SYSTEM MUTED - TAP ANYWHERE TO WAKE ]</div>

    <div id="loader">
        <h2 style="color:red; letter-spacing:5px;">GEN X INTERNATIONAL</h2>
        <div style="width:150px; height:2px; background:#333;"><div id="progress-bar"></div></div>
    </div>

    <div id="join-overlay" class="overlay">
        <div class="card">
            <h2 style="color:red; margin-top:0;">ENLIST</h2>
            <form action="https://formspree.io/f/xzdpavnj" method="POST">
                <input type="text" name="handle" placeholder="SOCIAL HANDLE" required>
                <input type="email" name="email" placeholder="EMAIL" required>
                <input type="number" name="year" placeholder="YEAR (1965-1980)" required>
                <button type="submit" class="submit-btn">JOIN THE FAMILY</button>
            </form>
            <p onclick="closeAll()" style="color:#444; margin-top:15px; font-size:12px; cursor:pointer;">[ BACK ]</p>
        </div>
    </div>

    <div class="stage" id="main-stage">
        <img src="https://i.ibb.co/99ktHFKw/dragons.webp" class="main-img" alt="dragons">
        <h1>GEN ❌️ INT</h1>
        <div class="lightning" id="lightning"></div>
        
        <div class="social-bar">
            <div class="social-icon" onclick="openJoin()">JOIN</div>
            <a href="tiktok.com/@stormyknightx74" class="social-icon">TIKTOK</a>
        </div>
    </div>

    <div class="ticker-wrap">
        <div class="ticker">
            ESTABLISHED 1965-1980... WE DRANK FROM A WATER HOSE... WE DIDN'T HAVE CELL PHONES, IT WAS A LANDLINE... DIAL-UP INTERNET... WE BABY SAT OURSELVES... WE DIDN'T HAVE A GPS, ONLY THAT GOD AWFUL PAPER ROAD MAP... THEN OF COURSE WE HAD OUR SLONGANS AS WELL..... FUCK AROUND AND FIND OUT... I'M GETTING TO OLD FOR THIS SHIT... WHERE'S THE BEEF?... I HAVE FALLEN AND I CAN'T GET UP... WHATEVER!... TAKE A PICTURE, IT'LL LAST LONGER... I KNOW YOU ARE, BUT WHAT AM I... WHAT'S YOUR MALFUNCTION?... NO SHIT SHERLOCK... TALK TO THE HAND... AS IF!!... TAKE A CHILL PILL... THE LAST GENERATION OF PRIVACY... THE FIRST GENERATION OF TECH... WE ARE GEN X INTERNATIONAL...
        </div>
    </div>

    <script>
        const audio = document.getElementById('bg-track');
        function openJoin() { document.getElementById('join-overlay').style.display = 'flex'; }
        function closeAll() { document.getElementById('join-overlay').style.display = 'none'; }

        let w = 0;
        const interval = setInterval(() => {
            w += 2;
            document.getElementById('progress-bar').style.width = w + '%';
            if(w >= 100) {
                clearInterval(interval);
                document.getElementById('loader').style.opacity = '0';
                setTimeout(() => {
                    document.getElementById('loader').style.display = 'none';
                    document.getElementById('main-stage').style.opacity = '1';
                }, 800);
            }
        }, 50);

        document.body.addEventListener('click', () => {
            audio.play();
            document.getElementById('audio-ui').innerText = "[ SYSTEM ONLINE ]";
        });

        function triggerLightning() {
            setTimeout(() => {
                document.getElementById('lightning').classList.add('flash-active');
                setTimeout(() => document.getElementById('lightning').classList.remove('flash-active'), 100);
                triggerLightning();
            }, Math.random() * 6000 + 2000);
        }
        triggerLightning();

        function googleTranslateElementInit() {
            new google.translate.TranslateElement({pageLanguage: 'en'}, 'google_translate_element');
        }
    </script>
    <script src="//translate.google.com/translate_a/element.js?cb=googleTranslateElementInit"></script>
</body>
</html>
<link rel="manifest" href="manifest.json">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
