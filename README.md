<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CHOR BAZAR | PREMIUM TOP UP</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500;700&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --purple-main: #6a0dad; /* রাজকীয় বেগুনি */
            --purple-light: #f5f3ff;
            --white: #ffffff;
            --text-dark: #1f2937;
            --bkash-color: #d12053;
            --border: #e5e7eb;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background: var(--white); color: var(--text-dark); overflow-x: hidden; width: 100%; }

        header { background: var(--purple-main); padding: 15px 0; text-align: center; border-bottom: 3px solid #4c1d95; position: sticky; top: 0; z-index: 100; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .logo { font-family: 'Poppins', sans-serif; font-size: clamp(1.2rem, 5vw, 1.8rem); color: var(--white); letter-spacing: 2px; font-weight: 700; }
        
        nav { display: flex; justify-content: center; gap: 10px; margin-top: 10px; }
        .nav-btn {
            background: rgba(255, 255, 255, 0.15); border: 1px solid rgba(255, 255, 255, 0.3);
            color: #fff; padding: 6px 15px; border-radius: 20px; font-size: 13px; cursor: pointer;
            transition: all 0.3s ease; font-weight: bold;
        }
        .nav-btn:hover { background: var(--white); color: var(--purple-main); transform: translateY(-2px); }

        .page { display: none; width: 95%; max-width: 480px; margin: 20px auto; animation: fadeIn 0.4s; }
        .page.active { display: block; }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }

        #notify-box { 
            background: var(--purple-light); border: 1px solid #ddd6fe; 
            padding: 12px; border-radius: 12px; margin-bottom: 20px; text-align: center; 
            font-weight: bold; color: var(--purple-main); font-size: 14px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
        }

        .box { background: var(--white); border: 1px solid var(--border); padding: 20px; border-radius: 16px; margin-bottom: 15px; box-shadow: 0 4px 12px rgba(0,0,0,0.03); }
        h2 { font-size: 15px; margin-bottom: 15px; color: var(--purple-main); text-transform: uppercase; border-left: 4px solid var(--purple-main); padding-left: 10px; font-family: 'Poppins', sans-serif; }

        input[type="text"] { width: 100%; padding: 14px; background: #f9fafb; border: 2px solid #e5e7eb; color: var(--text-dark); border-radius: 10px; text-align: center; font-weight: bold; outline: none; transition: 0.3s; }
        input[type="text"]:focus { border-color: var(--purple-main); }

        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
        .item { background: var(--white); border: 2px solid #f3f4f6; padding: 20px; border-radius: 14px; text-align: center; cursor: pointer; position: relative; transition: 0.3s; }
        .item:hover { border-color: #ddd6fe; background: var(--purple-light); }
        .item.active { border-color: var(--purple-main); background: var(--purple-light); box-shadow: 0 4px 8px rgba(106, 13, 173, 0.1); }
        .price { color: var(--purple-main); font-weight: bold; font-size: 20px; display: block; margin-top: 5px; }

        .btn-buy { width: 100%; padding: 16px; background: var(--purple-main); color: #fff; border: none; border-radius: 12px; font-weight: bold; cursor: pointer; margin-top: 15px; text-transform: uppercase; font-size: 16px; transition: 0.3s; }
        .btn-buy:hover { background: #4c1d95; box-shadow: 0 6px 15px rgba(106, 13, 173, 0.3); }

        /* Payment Modal */
        #bkash-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.6); z-index: 1000; justify-content: center; align-items: center; backdrop-filter: blur(5px); }
        .bkash-content { background: #fff; width: 92%; max-width: 360px; border-radius: 20px; overflow: hidden; color: #333; padding-bottom: 15px; box-shadow: 0 20px 40px rgba(0,0,0,0.2); }
        .bkash-header { padding: 15px; text-align: center; background: #f8f9fa; border-bottom: 1px solid #eee; }
        .bkash-header img { width: 90px; }
        .bkash-main-body { background: var(--bkash-color); color: #fff; padding: 15px; margin: 10px; border-radius: 15px; text-align: center; }
        .trx-input-box { width: 100%; padding: 12px; border-radius: 8px; border: 2px solid #eee; margin-bottom: 10px; text-align: center; font-weight: bold; color: #000; outline: none; font-size: 15px; }
        .verify-red-btn { width: 90%; margin: 10px auto 0; display: block; padding: 14px; background: #d00000; color: #fff; border: none; font-weight: bold; cursor: pointer; border-radius: 8px; font-size: 16px; }

        #success-popup { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); z-index: 2000; justify-content: center; align-items: center; }
        .success-card { background: var(--white); width: 85%; max-width: 340px; padding: 40px 20px; border-radius: 25px; text-align: center; border-bottom: 8px solid var(--purple-main); }

        footer { text-align: center; padding: 30px 10px; border-top: 1px solid #eee; font-size: 12px; background: #f9fafb; color: #6b7280; }
        .footer-glow { color: var(--purple-main); font-weight: bold; }
    </style>
</head>
<body onload="startOrderHistory()">

<header>
    <div class="logo">CHOR BAZAR</div>
    <nav>
        <button class="nav-btn" onclick="showPage('home')">Home</button>
        <button class="nav-btn" onclick="showPage('about')">About</button>
        <button class="nav-btn" onclick="showPage('contact')">Contact</button>
    </nav>
</header>

<div id="home" class="page active">
    <div id="notify-box">🚀 Waiting for new orders...</div>
    <div class="box">
        <h2>1. Player UID</h2>
        <input type="text" id="uid-input" placeholder="Enter Player UID here">
    </div>
    <div class="box">
        <h2>2. Select Pack</h2>
        <div class="grid">
            <div class="item" onclick="selectPack(this, 'Weekly Membership', 140)">
                <span style="font-weight: 700;">Weekly Pack</span>
                <span class="price">৳ 140</span>
            </div>
            <div class="item" onclick="selectPack(this, 'Monthly Membership', 650)">
                <span style="font-weight: 700;">Monthly Pack</span>
                <span class="price">৳ 650</span>
            </div>
        </div>
    </div>
    <div class="box">
        <div style="color:var(--purple-main); font-size:22px; font-weight:bold; text-align: center;">Total: ৳ <span id="sum-total">0</span></div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div class="bkash-header"><img src="https://www.logo.wine/a/logo/BKash/BKash-Logo.wine.svg" alt="bkash"></div>
        <div class="bkash-main-body">
            <h3 style="font-size: 14px; margin-bottom: 10px;">আপনার বিকাশ নম্বর ও TxID দিন</h3>
            <input type="text" class="trx-input-box" id="customer-phone" placeholder="নম্বরঃ 01XXXXXXXXX" maxlength="11">
            <input type="text" class="trx-input-box" id="trx-input" placeholder="ট্রানজেকশন আইডি দিন" maxlength="10">
            <p style="font-size: 11px; margin-top: 10px; text-align: left; border-top: 1px solid rgba(255,255,255,0.2); padding-top: 10px;">
                ● টাকা পাঠানঃ <b>01779772201</b> <button onclick="copyNum()" style="padding:2px 6px; font-size:10px; border-radius:4px; border:none; background:#fff; cursor:pointer;">Copy</button><br>
                ● টাকার পরিমাণঃ ৳ <b id="pay-amount">0</b>
            </p>
        </div>
        <button class="verify-red-btn" id="verify-btn" onclick="handleRealOrder()">VERIFY PAYMENT</button>
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width:100%; background:none; border:none; padding:12px; color:#999; cursor:pointer;">CANCEL</button>
    </div>
</div>

<div id="success-popup">
    <div class="success-card">
        <div style="font-size: 50px; color: var(--purple-main); margin-bottom: 10px;">✔</div>
        <h2 style="color:var(--purple-main); font-size: 24px;">অর্ডার সফল হয়েছে!</h2>
        <p style="margin:20px 0; color:#4b5563; font-size:15px; line-height:1.6;">
            আপনার পেমেন্ট ভেরিফাই করা হচ্ছে।<br>
            আগামী <b>৩০-৪০ মিনিটের</b> মধ্যে<br>
            আইডিতে ডায়মন্ড চলে যাবে।
        </p>
        <button onclick="closeSuccess()" style="background:var(--purple-main); color:#fff; border:none; padding:12px 40px; border-radius:10px; font-weight:bold; cursor:pointer; width: 100%;">ঠিক আছে</button>
    </div>
</div>

<footer>
    © 2026 <span class="footer-glow">CHOR BAZAR</span> | PREMIUM GAMING DESTINATION
</footer>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";
    let notifyInterval;

    const SHEETDB_API_URL = "https://sheetdb.io/api/v1/6oyklgob3u2fr"; 

    function showPage(pageId) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.getElementById(pageId).classList.add('active');
    }

    function selectPack(el, name, price) {
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price; selectedPackName = name;
        document.getElementById('sum-total').innerText = price;
        document.getElementById('pay-amount').innerText = price;
    }

    function openPayment() {
        let uid = document.getElementById('uid-input').value.trim();
        if(!selectedPrice || !uid) return alert("UID ও প্যাক সিলেক্ট করুন!");
        document.getElementById('bkash-modal').style.display = 'flex';
    }

    function handleRealOrder() {
        const trx = document.getElementById('trx-input').value.trim();
        const phone = document.getElementById('customer-phone').value.trim();
        const uid = document.getElementById('uid-input').value.trim();
        const verifyBtn = document.getElementById('verify-btn');
        
        if (phone.length < 11 || trx.length < 10) return alert("সঠিক ফোন নম্বর ও ১০ অক্ষরের TxID দিন!");
        
        verifyBtn.innerText = "VERIFYING...";
        verifyBtn.disabled = true;

        let orderData = {
            "data": [
                {
                    "Time": new Date().toLocaleString("en-US", {timeZone: "Asia/Dhaka"}),
                    "Player UID": uid,
                    "Selected Pack": selectedPackName,
                    "bKash Number": phone,
                    "TxID": trx.toUpperCase(),
                    "Status": "Pending"
                }
            ]
        };

        fetch(SHEETDB_API_URL, {
            method: 'POST',
            headers: { 'Accept': 'application/json', 'Content-Type': 'application/json' },
            body: JSON.stringify(orderData)
        })
        .then(response => response.json())
        .then(data => {
            verifyBtn.innerText = "VERIFY PAYMENT";
            verifyBtn.disabled = false;
            if(data.created === 1) {
                document.getElementById('bkash-modal').style.display = 'none';
                document.getElementById('success-popup').style.display = 'flex';
                document.getElementById('trx-input').value = "";
                document.getElementById('customer-phone').value = "";
                document.getElementById('uid-input').value = "";
                const notify = document.getElementById('notify-box');
                notify.innerHTML = `✅ সাকসেস! ${uid} এর জন্য ${selectedPackName} অর্ডার হয়েছে।`;
            }
        })
        .catch(error => {
            verifyBtn.disabled = false;
            alert("Error! Please check internet connection.");
        });
    }

    function closeSuccess() { document.getElementById('success-popup').style.display = 'none'; }
    function copyNum() { navigator.clipboard.writeText("01779772201"); alert("Number Copied!"); }

    function startOrderHistory() {
        const fakes = ["UID 5021****", "UID 8842****", "UID 1125****", "UID 7745****"];
        notifyInterval = setInterval(() => {
            const notify = document.getElementById('notify-box');
            if(notify) {
                notify.style.opacity = '0';
                setTimeout(() => {
                    notify.innerText = `✅ ${fakes[Math.floor(Math.random() * fakes.length)]} bought ${Math.random()>0.5?'Weekly':'Monthly'}!`;
                    notify.style.opacity = '1';
                }, 500);
            }
        }, 12000);
    }
</script>
</body>
</html>
