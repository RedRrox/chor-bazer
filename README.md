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
        .logo { font-family: 'Orbitron', sans-serif; font-size: clamp(1.2rem, 5vw, 1.8rem); color: var(--neon-yellow); letter-spacing: 3px; }

        .container { width: 95%; max-width: 450px; margin: 10px auto; padding-bottom: 20px; }

        /* Order History Style */
        #notify-box { 
            background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 255, 255, 0.1); 
            padding: 10px; border-radius: 8px; margin-bottom: 15px; text-align: center; 
            font-weight: bold; color: var(--neon-green); font-size: 13px; transition: opacity 0.5s ease-in-out;
        }

        .box { background: var(--card-bg); border: 1px solid var(--border-color); padding: 15px; border-radius: 12px; margin-bottom: 12px; }
        h2 { font-size: 14px; margin-bottom: 12px; color: var(--neon-yellow); text-transform: uppercase; border-left: 3px solid var(--neon-yellow); padding-left: 8px; }

        input[type="text"] { 
            width: 100%; padding: 12px; background: #000; border: 1px solid #333; 
            color: var(--neon-yellow); border-radius: 8px; font-size: 16px; outline: none; text-align: center; font-weight: bold;
        }

        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .item { 
            background: rgba(0,0,0,0.5); border: 1px solid var(--border-color); padding: 15px; 
            border-radius: 10px; cursor: pointer; text-align: center; position: relative; overflow: hidden;
        }
        .item.active { border-color: var(--neon-green); background: rgba(0, 255, 136, 0.05); }
        .item span { font-size: 12px; color: #999; }
        .item .price { color: var(--neon-green); font-weight: bold; font-size: 18px; display: block; }

        .special-badge { position: absolute; top: 0; left: 0; background: #ff4444; color: #fff; font-size: 8px; font-weight: 800; padding: 2px 8px; border-radius: 0 0 8px 0; }
        .premium-card { grid-column: span 2; border: 1px solid #ff4444 !important; opacity: 0.8; cursor: not-allowed; }
        .stock-tag { background: #ff4444; color: #fff; font-size: 9px; padding: 1px 6px; border-radius: 4px; margin-top: 4px; display: inline-block; }

        .total { color: var(--neon-green); font-size: 20px; font-weight: bold; border-top: 1px solid #222; padding-top: 8px; margin-top: 8px; }
        .btn-buy { width: 100%; padding: 14px; background: var(--neon-yellow); color: #000; border: none; border-radius: 8px; font-weight: bold; font-size: 16px; cursor: pointer; margin-top: 8px; text-transform: uppercase; }

        /* --- bKash Modal --- */
        #bkash-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 1000; justify-content: center; align-items: center; }
        .bkash-content { background: #fff; width: 92%; max-width: 340px; border-radius: 12px; overflow: hidden; color: #333; padding-bottom: 12px; }
        .bkash-header { padding: 8px; text-align: center; border-bottom: 1px solid #eee; }
        .bkash-header img { width: 70px; }
        .bkash-main-body { background: #d12053; color: #fff; padding: 12px; margin: 0 10px; border-radius: 8px; text-align: center; }
        .bkash-steps { text-align: left; font-size: 11px; line-height: 1.5; border-top: 1px solid rgba(255,255,255,0.2); padding-top: 10px; margin-top: 10px; }
        .verify-red-btn { width: 90%; margin: 10px auto 0; display: block; padding: 12px; background: #d00000; color: #fff; border: none; font-weight: bold; cursor: pointer; font-size: 14px; border-radius: 4px; }

        /* --- Success Animation Popup --- */
        #success-popup {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.85); z-index: 2000; justify-content: center; align-items: center;
        }
        .success-card {
            background: #111; border: 1px solid var(--neon-green); width: 85%; max-width: 300px;
            padding: 30px; border-radius: 20px; text-align: center; transform: scale(0.7); animation: popIn 0.4s forwards;
        }
        .checkmark-circle { width: 80px; height: 80px; border-radius: 50%; display: block; stroke-width: 2; stroke: var(--neon-green); margin: 0 auto 20px; }
        .checkmark-check { transform-origin: 50% 50%; stroke-dasharray: 48; stroke-dashoffset: 48; animation: stroke .3s cubic-bezier(0.65, 0, 0.45, 1) .8s forwards; }

        @keyframes stroke { 100% { stroke-dashoffset: 0; } }
        @keyframes popIn { to { transform: scale(1); } }

        /* --- Glowing Footer --- */
        footer { text-align: center; padding: 25px 10px; margin-top: 20px; border-top: 1px solid var(--border-color); font-size: 10px; color: #666; background: #000; letter-spacing: 1px; }
        .glow-text { color: var(--neon-green); text-shadow: 0 0 8px rgba(0, 255, 136, 0.6); font-weight: bold; }
    </style>
</head>
<body onload="startOrderHistory()">

<header><div class="logo">CHOR BAZER</div></header>

<div class="container">
    <div id="notify-box">🚀 Initializing Chor Bazer server...</div>

    <div class="box">
        <h2>1. Player UID</h2>
        <input type="text" id="uid-input" placeholder="Enter UID here">
    </div>

    <div class="box">
        <h2>2. Select Pack</h2>
        <div class="grid">
            <div class="item premium-card">
                <div class="special-badge">LIMITED TIME</div>
                <span style="font-weight:700;">💎 2x Monthly Member 💎</span>
                <span class="price" style="opacity: 0.5;">৳ 1</span>
                <span class="stock-tag">OUT OF STOCK</span>
            </div>
            <div class="item" onclick="selectPack(this, 'Weekly Member', 140)">
                <span>Weekly Member</span><span class="price">৳ 140</span>
            </div>
            <div class="item" onclick="selectPack(this, 'Monthly Member', 650)">
                <span>Monthly Member</span><span class="price">৳ 650</span>
            </div>
        </div>
    </div>

    <div class="box summary">
        <h2>3. Order Summary</h2>
        <div class="total">Total: ৳ <span id="sum-total">0</span></div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div class="bkash-header"><img src="bikashlogo.png" alt="bkash"></div>
        <div class="bkash-main-body">
            <h3 style="margin-bottom:10px;">ট্রান্সজেকশন আইডি দিন</h3>
            <input type="text" id="trx-input" style="width:100%; padding:10px; border-radius:5px; border:none; text-align:center;">
            <div class="bkash-steps">
                <p>● <b>"Send Money"</b> করুনঃ <b>01779772201</b> <button onclick="copyNum()" style="padding:2px 5px; font-size:9px;">Copy</button></p>
                <p>● টাকার পরিমাণঃ ৳ <b id="pay-amount">0</b></p>
                <p>● পেমেন্ট শেষে ট্রানজেকশন আইডি উপরে দিন।</p>
            </div>
        </div>
        <button class="verify-red-btn" onclick="showSuccess()">VERIFY</button>
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width:100%; background:none; border:none; padding:10px; color:#999; font-size:10px;">CANCEL</button>
    </div>
</div>

<div id="success-popup">
    <div class="success-card">
        <svg class="checkmark-circle" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 52 52">
            <circle cx="26" cy="26" r="25" fill="none" stroke="var(--neon-green)" stroke-width="2"/>
            <path class="checkmark-check" fill="none" stroke="var(--neon-green)" stroke-width="4" d="M14.1 27.2l7.1 7.2 16.7-16.8"/>
        </svg>
        <h3 style="color:var(--neon-green); margin-bottom:10px;">ORDER SUCCESS!</h3>
        <p style="font-size:13px; color:#aaa;">Check Notification Box for updates.</p>
        <button onclick="closeSuccess()" style="margin-top:20px; background:var(--neon-green); color:#000; border:none; padding:10px 20px; border-radius:5px; font-weight:bold;">CLOSE</button>
    </div>
</div>

<footer>
    © 2026 <span class="glow-text">CHOR BAZER</span> | POWERED BY <span class="glow-text">RRX STUDIOS</span>
</footer>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";
    let notifyInterval;

    // Order History Logic
    const fakeData = ["UID 4521***", "UID 9982***", "UID 1002***", "UID 7745***", "UID 1025***", "UID 8821***", "UID 3341***"];
    function startOrderHistory() {
        notifyInterval = setInterval(() => {
            const notify = document.getElementById('notify-box');
            notify.style.opacity = '0';
            setTimeout(() => {
                const randomID = fakeData[Math.floor(Math.random() * fakeData.length)];
                const randomPack = Math.random() > 0.5 ? 'Weekly' : 'Monthly';
                notify.innerText = `✅ ${randomID} just bought ${randomPack}!`;
                notify.style.opacity = '1';
            }, 500);
        }, 10000);
    }

    function selectPack(el, name, price) {
        if(el.classList.contains('premium-card')) return;
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price; selectedPackName = name;
        document.getElementById('sum-total').innerText = price;
        document.getElementById('pay-amount').innerText = price;
    }

    function openPayment() {
        if(!selectedPrice || !document.getElementById('uid-input').value) return alert("Please enter UID & select a Pack!");
        document.getElementById('bkash-modal').style.display = 'flex';
    }

    function showSuccess() {
        if(document.getElementById('trx-input').value.trim().length < 5) return alert("Invalid TrxID!");
        document.getElementById('bkash-modal').style.display = 'none';
        document.getElementById('success-popup').style.display = 'flex';
        
        // Update History Immediately on Success
        clearInterval(notifyInterval);
        const userUID = document.getElementById('uid-input').value;
        const notify = document.getElementById('notify-box');
        notify.innerHTML = `<span style="color:var(--neon-green)">🔥 SUCCESS! ${userUID} purchased ${selectedPackName}.</span>`;
    }

    function closeSuccess() {
        document.getElementById('success-popup').style.display = 'none';
        startOrderHistory(); // Resume history
    }

    function copyNum() { navigator.clipboard.writeText("01779772201"); alert("Number Copied!"); }
</script>

</body>
</html>
