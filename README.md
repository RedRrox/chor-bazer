<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CHOR BAZER | PREMIUM TOP UP</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;800&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --neon-green: #00ff88;
            --neon-yellow: #ccff00;
            --dark-bg: #030303;
            --card-bg: rgba(20, 20, 20, 0.95);
            --border-color: rgba(255, 255, 255, 0.08);
            --bkash-color: #d12053;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background: var(--dark-bg); color: #f0f0f0; overflow-x: hidden; width: 100%; }

        header { background: #000; padding: 15px 0; text-align: center; border-bottom: 1px solid var(--border-color); position: sticky; top: 0; z-index: 100; }
        .logo { font-family: 'Orbitron', sans-serif; font-size: clamp(1.2rem, 5vw, 1.8rem); color: var(--neon-yellow); letter-spacing: 3px; margin-bottom: 10px; }
        
        nav { display: flex; justify-content: center; gap: 8px; margin-top: 10px; flex-wrap: wrap; }
        .nav-btn {
            background: rgba(255, 255, 255, 0.05); border: 1px solid var(--border-color);
            color: #fff; padding: 6px 12px; border-radius: 5px; font-size: 12px; cursor: pointer;
        }
        .nav-btn:hover { background: var(--neon-yellow); color: #000; }

        .page { display: none; width: 95%; max-width: 450px; margin: 10px auto; animation: fadeIn 0.4s; }
        .page.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        #notify-box { 
            background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 255, 255, 0.1); 
            padding: 10px; border-radius: 8px; margin-bottom: 15px; text-align: center; 
            font-weight: bold; color: var(--neon-green); font-size: 13px;
        }

        .box { background: var(--card-bg); border: 1px solid var(--border-color); padding: 15px; border-radius: 12px; margin-bottom: 12px; }
        h2 { font-size: 14px; margin-bottom: 12px; color: var(--neon-yellow); text-transform: uppercase; border-left: 3px solid var(--neon-yellow); padding-left: 8px; }

        /* Auth Styles */
        .auth-container { text-align: center; padding: 20px; }
        .auth-btn { width: 100%; padding: 12px; margin-top: 10px; border-radius: 8px; border: none; font-weight: bold; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 10px; }
        .google-btn { background: #fff; color: #000; }
        .fb-btn { background: #1877F2; color: #fff; }

        /* Profile Styles */
        .profile-header { display: flex; align-items: center; gap: 15px; margin-bottom: 20px; }
        .profile-img { width: 60px; height: 60px; border-radius: 50%; background: var(--neon-yellow); border: 2px solid var(--neon-green); }
        .stats-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 15px; }
        .stat-card { background: rgba(255,255,255,0.05); padding: 10px; border-radius: 8px; text-align: center; }

        .item { background: rgba(0,0,0,0.5); border: 1px solid var(--border-color); padding: 15px; border-radius: 10px; text-align: center; cursor: pointer; position: relative; }
        .item.active { border-color: var(--neon-green); background: rgba(0, 255, 136, 0.05); }
        .price { color: var(--neon-green); font-weight: bold; font-size: 18px; display: block; }

        .btn-buy { width: 100%; padding: 14px; background: var(--neon-yellow); color: #000; border: none; border-radius: 8px; font-weight: bold; cursor: pointer; margin-top: 10px; }

        /* bKash & Popups */
        #bkash-modal, #success-popup { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 1000; justify-content: center; align-items: center; }
        .bkash-content, .success-card { background: #fff; width: 92%; max-width: 340px; border-radius: 12px; overflow: hidden; }
        .success-card { background: #111; border: 1px solid var(--neon-green); text-align: center; padding: 30px; }

        footer { text-align: center; padding: 25px 10px; border-top: 1px solid var(--border-color); font-size: 10px; background: #000; }
        .glow-text { color: var(--neon-green); text-shadow: 0 0 8px rgba(0, 255, 136, 0.6); font-weight: bold; }
    </style>
</head>
<body onload="initApp()">

<header>
    <div class="logo">CHOR BAZER</div>
    <nav id="main-nav">
        <button class="nav-btn" onclick="showPage('home')">Home</button>
        <button class="nav-btn" onclick="showPage('about')">About</button>
        <button class="nav-btn" onclick="showPage('contact')">Contact</button>
        <button class="nav-btn" id="login-nav-btn" onclick="showPage('login')">Login</button>
        <button class="nav-btn" id="profile-nav-btn" style="display:none;" onclick="showPage('profile')">My Account</button>
    </nav>
</header>

<div id="login" class="page">
    <div class="box auth-container">
        <h2>Join Chor Bazer</h2>
        <p style="font-size:13px; color:#aaa; margin-bottom:20px;">Please login to place an order</p>
        <button class="auth-btn google-btn" onclick="handleAuth('Google User')"> Continue with Google</button>
        <button class="auth-btn fb-btn" onclick="handleAuth('Facebook User')"> Continue with Facebook</button>
    </div>
</div>

<div id="profile" class="page">
    <div class="box">
        <div class="profile-header">
            <div class="profile-img"></div>
            <div>
                <h3 id="user-name-display">User Name</h3>
                <p id="user-email" style="font-size:12px; color:#777;">logged in</p>
            </div>
        </div>
        <div class="stats-grid">
            <div class="stat-card">
                <span style="font-size:10px; color:#aaa;">Total Spent</span>
                <div style="color:var(--neon-green); font-size:18px; font-weight:bold;">৳ <span id="total-spent">0</span></div>
            </div>
            <div class="stat-card">
                <span style="font-size:10px; color:#aaa;">Total Orders</span>
                <div style="color:var(--neon-yellow); font-size:18px; font-weight:bold;"><span id="order-count">0</span></div>
            </div>
        </div>
    </div>
    <div class="box">
        <h2>Order History</h2>
        <div id="my-orders" style="font-size:13px; color:#ccc;">
            No orders placed yet.
        </div>
    </div>
    <button onclick="logout()" style="width:100%; background:none; border:1px solid #ff4444; color:#ff4444; padding:10px; border-radius:8px; cursor:pointer;">Logout</button>
</div>

<div id="home" class="page active">
    <div id="notify-box">🚀 Loading server...</div>
    <div class="box">
        <h2>1. Player UID</h2>
        <input type="text" id="uid-input" placeholder="Enter Player UID here">
    </div>
    <div class="box">
        <h2>2. Select Pack</h2>
        <div class="grid">
            <div class="item" onclick="selectPack(this, 'Weekly Member', 140)">
                <span>Weekly Member</span><span class="price">৳ 140</span>
            </div>
            <div class="item" onclick="selectPack(this, 'Monthly Member', 650)">
                <span>Monthly Member</span><span class="price">৳ 650</span>
            </div>
        </div>
    </div>
    <div class="box">
        <div style="color:var(--neon-green); font-size:20px; font-weight:bold;">Total: ৳ <span id="sum-total">0</span></div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>
</div>

<div id="about" class="page">
    <div class="box"><h2>About</h2><p>Trusted Top-up Platform.</p></div>
</div>
<div id="contact" class="page">
    <div class="box"><h2>Contact</h2><button class="nav-btn">WhatsApp</button></div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div style="background:#d12053; color:#fff; padding:20px; text-align:center;">
            <h3>Transaction ID</h3>
            <input type="text" id="trx-input" style="width:100%; padding:8px; margin:10px 0;">
            <p style="font-size:11px;">Send Money to: 01779772201</p>
        </div>
        <button class="verify-red-btn" onclick="handleRealOrder()" style="width:90%; margin:10px auto; display:block; padding:12px; background:#d00000; color:#fff; border:none; font-weight:bold;">VERIFY</button>
    </div>
</div>

<div id="success-popup">
    <div class="success-card">
        <h2 style="color:var(--neon-green)">ORDER SUCCESS!</h2>
        <button onclick="closeSuccess()" style="margin-top:20px; background:var(--neon-green); color:#000; border:none; padding:10px 25px; border-radius:5px; font-weight:bold;">CLOSE</button>
    </div>
</div>

<footer>
    © 2026 <span class="glow-text">CHOR BAZER</span> | POWERED BY <span class="glow-text">RRX STUDIOS</span>
</footer>

<script>
    let currentUser = null;
    let selectedPrice = 0;
    let selectedPackName = "";
    let userStats = { spent: 0, orders: [] };

    function initApp() {
        const savedUser = localStorage.getItem('chor_user');
        const savedStats = localStorage.getItem('chor_stats');
        if(savedUser) {
            currentUser = savedUser;
            if(savedStats) userStats = JSON.parse(savedStats);
            updateUIForLogin();
        }
        startOrderHistory();
    }

    function showPage(pageId) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.getElementById(pageId).classList.add('active');
    }

    function handleAuth(name) {
        currentUser = name;
        localStorage.setItem('chor_user', name);
        updateUIForLogin();
        showPage('home');
    }

    function updateUIForLogin() {
        document.getElementById('login-nav-btn').style.display = 'none';
        document.getElementById('profile-nav-btn').style.display = 'inline-block';
        document.getElementById('user-name-display').innerText = currentUser;
        updateProfileData();
    }

    function logout() {
        localStorage.removeItem('chor_user');
        location.reload();
    }

    function selectPack(el, name, price) {
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price; selectedPackName = name;
        document.getElementById('sum-total').innerText = price;
    }

    function openPayment() {
        if(!currentUser) {
            alert("অর্ডার করতে আগে লগইন করুন!");
            showPage('login');
            return;
        }
        if(!selectedPrice || !document.getElementById('uid-input').value) return alert("UID ও প্যাক সিলেক্ট করুন!");
        document.getElementById('bkash-modal').style.display = 'flex';
    }

    function handleRealOrder() {
        if(document.getElementById('trx-input').value.length < 5) return alert("Invalid TrxID!");
        
        // Save Order to History
        const newOrder = {
            pack: selectedPackName,
            price: selectedPrice,
            date: new Date().toLocaleDateString()
        };
        userStats.orders.push(newOrder);
        userStats.spent += selectedPrice;
        localStorage.setItem('chor_stats', JSON.stringify(userStats));
        
        document.getElementById('bkash-modal').style.display = 'none';
        document.getElementById('success-popup').style.display = 'flex';
        updateProfileData();
    }

    function updateProfileData() {
        document.getElementById('total-spent').innerText = userStats.spent;
        document.getElementById('order-count').innerText = userStats.orders.length;
        const container = document.getElementById('my-orders');
        if(userStats.orders.length > 0) {
            container.innerHTML = userStats.orders.map(o => 
                `<div style="border-bottom:1px solid #222; padding:8px 0;">
                    ${o.date} - ${o.pack} <span style="float:right; color:var(--neon-green)">৳${o.price}</span>
                </div>`
            ).join('');
        }
    }

    function closeSuccess() {
        document.getElementById('success-popup').style.display = 'none';
        showPage('profile');
    }

    function startOrderHistory() {
        const fakes = ["UID 4521***", "UID 9982***", "UID 1025***", "UID 7745***"];
        setInterval(() => {
            const notify = document.getElementById('notify-box');
            notify.style.opacity = '0';
            setTimeout(() => {
                notify.innerText = `✅ ${fakes[Math.floor(Math.random() * fakes.length)]} bought ${Math.random()>0.5?'Weekly':'Monthly'}!`;
                notify.style.opacity = '1';
            }, 500);
        }, 10000);
    }
</script>
</body>
</html>
