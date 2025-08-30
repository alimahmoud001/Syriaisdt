<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام بيع وشراء USDT - شام كاش</title>
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
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
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 20px;
            text-align: center;
            border-radius: 8px 8px 0 0;
            margin-bottom: 20px;
        }
        
        h1, h2, h3 {
            margin-bottom: 15px;
        }
        
        .card {
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            padding: 20px;
            margin-bottom: 20px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        
        input[type="number"],
        input[type="text"],
        select {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
        }
        
        button {
            background-color: var(--secondary-color);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            width: 100%;
            transition: background-color 0.3s;
        }
        
        button:hover {
            background-color: #2980b9;
        }
        
        .result {
            display: none;
            margin-top: 20px;
            padding: 15px;
            background-color: #f8f9fa;
            border-radius: 4px;
            border-right: 4px solid var(--secondary-color);
        }
        
        .info-box {
            background-color: #e8f4fd;
            border-radius: 4px;
            padding: 15px;
            margin-bottom: 20px;
            border-right: 4px solid var(--secondary-color);
        }
        
        .address-box {
            background-color: #f9f9f9;
            padding: 10px;
            border-radius: 4px;
            margin: 10px 0;
            word-break: break-all;
            font-family: monospace;
        }
        
        .tab {
            overflow: hidden;
            border: 1px solid #ccc;
            background-color: #f1f1f1;
            border-radius: 4px 4px 0 0;
        }
        
        .tab button {
            background-color: inherit;
            float: right;
            border: none;
            outline: none;
            cursor: pointer;
            padding: 14px 16px;
            transition: 0.3s;
            color: var(--dark-color);
            width: 50%;
        }
        
        .tab button:hover {
            background-color: #ddd;
        }
        
        .tab button.active {
            background-color: var(--secondary-color);
            color: white;
        }
        
        .tabcontent {
            display: none;
            padding: 20px;
            border: 1px solid #ccc;
            border-top: none;
            border-radius: 0 0 4px 4px;
            background-color: white;
        }
        
        .commission-notice {
            font-size: 14px;
            color: #666;
            margin-top: 5px;
        }
        
        footer {
            text-align: center;
            margin-top: 30px;
            color: #666;
            font-size: 14px;
        }
        
        .telegram-link {
            color: var(--secondary-color);
            text-decoration: none;
        }
        
        .telegram-link:hover {
            text-decoration: underline;
        }
        
        .final-notice {
            margin-top: 20px;
            padding: 10px;
            background-color: #fff3cd;
            border-radius: 4px;
            border-right: 4px solid #ffc107;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>نظام بيع وشراء USDT عبر شام كاش</h1>
        </header>
        
        <div class="card">
            <div class="info-box">
                <h3>معلومات مهمة</h3>
                <p>سعر صرف الدولار: <strong>11000</strong> ليرة سورية</p>
                <p>العمولة: 1$ + 0.5% من المبلغ الإجمالي</p>
            </div>
            
            <div class="tab">
                <button class="tablinks active" onclick="openTab(event, 'Buy')">شراء USDT</button>
                <button class="tablinks" onclick="openTab(event, 'Sell')">بيع USDT</button>
            </div>
            
            <div id="Buy" class="tabcontent" style="display: block;">
                <h3>شراء USDT</h3>
                <form id="buyForm">
                    <div class="form-group">
                        <label for="buyAmount">المبلغ المراد شراءه (USDT):</label>
                        <input type="number" id="buyAmount" step="0.01" min="1" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="networkAddress">عنوان الشبكة (BEP20 فقط):</label>
                        <input type="text" id="networkAddress" required>
                    </div>
                    
                    <div class="form-group">
                        <label>طريقة الدفع:</label>
                        <select id="buyCurrency">
                            <option value="usd">الدولار الأمريكي ($)</option>
                            <option value="syp">الليرة السورية (SYP)</option>
                        </select>
                    </div>
                    
                    <button type="submit">احسب المبلغ المستحق</button>
                </form>
                
                <div id="buyResult" class="result">
                    <h3>تفاصيل عملية الشراء</h3>
                    <p>المبلغ المراد شراءه: <span id="resultBuyAmount"></span> USDT</p>
                    <p>العمولة: <span id="buyCommission"></span></p>
                    <p>المبلغ الإجمالي المستحق: <span id="totalBuyAmount"></span></p>
                    
                    <div class="info-box">
                        <p>يرجى تحويل المبلغ إلى عنوان شام كاش التالي:</p>
                        <div class="address-box">be456e0ea9392db4d68a7093ee317bc8</div>
                        <p>بعد التحويل، يرجى إرسال صورة لقطة الشاشة إلى الدعم على Telegram: 
                            <a href="https://t.me/ali0619000" class="telegram-link" target="_blank">@ali0619000</a>
                        </p>
                    </div>
                </div>
            </div>
            
            <div id="Sell" class="tabcontent">
                <h3>بيع USDT</h3>
                <form id="sellForm">
                    <div class="form-group">
                        <label for="sellAmount">المبلغ المراد بيعه (USDT):</label>
                        <input type="number" id="sellAmount" step="0.01" min="1" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="shamCashAddress">عنوان شام كاش الخاص بك:</label>
                        <input type="text" id="shamCashAddress" required>
                    </div>
                    
                    <div class="form-group">
                        <label>طريقة الاستلام:</label>
                        <select id="receiveCurrency">
                            <option value="syp">الليرة السورية (SYP)</option>
                            <option value="usd">الدولار الأمريكي ($)</option>
                        </select>
                    </div>
                    
                    <button type="submit">احسب المبلغ المستلم</button>
                </form>
                
                <div id="sellResult" class="result">
                    <h3>تفاصيل عملية البيع</h3>
                    <p>المبلغ المراد بيعه: <span id="resultSellAmount"></span> USDT</p>
                    <p>العمولة: <span id="sellCommission"></span></p>
                    <p>المبلغ الإجمالي المستلم: <span id="totalSellAmount"></span></p>
                    
                    <div class="info-box">
                        <p>يرجى تحويل USDT إلى العنوان التالي:</p>
                        <div class="address-box">0x2F1A184B6abBb49De547D539eDC3b5eAdc3E01F9</div>
                        <p>بعد التحويل، يرجى إرسال صورة لقطة الشاشة إلى الدعم على Telegram: 
                            <a href="https://t.me/ali0619000" class="telegram-link" target="_blank">@ali0619000</a>
                        </p>
                        <p>سيتم إرسال المبلغ خلال عدة دقائق بعد التأكد من التحويل.</p>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="final-notice">
            عند تحويل المبلغ سوف يتم اعتماد سعر صرف الدولار كما هو سعر الصرف في البنك المركزي.
        </div>
        
        <footer>
            <p>لأي استفسار، يرجى التواصل مع الدعم على Telegram: <a href="https://t.me/ali0619000" class="telegram-link" target="_blank">@ali0619000</a></p>
            <p>سيتم إرسال التفاصيل إلى مجموعة Telegram: <a href="https://t.me/shamcashusdt1" class="telegram-link" target="_blank">@shamcashusdt1</a></p>
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
        
        // معالجة نموذج الشراء
        document.getElementById('buyForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const amount = parseFloat(document.getElementById('buyAmount').value);
            const currency = document.getElementById('buyCurrency').value;
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
            
            // هنا يمكن إضافة كود لإرسال البيانات إلى مجموعة Telegram (يتطلب backend)
            sendToTelegram('شراء', amount, currency, commission, totalAmount);
        });
        
        // معالجة نموذج البيع
        document.getElementById('sellForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const amount = parseFloat(document.getElementById('sellAmount').value);
            const currency = document.getElementById('receiveCurrency').value;
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
            
            // هنا يمكن إضافة كود لإرسال البيانات إلى مجموعة Telegram (يتطلب backend)
            sendToTelegram('بيع', amount, currency, commission, netAmount);
        });
        
        // دالة محاكاة لإرسال البيانات إلى Telegram (التنفيذ الفعلي يتطلب backend)
        function sendToTelegram(type, amount, currency, commission, total) {
            console.log("إرسال البيانات إلى Telegram:");
            console.log("النوع: " + type);
            console.log("المبلغ: " + amount + " USDT");
            console.log("العملة: " + currency);
            console.log("العمولة: " + commission + " $");
            console.log("المبلغ الإجمالي: " + total + (currency === 'syp' ? ' SYP' : ' $'));
            
            // في التطبيق الحقيقي، هنا سيتم استخدام fetch أو axios لإرسال البيانات إلى backend
            // الذي بدوره سيرسلها إلى مجموعة Telegram باستخدام bot API
        }
    </script>
</body>
</html>
