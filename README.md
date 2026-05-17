<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>CHOR BAZAR | PREMIUM TOP UP</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@500;700;800&family=Rajdhani:wght@500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --purple-main: #6a0dad; 
            --purple-light: #f5f3ff;
            --white: #ffffff;
            --text-dark: #1f2937;
            --bkash-color: #d12053;
            --nagad-color: #f26522;
            --border: #e5e7eb;
            --whatsapp-color: #25d366;
            --telegram-color: #0088cc;
            --alert-bg: #fff7ed;
            --alert-border: #ffedd5;
            --alert-text: #c2410c;
            --success-green: #15803d;
            --blue-notice-bg: #e0f2fe; 
            --blue-notice-border: #0284c7; 
            --blue-notice-text: #0369a1; 
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Rajdhani', sans-serif; -webkit-tap-highlight-color: transparent; }
        body { background: var(--white); color: var(--text-dark); overflow-x: hidden; width: 100%; }

        @keyframes slidePageIn {
            from { opacity: 0; transform: translateY(25px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .top-notice-bar {
            background: var(--blue-notice-bg);
            border-bottom: 2px solid var(--blue-notice-border);
            color: var(--blue-notice-text);
            padding: 12px 40px 12px 15px;
            text-align: center;
            font-family: 'Poppins', sans-serif;
            font-size: 14px;
            font-weight: bold;
            line-height: 1.5;
            position: relative;
            width: 100%;
            display: block;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            z-index: 1001;
        }

        .close-notice-btn {
            position: absolute;
            right: 15px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 22px;
            cursor: pointer;
            color: var(--blue-notice-text);
            user-select: none;
        }

        header { background: var(--purple-main); padding: 15px 0; text-align: center; border-bottom: 3px solid #4c1d95; position: sticky; top: 0; z-index: 1000; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .logo { font-family: 'Poppins', sans-serif; font-size: clamp(1.2rem, 5vw, 1.8rem); color: var(--white); letter-spacing: 2px; font-weight: 700; cursor: pointer; }
        
        nav { display: flex; justify-content: center; gap: 10px; margin-top: 10px; }
        .nav-btn {
            background: rgba(255, 255, 255, 0.15); border: 1px solid rgba(255, 255, 255, 0.3);
            color: #fff; padding: 6px 15px; border-radius: 20px; font-size: 13px; cursor: pointer;
            transition: all 0.3s ease; font-weight: bold;
        }
        .nav-btn:hover { background: var(--white); color: var(--purple-main); transform: translateY(-2px); }

        .page { display: none; width: 95%; max-width: 480px; margin: 20px auto; animation: slidePageIn 0.4s ease-out; }
        .page.active { display: block; }

        #notify-box { 
            background: var(--purple-light); border: 1px solid #ddd6fe; 
            padding: 12px; border-radius: 12px; margin-bottom: 20px; text-align: center; 
            font-weight: bold; color: var(--purple-main); font-size: 14px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05); transition: opacity 0.5s ease;
        }

        .category-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-bottom: 20px;
        }

        .category-image-card {
            background: var(--white); border: 1px solid var(--border); border-radius: 16px;
            overflow: hidden; cursor: pointer; box-shadow: 0 4px 10px rgba(0,0,0,0.05);
            transition: transform 0.2s; text-align: center;
        }
        .category-image-card:hover { transform: scale(1.02); box-shadow: 0 6px 15px rgba(106, 13, 173, 0.15); }
        .category-image-card img { width: 100%; height: auto; display: block; object-fit: cover; }
        .category-card-title { padding: 10px 5px; font-size: 13px; font-weight: bold; color: var(--text-dark); font-family: 'Poppins', sans-serif; text-transform: uppercase; border-top: 1px solid #f3f4f6; }

        .box { background: var(--white); border: 1px solid var(--border); padding: 20px; border-radius: 16px; margin-bottom: 15px; box-shadow: 0 4px 12px rgba(0,0,0,0.03); }
        h2 { font-size: 15px; margin-bottom: 15px; color: var(--purple-main); text-transform: uppercase; border-left: 4px solid var(--purple-main); padding-left: 10px; font-family: 'Poppins', sans-serif; }

        .back-btn {
            background: none; border: 1px solid var(--purple-main); color: var(--purple-main);
            padding: 6px 15px; border-radius: 20px; font-size: 13px; cursor: pointer;
            font-weight: bold; margin-bottom: 15px; display: inline-flex; align-items: center; gap: 5px;
        }
        .back-btn:hover { background: var(--purple-main); color: white; }

        input[type="text"] { width: 100%; padding: 14px; background: #f9fafb; border: 2px solid #e5e7eb; color: var(--text-dark); border-radius: 10px; text-align: center; font-weight: bold; outline: none; transition: 0.3s; }
        input[type="text"]:focus { border-color: var(--purple-main); }

        .grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
        .item { background: var(--white); border: 2px solid #f3f4f6; padding: 15px 10px; border-radius: 14px; text-align: center; cursor: pointer; position: relative; transition: 0.3s; }
        .item:hover { border-color: #ddd6fe; background: var(--purple-light); }
        .item.active { border-color: var(--purple-main); background: var(--purple-light); box-shadow: 0 4px 8px rgba(106, 13, 173, 0.1); }
        .price { color: var(--purple-main); font-weight: bold; font-size: 18px; display: block; margin-top: 5px; }

        .btn-buy { width: 100%; padding: 16px; background: var(--purple-main); color: #fff; border: none; border-radius: 12px; font-weight: bold; cursor: pointer; margin-top: 15px; text-transform: uppercase; font-size: 16px; transition: 0.3s; }
        .btn-buy:hover { background: #4c1d95; box-shadow: 0 6px 15px rgba(106, 13, 173, 0.3); }

        /* পেমেন্ট গেটওয়ে সিলেকশন গ্রিড */
        .payment-method-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 10px;
        }
        .pay-method-card {
            border: 2px solid #e5e7eb;
            border-radius: 14px;
            padding: 12px;
            text-align: center;
            cursor: pointer;
            transition: 0.3s;
            background: #fafafa;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 65px;
        }
        .pay-method-card img {
            height: 35px;
            width: auto;
            object-fit: contain;
        }
        .pay-method-card.active {
            border-color: var(--purple-main);
            background: var(--purple-light);
        }
        /* নগদ লকড / সুন স্টাইল */
        .pay-method-card.disabled {
            opacity: 0.65;
            cursor: not-allowed;
            background: #f3f4f6;
            border-color: #e5e7eb;
        }
        .soon-badge {
            position: absolute;
            top: -8px;
            right: -5px;
            background: #ef4444;
            color: white;
            font-size: 10px;
            font-weight: bold;
            padding: 2px 7px;
            border-radius: 10px;
            font-family: 'Poppins', sans-serif;
            text-transform: uppercase;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
        }

        .rules-container { background: var(--alert-bg); border: 1px solid var(--alert-border); border-radius: 12px; padding: 15px; margin-top: 15px; }
        .rules-title { font-family: 'Poppins', sans-serif; font-weight: bold; color: var(--alert-text); font-size: 14px; margin-bottom: 10px; display: flex; align-items: center; gap: 5px; }
        .rules-list { font-size: 13px; color: #4a5568; line-height: 1.6; list-style: none; text-align: left; }
        .rules-list li { margin-bottom: 8px; position: relative; padding-left: 5px; }

        .about-text { font-size: 15px; line-height: 1.6; color: #4b5563; text-align: justify; margin-bottom: 15px; font-family: 'Poppins', sans-serif; }
        .support-badge { background: #10b981; color: white; display: inline-block; padding: 5px 12px; border-radius: 20px; font-weight: bold; font-size: 13px; margin-top: 10px; }
        
        .contact-btn { 
            display: flex; align-items: center; justify-content: center; gap: 10px;
            width: 100%; padding: 14px; margin-bottom: 12px; border: none; border-radius: 12px; 
            color: white; font-weight: bold; font-size: 16px; cursor: pointer; text-decoration: none;
            transition: transform 0.3s, box-shadow 0.3s; font-family: 'Poppins', sans-serif;
        }
        .contact-btn:hover { transform: translateY(-2px); }
        .whatsapp { background: var(--whatsapp-color); box-shadow: 0 4px 12px rgba(37, 211, 102, 0.2); }
        .telegram { background: var(--telegram-color); box-shadow: 0 4px 12px rgba(0, 136, 204, 0.2); }

        /* bKash Modal */
        #bkash-modal { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.6); z-index: 2000; justify-content: center; align-items: center; backdrop-filter: blur(5px); }
        .bkash-content { background: #fff; width: 92%; max-width: 360px; border-radius: 20px; overflow: hidden; color: #333; padding-bottom: 15px; box-shadow: 0 20px 40px rgba(0,0,0,0.2); }
        .bkash-header { padding: 15px; text-align: center; background: #f8f9fa; border-bottom: 1px solid #eee; }
        .bkash-header img { width: 90px; }
        .bkash-main-body { background: var(--bkash-color); color: #fff; padding: 15px; margin: 10px; border-radius: 15px; text-align: center; }
        .trx-input-box { width: 100%; padding: 12px; border-radius: 8px; border: 2px solid #eee; margin-bottom: 10px; text-align: center; font-weight: bold; color: #000; outline: none; font-size: 15px; }
        .verify-red-btn { width: 90%; margin: 10px auto 0; display: block; padding: 14px; background: #d00000; color: #fff; border: none; font-weight: bold; cursor: pointer; border-radius: 8px; font-size: 16px; }

        /* অ্যানিমেটেড সবুজ সাকসেস পপআপ */
        #success-popup { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.85); z-index: 3000; justify-content: center; align-items: center; backdrop-filter: blur(8px); }
        .success-card { 
            background: var(--white); width: 85%; max-width: 360px; padding: 35px 20px; 
            border-radius: 30px; text-align: center; border-bottom: 8px solid var(--purple-main);
            animation: slidePageIn 0.4s ease-out; box-shadow: 0 20px 45px rgba(0,0,0,0.3);
        }
        .success-icon { 
            width: 80px; height: 80px; background: #dcfce7; color: #16a34a; 
            border-radius: 50%; display: flex; align-items: center; justify-content: center; 
            font-size: 42px; margin: 0 auto 20px; animation: scalePop 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }
        @keyframes scalePop { from { transform: scale(0); } to { transform: scale(1); } }
        
        .success-text-bold { color: var(--success-green); font-size: 21px; font-weight: 800; font-family: 'Poppins', sans-serif; margin-bottom: 12px; }
        .success-text-sub { color: #374151; font-size: 15px; font-weight: 500; font-family: 'Poppins', sans-serif; line-height: 1.6; margin-bottom: 20px; }
        .contact-urgent { color: #dc2626; font-size: 15px; font-weight: bold; font-family: 'Poppins', sans-serif; border-top: 1px solid #f3f4f6; padding-top: 15px; margin-top: 5px; }

        footer { text-align: center; padding: 30px 10px; border-top: 1px solid #eee; font-size: 13px; background: #f9fafb; color: #6b7280; font-weight: bold; }
        .footer-purple { color: var(--purple-main); font-weight: bold; }
    </style>
</head>
<body onload="startLiveOrderTracking()">

<div class="top-notice-bar" id="top-announcement-bar">
    📢 <b>Notice:</b> মা-বাবা বা পরিবারের কারো ফোন থেকে টাকা চুরি করে কেউ টপআপ করবেন না! যদি করেন সে ক্ষেত্রে তাকে টপআপ দেওয়া হবে না। যেকোনো প্রয়োজন হোয়াটসঅ্যাপে বা টেলিগ্রাম এ যোগাযোগ করুন, ধন্যবাদ।
    <span class="close-notice-btn" onclick="closeTopNotice()">&times;</span>
</div>

<header>
    <div class="logo" onclick="showPage('home')">CHOR BAZAR</div>
    <nav>
        <button class="nav-btn" onclick="showPage('home')">Home</button>
        <button class="nav-btn" onclick="showPage('about')">About</button>
        <button class="nav-btn" onclick="showPage('contact')">Contact</button>
    </nav>
</header>

<div id="home" class="page active">
    <div id="notify-box">🔄 Loading last order details...</div>
    <div style="margin-bottom: 15px; font-weight: bold; color: var(--purple-main); font-family: 'Poppins'; text-transform: uppercase; font-size: 14px;">Select Game / Category</div>
    
    <div class="category-grid">
        <div class="category-image-card" onclick="openCategory('FreeFire UID TopUp')">
            <img src="ffuidtopup.jpg" alt="Free Fire UID TopUp">
            <div class="category-card-title">UID Top Up</div>
        </div>
        <div class="category-image-card" onclick="openCategory('Free Fire Membership')">
            <img src="ffmember.jpg" alt="Free Fire Membership">
            <div class="category-card-title">Membership</div>
        </div>
        <div class="category-image-card" onclick="openCategory('Evo Access UID')">
            <img src="evoacces.jpg" alt="Evo Access UID">
            <div class="category-card-title">Evo Access</div>
        </div>
        <div class="category-image-card" onclick="openCategory('Level Up Pass')">
            <img src="lvlup.jpg" alt="Level Up Pass">
            <div class="category-card-title">Level Up Pass</div>
        </div>
    </div>
</div>

<div id="pack-page" class="page">
    <button class="back-btn" onclick="showPage('home')">⬅ Back to Categories</button>
    
    <div class="box">
        <h2>1. Player UID</h2>
        <input type="text" id="uid-input" placeholder="Enter Player UID here">
    </div>
    
    <div class="box">
        <h2 id="pack-title">2. Select Recharge</h2>
        <div class="grid" id="pack-grid"></div>
    </div>

    <div class="box">
        <h2>3. Select Payment Method</h2>
        <div class="payment-method-grid">
            <div class="pay-method-card active" id="method-bkash" onclick="selectPaymentMethod('bkash')">
                <img src="https://www.logo.wine/a/logo/BKash/BKash-Logo.wine.svg" alt="bKash">
            </div>
            <div class="pay-method-card disabled" id="method-nagad">
                <img src="https://www.vectorlogo.zone/logos/nagad/nagad-ar21.svg" alt="Nagad">
                <span class="soon-badge">Soon</span>
            </div>
        </div>
    </div>
    
    <div class="box">
        <div style="color:var(--purple-main); font-size:22px; font-weight:bold; text-align: center;">Total: ৳ <span id="sum-total">0</span></div>
        <button class="btn-buy" onclick="openPayment()">BUY NOW</button>
    </div>

    <div class="rules-container" id="dynamic-rules-box">
        <div class="rules-title">⚠️ Rules & Conditions</div>
        <ul class="rules-list" id="rules-content-list"></ul>
    </div>
</div>

<div id="about" class="page">
    <div class="box">
        <h2>About CHOR BAZAR</h2>
        <p class="about-text">Welcome to <b>CHOR BAZAR</b>, your premium destination for instant gaming top-ups. We provide the fastest, safest, and most reliable Weekly and Monthly memberships for your favorite games.</p>
        <p class="about-text">Our mission is to ensure a smooth and hassle-free transaction experience so you can focus on your gaming without any interruptions.</p>
        <div style="text-align: center;"><span class="support-badge">⚡ 24/7 Support Available</span></div>
    </div>
</div>

<div id="contact" class="page">
    <div class="box">
        <h2>Contact Us</h2>
        <p class="about-text" style="text-align: center; margin-bottom: 20px;">Need help with your order? Feel free to reach out to our dedicated support team anytime through the platforms below:</p>
        <a href="https://wa.me/8801707566410" target="_blank" class="contact-btn whatsapp">💬 Connect via WhatsApp</a>
        <a href="https://t.me/RedRrox" target="_blank" class="contact-btn telegram">✈ Connect via Telegram</a>
    </div>
</div>

<div id="bkash-modal">
    <div class="bkash-content">
        <div class="bkash-header"><img src="https://www.logo.wine/a/logo/BKash/BKash-Logo.wine.svg" alt="bkash"></div>
        <div class="bkash-main-body">
            <h3 style="font-size: 14px; margin-bottom: 10px;">আপনার বিকাশ নম্বর ও TxID দিন</h3>
            <input type="text" class="trx-input-box" id="customer-phone" placeholder="নম্বরঃ 01XXXXXXXXX" maxlength="11">
            <input type="text" class="trx-input-box" id="trx-input" placeholder="ট্রানজেকশন আইডি দিন" maxlength="10">
            <p style="font-size: 12px; margin-top: 10px; text-align: left; border-top: 1px solid rgba(255,255,255,0.2); padding-top: 10px; line-height: 1.4;">
                ● send money করুনঃ <b>01779772201</b> <button onclick="copyNum()" style="padding:2px 6px; font-size:10px; border-radius:4px; border:none; background:#fff; cursor:pointer;">Copy</button><br>
                ● টাকার পরিমাণঃ ৳ <b id="pay-amount">0</b><br>
                <span style="color: #ffe4e6; font-weight: bold; display: block; margin-top: 5px; background: rgba(0,0,0,0.15); padding: 5px; border-radius: 4px;">⚠️ সতর্কবার্তা: অবশ্যই "Send Money" করতে হবে। মোবাইল রিচার্জ বা ক্যাশআউট করলে পেমেন্ট গ্রহণযোগ্য হবে না!</span>
            </p>
        </div>
        <button class="verify-red-btn" id="verify-btn" onclick="handleRealOrder()">VERIFY PAYMENT</button>
        <button onclick="document.getElementById('bkash-modal').style.display='none'" style="width:100%; background:none; border:none; padding:12px; color:#999; cursor:pointer;">CANCEL</button>
    </div>
</div>

<div id="success-popup">
    <div class="success-card">
        <div class="success-icon">✓</div>
        <div class="success-text-bold">আপনার অর্ডারটি সফল হয়েছে!</div>
        <div class="success-text-sub">কিছুক্ষণ এর মধ্যে আপনার অর্ডারটি কমপ্লিট হবে।</div>
        <div class="contact-urgent">কোনো প্রকার সমস্যা হলে contact করুন।</div>
        <button onclick="closeSuccess()" style="background:var(--purple-main); color:#fff; border:none; padding:13px 40px; border-radius:12px; font-weight:bold; cursor:pointer; width: 100%; margin-top: 20px; font-size: 15px;">ঠিক আছে</button>
    </div>
</div>

<footer>
    © 2026 <span class="footer-purple">CHOR BAZAR</span> | POWERED BY <span class="footer-purple">RRX STUDIOS</span>
</footer>

<script>
    let selectedPrice = 0;
    let selectedPackName = "";
    let activeCategory = ""; 
    let lastLoadedTxID = ""; 
    let selectedMethod = "bkash";

    const SHEETDB_API_URL = "https://sheetdb.io/api/v1/6oyklgob3u2fr"; 

    const ffUidPacks = [
        { name: "25 Diamond", price: 23 }, { name: "50 Diamond", price: 38 }, { name: "115 Diamond", price: 80 },
        { name: "240 Diamond", price: 160 }, { name: "355 Diamond", price: 240 }, { name: "480 Diamond", price: 319 },
        { name: "610 Diamond", price: 405 }, { name: "850 Diamond", price: 560 }, { name: "1240 Diamond", price: 805 },
        { name: "2530 Diamond", price: 1615 }, { name: "5060 Diamond", price: 3225 }, { name: "10120 Diamond", price: 6445 },
        { name: "Monthly", price: 800 }, { name: "Weekly Lite", price: 50 }, { name: "Weekly", price: 160 },
        { name: "2xWeekly", price: 320 }, { name: "2xMonthly", price: 1600 }
    ];

    const ffMembershipPacks = [
        { name: "Weekly Lite", price: 50 }, { name: "Weekly", price: 160 }, { name: "Monthly", price: 800 },
        { name: "2X Weekly", price: 320 }, { name: "3X Weekly", price: 480 }, { name: "2X Monthly", price: 1600 },
        { name: "1Weekly + 1Monthly", price: 960 }, { name: "2X Weekly Lite", price: 100 }, { name: "5xWeekly", price: 800 }
    ];

    const evoAccessPacks = [
        { name: "3 Days Evo Access", price: 90 }, { name: "7 Days Evo Access", price: 130 }, { name: "30 Days Evo Access", price: 340 }
    ];

    const levelUpPacks = [
        { name: "Level Up Package - Level 6", price: 50 }, { name: "Level Up Package - Level 10", price: 80 },
        { name: "Level Up Package - Level 15", price: 80 }, { name: "Level Up Package - Level 20", price: 80 },
        { name: "Level Up Package - Level 25", price: 80 }, { name: "Level Up Package - Level 30", price: 110 },
        { name: "Full Level Up Pass", price: 430 }
    ];

    const rulesData = {
        'FreeFire UID TopUp': [
            "⦿ শুধুমাত্র Bangladesh সার্ভারে ID Code দিয়ে টপ আপ হবে।",
            "⦿ Player ID Code ভুল দিয়ে Diamond না পেলে chorbazar.com কর্তৃপক্ষ দায়ী নয় ।",
            "⦿ Order কমপ্লিট হওয়ার পরেও আইডিতে ডাইমন্ড না গেলে চেক করার জন্য ID Pass দিতে হবে।",
            "⦿ অর্ডার Cancel হলে বা কোনো প্রকার সমস্যা হলে অবস্যই whatsapp বা telegram এ জানাতে হবে।"
        ],
        'Free Fire Membership': [
            "⦿ শুধুমাত্র Bangladesh সার্ভারে ID Code দিয়ে টপ আপ হবে।",
            "⦿ Player ID Code ভুল দিয়ে Diamond না পেলে chorbazar.com কর্তৃপক্ষ দায়ী নয় ।",
            "⦿ Order কমপ্লিট হওয়ার পরেও আইডিতে ডাইমন্ড না গেলে চেক করার জন্য ID Pass দিতে হবে।",
            "⦿ অর্ডার Cancel হলে বা কোনো প্রকার সমস্যা হলে অবস্যই whatsapp বা telegram এ জানাতে হবে।"
        ],
        'Evo Access UID': [
            "⦿ শুধুমাত্র Bangladesh সার্ভারে ID Code দিয়ে টপ আপ হবে।",
            "⦿ Player ID Code ভুল দিয়ে Diamond না পেলে chorbazar.com কর্তৃপক্ষ দায়ী নয় ।",
            "⦿ Order কমপ্লিট হওয়ার পরেও আইডিতে ডাইমন্ড না গেলে চেক করার জন্য ID Pass দিতে হবে।",
            "⦿ অর্ডার Cancel হলে বা কোনো প্রকার সমস্যা হলে অবস্যই whatsapp বা telegram এ জানাতে হবে।"
        ],
        'Level Up Pass': [
            "⦿ যারা আগে ৩০ লেভেল পর্যন্ত ৮০০ ডায়মন্ড এর Level Up Pass নিয়েছেন, তারা আর নিতে পারবেন না।",
            "⦿ একটা আইডিতে একবারই নিতে পারবেন, একবার নেওয়া হলে, ভবিষ্যতে সেই একই আইডিতে আর নিতে পারবেন না।",
            "⦿ নতুন Level Up Pass প্রত্যেক লেভেলের (LV.6 ,10, 15, 20, 25, 30) জন্য আলাদা করে অর্ডার করতে হবে।",
            "📊 Level Details: LV 6 (120💎) | LV 10 (200💎) | LV 15 (200💎) | LV 20 (200💎) | LV 25 (200💎) | LV 30 (350💎) = Total : 1270 Diamond.",
            "⦿ Player ID Code/UID ভুল দিয়ে Diamond না পেলে authority দায়ী নয় ।"
        ]
    };

    function closeTopNotice() { document.getElementById('top-announcement-bar').style.display = 'none'; }

    function showPage(pageId) {
        document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
        document.getElementById(pageId).classList.add('active');
        window.scrollTo({ top: 0, behavior: 'smooth' });
        if(pageId === 'home') {
            selectedPrice = 0; selectedPackName = "";
            document.getElementById('sum-total').innerText = 0;
            document.getElementById('uid-input').value = "";
        }
    }

    function openCategory(categoryName) {
        activeCategory = categoryName;
        document.getElementById('pack-title').innerText = "2. Select Recharge";
        const grid = document.getElementById('pack-grid');
        grid.innerHTML = ""; 
        
        let selectedArray = [];
        if(categoryName === 'FreeFire UID TopUp') selectedArray = ffUidPacks;
        else if(categoryName === 'Free Fire Membership') selectedArray = ffMembershipPacks;
        else if(categoryName === 'Evo Access UID') selectedArray = evoAccessPacks;
        else if(categoryName === 'Level Up Pass') selectedArray = levelUpPacks;

        selectedArray.forEach(pack => {
            grid.innerHTML += `
                <div class="item" onclick="selectPack(this, '${pack.name}', ${pack.price})">
                    <span style="font-weight: 700;">${pack.name}</span>
                    <span class="price">৳ ${pack.price}</span>
                </div>
            `;
        });

        const rulesListHTML = document.getElementById('rules-content-list');
        rulesListHTML.innerHTML = "";
        if(rulesData[categoryName]) {
            rulesData[categoryName].forEach(rule => { rulesListHTML.innerHTML += `<li>${rule}</li>`; });
        }
        showPage('pack-page');
    }

    function selectPack(el, name, price) {
        document.querySelectorAll('.item').forEach(i => i.classList.remove('active'));
        el.classList.add('active');
        selectedPrice = price; selectedPackName = name;
        document.getElementById('sum-total').innerText = price;
        document.getElementById('pay-amount').innerText = price;
    }

    function selectPaymentMethod(method) {
        // নগদ ডিসেবলড তাই শুধু বিকাশ সিলেক্ট করা যাবে
        if(method === 'bkash') {
            selectedMethod = "bkash";
            document.getElementById('method-bkash').classList.add('active');
        }
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
                    "Category": activeCategory, 
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
                updateNotifyBox(uid, selectedPackName);
                lastLoadedTxID = trx.toUpperCase();
            }
        })
        .catch(error => {
            verifyBtn.disabled = false;
            verifyBtn.innerText = "VERIFY PAYMENT";
            alert("Error! Please check internet connection.");
        });
    }

    function closeSuccess() { showPage('home'); document.getElementById('success-popup').style.display = 'none'; }
    function copyNum() { navigator.clipboard.writeText("01779772201"); alert("Number Copied!"); }

    function updateNotifyBox(uid, pack) {
        const notify = document.getElementById('notify-box');
        if (notify) {
            notify.style.opacity = '0';
            setTimeout(() => {
                let maskedUID = uid;
                if(uid.length > 4) { maskedUID = uid.substring(0, uid.length - 4) + "****"; }
                notify.innerHTML = `🔥 Last Order: <span style="color:#6a0dad">${maskedUID}</span> bought <b>${pack}</b>!`;
                notify.style.opacity = '1';
            }, 500);
        }
    }

    function fetchLiveLastOrder() {
        fetch(SHEETDB_API_URL)
        .then(response => response.json())
        .then(data => {
            if (data && data.length > 0) {
                const lastOrder = data[data.length - 1];
                const currentTxID = lastOrder['TxID'] || lastOrder['transaction_id'] || lastOrder['Txid'];
                
                if (currentTxID !== lastLoadedTxID) {
                    const uid = lastOrder['Player UID'] || lastOrder['UID'] || "Unknown";
                    const pack = lastOrder['Selected Pack'] || lastOrder['Pack'] || "Pack";
                    updateNotifyBox(uid, pack);
                    lastLoadedTxID = currentTxID; 
                }
            } else {
                document.getElementById('notify-box').innerText = "🚀 Waiting for the first order...";
            }
        })
        .catch(error => console.log("Live tracking check."));
    }

    function startLiveOrderTracking() {
        fetchLiveLastOrder(); 
        setInterval(fetchLiveLastOrder, 12000); 
    }

    document.getElementById('customer-phone').addEventListener('input', function (e) { this.value = this.value.replace(/[^0-9]/g, ''); });
    document.getElementById('uid-input').addEventListener('input', function (e) { this.value = this.value.replace(/[^0-9]/g, ''); });
</script>
</body>
</html>
