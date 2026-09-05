
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#050505">
<title>VirpriX Hub — Roblox</title>

<style>
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    body {
        min-height: 100vh;
        background: #000;
        color: #fff;
        font-family: Arial, Helvetica, sans-serif;
        overflow-x: hidden;
    }

    /* Background stars */
    body::before {
        content: "";
        position: fixed;
        inset: 0;
        pointer-events: none;
        opacity: .45;
        background-image:
            radial-gradient(circle, #fff 1px, transparent 1px),
            radial-gradient(circle, #fff 1px, transparent 1px);
        background-size: 85px 85px, 130px 130px;
        background-position: 10px 20px, 50px 70px;
    }

    .hero {
        position: relative;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 30px 20px;
        text-align: center;
        overflow: hidden;
    }

    /* Black-hole core */
    .black-hole {
        position: absolute;
        width: 280px;
        height: 280px;
        border-radius: 50%;
        background: #000;
        box-shadow:
            0 0 25px 8px #fff,
            0 0 65px 18px #555,
            0 0 120px 30px #222;
        opacity: .8;
        animation: float 5s ease-in-out infinite;
    }

    .black-hole::before {
        content: "";
        position: absolute;
        inset: -38px;
        border: 3px solid #fff;
        border-radius: 50%;
        opacity: .25;
        transform: rotate(-20deg) scaleY(.35);
    }

    .black-hole::after {
        content: "";
        position: absolute;
        inset: -65px;
        border: 2px solid #777;
        border-radius: 50%;
        opacity: .18;
        transform: rotate(25deg) scaleY(.27);
    }

    .v {
        position: relative;
        z-index: 2;
        font-size: clamp(130px, 35vw, 230px);
        line-height: .8;
        font-weight: 900;
        font-style: italic;
        color: #fff;
        text-shadow:
            0 0 10px #fff,
            0 0 35px #888;
        user-select: none;
    }

    .brand {
        position: relative;
        z-index: 3;
        margin-top: 45px;
        font-size: clamp(32px, 10vw, 58px);
        font-weight: 900;
        letter-spacing: 7px;
    }

    .brand span {
        color: #777;
    }

    .tagline {
        position: relative;
        z-index: 3;
        margin-top: 12px;
        color: #aaa;
        font-size: 15px;
        letter-spacing: 2px;
        max-width: 500px;
    }

    .buttons {
        position: relative;
        z-index: 3;
        display: flex;
        gap: 12px;
        margin-top: 30px;
        flex-wrap: wrap;
        justify-content: center;
    }

    button, .button {
        border: 1px solid #fff;
        background: #fff;
        color: #000;
        padding: 13px 22px;
        border-radius: 999px;
        font-weight: 800;
        text-decoration: none;
        cursor: pointer;
        transition: .2s;
    }

    button:hover, .button:hover {
        background: #000;
        color: #fff;
        transform: translateY(-2px);
    }

    .button.dark {
        background: #111;
        color: #fff;
    }

    .section {
        position: relative;
        z-index: 2;
        max-width: 1050px;
        margin: auto;
        padding: 80px 20px;
    }

    .section-title {
        font-size: 30px;
        margin-bottom: 10px;
    }

    .section-subtitle {
        color: #888;
        margin-bottom: 30px;
    }

    .cards {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
        gap: 15px;
    }

    .card {
        background: #080808;
        border: 1px solid #292929;
        border-radius: 20px;
        padding: 0;
        transition: .2s;
        overflow: hidden;
    }

    .card:hover {
        border-color: #aaa;
        transform: translateY(-4px);
    }

    .card-thumb {
        width: 100%;
        aspect-ratio: 16/9;
        object-fit: cover;
        display: block;
        background: #111;
    }

    .card-thumb-placeholder {
        width: 100%;
        aspect-ratio: 16/9;
        background: #111;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 36px;
        color: #333;
    }

    .card-body {
        padding: 18px 20px 20px;
    }

    .card-body h3 {
        margin-bottom: 6px;
        font-size: 15px;
    }

    .card-body p {
        color: #888;
        line-height: 1.5;
        font-size: 13px;
        margin-bottom: 14px;
    }

    .icon {
        width: 45px;
        height: 45px;
        border: 1px solid #555;
        border-radius: 50%;
        display: grid;
        place-items: center;
        font-weight: 900;
        margin-bottom: 14px;
        font-size: 18px;
    }

    /* Script display box */
    .script-box {
        background: #0d0d0d;
        border: 1px solid #2a2a2a;
        border-radius: 16px;
        padding: 20px 22px;
        margin: 0 0 30px;
    }

    .script-box-label {
        font-size: 11px;
        letter-spacing: 2px;
        color: #555;
        text-transform: uppercase;
        margin-bottom: 10px;
    }

    .script-text {
        font-family: 'Courier New', monospace;
        font-size: 13px;
        color: #ccc;
        word-break: break-all;
        line-height: 1.6;
        margin-bottom: 14px;
        user-select: all;
    }

    .script-actions {
        display: flex;
        gap: 10px;
        flex-wrap: wrap;
    }

    .copy-btn {
        border: 1px solid #444;
        background: #fff;
        color: #000;
        padding: 8px 18px;
        border-radius: 999px;
        font-size: 12px;
        font-weight: 800;
        cursor: pointer;
        transition: .2s;
        letter-spacing: .5px;
    }

    .copy-btn:hover {
        background: #ccc;
    }

    .copy-btn.copied {
        background: #1a1a1a;
        color: #aaa;
        border-color: #333;
    }

    .discord-btn {
        display: inline-flex;
        align-items: center;
        gap: 7px;
        border: 1px solid #5865F2;
        background: #5865F2;
        color: #fff;
        padding: 8px 18px;
        border-radius: 999px;
        font-size: 12px;
        font-weight: 800;
        text-decoration: none;
        cursor: pointer;
        transition: .2s;
        letter-spacing: .5px;
    }

    .discord-btn:hover {
        background: #4752c4;
        border-color: #4752c4;
        transform: translateY(-1px);
    }

    .stats {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 12px;
        margin-top: 18px;
    }

    .stat {
        background: #070707;
        border: 1px solid #222;
        border-radius: 16px;
        padding: 18px;
        text-align: center;
    }

    .stat strong {
        display: block;
        font-size: 25px;
    }

    .stat small {
        color: #777;
    }

    footer {
        position: relative;
        z-index: 2;
        text-align: center;
        padding: 40px 20px;
        border-top: 1px solid #171717;
        color: #666;
        font-size: 13px;
    }

    @keyframes float {
        0%, 100% { transform: translateY(0) scale(1); }
        50% { transform: translateY(-12px) scale(1.03); }
    }

    @media (max-width: 520px) {
        .stats {
            grid-template-columns: 1fr;
        }

        .brand {
            letter-spacing: 4px;
        }
    }
</style>
</head>

<body>

<section class="hero">
    <div class="black-hole"></div>

    <div class="v">V</div>

    <h1 class="brand">VIRPRIX<span> HUB</span></h1>
    <p class="tagline">Free Roblox scripts. Many games supported. One hub.</p>

    <div class="buttons">
        <a class="button" href="#scripts">Get Scripts</a>
        <a class="button dark" href="#about">About VirpriX</a>
        <a class="discord-btn" href="https://discord.gg/ZfSnnpy8a" target="_blank">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057c.002.022.015.043.033.053a19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994a.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03z"/></svg>
            Join Discord
        </a>
    </div>
</section>

<section class="section" id="about">
    <h2 class="section-title">What is VirpriX?</h2>
    <p class="section-subtitle">
        A free Roblox script hub — no key system, no paywalls. Just scripts that work.
    </p>

    <div class="cards">
        <div class="card">
            <div class="card-body">
                <div class="icon">V</div>
                <h3>VirpriX Hub</h3>
                <p>A constantly updated script hub built for the Roblox community. Free forever — no subscriptions, no keys.</p>
            </div>
        </div>

        <div class="card">
            <div class="card-body">
                <div class="icon">🎮</div>
                <h3>Many Games Supported</h3>
                <p>Scripts for popular Roblox titles. Rivals, MM2, Slap Battles, and more added regularly.</p>
            </div>
        </div>

        <div class="card">
            <div class="card-body">
                <div class="icon">∞</div>
                <h3>Always Free</h3>
                <p>No key system. No survey. No Discord requirement. Copy the script, paste it, run it. That's it.</p>
            </div>
        </div>
    </div>
</section>

<section class="section" id="scripts">
    <h2 class="section-title">Supported Games</h2>
    <p class="section-subtitle">Scripts updated regularly. Paste into any supported executor.</p>

    <!-- Main Script Box -->
    <div class="script-box">
        <div class="script-box-label">Main Script</div>
        <div class="script-text" id="main-script">loadstring(game:HttpGet("https://obfuscatorhub.vercel.app/api/FH7GgW0r"))()</div>
        <div class="script-actions">
            <button class="copy-btn" id="copy-btn" onclick="copyScript()">Copy Script</button>
            <a class="discord-btn" href="https://discord.gg/ZfSnnpy8a" target="_blank">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057c.002.022.015.043.033.053a19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994a.076.076 0 0 0-.041-.106 13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.062 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.03z"/></svg>
                Join Discord
            </a>
        </div>
    </div>

    <div class="cards" id="game-cards">

        <!-- Rivals — Game ID 17017769292 -->
        <div class="card">
            <img class="card-thumb" 
                 src="https://tr.rbxcdn.com/180DAY-7e0949d0b3a4e2a9fde6bbbd25f24001/768/432/Image/Webp/noFilter"
                 onerror="this.style.display='none';this.nextElementSibling.style.display='flex';"
                 alt="Rivals thumbnail">
            <div class="card-thumb-placeholder" style="display:none;">🎮</div>
            <div class="card-body">
                <h3>Rivals</h3>
                <p>1v1 to 5v5 FPS duels. First to 5 wins. Auto-aim, ESP, and silent aim supported.</p>
            </div>
        </div>

        <!-- Steal an Egg — Game ID 108016795637827 -->
        <div class="card">
            <img class="card-thumb"
                 src="https://tr.rbxcdn.com/180DAY-5e2c5b3e4f1a9b8c2d7e6f3a1b4c8d2e/768/432/Image/Webp/noFilter"
                 onerror="this.style.display='none';this.nextElementSibling.style.display='flex';"
                 alt="Steal an Egg thumbnail">
            <div class="card-thumb-placeholder" style="display:none;">🥚</div>
            <div class="card-body">
                <h3>Steal an Egg</h3>
                <p>Auto-steal, egg ESP, and speed boost. Farm eggs while AFK.</p>
            </div>
        </div>

        <!-- MM2 — Murder Mystery 2 — Game ID 142823291 -->
        <div class="card">
            <img class="card-thumb"
                 src="https://tr.rbxcdn.com/180DAY-c3e4f5a6b7d8e9f0a1b2c3d4e5f6a7b8/768/432/Image/Webp/noFilter"
                 onerror="this.style.display='none';this.nextElementSibling.style.display='flex';"
                 alt="Murder Mystery 2 thumbnail">
            <div class="card-thumb-placeholder" style="display:none;">🔪</div>
            <div class="card-body">
                <h3>MM2</h3>
                <p>Murderer ESP, gun snapper, and auto-collect coins. See everyone through walls.</p>
            </div>
        </div>

        <!-- Flick — Game ID 6415469319 -->
        <div class="card">
            <img class="card-thumb"
                 src="https://tr.rbxcdn.com/180DAY-a1b2c3d4e5f6a7b8c9d0e1f2a3b4c5d6/768/432/Image/Webp/noFilter"
                 onerror="this.style.display='none';this.nextElementSibling.style.display='flex';"
                 alt="Flick thumbnail">
            <div class="card-thumb-placeholder" style="display:none;">👆</div>
            <div class="card-body">
                <h3>Flick</h3>
                <p>Auto-flick, instant win assist, and hitbox expander. Dominate every round.</p>
            </div>
        </div>

        <!-- Slap Battles — Game ID 6403373529 -->
        <div class="card">
            <img class="card-thumb"
                 src="https://tr.rbxcdn.com/180DAY-f1e2d3c4b5a6978869504132241f1e2d/768/432/Image/Webp/noFilter"
                 onerror="this.style.display='none';this.nextElementSibling.style.display='flex';"
                 alt="Slap Battles thumbnail">
            <div class="card-thumb-placeholder" style="display:none;">👋</div>
            <div class="card-body">
                <h3>Slap Battles</h3>
                <p>Infinite slap range, auto-slap, knockback multiplier, and badge farmer.</p>
            </div>
        </div>

        <!-- More Upcoming -->
        <div class="card">
            <div class="card-thumb-placeholder" style="display:flex; background: #0a0a0a;">⏳</div>
            <div class="card-body">
                <h3>More Upcoming</h3>
                <p>New game scripts drop regularly. Stay tuned — more supported games coming soon.</p>
            </div>
        </div>

    </div>

    <div class="stats">
        <div class="stat">
            <strong>FREE</strong>
            <small>Always & Forever</small>
        </div>
        <div class="stat">
            <strong>5+</strong>
            <small>Games Supported</small>
        </div>
        <div class="stat">
            <strong>∞</strong>
            <small>No Key System</small>
        </div>
    </div>
</section>

<script>
  // Fetch real Roblox thumbnails via the public API using game IDs
  const games = [
    { id: '17017769292',   idx: 0 }, // Rivals
    { id: '108016795637827', idx: 1 }, // Steal an Egg
    { id: '142823291',     idx: 2 }, // MM2
    { id: '6415469319',    idx: 3 }, // Flick
    { id: '6403373529',    idx: 4 }, // Slap Battles
  ];

  const cards = document.querySelectorAll('#game-cards .card');

  games.forEach(({ id, idx }) => {
    const url = `https://thumbnails.roblox.com/v1/games/icons?universeIds=${id}&returnPolicy=PlaceHolder&size=512x512&format=Webp&isCircular=false`;
    fetch(url)
      .then(r => r.json())
      .then(data => {
        const imgUrl = data?.data?.[0]?.imageUrl;
        if (imgUrl && cards[idx]) {
          const img = cards[idx].querySelector('.card-thumb');
          const placeholder = cards[idx].querySelector('.card-thumb-placeholder');
          if (img) {
            img.src = imgUrl;
            img.style.display = 'block';
            if (placeholder) placeholder.style.display = 'none';
          }
        }
      })
      .catch(() => {});
  });
</script>

<footer>
    © 2026 VirpriX Hub · Free Roblox Scripts · No Key · No Paywall
</footer>

<script>
    // Smooth scroll
    document.querySelectorAll('a[href^="#"]').forEach(link => {
        link.addEventListener('click', event => {
            const target = document.querySelector(link.getAttribute('href'));
            if (target) {
                event.preventDefault();
                target.scrollIntoView({ behavior: 'smooth' });
            }
        });
    });

    // Copy script
    function copyScript() {
        const text = document.getElementById('main-script').innerText;
        const btn = document.getElementById('copy-btn');
        navigator.clipboard.writeText(text).then(() => {
            btn.textContent = 'Copied!';
            btn.classList.add('copied');
            setTimeout(() => {
                btn.textContent = 'Copy Script';
                btn.classList.remove('copied');
            }, 2000);
        }).catch(() => {
            // Fallback for older browsers
            const ta = document.createElement('textarea');
            ta.value = text;
            ta.style.position = 'fixed';
            ta.style.opacity = '0';
            document.body.appendChild(ta);
            ta.select();
            document.execCommand('copy');
            document.body.removeChild(ta);
            btn.textContent = 'Copied!';
            btn.classList.add('copied');
            setTimeout(() => {
                btn.textContent = 'Copy Script';
                btn.classList.remove('copied');
            }, 2000);
        });
    }
</script>

</body>
</html>
