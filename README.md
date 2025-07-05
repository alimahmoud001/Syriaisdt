<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>خدمة تحويل العملات الرقمية (USDT)</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            color: #333;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
        }
        .container {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 700px;
            box-sizing: border-box;
        }
        h1, h2 {
            color: #0056b3;
            text-align: center;
            margin-bottom: 25px;
        }
        .form-section {
            margin-bottom: 25px;
            padding: 20px;
            border: 1px solid #eee;
            border-radius: 5px;
            background-color: #fdfdfd;
        }
        .form-group {
            margin-bottom: 15px;
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
            width: calc(100% - 22px);
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 16px;
            box-sizing: border-box;
            background-color: #fff;
        }
        input[type="radio"] {
            margin-left: 5px;
            margin-right: 10px;
            transform: scale(1.2); /* Make radio buttons slightly larger */
        }
        .radio-group label {
            display: inline-block;
            margin-left: 15px;
            font-weight: normal;
        }
        button {
            background-color: #007bff;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 18px;
            width: 100%;
            margin-top: 20px;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #0056b3;
        }
        .hidden {
            display: none;
        }
        .details-box {
            background-color: #e9f7ef;
            border: 1px solid #d4edda;
            padding: 15px;
            border-radius: 5px;
            margin-top: 20px;
            color: #155724;
        }
        .details-box pre {
            white-space: pre-wrap; /* Ensures line breaks are respected */
            font-family: Arial, sans-serif; /* Use a readable font for pre */
        }
        .error {
            color: red;
            font-size: 0.9em;
            margin-top: -10px;
            margin-bottom: 10px;
        }
        #result-section {
            background-color: #f0f8ff;
            border: 1px solid #d0e7ff;
            padding: 20px;
            border-radius: 8px;
            margin-top: 30px;
            text-align: center;
        }
        #result-section h3 {
            color: #0056b3;
            margin-bottom: 15px;
        }
        #result-section pre {
            background-color: #e9ecef;
            padding: 15px;
            border-radius: 5px;
            white-space: pre-wrap;
            word-wrap: break-word;
            font-family: monospace;
            font-size: 14px;
            text-align: right; /* Align text right for Arabic */
            border: 1px solid #dee2e6;
        }
        .footer-note {
            font-size: 0.9em;
            color: #666;
            margin-top: 20px;
            text-align: center;
        }
        .mailto-link-container {
            margin-top: 20px;
            padding-top: 15px;
            border-top: 1px solid #eee;
        }
        .mailto-link-container a {
            display: inline-block;
            background-color: #28a745;
            color: white;
            padding: 12px 25px;
            border-radius: 5px;
            text-decoration: none;
            font-size: 1.1em;
            transition: background-color 0.3s ease;
        }
        .mailto-link-container a:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>خدمة تحويل العملات الرقمية USDT</h1>
        <form id="cryptoExchangeForm">
            <div class="form-section">
                <h2>الخطوة الأولى: معلوماتك الشخصية</h2>
                <div class="form-group">
                    <label for="fullName">الاسم الثلاثي:</label>
                    <input type="text" id="fullName" name="fullName" required>
                </div>
                <div class="form-group">
                    <label for="phoneNumber">رقم الهاتف:</label>
                    <input type="tel" id="phoneNumber" name="phoneNumber" required>
                </div>
                <div class="form-group">
                    <label for="city">المدينة:</label>
                    <input type="text" id="city" name="city" required>
                </div>
            </div>

            <div class="form-section">
                <h2>الخطوة الثانية: ما الذي ترغب به؟</h2>
                <div class="form-group radio-group">
                    <input type="radio" id="buy" name="transactionType" value="buy" required>
                    <label for="buy">شراء USDT</label>
                    <input type="radio" id="sell" name="transactionType" value="sell">
                    <label for="sell">بيع USDT</label>
                </div>
            </div>

            <div id="buySection" class="form-section hidden">
                <h2>تفاصيل شراء USDT</h2>
                <div class="form-group">
                    <label for="buyAmount">الكمية المطلوبة (USDT):</label>
                    <input type="number" id="buyAmount" name="buyAmount" min="0.01" step="0.01" required>
                    <div id="buyAmountError" class="error"></div>
                </div>
                <div class="form-group">
                    <label for="buyNetwork">اختر الشبكة التي ستستقبل عليها USDT:</label>
                    <select id="buyNetwork" name="buyNetwork" required>
                        <option value="">-- اختر شبكة --</option>
                        <option value="bep20">BEP20</option>
                        <option value="trc20">TRC20</option>
                        <option value="erc20">ERC20</option>
                        <option value="binance_pay">Binance Pay</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="usdtAddress">عنوان محفظة USDT الخاص بك (لكي نرسل لك USDT):</label>
                    <input type="text" id="usdtAddress" name="usdtAddress" required>
                </div>
                <div class="form-group">
                    <label for="buyNote">ملاحظات إضافية (اختياري):</label>
                    <textarea id="buyNote" name="buyNote" rows="3"></textarea>
                </div>
                <div class="form-group">
                    <label for="paymentMethodBuy">طريقة الدفع (بالليرة السورية):</label>
                    <select id="paymentMethodBuy" name="paymentMethodBuy" required>
                        <option value="">-- اختر طريقة دفع --</option>
                        <option value="sham_cash">شام كاش</option>
                        <option value="bank_bemo">بنك بيمو</option>
                        <option value="syriatel_cash">سيريتل كاش</option>
                        <option value="alharam_transfer">حوالة الهرم</option>
                    </select>
                </div>
                <div id="buyPaymentDetails" class="details-box hidden">
                    <h3>يرجى التحويل إلى هذه التفاصيل لإتمام الشراء:</h3>
                    <pre id="buyPaymentDetailsContent"></pre>
                </div>
            </div>

            <div id="sellSection" class="form-section hidden">
                <h2>تفاصيل بيع USDT</h2>
                <div class="form-group">
                    <label for="sellAmount">الكمية المراد بيعها (USDT):</label>
                    <input type="number" id="sellAmount" name="sellAmount" min="0.01" step="0.01" required>
                    <div id="sellAmountError" class="error"></div>
                </div>
                <div class="form-group">
                    <label for="receiveMethod">طريقة استلام المبلغ (بالليرة السورية):</label>
                    <select id="receiveMethod" name="receiveMethod" required>
                        <option value="">-- اختر طريقة استلام --</option>
                        <option value="syriatel_cash">سيريتل كاش</option>
                        <option value="alharam_transfer">حوالة الهرم</option>
                        <option value="bank_bemo">بنك بيمو</option>
                        <option value="sham_cash">شام كاش</option>
                    </select>
                </div>
                <div id="receiveMethodDetails" class="form-group hidden">
                    <label for="accountDetails">رقم الحساب / عنوان الحساب الخاص بك لاستلام الليرة السورية:</label>
                    <input type="text" id="accountDetails" name="accountDetails">
                </div>
                <div class="form-group">
                    <label for="sellNote">ملاحظات إضافية (اختياري):</label>
                    <textarea id="sellNote" name="sellNote" rows="3"></textarea>
                </div>
                <div class="form-group">
                    <label for="sellNetwork">اختر الشبكة التي سترسل منها USDT إلينا:</label>
                    <select id="sellNetwork" name="sellNetwork" required>
                        <option value="">-- اختر شبكة --</option>
                        <option value="bep20">BEP20</option>
                        <option value="trc20">TRC20</option>
                        <option value="erc20">ERC20</option>
                        <option value="binance_pay">Binance Pay</option>
                    </select>
                </div>
                <div id="sellCryptoAddress" class="details-box hidden">
                    <h3>يرجى إرسال USDT إلى هذا العنوان:</h3>
                    <pre id="sellCryptoAddressContent"></pre>
                </div>
            </div>

            <button type="submit">إتمام الطلب</button>
        </form>

        <div id="result-section" class="hidden">
            <h3>تم إرسال طلبك بنجاح!</h3>
            <p><strong>يرجى مراجعة تفاصيل طلبك والعمولات أدناه:</strong></p>
            <pre id="orderDetailsSummary"></pre>
            <div class="mailto-link-container">
                <p>الرجاء النقر على الزر أدناه لإرسال تفاصيل طلبك إلينا عبر بريدك الإلكتروني:</p>
                <a id="sendEmailLink" href="#">إرسال الطلب عبر البريد الإلكتروني</a>
            </div>
            <p class="footer-note">ملاحظة: عمولة التسديد على طرق التحويل المختلفة بالليرة السورية تقع على المستخدم كما تحددها هذه الجهات.</p>
        </div>
    </div>

    <script>
        // DOM Elements
        const buyRadio = document.getElementById('buy');
        const sellRadio = document.getElementById('sell');
        const buySection = document.getElementById('buySection');
        const sellSection = document.getElementById('sellSection');
        const buyAmountInput = document.getElementById('buyAmount');
        const sellAmountInput = document.getElementById('sellAmount');
        const paymentMethodBuySelect = document.getElementById('paymentMethodBuy');
        const buyPaymentDetailsDiv = document.getElementById('buyPaymentDetails');
        const buyPaymentDetailsContent = document.getElementById('buyPaymentDetailsContent');
        const receiveMethodSelect = document.getElementById('receiveMethod');
        const receiveMethodDetailsDiv = document.getElementById('receiveMethodDetails');
        const sellNetworkSelect = document.getElementById('sellNetwork');
        const sellCryptoAddressDiv = document.getElementById('sellCryptoAddress');
        const sellCryptoAddressContent = document.getElementById('sellCryptoAddressContent');
        const cryptoExchangeForm = document.getElementById('cryptoExchangeForm');
        const resultSection = document.getElementById('result-section');
        const orderDetailsSummary = document.getElementById('orderDetailsSummary');
        const buyAmountError = document.getElementById('buyAmountError');
        const sellAmountError = document.getElementById('sellAmountError');
        const sendEmailLink = document.getElementById('sendEmailLink');

        // Exchange rate (example, needs to be updated dynamically in a real app)
        // **هذا السعر هو سعر تقديري، ويجب أن يتم تحديثه ديناميكيًا من مصدر موثوق في تطبيق حقيقي.**
        const USD_TO_SYP_RATE = 15000; // مثال: 1 USDT = 15000 ل.س

        // Fixed network fees (for our side when sending/receiving)
        const NETWORK_FEES = {
            'trc20': 2,    // $2 for TRC20
            'bep20': 0.15, // $0.15 for BEP20
            'erc20': 0.3,  // $0.3 for ERC20
            'binance_pay': 0 // $0 for Binance Pay
        };

        // Payment details for buying USDT (where user sends SYP)
        const BUY_PAYMENT_DETAILS = {
            'sham_cash': 'عنواني هو: be456e0ea9392db4d68a7093ee317bc8\nرقم الحساب: 5991161126028260',
            'syriatel_cash': 'عنواني: 0934598967',
            'alharam_transfer': 'التفاصيل هي:\nعلي ابراهيم محمود\n0934598967\nاللاذقية',
            'bank_bemo': 'التفاصيل هي:\nعلي ابراهيم محمود\n060104947910013000000'
        };

        // Crypto addresses for selling USDT (where user sends USDT to us)
        const SELL_CRYPTO_ADDRESSES = {
            'bep20': '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            'trc20': 'TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX',
            'erc20': '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            'binance_pay': '969755964'
        };

        // Event Listeners for transaction type selection
        buyRadio.addEventListener('change', () => {
            buySection.classList.remove('hidden');
            sellSection.classList.add('hidden');
            clearSellFields();
        });

        sellRadio.addEventListener('change', () => {
            sellSection.classList.remove('hidden');
            buySection.classList.add('hidden');
            clearBuyFields();
        });

        // Event Listeners for dynamic content
        paymentMethodBuySelect.addEventListener('change', () => {
            const selectedMethod = paymentMethodBuySelect.value;
            if (selectedMethod && BUY_PAYMENT_DETAILS[selectedMethod]) {
                buyPaymentDetailsContent.innerText = BUY_PAYMENT_DETAILS[selectedMethod];
                buyPaymentDetailsDiv.classList.remove('hidden');
            } else {
                buyPaymentDetailsDiv.classList.add('hidden');
            }
        });

        receiveMethodSelect.addEventListener('change', () => {
            const selectedMethod = receiveMethodSelect.value;
            if (selectedMethod === 'bank_bemo' || selectedMethod === 'sham_cash') {
                receiveMethodDetailsDiv.classList.remove('hidden');
                document.getElementById('accountDetails').setAttribute('required', 'required');
                document.getElementById('accountDetails').placeholder = selectedMethod === 'bank_bemo' ? 'أدخل رقم الحساب البنكي' : 'أدخل رقم أو عنوان الحساب';
            } else {
                receiveMethodDetailsDiv.classList.add('hidden');
                document.getElementById('accountDetails').removeAttribute('required');
                document.getElementById('accountDetails').value = ''; // Clear input if hidden
            }
        });

        sellNetworkSelect.addEventListener('change', () => {
            const selectedNetwork = sellNetworkSelect.value;
            if (selectedNetwork && SELL_CRYPTO_ADDRESSES[selectedNetwork]) {
                sellCryptoAddressContent.innerText = SELL_CRYPTO_ADDRESSES[selectedNetwork];
                sellCryptoAddressDiv.classList.remove('hidden');
            } else {
                sellCryptoAddressDiv.classList.add('hidden');
            }
        });

        // Function to clear sell specific fields
        function clearSellFields() {
            document.getElementById('sellAmount').value = '';
            document.getElementById('receiveMethod').value = '';
            document.getElementById('accountDetails').value = '';
            document.getElementById('sellNote').value = '';
            document.getElementById('sellNetwork').value = '';
            receiveMethodDetailsDiv.classList.add('hidden');
            sellCryptoAddressDiv.classList.add('hidden');
            sellAmountError.textContent = '';
        }

        // Function to clear buy specific fields
        function clearBuyFields() {
            document.getElementById('buyAmount').value = '';
            document.getElementById('buyNetwork').value = '';
            document.getElementById('usdtAddress').value = '';
            document.getElementById('buyNote').value = '';
            document.getElementById('paymentMethodBuy').value = '';
            buyPaymentDetailsDiv.classList.add('hidden');
            buyAmountError.textContent = '';
        }

        // Form submission handler
        cryptoExchangeForm.addEventListener('submit', (event) => {
            event.preventDefault(); // Prevent default form submission

            const fullName = document.getElementById('fullName').value;
            const phoneNumber = document.getElementById('phoneNumber').value;
            const city = document.getElementById('city').value;
            const transactionType = document.querySelector('input[name="transactionType"]:checked').value;

            let orderDetails = `الاسم الثلاثي: ${fullName}\n`;
            orderDetails += `رقم الهاتف: ${phoneNumber}\n`;
            orderDetails += `المدينة: ${city}\n`;
            orderDetails += `نوع العملية: ${transactionType === 'buy' ? 'شراء USDT' : 'بيع USDT'}\n`;

            let amount = 0;
            let network = '';
            let transactionFees = 0; // Our commission
            let networkFeeFromUs = 0; // Network fee we pay to send USDT
            let totalUSDTFees = 0; // Total fees in USDT
            let transactionFeeDescription = '';
            let totalAmountSYP = 0;

            if (transactionType === 'buy') {
                amount = parseFloat(buyAmountInput.value);
                network = document.getElementById('buyNetwork').value;
                const usdtAddress = document.getElementById('usdtAddress').value;
                const buyNote = document.getElementById('buyNote').value;
                const paymentMethodBuy = document.getElementById('paymentMethodBuy').value;

                if (isNaN(amount) || amount <= 0) {
                    buyAmountError.textContent = 'الرجاء إدخال كمية USDT صحيحة.';
                    return;
                }
                buyAmountError.textContent = ''; // Clear error

                orderDetails += `الكمية المطلوبة (USDT): ${amount.toFixed(2)}\n`;
                orderDetails += `الشبكة: ${network.toUpperCase()}\n`;
                orderDetails += `عنوان محفظة USDT الخاص بالمستخدم: ${usdtAddress}\n`;
                orderDetails += `ملاحظات الشراء: ${buyNote || 'لا يوجد'}\n`;
                orderDetails += `طريقة الدفع (الليرة السورية): ${paymentMethodBuy}\n`;
                orderDetails += `\n--- تفاصيل التحويل المطلوبة منك لإتمام الشراء ---\n`;
                orderDetails += `${BUY_PAYMENT_DETAILS[paymentMethodBuy]}\n`;

                // Calculate our commission
                if (amount < 100) {
                    transactionFees = 1.65; // Fixed $1.65
                    transactionFeeDescription = '1.65$ (للمبالغ أقل من 100$)';
                } else if (amount <= 5000) {
                    transactionFees = amount * 0.01; // 1%
                    transactionFeeDescription = '1% من المبلغ';
                } else { // amount > 5000
                    transactionFees = amount * 0.0005; // 0.05%
                    transactionFeeDescription = '0.05% من المبلغ';
                }
                
                // Add network fee we pay to send USDT to user
                networkFeeFromUs = NETWORK_FEES[network];
                totalUSDTFees = transactionFees + networkFeeFromUs;

                totalAmountSYP = (amount + totalUSDTFees) * USD_TO_SYP_RATE;

                orderDetails += `\n--- تفاصيل العمولات والتكلفة الإجمالية ---\n`;
                orderDetails += `سعر الصرف التقديري (1 USDT ≈ ${USD_TO_SYP_RATE} ل.س)\n`;
                orderDetails += `عمولتنا على التحويل: ${transactionFeeDescription} (تقريبي $${transactionFees.toFixed(2)})\n`;
                orderDetails += `عمولة الشبكة (${network.toUpperCase()}): $${networkFeeFromUs.toFixed(2)} (ندفعها لإرسال USDT لك)\n`;
                orderDetails += `إجمالي العمولات بالـ USDT: $${totalUSDTFees.toFixed(2)}\n`;
                orderDetails += `المبلغ الإجمالي المطلوب تحويله بالليرة السورية (تقريبي): ${totalAmountSYP.toFixed(2)} ل.س\n`;


            } else { // transactionType === 'sell'
                amount = parseFloat(sellAmountInput.value);
                network = document.getElementById('sellNetwork').value;
                const receiveMethod = document.getElementById('receiveMethod').value;
                const accountDetails = document.getElementById('accountDetails').value;
                const sellNote = document.getElementById('sellNote').value;

                if (isNaN(amount) || amount <= 0) {
                    sellAmountError.textContent = 'الرجاء إدخال كمية USDT صحيحة.';
                    return;
                }
                sellAmountError.textContent = ''; // Clear error


                orderDetails += `الكمية المراد بيعها (USDT): ${amount.toFixed(2)}\n`;
                orderDetails += `الشبكة التي سيتم الإرسال منها (إلينا): ${network.toUpperCase()}\n`;
                orderDetails += `طريقة استلام المبلغ: ${receiveMethod}\n`;
                if (receiveMethod === 'bank_bemo' || receiveMethod === 'sham_cash') {
                    orderDetails += `تفاصيل حساب الاستلام الخاص بك: ${accountDetails}\n`;
                }
                orderDetails += `ملاحظات البيع: ${sellNote || 'لا يوجد'}\n`;
                orderDetails += `\n--- عنوان محفظتنا لاستقبال USDT ---\n`;
                orderDetails += `${SELL_CRYPTO_ADDRESSES[network]}\n`;

                // Calculate our commission for selling
                if (amount < 100) {
                    transactionFees = 1.65; // Fixed $1.65
                    transactionFeeDescription = '1.65$ (للمبالغ أقل من 100$)';
                } else if (amount <= 5000) {
                    transactionFees = amount * 0.01; // 1%
                    transactionFeeDescription = '1% من المبلغ';
                } else { // amount > 5000
                    transactionFees = amount * 0.0005; // 0.05%
                    transactionFeeDescription = '0.05% من المبلغ';
                }
                
                // Network fee for selling is paid by the user when sending USDT to us.
                // We don't deduct it from the amount we pay them.

                const amountAfterOurFees = amount - transactionFees;
                totalAmountSYP = amountAfterOurFees * USD_TO_SYP_RATE;

                orderDetails += `\n--- تفاصيل العمولات والمبلغ الصافي ---\n`;
                orderDetails += `سعر الصرف التقديري (1 USDT ≈ ${USD_TO_SYP_RATE} ل.س)\n`;
                orderDetails += `عمولتنا على التحويل: ${transactionFeeDescription} (تقريبي $${transactionFees.toFixed(2)})\n`;
                orderDetails += `المبلغ الصافي بالـ USDT الذي ستحصل عليه بعد عمولتنا: $${amountAfterOurFees.toFixed(2)}\n`;
                orderDetails += `المبلغ الصافي الذي ستستلمه بالليرة السورية (تقريبي): ${totalAmountSYP.toFixed(2)} ل.س\n`;
            }

            // Display order summary
            orderDetailsSummary.textContent = orderDetails;
            resultSection.classList.remove('hidden');
            cryptoExchangeForm.classList.add('hidden'); // Hide the form

            // Prepare mailto link
            const emailAddress = 'alimahmoud001a@gmail.com';
            const emailSubject = `طلب تحويل USDT - ${transactionType === 'buy' ? 'شراء' : 'بيع'} من ${fullName}`;
            // Encode the order details for the mailto body
            const emailBody = encodeURIComponent(orderDetails);
            sendEmailLink.href = `mailto:${emailAddress}?subject=${encodeURIComponent(emailSubject)}&body=${emailBody}`;
        });
    </script>
</body>
</html>
