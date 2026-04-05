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
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; }
        body { background: var(--dark-bg); color: #fff; padding-bottom: 50px; }

        header { background: #000; padding: 25px; text-align: center; border-bottom: 2px solid var(--neon-yellow); box-shadow: 0 0 20px rgba(204, 255, 0, 0.2); }
        .logo { font-family: 'Orbitron', sans-serif; font-size: 35px; color: var(--neon-yellow); letter-spacing: 5px; }

        .container { max-width: 600px; margin: 20px auto; padding: 15px; }

        .box { background: var(--card-bg); border: 1px solid #222; padding: 20px; border-radius: 12px; margin-bottom: 20px; }
        h2 { font-size: 18px; margin-bottom: 15px; color: var(--neon-yellow); text-transform: uppercase; border-left: 4px solid var(--neon-yellow); padding-left: 10px; }

        input[type="text"] { width: 100%; padding: 15px; background: #000; border: 1px solid #333; color: var(--neon-yellow); border-radius: 8px; font-size: 18px; outline: none; text-align: center; font-weight: bold; }

        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .item { background: #000; border: 1px solid #222; padding: 15px; border-radius: 8px; cursor: pointer; text-align: center; transition: 0.3s; }
        .item:hover { border-color: var(--neon-yellow); }
        .item.active { border-color: var(--neon-yellow); background: rgba(204, 255, 0, 0.05); }
        .item .price { display: block; color: var(--neon-yellow); font-weight: bold; font-size: 20px; }

        .summary p { display: flex; justify-content: space-between; margin-bottom: 5px; color: #aaa; }
        .summary .total { color: var(--neon-yellow); font-size: 22px; font-weight: bold; border-top: 1px solid #333; padding-top: 10px; margin-top: 10px; }

        .pay-method { display: flex; gap: 15px; margin-top: 15px; }
        .method { flex: 1; padding: 15px; border: 1px solid #222; border-radius: 10px; text-align: center; cursor: pointer; position: relative; background: #000; display: flex; align-items: center; justify-content: center; min-height: 80px; }
        
        /* Updated to match your filename */
        .method img { width: 85px; height: auto; object-fit: contain; }
        .method.active { border-color: var(--bkash-color); background: rgba(209, 32, 83, 0.05); }
        .method.disabled { opacity: 0.4; cursor: not-allowed; }
        .badge-soon { position: absolute; top: -10px; right: -5px; background: #444; color: #fff; font-size: 10px; padding: 2px 8px; border-radius: 4px; font-weight: bold; }

        /* bKash Modal */
        #bkash-modal {
            display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.9); z-index: 9999; justify-content: center; align-items: center;
        }
        .bkash-content { background: #fff; width: 90%; max-width: 400px; border-radius: 10px; overflow: hidden; color: #000; }
        .bkash-header { background: #fff; padding: 15px; text-align: center; border-bottom: 1px solid #eee; }
        .bkash-body { background: var(--bkash-color); color: #fff; padding: 20px; text-align: left; }
        .instr { font-size: 13px; margin-bottom: 10px; border-bottom: 1px solid rgba(255,255,255,0.2); padding-bottom: 8px; }
        .instr b { color: var(--neon-yellow); }
        .trx-input { width: 100%; padding: 12px; margin: 10px 0; border-radius: 5px; border: none; font-size: 16px; text-align: center; font-weight: bold; }
        
        /* Styled Red Verify Button */
        .verify-btn { 
            width: 90%; margin: 0 auto 20px auto; display: block;
            padding: 15px; background: #d00000; color: #fff; 
            border: none; font-weight: bold; cursor: pointer; 
            font-size: 18px; border-radius: 8px; 
            transition: 0.3s;
            text-transform: uppercase;
        }
        .verify-btn:hover { background: #ff0000; box-shadow: 0 0 15px rgba(255,0,0,0.5); }

        .btn-buy { width: 100%; padding: 18px; background: var(--neon-yellow); color: #000; border: none; border-radius: 8px; font-weight: bold; font-size: 20px; cursor: pointer; margin-top: 10px; }
    </style>
</head>
<body>

<header>
    <div class="logo">CHOR BAZER</div>
</header>

<div class="container">
    <div class="box">
        <h2>1. Player UID</h2>
        <input type="text" id="uid-input" placeholder="Enter Player UID" oninput="updateID()">
    </div>

    <div class="box">
        <h2>2. Select Diamonds</h2>
        <div class="grid">
            <div class="item" onclick="selectPack(this, '115 Diamonds', 85)">
                <span>115 Diamonds</span>
                <span class="price">৳ 85</span>
            </div>
            <div class="item" onclick="selectPack(this, '240 Diamonds', 165)">
                <span>240 Diamonds</span>
                <span class="price">৳ 165</span>
            </div>
            <div class="item" onclick="selectPack(this, 'Weekly Member', 160)">
                <span>Weekly Member</span>
                <span class="price">৳ 160</span>
            </div>
            <div class="item" onclick="selectPack(this, 'Monthly Member', 780)">
                <span>Monthly Member</span>
                <span class="price">৳ 780</span>
            </div>
        </div>
    </div>

    <div class="box summary">
        <h2>3. Order Summary</h2>
        <p>Selected: <span id="sum-pack">-</span></p>
        <p>Player ID: <span id="sum-id">-</span></p>
        <div class="total">Total: ৳ <span id="sum-total">0</span></div>

        <h2 style="margin-top: 20px;">4. Select Payment Method</h2>
        <div class="pay-method">
            <div class="method active">
                <img src="bikashlogo.png" alt="bkash">
            </div>
            <div class="method disabled">
                <span class="badge-soon">COMING SOON</span>
                <img src="https://download.logo.wine/logo/Nagad/Nagad-Logo.wine.png" alt="nagad">
            </div>
        </div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div class="bkash-header">
            <img src="bikashlogo.png" width="120">
        </div>
        <div class="bkash-body">
            <p style="text-align: center; font-weight: bold; margin-bottom: 15px;">ট্রানজেকশন আইডি দিন</p>
            <input type="text" class="trx-input" placeholder="TrxID এখানে দিন">
            <div class="instr">● "Send Money" এ ক্লিক করুন।</div>
            <div class="instr">● প্রাপক নম্বর হিসেবে এই নম্বরটি লিখুনঃ <b>01XXXXXXX69</b></div>
            <div class="instr">● টাকার পরিমাণঃ ৳ <b id="pay-amount">0</b></div>
            <div class="instr">● নিশ্চিত করতে এখন আপনার bKash মোবাইল মেনু পিন লিখুন।</div>
            <div class="instr">● পেমেন্ট হয়ে গেলে ট্রানজেকশন আইডি উপরের বক্সে দিন।</div>
        </div>
        <button class="verify-btn" onclick="verifyOrder()">VERIFY</button>
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width: 100%; background: #f0f0f0; border: none; padding: 12px; cursor: pointer; color: #555; font-weight: bold;">CANCEL</button>
    </div>
</div>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";

    function updateID() {
        const uid = document.getElementById('uid-input').value;
        document.getElementById('sum-id').innerText = uid ? uid : "-";
    }

    function selectPack(el, name, price) {
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price;
        selectedPackName = name;
        document.getElementById('sum-pack').innerText = name;
        document.getElementById('sum-total').innerText = price;
        document.getElementById('pay-amount').innerText = price;
    }

    function openPayment() {
        const uid = document.getElementById('uid-input').value;
        if(!uid || selectedPrice === 0) {
            alert("UID এবং প্যাক সিলেক্ট করুন!");
            return;
        }
        document.getElementById('bkash-modal').style.display = 'flex';
    }

    function verifyOrder() {
        const trx = document.querySelector('.trx-input').value;
        if(trx.length < 5) {
            alert("ভুল ট্রানজেকশন আইডি!");
        } else {
            alert("আপনার অর্ডারটি সফলভাবে জমা হয়েছে!");
            location.reload();
        }
    }
</script>

</body>
</html>
