<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام تحويل USDT في سورية</title>
    <style>
        * {
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #0d7e0d);
            color: #333;
            margin: 0;
            padding: 20px;
            min-height: 100vh;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            padding: 30px;
            position: relative;
            overflow: hidden;
        }
        
        .container::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 5px;
            background: linear-gradient(90deg, #1a2a6c, #b21f1f, #0d7e0d);
        }
        
        h1 {
            text-align: center;
            color: #1a2a6c;
            margin-top: 0;
            padding-bottom: 15px;
            border-bottom: 2px solid #eee;
        }
        
        .step {
            display: none;
            animation: fadeIn 0.5s ease-in;
        }
        
        .active {
            display: block;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #1a2a6c;
        }
        
        input, select, textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: border 0.3s;
        }
        
        input:focus, select:focus, textarea:focus {
            border-color: #1a2a6c;
            outline: none;
        }
        
        .btn-container {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
        }
        
        button {
            padding: 12px 25px;
            background: linear-gradient(to right, #1a2a6c, #b21f1f);
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
        }
        
        button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3);
        }
        
        button:disabled {
            background: #ccc;
            cursor: not-allowed;
        }
        
        .btn-next {
            background: linear-gradient(to right, #0d7e0d, #1a2a6c);
        }
        
        .summary {
            background-color: #f9f9f9;
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
            border-left: 5px solid #1a2a6c;
        }
        
        .summary h3 {
            margin-top: 0;
            color: #1a2a6c;
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
        }
        
        .summary-item {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            padding-bottom: 10px;
            border-bottom: 1px dashed #ddd;
        }
        
        .note {
            background-color: #fff8e1;
            border-radius: 8px;
            padding: 15px;
            margin-top: 20px;
            border-left: 4px solid #ffc107;
            font-size: 14px;
        }
        
        .payment-details {
            background-color: #e8f5e9;
            border-radius: 8px;
            padding: 15px;
            margin: 15px 0;
            border-left: 4px solid #4caf50;
        }
        
        .success {
            text-align: center;
            padding: 30px;
        }
        
        .success-icon {
            font-size: 60px;
            color: #4caf50;
            margin-bottom: 20px;
        }
        
        .network-fee {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 10px;
            padding: 10px;
            background-color: #f5f5f5;
            border-radius: 8px;
        }
        
        .commission-calculator {
            background: #e3f2fd;
            padding: 15px;
            border-radius: 8px;
            margin: 15px 0;
        }
        
        .commission-result {
            font-weight: bold;
            color: #d32f2f;
            margin-top: 10px;
            padding: 10px;
            background: white;
            border-radius: 8px;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @media (max-width: 600px) {
            .container {
                padding: 15px;
            }
            
            .btn-container {
                flex-direction: column;
                gap: 10px;
            }
            
            button {
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>نظام تحويل USDT في سورية</h1>
        
        <div id="step1" class="step active">
            <h2>الخطوة 1: معلومات المستخدم</h2>
            <div class="form-group">
                <label for="fullName">الاسم الثلاثي</label>
                <input type="text" id="fullName" placeholder="أدخل اسمك الثلاثي">
            </div>
            <div class="form-group">
                <label for="phone">رقم الهاتف</label>
                <input type="tel" id="phone" placeholder="أدخل رقم هاتفك">
            </div>
            <div class="form-group">
                <label for="city">المدينة</label>
                <input type="text" id="city" placeholder="أدخل مدينتك">
            </div>
            <div class="btn-container">
                <button id="nextToStep2" class="btn-next">التالي</button>
            </div>
        </div>
        
        <div id="step2" class="step">
            <h2>الخطوة 2: نوع العملية</h2>
            <div class="form-group">
                <label>ما الذي ترغب في القيام به؟</label>
                <div style="display: flex; gap: 15px; margin-top: 15px;">
                    <button id="buyBtn" style="flex: 1; background: linear-gradient(to right, #0d7e0d, #2e7d32);">شراء USDT</button>
                    <button id="sellBtn" style="flex: 1; background: linear-gradient(to right, #b71c1c, #d32f2f);">بيع USDT</button>
                </div>
            </div>
            <div class="btn-container">
                <button id="backToStep1">السابق</button>
            </div>
        </div>
        
        <div id="step3Buy" class="step">
            <h2>الخطوة 3: تفاصيل الشراء</h2>
            <div class="form-group">
                <label for="buyAmount">الكمية المطلوبة (USDT)</label>
                <input type="number" id="buyAmount" placeholder="أدخل الكمية المطلوبة">
            </div>
            <div class="form-group">
                <label for="buyNetwork">اختر شبكة التحويل</label>
                <select id="buyNetwork">
                    <option value="">-- اختر شبكة --</option>
                    <option value="bep20">BEP20</option>
                    <option value="trc20">TRC20</option>
                    <option value="erc20">ERC20</option>
                    <option value="binance">Binance Pay</option>
                </select>
            </div>
            <div class="form-group">
                <label for="buyAddress">عنوان المحفظة</label>
                <input type="text" id="buyAddress" placeholder="أدخل عنوان محفظتك">
            </div>
            <div class="form-group">
                <label for="buyNotes">ملاحظات (اختياري)</label>
                <textarea id="buyNotes" rows="3" placeholder="أي ملاحظات إضافية"></textarea>
            </div>
            <div class="form-group">
                <label for="buyMethod">طريقة الدفع</label>
                <select id="buyMethod">
                    <option value="">-- اختر طريقة الدفع --</option>
                    <option value="sham">شام كاش</option>
                    <option value="bemo">بنك بيمو</option>
                    <option value="syr">سيريتل كاش</option>
                    <option value="pyramid">حوالة الهرم</option>
                </select>
            </div>
            
            <div id="paymentDetails" class="payment-details" style="display: none;">
                <h3>تفاصيل الدفع</h3>
                <div id="shamDetails" style="display: none;">
                    <p><strong>شام كاش:</strong></p>
                    <p>العنوان: be456e0ea9392db4d68a7093ee317bc8</p>
                    <p>رقم الحساب: 5991161126028260</p>
                </div>
                <div id="syrDetails" style="display: none;">
                    <p><strong>سيريتل كاش:</strong></p>
                    <p>العنوان: 0934598967</p>
                </div>
                <div id="pyramidDetails" style="display: none;">
                    <p><strong>حوالة الهرم:</strong></p>
                    <p>الاسم: علي ابراهيم محمود</p>
                    <p>رقم الهاتف: 0934598967</p>
                    <p>المدينة: اللاذقية</p>
                </div>
                <div id="bemoDetails" style="display: none;">
                    <p><strong>بنك بيمو:</strong></p>
                    <p>الاسم: علي ابراهيم محمود</p>
                    <p>رقم الحساب: 060104947910013000000</p>
                </div>
            </div>
            
            <div class="commission-calculator">
                <h3>حساب العمولة</h3>
                <div class="commission-result" id="commissionResult"></div>
            </div>
            
            <div class="btn-container">
                <button id="backToStep2FromBuy">السابق</button>
                <button id="completeBuy">إتمام الشراء</button>
            </div>
        </div>
        
        <div id="step3Sell" class="step">
            <h2>الخطوة 3: تفاصيل البيع</h2>
            <div class="form-group">
                <label for="sellAmount">الكمية المعروضة (USDT)</label>
                <input type="number" id="sellAmount" placeholder="أدخل الكمية المعروضة">
            </div>
            <div class="form-group">
                <label for="receiveMethod">طريقة الاستلام</label>
                <select id="receiveMethod">
                    <option value="">-- اختر طريقة الاستلام --</option>
                    <option value="syr">سيريتل كاش</option>
                    <option value="pyramid">حوالة هرم</option>
                    <option value="bemo">بنك بيمو</option>
                    <option value="sham">شام كاش</option>
                </select>
            </div>
            
            <div id="receiveDetails" style="display: none;">
                <div id="syrReceive" class="form-group" style="display: none;">
                    <label for="syrAccount">رقم حساب سيريتل كاش</label>
                    <input type="text" id="syrAccount" placeholder="أدخل رقم حسابك">
                </div>
                <div id="pyramidReceive" class="form-group" style="display: none;">
                    <label for="pyramidAccount">تفاصيل حوالة الهرم</label>
                    <input type="text" id="pyramidAccount" placeholder="أدخل التفاصيل">
                </div>
                <div id="bemoReceive" class="form-group" style="display: none;">
                    <label for="bemoAccount">رقم الحساب البنكي</label>
                    <input type="text" id="bemoAccount" placeholder="أدخل رقم الحساب">
                </div>
                <div id="shamReceive" class="form-group" style="display: none;">
                    <label for="shamAccount">رقم حساب شام كاش</label>
                    <input type="text" id="shamAccount" placeholder="أدخل رقم الحساب">
                </div>
            </div>
            
            <div class="form-group">
                <label for="sellNetwork">اختر شبكة التحويل</label>
                <select id="sellNetwork">
                    <option value="">-- اختر شبكة --</option>
                    <option value="bep20">BEP20</option>
                    <option value="trc20">TRC20</option>
                    <option value="erc20">ERC20</option>
                    <option value="binance">Binance Pay</option>
                </select>
            </div>
            
            <div id="cryptoAddresses" class="payment-details" style="display: none;">
                <h3>عناوين المحفظة</h3>
                <div id="bep20Address" style="display: none;">
                    <p><strong>BEP20:</strong></p>
                    <p>0x21802218d8d661d66F2C7959347a6382E1cc614F</p>
                </div>
                <div id="trc20Address" style="display: none;">
                    <p><strong>TRC20:</strong></p>
                    <p>TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX</p>
                </div>
                <div id="erc20Address" style="display: none;">
                    <p><strong>ERC20:</strong></p>
                    <p>0x21802218d8d661d66F2C7959347a6382E1cc614F</p>
                </div>
                <div id="binanceAddress" style="display: none;">
                    <p><strong>Binance Pay:</strong></p>
                    <p>969755964</p>
                </div>
            </div>
            
            <div class="form-group">
                <label for="sellNotes">ملاحظات (اختياري)</label>
                <textarea id="sellNotes" rows="3" placeholder="أي ملاحظات إضافية"></textarea>
            </div>
            
            <div class="commission-calculator">
                <h3>حساب العمولة</h3>
                <div class="commission-result" id="sellCommissionResult"></div>
            </div>
            
            <div class="btn-container">
                <button id="backToStep2FromSell">السابق</button>
                <button id="completeSell">إتمام البيع</button>
            </div>
        </div>
        
        <div id="step4" class="step">
            <div class="success">
                <div class="success-icon">✓</div>
                <h2>تم إتمام طلبك بنجاح!</h2>
                <p>تم إرسال تفاصيل طلبك إلى فريق الدعم وسيتم التواصل معك قريباً.</p>
                
                <div class="summary">
                    <h3>تفاصيل الطلب</h3>
                    <div class="summary-item">
                        <span>الاسم:</span>
                        <span id="summaryName"></span>
                    </div>
                    <div class="summary-item">
                        <span>الهاتف:</span>
                        <span id="summaryPhone"></span>
                    </div>
                    <div class="summary-item">
                        <span>المدينة:</span>
                        <span id="summaryCity"></span>
                    </div>
                    <div class="summary-item">
                        <span>نوع العملية:</span>
                        <span id="summaryType"></span>
                    </div>
                    <div class="summary-item">
                        <span>الكمية:</span>
                        <span id="summaryAmount"></span>
                    </div>
                    <div class="summary-item">
                        <span>العمولة:</span>
                        <span id="summaryCommission"></span>
                    </div>
                    <div class="summary-item">
                        <span>الشبكة:</span>
                        <span id="summaryNetwork"></span>
                    </div>
                    <div class="summary-item">
                        <span>طريقة الدفع/الاستلام:</span>
                        <span id="summaryMethod"></span>
                    </div>
                    <div class="summary-item">
                        <span>المبلغ الصافي:</span>
                        <span id="summaryNetAmount"></span>
                    </div>
                </div>
                
                <div class="note">
                    <p><strong>ملاحظة:</strong> عمولة التسديد على طرق التحويل المختلفة بالليرة السورية تقع على المستخدم كما تحددها هذه الجهات.</p>
                </div>
                
                <p>تم إرسال الطلب إلى البريد الإلكتروني: alimahmoud001a@gmail.com</p>
                
                <div class="btn-container">
                    <button id="sendEmail">إرسال الطلب عبر البريد</button>
                </div>
            </div>
            
            <div class="btn-container">
                <button id="newOrder">طلب جديد</button>
            </div>
        </div>
    </div>

    <script>
        // التحكم في تدفق الخطوات
        const step1 = document.getElementById('step1');
        const step2 = document.getElementById('step2');
        const step3Buy = document.getElementById('step3Buy');
        const step3Sell = document.getElementById('step3Sell');
        const step4 = document.getElementById('step4');
        
        const nextToStep2 = document.getElementById('nextToStep2');
        const backToStep1 = document.getElementById('backToStep1');
        const buyBtn = document.getElementById('buyBtn');
        const sellBtn = document.getElementById('sellBtn');
        const backToStep2FromBuy = document.getElementById('backToStep2FromBuy');
        const backToStep2FromSell = document.getElementById('backToStep2FromSell');
        const completeBuy = document.getElementById('completeBuy');
        const completeSell = document.getElementById('completeSell');
        const newOrder = document.getElementById('newOrder');
        const sendEmail = document.getElementById('sendEmail');
        
        // تفاصيل الشراء
        const buyMethod = document.getElementById('buyMethod');
        const paymentDetails = document.getElementById('paymentDetails');
        const shamDetails = document.getElementById('shamDetails');
        const syrDetails = document.getElementById('syrDetails');
        const pyramidDetails = document.getElementById('pyramidDetails');
        const bemoDetails = document.getElementById('bemoDetails');
        
        // تفاصيل البيع
        const receiveMethod = document.getElementById('receiveMethod');
        const receiveDetails = document.getElementById('receiveDetails');
        const syrReceive = document.getElementById('syrReceive');
        const pyramidReceive = document.getElementById('pyramidReceive');
        const bemoReceive = document.getElementById('bemoReceive');
        const shamReceive = document.getElementById('shamReceive');
        
        const sellNetwork = document.getElementById('sellNetwork');
        const cryptoAddresses = document.getElementById('cryptoAddresses');
        const bep20Address = document.getElementById('bep20Address');
        const trc20Address = document.getElementById('trc20Address');
        const erc20Address = document.getElementById('erc20Address');
        const binanceAddress = document.getElementById('binanceAddress');
        
        // عناصر حساب العمولة
        const buyAmount = document.getElementById('buyAmount');
        const buyNetwork = document.getElementById('buyNetwork');
        const commissionResult = document.getElementById('commissionResult');
        
        const sellAmount = document.getElementById('sellAmount');
        const sellCommissionResult = document.getElementById('sellCommissionResult');
        
        // عناصر الملخص
        const summaryName = document.getElementById('summaryName');
        const summaryPhone = document.getElementById('summaryPhone');
        const summaryCity = document.getElementById('summaryCity');
        const summaryType = document.getElementById('summaryType');
        const summaryAmount = document.getElementById('summaryAmount');
        const summaryCommission = document.getElementById('summaryCommission');
        const summaryNetwork = document.getElementById('summaryNetwork');
        const summaryMethod = document.getElementById('summaryMethod');
        const summaryNetAmount = document.getElementById('summaryNetAmount');
        
        // رسوم الشبكات
        const networkFees = {
            'bep20': 0.15,
            'trc20': 2.00,
            'erc20': 0.30,
            'binance': 0.00
        };
        
        // الانتقال بين الخطوات
        nextToStep2.addEventListener('click', () => {
            if (validateStep1()) {
                step1.classList.remove('active');
                step2.classList.add('active');
            }
        });
        
        backToStep1.addEventListener('click', () => {
            step2.classList.remove('active');
            step1.classList.add('active');
        });
        
        buyBtn.addEventListener('click', () => {
            step2.classList.remove('active');
            step3Buy.classList.add('active');
        });
        
        sellBtn.addEventListener('click', () => {
            step2.classList.remove('active');
            step3Sell.classList.add('active');
        });
        
        backToStep2FromBuy.addEventListener('click', () => {
            step3Buy.classList.remove('active');
            step2.classList.add('active');
        });
        
        backToStep2FromSell.addEventListener('click', () => {
            step3Sell.classList.remove('active');
            step2.classList.add('active');
        });
        
        completeBuy.addEventListener('click', () => {
            if (validateBuyForm()) {
                calculateCommission('buy');
                prepareSummary('buy');
                step3Buy.classList.remove('active');
                step4.classList.add('active');
            }
        });
        
        completeSell.addEventListener('click', () => {
            if (validateSellForm()) {
                calculateCommission('sell');
                prepareSummary('sell');
                step3Sell.classList.remove('active');
                step4.classList.add('active');
            }
        });
        
        newOrder.addEventListener('click', () => {
            resetForm();
            step4.classList.remove('active');
            step1.classList.add('active');
        });
        
        sendEmail.addEventListener('click', () => {
            const subject = "طلب تحويل USDT جديد";
            const body = createEmailBody();
            const mailtoLink = `mailto:alimahmoud001a@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
            window.location.href = mailtoLink;
        });
        
        // عرض تفاصيل الدفع للشراء
        buyMethod.addEventListener('change', () => {
            const method = buyMethod.value;
            paymentDetails.style.display = 'block';
            shamDetails.style.display = method === 'sham' ? 'block' : 'none';
            syrDetails.style.display = method === 'syr' ? 'block' : 'none';
            pyramidDetails.style.display = method === 'pyramid' ? 'block' : 'none';
            bemoDetails.style.display = method === 'bemo' ? 'block' : 'none';
        });
        
        // عرض تفاصيل الاستلام للبيع
        receiveMethod.addEventListener('change', () => {
            const method = receiveMethod.value;
            receiveDetails.style.display = 'block';
            syrReceive.style.display = method === 'syr' ? 'block' : 'none';
            pyramidReceive.style.display = method === 'pyramid' ? 'block' : 'none';
            bemoReceive.style.display = method === 'bemo' ? 'block' : 'none';
            shamReceive.style.display = method === 'sham' ? 'block' : 'none';
        });
        
        // عرض عناوين المحفظة للبيع
        sellNetwork.addEventListener('change', () => {
            const network = sellNetwork.value;
            cryptoAddresses.style.display = 'block';
            bep20Address.style.display = network === 'bep20' ? 'block' : 'none';
            trc20Address.style.display = network === 'trc20' ? 'block' : 'none';
            erc20Address.style.display = network === 'erc20' ? 'block' : 'none';
            binanceAddress.style.display = network === 'binance' ? 'block' : 'none';
        });
        
        // حساب العمولة تلقائيًا أثناء الكتابة
        buyAmount.addEventListener('input', () => calculateCommission('buy'));
        buyNetwork.addEventListener('change', () => calculateCommission('buy'));
        
        sellAmount.addEventListener('input', () => calculateCommission('sell'));
        
        // التحقق من صحة الخطوة 1
        function validateStep1() {
            const fullName = document.getElementById('fullName').value;
            const phone = document.getElementById('phone').value;
            const city = document.getElementById('city').value;
            
            if (!fullName || !phone || !city) {
                alert('يرجى ملء جميع الحقول في الخطوة الأولى');
                return false;
            }
            return true;
        }
        
        // التحقق من صحة نموذج الشراء
        function validateBuyForm() {
            const amount = buyAmount.value;
            const network = buyNetwork.value;
            const address = document.getElementById('buyAddress').value;
            const method = buyMethod.value;
            
            if (!amount || amount <= 0 || !network || !address || !method) {
                alert('يرجى ملء جميع الحقول المطلوبة في نموذج الشراء');
                return false;
            }
            return true;
        }
        
        // التحقق من صحة نموذج البيع
        function validateSellForm() {
            const amount = sellAmount.value;
            const receive = receiveMethod.value;
            const network = sellNetwork.value;
            
            if (!amount || amount <= 0 || !receive || !network) {
                alert('يرجى ملء جميع الحقول المطلوبة في نموذج البيع');
                return false;
            }
            
            // التحقق من تفاصيل الاستلام بناءً على الطريقة المختارة
            if (receive === 'syr' && !document.getElementById('syrAccount').value) {
                alert('يرجى إدخال رقم حساب سيريتل كاش');
                return false;
            }
            if (receive === 'pyramid' && !document.getElementById('pyramidAccount').value) {
                alert('يرجى إدخال تفاصيل حوالة الهرم');
                return false;
            }
            if (receive === 'bemo' && !document.getElementById('bemoAccount').value) {
                alert('يرجى إدخال رقم الحساب البنكي');
                return false;
            }
            if (receive === 'sham' && !document.getElementById('shamAccount').value) {
                alert('يرجى إدخال رقم حساب شام كاش');
                return false;
            }
            
            return true;
        }
        
        // حساب العمولة
        function calculateCommission(type) {
            let amount, network, fee, commission;
            
            if (type === 'buy') {
                amount = parseFloat(buyAmount.value) || 0;
                network = buyNetwork.value;
                
                if (amount <= 0) {
                    commissionResult.textContent = 'أدخل كمية صحيحة';
                    return;
                }
                
                // حساب عمولة التحويل
                if (amount < 100) {
                    commission = 1.65;
                } else if (amount <= 5000) {
                    commission = amount * 0.0165;
                } else {
                    commission = amount * 0.0005;
                }
                
                // رسوم الشبكة
                fee = network ? networkFees[network] : 0;
                
                // إجمالي العمولة
                const totalCommission = commission + fee;
                const netAmount = amount + totalCommission;
                
                commissionResult.innerHTML = `
                    <div>عمولة التحويل: ${commission.toFixed(2)} USDT</div>
                    <div>عمولة الشبكة: ${fee.toFixed(2)} USDT</div>
                    <div>الإجمالي: ${totalCommission.toFixed(2)} USDT</div>
                    <div>المبلغ الإجمالي: ${netAmount.toFixed(2)} USDT</div>
                `;
                
            } else {
                amount = parseFloat(sellAmount.value) || 0;
                
                if (amount <= 0) {
                    sellCommissionResult.textContent = 'أدخل كمية صحيحة';
                    return;
                }
                
                // حساب عمولة التحويل
                if (amount < 100) {
                    commission = 1.65;
                } else if (amount <= 5000) {
                    commission = amount * 0.0165;
                } else {
                    commission = amount * 0.0005;
                }
                
                // رسوم الشبكة (يتم خصمها من المبلغ)
                fee = networkFees[sellNetwork.value] || 0;
                
                // إجمالي العمولة
                const totalCommission = commission + fee;
                const netAmount = amount - totalCommission;
                
                sellCommissionResult.innerHTML = `
                    <div>عمولة التحويل: ${commission.toFixed(2)} USDT</div>
                    <div>عمولة الشبكة: ${fee.toFixed(2)} USDT</div>
                    <div>الإجمالي: ${totalCommission.toFixed(2)} USDT</div>
                    <div>المبلغ الصافي: ${netAmount.toFixed(2)} USDT</div>
                `;
            }
        }
        
        // إعداد ملخص الطلب
        function prepareSummary(type) {
            // معلومات المستخدم
            summaryName.textContent = document.getElementById('fullName').value;
            summaryPhone.textContent = document.getElementById('phone').value;
            summaryCity.textContent = document.getElementById('city').value;
            
            if (type === 'buy') {
                const amount = parseFloat(buyAmount.value);
                const network = buyNetwork.options[buyNetwork.selectedIndex].text;
                const method = buyMethod.options[buyMethod.selectedIndex].text;
                
                // حساب العمولة
                let commission;
                if (amount < 100) {
                    commission = 1.65;
                } else if (amount <= 5000) {
                    commission = amount * 0.0165;
                } else {
                    commission = amount * 0.0005;
                }
                
                const fee = networkFees[buyNetwork.value] || 0;
                const totalCommission = commission + fee;
                const netAmount = amount + totalCommission;
                
                summaryType.textContent = 'شراء USDT';
                summaryAmount.textContent = amount.toFixed(2) + ' USDT';
                summaryCommission.textContent = totalCommission.toFixed(2) + ' USDT';
                summaryNetwork.textContent = network;
                summaryMethod.textContent = method;
                summaryNetAmount.textContent = netAmount.toFixed(2) + ' USDT';
                
            } else {
                const amount = parseFloat(sellAmount.value);
                const method = receiveMethod.options[receiveMethod.selectedIndex].text;
                const network = sellNetwork.options[sellNetwork.selectedIndex].text;
                
                // حساب العمولة
                let commission;
                if (amount < 100) {
                    commission = 1.65;
                } else if (amount <= 5000) {
                    commission = amount * 0.0165;
                } else {
                    commission = amount * 0.0005;
                }
                
                const fee = networkFees[sellNetwork.value] || 0;
                const totalCommission = commission + fee;
                const netAmount = amount - totalCommission;
                
                summaryType.textContent = 'بيع USDT';
                summaryAmount.textContent = amount.toFixed(2) + ' USDT';
                summaryCommission.textContent = totalCommission.toFixed(2) + ' USDT';
                summaryNetwork.textContent = network;
                summaryMethod.textContent = method;
                summaryNetAmount.textContent = netAmount.toFixed(2) + ' USDT';
            }
        }
        
        // إنشاء محتوى البريد الإلكتروني
        function createEmailBody() {
            const name = document.getElementById('fullName').value;
            const phone = document.getElementById('phone').value;
            const city = document.getElementById('city').value;
            const type = summaryType.textContent;
            const amount = summaryAmount.textContent;
            const commission = summaryCommission.textContent;
            const network = summaryNetwork.textContent;
            const method = summaryMethod.textContent;
            const netAmount = summaryNetAmount.textContent;
            
            return `طلب تحويل USDT جديد
            
الاسم: ${name}
الهاتف: ${phone}
المدينة: ${city}
نوع العملية: ${type}
الكمية: ${amount}
العمولة: ${commission}
الشبكة: ${network}
طريقة الدفع/الاستلام: ${method}
المبلغ الصافي: ${netAmount}

تم إرسال هذا الطلب من نظام تحويل USDT في سورية
`;
        }
        
        // إعادة تعيين النموذج
        function resetForm() {
            document.getElementById('fullName').value = '';
            document.getElementById('phone').value = '';
            document.getElementById('city').value = '';
            document.getElementById('buyAmount').value = '';
            document.getElementById('buyAddress').value = '';
            document.getElementById('buyNotes').value = '';
            document.getElementById('sellAmount').value = '';
            document.getElementById('syrAccount').value = '';
            document.getElementById('pyramidAccount').value = '';
            document.getElementById('bemoAccount').value = '';
            document.getElementById('shamAccount').value = '';
            document.getElementById('sellNotes').value = '';
            
            paymentDetails.style.display = 'none';
            receiveDetails.style.display = 'none';
            cryptoAddresses.style.display = 'none';
            commissionResult.textContent = '';
            sellCommissionResult.textContent = '';
        }
    </script>
</body>
</html>
