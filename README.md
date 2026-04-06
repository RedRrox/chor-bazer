<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CHOR BAZER | GAME TOP UP</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;800&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --neon-yellow: #ccff00;
            --dark-bg: #0a0a0a;
            --card-bg: #151515;
            --bkash-color: #d12053;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background: var(--dark-bg); color: #fff; padding-bottom: 50px; }

        header { background: #000; padding: 25px; text-align: center; border-bottom: 2px solid var(--neon-yellow); box-shadow: 0 0 20px rgba(204, 255, 0, 0.2); }
        .logo { font-family: 'Orbitron', sans-serif; font-size: 35px; color: var(--neon-yellow); letter-spacing: 5px; }

        .container { max-width: 600px; margin: 20px auto; padding: 15px; }

        /* Notification Box */
        #notify-box { 
            background: rgba(204, 255, 0, 0.05); 
            border: 1px dashed var(--neon-yellow); 
            padding: 12px; 
            border-radius: 8px; 
            margin-bottom: 20px; 
            text-align: center; 
            font-weight: bold; 
            color: var(--neon-yellow); 
            font-size: 14px;
            transition: all 0.5s ease-in-out;
        }

        .real-order-active { 
            color: #00ff88 !important; 
            border: 2px solid #00ff88 !important; 
            background: rgba(0, 255, 136, 0.1) !important; 
            transform: scale(1.02);
        }

        .box { background: var(--card-bg); border: 1px solid #222; padding: 20px; border-radius: 12px; margin-bottom: 20px; }
        h2 { font-size: 18px; margin-bottom: 15px; color: var(--neon-yellow); text-transform: uppercase; border-left: 4px solid var(--neon-yellow); padding-left: 10px; }

        input[type="text"] { width: 100%; padding: 15px; background: #000; border: 1px solid #333; color: var(--neon-yellow); border-radius: 8px; font-size: 18px; outline: none; text-align: center; font-weight: bold; }

        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
        .item { background: #000; border: 1px solid #222; padding: 20px; border-radius: 10px; cursor: pointer; text-align: center; transition: 0.3s; }
        .item.active { border-color: var(--neon-yellow); background: rgba(204, 255, 0, 0.08); }
        .item .price { color: var(--neon-yellow); font-weight: bold; font-size: 22px; display: block; }

        .summary p { display: flex; justify-content: space-between; margin-bottom: 8px; color: #aaa; }
        .summary .total { color: var(--neon-yellow); font-size: 24px; font-weight: bold; border-top: 1px solid #333; padding-top: 10px; margin-top: 10px; }

        /* Payment Methods */
        .pay-method { display: flex; gap: 15px; margin-top: 15px; }
        .logo-crop { width: 80px; height: 45px; overflow: hidden; display: flex; justify-content: center; align-items: flex-start; }
        .logo-crop img { width: 80px; height: auto; }
        .method { flex: 1; padding: 15px; border: 1px solid #222; border-radius: 10px; text-align: center; cursor: pointer; position: relative; background: #000; display: flex; align-items: center; justify-content: center; min-height: 85px; }
        .method.active { border-color: var(--bkash-color); background: rgba(209, 32, 83, 0.05); }

        /* Original bKash Modal Style */
        #bkash-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 9999; justify-content: center; align-items: center; }
        .bkash-content { background: #fff; width: 92%; max-width: 400px; border-radius: 12px; overflow: hidden; color: #000; }
        .bkash-header { background: #fff; padding: 15px; text-align: center; border-bottom: 1px solid #eee; display: flex; justify-content: center; }
        .header-crop { width: 120px; height: 65px; overflow: hidden; }
        .header-crop img { width: 120px; height: auto; }
        .bkash-body { background: var(--bkash-color); color: #fff; padding: 20px; text-align: left; }
        .instr { font-size: 13px; margin-bottom: 10px; border-bottom: 1px solid rgba(255,255,255,0.2); padding-bottom: 8px; }
        .instr b { color: var(--neon-yellow); }
        .trx-input { width: 100%; padding: 14px; margin: 10px 0; border-radius: 6px; border: none; font-size: 18px; text-align: center; font-weight: bold; text-transform: uppercase; }
        .copy-btn { background: #fff; color: #000; border: none; padding: 2px 8px; border-radius: 4px; font-size: 10px; cursor: pointer; margin-left: 10px; font-weight: bold; }
        .delivery-notice { background: #fff9c4; color: #d32f2f; padding: 10px; font-size: 12px; text-align: center; font-weight: bold; border-top: 1px dashed #ccc; }
        .verify-btn { width: 90%; margin: 15px auto; display: block; padding: 15px; background: #d00000; color: #fff; border: none; font-weight: bold; cursor: pointer; font-size: 18px; border-radius: 8px; text-transform: uppercase; }
        .btn-buy { width: 100%; padding: 18px; background: var(--neon-yellow); color: #000; border: none; border-radius: 8px; font-weight: bold; font-size: 20px; cursor: pointer; margin-top: 10px; }
    </style>
</head>
<body>

<header>
    <div class="logo">CHOR BAZER</div>
</header>

<div class="container">
    <div id="notify-box">🚀 Loading Chor Bazer Secure System...</div>

    <div class="box">
        <h2>1. Player UID / Roblox Username</h2>
        <input type="text" id="uid-input" placeholder="Enter UID or Username" oninput="updateID()">
    </div>

    <div class="box">
        <h2>2. Select Pack</h2>
        <div class="grid">
            <div class="item" onclick="selectPack(this, 'Weekly Member', 140)"><span>Weekly Member</span><span class="price">৳ 140</span></div>
            <div class="item" onclick="selectPack(this, 'Monthly Member', 650)"><span>Monthly Member</span><span class="price">৳ 650</span></div>
            <div class="item" onclick="selectPack(this, '40 Robux', 50)"><span>40 Robux</span><span class="price">৳ 50</span></div>
            <div class="item" onclick="selectPack(this, '400 Robux', 500)"><span>400 Robux</span><span class="price">৳ 500</span></div>
        </div>
    </div>

    <div class="box summary">
        <h2>3. Order Summary</h2>
        <p>Selected: <span id="sum-pack">-</span></p>
        <p>ID/Username: <span id="sum-id">-</span></p>
        <div class="total">Total: ৳ <span id="sum-total">0</span></div>

        <h2 style="margin-top: 20px;">4. Select Payment Method</h2>
        <div class="pay-method">
            <div class="method active"><div class="logo-crop"><img src="bikashlogo.png" alt="bkash"></div></div>
            <div class="method" style="opacity:0.4;"><span style="position:absolute; top:-5px; font-size:8px; background:#444; padding:2px 5px; border-radius:3px;">COMING SOON</span><img src="https://download.logo.wine/logo/Nagad/Nagad-Logo.wine.png" alt="nagad" style="width:70px;"></div>
        </div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div class="bkash-header"><div class="header-crop"><img src="bikashlogo.png" alt="bkash"></div></div>
        <div class="bkash-body">
            <p style="text-align: center; font-weight: bold; margin-bottom: 15px;">ট্রানজেকশন আইডি দিন</p>
            <input type="text" class="trx-input" id="trx-input" placeholder="TrxID এখানে দিন">
            <div class="instr">● "Send Money" এ ক্লিক করুন।</div>
            <div class="instr">● নম্বরঃ <b>01779772201</b> <button class="copy-btn" onclick="copyNum()">COPY</button></div>
            <div class="instr">● টাকার পরিমাণঃ ৳ <b id="pay-amount">0</b></div>
            <div class="instr">● পেমেন্ট হয়ে গেলে ট্রানজেকশন আইডি উপরের বক্সে দিন।</div>
        </div>
        <div class="delivery-notice">⚠️ পেমেন্ট সম্পন্ন হওয়ার ৩০-৪০ মিনিটের মধ্যে প্যাক চলে যাবে।</div>
        <button class="verify-btn" onclick="verifyRealOrder()">VERIFY</button>
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width: 100%; background: #f5f5f5; border: none; padding: 12px; cursor: pointer; color: #666; font-weight: bold;">CANCEL</button>
    </div>
</div>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";
    let notifyInterval;

    const fakeFF = ["ID 4521***", "ID 9982***", "ID 1002***", "ID 7745***"];
    const fakeRobux = ["user rafi***", "user sakib***", "user king***", "user topup_pro***"];

    function startFakeNotifications() {
        notifyInterval = setInterval(() => {
            const notify = document.getElementById('notify-box');
            notify.classList.remove('real-order-active');
            notify.style.opacity = '0';
            setTimeout(() => {
                const isRobux = Math.random() > 0.5;
                if(isRobux) {
                    const user = fakeRobux[Math.floor(Math.random() * fakeRobux.length)];
                    notify.innerText = `Success! ${user} got 40 Robux.`;
                } else {
                    const id = fakeFF[Math.floor(Math.random() * fakeFF.length)];
                    notify.innerText = `${id} just bought Weekly!`;
                }
                notify.style.opacity = '1';
            }, 500);
        }, 10000);
    }

    function verifyRealOrder() {
        const trx = document.getElementById('trx-input').value;
        const uid = document.getElementById('uid-input').value;
        if(trx.length < 5) { alert("ভুল ট্রানজেকশন আইডি!"); return; }

        clearInterval(notifyInterval);
        const notify = document.getElementById('notify-box');
        notify.classList.add('real-order-active');
        notify.innerText = `✅ ORDER DONE! ${uid} just purchased ${selectedPackName}.`;

        alert("অর্ডার সফল! ৩০-৪০ মিনিটের মধ্যে ডেলিভারি পাবেন।");
        document.getElementById('bkash-modal').style.display = 'none';

        setTimeout(() => { startFakeNotifications(); }, 15000); // ১৫ সেকেন্ড পর আবার ফেক শুরু
    }

    startFakeNotifications();

    function selectPack(el, name, price) {
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price;
        selectedPackName = name;
        document.getElementById('sum-pack').innerText = name;
        document.getElementById('sum-total').innerText = price;
        document.getElementById('pay-amount').innerText = price;
    }

    function updateID() { document.getElementById('sum-id').innerText = document.getElementById('uid-input').value || "-"; }
    function openPayment() { if(!document.getElementById('uid-input').value || selectedPrice === 0) { alert("তথ্য দিন!"); return; } document.getElementById('bkash-modal').style.display = 'flex'; }
    function copyNum() { navigator.clipboard.writeText("01779772201"); alert("Number Copied!"); }
</script>

</body>
</html>
