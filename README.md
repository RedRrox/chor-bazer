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
            --gold: #ffd700;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background: var(--dark-bg); color: #fff; padding-bottom: 50px; }

        header { background: #000; padding: 20px; text-align: center; border-bottom: 2px solid var(--neon-yellow); }
        .logo { font-family: 'Orbitron', sans-serif; font-size: 30px; color: var(--neon-yellow); letter-spacing: 5px; }

        .container { max-width: 500px; margin: 15px auto; padding: 10px; }

        #notify-box { 
            background: rgba(204, 255, 0, 0.05); 
            border: 1px dashed var(--neon-yellow); 
            padding: 10px; border-radius: 8px; margin-bottom: 15px; 
            text-align: center; font-weight: bold; color: var(--neon-yellow); font-size: 13px;
        }

        .box { background: var(--card-bg); border: 1px solid #222; padding: 15px; border-radius: 12px; margin-bottom: 15px; }
        h2 { font-size: 16px; margin-bottom: 12px; color: var(--neon-yellow); text-transform: uppercase; border-left: 4px solid var(--neon-yellow); padding-left: 10px; }

        input[type="text"] { width: 100%; padding: 12px; background: #000; border: 1px solid #333; color: var(--neon-yellow); border-radius: 8px; font-size: 16px; outline: none; text-align: center; font-weight: bold; }

        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .item { background: #000; border: 1px solid #222; padding: 15px; border-radius: 10px; cursor: pointer; text-align: center; position: relative; overflow: hidden; }
        .item.active { border-color: var(--neon-yellow); background: rgba(204, 255, 0, 0.08); }
        .item .price { color: var(--neon-yellow); font-weight: bold; font-size: 20px; display: block; }

        .special-badge { position: absolute; top: 0; left: 0; background: #ff0000; color: #fff; font-size: 9px; font-weight: 800; padding: 2px 8px; border-radius: 0 0 10px 0; }
        .premium-card { grid-column: span 2; border: 2px solid #ff0000 !important; cursor: not-allowed; opacity: 0.8; }
        .stock-tag { background: #ff4444; color: #fff; font-size: 9px; padding: 2px 6px; border-radius: 4px; margin-top: 5px; display: inline-block; }

        .summary p { display: flex; justify-content: space-between; margin-bottom: 6px; color: #aaa; font-size: 14px; }
        .total { color: var(--neon-yellow); font-size: 22px; font-weight: bold; border-top: 1px solid #333; padding-top: 8px; margin-top: 8px; }
        .btn-buy { width: 100%; padding: 15px; background: var(--neon-yellow); color: #000; border: none; border-radius: 8px; font-weight: bold; font-size: 18px; cursor: pointer; margin-top: 10px; }

        /* --- Compact bKash Modal --- */
        #bkash-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.9); z-index: 9999; justify-content: center; align-items: center; }
        .bkash-content { background: #fff; width: 90%; max-width: 380px; border-radius: 10px; overflow: hidden; color: #333; padding-bottom: 15px; box-shadow: 0 10px 25px rgba(0,0,0,0.5); }
        
        .bkash-header { padding: 12px; text-align: center; border-bottom: 1px solid #f1f1f1; }
        .bkash-header img { width: 85px; }

        .bkash-main-body { background: #d12053; color: #fff; padding: 15px; margin: 0 12px; border-radius: 8px; text-align: center; }
        .bkash-main-body h3 { font-size: 15px; margin-bottom: 12px; font-weight: 600; }
        .trx-input-box { width: 100%; padding: 10px; border-radius: 5px; border: none; margin-bottom: 15px; font-size: 16px; text-align: center; color: #000; outline: none; }

        .bkash-steps { text-align: left; font-size: 12px; line-height: 1.6; border-top: 1px solid rgba(255,255,255,0.2); padding-top: 12px; }
        .bkash-steps p { margin-bottom: 8px; position: relative; padding-left: 12px; }
        .bkash-steps p::before { content: "•"; position: absolute; left: 0; color: #fff; }

        .copy-btn-bkash { background: #fff; color: #000; border: none; padding: 2px 6px; border-radius: 4px; font-size: 10px; cursor: pointer; font-weight: bold; margin-left: 5px; }
        
        .verify-red-btn { width: 90%; margin: 12px auto 0; display: block; padding: 14px; background: #d00000; color: #fff; border: none; font-weight: bold; cursor: pointer; font-size: 15px; border-radius: 5px; text-transform: uppercase; }
    </style>
</head>
<body>

<header><div class="logo">CHOR BAZER</div></header>

<div class="container">
    <div id="notify-box">🚀 Waiting for new orders...</div>

    <div class="box">
        <h2>1. Player UID / Username</h2>
        <input type="text" id="uid-input" placeholder="Enter ID here" oninput="updateID()">
    </div>

    <div class="box">
        <h2>2. Select Pack</h2>
        <div class="grid">
            <div class="item premium-card">
                <div class="special-badge">LIMITED TIME</div>
                <span style="color:var(--gold); font-weight:800;">💎 2x Monthly Member 💎</span>
                <span class="price">৳ 1</span>
                <span class="stock-tag">OUT OF STOCK</span>
            </div>
            <div class="item" onclick="selectPack(this, 'Weekly Member', 140)"><span>Weekly Member</span><span class="price">৳ 140</span></div>
            <div class="item" onclick="selectPack(this, 'Monthly Member', 650)"><span>Monthly Member</span><span class="price">৳ 650</span></div>
        </div>
    </div>

    <div class="box summary">
        <h2>3. Order Summary</h2>
        <p>Selected: <span id="sum-pack">-</span></p>
        <p>ID/Username: <span id="sum-id">-</span></p>
        <div class="total">Total: ৳ <span id="sum-total">0</span></div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div class="bkash-header"><img src="bikashlogo.png" alt="bkash"></div>
        
        <div class="bkash-main-body">
            <h3>ট্রান্সজেকশন আইডি দিন</h3>
            <input type="text" class="trx-input-box" id="trx-input" placeholder="">
            
            <div class="bkash-steps">
                <p>*247# ডায়াল করে আপনার bKash মোবাইল মেনুতে যান অথবা bKash অ্যাপে যান।</p>
                <p><b>"Send Money"</b> -এ ক্লিক করুন।</p>
                <p>প্রাপক নম্বর হিসেবে এই নম্বরটি লিখুনঃ <b>01779772201</b> <button class="copy-btn-bkash" onclick="copyNum()">Copy</button></p>
                <p>টাকার পরিমাণঃ <b id="pay-amount">0</b></p>
                <p>নিশ্চিত করতে এখন আপনার bKash মোবাইল মেনু পিন লিখুন।</p>
                <p>সবকিছু ঠিক থাকলে, আপনি bKash থেকে একটি নিশ্চিতকরণ বার্তা পাবেন।</p>
                <p>এখন উপরের বক্সে আপনার <b>Transaction ID</b> দিন এবং নিচের <b>VERIFY</b> বাটনে ক্লিক করুন।</p>
            </div>
        </div>

        <button class="verify-red-btn" onclick="verifyRealOrder()">VERIFY</button>
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width: 100%; background: none; border: none; padding: 10px; cursor: pointer; color: #999; font-size: 11px;">CANCEL</button>
    </div>
</div>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";
    let notifyInterval;
    let lastMsgIndex = -1;

    const fakeOrders = ["ID 4521***", "user rafi***", "UID 9982***", "user topup_pro***", "ID 1025***", "UID 7741***", "player_king***"];
    function startFake() {
        notifyInterval = setInterval(() => {
            const notify = document.getElementById('notify-box');
            notify.style.opacity = '0';
            setTimeout(() => {
                let idx; do { idx = Math.floor(Math.random() * fakeOrders.length); } while (idx === lastMsgIndex);
                lastMsgIndex = idx;
                notify.innerText = `✅ ${fakeOrders[idx]} just bought ${Math.random() > 0.5 ? 'Weekly' : 'Monthly'}!`;
                notify.style.opacity = '1';
            }, 500);
        }, 10000);
    }

    function verifyRealOrder() {
        if(document.getElementById('trx-input').value.trim().length < 5) return alert("ভুল ট্রানজেকশন আইডি!");
        clearInterval(notifyInterval);
        document.getElementById('notify-box').innerHTML = `<span style="color:#00ff88">✅ ORDER DONE! ${document.getElementById('uid-input').value} just purchased ${selectedPackName}.</span>`;
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
    function openPayment() { if(!selectedPrice) return alert("প্যাক সিলেক্ট করুন!"); document.getElementById('bkash-modal').style.display = 'flex'; }
    function copyNum() { navigator.clipboard.writeText("01779772201"); alert("নম্বর কপি হয়েছে!"); }

    startFake();
</script>

</body>
</html>
