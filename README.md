
<html lang="ar" البيع="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>بيع وشراء USDT عبر شام كاش</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f8fa;
            color: #333;
            line-height: 1.6;
            padding: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }
        
        .container {
            width: 100%;
            max-width: 380px;
            background: white;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            position: relative;
        }
        
        header {
            background: linear-gradient(135deg, #2a6ac5, #1e488c);
            color: white;
            padding: 20px;
            text-align: center;
        }
        
        header h1 {
            font-size: 22px;
            margin-bottom: 5px;
        }
        
        header p {
            font-size: 14px;
            opacity: 0.9;
        }
        
        .telegram-float {
            position: fixed;
            bottom: 20px;
            left: 20px;
            z-index: 1000;
            background: #2a96d9;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            animation: pulse 2s infinite;
        }
        
        .telegram-float a {
            color: white;
            font-size: 24px;
        }
        
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        .form-container {
            padding: 20px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: 600;
            font-size: 14px;
        }
        
        .form-group input, .form-group select {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 6px;
            font-size: 14px;
        }
        
        .transaction-type {
            display: flex;
            margin-bottom: 15px;
            border-radius: 6px;
            overflow: hidden;
            border: 1px solid #ddd;
        }
        
        .transaction-type button {
            flex: 1;
            padding: 12px;
            border: none;
            background: #f0f0f0;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .transaction-type button.active {
            background: #2a6ac5;
            color: white;
        }
        
        .buy-section, .sell-section {
            display: none;
        }
        
        .buy-section.active, .sell-section.active {
            display: block;
            animation: fadeIn 0.5s;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .address-box {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 6px;
            margin: 15px 0;
            font-size: 12px;
            word-break: break-all;
            border: 1px dashed #ccc;
        }
        
        .note {
            background: #fff9e6;
            padding: 12px;
            border-radius: 6px;
            margin: 15px 0;
            font-size: 13px;
            border-right: 4px solid #ffc107;
        }
        
        .note h4 {
            margin-bottom: 5px;
            color: #856404;
        }
        
        .submit-btn {
            background: linear-gradient(135deg, #2a6ac5, #1e488c);
            color: white;
            border: none;
            padding: 15px;
            border-radius: 6px;
            width: 100%;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .submit-btn:hover {
            background: linear-gradient(135deg, #1e488c, #15376d);
        }
        
        .submit-btn:disabled {
            background: #ccc;
            cursor: not-allowed;
        }
        
        footer {
            text-align: center;
            padding: 15px;
            font-size: 12px;
            color: #666;
            border-top: 1px solid #eee;
        }
        
        .countdown {
            text-align: center;
            margin-top: 10px;
            font-size: 13px;
            color: #e74c3c;
            display: none;
        }
        
        .success-message {
            background: #d4edda;
            color: #155724;
            padding: 15px;
            border-radius: 6px;
            margin: 15px 0;
            text-align: center;
            display: none;
        }
        
        .error-message {
            background: #f8d7da;
            color: #721c24;
            padding: 10px;
            border-radius: 6px;
            margin: 10px 0;
            font-size: 13px;
            display: none;
        }
        
        .loading {
            display: none;
            text-align: center;
            margin: 10px 0;
        }
        
        .loading-spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #3498db;
            border-radius: 50%;
            width: 30px;
            height: 30px;
            animation: spin 1s linear infinite;
            margin: 0 auto;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- أيقونة التلجرام الطافية -->
    <div class="telegram-float">
        <a href="https://t.me/ali0619000" target="_blank">
            <i class="fab fa-telegram-plane"></i>
        </a>
    </div>

    <div class="container">
        <header>
            <h1>بيع وشراء USDT</h1>
            <p>من خلال شام كاش -  سعر الصرف 116.00p/p>
            <p>العمولة 1$ + 0.05% p/p>
        </header>

        <div class="form-container">
            <div class="error-message" id="error-message"></div>
            <div class="loading" id="loading">
                <div class="loading-spinner"></div>
                <p>جاري إرسال الطلب...</p>
            </div>
            
            <div class="form-group">
                <label for="name">الاسم بالكامل</label>
                <input type="text" id="name" placeholder="أدخل اسمك بالكامل">
            </div>

            <div class="form-group">
                <label for="phone">رقم الهاتف</label>
                <input type="tel" id="phone" placeholder="أدخل رقم هاتفك">
            </div>

            <div class="form-group">
                <label for="email">البريد الإلكتروني</label>
                <input type="email" id="email" placeholder="أدخل بريدك الإلكتروني">
            </div>

            <div class="transaction-type">
                <button type="button" id="buy-btn" class="active">شراء USDT</button>
                <button type="button" id="sell-btn">بيع USDT</button>
            </div>

            <!-- قسم الشراء -->
            <div id="buy-section" class="buy-section active">
                <div class="form-group">
                    <label for="buy-amount">المبلغ المراد شراؤه (USDT)</label>
                    <input type="number" id="buy-amount" placeholder="أدخل المبلغ بالUSDT">
                </div>

                <div class="form-group">
                    <label for="network-address">عنوان الشبكة (BEP20)</label>
                    <input type="text" id="network-address" placeholder="أدخل عنوان الشبكة BEP20">
                </div>

                <div class="form-group">
                    <label for="currency-type">طريقة الدفع</label>
                    <select id="currency-type">
وسريع                   <option value="syp">الليرة السورية</option>
                        <option value="usd">الدولار الأمريكي</option>
                    </select>
                </div>

                <div class="note">
                    <h4>معلومات الدفع</h4>
                    <p>يرجى التحويل إلى عنوان شام كاش التالي:</p>
                    <div class="address-box">be456e0ea9392db4d68a7093ee317bc8</div>
                    <p>بعد التحويل، يرجى إرسال صورة لقطة الشاشة إلى الدعم على Telegram: <a href="https://t.me/ali0619000" target="_blank">@ali0619000</a></p>
                </div>
            </div>

            <!-- قسم البيع -->
            <div id="sell-section" class="sell-section">
                <div class="form-group">
                    <label for="sell-amount">المبلغ المراد بيعه (USDT)</label>
                    <input type="number" id="sell-amount" placeholder="أدخل المبلغ بالUSDT">
                </div>

                <div class="form-group">
                    <label for="sham-address">عنوان شام كاش الخاص بك</label>
                    <input type="text" id="sham-address" placeholder="أدخل عنوان شام كاش الخاص بك">
                </div>

                <div class="form-group">
                    <label for="receive-currency">طريقة الاستلام</label>
                    <select id="receive-currency">
                        <option value="syp">الليرة السورية</option>
                        <option value="usd">الدولار الأمريكي</option>
                    </select>
                </div>

                <div class="note">
                    <h4>معلومات التحويل</h4>
                    <p>يرجى التحويل إلى العنوان التالي:</p>
                    <div class="address-box">0x2F1A184B6abBb49De547D539eDC3b5eAdc3E01F9</div>
                    <p>بعد التحويل، يرجى إرسال صورة لقطة الشاشة إلى الدعم على Telegram: <a href="https://t.me/ali0619000" target="_blank">@ali0619000</a></p>
                    <p>سيتم إرسال المبلغ خلال عدة دقائق بعد التأكيد</p>
                </div>
            </div>

            <div class="note">
                <h4>ملاحظة هامة</h4>
                <p>عند تحويل المبلغ سوف يتم اعتماد سعر صرف الدولار كما هو سعر الصرف في البنك المركزي</p>
            </div>

            <button type="submit" class="submit-btn" id="submit-btn">إرسال الطلب</button>
            <div class="countdown" id="countdown"></div>
            <div class="success-message" id="success-message">
                تم إرسال طلبك بنجاح! سيتم التواصل معك قريباً.
            </div>
        </div>

        <footer>
            <p>جميع الحقوق محفوظة ©  | نظام بيع وشراء USDT</p>
        </footer>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const buyBtn = document.getElementById('buy-btn');
            const sellBtn = document.getElementById('sell-btn');
            const buySection = document.getElementById('buy-section');
            const sellSection = document.getElementById('sell-section');
            const submitBtn = document.getElementById('submit-btn');
            const countdownEl = document.getElementById('countdown');
            const successMessage = document.getElementById('success-message');
            const errorMessage = document.getElementById('error-message');
            const loadingEl = document.getElementById('loading');
            
            // إعدادات Telegram
            const BOT_TOKEN = "8126453870:AAHKpVDTFA5R5SHcYQVldkNlQp83PKlxeio";
            const CHAT_ID = "910021564";
            
            // التبديل بين شراء وبيع
            buyBtn.addEventListener('click', function() {
                buyBtn.classList.add('active');
                sellBtn.classList.remove('active');
                buySection.classList.add('active');
                sellSection.classList.remove('active');
            });
            
            sellBtn.addEventListener('click', function() {
                sellBtn.classList.add('active');
                buyBtn.classList.remove('active');
                sellSection.classList.add('active');
                buySection.classList.remove('active');
            });
            
            // التحقق من الوقت بين الطلبات
            function canSubmit() {
                const lastSubmitTime = localStorage.getItem('lastSubmitTime');
                if (!lastSubmitTime) return true;
                
                const currentTime = new Date().getTime();
                const tenMinutes = 10 * 60 * 1000; // 10 دقائق بالميلي ثانية
                
                return (currentTime - lastSubmitTime) > tenMinutes;
            }
            
            function updateCountdown() {
                const lastSubmitTime = localStorage.getItem('lastSubmitTime');
                if (!lastSubmitTime) return;
                
                const currentTime = new Date().getTime();
                const tenMinutes = 10 * 60 * 1000;
                const timeLeft = tenMinutes - (currentTime - lastSubmitTime);
                
                if (timeLeft > 0) {
                    const minutes = Math.floor(timeLeft / 60000);
                    const seconds = Math.floor((timeLeft % 60000) / 1000);
                    
                    countdownEl.style.display = 'block';
                    countdownEl.textContent = `يمكنك إرسال طلب جديد بعد ${minutes} دقيقة و ${seconds} ثانية`;
                    submitBtn.disabled = true;
                    
                    setTimeout(updateCountdown, 1000);
                } else {
                    countdownEl.style.display = 'none';
                    submitBtn.disabled = false;
                    localStorage.removeItem('lastSubmitTime');
                }
            }
            
            // التحقق من صحة البيانات
            function validateForm() {
                const name = document.getElementById('name').value.trim();
                const phone = document.getElementById('phone').value.trim();
                const email = document.getElementById('email').value.trim();
                
                if (!name) {
                    showError('يرجى إدخال الاسم بالكامل');
                    return false;
                }
                
                if (!phone) {
                    showError('يرجى إدخال رقم الهاتف');
                    return false;
                }
                
                if (!email) {
                    showError('يرجى إدخال البريد الإلكتروني');
                    return false;
                }
                
                // التحقق من صحة البريد الإلكتروني
                const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                if (!emailRegex.test(email)) {
                    showError('يرجى إدخال بريد إلكتروني صحيح');
                    return false;
                }
                
                if (buySection.classList.contains('active')) {
                    const buyAmount = document.getElementById('buy-amount').value.trim();
                    const networkAddress = document.getElementById('network-address').value.trim();
                    
                    if (!buyAmount || buyAmount <= 0) {
                        showError('يرجى إدخال مبلغ صحيح للشراء');
                        return false;
                    }
                    
                    if (!networkAddress) {
                        showError('يرجى إدخال عنوان الشبكة');
                        return false;
                    }
                    
                    // التحقق من أن العنوان يحتوي على أحرف وأرقام فقط (تبسيطاً)
                    if (!/^[a-zA-Z0-9]+$/.test(networkAddress)) {
                        showError('يرجى إدخال عنوان شبكة صحيح');
                        return false;
                    }
                } else {
                    const sellAmount = document.getElementById('sell-amount').value.trim();
                    const shamAddress = document.getElementById('sham-address').value.trim();
                    
                    if (!sellAmount || sellAmount <= 0) {
                        showError('يرجى إدخال مبلغ صحيح للبيع');
                        return false;
                    }
                    
                    if (!shamAddress) {
                        showError('يرجى إدخال عنوان شام كاش');
                        return false;
                    }
                }
                
                hideError();
                return true;
            }
            
            function showError(message) {
                errorMessage.textContent = message;
                errorMessage.style.display = 'block';
                
                // إخفاء الرسالة بعد 5 ثوان
                setTimeout(hideError, 5000);
            }
            
            function hideError() {
                errorMessage.style.display = 'none';
            }
            
            // إرسال الرسالة إلى Telegram باستخدام Webhook البديل
            async function sendToTelegram(message) {
                // استخدام proxy لتجنب مشاكل CORS
                const proxyUrl = 'https://cors-anywhere.herokuapp.com/';
                const apiUrl = `https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`;
                
                try {
                    const response = await fetch(proxyUrl + apiUrl, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json',
                        },
                        body: JSON.stringify({
                            chat_id: CHAT_ID,
                            text: message,
                            parse_mode: 'HTML'
                        })
                    });
                    
                    const data = await response.json();
                    return data.ok;
                } catch (error) {
                    console.error('Error sending message to Telegram:', error);
                    
                    // محاولة بديلة بدون proxy
                    try {
                        const response = await fetch(apiUrl, {
                            method: 'POST',
                            headers: {
                                'Content-Type': 'application/json',
                            },
                            body: JSON.stringify({
                                chat_id: CHAT_ID,
                                text: message,
                                parse_mode: 'HTML'
                            })
                        });
                        
                        const data = await response.json();
                        return data.ok;
                    } catch (secondError) {
                        console.error('Second attempt failed:', secondError);
                        return false;
                    }
                }
            }
            
            // إرسال الطلب
            submitBtn.addEventListener('click', async function() {
                if (!canSubmit()) {
                    updateCountdown();
                    return;
                }
                
                if (!validateForm()) {
                    return;
                }
                
                // إظهار تحميل
                loadingEl.style.display = 'block';
                submitBtn.disabled = true;
                
                // جمع البيانات
                const name = document.getElementById('name').value.trim();
                const phone = document.getElementById('phone').value.trim();
                const email = document.getElementById('email').value.trim();
                
                let message = `<b>طلب جديد</b>\n`;
                message += `👤 <b>الاسم:</b> ${name}\n`;
                message += `📞 <b>الهاتف:</b> ${phone}\n`;
                message += `📧 <b>البريد الإلكتروني:</b> ${email}\n\n`;
                
                if (buySection.classList.contains('active')) {
                    const buyAmount = document.getElementById('buy-amount').value.trim();
                    const networkAddress = document.getElementById('network-address').value.trim();
                    const currencyType = document.getElementById('currency-type').value;
                    const currencyText = currencyType === 'syp' ? 'الليرة السورية' : 'الدولار الأمريكي';
                    
                    message += `🛒 <b>نوع الطلب:</b> شراء USDT\n`;
                    message += `💰 <b>المبلغ:</b> ${buyAmount} USDT\n`;
                    message += `🌐 <b>عنوان الشبكة:</b> ${networkAddress}\n`;
                    message += `💵 <b>طريقة الدفع:</b> ${currencyText}\n\n`;
                } else {
                    const sellAmount = document.getElementById('sell-amount').value.trim();
                    const shamAddress = document.getElementById('sham-address').value.trim();
                    const receiveCurrency = document.getElementById('receive-currency').value;
                    const currencyText = receiveCurrency === 'syp' ? 'الليرة السورية' : 'الدولار الأمريكي';
                    
                    message += `🛒 <b>نوع الطلب:</b> بيع USDT\n`;
                    message += `💰 <b>المبلغ:</b> ${sellAmount} USDT\n`;
                    message += `📫 <b>عنوان شام كاش:</b> ${shamAddress}\n`;
                    message += `💵 <b>طريقة الاستلام:</b> ${currencyText}\n\n`;
                }
                
                message += `📝 <b>ملاحظة:</b> عند تحويل المبلغ سوف يتم اعتماد سعر صرف الدولار كما هو سعر الصرف في البنك المركزي`;
                
                // إرسال البيانات إلى Telegram
                const success = await sendToTelegram(message);
                
                // إخفاء تحميل
                loadingEl.style.display = 'none';
                
                if (success) {
                    // حفظ وقت الإرسال الأخير
                    localStorage.setItem('lastSubmitTime', new Date().getTime());
                    
                    // عرض رسالة النجاح
                    successMessage.style.display = 'block';
                    submitBtn.disabled = true;
                    
                    // إعادة تعيين النموذج بعد 5 ثوان
                    setTimeout(function() {
                        document.querySelectorAll('input').forEach(input => input.value = '');
                        successMessage.style.display = 'none';
                        updateCountdown();
                    }, 5000);
                } else {
                    showError('حدث خطأ أثناء إرسال الطلب. يرجى المحاولة مرة أخرى أو التواصل مع الدعم.');
                    submitBtn.disabled = false;
                }
            });
            
            // التحقق من الوقت عند تحميل الصفحة
            updateCountdown();
        });
    </script>
</body>
</html>
