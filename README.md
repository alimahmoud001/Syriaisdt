<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام بيع وشراء USDT - شام كاش</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
            --success-color: #27ae60;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
            padding: 0;
            margin: 0;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 15px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary-color), #1a2530);
            color: white;
            padding: 20px;
            text-align: center;
            border-radius: 10px;
            margin-bottom: 20px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        h1, h2, h3 {
            margin-bottom: 15px;
        }
        
        .card {
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
            padding: 20px;
            margin-bottom: 20px;
            transition: transform 0.3s;
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: var(--dark-color);
        }
        
        input[type="number"],
        input[type="text"],
        select {
            width: 100%;
            padding: 14px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border 0.3s;
        }
        
        input:focus, select:focus {
            border-color: var(--secondary-color);
            outline: none;
            box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
        }
        
        button {
            background: linear-gradient(135deg, var(--secondary-color), #2980b9);
            color: white;
            border: none;
            padding: 16px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 18px;
            width: 100%;
            transition: all 0.3s;
            font-weight: bold;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        button:hover {
            background: linear-gradient(135deg, #2980b9, var(--secondary-color));
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }
        
        .result {
            display: none;
            margin-top: 25px;
            padding: 20px;
            background-color: #f8f9fa;
            border-radius: 8px;
            border-right: 4px solid var(--secondary-color);
            animation: fadeIn 0.5s ease-in;
        }
        
        .info-box {
            background-color: #e8f4fd;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 20px;
            border-right: 4px solid var(--secondary-color);
        }
        
        .address-box {
            background-color: #f9f9f9;
            padding: 15px;
            border-radius: 8px;
            margin: 15px 0;
            word-break: break-all;
            font-family: monospace;
            font-size: 14px;
            border: 1px dashed #ccc;
        }
        
        .tab {
            overflow: hidden;
            border: 1px solid #ccc;
            background-color: #f1f1f1;
            border-radius: 8px 8px 0 0;
            display: flex;
        }
        
        .tab button {
            background-color: inherit;
            border: none;
            outline: none;
            cursor: pointer;
            padding: 16px;
            transition: 0.3s;
            color: var(--dark-color);
            flex: 1;
            font-size: 16px;
            font-weight: bold;
        }
        
        .tab button:hover {
            background-color: #ddd;
        }
        
        .tab button.active {
            background: linear-gradient(135deg, var(--secondary-color), #2980b9);
            color: white;
        }
        
        .tabcontent {
            display: none;
            padding: 20px;
            border: 1px solid #ccc;
            border-top: none;
            border-radius: 0 0 8px 8px;
            background-color: white;
        }
        
        .commission-notice {
            font-size: 14px;
            color: #666;
            margin-top: 8px;
        }
        
        footer {
            text-align: center;
            margin-top: 30px;
            color: #666;
            font-size: 14px;
            padding: 20px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
        }
        
        .telegram-link {
            color: var(--secondary-color);
            text-decoration: none;
            font-weight: bold;
        }
        
        .telegram-link:hover {
            text-decoration: underline;
        }
        
        .final-notice {
            margin-top: 20px;
            padding: 15px;
            background-color: #fff3cd;
            border-radius: 8px;
            border-right: 4px solid #ffc107;
            font-size: 15px;
            text-align: center;
        }
        
        .loader {
            display: none;
            border: 5px solid #f3f3f3;
            border-radius: 50%;
            border-top: 5px solid var(--secondary-color);
            width: 50px;
            height: 50px;
            margin: 20px auto;
            animation: spin 1s linear infinite;
        }
        
        .success-message {
            display: none;
            color: var(--success-color);
            text-align: center;
            margin-top: 15px;
            font-weight: bold;
            font-size: 16px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        .copy-btn {
            background: linear-gradient(135deg, #7d7d7d, #5d5d5d);
            padding: 10px;
            font-size: 14px;
            margin-top: 10px;
            width: auto;
            display: inline-block;
        }
        
        .copy-btn:hover {
            background: linear-gradient(135deg, #5d5d5d, #7d7d7d);
        }
        
        /* تحسينات للجوال */
        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }
            
            header {
                padding: 15px;
            }
            
            h1 {
                font-size: 24px;
            }
            
            .card {
                padding: 15px;
            }
            
            input[type="number"],
            input[type="text"],
            select {
                padding: 12px;
            }
            
            button {
                padding: 14px;
                font-size: 16px;
            }
            
            .tab button {
                padding: 14px;
                font-size: 14px;
            }
            
            .address-box {
                font-size: 12px;
                padding: 12px;
            }
        }
        
        @media (max-width: 480px) {
            header h1 {
                font-size: 20px;
            }
            
            .tab {
                flex-direction: column;
            }
            
            .info-box {
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-exchange-alt"></i> نظام بيع وشراء USDT عبر شام كاش</h1>
        </header>
        
        <div class="card">
            <div class="info-box">
                <h3><i class="fas fa-info-circle"></i> معلومات مهمة</h3>
                <p><i class="fas fa-dollar-sign"></i> سعر صرف الدولار: <strong>11000</strong> ليرة سورية</p>
                <p><i class="fas fa-percentage"></i> العمولة: 1$ + 0.5% من المبلغ الإجمالي</p>
            </div>
            
            <div class="tab">
                <button class="tablinks active" onclick="openTab(event, 'Buy')"><i class="fas fa-shopping-cart"></i> شراء USDT</button>
                <button class="tablinks" onclick="openTab(event, 'Sell')"><i class="fas fa-coins"></i> بيع USDT</button>
            </div>
            
            <div id="Buy" class="tabcontent" style="display: block;">
                <h3><i class="fas fa-shopping-cart"></i> شراء USDT</h3>
                <form id="buyForm">
                    <div class="form-group">
                        <label for="buyAmount"><i class="fas fa-money-bill-wave"></i> المبلغ المراد شراءه (USDT):</label>
                        <input type="number" id="buyAmount" step="0.01" min="1" required placeholder="أدخل المبلغ بالـ USDT">
                    </div>
                    
                    <div class="form-group">
                        <label for="networkAddress"><i class="fas fa-wallet"></i> عنوان الشبكة (BEP20 فقط):</label>
                        <input type="text" id="networkAddress" required placeholder="أدخل عنوان المحفظة BEP20">
                    </div>
                    
                    <div class="form-group">
                        <label><i class="fas fa-money-check"></i> طريقة الدفع:</label>
                        <select id="buyCurrency">
                            <option value="usd">الدولار الأمريكي ($)</option>
                            <option value="syp">الليرة السورية (SYP)</option>
                        </select>
                    </div>
                    
                    <button type="submit"><i class="fas fa-calculator"></i> احسب المبلغ المستحق</button>
                </form>
                
                <div id="buyResult" class="result">
                    <h3><i class="fas fa-file-invoice-dollar"></i> تفاصيل عملية الشراء</h3>
                    <p>المبلغ المراد شراءه: <span id="resultBuyAmount"></span> USDT</p>
                    <p>العمولة: <span id="buyCommission"></span></p>
                    <p>المبلغ الإجمالي المستحق: <span id="totalBuyAmount"></span></p>
                    
                    <div class="info-box">
                        <p><i class="fas fa-info-circle"></i> يرجى تحويل المبلغ إلى عنوان شام كاش التالي:</p>
                        <div class="address-box">be456e0ea9392db4d68a7093ee317bc8</div>
                        <button class="copy-btn" onclick="copyToClipboard('be456e0ea9392db4d68a7093ee317bc8')"><i class="fas fa-copy"></i> نسخ العنوان</button>
                        
                        <p style="margin-top: 15px;">
                            <i class="fas fa-comment"></i> بعد التحويل، يرجى إرسال صورة لقطة الشاشة إلى الدعم على Telegram: 
                            <a href="https://t.me/ali0619000" class="telegram-link" target="_blank">@ali0619000</a>
                        </p>
                    </div>
                    
                    <button onclick="sendToTelegram('buy')" style="margin-top: 15px; background: linear-gradient(135deg, #0088cc, #005c8a);">
                        <i class="fab fa-telegram"></i> إرسال الطلب إلى Telegram
                    </button>
                </div>
            </div>
            
            <div id="Sell" class="tabcontent">
                <h3><i class="fas fa-coins"></i> بيع USDT</h3>
                <form id="sellForm">
                    <div class="form-group">
                        <label for="sellAmount"><i class="fas fa-money-bill-wave"></i> المبلغ المراد بيعه (USDT):</label>
                        <input type="number" id="sellAmount" step="0.01" min="1" required placeholder="أدخل المبلغ بالـ USDT">
                    </div>
                    
                    <div class="form-group">
                        <label for="shamCashAddress"><i class="fas fa-wallet"></i> عنوان شام كاش الخاص بك:</label>
                        <input type="text" id="shamCashAddress" required placeholder="أدخل عنوان شام كاش">
                    </div>
                    
                    <div class="form-group">
                        <label><i class="fas fa-money-check"></i> طريقة الاستلام:</label>
                        <select id="receiveCurrency">
                            <option value="syp">الليرة السورية (SYP)</option>
                            <option value="usd">الدولار الأمريكي ($)</option>
                        </select>
                    </div>
                    
                    <button type="submit"><i class="fas fa-calculator"></i> احسب المبلغ المستلم</button>
                </form>
                
                <div id="sellResult" class="result">
                    <h3><i class="fas fa-file-invoice-dollar"></i> تفاصيل عملية البيع</h3>
                    <p>المبلغ المراد بيعه: <span id="resultSellAmount"></span> USDT</p>
                    <p>العمولة: <span id="sellCommission"></span></p>
                    <p>المبلغ الإجمالي المستلم: <span id="totalSellAmount"></span></p>
                    
                    <div class="info-box">
                        <p><i class="fas fa-info-circle"></i> يرجى تحويل USDT إلى العنوان التالي:</p>
                        <div class="address-box">0x2F1A184B6abBb49De547D539eDC3b5eAdc3E01F9</div>
                        <button class="copy-btn" onclick="copyToClipboard('0x2F1A184B6abBb49De547D539eDC3b5eAdc3E01F9')"><i class="fas fa-copy"></i> نسخ العنوان</button>
                        
                        <p style="margin-top: 15px;">
                            <i class="fas fa-comment"></i> بعد التحويل، يرجى إرسال صورة لقطة الشاشة إلى الدعم على Telegram: 
                            <a href="https://t.me/ali0619000" class="telegram-link" target="_blank">@ali0619000</a>
                        </p>
                        <p><i class="fas fa-clock"></i> سيتم إرسال المبلغ خلال عدة دقائق بعد التأكد من التحويل.</p>
                    </div>
                    
                    <button onclick="sendToTelegram('sell')" style="margin-top: 15px; background: linear-gradient(135deg, #0088cc, #005c8a);">
                        <i class="fab fa-telegram"></i> إرسال الطلب إلى Telegram
                    </button>
                </div>
            </div>
        </div>
        
        <div class="final-notice">
            <i class="fas fa-exclamation-circle"></i> عند تحويل المبلغ سوف يتم اعتماد سعر صرف الدولار كما هو سعر الصرف في البنك المركزي.
        </div>
        
        <div class="loader" id="loader"></div>
        <div class="success-message" id="successMessage">
            <i class="fas fa-check-circle"></i> تم إرسال الطلب بنجاح إلى المجموعة!
        </div>
        
        <footer>
            <p><i class="fas fa-headset"></i> لأي استفسار، يرجى التواصل مع الدعم على Telegram: <a href="https://t.me/ali0619000" class="telegram-link" target="_blank">@ali0619000</a></p>
            <p><i class="fab fa-telegram"></i> سيتم إرسال التفاصيل إلى مجموعة Telegram: <a href="https://t.me/shamcashusdt1" class="telegram-link" target="_blank">@shamcashusdt1</a></p>
        </footer>
    </div>

    <script>
        // سعر الصرف الثابت
        const exchangeRate = 11000; // 1 USD = 11000 SYP
        
        // فتح التبويبات
        function openTab(evt, tabName) {
            var i, tabcontent, tablinks;
            tabcontent = document.getElementsByClassName("tabcontent");
            for (i = 0; i < tabcontent.length; i++) {
                tabcontent[i].style.display = "none";
            }
            tablinks = document.getElementsByClassName("tablinks");
            for (i = 0; i < tablinks.length; i++) {
                tablinks[i].className = tablinks[i].className.replace(" active", "");
            }
            document.getElementById(tabName).style.display = "block";
            evt.currentTarget.className += " active";
        }
        
        // حساب العمولة
        function calculateCommission(amount) {
            const fixedFee = 1; // 1$ ثابت
            const percentageFee = 0.005; // 0.5%
            return fixedFee + (amount * percentageFee);
        }
        
        // نسخ النص إلى الحافظة
        function copyToClipboard(text) {
            navigator.clipboard.writeText(text).then(function() {
                alert("تم نسخ العنوان: " + text);
            }, function() {
                // Fallback for older browsers
                const textArea = document.createElement("textarea");
                textArea.value = text;
                document.body.appendChild(textArea);
                textArea.select();
                document.execCommand('copy');
                document.body.removeChild(textArea);
                alert("تم نسخ العنوان: " + text);
            });
        }
        
        // معالجة نموذج الشراء
        document.getElementById('buyForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const amount = parseFloat(document.getElementById('buyAmount').value);
            const currency = document.getElementById('buyCurrency').value;
            const address = document.getElementById('networkAddress').value;
            const commission = calculateCommission(amount);
            
            let totalAmount;
            let commissionText;
            let totalText;
            
            if (currency === 'usd') {
                totalAmount = amount + commission;
                commissionText = commission.toFixed(2) + " $";
                totalText = totalAmount.toFixed(2) + " $";
            } else {
                totalAmount = (amount + commission) * exchangeRate;
                commissionText = (commission * exchangeRate).toFixed(0) + " SYP (" + commission.toFixed(2) + " $)";
                totalText = totalAmount.toFixed(0) + " SYP";
            }
            
            document.getElementById('resultBuyAmount').textContent = amount.toFixed(2);
            document.getElementById('buyCommission').textContent = commissionText;
            document.getElementById('totalBuyAmount').textContent = totalText;
            document.getElementById('buyResult').style.display = 'block';
            
            // حفظ البيانات في localStorage لإرسالها لاحقًا
            const transactionData = {
                type: 'شراء',
                amount: amount,
                currency: currency,
                address: address,
                commission: commission,
                total: totalAmount,
                timestamp: new Date().toLocaleString()
            };
            localStorage.setItem('currentTransaction', JSON.stringify(transactionData));
        });
        
        // معالجة نموذج البيع
        document.getElementById('sellForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const amount = parseFloat(document.getElementById('sellAmount').value);
            const currency = document.getElementById('receiveCurrency').value;
            const address = document.getElementById('shamCashAddress').value;
            const commission = calculateCommission(amount);
            
            let netAmount;
            let commissionText;
            let totalText;
            
            if (currency === 'usd') {
                netAmount = amount - commission;
                commissionText = commission.toFixed(2) + " $";
                totalText = netAmount.toFixed(2) + " $";
            } else {
                netAmount = (amount - commission) * exchangeRate;
                commissionText = (commission * exchangeRate).toFixed(0) + " SYP (" + commission.toFixed(2) + " $)";
                totalText = netAmount.toFixed(0) + " SYP";
            }
            
            document.getElementById('resultSellAmount').textContent = amount.toFixed(2);
            document.getElementById('sellCommission').textContent = commissionText;
            document.getElementById('totalSellAmount').textContent = totalText;
            document.getElementById('sellResult').style.display = 'block';
            
            // حفظ البيانات في localStorage لإرسالها لاحقًا
            const transactionData = {
                type: 'بيع',
                amount: amount,
                currency: currency,
                address: address,
                commission: commission,
                total: netAmount,
                timestamp: new Date().toLocaleString()
            };
            localStorage.setItem('currentTransaction', JSON.stringify(transactionData));
        });
        
        // إرسال البيانات إلى Telegram
        function sendToTelegram(type) {
            const transactionData = JSON.parse(localStorage.getItem('currentTransaction'));
            if (!transactionData) {
                alert('لا يوجد بيانات لإرسالها. يرجى تعبئة النموذج أولاً.');
                return;
            }
            
            // عرض تحميل
            document.getElementById('loader').style.display = 'block';
            document.getElementById('successMessage').style.display = 'none';
            
            // نص الرسالة
            let message = `*طلب ${transactionData.type} USDT عبر شام كاش*%0A%0A`;
            message += `*النوع:* ${transactionData.type}%0A`;
            message += `*المبلغ:* ${transactionData.amount} USDT%0A`;
            message += `*طريقة الدفع/الاستلام:* ${transactionData.currency === 'usd' ? 'دولار أمريكي' : 'ليرة سورية'}%0A`;
            message += `*العمولة:* ${transactionData.commission.toFixed(2)} $%0A`;
            message += `*المبلغ الإجمالي:* ${transactionData.total} ${transactionData.currency === 'usd' ? '$' : 'SYP'}%0A`;
            message += `*العنوان:* ${transactionData.address}%0A`;
            message += `*الوقت:* ${transactionData.timestamp}%0A%0A`;
            message += `*رسالة تذكير:* عند تحويل المبلغ سوف يتم اعتماد سعر صرف الدولار كما هو سعر الصرف في البنك المركزي.`;
            
            // إرسال الطلب إلى مجموعة التلجرام باستخدام Webhook
            // ملاحظة: هذا مثال، تحتاج إلى استبدال الرابط برابط Webhook الخاص بك
            const webhookURL = 'https://api.telegram.org/botYOUR_BOT_TOKEN/sendMessage?chat_id=@shamcashusdt1&text=';
            
            // محاكاة إرسال البيانات (لأننا لا نستطيع إجراء طلبات بين المصادر من المتصفح مباشرة)
            // في التطبيق الحقيقي، ستحتاج إلى استخدام خدمة وسيطة أو تطبيق ويب خاص
            setTimeout(function() {
                document.getElementById('loader').style.display = 'none';
                document.getElementById('successMessage').style.display = 'block';
                
                // فتح رابط التلجرام مع نص الرسالة (حل بديل)
                window.open(`https://t.me/share/url?url=&text=${message}`, '_blank');
            }, 2000);
        }
        
        // جعل التطبيق متجاوباً مع الأجهزة المحمولة
        window.addEventListener('resize', function() {
            // تحديث الواجهة عند تغيير حجم الشاشة
        });
    </script>
</body>
</html>
