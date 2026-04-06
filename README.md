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
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background: var(--dark-bg); color: #f0f0f0; overflow-x: hidden; width: 100%; }

        /* --- Premium Navigation --- */
        header { 
            background: #000; padding: 15px 0; text-align: center; 
            border-bottom: 1px solid var(--border-color); position: sticky; top: 0; z-index: 100; 
        }
        .logo { font-family: 'Orbitron', sans-serif; font-size: clamp(1.2rem, 5vw, 1.8rem); color: var(--neon-yellow); letter-spacing: 3px; margin-bottom: 10px; }
        
        nav { display: flex; justify-content: center; gap: 15px; margin-top: 10px; }
        .nav-btn {
            background: rgba(255, 255, 255, 0.05); border: 1px solid var(--border-color);
            color: #fff; padding: 8px 18px; border-radius: 5px; font-size: 14px; cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); position: relative; overflow: hidden;
        }
        /* Hover Slide Animation */
        .nav-btn:hover {
            background: var(--neon-yellow); color: #000; transform: translateX(5px);
            box-shadow: -5px 0 15px rgba(204, 255, 0, 0.3);
        }

        /* --- Page Transitions --- */
        .page { display: none; width: 95%; max-width: 450px; margin: 10px auto; animation: slideIn 0.4s ease-out; }
        .page.active { display: block; }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* --- Existing UI Components --- */
        #notify-box { 
            background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 255, 255, 0.1); 
            padding: 10px; border-radius: 8px; margin-bottom: 15px; text-align: center; 
            font-weight: bold; color: var(--neon-green); font-size: 13px;
        }
        .box { background: var(--card-bg); border: 1px solid var(--border-color); padding: 15px; border-radius: 12px; margin-bottom: 12px; }
        h2 { font-size: 14px; margin-bottom: 12px; color: var(--neon-yellow); text-transform: uppercase; border-left: 3px solid var(--neon-yellow); padding-left: 8px; }

        /* --- About & Contact Premium Design --- */
        .content-text { line-height: 1.6; color: #ccc; font-size: 15px; }
        .contact-link { display: block; margin-top: 15px; padding: 12px; background: #0088cc; color: #fff; text-decoration: none; border-radius: 8px; text-align: center; font-weight: bold; }
        
        /* Input & Grid Styles */
        input[type="text"] { width: 100%; padding: 12px; background: #000; border: 1px solid #333; color: var(--neon-yellow); border-radius: 8px; text-align: center; font-weight: bold; }
        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .item { background: rgba(0,0,0,0.5); border: 1px solid var(--border-color); padding: 15px; border-radius: 10px; text-align: center; cursor: pointer; }
        .item.active { border-color: var(--neon-green); background: rgba(0, 255, 136, 0.05); }
        .btn-buy { width: 100%; padding: 14px; background: var(--neon-yellow); color: #000; border: none; border-radius: 8px; font-weight: bold; cursor: pointer; margin-top: 8px; }

        /* Footer */
        footer { text-align: center; padding: 25px 10px; border-top: 1px solid var(--border-color); font-size: 10px; background: #000; }
        .glow-text { color: var(--neon-green); text-shadow: 0 0 8px rgba(0, 255, 136, 0.6); font-weight: bold; }

        /* Success & bKash Modals (Same as before) */
        #bkash-modal, #success-popup { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 1000; justify-content: center; align-items: center; }
        .bkash-content, .success-card { background: #fff; width: 92%; max-width: 340px; border-radius: 12px; padding-bottom: 12px; overflow: hidden; }
        .success-card { background: #111; border: 1px solid var(--neon-green); text-align: center; padding: 30px; }
    </style>
</head>
<body onload="startOrderHistory()">

<header>
    <div class="logo">CHOR BAZER</div>
    <nav>
        <button class="nav-btn" onclick="showPage('home')">Home</button>
        <button class="nav-btn" onclick="showPage('about')">About</button>
        <button class="nav-btn" onclick="showPage('contact')">Contact</button>
    </nav>
</header>

<div id="home" class="page active">
    <div id="notify-box">🚀 Secure Top-Up System Ready</div>
    <div class="box">
        <h2>1. Player UID</h2>
        <input type="text" id="uid-input" placeholder="Enter UID here">
    </div>
    <div class="box">
        <h2>2. Select Pack</h2>
        <div class="grid">
            <div class="item" onclick="selectPack(this, 'Weekly Member', 140)">
                <span>Weekly Member</span><span style="display:block; color:var(--neon-green); font-size:18px;">৳ 140</span>
            </div>
            <div class="item" onclick="selectPack(this, 'Monthly Member', 650)">
                <span>Monthly Member</span><span style="display:block; color:var(--neon-green); font-size:18px;">৳ 650</span>
            </div>
        </div>
    </div>
    <div class="box">
        <div style="color:var(--neon-green); font-size:20px; font-weight:bold;">Total: ৳ <span id="sum-total">0</span></div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>
</div>

<div id="about" class="page">
    <div class="box">
        <h2>About Chor Bazer</h2>
        <div class="content-text">
            <p>Welcome to <b>Chor Bazer</b>, the most trusted and fastest gaming top-up platform in Bangladesh.</p><br>
            <p>We specialize in Free Fire Membership and Diamonds with 100% security. Our mission is to provide gamers with a seamless payment experience using bKash and Nagad.</p><br>
            <p>✅ Super Fast Delivery<br>✅ 24/7 Customer Support<br>✅ No ID Risk</p>
        </div>
    </div>
</div>

<div id="contact" class="page">
    <div class="box">
        <h2>Contact Us</h2>
        <div class="content-text">
            <p>কোনো সমস্যা হলে আমাদের সাথে সরাসরি যোগাযোগ করুন।</p>
            <a href="https://wa.me/8801779772201" class="contact-link" target="_blank">Message on WhatsApp</a>
            <p style="margin-top:15px; font-size:13px; text-align:center;">Email: support@chorbazer.com</p>
        </div>
    </div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div style="background:#d12053; color:#fff; padding:20px; text-align:center;">
            <h3>Transaction ID দিন</h3>
            <input type="text" id="trx-input" style="width:100%; margin-top:10px; padding:8px; border-radius:4px; border:none;">
            <p style="font-size:11px; margin-top:10px;">Send Money to: 01779772201</p>
        </div>
        <button onclick="showSuccess()" style="width:90%; margin:10px auto; display:block; padding:12px; background:#d00000; color:#fff; border:none; font-weight:bold; border-radius:4px;">VERIFY</button>
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width:100%; background:none; border:none; color:#999; font-size:10px;">CANCEL</button>
    </div>
</div>

<div id="success-popup">
    <div class="success-card">
        <h2 style="color:var(--neon-green)">ORDER SUCCESS!</h2>
        <p style="margin:15px 0; color:#aaa;">Your order is being processed.</p>
        <button onclick="closeSuccess()" style="background:var(--neon-green); color:#000; border:none; padding:10px 25px; border-radius:5px; font-weight:bold;">OK</button>
    </div>
</div>

<footer>
    © 2026 <span class="glow-text">CHOR BAZER</span> | POWERED BY <span class="glow-text">RRX STUDIOS</span>
</footer>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";
    let notifyInterval;

    function showPage(pageId) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.getElementById(pageId).classList.add('active');
        window.scrollTo(0, 0);
    }

    function selectPack(el, name, price) {
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price; selectedPackName = name;
        document.getElementById('sum-total').innerText = price;
    }

    function openPayment() {
        if(!selectedPrice || !document.getElementById('uid-input').value) return alert("Enter UID & Select Pack!");
        document.getElementById('bkash-modal').style.display = 'flex';
    }

    function showSuccess() {
        if(document.getElementById('trx-input').value.length < 5) return alert("Invalid TrxID!");
        document.getElementById('bkash-modal').style.display = 'none';
        document.getElementById('success-popup').style.display = 'flex';
    }

    function closeSuccess() {
        document.getElementById('success-popup').style.display = 'none';
        showPage('home');
    }

    const fakeData = ["UID 4521***", "UID 9982***", "UID 1025***", "UID 7745***"];
    function startOrderHistory() {
        setInterval(() => {
            const notify = document.getElementById('notify-box');
            notify.style.opacity = '0';
            setTimeout(() => {
                notify.innerText = `✅ ${fakeData[Math.floor(Math.random() * fakeData.length)]} bought ${Math.random()>0.5?'Weekly':'Monthly'}!`;
                notify.style.opacity = '1';
            }, 500);
        }, 10000);
    }
</script>
</body>
</html>
