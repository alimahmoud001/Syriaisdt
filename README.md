<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تحويل العملات الرقمية (USDT)</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #f4f4f4;
            direction: rtl;
        }
        h1, h2, h3 {
            text-align: center;
            color: #333;
        }
        .form-section {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin: 10px 0 5px;
            font-weight: bold;
        }
        input, select, textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }
        button {
            background-color: #28a745;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            display: block;
            margin: 20px auto;
        }
        button:hover {
            background-color: #218838;
        }
        #result {
            margin-top: 20px;
            padding: 15px;
            background: #e9ecef;
            border-radius: 4px;
            display: none;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>
    <h1>تحويل العملات الرقمية (USDT)</h1>

    <!-- User Information Section -->
    <div class="form-section">
        <h2>معلومات المستخدم</h2>
        <label for="fullName">الاسم الثلاثي:</label>
        <input type="text" id="fullName" required>

        <label for="phoneNumber">رقم الهاتف:</label>
        <input type="text" id="phoneNumber" required>

        <label for="city">المدينة:</label>
        <input type="text" id="city" required>
    </div>

    <!-- Transaction Type Selection -->
    <div class="form-section">
        <h2>نوع العملية</h2>
        <label for="transactionType">هل تريد البيع أم الشراء؟</label>
        <select id="transactionType" onchange="toggleTransactionFields()">
            <option value="">اختر...</option>
            <option value="buy">شراء USDT</option>
            <option value="sell">بيع USDT</option>
        </select>
    </div>

    <!-- Buy USDT Section -->
    <div id="buySection" class="form-section hidden">
        <h2>تفاصيل شراء USDT</h2>
        <label for="buyAmount">الكمية المطلوبة (USDT):</label>
        <input type="number" id="buyAmount" min="0" step="0.01" onchange="calculateFees()">

        <label for="buyNetwork">اختر الشبكة:</label>
        <select id="buyNetwork" onchange="calculateFees()">
            <option value="">اختر...</option>
            <option value="bep20">BEP20</option>
            <option value="trc20">TRC20</option>
            <option value="erc20">ERC20</option>
            <option value="binancePay">Binance Pay</option>
        </select>

        <label for="walletAddress">عنوان المحفظة:</label>
        <input type="text" id="walletAddress">

        <label for="buyNotes">ملاحظات (اختياري):</label>
        <textarea id="buyNotes" rows="4"></textarea>

        <label for="paymentMethod">طريقة الدفع:</label>
        <select id="paymentMethod" onchange="showPaymentDetails()">
            <option value="">اختر...</option>
            <option value="shamCash">شام كاش</option>
            <option value="syriatelCash">سيريتل كاش</option>
            <option value="haramTransfer">حوالة الهرم</option>
            <option value="bemoBank">بنك بيمو</option>
        </select>

        <div id="paymentDetails" class="hidden"></div>
    </div>

    <!-- Sell USDT Section -->
    <div id="sellSection" class="form-section hidden">
        <h2>تفاصيل بيع USDT</h2>
        <label for="sellAmount">الكمية المراد بيعها (USDT):</label>
        <input type="number" id="sellAmount" min="0" step="0.01" onchange="calculateFees()">

        <label for="receiveMethod">طريقة الاستلام:</label>
        <select id="receiveMethod" onchange="showReceiveDetails()">
            <option value="">اختر...</option>
            <option value="syriatelCash">سيريتل كاش</option>
            <option value="haramTransfer">حوالة الهرم</option>
            <option value="bemoBank">بنك بيمو</option>
            <option value="shamCash">شام كاش</option>
        </select>

        <div id="receiveDetails"></div>

        <label for="sellNotes">ملاحظات (اختياري):</label>
        <textarea id="sellNotes" rows="4"></textarea>

        <label for="sellNetwork">اختر الشبكة:</label>
        <select id="sellNetwork" onchange="showCryptoAddress()">
            <option value="">اختر...</option>
            <option value="bep20">BEP20</option>
            <option value="trc20">TRC20</option>
            <option value="erc20">ERC20</option>
            <option value="binancePay">Binance Pay</option>
        </select>

        <div id="cryptoAddress" class="hidden"></div>
    </div>

    <!-- Result Section -->
    <div id="result"></div>

    <button onclick="submitRequest()">إرسال الطلب</button>

    <script>
        // Toggle visibility of buy/sell sections
        function toggleTransactionFields() {
            const transactionType = document.getElementById('transactionType').value;
            document.getElementById('buySection').classList.add('hidden');
            document.getElementById('sellSection').classList.add('hidden');
            document.getElementById('result').style.display = 'none';

            if (transactionType === 'buy') {
                document.getElementById('buySection').classList.remove('hidden');
            } else if (transactionType === 'sell') {
                document.getElementById('sellSection').classList.remove('hidden');
            }
            calculateFees();
        }

        // Show payment details for buying
        function showPaymentDetails() {
            const paymentMethod = document.getElementById('paymentMethod').value;
            const paymentDetails = document.getElementById('paymentDetails');
            paymentDetails.classList.remove('hidden');
            let details = '';

            if (paymentMethod === 'shamCash') {
                details = `
                    <strong>تفاصيل الدفع (شام كاش):</strong><br>
                    العنوان: be456e0ea9392db4d68a7093ee317bc8<br>
                    رقم الحساب: 5991161126028260
                `;
            } else if (paymentMethod === 'syriatelCash') {
                details = `
                    <strong>تفاصيل الدفع (سيريتل كاش):</strong><br>
                    العنوان: 0934598967
                `;
            } else if (paymentMethod === 'haramTransfer') {
                details = `
                    <strong>تفاصيل الدفع (حوالة الهرم):</strong><br>
                    الاسم: علي ابراهيم محمود<br>
                    رقم الهاتف: 0934598967<br>
                    المدينة: اللاذقية
                `;
            } else if (paymentMethod === 'bemoBank') {
                details = `
                    <strong>تفاصيل الدفع (بنك بيمو):</strong><br>
                    الاسم: علي ابراهيم محمود<br>
                    رقم الحساب: 060104947910013000000
                `;
            } else {
                paymentDetails.classList.add('hidden');
            }

            paymentDetails.innerHTML = details;
        }

        // Show receive details for selling
        function showReceiveDetails() {
            const receiveMethod = document.getElementById('receiveMethod').value;
            const receiveDetails = document.getElementById('receiveDetails');
            let details = '';

            if (receiveMethod === 'syriatelCash') {
                details = `
                    <label>رقم الحساب (سيريتل كاش):</label>
                    <input type="text" id="receiveAccount" required>
                `;
            } else if (receiveMethod === 'haramTransfer') {
                details = `
                    <label>تفاصيل الحوالة (حوالة الهرم):</label>
                    <input type="text" id="receiveAccount" placeholder="الاسم، رقم الهاتف، المدينة" required>
                `;
            } else if (receiveMethod === 'bemoBank') {
                details = `
                    <label>رقم الحساب البنكي (بنك بيمو):</label>
                    <input type="text" id="receiveAccount" required>
                `;
            } else if (receiveMethod === 'shamCash') {
                details = `
                    <label>رقم الحساب أو عنوان الحساب (شام كاش):</label>
                    <input type="text" id="receiveAccount" required>
                `;
            } else {
                details = '';
            }

            receiveDetails.innerHTML = details;
        }

        // Show crypto address for selling
        function showCryptoAddress() {
            const sellNetwork = document.getElementById('sellNetwork').value;
            const cryptoAddress = document.getElementById('cryptoAddress');
            cryptoAddress.classList.remove('hidden');
            let address = '';

            if (sellNetwork === 'bep20') {
                address = 'BEP20: 0x21802218d8d661d66F2C7959347a6382E1cc614F';
            } else if (sellNetwork === 'trc20') {
                address = 'TRC20: TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX';
            } else if (sellNetwork === 'erc20') {
                address = 'ERC20: 0x21802218d8d661d66F2C7959347a6382E1cc614F';
            } else if (sellNetwork === 'binancePay') {
                address = 'Binance Pay: 969755964';
            } else {
                cryptoAddress.classList.add('hidden');
            }

            cryptoAddress.innerHTML = `<strong>عنوان الإرسال:</strong><br>${address}`;
        }

        // Calculate fees
        function calculateFees() {
            const transactionType = document.getElementById('transactionType').value;
            let amount = 0;
            let network = '';
            let commission = 0;
            let networkFee = 0;

            if (transactionType === 'buy') {
                amount = parseFloat(document.getElementById('buyAmount').value) || 0;
                network = document.getElementById('buyNetwork').value;
            } else if (transactionType === 'sell') {
                amount = parseFloat(document.getElementById('sellAmount').value) || 0;
                network = document.getElementById('sellNetwork').value;
            }

            // Calculate commission
            if (amount < 100) {
                commission = 1.65;
            } else if (amount <= 5000) {
                commission = amount * 0.0165;
            } else {
                commission = amount * 0.005;
            }

            // Network fees
            if (network === 'trc20') {
                networkFee = 0.3;
            } else if (network === 'bep20') {
                networkFee = 0.15;
            } else if (network === 'erc20') {
                networkFee = 2;
            } else if (network === 'binancePay') {
                networkFee = 0;
            }

            const totalFees = commission + networkFee;
            const netAmount = amount - totalFees;

            document.getElementById('result').style.display = 'block';
            document.getElementById('result').innerHTML = `
                <strong>تفاصيل العمولة:</strong><br>
                المبلغ: ${amount.toFixed(2)} USDT<br>
                عمولة التحويل: ${commission.toFixed(2)} USDT<br>
                رسوم الشبكة (${network || 'غير محدد'}): ${networkFee.toFixed(2)} USDT<br>
                الإجمالي (المبلغ بعد الرسوم): ${netAmount.toFixed(2)} USDT
            `;
        }

        // Submit request
        function submitRequest() {
            const fullName = document.getElementById('fullName').value;
            const phoneNumber = document.getElementById('phoneNumber').value;
            const city = document.getElementById('city').value;
            const transactionType = document.getElementById('transactionType').value;

            if (!fullName || !phoneNumber || !city || !transactionType) {
                alert('يرجى ملء جميع الحقول المطلوبة في معلومات المستخدم ونوع العملية.');
                return;
            }

            let emailBody = `طلب تحويل USDT\n\n`;
            emailBody += `معلومات المستخدم:\n`;
            emailBody += `الاسم الثلاثي: ${fullName}\n`;
            emailBody += `رقم الهاتف: ${phoneNumber}\n`;
            emailBody += `المدينة: ${city}\n\n`;

            let amount, network, commission, networkFee, netAmount;

            if (transactionType === 'buy') {
                amount = parseFloat(document.getElementById('buyAmount').value) || 0;
                network = document.getElementById('buyNetwork').value;
                const walletAddress = document.getElementById('walletAddress').value;
                const notes = record.getElementById('buyNotes').value;
                const paymentMethod = document.getElementById('paymentMethod').value;

                if (!amount || !network || !walletAddress || !paymentMethod) {
                    alert('يرجى ملء جميع الحقول المطلوبة في قسم الشراء.');
                    return;
                }

                // Calculate fees
                if (amount < 100) {
                    commission = 1.65;
                } else if (amount <= 5000) {
                    commission = amount * 0.0165;
                } else {
                    commission = amount * 0.005;
                }

                if (network === 'trc20') {
                    networkFee = 0.3;
                } else if (network === 'bep20') {
                    networkFee = 0.15;
                } else if (network === 'erc20') {
                    networkFee = 2;
                } else if (network === 'binancePay') {
                    networkFee = 0;
                }

                netAmount = amount - (commission + networkFee);

                emailBody += `تفاصيل الشراء:\n`;
                emailBody += `الكمية: ${amount.toFixed(2)} USDT\n`;
                emailBody += `الشبكة: ${network}\n`;
                emailBody += `عنوان المحفظة: ${walletAddress}\n`;
                emailBody += `طريقة الدفع: ${paymentMethod}\n`;
                emailBody += `ملاحظات: ${notes || 'لا توجد'}\n`;
                emailBody += `تفاصيل الدفع:\n${document.getElementById('paymentDetails').innerText}\n`;
                emailBody += `عمولة التحويل: ${commission.toFixed(2)} USDT\n`;
                emailBody += `رسوم الشبكة: ${networkFee.toFixed(2)} USDT\n`;
                emailBody += `الصافي: ${netAmount.toFixed(2)} USDT\n`;
            } else if (transactionType === 'sell') {
                amount = parseFloat(document.getElementById('sellAmount').value) || 0;
                network = document.getElementById('sellNetwork').value;
                const receiveMethod = document.getElementById('receiveMethod').value;
                const receiveAccount = document.getElementById('receiveAccount')?.value;
                const notes = document.getElementById('sellNotes').value;

                if (!amount || !network || !receiveMethod || !receiveAccount) {
                    alert('يرجى ملء جميع الحقول المطلوبة في قسم البيع.');
                    return;
                }

                // Calculate fees
                if (amount < 100) {
                    commission = 1.65;
                } else if (amount <= 5000) {
                    commission = amount * 0.0165;
                } else {
                    commission = amount * 0.005;
                }

                if (network === 'trc20') {
                    networkFee = 0.3;
                } else if (network === 'bep20') {
                    networkFee = 0.15;
                } else if (network === 'erc20') {
                    networkFee = 2;
                } else if (network === 'binancePay') {
                    networkFee = 0;
                }

                netAmount = amount - (commission + networkFee);

                emailBody += `تفاصيل البيع:\n`;
                emailBody += `الكمية: ${amount.toFixed(2)} USDT\n`;
                emailBody += `الشبكة: ${network}\n`;
                emailBody += `طريقة الاستلام: ${receiveMethod}\n`;
                emailBody += `تفاصيل الحساب: ${receiveAccount}\n`;
                emailBody += `ملاحظات: ${notes || 'لا توجد'}\n`;
                emailBody += `عنوان الإرسال:\n${document.getElementById('cryptoAddress').innerText}\n`;
                emailBody += `عمولة التحويل: ${commission.toFixed(2)} USDT\n`;
                emailBody += `رسوم الشبكة: ${networkFee.toFixed(2)} USDT\n`;
                emailBody += `الصافي: ${netAmount.toFixed(2)} USDT\n`;
            }

            emailBody += `\nملاحظة: عمولة التسديد على طرق التحويل المختلفة بالليرة السورية تقع على المستخدم كما تحددها هذه الجهات.`;

            // Simulate sending email (replace with actual email API if available)
            console.log('Sending email to alimahmoud001a@gmail.com with body:\n', emailBody);
            alert('تم إرسال الطلب بنجاح!\n' + emailBody);

            // Display result to user
            document.getElementById('result').style.display = 'block';
            document.getElementById('result').innerHTML += `<br><strong>تم إرسال الطلب بنجاح!</strong><br>ملاحظة: عمولة التسديد على طرق التحويل المختلفة بالليرة السورية تقع على المستخدم كما تحددها هذه الجهات.`;
        }
    </script>
</body>
</html>
