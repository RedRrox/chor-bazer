<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CHOR BAZER | FF UID TOP UP</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;800&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --neon-yellow: #ccff00;
            --dark-bg: #0a0a0a;
            --card-bg: #151515;
            --bkash-color: #d12053;
            --gold: #ffd700;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background: var(--dark-bg); color: #fff; padding-bottom: 50px; transition: 0.3s; }

        header { background: #000; padding: 25px; text-align: center; border-bottom: 2px solid var(--neon-yellow); box-shadow: 0 0 20px rgba(204, 255, 0, 0.2); }
        .logo { font-family: 'Orbitron', sans-serif; font-size: 35px; color: var(--neon-yellow); letter-spacing: 5px; }

        .container { max-width: 600px; margin: 20px auto; padding: 15px; }

        #notify-box { background: rgba(204, 255, 0, 0.05); border: 1px dashed var(--neon-yellow); padding: 12px; border-radius: 8px; margin-bottom: 20px; text-align: center; font-weight: bold; color: var(--neon-yellow); font-size: 14px; transition: opacity 0.5s ease-in-out; }

        .box { background: var(--card-bg); border: 1px solid #222; padding: 20px; border-radius: 12px; margin-bottom: 20px; }
        h2 { font-size: 18px; margin-bottom: 15px; color: var(--neon-yellow); text-transform: uppercase; border-left: 4px solid var(--neon-yellow); padding-left: 10px; }

        input[type="text"] { width: 100%; padding: 15px; background: #000; border: 1px solid #333; color: var(--neon-yellow); border-radius: 8px; font-size: 18px; outline: none; text-align: center; font-weight: bold; }

        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
        .item { background: #000; border: 1px solid #222; padding: 20px; border-radius: 10px; cursor: pointer; text-align: center; transition: 0.3s; position: relative; overflow: hidden; }
        .item:hover { border-color: var(--neon-yellow); }
        .item.active { border-color: var(--neon-yellow); background: rgba(204, 255, 0, 0.08); }
        .item .price { color: var(--neon-yellow); font-weight: bold; font-size: 22px; display: block; }

        /* --- RED LIMITED TIME BAGE --- */
        .special-badge {
            position: absolute;
            top: 0;
            left: 0;
            background: #ff0000; /* লাল রং */
            color: #fff;
            font-size: 10px;
            font-weight: 800;
            padding: 2px 10px;
            border-radius: 0 0 10px 0;
            box-shadow: 0 0 10px rgba(255, 0, 0, 0.5);
        }
        .premium-card { grid-column: span 2; border: 2px solid #ff0000 !important; cursor: not-allowed; }
        .premium-card .price { color: #ff0000 !important; text-decoration: line-through; opacity: 0.5; }
        .stock-tag { background: #ff4444; color: #fff; font-size: 10px; padding: 2px 8px; border-radius: 4px; margin-top: 5px; display: inline-block; font-weight: 800; }

        .summary p { display: flex; justify-content: space-between; margin-bottom: 8px; color: #aaa; }
        .total { color: var(--neon-yellow); font-size: 24px; font-weight: bold; border-top: 1px solid #333; padding-top: 10px; margin-top: 10px; }
        .btn-buy { width: 100%; padding: 18px; background: var(--neon-yellow); color: #000; border: none; border-radius: 8px; font-weight: bold; font-size: 20px; cursor: pointer; margin-top: 10px; }

        /* --- BKASH MODAL HUBEHU SAME DESIGN --- */
        #bkash-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 9999; justify-content: center; align-items: center; }
        .bkash-content { background: #fff; width: 92%; max-width: 400px; border-radius: 12px; overflow: hidden; color: #000; box-shadow: 0 10px 30px rgba(0,0,0,0.5); }
        .bkash-header { background: #fff; padding: 10px; text-align: center; border-bottom: 1px solid #eee; display: flex; justify-content: center; }
        .bkash-header img { width: 100px; height: auto; }
        .bkash-body { background: var(--bkash-color); color: #fff; padding: 20px; text-align: left; }
        .instr { font-size: 13px; margin-bottom: 10px; border-bottom: 1px solid rgba(255,255,255,0.2); padding-bottom: 8px; }
        .instr b { color: var(--neon-yellow); }
        .trx-input { width: 100%; padding: 14px; margin: 10px 0; border-radius: 6px; border: none; font-size: 18px; text-align: center; font-weight: bold; text-transform: uppercase; }
        .copy-btn { background: #fff; color: #000; border: none; padding: 2px 8px; border-radius: 4px; font-size: 10px; cursor: pointer; margin-left: 10px; font-weight: bold; }
        .delivery-notice { background: #fff9c4; color: #d32f2f; padding: 10px; font-size: 12px; text-align: center; font-weight: bold; border-top: 1px dashed #ccc; }
        .verify-btn { width: 90%; margin: 15px auto; display: block; padding: 15px; background: #d00000; color: #fff; border: none; font-weight: bold; cursor: pointer; font-size: 18px; border-radius: 8px; text-transform: uppercase; }
    </style>
</head>
<body>

<header><div class="logo">CHOR BAZER</div></header>

<div class="container">
    <div id="notify-box">🚀 Initializing Chor Bazer server...</div>

    <div class="box">
        <h2>1. Player UID</h2>
        <input type="text" id="uid-input" placeholder="Enter Player UID" oninput="updateID()">
    </div>

    <div class="box">
        <h2>2. Select Pack</h2>
        <div class="grid">
            <div class="item premium-card">
                <div class="special-badge">LIMITED TIME</div>
                <span style="color:var(--gold); font-weight:800; font-size:18px;">💎 2x Monthly Member 💎</span>
                <span class="price">৳ 1</span>
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
        <p>Selected: <span id="sum-pack">-</span></p>
        <p>Player ID: <span id="sum-id">-</span></p>
        <div class="total">Total: ৳ <span id="sum-total">0</span></div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div class="bkash-header"><img src="bikashlogo.png" alt="bkash"></div>
        <div class="bkash-body">
            <p style="text-align: center; font-weight: bold; margin-bottom: 15px;">ট্রানজেকশন আইডি দিন</p>
            <input type="text" class="trx-input" id="trx-input" placeholder="TrxID">
            <div class="instr">● নম্বরঃ <b>017797722010</b> <button class="copy-btn" onclick="copyNum()">COPY</button></div>
            <div class="instr">● টাকার পরিমাণঃ ৳ <b id="pay-amount">0</b></div>
            <div class="instr">● পেমেন্ট শেষে ট্রানজেকশন আইডি উপরে দিন।</div>
        </div>
        <div class="delivery-notice">⚠️ ডেলিভারি সময় ৩০-৪০ মিনিট।</div>
        <button class="verify-btn" onclick="verifyRealOrder()">VERIFY</button>
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width: 100%; background: #f5f5f5; border: none; padding: 12px; cursor: pointer; color: #666; font-weight: bold;">CANCEL</button>
    </div>
</div>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";
    let notifyInterval;

    // Fake Orders (10 seconds delay)
    const fakeData = ["ID 4521*** just bought Weekly!", "UID 9982*** received Monthly!", "Order #8841 for ID 1002*** completed!", "Success! UID 7745*** got Weekly Member."];
    function startFake() {
        notifyInterval = setInterval(() => {
            const notify = document.getElementById('notify-box');
            notify.style.opacity = '0';
            setTimeout(() => {
                notify.innerText = "🔥 " + fakeData[Math.floor(Math.random() * fakeData.length)];
                notify.style.opacity = '1';
            }, 500);
        }, 10000);
    }

    function verifyRealOrder() {
        if(document.getElementById('trx-input').value.length < 5) return alert("Invalid TrxID!");
        clearInterval(notifyInterval);
        const notify = document.getElementById('notify-box');
        notify.innerHTML = `<span style="color:#00ff88">✅ ORDER DONE! ${document.getElementById('uid-input').value} just purchased ${selectedPackName}.</span>`;
        alert("অর্ডার সফল! ৩০-৪০ মিনিটের মধ্যে ডেলিভারি পাবেন।");
        document.getElementById('bkash-modal').style.display = 'none';
        setTimeout(startFake, 15000);
    }

    function selectPack(el, name, price) {
        if(el.classList.contains('premium-card')) return;
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price; selectedPackName = name;
        document.getElementById('sum-pack').innerText = name;
        document.getElementById('sum-total').innerText = price;
        document.getElementById('pay-amount').innerText = price;
    }

    function updateID() { document.getElementById('sum-id').innerText = document.getElementById('uid-input').value || "-"; }
    function openPayment() { if(!selectedPrice) return alert("Select Pack!"); document.getElementById('bkash-modal').style.display = 'flex'; }
    function copyNum() { navigator.clipboard.writeText("017797722010"); alert("Number Copied!"); }

    startFake();
</script>

</body>
</html>
