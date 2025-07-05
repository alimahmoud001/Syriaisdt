<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تحويل العملات الرقمية (USDT)</title>
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
        .details-box p {
            margin: 5px 0;
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
        }
        #result-section h3 {
            color: #0056b3;
            text-align: center;
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
            border: 1px solid #dee2e6;
        }
        .footer-note {
            font-size: 0.9em;
            color: #666;
            margin-top: 20px;
            text-align: center;
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
                    <label for="buyNetwork">اختر الشبكة:</label>
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
                    <label for="paymentMethodBuy">طريقة الدفع (الليرة السورية):</label>
                    <select id="paymentMethodBuy" name="paymentMethodBuy" required>
                        <option value="">-- اختر طريقة دفع --</option>
                        <option value="sham_cash">شام كاش</option>
                        <option value="bank_bemo">بنك بيمو</option>
                        <option value="syriatel_cash">سيريتل كاش</option>
                        <option value="alharam_transfer">حوالة الهرم</option>
                    </select>
                </div>
                <div id="buyPaymentDetails" class="details-box hidden">
                    <h3>تفاصيل الدفع (يرجى التحويل إلى هذه التفاصيل):</h3>
                    <p id="buyPaymentDetailsContent"></p>
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
                    <label for="receiveMethod">طريقة استلام المبلغ (الليرة السورية):</label>
                    <select id="receiveMethod" name="receiveMethod" required>
                        <option value="">-- اختر طريقة استلام --</option>
                        <option value="syriatel_cash">سيريتل كاش</option>
                        <option value="alharam_transfer">حوالة الهرم</option>
                        <option value="bank_bemo">بنك بيمو</option>
                        <option value="sham_cash">شام كاش</option>
                    </select>
                </div>
                <div id="receiveMethodDetails" class="form-group hidden">
                    <label for="accountDetails">رقم الحساب / عنوان الحساب الخاص بك:</label>
                    <input type="text" id="accountDetails" name="accountDetails">
                </div>
                <div class="form-group">
                    <label for="sellNote">ملاحظات إضافية (اختياري):</label>
                    <textarea id="sellNote" name="sellNote" rows="3"></textarea>
                </div>
                <div class="form-group">
                    <label for="sellNetwork">اختر الشبكة التي سترسل منها USDT:</label>
                    <select id="sellNetwork" name="sellNetwork" required>
                        <option value="">-- اختر شبكة --</option>
                        <option value="bep20">BEP20</option>
                        <option value="trc20">TRC20</option>
                        <option value="erc20">ERC20</option>
                        <option value="binance_pay">Binance Pay</option>
                    </select>
                </div>
                <div id="sellCryptoAddress" class="details-box hidden">
                    <h3>عنوان محفظتنا لاستلام USDT (يرجى إرسال USDT إلى هذا العنوان):</h3>
                    <p id="sellCryptoAddressContent"></p>
                </div>
            </div>

            <button type="submit">إتمام الطلب</button>
        </form>

        <div id="result-section" class="hidden">
            <h3>تم إرسال طلبك بنجاح!</h3>
            <p><strong>تفاصيل طلبك والعمولات:</strong></p>
            <pre id="orderDetailsSummary"></pre>
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

        // Exchange rate (example, needs to be updated dynamically in a real app)
        const USD_TO_SYP_RATE = 15000; // Example rate, please adjust

        // Fixed network fees
        const NETWORK_FEES = {
            'trc20': 2,
            'bep20': 0.15,
            'erc20': 0.3,
            'binance_pay': 0
        };

        // Payment details for buying USDT
        const BUY_PAYMENT_DETAILS = {
            'sham_cash': 'عنواني هو: be456e0ea9392db4d68a7093ee317bc8\nرقم الحساب: 5991161126028260',
            'syriatel_cash': 'عنواني: 0934598967',
            'alharam_transfer': 'التفاصيل هي:\nعلي ابراهيم محمود\n0934598967\nاللاذقية',
            'bank_bemo': 'التفاصيل هي:\nعلي ابراهيم محمود\n060104947910013000000'
        };

        // Crypto addresses for selling USDT
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
            let totalFees = 0;
            let transactionFeePercentage = 0;
            let totalAmountSYP = 0;

            if (transactionType === 'buy') {
                amount = parseFloat(buyAmountInput.value);
                network = document.getElementById('buyNetwork').value;
                const usdtAddress = document.getElementById('usdtAddress').value;
                const buyNote = document.getElementById('buyNote').value;
                const paymentMethodBuy = document.getElementById('paymentMethodBuy').value;

                if (isNaN(amount) || amount <= 0) {
                    buyAmountError.textContent = 'الرجاء إدخال كمية صحيحة.';
                    return;
                }
                buyAmountError.textContent = ''; // Clear error

                orderDetails += `الكمية المطلوبة (USDT): ${amount.toFixed(2)}\n`;
                orderDetails += `الشبكة: ${network.toUpperCase()}\n`;
                orderDetails += `عنوان محفظة USDT الخاص بالمستخدم: ${usdtAddress}\n`;
                orderDetails += `ملاحظات الشراء: ${buyNote || 'لا يوجد'}\n`;
                orderDetails += `طريقة الدفع (الليرة السورية): ${paymentMethodBuy}\n`;
                orderDetails += `تفاصيل التحويل المطلوبة من المستخدم:\n${BUY_PAYMENT_DETAILS[paymentMethodBuy]}\n`;

                // Calculate transaction fee based on amount
                if (amount < 100) {
                    totalFees = 1.65; // Fixed $1.65
                    transactionFeePercentage = null; // Not applicable
                } else if (amount <= 5000) {
                    transactionFeePercentage = 0.01; // 1%
                    totalFees = amount * transactionFeePercentage;
                } else { // amount > 5000
                    transactionFeePercentage = 0.0005; // 0.05%
                    totalFees = amount * transactionFeePercentage;
                }
                
                // Add network fee if applicable (for sending USDT to user)
                const networkFee = NETWORK_FEES[network];
                totalFees += networkFee;

                totalAmountSYP = (amount + totalFees) * USD_TO_SYP_RATE;

                orderDetails += `\n--- تفاصيل العمولات والتكلفة الإجمالية ---\n`;
                orderDetails += `سعر الصرف التقديري (1 USDT = ${USD_TO_SYP_RATE} ل.س)\n`;
                if (transactionFeePercentage !== null) {
                    orderDetails += `عمولة التحويل (نسبة مئوية): ${transactionFeePercentage * 100}%\n`;
                } else {
                     orderDetails += `عمولة التحويل (مبلغ ثابت): $1.65 (للمبالغ أقل من $100)\n`;
                }
                orderDetails += `عمولة الشبكة (${network.toUpperCase()}): $${networkFee.toFixed(2)}\n`;
                orderDetails += `إجمالي عمولة USDT: $${totalFees.toFixed(2)}\n`;
                orderDetails += `المبلغ الإجمالي المطلوب بالليرة السورية (تقريبي): ${totalAmountSYP.toFixed(2)} ل.س\n`;


            } else { // transactionType === 'sell'
                amount = parseFloat(sellAmountInput.value);
                network = document.getElementById('sellNetwork').value;
                const receiveMethod = document.getElementById('receiveMethod').value;
                const accountDetails = document.getElementById('accountDetails').value;
                const sellNote = document.getElementById('sellNote').value;

                if (isNaN(amount) || amount <= 0) {
                    sellAmountError.textContent = 'الرجاء إدخال كمية صحيحة.';
                    return;
                }
                sellAmountError.textContent = ''; // Clear error


                orderDetails += `الكمية المراد بيعها (USDT): ${amount.toFixed(2)}\n`;
                orderDetails += `الشبكة التي سيتم الإرسال منها: ${network.toUpperCase()}\n`;
                orderDetails += `طريقة استلام المبلغ: ${receiveMethod}\n`;
                if (receiveMethod === 'bank_bemo' || receiveMethod === 'sham_cash') {
                    orderDetails += `تفاصيل حساب الاستلام: ${accountDetails}\n`;
                }
                orderDetails += `ملاحظات البيع: ${sellNote || 'لا يوجد'}\n`;
                orderDetails += `عنوان محفظتنا لاستقبال USDT: ${SELL_CRYPTO_ADDRESSES[network]}\n`;

                // Calculate transaction fee based on amount
                if (amount < 100) {
                    totalFees = 1.65; // Fixed $1.65
                    transactionFeePercentage = null; // Not applicable
                } else if (amount <= 5000) {
                    transactionFeePercentage = 0.01; // 1%
                    totalFees = amount * transactionFeePercentage;
                } else { // amount > 5000
                    transactionFeePercentage = 0.0005; // 0.05%
                    totalFees = amount * transactionFeePercentage;
                }

                // Note: Network fee for selling is paid by the user when sending USDT, not deducted by us.
                // The prompt specified "عمولة التحويل في الشبكات المختلفة هي ... العمولات كلها ثابتة وليست نسب مئوية"
                // which implies these are *our* processing fees, not blockchain gas fees directly.
                // So, the network fee here is on the user's side when they send to us.
                // We calculate what the user *receives* after our commission.

                const amountAfterOurFees = amount - totalFees;
                totalAmountSYP = amountAfterOurFees * USD_TO_SYP_RATE;

                orderDetails += `\n--- تفاصيل العمولات والمبلغ الصافي ---\n`;
                orderDetails += `سعر الصرف التقديري (1 USDT = ${USD_TO_SYP_RATE} ل.س)\n`;
                if (transactionFeePercentage !== null) {
                    orderDetails += `عمولة التحويل (نسبة مئوية): ${transactionFeePercentage * 100}%\n`;
                } else {
                     orderDetails += `عمولة التحويل (مبلغ ثابت): $1.65 (للمبالغ أقل من $100)\n`;
                }
                orderDetails += `إجمالي عمولة USDT: $${totalFees.toFixed(2)}\n`;
                orderDetails += `المبلغ الصافي بالـ USDT بعد عمولتنا: $${amountAfterOurFees.toFixed(2)}\n`;
                orderDetails += `المبلغ الصافي الذي ستستلمه بالليرة السورية (تقريبي): ${totalAmountSYP.toFixed(2)} ل.س\n`;
            }

            // Display order summary
            orderDetailsSummary.textContent = orderDetails;
            resultSection.classList.remove('hidden');
            cryptoExchangeForm.classList.add('hidden'); // Hide the form

            // Simulate sending email (in a real app, this would be handled by a backend)
            sendEmail('alimahmoud001a@gmail.com', 'طلب تحويل عملات رقمية جديد', orderDetails);
        });

        // Simple function to simulate email sending (client-side limitation)
        function sendEmail(to, subject, body) {
            // In a real application, you would send this data to a backend server.
            // For example, using fetch API:
            /*
            fetch('/api/send-email', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ to, subject, body })
            })
            .then(response => response.json())
            .then(data => console.log('Email simulated successfully:', data))
            .catch(error => console.error('Error simulating email:', error));
            */
            console.log(`Simulating Email Send:\nTo: ${to}\nSubject: ${subject}\nBody:\n${body}`);
            alert('تم إرسال طلبك بنجاح! (تمت محاكاة إرسال البريد الإلكتروني)');
        }
    </script>
</body>
</html>
