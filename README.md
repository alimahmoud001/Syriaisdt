<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>خدمة تحويل العملات الرقمية (USDT) في سوريا</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f7f6;
            color: #333;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            direction: rtl;
            text-align: right;
        }
        .container {
            max-width: 800px;
            margin: 30px auto;
            background: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }
        h1, h2 {
            color: #0056b3;
            text-align: center;
            margin-bottom: 25px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #555;
        }
        input[type="text"],
        input[type="tel"],
        input[type="number"],
        textarea,
        select {
            width: calc(100% - 20px);
            padding: 12px;
            margin-bottom: 20px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
            box-sizing: border-box;
        }
        input[type="radio"] {
            margin-left: 10px;
            margin-right: 5px;
        }
        .radio-group label {
            display: inline-block;
            margin-left: 15px;
            font-weight: normal;
        }
        button {
            background-color: #007bff;
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 18px;
            display: block;
            width: 100%;
            margin-top: 20px;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #0056b3;
        }
        .section {
            border-top: 1px solid #eee;
            padding-top: 25px;
            margin-top: 25px;
        }
        #output {
            background-color: #e9f5ee;
            border: 1px solid #c3e6cb;
            padding: 15px;
            margin-top: 30px;
            border-radius: 8px;
            white-space: pre-wrap;
            word-wrap: break-word;
        }
        .hidden {
            display: none;
        }
        .note {
            background-color: #fff3cd;
            border: 1px solid #ffeeba;
            padding: 10px;
            margin-top: 20px;
            border-radius: 5px;
            color: #856404;
            font-size: 14px;
        }
        .instruction-box {
            background-color: #e6f7ff;
            border: 1px solid #91d5ff;
            padding: 15px;
            margin-top: 15px;
            border-radius: 5px;
            font-size: 15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>خدمة تحويل العملات الرقمية (USDT)</h1>
        <h2>مرحباً بك في خدمة تحويل USDT في سوريا</h2>

        <div id="mainForm">
            <div class="section">
                <h2>معلوماتك الشخصية</h2>
                <label for="fullName">الاسم الثلاثي:</label>
                <input type="text" id="fullName" name="fullName" required>

                <label for="phoneNumber">رقم الهاتف:</label>
                <input type="tel" id="phoneNumber" name="phoneNumber" required>

                <label for="city">المدينة:</label>
                <input type="text" id="city" name="city" required>
            </div>

            <div class="section">
                <h2>ما الذي ترغب بفعله؟</h2>
                <div class="radio-group">
                    <input type="radio" id="buy" name="transactionType" value="buy" onchange="showTransactionFields()">
                    <label for="buy">شراء USDT</label>

                    <input type="radio" id="sell" name="transactionType" value="sell" onchange="showTransactionFields()">
                    <label for="sell">بيع USDT</label>
                </div>

                <div id="buyFields" class="hidden">
                    <label for="usdtQuantity">الكمية المطلوبة (USDT):</label>
                    <input type="number" id="usdtQuantity" name="usdtQuantity" step="0.01" min="1" required>

                    <label for="network">اختر الشبكة (التي ستستقبل عليها USDT):</label>
                    <select id="network" name="network" required>
                        <option value="">اختر شبكة</option>
                        <option value="bep20">BEP20</option>
                        <option value="trc20">TRC20</option>
                        <option value="erc20">ERC20</option>
                        <option value="binancepay">Binance Pay</option>
                    </select>

                    <label for="walletAddress">عنوان المحفظة (الذي ستستقبل عليه USDT):</label>
                    <input type="text" id="walletAddress" name="walletAddress" required>

                    <label for="buyPaymentMethod">طريقة الدفع (بالليرة السورية لشراء USDT):</label>
                    <select id="buyPaymentMethod" name="buyPaymentMethod" onchange="displayBuyPaymentDetails()" required>
                        <option value="">اختر طريقة الدفع</option>
                        <option value="syriatelCash">سيريتل كاش</option>
                        <option value="haramTransfer">حوالة الهرم</option>
                        <option value="bemoBank">بنك بيمو</option>
                        <option value="shamCash">شام كاش</option>
                    </select>
                    <div id="buyPaymentDetailsOutput" class="instruction-box hidden"></div>

                    <label for="buyNote">ملاحظة (اختياري):</label>
                    <textarea id="buyNote" name="buyNote" rows="3"></textarea>
                </div>

                <div id="sellFields" class="hidden">
                    <label for="sellQuantity">الكمية التي تريد بيعها (USDT):</label>
                    <input type="number" id="sellQuantity" name="sellQuantity" step="0.01" min="1" required>

                    <label for="sellPaymentMethod">اختر طريقة استلام المبلغ (الليرة السورية):</label>
                    <select id="sellPaymentMethod" name="sellPaymentMethod" required>
                        <option value="">اختر طريقة الاستلام</option>
                        <option value="syriatelCash">سيريتل كاش</option>
                        <option value="haramTransfer">حوالة الهرم</option>
                        <option value="bemoBank">بنك بيمو</option>
                        <option value="shamCash">شام كاش</option>
                    </select>

                    <label for="sendCryptoNetwork">اختر شبكة إرسال USDT إلينا:</label>
                    <select id="sendCryptoNetwork" name="sendCryptoNetwork" onchange="displaySellCryptoAddress()" required>
                        <option value="">اختر شبكة</option>
                        <option value="bep20">BEP20</option>
                        <option value="trc20">TRC20</option>
                        <option value="erc20">ERC20</option>
                        <option value="binancepay">Binance Pay ID</option>
                    </select>
                    <div id="sellCryptoAddressOutput" class="instruction-box hidden"></div>
                    <p class="note">يرجى التأكد من اختيار الشبكة الصحيحة عند الإرسال لتجنب فقدان أموالك.</p>

                    <label for="sellNote">ملاحظة (اختياري):</label>
                    <textarea id="sellNote" name="sellNote" rows="3"></textarea>
                </div>
            </div>

            <button onclick="submitOrder()">تأكيد وإرسال الطلب</button>
        </div>

        <div id="output" class="hidden"></div>
    </div>

    <script>
        const exchangeRate = 14500; // مثال: سعر صرف 1 USDT = 14500 ليرة سورية (يمكن تحديثه)
        const syriatelCashNumber = '0934598967';
        const shamCashAccount = '5991161126028260';

        const cryptoAddresses = {
            bep20: '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            trc20: 'TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX',
            erc20: '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            binancepay: '969755964'
        };

        function showTransactionFields() {
            document.getElementById('buyFields').classList.add('hidden');
            document.getElementById('sellFields').classList.add('hidden');
            const transactionType = document.querySelector('input[name="transactionType"]:checked').value;
            if (transactionType === 'buy') {
                document.getElementById('buyFields').classList.remove('hidden');
            } else if (transactionType === 'sell') {
                document.getElementById('sellFields').classList.remove('hidden');
            }
        }

        function displayBuyPaymentDetails() {
            const buyPaymentMethod = document.getElementById('buyPaymentMethod').value;
            const buyPaymentDetailsOutput = document.getElementById('buyPaymentDetailsOutput');
            buyPaymentDetailsOutput.classList.remove('hidden');

            let outputHtml = '';
            switch (buyPaymentMethod) {
                case 'syriatelCash':
                    outputHtml = `<p><strong>للدفع عبر سيريتل كاش:</strong></p>
                                  <p>يرجى تحويل المبلغ إلى الرقم: <strong>${syriatelCashNumber}</strong></p>
                                  <p>يرجى إرسال لقطة شاشة لعملية التحويل بعد إتمامها.</p>`;
                    break;
                case 'haramTransfer':
                    outputHtml = `<p><strong>للدفع عبر حوالة الهرم:</strong></p>
                                  <p>يرجى إرسال حوالة باسم:</p>
                                  <ul>
                                      <li><strong>الاسم:</strong> علي ابراهيم محمود</li>
                                      <li><strong>رقم الهاتف:</strong> 0934598967</li>
                                      <li><strong>المدينة:</strong> اللاذقية</li>
                                  </ul>
                                  <p>يرجى إرسال صورة عن وصل الحوالة بعد إتمامها.</p>`;
                    break;
                case 'bemoBank':
                    outputHtml = `<p><strong>للدفع عبر بنك بيمو:</strong></p>
                                  <p>يرجى التحويل إلى الحساب البنكي التالي:</p>
                                  <ul>
                                      <li><strong>الاسم:</strong> علي ابراهيم محمود</li>
                                      <li><strong>رقم الحساب:</strong> 060104947910013000000</li>
                                  </ul>
                                  <p>يرجى إرسال صورة عن إشعار التحويل بعد إتمامه.</p>`;
                    break;
                case 'shamCash':
                    outputHtml = `<p><strong>للدفع عبر شام كاش:</strong></p>
                                  <p>يرجى تحويل المبلغ إلى الرقم: <strong>${shamCashAccount}</strong></p>
                                  <p>يرجى إرسال لقطة شاشة لعملية التحويل بعد إتمامها.</p>`;
                    break;
                default:
                    outputHtml = '';
                    buyPaymentDetailsOutput.classList.add('hidden');
            }
            buyPaymentDetailsOutput.innerHTML = outputHtml;
        }

        function displaySellCryptoAddress() {
            const sendCryptoNetwork = document.getElementById('sendCryptoNetwork').value;
            const sellCryptoAddressOutput = document.getElementById('sellCryptoAddressOutput');
            sellCryptoAddressOutput.classList.remove('hidden');

            let outputHtml = '';
            if (sendCryptoNetwork && cryptoAddresses[sendCryptoNetwork]) {
                outputHtml = `<p><strong>يرجى إرسال USDT إلى هذا العنوان لشبكة ${sendCryptoNetwork.toUpperCase()}:</strong></p>
                              <p><code>${cryptoAddresses[sendCryptoNetwork]}</code></p>`;
            } else {
                outputHtml = '';
                sellCryptoAddressOutput.classList.add('hidden');
            }
            sellCryptoAddressOutput.innerHTML = outputHtml;
        }

        function calculateTransactionFee(amount) {
            if (amount < 100) {
                return 1.65;
            } else if (amount >= 100 && amount <= 5000) {
                return amount * 0.01;
            } else { // amount > 5000
                return amount * 0.0005;
            }
        }

        function getNetworkFee(network) {
            switch (network) {
                case 'trc20':
                    return 2;
                case 'bep20':
                    return 0.15;
                case 'erc20':
                    return 0.3; // Corrected as per your last request (0.3 for ERC20, not TRC20 again)
                case 'binancepay':
                    return 0;
                default:
                    return 0;
            }
        }

        function submitOrder() {
            const fullName = document.getElementById('fullName').value;
            const phoneNumber = document.getElementById('phoneNumber').value;
            const city = document.getElementById('city').value;
            const transactionTypeRadios = document.querySelector('input[name="transactionType"]:checked');

            if (!fullName || !phoneNumber || !city) {
                alert('الرجاء ملء جميع معلوماتك الشخصية.');
                return;
            }

            if (!transactionTypeRadios) {
                alert('الرجاء اختيار نوع المعاملة (شراء أو بيع).');
                return;
            }

            const transactionType = transactionTypeRadios.value;
            let details = `طلب جديد:\n`;
            details += `الاسم الثلاثي: ${fullName}\n`;
            details += `رقم الهاتف: ${phoneNumber}\n`;
            details += `المدينة: ${city}\n`;
            details += `نوع المعاملة: ${transactionType === 'buy' ? 'شراء USDT' : 'بيع USDT'}\n`;

            let usdtAmount = 0;
            let transactionFee = 0;
            let networkFee = 0;
            let estimatedLiraAmount = 0;
            let paymentMethodChosen = '';
            let cryptoNetworkChosen = ''; // This will be for the network user chooses to send/receive USDT on

            if (transactionType === 'buy') {
                usdtAmount = parseFloat(document.getElementById('usdtQuantity').value);
                const network = document.getElementById('network').value;
                const walletAddress = document.getElementById('walletAddress').value;
                const buyPaymentMethod = document.getElementById('buyPaymentMethod').value;
                const buyNote = document.getElementById('buyNote').value;

                if (!usdtAmount || !network || !walletAddress || !buyPaymentMethod) {
                    alert('الرجاء ملء جميع الحقول المطلوبة للشراء.');
                    return;
                }

                transactionFee = calculateTransactionFee(usdtAmount);
                networkFee = getNetworkFee(network);
                
                // When buying, the user sends Lira and receives USDT.
                // The Lira amount they pay should cover: USDT quantity + service fee (in USDT then converted) + network fee (in USDT then converted)
                const totalUsdtForConversion = usdtAmount + transactionFee + networkFee;
                estimatedLiraAmount = totalUsdtForConversion * exchangeRate;
                paymentMethodChosen = buyPaymentMethod;
                cryptoNetworkChosen = network; // Network user receives USDT on

                details += `الكمية المطلوبة (USDT): ${usdtAmount}\n`;
                details += `الشبكة التي ستستقبل عليها: ${cryptoNetworkChosen}\n`;
                details += `عنوان المحفظة: ${walletAddress}\n`;
                details += `طريقة الدفع المختارة (بالليرة السورية): ${paymentMethodChosen}\n`;
                details += `ملاحظة (شراء): ${buyNote || 'لا يوجد'}\n`;
                details += `\n--- تفاصيل العمولة و المبلغ المطلوب ---\n`;
                details += `عمولة الخدمة: ${transactionFee.toFixed(2)} USDT\n`;
                details += `عمولة الشبكة (${cryptoNetworkChosen}): ${networkFee.toFixed(2)} USDT\n`;
                details += `المبلغ الإجمالي بالليرة السورية المطلوب للدفع (تقريبي): ${estimatedLiraAmount.toFixed(2)} ل.س\n`;
                details += `(هذا المبلغ يشمل قيمة الـ USDT المطلوبة + عمولة الخدمة + عمولة الشبكة محولة إلى الليرة السورية).\n`;

            } else { // sell
                usdtAmount = parseFloat(document.getElementById('sellQuantity').value);
                const sellPaymentMethod = document.getElementById('sellPaymentMethod').value;
                const sendCryptoNetwork = document.getElementById('sendCryptoNetwork').value; // Network user sends USDT on
                const sellNote = document.getElementById('sellNote').value;

                if (!usdtAmount || !sellPaymentMethod || !sendCryptoNetwork) {
                    alert('الرجاء ملء جميع الحقول المطلوبة للبيع.');
                    return;
                }
                
                transactionFee = calculateTransactionFee(usdtAmount);
                
                estimatedLiraAmount = (usdtAmount - transactionFee) * exchangeRate;
                paymentMethodChosen = sellPaymentMethod;
                cryptoNetworkChosen = sendCryptoNetwork; // Network user sends USDT on

                details += `الكمية المراد بيعها (USDT): ${usdtAmount}\n`;
                details += `طريقة استلام المبلغ (بالليرة السورية): ${paymentMethodChosen}\n`;
                details += `شبكة إرسال USDT إلينا: ${cryptoNetworkChosen}\n`;
                details += `ملاحظة (بيع): ${sellNote || 'لا يوجد'}\n`;
                details += `\n--- تفاصيل العمولة و المبلغ المستلم ---\n`;
                details += `عمولة الخدمة: ${transactionFee.toFixed(2)} USDT\n`;
                details += `المبلغ الصافي بالليرة السورية المستلم (تقريبي): ${estimatedLiraAmount.toFixed(2)} ل.س\n`;
                details += `(هذا المبلغ هو قيمة الـ USDT بعد خصم عمولة الخدمة).\n`;
            }

            const outputDiv = document.getElementById('output');
            outputDiv.innerHTML = `
                <h3>تم إرسال طلبك بنجاح!</h3>
                <p>سنقوم بمراجعة طلبك والتواصل معك قريباً.</p>
                <h4>تفاصيل طلبك:</h4>
                <pre>${details}</pre>
                <div class="note">
                    <p><strong>ملاحظة هامة:</strong> عمولة التسديد على طرق التحويل المختلفة بالليرة السورية تقع على المستخدم كما تحددها هذه الجهات.</p>
                </div>
            `;
            outputDiv.classList.remove('hidden');
            document.getElementById('mainForm').classList.add('hidden');

            sendEmail(details);
        }

        function sendEmail(details) {
            const subject = "طلب تحويل عملات رقمية جديد من موقعك";
            const body = encodeURIComponent(details);
            const mailtoLink = `mailto:alimahmoud001a@gmail.com?subject=${subject}&body=${body}`;

            window.location.href = mailtoLink;
        }

    </script>
</body>
</html>
