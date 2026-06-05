// ============================================
// 🔥 BBBL GATEWAY - FREE INTERNET WORKER
// ============================================

// لیست سرورهای آزاد (داینامیک آپدیت میشه)
const FREE_ENDPOINTS = [
    "https://freedom.bbbl.workers.dev",
    "https://gateway.bbbl.workers.dev",
    "https://unblock.bbbl.workers.dev"
];

// سایت‌های معروف برای روت کردن
const TARGETS = {
    yt: "https://www.youtube.com",
    gg: "https://www.google.com",
    tw: "https://www.twitter.com",
    ig: "https://www.instagram.com",
    tg: "https://web.telegram.org"
};

export default {
    async fetch(request, env, ctx) {
        const url = new URL(request.url);
        
        // ===================================
        // لایه 1: تشخیص نوع درخواست
        // ===================================
        const target = url.searchParams.get('target');
        
        if (target && TARGETS[target]) {
            // روتینگ به سایت هدف
            return fetch(TARGETS[target], {
                headers: {
                    ...request.headers,
                    "User-Agent": "Mozilla/5.0 (BBBL Gateway)"
                }
            });
        }
        
        // ===================================
        // لایه 2: پراکسی تمام سایت‌ها
        // ===================================
        const destination = url.searchParams.get('url');
        
        if (destination) {
            try {
                const response = await fetch(destination, {
                    method: request.method,
                    headers: request.headers,
                    body: request.body
                });
                
                // بازنویسی لینک‌ها برای ماندن در پراکسی
                let body = await response.text();
                body = body.replace(/href="\//g, `href="/?url=${destination}/`);
                body = body.replace(/src="\//g, `src="/?url=${destination}/`);
                
                return new Response(body, {
                    status: response.status,
                    headers: {
                        "Content-Type": response.headers.get("Content-Type"),
                        "Cache-Control": "no-cache",
                        "Access-Control-Allow-Origin": "*"
                    }
                });
                
            } catch(e) {
                return new Response(`❌ Error: ${e.message}`, { status: 500 });
            }
        }
        
        // ===================================
        // لایه 3: صفحه اصلی گیت‌وی
        // ===================================
        return new Response(`
            <!DOCTYPE html>
            <html>
            <head>
                <title>BBBL Gateway - Free Internet</title>
                <style>
                    body {
                        background: #0a0a0a;
                        color: white;
                        font-family: monospace;
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        height: 100vh;
                    }
                    .container {
                        text-align: center;
                        max-width: 600px;
                    }
                    input {
                        width: 100%;
                        padding: 15px;
                        background: #1a1a1a;
                        border: 1px solid #333;
                        color: white;
                        border-radius: 10px;
                        font-size: 16px;
                    }
                    button {
                        margin-top: 20px;
                        padding: 12px 30px;
                        background: white;
                        color: black;
                        border: none;
                        border-radius: 10px;
                        cursor: pointer;
                        font-weight: bold;
                    }
                    .shortcuts {
                        margin-top: 30px;
                        display: flex;
                        gap: 10px;
                        flex-wrap: wrap;
                        justify-content: center;
                    }
                    .shortcut {
                        background: #1a1a1a;
                        padding: 8px 16px;
                        border-radius: 20px;
                        text-decoration: none;
                        color: white;
                    }
                </style>
            </head>
            <body>
                <div class="container">
                    <h1>🌐 BBBL GATEWAY</h1>
                    <p>Beyond Borders, Beyond Limits</p>
                    
                    <input type="text" id="urlInput" placeholder="Enter URL (https://...)" />
                    <button onclick="go()">🌍 GO</button>
                    
                    <div class="shortcuts">
                        <a href="/?target=yt" class="shortcut">▶️ YouTube</a>
                        <a href="/?target=gg" class="shortcut">🔍 Google</a>
                        <a href="/?target=tw" class="shortcut">🐦 Twitter</a>
                        <a href="/?target=ig" class="shortcut">📸 Instagram</a>
                        <a href="/?target=tg" class="shortcut">✈️ Telegram</a>
                    </div>
                    
                    <p style="margin-top: 40px; font-size: 12px; color: #666;">
                        🔒 100% Encrypted | 🚫 Zero Logs | ⚡ Global Network
                    </p>
                </div>
                
                <script>
                    function go() {
                        const url = document.getElementById('urlInput').value;
                        if(url) {
                            window.location.href = '/?url=' + encodeURIComponent(url);
                        }
                    }
                </script>
            </body>
            </html>
        `, {
            headers: { "Content-Type": "text/html" }
        });
    }
};
