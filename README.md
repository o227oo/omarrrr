<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تطبيق FOODI</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #e23744;
            --secondary-color: #2f3542;
        }

        body {
            background-color: #f5f5f5;
            padding-bottom: 70px;
            font-family: 'Cairo', sans-serif;
        }

        .restaurant-card {
            border-radius: 15px;
            transition: 0.3s;
            position: relative;
            margin-bottom: 1.5rem;
        }

        .restaurant-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .restaurant-image {
            height: 200px;
            object-fit: cover;
            border-radius: 15px 15px 0 0;
        }

        .offer-ribbon {
            position: absolute;
            top: 15px;
            left: -30px;
            background: var(--primary-color);
            color: white;
            padding: 5px 40px;
            transform: rotate(-45deg);
            font-size: 0.9rem;
            z-index: 1;
        }

        .menu-item {
            border-bottom: 1px solid #eee;
            padding: 1rem 0;
        }

        .cart-badge {
            position: absolute;
            top: -5px;
            left: -5px;
        }

        .fixed-bottom-nav {
            box-shadow: 0 -2px 10px rgba(0,0,0,0.1);
        }
    </style>
</head>
<body>

<!-- شريط التنقل العلوي -->
<nav class="navbar bg-white shadow-sm sticky-top">
    <div class="container">
        <a class="navbar-brand fw-bold text-danger" href="#">FOODI</a>
        <div class="d-flex align-items-center">
            <a href="#cart" class="btn btn-light position-relative">
                <i class="fas fa-shopping-cart text-danger"></i>
                <span class="cart-badge badge bg-danger rounded-pill">0</span>
            </a>
        </div>
    </div>
</nav>

<!-- المحتوى الرئيسي -->
<main class="container mt-4">
    <!-- مطعم ترليون -->
    <div class="card restaurant-card">
        <span class="offer-ribbon">خصم 25%</span>
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTXLILrKPRy-YgsG-Kn2_Ls0rZX802POlQFsw&s" 
             class="card-img-top restaurant-image" 
             alt="مطعم ترليون">
        <div class="card-body">
            <div class="d-flex justify-content-between align-items-center mb-3">
                <h5 class="card-title fw-bold">ترليون</h5>
                <div>
                    <span class="badge bg-warning text-dark">4.8 ★</span>
                    <small class="text-muted">(2.1K تقييم)</small>
                </div>
            </div>
            
            <div class="row g-3 mb-3">
                <div class="col-6">
                    <i class="fas fa-clock text-danger"></i>
                    <span>35-50 دقيقة</span>
                </div>
                <div class="col-6">
                    <i class="fas fa-tag text-danger"></i>
                    <span>الحد الأدنى: 25 ر.س</span>
                </div>
            </div>

            <!-- قائمة الأصناف -->
            <div class="menu-items">
                <div class="menu-item">
                    <div class="d-flex justify-content-between align-items-center">
                        <div>
                            <h6 class="fw-bold mb-0">برجر ترليون</h6>
                            <small class="text-muted">لحم بقر 200جم مع صلصة خاصة</small>
                        </div>
                        <div>
                            <span class="text-danger fw-bold">35 ر.س</span>
                            <button class="btn btn-sm btn-danger" onclick="addToCart('برجر ترليون', 35)">+</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- مطعم الكورنيش -->
    <div class="card restaurant-card">
        <span class="offer-ribbon">تخفيض 20%</span>
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQhc2f4jyEErCy4Xze3_AKbQ8azqEsORMVozQ&s" 
             class="card-img-top restaurant-image" 
             alt="مطعم الكورنيش">
        <div class="card-body">
            <div class="d-flex justify-content-between align-items-center mb-3">
                <h5 class="card-title fw-bold">مطعم الكورنيش</h5>
                <div>
                    <span class="badge bg-warning text-dark">4.3 ★</span>
                    <small class="text-muted">(1.5K تقييم)</small>
                </div>
            </div>
            
            <div class="row g-3 mb-3">
                <div class="col-6">
                    <i class="fas fa-clock text-danger"></i>
                    <span>30-45 دقيقة</span>
                </div>
                <div class="col-6">
                    <i class="fas fa-tag text-danger"></i>
                    <span>الحد الأدنى: 30 ر.س</span>
                </div>
            </div>

            <!-- قائمة الأصناف -->
            <div class="menu-items">
                <div class="menu-item">
                    <div class="d-flex justify-content-between align-items-center">
                        <div>
                            <h6 class="fw-bold mb-0">صحن بروست</h6>
                            <small class="text-muted">قطع دجاج مقرمشة مع صلصة خاصة</small>
                        </div>
                        <div>
                            <span class="text-danger fw-bold">30 ر.س</span>
                            <button class="btn btn-sm btn-danger" onclick="addToCart('صحن بروست', 30)">+</button>
                        </div>
                    </div>
                </div>
                <div class="menu-item">
                    <div class="d-flex justify-content-between align-items-center">
                        <div>
                            <h6 class="fw-bold mb-0">صحن شبس</h6>
                            <small class="text-muted">شيبس مقرمش مع صلصة الجبن</small>
                        </div>
                        <div>
                            <span class="text-danger fw-bold">10 ر.س</span>
                            <button class="btn btn-sm btn-danger" onclick="addToCart('صحن شبس', 10)">+</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- مطعم العمودي -->
    <div class="card restaurant-card">
        <span class="offer-ribbon">توصيل مجاني</span>
        <img src="https://images.app.goo.gl/kT6RogddHotHpmN37" 
             class="card-img-top restaurant-image" 
             alt="مطعم العمودي">
        <div class="card-body">
            <div class="d-flex justify-content-between align-items-center mb-3">
                <h5 class="card-title fw-bold">مطعم العمودي</h5>
                <div>
                    <span class="badge bg-warning text-dark">4.5 ★</span>
                    <small class="text-muted">(1.8K تقييم)</small>
                </div>
            </div>
            
            <div class="row g-3 mb-3">
                <div class="col-6">
                    <i class="fas fa-clock text-danger"></i>
                    <span>25-40 دقيقة</span>
                </div>
                <div class="col-6">
                    <i class="fas fa-tag text-danger"></i>
                    <span>الحد الأدنى: 35 ر.س</span>
                </div>
            </div>

            <!-- قائمة الأصناف -->
            <div class="menu-items">
                <div class="menu-item">
                    <div class="d-flex justify-content-between align-items-center">
                        <div>
                            <h6 class="fw-bold mb-0">مشاوي عمودي</h6>
                            <small class="text-muted">مشويات مشكلة مع أرز</small>
                        </div>
                        <div>
                            <span class="text-danger fw-bold">45 ر.س</span>
                            <button class="btn btn-sm btn-danger" onclick="addToCart('مشاوي عمودي', 45)">+</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</main>

<!-- شريط التنقل السفلي -->
<nav class="navbar bg-white fixed-bottom fixed-bottom-nav">
    <div class="container">
        <div class="d-flex justify-content-around w-100">
            <a href="#home" class="nav-link active text-danger">
                <i class="fas fa-home fa-lg"></i>
                <small>الرئيسية</small>
            </a>
            <a href="#search" class="nav-link text-secondary">
                <i class="fas fa-search fa-lg"></i>
                <small>بحث</small>
            </a>
            <a href="#orders" class="nav-link text-secondary">
                <i class="fas fa-clipboard-list fa-lg"></i>
                <small>طلباتي</small>
            </a>
            <a href="#account" class="nav-link text-secondary">
                <i class="fas fa-user fa-lg"></i>
                <small>حسابي</small>
            </a>
        </div>
    </div>
</nav>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
<script>
    let cartItems = [];
    let total = 0;

    function addToCart(itemName, price) {
        cartItems.push({name: itemName, price: price});
        total += price;
        updateCartUI();
    }

    function updateCartUI() {
        document.querySelector('.cart-badge').textContent = cartItems.length;
    }
</script>
</body>
</html>
