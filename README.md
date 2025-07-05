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
        .step-section {
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
    </style>
</head>
<body>
    <div class="container">
        <h1>خدمة تحويل العملات الرقمية (USDT)</h1>
        <h2>مرحباً بك في خدمة تحويل USDT في سوريا</h2>

        <div id="step1" class="step-section">
            <h2>الخطوة 1: معلوماتك الشخصية</h2>
            <label for="fullName">الاسم الثلاثي:</label>
            <input type="text" id="fullName" name="fullName" required>

            <label for="phoneNumber">رقم الهاتف:</label>
            <input type="tel" id="phoneNumber" name="phoneNumber" required>

            <label for="city">المدينة:</label>
            <input type="text" id="city" name="city" required>

            <button onclick="nextStep(2)">التالي</button>
        </div>

        <div id="step2" class="step-section hidden">
            <h2>الخطوة 2: ما الذي ترغب بفعله؟</h2>
            <div class="radio-group">
                <input type="radio" id="buy" name="transactionType" value="buy" onchange="showTransactionFields()">
                <label for="buy">شراء USDT</label>

                <input type="radio" id="sell" name="transactionType" value="sell" onchange="showTransactionFields()">
                <label for="sell">بيع USDT</label>
            </div>

            <div id="buyFields" class="hidden">
                <label for="usdtQuantity">الكمية المطلوبة (USDT):</label>
                <input type="number" id="usdtQuantity" name="usdtQuantity" step="0.01" min="1" required>

                <label for="network">اختر الشبكة:</label>
                <select id="network" name="network" required>
                    <option value="">اختر شبكة</option>
                    <option value="bep20">BEP20</option>
                    <option value="trc20">TRC20</option>
                    <option value="erc20">ERC20</option>
                    <option value="binancepay">Binance Pay</option>
                </select>

                <label for="walletAddress">عنوان المحفظة (الذي ستستقبل عليه USDT):</label>
                <input type="text" id="walletAddress" name="walletAddress" required>

                <label for="buyNote">ملاحظة (اختياري):</label>
                <textarea id="buyNote" name="buyNote" rows="3"></textarea>
            </div>

            <div id="sellFields" class="hidden">
                <label for="sellQuantity">الكمية التي تريد بيعها (USDT):</label>
                <input type="number" id="sellQuantity" name="sellQuantity" step="0.01" min="1" required>

                <label for="paymentMethod">اختر طريقة استلام المبلغ (الليرة السورية):</label>
                <select id="paymentMethod" name="paymentMethod" onchange="showPaymentDetailsField()" required>
                    <option value="">اختر طريقة الدفع</option>
                    <option value="syriatelCash">سيريتل كاش</option>
                    <option value="haramTransfer">حوالة الهرم</option>
                    <option value="bemoBank">بنك بيمو</option>
                    <option value="shamCash">شام كاش</option>
                </select>

                <div id="paymentDetails" class="hidden">
                    <label for="accountInfo">رقم الحساب البنكي / عنوان الحساب (حسب الطريقة المختارة):</label>
                    <input type="text" id="accountInfo" name="accountInfo">
                </div>

                <label for="sellNote">ملاحظة (اختياري):</label>
                <textarea id="sellNote" name="sellNote" rows="3"></textarea>
            </div>

            <button onclick="nextStep(3)">متابعة</button>
        </div>

        <div id="step3" class="step-section hidden">
            <h2>الخطوة 3: إتمام طلبك</h2>
            <div id="paymentInstructions">
                </div>
            <button onclick="submitOrder()">تأكيد وإرسال الطلب</button>
        </div>

        <div id="output" class="hidden"></div>
    </div>

    <script>
        const exchangeRate = 14500; // مثال: سعر صرف 1 USDT = 14500 ليرة سورية (يمكن تحديثه)

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

        function showPaymentDetailsField() {
            const paymentMethod = document.getElementById('paymentMethod').value;
            const paymentDetailsDiv = document.getElementById('paymentDetails');
            const accountInfoInput = document.getElementById('accountInfo');

            if (paymentMethod === 'bemoBank' || paymentMethod === 'shamCash') {
                paymentDetailsDiv.classList.remove('hidden');
                accountInfoInput.setAttribute('required', 'required');
                if (paymentMethod === 'bemoBank') {
                    accountInfoInput.placeholder = "أدخل رقم الحساب البنكي لبنك بيمو";
                } else {
                    accountInfoInput.placeholder = "أدخل رقم الحساب أو عنوان الحساب لشام كاش";
                }
            } else {
                paymentDetailsDiv.classList.add('hidden');
                accountInfoInput.removeAttribute('required');
                accountInfoInput.value = ''; // Clear previous input
            }
        }

        function calculateTransactionFee(amount) {
            if (amount < 100) {
                return 1.65; // 1.65 دولار ثابت
            } else if (amount >= 100 && amount <= 5000) {
                return amount * 0.01; // 1% من المبلغ
            } else { // amount > 5000
                return amount * 0.0005; // 0.05% من المبلغ
            }
        }

        function getNetworkFee(network) {
            switch (network) {
                case 'trc20':
                    return 2;
                case 'bep20':
                    return 0.15;
                case 'erc20': // Based on the user's prompt, ERC20 fee is listed as TRC20, needs clarification, assuming 0.3 for now based on context.
                    return 0.3;
                case 'binancepay':
                    return 0;
                default:
                    return 0;
            }
        }

        function nextStep(step) {
            if (step === 2) {
                const fullName = document.getElementById('fullName').value;
                const phoneNumber = document.getElementById('phoneNumber').value;
                const city = document.getElementById('city').value;

                if (!fullName || !phoneNumber || !city) {
                    alert('الرجاء ملء جميع الحقول المطلوبة في الخطوة الأولى.');
                    return;
                }
                document.getElementById('step1').classList.add('hidden');
                document.getElementById('step2').classList.remove('hidden');
            } else if (step === 3) {
                const transactionType = document.querySelector('input[name="transactionType"]:checked');
                if (!transactionType) {
                    alert('الرجاء اختيار نوع المعاملة (شراء أو بيع).');
                    return;
                }

                const paymentInstructionsDiv = document.getElementById('paymentInstructions');
                paymentInstructionsDiv.innerHTML = ''; // Clear previous instructions

                if (transactionType.value === 'buy') {
                    const usdtQuantity = parseFloat(document.getElementById('usdtQuantity').value);
                    const network = document.getElementById('network').value;
                    const walletAddress = document.getElementById('walletAddress').value;

                    if (!usdtQuantity || !network || !walletAddress) {
                        alert('الرجاء ملء جميع الحقول المطلوبة للشراء.');
                        return;
                    }

                    // Display payment options for buying USDT
                    paymentInstructionsDiv.innerHTML = `
                        <h3>لإتمام عملية شراء USDT، يرجى التحويل إلى أحد العناوين التالية:</h3>
                        <p><strong>إذا اخترت الدفع عبر شام كاش:</strong></p>
                        <p><strong>عنوان المحفظة (USDT):</strong> <code>be456e0ea9392db4d68a7093ee317bc8</code></p>
                        <p><strong>رقم الحساب:</strong> <code>5991161126028260</code></p>
                        <hr>
                        <p><strong>إذا اخترت الدفع عبر سيريتل كاش:</strong></p>
                        <p><strong>عنوان المحفظة (USDT):</strong> <code>0934598967</code></p>
                        <hr>
                        <p><strong>إذا اخترت الدفع عبر حوالة الهرم:</strong></p>
                        <p><strong>التفاصيل:</strong></p>
                        <ul>
                            <li><strong>الاسم:</strong> علي ابراهيم محمود</li>
                            <li><strong>رقم الهاتف:</strong> 0934598967</li>
                            <li><strong>المدينة:</strong> اللاذقية</li>
                        </ul>
                        <hr>
                        <p><strong>إذا اخترت الدفع عبر بنك بيمو:</strong></p>
                        <p><strong>التفاصيل:</strong></p>
                        <ul>
                            <li><strong>الاسم:</strong> علي ابراهيم محمود</li>
                            <li><strong>رقم الحساب:</strong> 060104947910013000000</li>
                        </ul>
                    `;

                } else if (transactionType.value === 'sell') {
                    const sellQuantity = parseFloat(document.getElementById('sellQuantity').value);
                    const paymentMethod = document.getElementById('paymentMethod').value;
                    const accountInfo = document.getElementById('accountInfo').value;

                    if (!sellQuantity || !paymentMethod) {
                        alert('الرجاء ملء جميع الحقول المطلوبة للبيع.');
                        return;
                    }
                     if ((paymentMethod === 'bemoBank' || paymentMethod === 'shamCash') && !accountInfo) {
                        alert('الرجاء إدخال تفاصيل الحساب للدفع.');
                        return;
                    }

                    // Display crypto addresses for selling USDT
                    paymentInstructionsDiv.innerHTML = `
                        <h3>لإتمام عملية بيع USDT، يرجى إرسال USDT إلى أحد العناوين التالية:</h3>
                        <p><strong>شبكة BEP20:</strong> <code>0x21802218d8d661d66F2C7959347a6382E1cc614F</code></p>
                        <p><strong>شبكة TRC20:</strong> <code>TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX</code></p>
                        <p><strong>شبكة ERC20:</strong> <code>0x21802218d8d661d66F2C7959347a6382E1cc614F</code></p>
                        <p><strong>Binance Pay ID:</strong> <code>969755964</code></p>
                        <p class="note">يرجى التأكد من اختيار الشبكة الصحيحة عند الإرسال لتجنب فقدان أموالك.</p>
                    `;
                }

                document.getElementById('step2').classList.add('hidden');
                document.getElementById('step3').classList.remove('hidden');
            }
        }

        function submitOrder() {
            const fullName = document.getElementById('fullName').value;
            const phoneNumber = document.getElementById('phoneNumber').value;
            const city = document.getElementById('city').value;
            const transactionType = document.querySelector('input[name="transactionType"]:checked').value;

            let details = `طلب جديد:\n`;
            details += `الاسم الثلاثي: ${fullName}\n`;
            details += `رقم الهاتف: ${phoneNumber}\n`;
            details += `المدينة: ${city}\n`;
            details += `نوع المعاملة: ${transactionType === 'buy' ? 'شراء USDT' : 'بيع USDT'}\n`;

            let usdtAmount = 0;
            let transactionFee = 0;
            let networkFee = 0;
            let totalUsdtCost = 0; // for buy
            let totalSyrianLiraReceived = 0; // for sell
            let paymentMethodDetails = '';

            if (transactionType === 'buy') {
                usdtAmount = parseFloat(document.getElementById('usdtQuantity').value);
                const network = document.getElementById('network').value;
                const walletAddress = document.getElementById('walletAddress').value;
                const buyNote = document.getElementById('buyNote').value;

                transactionFee = calculateTransactionFee(usdtAmount);
                networkFee = getNetworkFee(network);
                totalUsdtCost = usdtAmount + networkFee; // Customer pays USDT amount + network fee
                const totalUsdtCostWithServiceFee = totalUsdtCost + transactionFee; // Total USDT including all fees to be covered by the user, for Lira calculation.

                details += `الكمية المطلوبة (USDT): ${usdtAmount}\n`;
                details += `الشبكة المختارة: ${network}\n`;
                details += `عنوان المحفظة: ${walletAddress}\n`;
                details += `ملاحظة (شراء): ${buyNote || 'لا يوجد'}\n`;
                details += `\n--- تفاصيل العمولة ---\n`;
                details += `عمولة الخدمة: ${transactionFee.toFixed(2)} USDT\n`;
                details += `عمولة الشبكة (${network}): ${networkFee.toFixed(2)} USDT\n`;
                details += `إجمالي USDT المطلوب للدفع (يشمل عمولة الشبكة): ${totalUsdtCost.toFixed(2)} USDT\n`;
                details += `المبلغ الإجمالي بالليرة السورية للدفع (تقريبي): ${(totalUsdtCostWithServiceFee * exchangeRate).toFixed(2)} ل.س\n`; // Add service fee for Lira calculation
            } else { // sell
                usdtAmount = parseFloat(document.getElementById('sellQuantity').value);
                const paymentMethod = document.getElementById('paymentMethod').value;
                const accountInfo = document.getElementById('accountInfo').value;
                const sellNote = document.getElementById('sellNote').value;

                transactionFee = calculateTransactionFee(usdtAmount);
                // For selling, network fee is usually on the sender, but if it affects amount received, consider it.
                // Assuming customer sends USDT, network fee is for sending.
                // Let's assume for selling, the network fee is implicitly covered by sender, and we calculate what they receive.
                // The prompt for sell asks for "طريقة الاستلام" and then lists crypto addresses. This implies the user is SENDING to us.
                // So, the network fee is on their side. Our service fee applies to the received amount.
                // We don't apply network fee for calculation from our side for selling.

                totalSyrianLiraReceived = (usdtAmount - transactionFee) * exchangeRate;

                details += `الكمية المراد بيعها (USDT): ${usdtAmount}\n`;
                details += `طريقة استلام المبلغ: ${paymentMethod}\n`;
                if (paymentMethod === 'bemoBank') {
                    paymentMethodDetails = `رقم الحساب البنكي: ${accountInfo}`;
                } else if (paymentMethod === 'shamCash') {
                    paymentMethodDetails = `رقم الحساب أو عنوان الحساب: ${accountInfo}`;
                } else if (paymentMethod === 'syriatelCash') {
                    paymentMethodDetails = `رقم هاتف سيريتل كاش: ${phoneNumber}`; // Assuming it's their phone number
                } else if (paymentMethod === 'haramTransfer') {
                     paymentMethodDetails = `معلومات حوالة الهرم: ${fullName}, ${phoneNumber}, ${city}`;
                }
                details += `تفاصيل استلام المبلغ: ${paymentMethodDetails}\n`;
                details += `ملاحظة (بيع): ${sellNote || 'لا يوجد'}\n`;
                details += `\n--- تفاصيل العمولة ---\n`;
                details += `عمولة الخدمة: ${transactionFee.toFixed(2)} USDT\n`;
                details += `المبلغ الصافي بالليرة السورية المستلم (تقريبي): ${totalSyrianLiraReceived.toFixed(2)} ل.س\n`;
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
            document.getElementById('step3').classList.add('hidden');

            // Send email
            sendEmail(details);
        }

        function sendEmail(details) {
            const subject = "طلب تحويل عملات رقمية جديد من موقعك";
            const body = encodeURIComponent(details);
            const mailtoLink = `mailto:alimahmoud001a@gmail.com?subject=${subject}&body=${body}`;

            // This will open the user's default email client.
            // For a fully automated server-side email sending, you would need a backend.
            // As this is a pure HTML/JS frontend, we rely on mailto.
            window.location.href = mailtoLink;
        }
    </script>
</body>
</html>
