<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CHOR BAZER | PREMIUM GAME TOP UP</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;800&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <style>
        /* --- Core Variables & Reset --- */
        :root {
            --neon-green: #00ff88;
            --neon-yellow: #ccff00;
            --dark-bg: #030303;
            --card-bg: rgba(20, 20, 20, 0.9);
            --border-color: rgba(255, 255, 255, 0.08);
            --bkash-color: #d12053;
            --gold: #ffd700;
            --text-main: #f0f0f0;
            --text-dim: #999;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; -webkit-font-smoothing: antialiased; }
        body { background: var(--dark-bg); color: var(--text-main); padding-bottom: 20px; overflow-x: hidden; }

        /* --- Custom Scrollbar --- */
        ::-webkit-scrollbar { width: 5px; }
        ::-webkit-scrollbar-track { background: #000; }
        ::-webkit-scrollbar-thumb { background: var(--neon-yellow); border-radius: 5px; }

        /* --- Modern Header --- */
        header { 
            background: #000; 
            padding: 25px 0; 
            text-align: center; 
            border-bottom: 1px solid var(--border-color); 
            position: sticky; top: 0; z-index: 999;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }
        .logo { 
            font-family: 'Orbitron', sans-serif; 
            font-size: 30px; 
            color: var(--neon-yellow); 
            letter-spacing: 4px; 
            text-shadow: 0 0 10px rgba(204, 255, 0, 0.4);
            animation: pulse 3s infinite;
        }

        /* --- Premium Container --- */
        .container { max-width: 500px; margin: 15px auto; padding: 10px; }

        /* --- Glassmorphic Notification --- */
        #notify-box { 
            background: rgba(255, 255, 255, 0.03); 
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.06); 
            padding: 12px; border-radius: 8px; margin-bottom: 15px; 
            text-align: center; font-weight: bold; color: var(--neon-green); font-size: 13px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }

        /* --- Modern Boxes --- */
        .box { 
            background: var(--card-bg); 
            border: 1px solid var(--border-color); 
            padding: 18px; border-radius: 12px; margin-bottom: 15px; 
            box-shadow: 0 4px 15px rgba(0,0,0,0.15);
        }
        h2 { 
            font-size: 15px; 
            margin-bottom: 15px; 
            color: var(--neon-yellow); 
            text-transform: uppercase; 
            border-left: 3px solid var(--neon-yellow); 
            padding-left: 10px;
            letter-spacing: 1.5px;
        }

        /* --- Premium Input --- */
        input[type="text"] { 
            width: 100%; 
            padding: 14px; 
            background: rgba(0,0,0,0.6); 
            border: 1px solid #333; 
            color: var(--neon-yellow); 
            border-radius: 8px; 
            font-size: 16px; 
            outline: none; 
            text-align: center; 
            font-weight: bold; 
            transition: 0.2s;
        }
        input[type="text"]:focus { border-color: var(--neon-yellow); box-shadow: 0 0 10px rgba(204, 255, 0, 0.15); }

        /* --- Sleek Grid --- */
        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
        
        .item { 
            background: rgba(0,0,0,0.5); 
            border: 1px solid var(--border-color); 
            padding: 18px; border-radius: 10px; 
            cursor: pointer; text-align: center; 
            position: relative; overflow: hidden; 
            transition: all 0.2s ease-in-out;
        }
        .item:hover { border-color: rgba(255,255,255,0.3); transform: translateY(-2px); }
        
        .item.active { 
            border-color: var(--neon-green); 
            background: rgba(0, 255, 136, 0.08); 
            box-shadow: 0 0 15px rgba(0, 255, 136, 0.1);
        }
        .item span { font-size: 13px; color: var(--text-dim); }
        .item .price { color: var(--neon-green); font-weight: bold; font-size: 20px; display: block; margin-top: 5px; }

        /* Premium Bage (Redesign) */
        .special-badge { 
            position: absolute; top: 0; left: 0; 
            background: #ff4444; 
            color: #fff; font-size: 9px; font-weight: 800; 
            padding: 2px 10px; border-radius: 0 0 10px 0; 
        }
        .premium-card { 
            grid-column: span 2; 
            border: 2px solid #ff4444 !important; 
            cursor: not-allowed; opacity: 0.8; 
            box-shadow: 0 0 15px rgba(255, 68, 68, 0.1);
        }
        .premium-card span { color: #fcc !important; }
        .stock-tag { background: #ff4444; color: #fff; font-size: 9px; padding: 2px 6px; border-radius: 4px; margin-top: 5px; display: inline-block; }

        /* --- Sleek Summary --- */
        .summary p { display: flex; justify-content: space-between; margin-bottom: 8px; color: var(--text-dim); font-size: 13px; }
        .total { 
            color: var(--neon-green); font-size: 22px; font-weight: bold; 
            border-top: 1px solid #222; padding-top: 10px; margin-top: 10px; 
        }
        
        /* Premium Buy Button */
        .btn-buy { 
            width: 100%; padding: 16px; 
            background: var(--neon-yellow); color: #000; 
            border: none; border-radius: 8px; 
            font-weight: bold; font-size: 17px; cursor: pointer; 
            margin-top: 10px; text-transform: uppercase; letter-spacing: 1px;
            transition: all 0.2s ease-in-out;
            box-shadow: 0 4px 10px rgba(204, 255, 0, 0.1);
        }
        .btn-buy:hover { background: #d4ff00; transform: translateY(-2px); box-shadow: 0 6px 15px rgba(204, 255, 0, 0.2); }

        /* --- Professional Footer (Requested) --- */
        footer { 
            text-align: center; 
            padding: 30px 15px; 
            margin-top: 30px; 
            border-top: 1px solid var(--border-color); 
            font-size: 11px; 
            color: #444; 
            background: #000;
            letter-spacing: 1px;
        }
        footer b { color: var(--text-dim); }

        /* --- Professional bKash Modal --- */
        #bkash-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.95); z-index: 9999; justify-content: center; align-items: center; }
        .bkash-content { background: #fff; width: 90%; max-width: 380px; border-radius: 12px; overflow: hidden; color: #333; padding-bottom: 15px; box-shadow: 0 10px 30px rgba(0,0,0,0.5); border: 1px solid rgba(255,255,255,0.05); }
        
        .bkash-header { padding: 12px; text-align: center; border-bottom: 1px solid #f1f1f1; background: rgba(255,255,255,0.8); }
        .bkash-header img { width: 85px; }

        .bkash-main-body { background: #d12053; color: #fff; padding: 18px; margin: 0 12px; border-radius: 8px; text-align: center; }
        .bkash-main-body h3 { font-size: 15px; margin-bottom: 12px; font-weight: 600; }
        
        /* TRX Box Cleaned */
        .trx-input-box { 
            width: 100%; padding: 10px; border-radius: 5px; border: none; 
            margin-bottom: 15px; font-size: 16px; text-align: center; 
            color: #000; outline: none; background: #fff;
        }

        .bkash-steps { text-align: left; font-size: 12px; line-height: 1.6; border-top: 1px solid rgba(255,255,255,0.2); padding-top: 12px; }
        .bkash-steps p { margin-bottom: 8px; position: relative; padding-left: 12px; }
        .bkash-steps p::before { content: "•"; position: absolute; left: 0; color: #fff; }

        .copy-btn-bkash { background: #fff; color: #000; border: none; padding: 2px 6px; border-radius: 4px; font-size: 10px; cursor: pointer; font-weight: bold; margin-left: 5px; }
        
        .verify-red-btn { width: 90%; margin: 12px auto 0; display: block; padding: 14px; background: #d00000; color: #fff; border: none; font-weight: bold; cursor: pointer; font-size: 15px; border-radius: 5px; text-transform: uppercase; letter-spacing: 1px; }
        
        /* Keyframes */
        @keyframes pulse {
            0% { transform: scale(1); opacity: 1; text-shadow: 0 0 10px rgba(204, 255, 0, 0.4); }
            50% { transform: scale(1.02); opacity: 0.9; text-shadow: 0 0 20px rgba(204, 255, 0, 0.6); }
            100% { transform: scale(1); opacity: 1; text-shadow: 0 0 10px rgba(204, 255, 0, 0.4); }
        }
    </style>
</head>
<body>

<header><div class="logo">CHOR BAZER</div></header>

<div class="container">
    <div id="notify-box">🚀 Waiting for new orders...</div>

    <div class="box">
        <h2>1. Player UID</h2>
        <input type="text" id="uid-input" placeholder="Enter Player UID here" oninput="updateID()">
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
        <p>Selected Pack: <span id="sum-pack">-</span></p>
        <p>Player UID: <span id="sum-id">-</span></p>
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
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width: 100%; background: none; border: none; padding: 10px; cursor: pointer; color: #999; font-size: 10px;">CANCEL</button>
    </div>
</div>

<footer>
    © 2026 <b>CHOR BAZER</b> | POWERED BY <b>RRX STUDIOS</b>
</footer>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";
    let notifyInterval;
    let lastMsgIndex = -1;

    // Fake & Real Order History Logic
    const fakeFF = ["UID 4521***", "UID 9982***", "UID 1002***", "UID 7745***", "UID 1025***"];
    function startFake() {
        notifyInterval = setInterval(() => {
            const notify = document.getElementById('notify-box');
            notify.style.opacity = '0';
            setTimeout(() => {
                let idx; do { idx = Math.floor(Math.random() * fakeFF.length); } while (idx === lastMsgIndex);
                lastMsgIndex = idx;
                const packType = Math.random() > 0.5 ? 'Weekly' : 'Monthly';
                notify.innerText = `✅ ${fakeFF[idx]} just bought ${packType}!`;
                notify.style.color = "var(--neon-green)";
                notify.style.opacity = '1';
            }, 500);
        }, 8000);
    }

    function verifyRealOrder() {
        const trxInput = document.getElementById('trx-input');
        if(trxInput.value.trim().length < 5) return alert("ভুল ট্রানজেকশন আইডি!");
        clearInterval(notifyInterval);
        const notify = document.getElementById('notify-box');
        notify.innerHTML = `<span style="color:var(--neon-green)">✅ ORDER DONE! ${document.getElementById('uid-input').value} just purchased ${selectedPackName}.</span>`;
        alert("অর্ডার সফল! ৩০-৪০ মিনিটের মধ্যে ডেলিভারি পাবেন।");
        document.getElementById('bkash-modal').style.display = 'none';
        setTimeout(startFake, 15000);
    }

    // Pack Selection
    function selectPack(el, name, price) {
        if(el.classList.contains('premium-card')) return;
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price; selectedPackName = name;
        document.getElementById('sum-pack').innerText = name;
        document.getElementById('sum-total').innerText = price;
        document.getElementById('pay-amount').innerText = price;
    }

    // Summary Update
    function updateID() { document.getElementById('sum-id').innerText = document.getElementById('uid-input').value || "-"; }
    
    // Modal Open
    function openPayment() { 
        if(!selectedPrice) return alert("প্যাক সিলেক্ট করুন!"); 
        document.getElementById('bkash-modal').style.display = 'flex'; 
    }
    
    // Copy Function
    function copyNum() { 
        navigator.clipboard.writeText("01779772201"); 
        alert("নম্বর কপি হয়েছে!"); 
    }

    // Start
    startFake();
</script>

</body>
</html>
