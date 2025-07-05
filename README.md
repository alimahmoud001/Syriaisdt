<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تحويل USDT - المنصة السورية</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;700&display=swap');

        :root {
            --primary-color: #0056b3; /* Dark Blue */
            --secondary-color: #007bff; /* Royal Blue */
            --accent-color: #28a745; /* Green for success */
            --text-color: #333;
            --background-color: #f8f9fa; /* Light Grey */
            --card-background: #ffffff;
            --border-color: #dee2e6;
            --shadow-color: rgba(0, 0, 0, 0.1);
        }

        body {
            font-family: 'Cairo', sans-serif;
            margin: 0;
            padding: 20px;
            background-color: var(--background-color);
            color: var(--text-color);
            line-height: 1.6;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
        }

        .container {
            background-color: var(--card-background);
            border-radius: 10px;
            box-shadow: 0 4px 15px var(--shadow-color);
            padding: 30px;
            width: 100%;
            max-width: 800px;
            box-sizing: border-box;
            direction: rtl;
        }

        h1, h2 {
            color: var(--primary-color);
            text-align: center;
            margin-bottom: 25px;
            font-weight: 700;
        }

        .form-section {
            margin-bottom: 30px;
            padding: 20px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            background-color: #fefefe;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 700;
            color: var(--secondary-color);
        }

        input[type="text"],
        input[type="tel"],
        input[type="number"],
        textarea,
        select {
            width: calc(100% - 22px);
            padding: 12px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-size: 1rem;
            color: var(--text-color);
            background-color: #fff;
            box-sizing: border-box;
            transition: border-color 0.3s ease;
        }

        input[type="text"]:focus,
        input[type="tel"]:focus,
        input[type="number"]:focus,
        textarea:focus,
        select:focus {
            border-color: var(--secondary-color);
            outline: none;
            box-shadow: 0 0 0 3px rgba(0, 123, 255, 0.25);
        }

        textarea {
            resize: vertical;
            min-height: 80px;
        }

        .radio-group label {
            display: inline-block;
            margin-left: 20px;
            font-weight: normal;
            cursor: pointer;
        }

        .radio-group input[type="radio"] {
            margin-left: 8px;
        }

        button {
            background-color: var(--primary-color);
            color: white;
            padding: 14px 25px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: 700;
            transition: background-color 0.3s ease, transform 0.2s ease;
            width: 100%;
            margin-top: 20px;
        }

        button:hover {
            background-color: var(--secondary-color);
            transform: translateY(-2px);
        }

        .hidden {
            display: none;
        }

        .details-box {
            background-color: #e9f7ee; /* Light green for success */
            border: 1px solid var(--accent-color);
            border-radius: 8px;
            padding: 20px;
            margin-top: 25px;
            text-align: right;
            line-height: 1.8;
        }

        .details-box p {
            margin: 8px 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .details-box p strong {
            color: var(--primary-color);
            margin-left: 10px;
            white-space: nowrap; /* Prevent breaking on small screens */
        }

        .copy-button {
            background-color: #6c757d; /* Grey */
            color: white;
            border: none;
            padding: 8px 12px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: background-color 0.3s ease;
            margin-right: 10px; /* Space between value and button */
        }

        .copy-button:hover {
            background-color: #5a6268;
        }

        .info-message {
            background-color: #d1ecf1;
            color: #0c5460;
            border: 1px solid #bee5eb;
            padding: 15px;
            border-radius: 8px;
            margin-top: 25px;
            text-align: center;
            font-size: 0.95rem;
        }

        #confirmationMessage {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
            padding: 20px;
            border-radius: 8px;
            margin-top: 30px;
            text-align: center;
            font-size: 1.1rem;
            font-weight: bold;
            display: none; /* Hidden by default */
        }

        /* Responsive adjustments */
        @media (max-width: 600px) {
            body {
                padding: 15px;
            }

            .container {
                padding: 20px;
            }

            input[type="text"],
            input[type="tel"],
            input[type="number"],
            textarea,
            select {
                width: 100%;
            }

            .radio-group label {
                margin-left: 10px;
                display: block;
                margin-bottom: 10px;
            }

            .details-box p {
                flex-direction: column;
                align-items: flex-start;
            }
            .details-box p strong {
                margin-bottom: 5px;
                margin-left: 0;
            }
            .copy-button {
                margin-top: 5px;
                margin-right: 0;
                width: 100%;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>منصة تحويل USDT</h1>
        <form id="conversionForm">
            <div id="step1" class="form-section">
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

            <div id="step2" class="form-section">
                <h2>الخطوة الثانية: بيع أو شراء USDT</h2>
                <div class="form-group radio-group">
                    <input type="radio" id="buy" name="transactionType" value="buy" required>
                    <label for="buy">شراء USDT</label>
                    <input type="radio" id="sell" name="transactionType" value="sell" required>
                    <label for="sell">بيع USDT</label>
                </div>

                <div id="buySection" class="hidden">
                    <h3>معلومات الشراء</h3>
                    <div class="form-group">
                        <label for="buyAmount">الكمية المطلوبة (USDT):</label>
                        <input type="number" id="buyAmount" name="buyAmount" min="1" step="any" required>
                    </div>
                    <div class="form-group">
                        <label for="buyNetwork">اختر الشبكة:</label>
                        <select id="buyNetwork" name="buyNetwork" required>
                            <option value="">اختر شبكة</option>
                            <option value="bep20">BEP20</option>
                            <option value="trc20">TRC20</option>
                            <option value="erc20">ERC20</option>
                            <option value="binance_pay">Binance Pay</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="buyAddress">عنوان المحفظة الخاص بك (لاستلام USDT):</label>
                        <input type="text" id="buyAddress" name="buyAddress" required>
                    </div>
                    <div class="form-group">
                        <label for="buyNote">ملاحظة (اختياري):</label>
                        <textarea id="buyNote" name="buyNote"></textarea>
                    </div>
                </div>

                <div id="sellSection" class="hidden">
                    <h3>معلومات البيع</h3>
                    <div class="form-group">
                        <label for="sellAmount">الكمية التي تبيعها (USDT):</label>
                        <input type="number" id="sellAmount" name="sellAmount" min="1" step="any" required>
                    </div>
                    <div class="form-group">
                        <label for="sellNetwork">اختر شبكة USDT التي سترسل منها:</label>
                        <select id="sellNetwork" name="sellNetwork" required>
                            <option value="">اختر شبكة</option>
                            <option value="bep20">BEP20</option>
                            <option value="trc20">TRC20</option>
                            <option value="erc20">ERC20</option>
                            <option value="binance_pay">Binance Pay</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label for="receiveMethod">طريقة استلام المبلغ (الليرة السورية):</label>
                        <select id="receiveMethod" name="receiveMethod" required>
                            <option value="">اختر طريقة الاستلام</option>
                            <option value="syriatel_cash">سيريتل كاش</option>
                            <option value="harram_transfer">حوالة هرم</option>
                            <option value="bemo_bank">بنك بيمو</option>
                            <option value="sham_cash">شام كاش</option>
                        </select>
                    </div>
                    <div id="bankAccountDiv" class="form-group hidden">
                        <label for="bankAccount">رقم الحساب البنكي (بنك بيمو):</label>
                        <input type="text" id="bankAccount" name="bankAccount">
                    </div>
                    <div id="shamCashAccountDiv" class="form-group hidden">
                        <label for="shamCashAccount">رقم/عنوان حساب شام كاش:</label>
                        <input type="text" id="shamCashAccount" name="shamCashAccount">
                    </div>
                    <div class="form-group">
                        <label for="sellNote">ملاحظة (اختياري):</label>
                        <textarea id="sellNote" name="sellNote"></textarea>
                    </div>
                </div>
            </div>

            <div id="step3" class="form-section hidden">
                <h2>الخطوة الثالثة: تفاصيل التحويل</h2>

                <div id="buyPaymentDetails" class="hidden details-box">
                    <h3>تفاصيل الدفع بالليرة السورية</h3>
                    <div class="form-group">
                        <label for="paymentMethodBuy">اختر طريقة الدفع بالليرة السورية:</label>
                        <select id="paymentMethodBuy" name="paymentMethodBuy" required>
                            <option value="">اختر طريقة الدفع</option>
                            <option value="sham_cash">شام كاش</option>
                            <option value="bemo_bank">بنك بيمو</option>
                            <option value="syriatel_cash">سيريتل كاش</option>
                            <option value="harram_transfer">حوالة هرم</option>
                        </select>
                    </div>
                    <div id="buyPaymentInfo" class="hidden">
                        <p><strong>تفاصيل الدفع:</strong></p>
                        <p id="shamCashDetails" class="hidden">
                            <span>عنوان المحفظة: <span id="shamCashAddress">be456e0ea9392db4d68a7093ee317bc8</span></span>
                            <button type="button" class="copy-button" onclick="copyToClipboard('shamCashAddress')">نسخ</button><br>
                            <span>رقم الحساب: <span id="shamCashAccNum">5991161126028260</span></span>
                            <button type="button" class="copy-button" onclick="copyToClipboard('shamCashAccNum')">نسخ</button>
                        </p>
                        <p id="syriatelCashDetails" class="hidden">
                            <span>رقم الهاتف: <span id="syriatelCashNum">0934598967</span></span>
                            <button type="button" class="copy-button" onclick="copyToClipboard('syriatelCashNum')">نسخ</button>
                        </p>
                        <p id="harramTransferDetails" class="hidden">
                            <span>الاسم: علي ابراهيم محمود</span><br>
                            <span>رقم الهاتف: <span id="harramTelNum">0934598967</span></span>
                            <button type="button" class="copy-button" onclick="copyToClipboard('harramTelNum')">نسخ</button><br>
                            <span>المدينة: اللاذقية</span>
                        </p>
                        <p id="bemoBankDetails" class="hidden">
                            <span>الاسم: علي ابراهيم محمود</span><br>
                            <span>رقم الحساب: <span id="bemoAccNum">060104947910013000000</span></span>
                            <button type="button" class="copy-button" onclick="copyToClipboard('bemoAccNum')">نسخ</button>
                        </p>
                    </div>
                </div>

                <div id="sellCryptoDetails" class="hidden details-box">
                    <h3>عناوين USDT لإرسال المبلغ</h3>
                    <p>الرجاء إرسال مبلغ USDT إلى العنوان المناسب للشبكة التي اخترتها:</p>
                    <p id="bep20Address" class="hidden">
                        <strong>BEP20:</strong> <span>0x21802218d8d661d66F2C7959347a6382E1cc614F</span>
                        <button type="button" class="copy-button" onclick="copyToClipboard(this)">نسخ</button>
                    </p>
                    <p id="trc20Address" class="hidden">
                        <strong>TRC20:</strong> <span>TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX</span>
                        <button type="button" class="copy-button" onclick="copyToClipboard(this)">نسخ</button>
                    </p>
                    <p id="erc20Address" class="hidden">
                        <strong>ERC20:</strong> <span>0x21802218d8d661d66F2C7959347a6382E1cc614F</span>
                        <button type="button" class="copy-button" onclick="copyToClipboard(this)">نسخ</button>
                    </p>
                    <p id="binancePayId" class="hidden">
                        <strong>Binance Pay ID:</strong> <span>969755964</span>
                        <button type="button" class="copy-button" onclick="copyToClipboard(this)">نسخ</button>
                    </p>
                </div>
            </div>

            <button type="submit">إتمام الطلب</button>
        </form>

        <div id="confirmationMessage" class="info-message">
            </div>

        <div id="commissionNote" class="info-message hidden">
            <p><strong>ملاحظة هامة:</strong> عمولة التسديد على طرق التحويل المختلفة بالليرة السورية تقع على المستخدم كما تحددها هذه الجهات.</p>
        </div>
    </div>

    <script>
        // Exchange rate (manual update)
        const SYP_EXCHANGE_RATE = 10000; // 1 USDT = 10000 SYP

        // Network fees
        const NETWORK_FEES = {
            'trc20': 2,
            'bep20': 0.15,
            'erc20': 0.3, // Note: You listed TRC20 twice. Assuming the second one is ERC20.
            'binance_pay': 0
        };

        // DOM Elements
        const form = document.getElementById('conversionForm');
        const buyRadio = document.getElementById('buy');
        const sellRadio = document.getElementById('sell');
        const buySection = document.getElementById('buySection');
        const sellSection = document.getElementById('sellSection');
        const step3 = document.getElementById('step3');
        const buyPaymentDetails = document.getElementById('buyPaymentDetails');
        const sellCryptoDetails = document.getElementById('sellCryptoDetails');

        const receiveMethodSelect = document.getElementById('receiveMethod');
        const bankAccountDiv = document.getElementById('bankAccountDiv');
        const shamCashAccountDiv = document.getElementById('shamCashAccountDiv');

        const paymentMethodBuySelect = document.getElementById('paymentMethodBuy');
        const buyPaymentInfoDiv = document.getElementById('buyPaymentInfo');
        const shamCashDetails = document.getElementById('shamCashDetails');
        const syriatelCashDetails = document.getElementById('syriatelCashDetails');
        const harramTransferDetails = document.getElementById('harramTransferDetails');
        const bemoBankDetails = document.getElementById('bemoBankDetails');

        const sellNetworkSelect = document.getElementById('sellNetwork');
        const bep20AddressElem = document.getElementById('bep20Address');
        const trc20AddressElem = document.getElementById('trc20Address');
        const erc20AddressElem = document.getElementById('erc20Address');
        const binancePayIdElem = document.getElementById('binancePayId');

        const confirmationMessageDiv = document.getElementById('confirmationMessage');
        const commissionNoteDiv = document.getElementById('commissionNote');

        // Event Listeners
        buyRadio.addEventListener('change', toggleSections);
        sellRadio.addEventListener('change', toggleSections);
        receiveMethodSelect.addEventListener('change', toggleReceiveMethodDetails);
        paymentMethodBuySelect.addEventListener('change', toggleBuyPaymentDetails);
        sellNetworkSelect.addEventListener('change', toggleSellCryptoAddresses);
        form.addEventListener('submit', handleSubmit);

        // Functions
        function toggleSections() {
            buySection.classList.add('hidden');
            sellSection.classList.add('hidden');
            step3.classList.add('hidden');
            buyPaymentDetails.classList.add('hidden');
            sellCryptoDetails.classList.add('hidden');
            confirmationMessageDiv.style.display = 'none'; // Hide confirmation on type change
            commissionNoteDiv.classList.add('hidden'); // Hide commission note initially

            if (buyRadio.checked) {
                buySection.classList.remove('hidden');
                step3.classList.remove('hidden');
                buyPaymentDetails.classList.remove('hidden');
                // Ensure other details are hidden when switching to buy
                hideAllBuyPaymentDetails();
                hideAllSellCryptoAddresses();
            } else if (sellRadio.checked) {
                sellSection.classList.remove('hidden');
                step3.classList.remove('hidden');
                sellCryptoDetails.classList.remove('hidden');
                // Ensure other details are hidden when switching to sell
                hideAllSellCryptoAddresses();
                hideAllBuyPaymentDetails();
            }
        }

        function toggleReceiveMethodDetails() {
            bankAccountDiv.classList.add('hidden');
            shamCashAccountDiv.classList.add('hidden');
            document.getElementById('bankAccount').required = false;
            document.getElementById('shamCashAccount').required = false;

            const selectedMethod = receiveMethodSelect.value;
            if (selectedMethod === 'bemo_bank') {
                bankAccountDiv.classList.remove('hidden');
                document.getElementById('bankAccount').required = true;
            } else if (selectedMethod === 'sham_cash') {
                shamCashAccountDiv.classList.remove('hidden');
                document.getElementById('shamCashAccount').required = true;
            }
        }

        function hideAllBuyPaymentDetails() {
            buyPaymentInfoDiv.classList.add('hidden');
            shamCashDetails.classList.add('hidden');
            syriatelCashDetails.classList.add('hidden');
            harramTransferDetails.classList.add('hidden');
            bemoBankDetails.classList.add('hidden');
        }

        function toggleBuyPaymentDetails() {
            hideAllBuyPaymentDetails();
            const selectedMethod = paymentMethodBuySelect.value;
            if (selectedMethod) {
                buyPaymentInfoDiv.classList.remove('hidden');
                if (selectedMethod === 'sham_cash') {
                    shamCashDetails.classList.remove('hidden');
                } else if (selectedMethod === 'syriatel_cash') {
                    syriatelCashDetails.classList.remove('hidden');
                } else if (selectedMethod === 'harram_transfer') {
                    harramTransferDetails.classList.remove('hidden');
                } else if (selectedMethod === 'bemo_bank') {
                    bemoBankDetails.classList.remove('hidden');
                }
            }
        }

        function hideAllSellCryptoAddresses() {
            bep20AddressElem.classList.add('hidden');
            trc20AddressElem.classList.add('hidden');
            erc20AddressElem.classList.add('hidden');
            binancePayIdElem.classList.add('hidden');
        }

        function toggleSellCryptoAddresses() {
            hideAllSellCryptoAddresses();
            const selectedNetwork = sellNetworkSelect.value;
            if (selectedNetwork) {
                if (selectedNetwork === 'bep20') {
                    bep20AddressElem.classList.remove('hidden');
                } else if (selectedNetwork === 'trc20') {
                    trc20AddressElem.classList.remove('hidden');
                } else if (selectedNetwork === 'erc20') {
                    erc20AddressElem.classList.remove('hidden');
                } else if (selectedNetwork === 'binance_pay') {
                    binancePayIdElem.classList.remove('hidden');
                }
            }
        }

        function calculateCommission(amount) {
            let commissionRate;
            let flatCommission = 0;

            if (amount < 100) {
                flatCommission = 1.65; // Fixed $1.65 for amounts less than $100
                commissionRate = 0; // No percentage
            } else if (amount <= 5000) {
                commissionRate = 0.01; // 1%
            } else {
                commissionRate = 0.0005; // 0.05%
            }

            let calculatedCommission = (amount * commissionRate) + flatCommission;
             // Ensure minimum 1.65% for amounts >= 100 USD (as per the first rule "1.65% من المبلغ الكامل بدءا من 100 دولار")
            if (amount >= 100 && calculatedCommission < (amount * 0.0165)) {
                calculatedCommission = amount * 0.0165;
            }
            return calculatedCommission;
        }

        function copyToClipboard(elementIdOrButton) {
            let textToCopy;
            let button;

            if (typeof elementIdOrButton === 'string') {
                const spanElement = document.getElementById(elementIdOrButton);
                if (spanElement) {
                    textToCopy = spanElement.textContent || spanElement.innerText;
                    button = spanElement.nextElementSibling; // Get the next sibling, which is the button
                }
            } else { // It's the button element itself
                button = elementIdOrButton;
                const spanElement = button.previousElementSibling;
                if (spanElement) {
                    textToCopy = spanElement.textContent || spanElement.innerText;
                }
            }

            if (textToCopy) {
                navigator.clipboard.writeText(textToCopy).then(() => {
                    if (button) {
                        const originalText = button.textContent;
                        button.textContent = 'تم النسخ!';
                        setTimeout(() => {
                            button.textContent = originalText;
                        }, 2000);
                    }
                }).catch(err => {
                    console.error('Failed to copy: ', err);
                    alert('فشل النسخ. الرجاء المحاولة يدويًا.');
                });
            }
        }

        function handleSubmit(event) {
            event.preventDefault(); // Prevent default form submission

            if (!form.checkValidity()) {
                alert('الرجاء تعبئة جميع الحقول المطلوبة.');
                return;
            }

            const fullName = document.getElementById('fullName').value;
            const phoneNumber = document.getElementById('phoneNumber').value;
            const city = document.getElementById('city').value;
            const transactionType = document.querySelector('input[name="transactionType"]:checked').value;

            let details = `معلومات المستخدم:\nالاسم: ${fullName}\nالهاتف: ${phoneNumber}\nالمدينة: ${city}\n\n`;
            let customerMessage = ``;
            let totalAmountSYP = 0;
            let cryptoAmount = 0;
            let networkFee = 0;
            let serviceCommission = 0;
            let netUSDT = 0;
            let usdtRate = SYP_EXCHANGE_RATE; // Current fixed rate

            if (transactionType === 'buy') {
                cryptoAmount = parseFloat(document.getElementById('buyAmount').value);
                const network = document.getElementById('buyNetwork').value;
                const address = document.getElementById('buyAddress').value;
                const note = document.getElementById('buyNote').value;
                const paymentMethod = document.getElementById('paymentMethodBuy').value;

                networkFee = NETWORK_FEES[network] || 0;
                serviceCommission = calculateCommission(cryptoAmount);
                const totalUSDT = cryptoAmount + networkFee + serviceCommission; // User pays for amount + network + service
                totalAmountSYP = totalUSDT * SYP_EXCHANGE_RATE;

                details += `نوع العملية: شراء USDT\n`;
                details += `الكمية المطلوبة (USDT): ${cryptoAmount}\n`;
                details += `شبكة الاستلام: ${network.toUpperCase()}\n`;
                details += `عنوان محفظتك: ${address}\n`;
                if (note) details += `ملاحظات: ${note}\n`;
                details += `طريقة الدفع (ليرة سورية): ${getPaymentMethodName(paymentMethod)}\n\n`;
                details += `تفاصيل الرسوم:\n`;
                details += `  - عمولة المنصة: ${serviceCommission.toFixed(2)} USDT\n`;
                details += `  - رسوم الشبكة (${network.toUpperCase()}): ${networkFee.toFixed(2)} USDT\n`;
                details += `المبلغ الإجمالي بالـ USDT (شامل العمولة والرسوم): ${totalUSDT.toFixed(2)} USDT\n`;
                details += `المبلغ المستحق للدفع (بالليرة السورية): ${totalAmountSYP.toFixed(2)} ل.س\n\n`;

                customerMessage = `<h3>تم إرسال طلب الشراء بنجاح!</h3>
                                    <p><strong>تفاصيل طلبك:</strong></p>
                                    <ul>
                                        <li>نوع العملية: <strong>شراء USDT</strong></li>
                                        <li>الكمية المطلوبة: <strong>${cryptoAmount} USDT</strong></li>
                                        <li>شبكة الاستلام: <strong>${network.toUpperCase()}</strong></li>
                                        <li>عمولة المنصة: <strong>${serviceCommission.toFixed(2)} USDT</strong></li>
                                        <li>رسوم الشبكة (${network.toUpperCase()}): <strong>${networkFee.toFixed(2)} USDT</strong></li>
                                        <li>المبلغ الإجمالي بالـ USDT الذي سيتم خصمه منك: <strong>${totalUSDT.toFixed(2)} USDT</strong></li>
                                        <li>المبلغ المستحق للدفع بالليرة السورية: <strong>${totalAmountSYP.toFixed(2)} ل.س</strong></li>
                                    </ul>
                                    <p>سيتم مراجعة طلبك والتواصل معك قريباً لإتمام العملية. يرجى التأكد من الدفع بالطريقة التي اخترتها.</p>`;

            } else if (transactionType === 'sell') {
                cryptoAmount = parseFloat(document.getElementById('sellAmount').value);
                const network = document.getElementById('sellNetwork').value;
                const receiveMethod = document.getElementById('receiveMethod').value;
                const bankAccount = document.getElementById('bankAccount').value;
                const shamCashAccount = document.getElementById('shamCashAccount').value;
                const note = document.getElementById('sellNote').value;

                networkFee = NETWORK_FEES[network] || 0;
                serviceCommission = calculateCommission(cryptoAmount);
                netUSDT = cryptoAmount - serviceCommission - networkFee; // User receives net after fees
                totalAmountSYP = netUSDT * SYP_EXCHANGE_RATE;

                details += `نوع العملية: بيع USDT\n`;
                details += `الكمية المراد بيعها (USDT): ${cryptoAmount}\n`;
                details += `شبكة الإرسال: ${network.toUpperCase()}\n`;
                details += `طريقة الاستلام (ليرة سورية): ${getPaymentMethodName(receiveMethod)}\n`;
                if (receiveMethod === 'bemo_bank') details += `رقم الحساب البنكي: ${bankAccount}\n`;
                if (receiveMethod === 'sham_cash') details += `رقم/عنوان حساب شام كاش: ${shamCashAccount}\n`;
                if (note) details += `ملاحظات: ${note}\n\n`;
                details += `تفاصيل الرسوم:\n`;
                details += `  - عمولة المنصة: ${serviceCommission.toFixed(2)} USDT\n`;
                details += `  - رسوم الشبكة (${network.toUpperCase()}): ${networkFee.toFixed(2)} USDT\n`;
                details += `المبلغ الصافي بالـ USDT بعد خصم العمولة والرسوم: ${netUSDT.toFixed(2)} USDT\n`;
                details += `المبلغ المتوقع استلامه (بالليرة السورية): ${totalAmountSYP.toFixed(2)} ل.س\n\n`;


                customerMessage = `<h3>تم إرسال طلب البيع بنجاح!</h3>
                                    <p><strong>تفاصيل طلبك:</strong></p>
                                    <ul>
                                        <li>نوع العملية: <strong>بيع USDT</strong></li>
                                        <li>الكمية المراد بيعها: <strong>${cryptoAmount} USDT</strong></li>
                                        <li>شبكة الإرسال: <strong>${network.toUpperCase()}</strong></li>
                                        <li>عمولة المنصة: <strong>${serviceCommission.toFixed(2)} USDT</strong></li>
                                        <li>رسوم الشبكة (${network.toUpperCase()}): <strong>${networkFee.toFixed(2)} USDT</strong></li>
                                        <li>المبلغ الصافي بالـ USDT الذي ستستلمه: <strong>${netUSDT.toFixed(2)} USDT</strong></li>
                                        <li>المبلغ المتوقع استلامه بالليرة السورية: <strong>${totalAmountSYP.toFixed(2)} ل.س</strong></li>
                                    </ul>
                                    <p>يرجى إرسال مبلغ USDT إلى العنوان الموضح في الخطوة الثالثة. سيتم مراجعة طلبك والتواصل معك قريباً بعد استلام التحويل.</p>`;
            }

            // Construct mailto link
            const subject = encodeURIComponent(`طلب تحويل USDT جديد من ${fullName}`);
            const body = encodeURIComponent(details);
            const mailtoLink = `mailto:alimahmoud001a@gmail.com?subject=${subject}&body=${body}`;

            // Display confirmation message and commission note
            confirmationMessageDiv.innerHTML = customerMessage;
            confirmationMessageDiv.style.display = 'block';
            commissionNoteDiv.classList.remove('hidden');

            // Open mailto link
            window.location.href = mailtoLink;

            // Optionally, reset form after submission if needed
            // form.reset();
            // toggleSections(); // Reset visibility
        }

        function getPaymentMethodName(value) {
            switch (value) {
                case 'syriatel_cash': return 'سيريتل كاش';
                case 'harram_transfer': return 'حوالة هرم';
                case 'bemo_bank': return 'بنك بيمو';
                case 'sham_cash': return 'شام كاش';
                default: return value;
            }
        }

        // Initial setup
        toggleSections(); // Hide sections on page load
    </script>
</body>
</html>
