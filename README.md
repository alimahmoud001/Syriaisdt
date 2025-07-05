# Syriausdt

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام تحويل العملات الرقمية في سورية</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --success: #27ae60;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #2c3e50);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            font-family: 'Tajawal', sans-serif;
            color: #333;
            min-height: 100vh;
            padding-bottom: 60px;
        }
        
        @keyframes gradientBG {
            0% { background-position: 0% 50% }
            50% { background-position: 100% 50% }
            100% { background-position: 0% 50% }
        }
        
        .card {
            border-radius: 15px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            border: none;
            transition: transform 0.3s ease;
            background: rgba(255, 255, 255, 0.95);
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .step {
            display: none;
        }
        
        .step.active {
            display: block;
            animation: fadeIn 0.5s;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .btn-primary {
            background-color: var(--secondary);
            border: none;
            padding: 10px 25px;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .btn-primary:hover {
            background-color: var(--primary);
            transform: scale(1.05);
        }
        
        .btn-outline-primary {
            color: var(--secondary);
            border-color: var(--secondary);
        }
        
        .btn-outline-primary:hover {
            background-color: var(--secondary);
            color: white;
        }
        
        .payment-method {
            cursor: pointer;
            border: 2px solid #ddd;
            border-radius: 10px;
            padding: 15px;
            margin-bottom: 15px;
            transition: all 0.3s;
            background: white;
        }
        
        .payment-method:hover, .payment-method.selected {
            border-color: var(--secondary);
            background-color: rgba(52, 152, 219, 0.1);
            transform: translateY(-3px);
        }
        
        .payment-method i {
            font-size: 2rem;
            margin-bottom: 10px;
            color: var(--secondary);
        }
        
        .summary-item {
            border-bottom: 1px dashed #ddd;
            padding: 10px 0;
        }
        
        .summary-item:last-child {
            border-bottom: none;
        }
        
        .fee-badge {
            background-color: var(--accent);
            color: white;
            padding: 5px 10px;
            border-radius: 20px;
            font-size: 0.85rem;
        }
        
        .logo {
            font-weight: 800;
            color: white;
            text-shadow: 0 2px 4px rgba(0,0,0,0.3);
        }
        
        .logo span {
            color: var(--secondary);
        }
        
        .header {
            background: rgba(44, 62, 80, 0.9);
            border-radius: 0 0 20px 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        }
        
        .form-control, .form-select {
            border-radius: 10px;
            padding: 12px 15px;
            border: 2px solid #ddd;
            transition: all 0.3s;
        }
        
        .form-control:focus, .form-select:focus {
            border-color: var(--secondary);
            box-shadow: 0 0 0 0.25rem rgba(52, 152, 219, 0.25);
        }
        
        .note-box {
            background-color: #fff9e6;
            border-left: 4px solid #ffc107;
            padding: 15px;
            border-radius: 0 10px 10px 0;
            margin: 20px 0;
        }
        
        .progress-container {
            margin: 30px 0;
        }
        
        .progress-bar {
            background-color: var(--secondary);
            height: 10px;
            border-radius: 5px;
        }
        
        .step-title {
            position: relative;
            padding-bottom: 15px;
            margin-bottom: 25px;
            border-bottom: 2px solid var(--secondary);
        }
        
        .step-title::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            width: 80px;
            height: 4px;
            background: var(--accent);
            border-radius: 2px;
        }
        
        .receiving-details {
            background: #f8f9fa;
            border-radius: 10px;
            padding: 20px;
            margin-top: 20px;
            border-left: 4px solid var(--success);
        }
        
        .receiving-details h5 {
            color: var(--success);
        }
        
        .crypto-address {
            word-break: break-all;
            font-family: monospace;
            background: #2c3e50;
            color: white;
            padding: 10px;
            border-radius: 5px;
        }
        
        footer {
            position: fixed;
            bottom: 0;
            width: 100%;
            background: rgba(44, 62, 80, 0.95);
            color: white;
            padding: 10px 0;
            text-align: center;
        }
        
        .transaction-type-btn {
            height: 150px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            font-size: 1.2rem;
            font-weight: bold;
        }
        
        @media (max-width: 768px) {
            .transaction-type-btn {
                height: 120px;
                font-size: 1rem;
            }
            
            .payment-method {
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="header py-3 mb-4">
        <div class="container">
            <div class="d-flex justify-content-between align-items-center">
                <h1 class="logo">Syria<span>Coin</span> Exchange</h1>
                <div class="d-flex align-items-center">
                    <div class="me-3">
                        <div class="text-white"><i class="fas fa-dollar-sign me-1"></i> <span id="rate-display">1 USDT = 14,500 SYP</span></div>
                    </div>
                    <div class="bg-success text-white px-2 py-1 rounded">
                        <i class="fas fa-check-circle me-1"></i> آمن
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="container">
        <div class="row justify-content-center">
            <div class="col-lg-8">
                <div class="card p-4 mb-4">
                    <div class="progress-container">
                        <div class="d-flex justify-content-between mb-2">
                            <span class="step-indicator" data-step="1">المعلومات الشخصية</span>
                            <span class="step-indicator" data-step="2">نوع العملية</span>
                            <span class="step-indicator" data-step="3">التفاصيل</span>
                            <span class="step-indicator" data-step="4">الملخص</span>
                        </div>
                        <div class="progress" style="height: 10px;">
                            <div class="progress-bar" id="progress-bar" role="progressbar" style="width: 25%;"></div>
                        </div>
                    </div>

                    <!-- الخطوة الأولى: المعلومات الشخصية -->
                    <div id="step1" class="step active">
                        <h3 class="step-title">المعلومات الشخصية</h3>
                        <p class="text-muted mb-4">الرجاء إدخال معلوماتك الأساسية للبدء</p>
                        
                        <div class="mb-3">
                            <label for="fullName" class="form-label">الاسم الثلاثي</label>
                            <input type="text" class="form-control" id="fullName" placeholder="أدخل اسمك الكامل">
                        </div>
                        
                        <div class="mb-3">
                            <label for="phone" class="form-label">رقم الهاتف</label>
                            <input type="tel" class="form-control" id="phone" placeholder="09xxxxxxxx">
                        </div>
                        
                        <div class="mb-4">
                            <label for="city" class="form-label">المدينة</label>
                            <select class="form-select" id="city">
                                <option selected disabled>اختر مدينتك</option>
                                <option>دمشق</option>
                                <option>حلب</option>
                                <option>حمص</option>
                                <option>اللاذقية</option>
                                <option>حماة</option>
                                <option>طرطوس</option>
                                <option>درعا</option>
                                <option>السويداء</option>
                                <option>القنيطرة</option>
                            </select>
                        </div>
                        
                        <div class="d-flex justify-content-end">
                            <button class="btn btn-primary" onclick="nextStep(2)">التالي <i class="fas fa-arrow-left ms-2"></i></button>
                        </div>
                    </div>

                    <!-- الخطوة الثانية: نوع العملية -->
                    <div id="step2" class="step">
                        <h3 class="step-title">نوع العملية</h3>
                        <p class="text-muted mb-4">اختر العملية التي ترغب في إتمامها</p>
                        
                        <div class="row mb-4">
                            <div class="col-md-6 mb-3">
                                <div class="card text-center transaction-type-btn" onclick="selectTransactionType('buy')">
                                    <div class="card-body">
                                        <i class="fas fa-shopping-cart fa-2x mb-3 text-success"></i>
                                        <h5>شراء USDT</h5>
                                        <p class="mb-0">(دفع بالليرة السورية)</p>
                                    </div>
                                </div>
                            </div>
                            <div class="col-md-6 mb-3">
                                <div class="card text-center transaction-type-btn" onclick="selectTransactionType('sell')">
                                    <div class="card-body">
                                        <i class="fas fa-coins fa-2x mb-3 text-warning"></i>
                                        <h5>بيع USDT</h5>
                                        <p class="mb-0">(استلام بالليرة السورية)</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <div class="d-flex justify-content-between">
                            <button class="btn btn-outline-primary" onclick="prevStep(1)"><i class="fas fa-arrow-right me-2"></i> السابق</button>
                        </div>
                    </div>

                    <!-- الخطوة الثالثة: تفاصيل الشراء -->
                    <div id="step3-buy" class="step">
                        <h3 class="step-title">تفاصيل شراء USDT</h3>
                        <p class="text-muted mb-4">الرجاء تعبئة تفاصيل طلب الشراء</p>
                        
                        <div class="mb-3">
                            <label for="buyAmount" class="form-label">الكمية المطلوبة (USDT)</label>
                            <input type="number" class="form-control" id="buyAmount" placeholder="أدخل الكمية" min="1" step="0.01" oninput="calculateFees()">
                        </div>
                        
                        <div class="mb-3">
                            <label for="network" class="form-label">اختر الشبكة</label>
                            <select class="form-select" id="network" onchange="calculateFees()">
                                <option value="bep20">BEP20</option>
                                <option value="trc20">TRC20</option>
                                <option value="erc20">ERC20</option>
                                <option value="binance">Binance Pay</option>
                            </select>
                        </div>
                        
                        <div class="mb-3">
                            <label for="walletAddress" class="form-label">العنوان المحفظة</label>
                            <input type="text" class="form-control" id="walletAddress" placeholder="أدخل عنوان محفظتك">
                        </div>
                        
                        <div class="mb-4">
                            <label for="buyNotes" class="form-label">ملاحظات (اختياري)</label>
                            <textarea class="form-control" id="buyNotes" rows="3" placeholder="أي ملاحظات إضافية"></textarea>
                        </div>
                        
                        <div class="fee-summary mb-4 p-3 bg-light rounded">
                            <h5>تفاصيل التكلفة</h5>
                            <div class="d-flex justify-content-between mb-2">
                                <span>مبلغ USDT:</span>
                                <span id="amount-display">0.00 USDT</span>
                            </div>
                            <div class="d-flex justify-content-between mb-2">
                                <span>عمولة الخدمة:</span>
                                <span id="service-fee">0.00 USDT</span>
                            </div>
                            <div class="d-flex justify-content-between mb-2">
                                <span>عمولة الشبكة:</span>
                                <span id="network-fee">0.00 USDT</span>
                            </div>
                            <div class="d-flex justify-content-between fw-bold">
                                <span>المبلغ الإجمالي:</span>
                                <span id="total-amount">0.00 USDT</span>
                            </div>
                        </div>
                        
                        <div class="d-flex justify-content-between">
                            <button class="btn btn-outline-primary" onclick="prevStep(2)"><i class="fas fa-arrow-right me-2"></i> السابق</button>
                            <button class="btn btn-primary" onclick="nextStep(4)">التالي <i class="fas fa-arrow-left ms-2"></i></button>
                        </div>
                    </div>

                    <!-- الخطوة الثالثة: تفاصيل البيع -->
                    <div id="step3-sell" class="step">
                        <h3 class="step-title">تفاصيل بيع USDT</h3>
                        <p class="text-muted mb-4">الرجاء تعبئة تفاصيل طلب البيع</p>
                        
                        <div class="mb-3">
                            <label for="sellAmount" class="form-label">الكمية المراد بيعها (USDT)</label>
                            <input type="number" class="form-control" id="sellAmount" placeholder="أدخل الكمية" min="1" step="0.01" oninput="calculateFees()">
                        </div>
                        
                        <div class="mb-3">
                            <label for="receiveMethod" class="form-label">طريقة الاستلام</label>
                            <div class="row">
                                <!-- سيريتل كاش -->
                                <div class="col-md-6 mb-3">
                                    <div class="payment-method" onclick="selectPaymentMethod('syrTel')">
                                        <i class="fas fa-mobile-alt"></i>
                                        <h5>سيريتل كاش</h5>
                                        <p>تحويل إلى رقم الجوال</p>
                                    </div>
                                </div>
                                
                                <!-- حوالة الهرم -->
                                <div class="col-md-6 mb-3">
                                    <div class="payment-method" onclick="selectPaymentMethod('haram')">
                                        <i class="fas fa-money-bill-wave"></i>
                                        <h5>حوالة الهرم</h5>
                                        <p>تحويل عبر حوالات الهرم</p>
                                    </div>
                                </div>
                                
                                <!-- بنك بيمو -->
                                <div class="col-md-6 mb-3">
                                    <div class="payment-method" onclick="selectPaymentMethod('bemo')">
                                        <i class="fas fa-university"></i>
                                        <h5>بنك بيمو</h5>
                                        <p>تحويل بنكي</p>
                                    </div>
                                </div>
                                
                                <!-- شام كاش -->
                                <div class="col-md-6 mb-3">
                                    <div class="payment-method" onclick="selectPaymentMethod('sham')">
                                        <i class="fas fa-wallet"></i>
                                        <h5>شام كاش</h5>
                                        <p>محفظة إلكترونية</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <div id="payment-details" class="mb-4" style="display: none;">
                            <label id="account-label" class="form-label">رقم الحساب</label>
                            <input type="text" class="form-control" id="account-number" placeholder="أدخل رقم الحساب">
                        </div>
                        
                        <div class="fee-summary mb-4 p-3 bg-light rounded">
                            <h5>تفاصيل التكلفة</h5>
                            <div class="d-flex justify-content-between mb-2">
                                <span>مبلغ USDT:</span>
                                <span id="sell-amount-display">0.00 USDT</span>
                            </div>
                            <div class="d-flex justify-content-between mb-2">
                                <span>عمولة الخدمة:</span>
                                <span id="sell-service-fee">0.00 USDT</span>
                            </div>
                            <div class="d-flex justify-content-between fw-bold">
                                <span>المبلغ المستلم:</span>
                                <span id="net-amount">0.00 USDT</span>
                            </div>
                        </div>
                        
                        <div class="d-flex justify-content-between">
                            <button class="btn btn-outline-primary" onclick="prevStep(2)"><i class="fas fa-arrow-right me-2"></i> السابق</button>
                            <button class="btn btn-primary" onclick="nextStep(4)">التالي <i class="fas fa-arrow-left ms-2"></i></button>
                        </div>
                    </div>

                    <!-- الخطوة الرابعة: الملخص -->
                    <div id="step4" class="step">
                        <h3 class="step-title">ملخص الطلب</h3>
                        <p class="text-muted mb-4">يرجى مراجعة المعلومات قبل الإرسال</p>
                        
                        <div class="card mb-4">
                            <div class="card-header bg-primary text-white">
                                <h5 class="mb-0">المعلومات الشخصية</h5>
                            </div>
                            <div class="card-body">
                                <div class="summary-item">
                                    <strong>الاسم:</strong> <span id="summary-name"></span>
                                </div>
                                <div class="summary-item">
                                    <strong>الهاتف:</strong> <span id="summary-phone"></span>
                                </div>
                                <div class="summary-item">
                                    <strong>المدينة:</strong> <span id="summary-city"></span>
                                </div>
                            </div>
                        </div>
                        
                        <div class="card mb-4">
                            <div class="card-header bg-primary text-white">
                                <h5 class="mb-0">تفاصيل العملية</h5>
                            </div>
                            <div class="card-body">
                                <div id="transaction-details"></div>
                            </div>
                        </div>
                        
                        <div class="receiving-details">
                            <h5><i class="fas fa-info-circle me-2"></i> تفاصيل الاستلام</h5>
                            <div id="receive-instructions"></div>
                        </div>
                        
                        <div class="note-box mt-4">
                            <p class="mb-0">
                                <i class="fas fa-exclamation-triangle me-2 text-warning"></i>
                                عمولة التسديد على طرق التحويل المختلفة بالليرة السورية تقع على المستخدم كما تحددها هذه الجهات
                            </p>
                        </div>
                        
                        <div class="d-flex justify-content-between mt-4">
                            <button class="btn btn-outline-primary" onclick="prevStep(3)"><i class="fas fa-arrow-right me-2"></i> السابق</button>
                            <button class="btn btn-success" onclick="submitForm()"><i class="fas fa-paper-plane me-2"></i> تأكيد وإرسال الطلب</button>
                        </div>
                    </div>

                    <!-- الخطوة الخامسة: تأكيد -->
                    <div id="step5" class="step">
                        <div class="text-center py-5">
                            <i class="fas fa-check-circle fa-5x text-success mb-4"></i>
                            <h2 class="mb-3">تم إرسال طلبك بنجاح!</h2>
                            <p class="lead">سيتم معالجة طلبك خلال 24 ساعة وسنتصل بك للتأكيد</p>
                            <p id="confirmation-message" class="mb-4"></p>
                            <p>تم إرسال تفاصيل الطلب إلى البريد الإلكتروني: alimahmoud001a@gmail.com</p>
                            <button class="btn btn-primary mt-3" onclick="resetForm()"><i class="fas fa-redo me-2"></i> إنشاء طلب جديد</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <div class="container">
            <p class="mb-0">جميع الحقوق محفوظة &copy; 2023 | نظام تحويل العملات الرقمية في سورية</p>
        </div>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        // بيانات التطبيق
        const transactionData = {
            step: 1,
            transactionType: '',
            paymentMethod: '',
            personalInfo: {
                name: '',
                phone: '',
                city: ''
            },
            transactionDetails: {}
        };
        
        // رسوم الشبكات
        const networkFees = {
            bep20: 0.15,
            trc20: 2,
            erc20: 0.3,
            binance: 0
        };
        
        // تفاصيل الاستلام
        const receiveDetails = {
            syrTel: {
                name: 'سيريتل كاش',
                instructions: 'عنواني هو: 0934598967',
                accountLabel: 'رقم الجوال'
            },
            haram: {
                name: 'حوالة الهرم',
                instructions: 'التفاصيل هي:<br>علي ابراهيم محمود<br>0934598967<br>اللاذقية',
                accountLabel: 'رقم الهاتف'
            },
            bemo: {
                name: 'بنك بيمو',
                instructions: 'التفاصيل هي:<br>علي ابراهيم محمود<br>060104947910013000000',
                accountLabel: 'رقم الحساب'
            },
            sham: {
                name: 'شام كاش',
                instructions: 'عنواني هو: be456e0ea9392db4d68a7093ee317bc8<br>رقم الحساب: 5991161126028260',
                accountLabel: 'رقم الحساب'
            }
        };
        
        // عناوين كريبتو
        const cryptoAddresses = {
            bep20: '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            trc20: 'TD2LoErPRkVPBxDk72ZErtiyi6agirZQjX',
            erc20: '0x21802218d8d661d66F2C7959347a6382E1cc614F',
            binance: '969755964'
        };
        
        // إدارة الخطوات
        function nextStep(step) {
            // التحقق من صحة البيانات قبل الانتقال
            if (step === 2 && !validateStep1()) return;
            if (step === 3 && !transactionData.transactionType) return;
            if (step === 4 && !validateStep3()) return;
            
            document.querySelectorAll('.step').forEach(el => el.classList.remove('active'));
            
            if (step === 3) {
                document.getElementById(`step3-${transactionData.transactionType}`).classList.add('active');
            } else {
                document.getElementById(`step${step}`).classList.add('active');
            }
            
            transactionData.step = step;
            updateProgressBar();
            updateStepIndicators();
            
            if (step === 4) {
                prepareSummary();
            }
        }
        
        function prevStep(step) {
            document.querySelectorAll('.step').forEach(el => el.classList.remove('active'));
            
            if (step === 3) {
                document.getElementById(`step3-${transactionData.transactionType}`).classList.add('active');
                transactionData.step = 3;
            } else {
                document.getElementById(`step${step}`).classList.add('active');
                transactionData.step = step;
            }
            
            updateProgressBar();
            updateStepIndicators();
        }
        
        function updateProgressBar() {
            const progress = (transactionData.step - 1) * 25;
            document.getElementById('progress-bar').style.width = `${progress}%`;
        }
        
        function updateStepIndicators() {
            document.querySelectorAll('.step-indicator').forEach((el, index) => {
                const stepNum = parseInt(el.getAttribute('data-step'));
                if (stepNum <= transactionData.step) {
                    el.classList.add('text-primary', 'fw-bold');
                } else {
                    el.classList.remove('text-primary', 'fw-bold');
                }
            });
        }
        
        // اختيار نوع العملية
        function selectTransactionType(type) {
            transactionData.transactionType = type;
            nextStep(3);
        }
        
        // اختيار طريقة الدفع
        function selectPaymentMethod(method) {
            transactionData.paymentMethod = method;
            
            // إزالة التحديد من جميع العناصر
            document.querySelectorAll('.payment-method').forEach(el => {
                el.classList.remove('selected');
            });
            
            // إضافة التحديد للعنصر المختار
            event.currentTarget.classList.add('selected');
            
            // إظهار حقل التفاصيل الإضافية
            document.getElementById('payment-details').style.display = 'block';
            document.getElementById('account-label').textContent = receiveDetails[method].accountLabel;
        }
        
        // حساب الرسوم
        function calculateFees() {
            if (transactionData.transactionType === 'buy') {
                const amount = parseFloat(document.getElementById('buyAmount').value) || 0;
                const network = document.getElementById('network').value;
                
                // حساب رسوم الخدمة
                let serviceFee;
                if (amount < 100) {
                    serviceFee = 1.65;
                } else if (amount <= 5000) {
                    serviceFee = amount * 0.0165;
                } else {
                    serviceFee = amount * 0.0005;
                }
                
                // رسوم الشبكة
                const networkFee = networkFees[network];
                
                // تحديث الواجهة
                document.getElementById('amount-display').textContent = amount.toFixed(2) + ' USDT';
                document.getElementById('service-fee').textContent = serviceFee.toFixed(2) + ' USDT';
                document.getElementById('network-fee').textContent = networkFee.toFixed(2) + ' USDT';
                document.getElementById('total-amount').textContent = (amount + serviceFee + networkFee).toFixed(2) + ' USDT';
                
                // حفظ البيانات
                transactionData.transactionDetails = {
                    amount: amount,
                    network: network,
                    walletAddress: document.getElementById('walletAddress').value,
                    notes: document.getElementById('buyNotes').value,
                    serviceFee: serviceFee,
                    networkFee: networkFee,
                    total: amount + serviceFee + networkFee
                };
                
            } else { // بيع
                const amount = parseFloat(document.getElementById('sellAmount').value) || 0;
                
                // حساب رسوم الخدمة
                let serviceFee;
                if (amount < 100) {
                    serviceFee = 1.65;
                } else if (amount <= 5000) {
                    serviceFee = amount * 0.0165;
                } else {
                    serviceFee = amount * 0.0005;
                }
                
                // تحديث الواجهة
                document.getElementById('sell-amount-display').textContent = amount.toFixed(2) + ' USDT';
                document.getElementById('sell-service-fee').textContent = serviceFee.toFixed(2) + ' USDT';
                document.getElementById('net-amount').textContent = (amount - serviceFee).toFixed(2) + ' USDT';
                
                // حفظ البيانات
                transactionData.transactionDetails = {
                    amount: amount,
                    receiveMethod: transactionData.paymentMethod,
                    accountNumber: document.getElementById('account-number').value,
                    serviceFee: serviceFee,
                    netAmount: amount - serviceFee
                };
            }
        }
        
        // إعداد ملخص الطلب
        function prepareSummary() {
            // تحديث المعلومات الشخصية
            document.getElementById('summary-name').textContent = transactionData.personalInfo.name;
            document.getElementById('summary-phone').textContent = transactionData.personalInfo.phone;
            document.getElementById('summary-city').textContent = transactionData.personalInfo.city;
            
            // تحديث تفاصيل العملية
            const transactionDetails = document.getElementById('transaction-details');
            
            if (transactionData.transactionType === 'buy') {
                const details = transactionData.transactionDetails;
                transactionDetails.innerHTML = `
                    <div class="summary-item">
                        <strong>نوع العملية:</strong> شراء USDT
                    </div>
                    <div class="summary-item">
                        <strong>الكمية:</strong> ${details.amount.toFixed(2)} USDT
                    </div>
                    <div class="summary-item">
                        <strong>الشبكة:</strong> ${getNetworkName(details.network)}
                    </div>
                    <div class="summary-item">
                        <strong>رسوم الخدمة:</strong> ${details.serviceFee.toFixed(2)} USDT
                    </div>
                    <div class="summary-item">
                        <strong>رسوم الشبكة:</strong> ${details.networkFee.toFixed(2)} USDT
                    </div>
                    <div class="summary-item fw-bold">
                        <strong>المبلغ الإجمالي:</strong> ${details.total.toFixed(2)} USDT
                    </div>
                    <div class="summary-item">
                        <strong>عنوان المحفظة:</strong> ${details.walletAddress}
                    </div>
                    <div class="summary-item">
                        <strong>ملاحظات:</strong> ${details.notes || 'لا يوجد'}
                    </div>
                `;
                
                // إظهار تفاصيل الاستلام
                document.getElementById('receive-instructions').innerHTML = `
                    <p>الرجاء إرسال المبلغ الإجمالي بالليرة السورية إلى أحد الخيارات التالية:</p>
                    <div class="row mt-3">
                        <div class="col-md-6 mb-3">
                            <div class="card">
                                <div class="card-body">
                                    <h6>سيريتل كاش</h6>
                                    <p class="mb-1">رقم الجوال: 0934598967</p>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-6 mb-3">
                            <div class="card">
                                <div class="card-body">
                                    <h6>حوالة الهرم</h6>
                                    <p class="mb-1">الاسم: علي ابراهيم محمود</p>
                                    <p class="mb-1">رقم الهاتف: 0934598967</p>
                                    <p class="mb-1">المدينة: اللاذقية</p>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-6 mb-3">
                            <div class="card">
                                <div class="card-body">
                                    <h6>بنك بيمو</h6>
                                    <p class="mb-1">الاسم: علي ابراهيم محمود</p>
                                    <p class="mb-1">رقم الحساب: 060104947910013000000</p>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-6 mb-3">
                            <div class="card">
                                <div class="card-body">
                                    <h6>شام كاش</h6>
                                    <p class="mb-1">العنوان: be456e0ea9392db4d68a7093ee317bc8</p>
                                    <p class="mb-1">رقم الحساب: 5991161126028260</p>
                                </div>
                            </div>
                        </div>
                    </div>
                `;
                
            } else { // بيع
                const details = transactionData.transactionDetails;
                const method = receiveDetails[details.receiveMethod];
                
                transactionDetails.innerHTML = `
                    <div class="summary-item">
                        <strong>نوع العملية:</strong> بيع USDT
                    </div>
                    <div class="summary-item">
                        <strong>الكمية:</strong> ${details.amount.toFixed(2)} USDT
                    </div>
                    <div class="summary-item">
                        <strong>طريقة الاستلام:</strong> ${method.name}
                    </div>
                    <div class="summary-item">
                        <strong>${method.accountLabel}:</strong> ${details.accountNumber}
                    </div>
                    <div class="summary-item">
                        <strong>رسوم الخدمة:</strong> ${details.serviceFee.toFixed(2)} USDT
                    </div>
                    <div class="summary-item fw-bold">
                        <strong>المبلغ المستلم:</strong> ${details.netAmount.toFixed(2)} USDT
                    </div>
                `;
                
                // إظهار تفاصيل الاستلام
                document.getElementById('receive-instructions').innerHTML = `
                    <p>الرجاء إرسال USDT إلى أحد العناوين التالية:</p>
                    <div class="row mt-3">
                        <div class="col-md-6 mb-3">
                            <div class="card">
                                <div class="card-body">
                                    <h6>BEP20</h6>
                                    <p class="crypto-address">${cryptoAddresses.bep20}</p>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-6 mb-3">
                            <div class="card">
                                <div class="card-body">
                                    <h6>TRC20</h6>
                                    <p class="crypto-address">${cryptoAddresses.trc20}</p>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-6 mb-3">
                            <div class="card">
                                <div class="card-body">
                                    <h6>ERC20</h6>
                                    <p class="crypto-address">${cryptoAddresses.erc20}</p>
                                </div>
                            </div>
                        </div>
                        <div class="col-md-6 mb-3">
                            <div class="card">
                                <div class="card-body">
                                    <h6>Binance Pay</h6>
                                    <p class="crypto-address">${cryptoAddresses.binance}</p>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="alert alert-info mt-3">
                        <i class="fas fa-info-circle me-2"></i>
                        يرجى استخدام الشبكة التي اخترتها أثناء إنشاء الطلب
                    </div>
                `;
            }
        }
        
        // الحصول على اسم الشبكة
        function getNetworkName(network) {
            const names = {
                bep20: 'BEP20',
                trc20: 'TRC20',
                erc20: 'ERC20',
                binance: 'Binance Pay'
            };
            return names[network] || network;
        }
        
        // التحقق من صحة الخطوة 1
        function validateStep1() {
            const name = document.getElementById('fullName').value;
            const phone = document.getElementById('phone').value;
            const city = document.getElementById('city').value;
            
            if (!name || !phone || !city) {
                alert('الرجاء تعبئة جميع الحقول في المعلومات الشخصية');
                return false;
            }
            
            // حفظ البيانات الشخصية
            transactionData.personalInfo = {
                name: name,
                phone: phone,
                city: city
            };
            
            return true;
        }
        
        // التحقق من صحة الخطوة 3
        function validateStep3() {
            if (transactionData.transactionType === 'buy') {
                const amount = document.getElementById('buyAmount').value;
                const wallet = document.getElementById('walletAddress').value;
                
                if (!amount || parseFloat(amount) <= 0) {
                    alert('الرجاء إدخال كمية صحيحة');
                    return false;
                }
                
                if (!wallet) {
                    alert('الرجاء إدخال عنوان المحفظة');
                    return false;
                }
                
            } else { // بيع
                const amount = document.getElementById('sellAmount').value;
                
                if (!amount || parseFloat(amount) <= 0) {
                    alert('الرجاء إدخال كمية صحيحة');
                    return false;
                }
                
                if (!transactionData.paymentMethod) {
                    alert('الرجاء اختيار طريقة الاستلام');
                    return false;
                }
                
                const accountNumber = document.getElementById('account-number').value;
                if (!accountNumber) {
                    alert(`الرجاء إدخال ${receiveDetails[transactionData.paymentMethod].accountLabel}`);
                    return false;
                }
            }
            
            return true;
        }
        
        // إرسال الطلب
        function submitForm() {
            // في تطبيق حقيقي، هنا سيتم إرسال البيانات إلى الخادم
            document.getElementById('confirmation-message').innerHTML = `
                <div class="alert alert-success">
                    <p>تم استلام طلبك بنجاح وسيتم معالجته في أقرب وقت</p>
                    <p>رقم الطلب: #${Math.floor(100000 + Math.random() * 900000)}</p>
                </div>
            `;
            
            nextStep(5);
        }
        
        // إعادة تعيين النموذج
        function resetForm() {
            // إعادة تعيين جميع الحقول
            document.getElementById('fullName').value = '';
            document.getElementById('phone').value = '';
            document.getElementById('city').value = '';
            document.getElementById('buyAmount').value = '';
            document.getElementById('walletAddress').value = '';
            document.getElementById('buyNotes').value = '';
            document.getElementById('sellAmount').value = '';
            document.getElementById('account-number').value = '';
            
            // إعادة تعيين البيانات
            transactionData.step = 1;
            transactionData.transactionType = '';
            transactionData.paymentMethod = '';
            transactionData.personalInfo = { name: '', phone: '', city: '' };
            transactionData.transactionDetails = {};
            
            // إعادة تعيين الواجهة
            document.querySelectorAll('.step').forEach(el => el.classList.remove('active'));
            document.getElementById('step1').classList.add('active');
            updateProgressBar();
            updateStepIndicators();
            
            // إخفاء تفاصيل الدفع
            document.getElementById('payment-details').style.display = 'none';
            
            // إزالة التحديد من طرق الدفع
            document.querySelectorAll('.payment-method').forEach(el => {
                el.classList.remove('selected');
            });
        }
        
        // تهيئة الصفحة
        document.addEventListener('DOMContentLoaded', function() {
            updateStepIndicators();
            
            // تحديث سعر الصرف بشكل عشوائي كل 30 ثانية (محاكاة)
            setInterval(() => {
                const rate = 14000 + Math.floor(Math.random() * 1000);
                document.getElementById('rate-display').textContent = `1 USDT = ${rate.toLocaleString()} SYP`;
            }, 30000);
        });
    </script>
</body>
</html>
