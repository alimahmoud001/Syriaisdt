<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تحويل عملات رقمية USDT</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f4f4f4;
            color: #333;
            line-height: 1.6;
            margin: 20px;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1, h2 {
            color: #0056b3;
            text-align: center;
            margin-bottom: 20px;
        }
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
        }
        input[type="text"],
        input[type="tel"],
        input[type="number"],
        textarea,
        select {
            width: calc(100% - 22px);
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }
        input[type="radio"] {
            margin-left: 10px;
            margin-bottom: 15px;
        }
        .radio-group label {
            display: inline-block;
            margin-right: 20px;
        }
        button {
            background-color: #007bff;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            width: 100%;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #0056b3;
        }
        .section {
            background-color: #e9f7ff;
            border-left: 5px solid #007bff;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 5px;
        }
        .hidden {
            display: none;
        }
        .result-section {
            background-color: #d4edda;
            color: #155724;
            padding: 20px;
            border-radius: 5px;
            margin-top: 20px;
            border: 1px solid #c3e6cb;
            display: none; /* Hidden by default */
        }
        .result-section h3 {
            color: #155724;
        }
        .error-message {
            color: red;
            font-weight: bold;
            margin-bottom: 10px;
        }
        .note {
            font-size: 0.9em;
            color: #666;
            margin-top: 20px;
            padding-top: 10px;
            border-top: 1px dashed #ccc;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>خدمة تحويل العملات الرقمية</h1>
        <form id="cryptoForm">
            <div class="section">
                <h2>الخطوة الأولى: معلوماتك الشخصية</h2>
                <label for="fullName">الاسم الثلاثي:</label>
                <input type="text" id="fullName" name="fullName" required>

                <label for="phone">رقم الهاتف:</label>
                <input type="tel" id="phone" name="phone" required>

                <label for="city">المدينة:</label>
                <input type="text" id="city" name="city" required>
            </div>

            <div class="section">
                <h2>الخطوة الثانية: نوع العملية</h2>
                <label>ماذا تريد؟</label>
                <div class="radio-group">
                    <input type="radio" id="buy" name="transactionType" value="buy" required>
                    <label for="buy">شراء USDT</label>
                    <input type="radio" id="sell" name="transactionType" value="sell">
                    <label for="sell">بيع USDT</label>
                </div>
            </div>

            <div id="buySection" class="section hidden">
                <h2>شراء USDT</h2>
                <label for="buyAmount">الكمية المطلوبة (USDT):</label>
                <input type="number" id="buyAmount" name="buyAmount" min="1" step="0.01">
                <p class="error-message" id="buyAmountError"></p>

                <label for="buyNetwork">اختر الشبكة:</label>
                <select id="buyNetwork" name="buyNetwork">
                    <option value="">اختر شبكة</option>
                    <option value="bep20">BEP20</option>
                    <option value="trc20">TRC20</option>
                    <option value="erc20">ERC20</option>
                    <option value="binance_pay">Binance Pay</option>
                </select>

                <label for="buyAddress">عنوان استلام USDT (يكتبه المستخدم):</label>
                <input type="text" id="buyAddress" name="buyAddress">

                <label for="buyNote">ملاحظة (اختياري):</label>
                <textarea id="buyNote" name="buyNote" rows="3"></textarea>

                <label for="paymentMethodBuy">طريقة الدفع (بالليرة السورية):</label>
                <select id="paymentMethodBuy" name="paymentMethodBuy">
                    <option value="">اختر طريقة دفع</option>
                    <option value="sham_cash">شام كاش</option>
                    <option value="syriatel_cash">سيريتل كاش</option>
                    <option value="haram_transfer">حوالة الهرم</option>
                    <option value="bemo_bank">بنك بيمو</option>
                </select>

                <div id="buyPaymentDetails" class="section hidden">
                    <h3>تفاصيل الدفع المطلوبة:</h3>
                    <p id="buyPaymentInfo"></p>
                </div>
            </div>

            <div id="sellSection" class="section hidden">
                <h2>بيع USDT</h2>
                <label for="sellAmount">الكمية التي تريد بيعها (USDT):</label>
                <input type="number" id="sellAmount" name="sellAmount" min="1" step="0.01">
                <p class="error-message" id="sellAmountError"></p>

                <label for="sellNetwork">اختر الشبكة التي ستبيع منها:</label>
                <select id="sellNetwork" name="sellNetwork">
                    <option value="">اختر شبكة</option>
                    <option value="bep20">BEP20</option>
                    <option value="trc20">TRC20</option>
                    <option value="erc20">ERC20</option>
                    <option value="binance_pay">Binance Pay</option>
                </select>

                <div id="cryptoAddressSell" class="section hidden">
                    <h3>عنوان المحفظة المطلوب إرسال USDT إليها:</h3>
                    <p id="cryptoAddressInfo"></p>
                </div>

                <label for="paymentMethodSell">طريقة استلام المبلغ (بالليرة السورية):</label>
                <select id="paymentMethodSell" name="paymentMethodSell">
                    <option value="">اختر طريقة استلام</option>
                    <option value="syriatel_cash">سيريتل كاش</option>
                    <option value="haram_transfer">حوالة الهرم</option>
                    <option value="bemo_bank">بنك بيمو</option>
                    <option value="sham_cash">شام كاش</option>
                </select>

                <div id="sellPaymentDetailsInput" class="hidden">
                    <label for="bankAccountNum">رقم الحساب البنكي (لبنك بيمو):</label>
                    <input type="text" id="bankAccountNum" name="bankAccountNum">

                    <label for="shamCashDetails">رقم الحساب أو عنوان الحساب (لشام كاش):</label>
                    <input type="text" id="shamCashDetails" name="shamCashDetails">
                </div>

                <label for="sellNote">ملاحظة (اختياري):</label>
                <textarea id="sellNote" name="sellNote" rows="3"></textarea>
            </div>

            <button type="submit">إرسال الطلب</button>
        </form>

        <div id="resultSection" class="result-section">
            <h2>تم إرسال طلبك بنجاح!</h2>
            <p><strong>تفاصيل طلبك والعمولات:</strong></p>
            <div id="orderSummary"></div>
            <p class="note">ملاحظة: عمولة التسديد على طرق التحويل المختلفة بالليرة السورية تقع على المستخدم كما تحددها هذه الجهات.</p>
        </div>
    </div>

    <script>
        // افتراضي: سعر USDT مقابل الليرة السورية
        const USDT_TO_SYP_RATE = 14500; // مثال: 1 USDT = 14500 SYP (يجب تحديث هذا السعر ديناميكيا)

        // عمولات الشبكات (ثابتة)
        const NETWORK_FEES = {
            'trc20': 2,    // دولار
            'bep20': 0.15, // دولار
            'erc20': 0.3,  // دولار
            'binance_pay': 0   // دولار
        };

        // عناوين محفظة البائع (للحالة الثانية: بيع USDT)
        const SELLER_CRYPTO_ADDRESSES = {
            'bep20': '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            'trc20': 'TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX',
            'erc20': '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            'binance_pay': '969755964'
        };

        // تفاصيل الدفع للمشتري (للحالة الأولى: شراء USDT)
        const BUYER_PAYMENT_DETAILS = {
            'sham_cash': 'عنواني هو: be456e0ea9392db4d68a7093ee317bc8<br>رقم الحساب: 5991161126028260',
            'syriatel_cash': 'عنواني: 0934598967',
            'haram_transfer': 'التفاصيل هي:<br>علي ابراهيم محمود<br>0934598967<br>اللاذقية',
            'bemo_bank': 'التفاصيل هي:<br>علي ابراهيم محمود<br>060104947910013000000'
        };

        // Elements
        const transactionTypeRadios = document.querySelectorAll('input[name="transactionType"]');
        const buySection = document.getElementById('buySection');
        const sellSection = document.getElementById('sellSection');
        const buyAmountInput = document.getElementById('buyAmount');
        const sellAmountInput = document.getElementById('sellAmount');
        const buyAmountError = document.getElementById('buyAmountError');
        const sellAmountError = document.getElementById('sellAmountError');
        const buyNetworkSelect = document.getElementById('buyNetwork');
        const sellNetworkSelect = document.getElementById('sellNetwork');
        const cryptoAddressSellDiv = document.getElementById('cryptoAddressSell');
        const cryptoAddressInfo = document.getElementById('cryptoAddressInfo');
        const paymentMethodBuySelect = document.getElementById('paymentMethodBuy');
        const buyPaymentDetailsDiv = document.getElementById('buyPaymentDetails');
        const buyPaymentInfo = document.getElementById('buyPaymentInfo');
        const paymentMethodSellSelect = document.getElementById('paymentMethodSell');
        const sellPaymentDetailsInputDiv = document.getElementById('sellPaymentDetailsInput');
        const bankAccountNumInput = document.getElementById('bankAccountNum');
        const shamCashDetailsInput = document.getElementById('shamCashDetails');
        const resultSection = document.getElementById('resultSection');
        const orderSummary = document.getElementById('orderSummary');
        const cryptoForm = document.getElementById('cryptoForm');

        // Event Listeners
        transactionTypeRadios.forEach(radio => {
            radio.addEventListener('change', function() {
                if (this.value === 'buy') {
                    buySection.classList.remove('hidden');
                    sellSection.classList.add('hidden');
                    buyAmountInput.setAttribute('required', 'true');
                    sellAmountInput.removeAttribute('required');
                } else {
                    sellSection.classList.remove('hidden');
                    buySection.classList.add('hidden');
                    sellAmountInput.setAttribute('required', 'true');
                    buyAmountInput.removeAttribute('required');
                }
                // Reset any previous selections/displays
                buyPaymentDetailsDiv.classList.add('hidden');
                cryptoAddressSellDiv.classList.add('hidden');
                sellPaymentDetailsInputDiv.classList.add('hidden');
                buyAmountError.textContent = '';
                sellAmountError.textContent = '';
            });
        });

        buyAmountInput.addEventListener('input', validateBuyAmount);
        sellAmountInput.addEventListener('input', validateSellAmount);

        buyNetworkSelect.addEventListener('change', function() {
            // No dynamic update for buy network, just selected
        });

        sellNetworkSelect.addEventListener('change', function() {
            const selectedNetwork = this.value;
            if (selectedNetwork && SELLER_CRYPTO_ADDRESSES[selectedNetwork]) {
                cryptoAddressInfo.innerHTML = `<strong>${selectedNetwork.toUpperCase()}:</strong> ${SELLER_CRYPTO_ADDRESSES[selectedNetwork]}`;
                cryptoAddressSellDiv.classList.remove('hidden');
            } else {
                cryptoAddressSellDiv.classList.add('hidden');
            }
        });

        paymentMethodBuySelect.addEventListener('change', function() {
            const selectedMethod = this.value;
            if (selectedMethod && BUYER_PAYMENT_DETAILS[selectedMethod]) {
                buyPaymentInfo.innerHTML = BUYER_PAYMENT_DETAILS[selectedMethod];
                buyPaymentDetailsDiv.classList.remove('hidden');
            } else {
                buyPaymentDetailsDiv.classList.add('hidden');
            }
        });

        paymentMethodSellSelect.addEventListener('change', function() {
            const selectedMethod = this.value;
            bankAccountNumInput.removeAttribute('required');
            shamCashDetailsInput.removeAttribute('required');
            bankAccountNumInput.value = '';
            shamCashDetailsInput.value = '';

            if (selectedMethod === 'bemo_bank') {
                sellPaymentDetailsInputDiv.classList.remove('hidden');
                bankAccountNumInput.style.display = 'block';
                shamCashDetailsInput.style.display = 'none';
                bankAccountNumInput.setAttribute('required', 'true');
            } else if (selectedMethod === 'sham_cash') {
                sellPaymentDetailsInputDiv.classList.remove('hidden');
                shamCashDetailsInput.style.display = 'block';
                bankAccountNumInput.style.display = 'none';
                shamCashDetailsInput.setAttribute('required', 'true');
            } else {
                sellPaymentDetailsInputDiv.classList.add('hidden');
            }
        });

        function calculateCommission(amount, transactionType, network) {
            let commissionPercentage = 0;
            let fixedCommissionUSD = 0;
            let networkFee = NETWORK_FEES[network] || 0;

            if (amount < 100) {
                fixedCommissionUSD = 1.65;
            } else if (amount >= 100 && amount <= 5000) {
                commissionPercentage = 0.0165; // 1.65%
            } else { // amount > 5000
                commissionPercentage = 0.0005; // 0.05%
            }

            let commissionAmount = amount * commissionPercentage;
            if (fixedCommissionUSD > 0) {
                commissionAmount = fixedCommissionUSD;
            }
            
            // For selling, network fee is deducted from the USDT received.
            // For buying, network fee is added to the total cost.
            let totalCommission = commissionAmount + networkFee;

            return {
                baseCommissionUSD: commissionAmount,
                networkFeeUSD: networkFee,
                totalUSDCommission: totalCommission
            };
        }

        function validateBuyAmount() {
            const amount = parseFloat(buyAmountInput.value);
            if (isNaN(amount) || amount <= 0) {
                buyAmountError.textContent = 'الرجاء إدخال كمية صحيحة (أكبر من 0).';
                return false;
            } else {
                buyAmountError.textContent = '';
                return true;
            }
        }

        function validateSellAmount() {
            const amount = parseFloat(sellAmountInput.value);
            if (isNaN(amount) || amount <= 0) {
                sellAmountError.textContent = 'الرجاء إدخال كمية صحيحة (أكبر من 0).';
                return false;
            } else {
                sellAmountError.textContent = '';
                return true;
            }
        }

        cryptoForm.addEventListener('submit', function(event) {
            event.preventDefault(); // Prevent default form submission

            if (!cryptoForm.checkValidity()) {
                alert('الرجاء تعبئة جميع الحقول المطلوبة بشكل صحيح.');
                return;
            }

            const fullName = document.getElementById('fullName').value;
            const phone = document.getElementById('phone').value;
            const city = document.getElementById('city').value;
            const transactionType = document.querySelector('input[name="transactionType"]:checked').value;

            let orderDetails = {
                fullName,
                phone,
                city,
                transactionType
            };

            let totalUSDT = 0;
            let totalSYP = 0;
            let feesInfo = {};
            let paymentDetailsGiven = '';

            if (transactionType === 'buy') {
                totalUSDT = parseFloat(buyAmountInput.value);
                const buyNetwork = buyNetworkSelect.value;
                const buyAddress = document.getElementById('buyAddress').value;
                const buyNote = document.getElementById('buyNote').value;
                const paymentMethodBuy = paymentMethodBuySelect.value;

                if (!validateBuyAmount() || !buyNetwork || !buyAddress || !paymentMethodBuy) {
                    alert('الرجاء التأكد من تعبئة جميع حقول الشراء المطلوبة.');
                    return;
                }

                feesInfo = calculateCommission(totalUSDT, 'buy', buyNetwork);
                let totalUSDTWithFees = totalUSDT + feesInfo.totalUSDCommission; // Customer pays fees
                totalSYP = totalUSDTWithFees * USDT_TO_SYP_RATE;

                orderDetails = {
                    ...orderDetails,
                    buyAmount: totalUSDT,
                    buyNetwork,
                    buyAddress,
                    buyNote,
                    paymentMethodBuy,
                    totalUSDTToPay: totalUSDTWithFees.toFixed(2),
                    totalSYPToPay: totalSYP.toFixed(2),
                    commissionDetails: feesInfo
                };
                paymentDetailsGiven = BUYER_PAYMENT_DETAILS[paymentMethodBuy];

            } else { // sell
                totalUSDT = parseFloat(sellAmountInput.value);
                const sellNetwork = sellNetworkSelect.value;
                const sellNote = document.getElementById('sellNote').value;
                const paymentMethodSell = paymentMethodSellSelect.value;
                const bankAccountNum = document.getElementById('bankAccountNum').value;
                const shamCashDetails = document.getElementById('shamCashDetails').value;

                if (!validateSellAmount() || !sellNetwork || !paymentMethodSell ||
                    (paymentMethodSell === 'bemo_bank' && !bankAccountNum) ||
                    (paymentMethodSell === 'sham_cash' && !shamCashDetails)) {
                    alert('الرجاء التأكد من تعبئة جميع حقول البيع المطلوبة.');
                    return;
                }

                feesInfo = calculateCommission(totalUSDT, 'sell', sellNetwork);
                let receivedUSDTAfterFees = totalUSDT - feesInfo.totalUSDCommission; // Fees deducted from user
                totalSYP = receivedUSDTAfterFees * USDT_TO_SYP_RATE;

                orderDetails = {
                    ...orderDetails,
                    sellAmount: totalUSDT,
                    sellNetwork,
                    sellNote,
                    paymentMethodSell,
                    receivedUSDTAfterFees: receivedUSDTAfterFees.toFixed(2),
                    receivedSYP: totalSYP.toFixed(2),
                    commissionDetails: feesInfo
                };
                orderDetails.sellerCryptoAddress = SELLER_CRYPTO_ADDRESSES[sellNetwork];
                if (paymentMethodSell === 'bemo_bank') {
                    orderDetails.bankAccountNum = bankAccountNum;
                } else if (paymentMethodSell === 'sham_cash') {
                    orderDetails.shamCashDetails = shamCashDetails;
                }
            }

            // Display results to user
            let summaryHTML = `<p><strong>الاسم:</strong> ${fullName}</p>`;
            summaryHTML += `<p><strong>الهاتف:</strong> ${phone}</p>`;
            summaryHTML += `<p><strong>المدينة:</strong> ${city}</p>`;
            summaryHTML += `<p><strong>نوع العملية:</strong> ${transactionType === 'buy' ? 'شراء USDT' : 'بيع USDT'}</p>`;

            if (transactionType === 'buy') {
                summaryHTML += `<p><strong>الكمية المطلوبة (USDT):</strong> ${orderDetails.buyAmount} USDT</p>`;
                summaryHTML += `<p><strong>الشبكة:</strong> ${orderDetails.buyNetwork.toUpperCase()}</p>`;
                summaryHTML += `<p><strong>عنوان استلام USDT:</strong> ${orderDetails.buyAddress}</p>`;
                summaryHTML += `<p><strong>طريقة الدفع (ليرة سورية):</strong> ${orderDetails.paymentMethodBuy === 'sham_cash' ? 'شام كاش' : orderDetails.paymentMethodBuy === 'syriatel_cash' ? 'سيريتل كاش' : orderDetails.paymentMethodBuy === 'haram_transfer' ? 'حوالة الهرم' : 'بنك بيمو'}</p>`;
                summaryHTML += `<p><strong>العمولة الأساسية (دولار):</strong> ${feesInfo.baseCommissionUSD.toFixed(2)} $</p>`;
                summaryHTML += `<p><strong>عمولة الشبكة (دولار):</strong> ${feesInfo.networkFeeUSD.toFixed(2)} $</p>`;
                summaryHTML += `<p><strong>إجمالي العمولة بالدولار:</strong> ${feesInfo.totalUSDCommission.toFixed(2)} $</p>`;
                summaryHTML += `<p><strong>إجمالي ما ستدفعه (USDT):</strong> ${orderDetails.totalUSDTToPay} USDT</p>`;
                summaryHTML += `<p><strong>المبلغ المطلوب دفعه بالليرة السورية:</strong> ${orderDetails.totalSYPToPay} ل.س</p>`;
                if (paymentDetailsGiven) {
                    summaryHTML += `<div style="border-top: 1px dashed #ccc; padding-top: 10px; margin-top: 15px;">`;
                    summaryHTML += `<h4>تفاصيل الدفع لإتمام عملية الشراء:</h4>`;
                    summaryHTML += `<p>${paymentDetailsGiven}</p></div>`;
                }
            } else { // sell
                summaryHTML += `<p><strong>الكمية التي تبيعها (USDT):</strong> ${orderDetails.sellAmount} USDT</p>`;
                summaryHTML += `<p><strong>الشبكة التي تبيع منها:</strong> ${orderDetails.sellNetwork.toUpperCase()}</p>`;
                summaryHTML += `<p><strong>عنوان محفظتنا لاستلام USDT:</strong> ${orderDetails.sellerCryptoAddress}</p>`;
                summaryHTML += `<p><strong>طريقة استلام المبلغ (ليرة سورية):</strong> ${orderDetails.paymentMethodSell === 'syriatel_cash' ? 'سيريتل كاش' : orderDetails.paymentMethodSell === 'haram_transfer' ? 'حوالة الهرم' : orderDetails.paymentMethodSell === 'bemo_bank' ? 'بنك بيمو' : 'شام كاش'}</p>`;
                if (orderDetails.bankAccountNum) {
                    summaryHTML += `<p><strong>رقم الحساب البنكي:</strong> ${orderDetails.bankAccountNum}</p>`;
                }
                if (orderDetails.shamCashDetails) {
                    summaryHTML += `<p><strong>رقم/عنوان حساب شام كاش:</strong> ${orderDetails.shamCashDetails}</p>`;
                }
                summaryHTML += `<p><strong>العمولة الأساسية (دولار):</strong> ${feesInfo.baseCommissionUSD.toFixed(2)} $</p>`;
                summaryHTML += `<p><strong>عمولة الشبكة (دولار):</strong> ${feesInfo.networkFeeUSD.toFixed(2)} $</p>`;
                summaryHTML += `<p><strong>إجمالي العمولة بالدولار:</strong> ${feesInfo.totalUSDCommission.toFixed(2)} $</p>`;
                summaryHTML += `<p><strong>صافي USDT التي ستستلمها بعد العمولات:</strong> ${orderDetails.receivedUSDTAfterFees} USDT</p>`;
                summaryHTML += `<p><strong>المبلغ الذي ستستلمه بالليرة السورية:</strong> ${orderDetails.receivedSYP} ل.س</p>`;
            }

            orderSummary.innerHTML = summaryHTML;
            resultSection.style.display = 'block';

            // Scroll to the result section
            resultSection.scrollIntoView({ behavior: 'smooth' });


            // --- Backend Integration Placeholder ---
            // This is where you would send the 'orderDetails' object to your server-side script
            // (e.g., PHP, Node.js) to send the email.
            // Example using fetch API (requires a server-side endpoint):
            /*
            fetch('your_server_endpoint_to_send_email.php', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify(orderDetails),
            })
            .then(response => response.json())
            .then(data => {
                console.log('Success:', data);
                // Optionally show a success message or redirect
            })
            .catch((error) => {
                console.error('Error:', error);
                // Handle error (e.g., show error message to user)
            });
            */
            // For demonstration, we'll just log it to console.
            console.log("Order Details to be sent:", orderDetails);
        });

    </script>
</body>
</html>
