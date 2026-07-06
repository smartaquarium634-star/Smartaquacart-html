html_content = """<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>SMART AQUA CART | Premium Aquarium Store</title>
    
    <meta name="description" content="Premium Quality Fishes and Aquarium Accessories in Karad, Satara, Maharashtra. Order online with ease.">
    <meta name="theme-color" content="#070f1e">
    <meta property="og:title" content="SMART AQUA CART">
    <meta property="og:description" content="Premium Quality Fishes and Aquarium Accessories.">
    <meta property="og:type" content="website">
    
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        /* CSS RESET & VARIABLES */
        *, *::before, *::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Plus Jakarta Sans', sans-serif;
            -webkit-tap-highlight-color: transparent;
        }

        :root {
            --bg-base: #070f1e;
            --bg-surface: rgba(15, 32, 67, 0.55);
            --bg-surface-solid: #0f2043;
            --border-glass: rgba(0, 242, 254, 0.15);
            --accent-primary: #00f2fe;
            --accent-secondary: #05g9a3; /* Emerald/Aqua shift */
            --accent-gradient: linear-gradient(135deg, #00f2fe 0%, #4facfe 100%);
            --accent-green: #10b981;
            --text-main: #f8fafc;
            --text-muted: #94a3b8;
            --shadow-premium:0 20px 40px -15px rgba(0, 0, 0, 0.5);
            --blur-radius: 16px;
            --transition-smooth: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
        }

        /* THEMES */
        body.theme-light {
            --bg-base: #f1f5f9;
            --bg-surface: rgba(255, 255, 255, 0.65);
            --bg-surface-solid: #ffffff;
            --border-glass: rgba(15, 32, 67, 0.1);
            --accent-gradient: linear-gradient(135deg, #0284c7 0%, #0369a1 100%);
            --accent-primary: #0284c7;
            --text-main: #0f172a;
            --text-muted: #64748b;
            --shadow-premium: 0 20px 40px -15px rgba(15, 32, 67, 0.15);
        }

        body.theme-aqua {
            --bg-base: #011627;
            --bg-surface: rgba(1, 42, 74, 0.6);
            --bg-surface-solid: #012a4a;
            --border-glass: rgba(107, 236, 227, 0.2);
            --accent-gradient: linear-gradient(135deg, #01c4e7 0%, #2a9d8f 100%);
            --accent-primary: #01c4e7;
            --text-main: #e2f1f5;
            --text-muted: #8ecae6;
        }

        body.theme-emerald {
            --bg-base: #022c22;
            --bg-surface: rgba(6, 78, 59, 0.6);
            --bg-surface-solid: #064e3b;
            --border-glass: rgba(52, 211, 153, 0.2);
            --accent-gradient: linear-gradient(135deg, #34d399 0%, #059669 100%);
            --accent-primary: #34d399;
            --text-main: #f0fdf4;
            --text-muted: #a7f3d0;
        }

        body.theme-black {
            --bg-base: #050505;
            --bg-surface: rgba(24, 24, 27, 0.7);
            --bg-surface-solid: #18181b;
            --border-glass: rgba(255, 255, 255, 0.08);
            --accent-gradient: linear-gradient(135deg, #ffffff 0%, #a1a1aa 100%);
            --accent-primary: #ffffff;
            --text-main: #fafafa;
            --text-muted: #a1a1aa;
        }

        /* GLOBAL STYLES */
        body {
            background-color: var(--bg-base);
            color: var(--text-main);
            overflow-x: hidden;
            transition: background-color 0.5s ease;
            line-height: 1.6;
        }

        img {
            max-width: 100%;
            height: auto;
            display: block;
        }

        button, input, textarea, select {
            background: none;
            border: none;
            outline: none;
            color: inherit;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* SCROLLBAR */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-base);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--bg-surface-solid);
            border-radius: 10px;
            border: 2px solid var(--bg-base);
        }

        /* LOADING SCREEN */
        #loading-screen {
            position: fixed;
            inset: 0;
            background: var(--bg-base);
            z-index: 99999;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            transition: opacity 0.6s cubic-bezier(0.16, 1, 0.3, 1);
        }
        .spinner {
            width: 60px;
            height: 60px;
            border: 4px solid var(--border-glass);
            border-top: 4px solid var(--accent-primary);
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            to { transform: rotate(300deg); }
        }

        /* GLASS STYLING */
        .glass {
            background: var(--bg-surface);
            backdrop-filter: blur(var(--blur-radius));
            -webkit-backdrop-filter: blur(var(--blur-radius));
            border: 1px solid var(--border-glass);
            border-radius: 24px;
            box-shadow: var(--shadow-premium);
        }

        /* STICKY HEADER */
        header {
            position: sticky;
            top: 0;
            z-index: 1000;
            padding: 15px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            transition: var(--transition-smooth);
            background: rgba(7, 15, 30, 0.7);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border-bottom: 1px solid var(--border-glass);
        }
        header.scrolled {
            padding: 10px 5%;
            background: var(--bg-base);
        }
        .logo-area {
            display: flex;
            align-items: center;
            gap: 12px;
            cursor: pointer;
            user-select: none;
        }
        .logo-icon {
            width: 40px;
            height: 40px;
            background: var(--accent-gradient);
            border-radius: 12px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: 800;
            color: #050505;
            box-shadow: 0 0 20px rgba(0, 242, 254, 0.4);
            animation: pulse 3s infinite;
        }
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); box-shadow: 0 0 30px rgba(0, 242, 254, 0.6); }
        }
        .logo-text h1 {
            font-size: 18pt;
            font-weight: 800;
            letter-spacing: -0.5px;
            background: var(--accent-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .logo-text p {
            font-size: 8pt;
            color: var(--text-muted);
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        .nav-actions {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        .nav-btn {
            width: 44px;
            height: 44px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            background: var(--bg-surface-solid);
            border: 1px solid var(--border-glass);
            cursor: pointer;
            position: relative;
            transition: var(--transition-smooth);
        }
        .nav-btn:hover {
            transform: translateY(-3px);
            border-color: var(--accent-primary);
        }
        .badge {
            position: absolute;
            top: -4px;
            right: -4px;
            background: red;
            color: white;
            font-size: 8pt;
            font-weight: bold;
            padding: 2px 6px;
            border-radius: 10px;
            min-width: 18px;
            text-align: center;
        }

        /* HERO BANNER */
        .hero-section {
            padding: 60px 5% 40px;
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            align-items: center;
            gap: 40px;
            max-width: 1400px;
            margin: 0 auto;
        }
        .hero-content h2 {
            font-size: 36pt;
            line-height: 1.1;
            font-weight: 800;
            margin-bottom: 20px;
            letter-spacing: -1px;
        }
        .hero-content h2 span {
            background: var(--accent-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero-content p {
            color: var(--text-muted);
            font-size: 12pt;
            margin-bottom: 30px;
            max-width: 500px;
        }
        .cta-btn {
            background: var(--accent-gradient);
            color: #000;
            padding: 14px 32px;
            border-radius: 14px;
            font-weight: 700;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            box-shadow: 0 10px 25px rgba(0, 242, 254, 0.3);
            transition: var(--transition-smooth);
        }
        .cta-btn:hover {
            transform: translateY(-4px) scale(1.02);
            box-shadow: 0 15px 30px rgba(0, 242, 254, 0.5);
        }
        .hero-banner-container {
            position: relative;
            border-radius: 32px;
            overflow: hidden;
            border: 1px solid var(--border-glass);
            transform: perspective(1000px) rotateY(-5deg);
            transition: var(--transition-smooth);
        }
        .hero-banner-container:hover {
            transform: perspective(1000px) rotateY(0deg) scale(1.02);
        }
        .hero-banner-container img {
            width: 100%;
            height: 380px;
            object-fit: cover;
        }

        /* MAIN LAYOUT WRAPPER */
        main {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px 5% 80px;
        }

        /* SEARCH & FILTER BAR */
        .controls-row {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            gap: 20px;
            margin-bottom: 40px;
        }
        .search-box {
            position: relative;
            flex: 1;
            min-width: 280px;
            max-width: 450px;
        }
        .search-box input {
            width: 100%;
            padding: 14px 20px 14px 50px;
            border-radius: 16px;
            background: var(--bg-surface-solid);
            border: 1px solid var(--border-glass);
            transition: var(--transition-smooth);
        }
        .search-box input:focus {
            border-color: var(--accent-primary);
            box-shadow: 0 0 15px rgba(0, 242, 254, 0.2);
        }
        .search-box svg {
            position: absolute;
            left: 18px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--text-muted);
        }
        .category-track {
            display: flex;
            gap: 10px;
            overflow-x: auto;
            padding-bottom: 10px;
            width: 100%;
            scrollbar-width: none;
        }
        .category-track::-webkit-scrollbar {
            display: none;
        }
        .cat-btn {
            white-space: nowrap;
            padding: 10px 22px;
            border-radius: 12px;
            background: var(--bg-surface);
            border: 1px solid var(--border-glass);
            cursor: pointer;
            font-weight: 600;
            font-size: 10pt;
            transition: var(--transition-smooth);
        }
        .cat-btn.active, .cat-btn:hover {
            background: var(--accent-gradient);
            color: #000;
            border-color: transparent;
        }

        /* SECTION TILES */
        .section-title {
            font-size: 20pt;
            font-weight: 800;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .section-title span {
            width: 6px;
            height: 24px;
            background: var(--accent-gradient);
            border-radius: 4px;
        }

        /* PRODUCT GRID */
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        /* PRODUCT CARD */
        .product-card {
            position: relative;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            height: 100%;
            transition: var(--transition-smooth);
            overflow: hidden;
        }
        .product-card:hover {
            transform: translateY(-10px);
            border-color: var(--accent-primary);
            box-shadow: 0 22px 40px rgba(0, 0, 0, 0.4);
        }
        .card-img-holder {
            position: relative;
            padding: 15px;
            background: rgba(255,255,255,0.02);
            border-radius: 20px;
            overflow: hidden;
            cursor: pointer;
        }
        .card-img-holder img {
            width: 100%;
            height: 200px;
            object-fit: contain;
            border-radius: 14px;
            transition: var(--transition-smooth);
        }
        .product-card:hover .card-img-holder img {
            transform: scale(1.06);
        }
        .card-badges {
            position: absolute;
            top: 20px;
            left: 20px;
            display: flex;
            flex-direction: column;
            gap: 6px;
            z-index: 2;
        }
        .badge-tag {
            padding: 4px 10px;
            border-radius: 8px;
            font-size: 7.5pt;
            font-weight: 700;
            text-transform: uppercase;
        }
        .badge-best { background: #f59e0b; color: #000; }
        .badge-feat { background: #3b82f6; color: #fff; }
        .badge-discount { background: #ef4444; color: #fff; }
        .badge-outofstock { background: #64748b; color: #fff; }

        .card-wish-btn {
            position: absolute;
            top: 20px;
            right: 20px;
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background: rgba(15, 32, 67, 0.8);
            border: 1px solid var(--border-glass);
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            z-index: 2;
            transition: var(--transition-smooth);
        }
        .card-wish-btn svg {
            fill: none;
            stroke: var(--text-main);
            transition: var(--transition-smooth);
        }
        .card-wish-btn.active svg {
            fill: #ef4444;
            stroke: #ef4444;
        }

        .card-details {
            padding: 20px;
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }
        .card-cat {
            font-size: 8pt;
            text-transform: uppercase;
            color: var(--text-muted);
            letter-spacing: 0.5px;
            margin-bottom: 6px;
        }
        .card-title {
            font-size: 11pt;
            font-weight: 700;
            margin-bottom: 12px;
            line-height: 1.4;
            height: 44px;
            overflow: hidden;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
            cursor: pointer;
        }
        .card-price-row {
            display: flex;
            align-items: baseline;
            gap: 8px;
            margin-top: auto;
            margin-bottom: 15px;
        }
        .current-price {
            font-size: 14pt;
            font-weight: 800;
            color: var(--accent-primary);
        }
        .old-price {
            font-size: 10pt;
            color: var(--text-muted);
            text-decoration: line-through;
        }
        .add-cart-btn {
            width: 100%;
            background: var(--bg-surface-solid);
            border: 1px solid var(--border-glass);
            padding: 12px;
            border-radius: 12px;
            font-weight: 700;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 8px;
            transition: var(--transition-smooth);
        }
        .add-cart-btn:hover:not(:disabled) {
            background: var(--accent-gradient);
            color: #000;
            border-color: transparent;
            box-shadow: 0 8px 20px rgba(0, 242, 254, 0.25);
        }
        .add-cart-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        /* WHY CHOOSE US */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 25px;
            margin-bottom: 60px;
        }
        .feat-card {
            padding: 30px;
            text-align: center;
        }
        .feat-icon {
            width: 60px;
            height: 60px;
            border-radius: 18px;
            background: var(--bg-surface-solid);
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 0 auto 20px;
            color: var(--accent-primary);
            border: 1px solid var(--border-glass);
        }
        .feat-card h3 { font-size: 12pt; margin-bottom: 10px; font-weight: 700; }
        .feat-card p { font-size: 9.5pt; color: var(--text-muted); }

        /* RECENTLY VIEWED & WISHLIST ROW */
        .horizontal-scroller {
            display: flex;
            gap: 20px;
            overflow-x: auto;
            padding: 10px 0 25px;
            scrollbar-width: thin;
        }
        .mini-card {
            min-width: 200px;
            max-width: 200px;
            padding: 12px;
        }
        .mini-card img {
            width: 100%;
            height: 120px;
            object-fit: contain;
            border-radius: 12px;
            background: rgba(255,255,255,0.02);
            margin-bottom: 10px;
        }
        .mini-title {
            font-size: 9.5pt;
            font-weight: 700;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        /* FAQ ACCORDION */
        .faq-section { margin-bottom: 60px; }
        .faq-item {
            margin-bottom: 15px;
            border-radius: 16px;
            overflow: hidden;
            border: 1px solid var(--border-glass);
        }
        .faq-trigger {
            width: 100%;
            padding: 18px 25px;
            background: var(--bg-surface-solid);
            display: flex;
            justify-content: space-between;
            align-items: center;
            cursor: pointer;
            font-weight: 600;
            text-align: left;
        }
        .faq-content {
            padding: 0 25px;
            max-height: 0;
            overflow: hidden;
            background: rgba(15,32,67,0.2);
            transition: all 0.3s ease-out;
            color: var(--text-muted);
            font-size: 10pt;
        }

        /* MODALS & DRAWERS (BASE SYSTEM) */
        .overlay {
            position: fixed;
            inset: 0;
            background: rgba(5, 5, 10, 0.75);
            backdrop-filter: blur(8px);
            z-index: 2000;
            opacity: 0;
            visibility: hidden;
            transition: var(--transition-smooth);
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal-box {
            width: 90%;
            max-width: 600px;
            max-height: 85vh;
            overflow-y: auto;
            padding: 35px;
            position: relative;
            transform: scale(0.9);
            transition: var(--transition-smooth);
        }
        .overlay.active .modal-box {
            transform: scale(1);
        }

        .drawer {
            position: fixed;
            top: 0;
            right: 0;
            bottom: 0;
            width: 100%;
            max-width: 460px;
            background: var(--bg-base);
            border-left: 1px solid var(--border-glass);
            z-index: 2500;
            transform: translateX(100%);
            transition: var(--transition-smooth);
            display: flex;
            flex-direction: column;
            box-shadow: -10px 0 40px rgba(0,0,0,0.5);
        }
        .drawer.active {
            transform: translateX(0);
        }
        .drawer-header {
            padding: 25px;
            border-bottom: 1px solid var(--border-glass);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .drawer-body {
            flex-grow: 1;
            overflow-y: auto;
            padding: 25px;
        }
        .drawer-footer {
            padding: 25px;
            border-top: 1px solid var(--border-glass);
            background: var(--bg-surface-solid);
        }

        .close-btn {
            width: 36px;
            height: 36px;
            border-radius: 50%;
            background: var(--bg-surface-solid);
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            border: 1px solid var(--border-glass);
        }

        /* QUICK VIEW / PRODUCT DETAILS MODAL */
        .qv-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
        }
        .qv-img-box {
            background: rgba(255,255,255,0.02);
            border-radius: 20px;
            padding: 20px;
            overflow: hidden;
            position: relative;
        }
        .qv-img-box img {
            width: 100%;
            height: 280px;
            object-fit: contain;
            transition: transform 0.2s ease;
        }
        .qv-img-box:hover img {
            transform: scale(1.5);
            cursor: zoom-in;
        }

        /* CART DRAWERS & CHECKOUT ELEMENTS */
        .cart-item {
            display: flex;
            gap: 15px;
            padding-bottom: 20px;
            margin-bottom: 20px;
            border-bottom: 1px solid var(--border-glass);
            align-items: center;
        }
        .cart-item img {
            width: 70px;
            height: 70px;
            object-fit: contain;
            background: rgba(255,255,255,0.02);
            border-radius: 12px;
        }
        .cart-item-details { flex-grow: 1; }
        .qty-control {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-top: 8px;
        }
        .qty-btn {
            width: 28px;
            height: 28px;
            background: var(--bg-surface-solid);
            border: 1px solid var(--border-glass);
            border-radius: 6px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
        }

        /* FORMS */
        .form-group {
            margin-bottom: 18px;
        }
        .form-group label {
            display: block;
            font-size: 9pt;
            color: var(--text-muted);
            margin-bottom: 6px;
            font-weight: 600;
        }
        .form-group input, .form-group textarea, .form-group select {
            width: 100%;
            padding: 12px 16px;
            background: var(--bg-surface-solid);
            border: 1px solid var(--border-glass);
            border-radius: 12px;
            color: var(--text-main);
        }
        .form-group input:focus, .form-group textarea:focus {
            border-color: var(--accent-primary);
        }

        /* ADMIN DASHBOARD */
        .admin-layout {
            display: grid;
            grid-template-columns: 220px 1fr;
            gap: 30px;
            height: 75vh;
        }
        .admin-sidebar {
            border-right: 1px solid var(--border-glass);
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        .admin-tab-btn {
            width: 100%;
            padding: 12px 16px;
            border-radius: 10px;
            text-align: left;
            cursor: pointer;
            font-weight: 600;
            font-size: 10pt;
            transition: var(--transition-smooth);
        }
        .admin-tab-btn.active, .admin-tab-btn:hover {
            background: var(--bg-surface-solid);
            color: var(--accent-primary);
        }
        .admin-pane {
            display: none;
            height: 100%;
            overflow-y: auto;
            padding-right: 10px;
        }
        .admin-pane.active { display: block; }
        
        .admin-table {
            width: 100%;
            border-collapse: collapse;
            font-size: 9.5pt;
        }
        .admin-table th, .admin-table td {
            padding: 12px;
            text-align: left;
            border-bottom: 1px solid var(--border-glass);
        }
        .admin-table th { background: rgba(0,0,0,0.2); font-weight: 700; }

        /* FLOATING UTILITIES */
        .floating-actions {
            position: fixed;
            bottom: 30px;
            left: 30px;
            display: flex;
            flex-direction: column;
            gap: 12px;
            z-index: 1500;
        }
        .float-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
            cursor: pointer;
            transition: var(--transition-smooth);
        }
        .float-btn:hover { transform: translateY(-5px); }
        .float-wa { background: #25d366; }
        .float-call { background: #3b82f6; }
        #scroll-top {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--bg-surface-solid);
            border: 1px solid var(--border-glass);
            display: none;
        }

        /* TOAST NOTIFICATION SYSTEM */
        #toast-container {
            position: fixed;
            bottom: 30px;
            right: 30px;
            z-index: 10000;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .toast {
            background: var(--bg-surface-solid);
            border-left: 4px solid var(--accent-primary);
            padding: 15px 25px;
            border-radius: 8px;
            box-shadow: var(--shadow-premium);
            font-size: 10pt;
            font-weight: 600;
            animation: slideIn 0.3s ease forwards;
        }
        @keyframes slideIn {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        /* SKELETON LOADERS */
        .skeleton {
            background: linear-gradient(90deg, var(--bg-surface-solid) 25%, var(--border-glass) 50%, var(--bg-surface-solid) 75%);
            background-size: 200% 100%;
            animation: loading-skeleton 1.5s infinite;
        }
        @keyframes loading-skeleton {
            0% { background-position: 200% 0; }
            100% { background-position: -200% 0; }
        }

        /* TESTIMONIALS & FOOTER */
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            margin-bottom: 60px;
        }
        .testi-card { padding: 25px; }
        .stars { color: #fbbf24; margin-bottom: 10px; }

        footer {
            background: rgba(5,5,10,0.8);
            border-top: 1px solid var(--border-glass);
            padding: 60px 5% 30px;
            font-size: 10pt;
            color: var(--text-muted);
        }
        .footer-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        .footer-logo h4 { font-size: 16pt; color: #fff; margin-bottom: 10px; }

        /* RESPONSIVE LAYOUT */
        @media (max-width: 992px) {
            .hero-section { grid-template-columns: 1fr; text-align: center; }
            .hero-content p { margin: 0 auto 30px; }
            .hero-banner-container { transform: none; }
            .hero-banner-container:hover { transform: scale(1.01); }
            .qv-grid { grid-template-columns: 1fr; }
            .admin-layout { grid-template-columns: 1fr; height: auto; }
            .admin-sidebar { flex-direction: row; overflow-x: auto; border-right: none; border-bottom: 1px solid var(--border-glass); padding-bottom: 10px; }
            .admin-tab-btn { white-space: nowrap; }
        }
    </style>
</head>
<body class="theme-dark">

    <div id="loading-screen">
        <div class="spinner"></div>
        <p style="margin-top:20px; color:var(--text-muted); font-weight:600; letter-spacing:1px;">SMART AQUA CART</p>
    </div>

    <div id="toast-container"></div>

    <header>
        <div class="logo-area" id="logo-trigger">
            <div class="logo-icon">S</div>
            <div class="logo-text">
                <h1 id="sett-shop-name">SMART AQUA CART</h1>
                <p id="sett-shop-tagline">PREMIUM QUALITY FISHES AND THEIR ACCESSORIES</p>
            </div>
        </div>
        <div class="nav-actions">
            <div class="search-box" style="max-width:200px; display:none;" id="header-search-wrap">
                <input type="text" id="global-search" placeholder="Search products...">
            </div>
            <button class="nav-btn" onclick="toggleSearch()" title="Search">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
            </button>
            <button class="nav-btn" onclick="openDrawer('wishlist-drawer')" title="Wishlist">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
                <span class="badge" id="wishlist-count">0</span>
            </button>
            <button class="nav-btn" onclick="openDrawer('cart-drawer')" title="Shopping Cart">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M6 2L3 6v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V6l-3-4z"></path><line x1="3" y1="6" x2="21" y2="6"></line><path d="M16 10a4 4 0 0 1-8 0"></path></svg>
                <span class="badge" id="cart-count">0</span>
            </button>
            <button class="nav-btn" onclick="triggerAdmin()" title="Admin Control Panel">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><circle cx="12" cy="12" r="3"></circle><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-2 2 2 2 0 0 1-2-2v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1-2-2 2 2 0 0 1 2-2h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 2-2 2 2 0 0 1 2 2v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 2 2 2 2 0 0 1-2 2h-.09a1.65 1.65 0 0 0-1.51 1z"></path></svg>
            </button>
        </div>
    </header>

    <section class="hero-section">
        <div class="hero-content">
            <h2>Experience The <span>Luxury</span> Of Aqua Spaces</h2>
            <p>Transform your space with high-end premium fish species and cutting-edge bio-filtration filtration equipment designed for aquatic perfection.</p>
            <button class="cta-btn" onclick="scrollToProducts()">
                <span>Explore Showcase</span>
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
            </button>
        </div>
        <div class="hero-banner-container">
            <img id="hero-banner-img" src="https://i.ibb.co/tPM0vQdL/1683465900149-SKU-0046-0.webp" alt="Premium Ocean Banner" loading="lazy">
        </div>
    </section>

    <main>
        <div class="controls-row" id="showcase-anchor">
            <div class="search-box">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
                <input type="text" id="main-search" placeholder="Search boutique elements..." oninput="filterShowcase()">
            </div>
            <div class="category-track" id="category-bar">
                </div>
        </div>

        <div class="section-title"><span></span>Dynamic Collection Boutique</div>
        <div class="product-grid" id="product-container">
            </div>

        <div id="recent-view-section" style="display:none; margin-top: 40px;">
            <div class="section-title"><span></span>Recently Viewed Architectural Additions</div>
            <div class="horizontal-scroller" id="recent-container"></div>
        </div>

        <div class="section-title" style="margin-top:60px;"><span></span>The Premium Standard</div>
        <div class="features-grid">
            <div class="feat-card glass">
                <div class="feat-icon">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"></path></svg>
                </div>
                <h3>Elite Biosecurity</h3>
                <p>Every living organism undergoes meticulous inspection and quarantine procedures before dispatch.</p>
            </div>
            <div class="feat-card glass">
                <div class="feat-icon">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><polyline points="12 6 12 12 14 14"></polyline></svg>
                </div>
                <h3>Hyper-Local Logistics</h3>
                <p>Swift order processing dispatched straight from our elite storefront base in Karad.</p>
            </div>
            <div class="feat-card glass">
                <div class="feat-icon">
                    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path></svg>
                </div>
                <h3>24/7 Expert Consulting</h3>
                <p>Direct WhatsApp integration lines matching you with masterful aquatic engineers instantly.</p>
            </div>
        </div>

        <div class="section-title"><span></span>Collector Expressions</div>
        <div class="testimonials-grid">
            <div class="testi-card glass">
                <div class="stars">★★★★★</div>
                <p style="font-style:italic; font-size:10pt; color:var(--text-muted); mb:10px;">"The Opalfin premium pellets enhanced my Arowana's depth spectrum within mere days. Exceptional purity."</p>
                <h4 style="font-size:10pt;">— Ranveer S., Satara</h4>
            </div>
            <div class="testi-card glass">
                <div class="stars">★★★★★</div>
                <p style="font-style:italic; font-size:10pt; color:var(--text-muted); mb:10px;">"Flawless filtration power with the Bluepet 6000F system. Crystal clear aquatic definition."</p>
                <h4 style="font-size:10pt;">— Amit K., Karad Local</h4>
            </div>
        </div>

        <div class="faq-section">
            <div class="section-title"><span></span>Knowledge Bases</div>
            <div class="faq-item">
                <button class="faq-trigger" onclick="toggleFaq(this)">How are orders systematically collected? <span>+</span></button>
                <div class="faq-content"><p style="padding:20px 0;">This portal is a direct collection suite. Once checked out, a detailed cryptographic list parses directly to the owner via Formspree, and triggers a synced WhatsApp order prompt to close logistics tracking manually with zero platform markups.</p></div>
            </div>
            <div class="faq-item">
                <button class="faq-trigger" onclick="toggleFaq(this)">Can I return live fish species? <span>+</span></button>
                <div class="faq-content"><p style="padding:20px 0;">To preserve rigid biosecurity standards, live species transactions are carefully scrutinized and final. Live verification can be executed via dynamic WhatsApp video link during packaging.</p></div>
            </div>
        </div>
    </main>

    <div class="floating-actions">
        <a id="float-whatsapp-link" href="https://wa.me/917350039389" target="_blank" class="float-btn float-wa" title="Secure WhatsApp Dispatcher Line">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z"></path></svg>
        </a>
        <a id="float-phone-link" href="tel:7350039389" class="float-btn float-call" title="Direct Telephony Voice Link">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"></path></svg>
        </a>
    </div>
    <button class="nav-btn float-btn" id="scroll-top" onclick="window.scrollTo({top:0, behavior:'smooth'})">↑</button>

    <div class="drawer" id="cart-drawer">
        <div class="drawer-header">
            <h3>Boutique Cargo Container</h3>
            <button class="close-btn" onclick="closeDrawer('cart-drawer')">✕</button>
        </div>
        <div class="drawer-body" id="cart-items-wrapper">
            </div>
        <div class="drawer-footer">
            <div style="display:flex; justify-content:space-between; margin-bottom:20px; font-weight:700;">
                <span>Consolidated Subtotal:</span>
                <span id="cart-grand-total">₹0</span>
            </div>
            <button class="cta-btn" style="width:100%; justify-content:center;" onclick="openCheckoutModal()">Advance To Checkout Core</button>
        </div>
    </div>

    <div class="drawer" id="wishlist-drawer">
        <div class="drawer-header">
            <h3>Desired Acquisitions</h3>
            <button class="close-btn" onclick="closeDrawer('wishlist-drawer')">✕</button>
        </div>
        <div class="drawer-body" id="wishlist-items-wrapper">
            </div>
    </div>

    <div class="overlay" id="quickview-modal">
        <div class="modal-box glass" id="qv-modal-content">
            </div>
    </div>

    <div class="overlay" id="checkout-modal">
        <div class="modal-box glass">
            <div style="display:flex; justify-content:between; align-items:center; margin-bottom:25px;">
                <h3>Logistics Allocation Profile</h3>
                <button class="close-btn" onclick="closeOverlay('checkout-modal')" style="margin-left:auto;">✕</button>
            </div>
            <form id="checkout-form" action="https://formspree.io/f/mnqeozgq" method="POST" onsubmit="handleCheckoutSubmission(event)">
                <div class="form-group">
                    <label>Acquirer Legal Identity Name *</label>
                    <input type="text" name="customer_name" required placeholder="e.g. Rahul Sharma">
                </div>
                <div class="form-group">
                    <label>Telephony Destination Contact Line *</label>
                    <input type="tel" name="customer_phone" required placeholder="e.g. 9876543210">
                </div>
                <div class="form-group">
                    <label>Physical Delivery Infrastructure Axis Address *</label>
                    <textarea name="customer_address" rows="3" required placeholder="Complete location layout..."></textarea>
                </div>
                <div class="form-group">
                    <label>Special Tactical Instructions (Optional)</label>
                    <textarea name="customer_notes" rows="2" placeholder="Aquatic custom setup markers..."></textarea>
                </div>
                
                <input type="hidden" name="_subject" value="NEW LUXURY AQUA ORDER INCOMING">
                <input type="hidden" name="compiled_manifest_order" id="hidden-manifest-field">
                
                <button type="submit" class="cta-btn" style="width:100%; justify-content:center; margin-top:10px;">Transmit Cargo Manifest</button>
            </form>
        </div>
    </div>

    <div class="overlay" id="success-modal">
        <div class="modal-box glass" style="text-align:center;">
            <div style="width:80px; height:80px; background:var(--accent-green); color:#fff; border-radius:50%; display:flex; justify-content:center; align-items:center; margin:0 auto 20px; font-size:32px; font-weight:bold;">✓</div>
            <h2>Manifest Transmitted Securely</h2>
            <p style="color:var(--text-muted); margin:15px 0 25px;">Your boutique specification file has dropped safely to our central parsing desk. Launch the automated WhatsApp validation tracker below to authorize immediate routing clear paths.</p>
            <a id="success-wa-action-btn" href="#" target="_blank" class="cta-btn" style="background:#25d366; color:white; box-shadow:0 10px 20px rgba(37,211,102,0.3);">
                <span>Launch WhatsApp Verification Link</span>
            </a>
        </div>
    </div>

    <div class="overlay" id="admin-modal">
        <div class="modal-box glass" style="max-width:1000px; width:95vw;">
            <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:25px; border-bottom:1px solid var(--border-glass); padding-bottom:15px;">
                <div>
                    <h3>Central Telemetry Control Core</h3>
                    <p style="font-size:8pt; color:var(--text-muted);">SMART AQUA MASTER PLATFORM MANAGEMENT</p>
                </div>
                <button class="close-btn" onclick="closeOverlay('admin-modal')">✕</button>
            </div>
            
            <div class="admin-layout">
                <div class="admin-sidebar">
                    <button class="admin-tab-btn active" onclick="switchAdminTab('pane-products', this)">Boutique Matrix</button>
                    <button class="admin-tab-btn" onclick="switchAdminTab('pane-categories', this)">Category Matrix</button>
                    <button class="admin-tab-btn" onclick="switchAdminTab('pane-settings', this)">Boutique Parameters</button>
                    <button class="admin-tab-btn" onclick="switchAdminTab('pane-themes', this)">Display Ecosystem</button>
                    <button class="admin-tab-btn" onclick="switchAdminTab('pane-backup', this)">Data Vault System</button>
                </div>
                <div class="admin-main-stage">
                    
                    <div class="admin-pane active" id="pane-products">
                        <div style="display:flex; justify-content:between; align-items:center; mb:20px; margin-bottom: 15px;">
                            <h4 style="font-size:12pt;">Asset Directory Registry</h4>
                            <button class="cta-btn" style="padding:8px 16px; font-size:9pt; margin-left:auto;" onclick="openProductForm()">+ Append Luxury Item</button>
                        </div>
                        
                        <div id="product-form-wrapper" style="display:none; background:rgba(0,0,0,0.2); padding:20px; border-radius:16px; margin-bottom:20px; border:1px solid var(--border-glass);">
                            <h5 id="form-product-title" style="margin-bottom:15px; font-size:11pt;">Configure Identity Matrix</h5>
                            <input type="hidden" id="form-product-index">
                            <div style="display:grid; grid-template-columns:1fr 1fr; gap:15px;">
                                <div class="form-group"><label>Asset Descriptor Title</label><input type="text" id="pform-name"></div>
                                <div class="form-group"><label>Base Value Tier (₹)</label><input type="number" id="pform-price"></div>
                                <div class="form-group"><label>Promo Yield Price (Optional)</label><input type="number" id="pform-offer-price"></div>
                                <div class="form-group"><label>Classification Category</label><select id="pform-category"></select></div>
                                <div class="form-group" style="grid-column: span 2;"><label>Asset Graphics Deployment URI (imgbb Link)</label><input type="text" id="pform-image"></div>
                                <div class="form-group" style="grid-column: span 2;"><label>Technical Feature Details Narrative</label><textarea id="pform-desc" rows="2"></textarea></div>
                            </div>
                            <div style="display:flex; gap:15px; margin-top:10px;">
                                <label><input type="checkbox" id="pform-featured"> Mark As Showcase Star ⭐</label>
                                <label><input type="checkbox" id="pform-bestseller"> Toggle Hot Status Badge 🔥</label>
                                <label><input type="checkbox" id="pform-instock" checked> Warehouse Stock Clear Path</label>
                            </div>
                            <div style="display:flex; gap:10px; justify-content:flex-end; margin-top:15px;">
                                <button class="cat-btn" onclick="document.getElementById('product-form-wrapper').style.display='none'">Abort</button>
                                <button class="cta-btn" style="padding:8px 20px; font-size:10pt;" onclick="saveProductForm()">Commit Changes</button>
                            </div>
                        </div>

                        <div style="overflow-x:auto;">
                            <table class="admin-table">
                                <thead>
                                    <tr>
                                        <th>Item Asset</th>
                                        <th>Category</th>
                                        <th>Price Metrics</th>
                                        <th>Status Badges</th>
                                        <th>Priority Sorting</th>
                                        <th>Mod Actions</th>
                                    </tr>
                                </thead>
                                <tbody id="admin-products-table-body">
                                    </tbody>
                            </table>
                        </div>
                    </div>

                    <div class="admin-pane" id="pane-categories">
                        <h4 style="margin-bottom:15px;">Category Registry Matrix</h4>
                        <div style="display:flex; gap:10px; margin-bottom:25px;">
                            <input type="text" id="new-cat-input" class="glass" style="background:var(--bg-surface-solid); border:1px solid var(--border-glass); padding:10px 15px; border-radius:10px; flex-grow:1; color:white;" placeholder="Enter fresh category identifier...">
                            <button class="cta-btn" style="padding:10px 20px; font-size:9pt;" onclick="addCategorySystem()">Append Core Cluster</button>
                        </div>
                        <div id="admin-categories-list-wrapper">
                            </div>
                    </div>

                    <div class="admin-pane" id="pane-settings">
                        <h4 style="margin-bottom:15px;">Storefront Variable Parameters</h4>
                        <div style="display:grid; grid-template-columns:1fr 1fr; gap:15px;">
                            <div class="form-group"><label>Shop Brand Name</label><input type="text" id="sform-name"></div>
                            <div class="form-group"><label>Tagline Subtext Motto</label><input type="text" id="sform-tagline"></div>
                            <div class="form-group"><label>Telephony Secure Line</label><input type="text" id="sform-phone"></div>
                            <div class="form-group"><label>Email Axis Route</label><input type="email" id="sform-email"></div>
                            <div class="form-group" style="grid-column: span 2;"><label>Physical Geographic Grid Hub Address</label><input type="text" id="sform-address"></div>
                            <div class="form-group" style="grid-column: span 2;"><label>Main Landing Vector Showcase Image URL</label><input type="text" id="sform-hero"></div>
                        </div>
                        <button class="cta-btn" style="margin-top:15px; padding:10px 25px;" onclick="saveStoreSettings()">Commit Global Parameter Sets</button>
                    </div>

                    <div class="admin-pane" id="pane-themes">
                        <h4 style="margin-bottom:15px;">Aesthetics Environmental Matrix</h4>
                        <p style="font-size:9pt; color:var(--text-muted); margin-bottom:20px;">Select deep processing styling algorithms applied instantly to user endpoints browsers.</p>
                        <div style="display:grid; grid-template-columns: repeat(auto-fit, minmax(140px, 1fr)); gap:15px;">
                            <button class="cat-btn" style="padding:20px;" onclick="switchThemeSystem('dark')">🌌 Abyssal Depths</button>
                            <button class="cat-btn" style="padding:20px;" onclick="switchThemeSystem('light')">☀️ Polar Glare</button>
                            <button class="cat-btn" style="padding:20px;" onclick="switchThemeSystem('aqua')">🌀 Oceanic Reef</button>
                            <button class="cat-btn" style="padding:20px;" onclick="switchThemeSystem('emerald')">🌿 Amazon Foliage</button>
                            <button class="cat-btn" style="padding:20px;" onclick="switchThemeSystem('black')">♟️ Carbon Elite</button>
                        </div>
                    </div>

                    <div class="admin-pane" id="pane-backup">
                        <h4 style="margin-bottom:15px;">Secure Platform Data Ledger Vault</h4>
                        <p style="font-size:9pt; color:var(--text-muted); margin-bottom:25px;">Export structural definitions matrix files down locally or parsing state variables updates effortlessly.</p>
                        <div style="display:flex; flex-wrap:wrap; gap:15px;">
                            <button class="add-cart-btn" style="width:auto; padding:12px 25px;" onclick="exportDataLedger()">Download Snapshot File Ledger (JSON)</button>
                            <button class="add-cart-btn" style="width:auto; padding:12px 25px;" onclick="document.getElementById('import-file-trigger').click()">Upload Restructuring File Ledger</button>
                            <input type="file" id="import-file-trigger" style="display:none;" accept=".json" onchange="importDataLedger(event)">
                        </div>
                        <hr style="border:none; border-top:1px solid var(--border-glass); margin:30px 0;">
                        <h4 style="color:#ef4444; margin-bottom:10px;">Dangerous Nuclear Operation Overrides</h4>
                        <p style="font-size:9pt; color:var(--text-muted); margin-bottom:15px;">Wipe localized parameters completely resetting state structures instantly back to vendor baseline default settings arrays.</p>
                        <button class="cta-btn" style="background:#ef4444; color:white; border:none; box-shadow:none; padding:10px 20px;" onclick="purgeSystemClear()">Execute Absolute Purge Clear Reset</button>
                    </div>

                </div>
            </div>
        </div>
    </div>

    <footer>
        <div class="footer-grid">
            <div class="footer-logo">
                <h4 id="footer-brand-name">SMART AQUA CART</h4>
                <p id="footer-brand-motto">PREMIUM QUALITY FISHES AND THEIR ACCESSORIES</p>
                <p style="font-size:8.5pt; margin-top:15px; color:var(--text-muted);" id="footer-address-label">KARAD, DIST- SATARA, MAHARASHTRA</p>
            </div>
            <div>
                <h5 style="color:#fff; margin-bottom:15px; font-size:11pt;">Central Coordinates</h5>
                <p style="font-size:9.5pt; margin-bottom:8px;">Line: <span id="footer-phone-label">+91 7350039389</span></p>
                <p style="font-size:9.5pt;">Inbound: <span id="footer-email-label" style="word-break:break-all;">smartaquariumkarad634@gmail.com</span></p>
            </div>
            <div>
                <h5 style="color:#fff; margin-bottom:15px; font-size:11pt;">Platform Structural Integrity</h5>
                <p style="font-size:8.5pt; color:var(--text-muted);">Zero framework architecture utilizing state-allocated local database variables engines mapping out optimized offline responsive capabilities flawlessly.</p>
            </div>
        </div>
        <div style="border-top:1px solid var(--border-glass); padding-top:20px; display:flex; justify-content:space-between; flex-wrap:wrap; font-size:8.5pt;">
            <span>© 2026 SMART AQUA CART. All Sovereignty Protected Reserved.</span>
            <span>Handcrafted In Purity</span>
        </div>
    </footer>

    <script>
        // 17 RAW DEFAULT CORE PRODUCTS PRELOAD DATABASE OBJECT SETS
        const PRELOAD_PRODUCTS = [
            { id: "p1", name: "Bluepet Aquarium Powerfilter 6000F", price: 320, offerPrice: null, category: "Filters", image: "https://i.ibb.co/4ZxR9JpS/1782745859148.webp", desc: "High-throughput power head operational matrix configured for large bio-load aquariums.", isFeatured: true, isBestseller: true, inStock: true },
            { id: "p2", name: "Bluepet Aquarium Powerfilter 1000F", price: 350, offerPrice: 320, category: "Filters", image: "https://i.ibb.co/Z6D6DWRM/product-jpeg.jpg", desc: "Meticulous internal mechanical filtration module ensuring steady hydrodynamic clear states.", isFeatured: false, isBestseller: false, inStock: true },
            { id: "p3", name: "Premium sponge filter XF-380", price: 250, offerPrice: null, category: "Filters", image: "https://i.ibb.co/Jjdm4N7b/g-Iz-Ozi-HU.webp", desc: "Super-dense dual foam bio-filtration grid for sensitive fry breeding zones.", isFeatured: true, isBestseller: false, inStock: true },
            { id: "p4", name: "Premium Sponge Filter XF-280", price: 200, offerPrice: null, category: "Filters", image: "https://i.ibb.co/dJHDzpLN/71p4-Sso-Vvj-L.jpg", desc: "Ergonomic sub-surface sponge element optimized for deep beneficial bacteria colonies.", isFeatured: false, isBestseller: false, inStock: true },
            { id: "p5", name: "Aquarium Airpump For fishes", price: 200, offerPrice: 180, category: "Filters", image: "https://i.ibb.co/rRgyjSwj/portable-aquarium-air-pump.jpg", desc: "Whisper-quiet pneumatic structural pump pushing sustained high gaseous oxygen flow rates.", isFeatured: false, isBestseller: true, inStock: true },
            { id: "p6", name: "6 in 1 Biological Sponge", price: 280, offerPrice: null, category: "Filters", image: "https://i.ibb.co/tPM0vQdL/1683465900149-SKU-0046-0.webp", desc: "Multi-layered compound processing filtration pad capturing particulate micro-debris easily.", isFeatured: true, isBestseller: false, inStock: true },
            { id: "p7", name: "Best Quality Siphon Pipe", price: 180, offerPrice: null, category: "Filters", image: "https://i.ibb.co/DHPpFDLN/51j0-X8-B5-KQL.jpg", desc: "Heavy-duty manual hydraulic priming vacuum pipe for precision substrate cleansing tasks.", isFeatured: false, isBestseller: false, inStock: true },
            { id: "p8", name: "Premium Colour Enhancing Royal arowana Food (100gm)", price: 250, offerPrice: 220, category: "Fish Food", image: "https://i.ibb.co/HTmSKwCB/71c-OFRBmi-PL.jpg", desc: "Astaxanthin infused top-tier nutritional formulas mapping vivid spectrum adjustments on monster specimens.", isFeatured: true, isBestseller: true, inStock: true },
            { id: "p9", name: "Taiyo Turtle Food 250gm", price: 250, offerPrice: null, category: "Turtle Food", image: "https://i.ibb.co/ccnMLzTW/51yv-UMAh-P6-L-AC-UF1000-1000-QL80.jpg", desc: "Calcium-dense formulated floating sticks maintaining rigid carapace optimization paths safely.", isFeatured: false, isBestseller: false, inStock: true },
            { id: "p10", name: "Tokyo Gold turtle food 500gm", price: 350, offerPrice: null, category: "Turtle Food", image: "https://i.ibb.co/5Xc9t7DZ/7183b1-K6ah-L.jpg", desc: "Bulk macro-nutrient dense ration pack supporting pristine developmental metrics naturally.", isFeatured: false, isBestseller: true, inStock: true },
            { id: "p11", name: "Taiyo Pink Fish Food 1kg", price: 550, offerPrice: 499, category: "Fish Food", image: "https://i.ibb.co/gbCY2zb9/61-Sf-T-xt-Uo-L.jpg", desc: "Universal high-protein complete community maintenance pellet matrices for large collector setups.", isFeatured: true, isBestseller: false, inStock: true },
            { id: "p12", name: "Taiyo Pink Fish Food 500gm", price: 350, offerPrice: null, category: "Fish Food", image: "https://i.ibb.co/ymJx94d5/Taiyo-Pink.png", desc: "Mid-tier volume preservation package built for everyday omnivorous marine and freshwater varieties.", isFeatured: false, isBestseller: false, inStock: true },
            { id: "p13", name: "Opalfin Premium Quality Ultrafine Fish food (100gm)", price: 120, offerPrice: null, category: "Fish Food", image: "https://i.ibb.co/M53dPDy9/IMG-20260629-214330.jpg", desc: "Micro-milled slow-sinking nutrient crumble engineered for immediate tetras and nano species capture.", isFeatured: false, isBestseller: false, inStock: true },
            { id: "p14", name: "Opalfin Nutrimax Fish Food", price: 100, offerPrice: 90, category: "Fish Food", image: "https://i.ibb.co/6Rbdg0JV/IMG-20260629-202101.jpg", desc: "Probiotic enrichment vectors added to enhance complete metabolic health loops.", isFeatured: false, isBestseller: false, inStock: true },
            { id: "p15", name: "Opalfin Xtrabite Fish Food Pellets 100gm (Container)", price: 120, offerPrice: null, category: "Fish Food", image: "https://i.ibb.co/M53dPDy9/IMG-20260629-214330.jpg", desc: "Hermetically sealed freshness canister preservation array preventing nutritional oxidation degradation.", isFeatured: false, isBestseller: false, inStock: true },
            { id: "p16", name: "Opalfin Guppy Plus", price: 150, offerPrice: 130, category: "Fish Food", image: "https://i.ibb.co/LDTmp86h/IMG-20260629-202123.jpg", desc: "Specialized dynamic structural granular layout keeping fin extensions looking pristine and full.", isFeatured: true, isBestseller: false, inStock: true },
            { id: "p17", name: "Optimum Premium Fish Food 100gm", price: 80, offerPrice: null, category: "Fish Food", image: "https://i.ibb.co/HDtWZtK8/Untitleddesign-64-fb49fadc-f93d-47f9-ae9c-ccdd929f4e3c.png", desc: "Highly stable highly popular structural standard value compound formulation across Indian domains.", isFeatured: false, isBestseller: true, inStock: true }
        ];

        const DEFAULT_CATEGORIES = ["All Matrix", "Live Fishes", "Fish Food", "Filters", "Air Pumps", "Sponge Filters", "Aquarium Accessories", "Turtle Food", "Aquascaping"];

        const DEFAULT_SETTINGS = {
            name: "SMART AQUA CART",
            tagline: "PREMIUM QUALITY FISHES AND THEIR ACCESSORIES",
            phone: "7350039389",
            email: "smartaquariumkarad634@gmail.com",
            address: "KARAD, DIST- SATARA, MAHARASHTRA",
            heroImage: "https://i.ibb.co/tPM0vQdL/1683465900149-SKU-0046-0.webp",
            theme: "dark"
        };

        // RUNTIME INTERNAL VARIABLE STATE ARRAYS
        let state = {
            products: [],
            categories: [],
            settings: {},
            cart: [],
            wishlist: [],
            recent: [],
            currentFilter: "All Matrix"
        };

        // ENGINE APPARATUS INITIALIZATION
        window.addEventListener('DOMContentLoaded', () => {
            initializeDatabaseEngine();
            bindDynamicDOMListeners();
            setTimeout(() => {
                const loader = document.getElementById('loading-screen');
                if (loader) loader.style.opacity = '0';
                setTimeout(() => loader ? loader.style.display = 'none' : null, 600);
            }, 800);
        });

        function initializeDatabaseEngine() {
            // Read or populate local database matrices
            if (!localStorage.getItem('sa_products')) {
                localStorage.setItem('sa_products', JSON.stringify(PRELOAD_PRODUCTS));
                localStorage.setItem('sa_categories', JSON.stringify(DEFAULT_CATEGORIES));
                localStorage.setItem('sa_settings', JSON.stringify(DEFAULT_SETTINGS));
                localStorage.setItem('sa_wishlist', JSON.stringify([]));
                localStorage.setItem('sa_recent', JSON.stringify([]));
            }

            state.products = JSON.parse(localStorage.getItem('sa_products'));
            state.categories = JSON.parse(localStorage.getItem('sa_categories'));
            state.settings = JSON.parse(localStorage.getItem('sa_settings'));
            state.wishlist = JSON.parse(localStorage.getItem('sa_wishlist')) || [];
            state.recent = JSON.parse(localStorage.getItem('sa_recent')) || [];
            state.cart = JSON.parse(localStorage.getItem('sa_cart')) || [];

            applyThemeState(state.settings.theme || 'dark');
            syncGlobalDynamicText();
            renderCategoryTrack();
            renderProductShowcase();
            updateCountBadges();
        }

        function syncGlobalDynamicText() {
            document.getElementById('sett-shop-name').innerText = state.settings.name;
            document.getElementById('sett-shop-tagline').innerText = state.settings.tagline;
            document.getElementById('footer-brand-name').innerText = state.settings.name;
            document.getElementById('footer-brand-motto').innerText = state.settings.tagline;
            document.getElementById('footer-address-label').innerText = state.settings.address;
            document.getElementById('footer-phone-label').innerText = "+91 " + state.settings.phone;
            document.getElementById('footer-email-label').innerText = state.settings.email;
            document.getElementById('hero-banner-img').src = state.settings.heroImage;
            document.getElementById('float-whatsapp-link').href = `https://wa.me/91${state.settings.phone}`;
            document.getElementById('float-phone-link').href = `tel:${state.settings.phone}`;
        }

        // SCROLL EFFECTS & LONG PRESS ENGINE
        function bindDynamicDOMListeners() {
            window.addEventListener('scroll', () => {
                const header = document.querySelector('header');
                const scrollBtn = document.getElementById('scroll-top');
                if (window.scrollY > 80) {
                    header.classList.add('scrolled');
                    if(scrollBtn) scrollBtn.style.display = 'flex';
                } else {
                    header.classList.remove('scrolled');
                    if(scrollBtn) scrollBtn.style.display = 'none';
                }
            });

            // Master hidden admin logic panel activation tracking mechanism via logo longpress
            const logoTrigger = document.getElementById('logo-trigger');
            let logoTimer;
            
            logoTrigger.addEventListener('mousedown', startPress);
            logoTrigger.addEventListener('touchstart', startPress, {passive: true});
            logoTrigger.addEventListener('mouseup', clearPress);
            logoTrigger.addEventListener('mouseleave', clearPress);
            logoTrigger.addEventListener('touchend', clearPress);

            function startPress() { logoTimer = setTimeout(triggerAdmin, 3000); }
            function clearPress() { clearTimeout(logoTimer); }
        }

        function triggerAdmin() {
            const pass = prompt("Provide decryption validation credentials password code sequence:", "");
            if (pass === "smartaquarium123") {
                spawnToastNotification("Credentials clear. Panel unlocked.");
                openOverlay('admin-modal');
                hydrateAdminDashboard();
            } else if (pass !== null) {
                alert("Unauthorized intrusion vector detected. Sequence terminated.");
            }
        }

        // CATEGORY VIEW POPULATER ENGINE
        function renderCategoryTrack() {
            const track = document.getElementById('category-bar');
            track.innerHTML = "";
            state.categories.forEach(cat => {
                const btn = document.createElement('button');
                btn.className = `cat-btn ${state.currentFilter === cat ? 'active' : ''}`;
                btn.innerText = cat;
                btn.onclick = () => {
                    state.currentFilter = cat;
                    document.querySelectorAll('.cat-btn').forEach(b => b.classList.remove('active'));
                    btn.classList.add('active');
                    renderProductShowcase();
                };
                track.appendChild(btn);
            });
        }

        // PRODUCT CARD GRID RENDERING CORE ENGINE
        function renderProductShowcase() {
            const container = document.getElementById('product-container');
            container.innerHTML = "";

            const query = document.getElementById('main-search').value.toLowerCase();
            const hQuery = document.getElementById('global-search').value.toLowerCase();
            const activeQuery = query || hQuery;

            let filtered = state.products;

            // Apply category filter logic variables
            if (state.currentFilter !== "All Matrix") {
                filtered = filtered.filter(p => p.category.toLowerCase() === state.currentFilter.toLowerCase());
            }

            // Apply specific textual filter bounds strings
            if (activeQuery) {
                filtered = filtered.filter(p => p.name.toLowerCase().includes(activeQuery) || p.desc.toLowerCase().includes(activeQuery));
            }

            if(filtered.length === 0) {
                container.innerHTML = `<div style="grid-column:1/-1; text-align:center; padding:40px; color:var(--text-muted);">No luxury aquascaping elements matching search profile bounds parameters.</div>`;
                return;
            }

            filtered.forEach(prod => {
                const isWish = state.wishlist.includes(prod.id);
                const hasOffer = prod.offerPrice && prod.offerPrice < prod.price;
                const activePrice = hasOffer ? prod.offerPrice : prod.price;

                const card = document.createElement('div');
                card.className = "product-card glass";
                
                let badgesHTML = "";
                if (!prod.inStock) badgesHTML += `<span class="badge-tag badge-outofstock">Depleted</span>`;
                if (prod.isBestseller) badgesHTML += `<span class="badge-tag badge-best">Hot 🔥</span>`;
                if (prod.isFeatured) badgesHTML += `<span class="badge-tag badge-feat">Star ⭐</span>`;
                if (hasOffer) badgesHTML += `<span class="badge-tag badge-discount">-${Math.round((prod.price-prod.offerPrice)/prod.price*100)}%</span>`;

                card.innerHTML = `
                    <div class="card-img-holder" onclick="launchQuickView('${prod.id}')">
                        <div class="card-badges">${badgesHTML}</div>
                        <button class="card-wish-btn ${isWish ? 'active' : ''}" onclick="event.stopPropagation(); toggleWishlistSystem('${prod.id}')">
                            <svg width="18" height="18" viewBox="0 0 24 24"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
                        </button>
                        <img src="${prod.image}" alt="${prod.name}" loading="lazy">
                    </div>
                    <div class="card-details">
                        <span class="card-cat">${prod.category}</span>
                        <h4 class="card-title" onclick="launchQuickView('${prod.id}')">${prod.name}</h4>
                        <div class="card-price-row">
                            <span class="current-price">₹${activePrice}</span>
                            ${hasOffer ? `<span class="old-price">₹${prod.price}</span>` : ''}
                        </div>
                        <button class="add-cart-btn" ${!prod.inStock ? 'disabled' : ''} onclick="appendItemToCart('${prod.id}')">
                            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M6 2L3 6v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V6l-3-4z"></path><line x1="3" y1="6" x2="21" y2="6"></line></svg>
                            <span>${prod.inStock ? 'Allocate Cargo Container' : 'Out of Stock Supply'}</span>
                        </button>
                    </div>
                `;
                container.appendChild(card);
            });
        }

        function toggleSearch() {
            const hSearch = document.getElementById('header-search-wrap');
            if(hSearch.style.display === 'none') {
                hSearch.style.display = 'block';
                document.getElementById('global-search').focus();
            } else {
                hSearch.style.display = 'none';
                document.getElementById('global-search').value = "";
                renderProductShowcase();
            }
            document.getElementById('global-search').addEventListener('input', renderProductShowcase);
        }

        function filterShowcase() { renderProductShowcase(); }
        function scrollToProducts() { document.getElementById('showcase-anchor').scrollIntoView({behavior: 'smooth'}); }

        // OVERLAY CONTROLS SYSTEM APPARATUS
        function openOverlay(id) { document.getElementById(id).classList.add('active'); }
        function closeOverlay(id) { document.getElementById(id).classList.remove('active'); }
        function openDrawer(id) { 
            document.getElementById(id).classList.add('active'); 
            if(id === 'cart-drawer') renderCartContents();
            if(id === 'wishlist-drawer') renderWishlistContents();
        }
        function closeDrawer(id) { document.getElementById(id).classList.remove('active'); }

        // CART LOGICS AND DISPATCH OPERATIONS
        function appendItemToCart(id) {
            const prod = state.products.find(p => p.id === id);
            if(!prod || !prod.inStock) return;

            const existing = state.cart.find(item => item.id === id);
            if(existing) {
                existing.qty += 1;
            } else {
                state.cart.push({ id: id, qty: 1 });
            }
            localStorage.setItem('sa_cart', JSON.stringify(state.cart));
            updateCountBadges();
            spawnToastNotification(`Appended ${prod.name} down into logistics stream.`);
        }

        function adjustCartQty(id, delta) {
            const target = state.cart.find(item => item.id === id);
            if(!target) return;
            target.qty += delta;
            if(target.qty <= 0) {
                state.cart = state.cart.filter(item => item.id !== id);
            }
            localStorage.setItem('sa_cart', JSON.stringify(state.cart));
            updateCountBadges();
            renderCartContents();
        }

        function renderCartContents() {
            const wrapper = document.getElementById('cart-items-wrapper');
            wrapper.innerHTML = "";
            let grandTotal = 0;

            if(state.cart.length === 0) {
                wrapper.innerHTML = `<p style="text-align:center; color:var(--text-muted); padding:30px 0;">Cargo stack completely empty.</p>`;
                document.getElementById('cart-grand-total').innerText = "₹0";
                return;
            }

            state.cart.forEach(cItem => {
                const prod = state.products.find(p => p.id === cItem.id);
                if(!prod) return;
                const currentPrice = (prod.offerPrice && prod.offerPrice < prod.price) ? prod.offerPrice : prod.price;
                const rowTotal = currentPrice * cItem.qty;
                grandTotal += rowTotal;

                const row = document.createElement('div');
                row.className = "cart-item";
                row.innerHTML = `
                    <img src="${prod.image}" alt="${prod.name}">
                    <div class="cart-item-details">
                        <h5 style="font-size:9.5pt; font-weight:700;">${prod.name}</h5>
                        <p style="font-size:8.5pt; color:var(--accent-primary); margin-top:4px;">₹${currentPrice} × ${cItem.qty} = ₹${rowTotal}</p>
                        <div class="qty-control">
                            <button class="qty-btn" onclick="adjustCartQty('${prod.id}', -1)">-</button>
                            <span style="font-size:9.5pt; font-weight:600;">${cItem.qty}</span>
                            <button class="qty-btn" onclick="adjustCartQty('${prod.id}', 1)">+</button>
                        </div>
                    </div>
                    <button class="close-btn" style="width:28px; height:28px; font-size:8pt;" onclick="adjustCartQty('${prod.id}', -${cItem.qty})">✕</button>
                `;
                wrapper.appendChild(row);
            });

            document.getElementById('cart-grand-total').innerText = "₹" + grandTotal;
        }

        function updateCountBadges() {
            document.getElementById('cart-count').innerText = state.cart.reduce((acc, i) => acc + i.qty, 0);
            document.getElementById('wishlist-count').innerText = state.wishlist.length;
        }

        // WISHLIST LOGICS SYSTEM VARIABLES
        function toggleWishlistSystem(id) {
            if(state.wishlist.includes(id)) {
                state.wishlist = state.wishlist.filter(i => i !== id);
                spawnToastNotification("Item removed from desired inventory sets.");
            } else {
                state.wishlist.push(id);
                spawnToastNotification("Added item onto internal desired listings.");
            }
            localStorage.setItem('sa_wishlist', JSON.stringify(state.wishlist));
            updateCountBadges();
            renderProductShowcase();
        }

        function renderWishlistContents() {
            const wrapper = document.getElementById('wishlist-items-wrapper');
            wrapper.innerHTML = "";

            if(state.wishlist.length === 0) {
                wrapper.innerHTML = `<p style="text-align:center; color:var(--text-muted); padding:30px 0;">No prioritized wishlist items found.</p>`;
                return;
            }

            state.wishlist.forEach(wid => {
                const prod = state.products.find(p => p.id === wid);
                if(!prod) return;
                const activePrice = (prod.offerPrice && prod.offerPrice < prod.price) ? prod.offerPrice : prod.price;

                const row = document.createElement('div');
                row.className = "cart-item";
                row.innerHTML = `
                    <img src="${prod.image}" alt="${prod.name}">
                    <div class="cart-item-details">
                        <h5 style="font-size:9.5pt; font-weight:700;">${prod.name}</h5>
                        <p style="font-size:8.5pt; color:var(--accent-primary); margin-top:4px;">₹${activePrice}</p>
                    </div>
                    <button class="add-cart-btn" style="width:auto; padding:6px 12px; font-size:8pt;" ${!prod.inStock ? 'disabled' : ''} onclick="appendItemToCart('${prod.id}')">Add</button>
                    <button class="close-btn" style="width:28px; height:28px; font-size:8pt; margin-left:6px;" onclick="toggleWishlistSystem('${prod.id}'); renderWishlistContents();">✕</button>
                `;
                wrapper.appendChild(row);
            });
        }

        // PRODUCT QUICK VIEW POPUP LOGIC WITH RELATED & RECENT ACTIONS
        function launchQuickView(id) {
            const prod = state.products.find(p => p.id === id);
            if(!prod) return;

            // Log item directly into recently viewed arrays data sets
            if(!state.recent.includes(id)) {
                state.recent.unshift(id);
                if(state.recent.length > 6) state.recent.pop();
                localStorage.setItem('sa_recent', JSON.stringify(state.recent));
                renderRecentScrollerModule();
            }

            const activePrice = (prod.offerPrice && prod.offerPrice < prod.price) ? prod.offerPrice : prod.price;
            const related = state.products.filter(p => p.category === prod.category && p.id !== prod.id).slice(0, 3);

            let relatedHTML = "";
            related.forEach(r => {
                relatedHTML += `
                    <div style="display:flex; gap:10px; align-items:center; background:rgba(0,0,0,0.1); padding:8px; border-radius:10px; cursor:pointer;" onclick="launchQuickView('${r.id}')">
                        <img src="${r.image}" style="width:40px; height:40px; object-fit:contain; border-radius:6px;">
                        <span style="font-size:8.5pt; font-weight:600; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; max-width:140px;">${r.name}</span>
                    </div>
                `;
            });

            const content = document.getElementById('qv-modal-content');
            content.innerHTML = `
                <button class="close-btn" style="position:absolute; top:20px; right:20px; z-index:10;" onclick="closeOverlay('quickview-modal')">✕</button>
                <div class="qv-grid">
                    <div class="qv-img-box">
                        <img src="${prod.image}" alt="${prod.name}">
                    </div>
                    <div style="display:flex; flex-direction:column; justify-content:center;">
                        <span style="font-size:8pt; text-transform:uppercase; color:var(--text-muted); font-weight:700;">${prod.category}</span>
                        <h3 style="font-size:16pt; font-weight:800; margin:5px 0 15px; line-height:1.3;">${prod.name}</h3>
                        <p style="font-size:9.5pt; color:var(--text-muted); margin-bottom:20px; line-height:1.5;">${prod.desc || 'No further blueprint parameters attached to this dynamic asset selection element module.'}</p>
                        <div style="display:flex; align-items:baseline; gap:10px; margin-bottom:20px;">
                            <span style="font-size:18pt; font-weight:800; color:var(--accent-primary)">₹${activePrice}</span>
                            ${prod.offerPrice ? `<span style="font-size:12pt; text-decoration:line-through; color:var(--text-muted)">₹${prod.price}</span>` : ''}
                        </div>
                        <div style="display:flex; gap:10px; margin-bottom:25px;">
                            <button class="cta-btn" style="flex-grow:1; justify-content:center;" ${!prod.inStock ? 'disabled' : ''} onclick="appendItemToCart('${prod.id}')">${prod.inStock ? 'Add Core Allocation' : 'Out of Stock'}</button>
                            <button class="nav-btn" onclick="copyAssetShareLink('${prod.id}')" title="Copy Structural Item Identifier Route Link">
                                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="18" cy="5" r="3"></circle><circle cx="6" cy="12" r="3"></circle><circle cx="18" cy="19" r="3"></circle><line x1="8.59" y1="13.51" x2="15.42" y2="17.49"></line><line x1="15.41" y1="6.51" x2="8.59" y2="10.49"></line></svg>
                            </button>
                        </div>
                        ${related.length > 0 ? `
                            <h5 style="font-size:9pt; text-transform:uppercase; margin-bottom:10px; color:var(--text-muted);">Affiliated Cluster Sets</h5>
                            <div style="display:grid; grid-template-columns:1fr 1fr; gap:10px;">${relatedHTML}</div>
                        ` : ''}
                    </div>
                </div>
            `;
            openOverlay('quickview-modal');
        }

        function renderRecentScrollerModule() {
            const block = document.getElementById('recent-view-section');
            const target = document.getElementById('recent-container');
            target.innerHTML = "";

            if(state.recent.length === 0) {
                block.style.display = 'none';
                return;
            }
            block.style.display = 'block';

            state.recent.forEach(rid => {
                const prod = state.products.find(p => p.id === rid);
                if(!prod) return;
                const card = document.createElement('div');
                card.className = "mini-card glass";
                card.onclick = () => launchQuickView(prod.id);
                card.innerHTML = `
                    <img src="${prod.image}" alt="${prod.name}">
                    <div class="mini-title">${prod.name}</div>
                    <div style="font-size:9pt; color:var(--accent-primary); font-weight:700; margin-top:4px;">₹${prod.price}</div>
                `;
                target.appendChild(card);
            });
        }

        function copyAssetShareLink(id) {
            const routeStr = window.location.origin + window.location.pathname + "?asset=" + id;
            navigator.clipboard.writeText(routeStr).then(() => {
                spawnToastNotification("Asset address map copied securely to local clipboard.");
            });
        }

        // TOAST NOTIFICATION CREATION FACTORY ENGINE
        function spawnToastNotification(text) {
            const container = document.getElementById('toast-container');
            const el = document.createElement('div');
            el.className = "toast";
            el.innerText = text;
            container.appendChild(el);
            setTimeout(() => {
                el.style.opacity = '0';
                setTimeout(() => el.remove(), 400);
            }, 3000);
        }

        function toggleFaq(btn) {
            const content = btn.nextElementSibling;
            if(content.style.maxHeight) {
                content.style.maxHeight = null;
                btn.querySelector('span').innerText = "+";
            } else {
                content.style.maxHeight = content.scrollHeight + "px";
                btn.querySelector('span').innerText = "-";
            }
        }

        // CHECKOUT DISPATCH INFRASTRUCTURE LOGICS
        function openCheckoutModal() {
            if(state.cart.length === 0) {
                alert("Cannot clear cargo vectors across an empty structural layout package manifest!");
                return;
            }
            closeDrawer('cart-drawer');
            
            // Build dynamic text value mappings representing complete shopping ledger arrays
            let manifestText = "=== SMART AQUA CART SYSTEM MANIFEST ===\\n";
            let grandTotal = 0;
            state.cart.forEach(item => {
                const p = state.products.find(pr => pr.id === item.id);
                if(!p) return;
                const cost = (p.offerPrice && p.offerPrice < p.price) ? p.offerPrice : p.price;
                manifestText += `• ${p.name} [x${item.qty}] @ ₹${cost} each = ₹${cost * item.qty}\\n`;
                grandTotal += (cost * item.qty);
            });
            manifestText += `----------------------------------------\\n`;
            manifestText += `CONSOLIDATED DISPATCH TOTAL VALUATION: ₹${grandTotal}\\n`;
            
            document.getElementById('hidden-manifest-field').value = manifestText;
            openOverlay('checkout-modal');
        }

        function handleCheckoutSubmission(event) {
            // Form handles native POST extraction routing downstream straight into Formspree action engine.
            // This function processes structural state variables cleanup asynchronously.
            spawnToastNotification("Transmitting structural log matrix rows...");
            
            // Build direct target text parameters mapping directly into subsequent WhatsApp execution routes
            const name = document.querySelector('input[name="customer_name"]').value;
            const phone = document.querySelector('input[name="customer_phone"]').value;
            const address = document.querySelector('textarea[name="customer_address"]').value;
            const notes = document.querySelector('textarea[name="customer_notes"]').value;
            
            let waText = `*NEW MANIFEST INBOUND - SMART AQUA CART*\\n\\n`;
            waText += `*Acquirer:* ${name}\\n`;
            waText += `*Phone:* ${phone}\\n`;
            waText += `*Destination:* ${address}\\n`;
            if(notes) waText += `*Notes:* ${notes}\\n\\n`;
            waText += `*Cargo Manifest Ordered Sets:*\\n`;
            
            let total = 0;
            state.cart.forEach(i => {
                const p = state.products.find(pr => pr.id === i.id);
                if(!p) return;
                const price = (p.offerPrice && p.offerPrice < p.price) ? p.offerPrice : p.price;
                waText += `- ${p.name} (x${i.qty}) @ ₹${price}\\n`;
                total += (price * i.qty);
            });
            waText += `\\n*Grand Aggregate Value:* ₹${total}`;
            
            const encoded = encodeURIComponent(waText);
            const targetWaURL = `https://wa.me/91${state.settings.phone}?text=${encoded}`;
            
            // Wipe operational internal cart arrays clean locally
            state.cart = [];
            localStorage.removeItem('sa_cart');
            updateCountBadges();

            // Intercept form post gracefully or push success route layout instantly
            setTimeout(() => {
                closeOverlay('checkout-modal');
                document.getElementById('success-wa-action-btn').href = targetWaURL;
                openOverlay('success-modal');
            }, 800);
        }

        // THEME ALLOCATION MATRIX PROCESSOR
        function applyThemeState(themeName) {
            document.body.className = "";
            document.body.classList.add("theme-" + themeName);
        }

        // ==========================================
        // DYNAMIC HIDDEN BACK PANEL OWNER LOGICS CORE
        // ==========================================
        function hydrateAdminDashboard() {
            populateAdminProductsTable();
            populateAdminCategoriesList();
            
            // Populate storefront value inputs
            document.getElementById('sform-name').value = state.settings.name;
            document.getElementById('sform-tagline').value = state.settings.tagline;
            document.getElementById('sform-phone').value = state.settings.phone;
            document.getElementById('sform-email').value = state.settings.email;
            document.getElementById('sform-address').value = state.settings.address;
            document.getElementById('sform-hero').value = state.settings.heroImage;

            // Prepare categories select inside product editor form fields list
            const select = document.getElementById('pform-category');
            select.innerHTML = "";
            state.categories.filter(c => c !== "All Matrix").forEach(c => {
                select.innerHTML += `<option value="${c}">${c}</option>`;
            });
        }

        function switchAdminTab(targetPaneId, clickedBtn) {
            document.querySelectorAll('.admin-pane').forEach(p => p.classList.remove('active'));
            document.querySelectorAll('.admin-tab-btn').forEach(b => b.classList.remove('active'));
            
            document.getElementById(targetPaneId).classList.add('active');
            clickedBtn.classList.add('active');
        }

        function populateAdminProductsTable() {
            const tbody = document.getElementById('admin-products-table-body');
            tbody.innerHTML = "";

            state.products.forEach((prod, index) => {
                const tr = document.createElement('tr');
                tr.innerHTML = `
                    <td style="display:flex; align-items:center; gap:8px;">
                        <img src="${prod.image}" style="width:30px; height:30px; object-fit:contain; border-radius:4px;">
                        <span style="font-weight:600; max-width:180px; overflow:hidden; text-overflow:ellipsis; white-space:nowrap;">${prod.name}</span>
                    </td>
                    <td>${prod.category}</td>
                    <td>₹${prod.offerPrice ? prod.offerPrice + ' <span style="text-decoration:line-through; font-size:8pt; color:var(--text-muted)">₹'+prod.price+'</span>' : prod.price}</td>
                    <td>
                        <span style="font-size:7.5pt; padding:2px 6px; border-radius:4px; background:${prod.inStock ? 'var(--accent-green)':'#ef4444'}; color:#fff;">${prod.inStock ? 'In-Stock':'Depleted'}</span>
                        ${prod.isFeatured ? '⭐':''}
                        ${prod.isBestseller ? '🔥':''}
                    </td>
                    <td>
                        <button class="qty-btn" style="display:inline-flex; padding:2px 6px;" onclick="shiftProductPriorityOrder(${index}, -1)">▲</button>
                        <button class="qty-btn" style="display:inline-flex; padding:2px 6px;" onclick="shiftProductPriorityOrder(${index}, 1)">▼</button>
                    </td>
                    <td>
                        <button style="color:var(--accent-primary); font-weight:700; margin-right:8px; cursor:pointer;" onclick="editProductAssetMatrix(${index})">Edit</button>
                        <button style="color:#ef4444; font-weight:700; cursor:pointer;" onclick="deleteProductAssetMatrix(${index})">Delete</button>
                    </td>
                `;
                tbody.appendChild(tr);
            });
        }

        function openProductForm() {
            document.getElementById('form-product-index').value = "";
            document.getElementById('form-product-title').innerText = "Append Core Showpiece Element Asset";
            document.getElementById('pform-name').value = "";
            document.getElementById('pform-price').value = "";
            document.getElementById('pform-offer-price').value = "";
            document.getElementById('pform-image').value = "";
            document.getElementById('pform-desc').value = "";
            document.getElementById('pform-featured').checked = false;
            document.getElementById('pform-bestseller').checked = false;
            document.getElementById('pform-instock').checked = true;
            
            document.getElementById('product-form-wrapper').style.display = 'block';
        }

        function editProductAssetMatrix(index) {
            const prod = state.products[index];
            document.getElementById('form-product-index').value = index;
            document.getElementById('form-product-title').innerText = `Modify System Configuration Asset [Index Vector: ${index}]`;
            
            document.getElementById('pform-name').value = prod.name;
            document.getElementById('pform-price').value = prod.price;
            document.getElementById('pform-offer-price').value = prod.offerPrice || "";
            document.getElementById('pform-category').value = prod.category;
            document.getElementById('pform-image').value = prod.image;
            document.getElementById('pform-desc').value = prod.desc || "";
            document.getElementById('pform-featured').checked = !!prod.isFeatured;
            document.getElementById('pform-bestseller').checked = !!prod.isBestseller;
            document.getElementById('pform-instock').checked = !!prod.inStock;

            document.getElementById('product-form-wrapper').style.display = 'block';
        }

        function saveProductForm() {
            const idxStr = document.getElementById('form-product-index').value;
            const name = document.getElementById('pform-name').value.trim();
            const price = parseFloat(document.getElementById('pform-price').value);
            const offerPriceRaw = document.getElementById('pform-offer-price').value;
            const category = document.getElementById('pform-category').value;
            const image = document.getElementById('pform-image').value.trim();
            const desc = document.getElementById('pform-desc').value.trim();
            const isFeatured = document.getElementById('pform-featured').checked;
            const isBestseller = document.getElementById('pform-bestseller').checked;
            const inStock = document.getElementById('pform-instock').checked;

            if(!name || !price || !image) {
                alert("Ensure parameters structural names, value weights, images and categories match basic validation schemas!");
                return;
            }

            const offerPrice = offerPriceRaw ? parseFloat(offerPriceRaw) : null;
            const payload = {
                id: idxStr !== "" ? state.products[parseInt(idxStr)].id : "p_gen_" + Date.now(),
                name, price, offerPrice, category, image, desc, isFeatured, isBestseller, inStock
            };

            if(idxStr !== "") {
                state.products[parseInt(idxStr)] = payload;
                spawnToastNotification("Target structural database asset parameters written.");
            } else {
                state.products.push(payload);
                spawnToastNotification("Fresh boutique item appended into global indexes database.");
            }

            localStorage.setItem('sa_products', JSON.stringify(state.products));
            document.getElementById('product-form-wrapper').style.display = 'none';
            populateAdminProductsTable();
            renderProductShowcase();
        }

        function deleteProductAssetMatrix(index) {
            if(confirm("Confirm permanent removal configuration track path for this boutique item entry?")) {
                state.products.splice(index, 1);
                localStorage.setItem('sa_products', JSON.stringify(state.products));
                populateAdminProductsTable();
                renderProductShowcase();
                spawnToastNotification("Boutique element entry destroyed safely from register.");
            }
        }

        function shiftProductPriorityOrder(index, direction) {
            const targetIdx = index + direction;
            if(targetIdx < 0 || targetIdx >= state.products.length) return;
            
            // Swap places smoothly inside matrix sequence track lines
            const temp = state.products[index];
            state.products[index] = state.products[targetIdx];
            state.products[targetIdx] = temp;
            
            localStorage.setItem('sa_products', JSON.stringify(state.products));
            populateAdminProductsTable();
            renderProductShowcase();
        }

        function populateAdminCategoriesList() {
            const container = document.getElementById('admin-categories-list-wrapper');
            container.innerHTML = "";

            state.categories.forEach((cat) => {
                if(cat === "All Matrix") return;
                const row = document.createElement('div');
                row.style.cssText = "display:flex; justify-content:space-between; padding:10px; background:rgba(0,0,0,0.1); margin-bottom:8px; border-radius:8px; align-items:center;";
                row.innerHTML = `
                    <span style="font-weight:600;">${cat}</span>
                    <button style="color:#ef4444; font-size:9pt; font-weight:700; cursor:pointer;" onclick="deleteCategorySystem('${cat}')">Delete Cluster</button>
                `;
                container.appendChild(row);
            });
        }

        function addCategorySystem() {
            const input = document.getElementById('new-cat-input');
            const val = input.value.trim();
            if(!val) return;
            if(state.categories.map(c=>c.toLowerCase()).includes(val.toLowerCase())) {
                alert("Cluster sequence label index name duplication constraint error.");
                return;
            }
            state.categories.push(val);
            localStorage.setItem('sa_categories', JSON.stringify(state.categories));
            input.value = "";
            populateAdminCategoriesList();
            hydrateAdminDashboard();
            renderCategoryTrack();
            spawnToastNotification(`Assigned '${val}' cluster array definition.`);
        }

        function deleteCategorySystem(catName) {
            if(confirm(`Confirm deletion of cluster set: [${catName}]? Affiliated items classification matrices remain untouched.`)) {
                state.categories = state.categories.filter(c => c !== catName);
                localStorage.setItem('sa_categories', JSON.stringify(state.categories));
                populateAdminCategoriesList();
                hydrateAdminDashboard();
                renderCategoryTrack();
                spawnToastNotification("Classification category mapping destroyed.");
            }
        }

        function saveStoreSettings() {
            state.settings.name = document.getElementById('sform-name').value.trim();
            state.settings.tagline = document.getElementById('sform-tagline').value.trim();
            state.settings.phone = document.getElementById('sform-phone').value.trim();
            state.settings.email = document.getElementById('sform-email').value.trim();
            state.settings.address = document.getElementById('sform-address').value.trim();
            state.settings.heroImage = document.getElementById('sform-hero').value.trim();

            localStorage.setItem('sa_settings', JSON.stringify(state.settings));
            syncGlobalDynamicText();
            spawnToastNotification("Global physical parameters re-calculated and stored.");
        }

        function switchThemeSystem(themeName) {
            state.settings.theme = themeName;
            localStorage.setItem('sa_settings', JSON.stringify(state.settings));
            applyThemeState(themeName);
            spawnToastNotification(`Refracted interface colors algorithm into: ${themeName}`);
        }

        function exportDataLedger() {
            const pack = {
                products: state.products,
                categories: state.categories,
                settings: state.settings
            };
            const dataStr = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(pack, null, 2));
            const dlAnchor = document.createElement('a');
            dlAnchor.setAttribute("href", dataStr);
            dlAnchor.setAttribute("download", `SMART_AQUA_MANIFEST_SNAPSHOT_${Date.now()}.json`);
            document.body.appendChild(dlAnchor);
            dlAnchor.click();
            dlAnchor.remove();
        }

        function importDataLedger(event) {
            const reader = new FileReader();
            reader.onload = function(e) {
                try {
                    const parsed = JSON.parse(e.target.result);
                    if(parsed.products && parsed.categories && parsed.settings) {
                        state.products = parsed.products;
                        state.categories = parsed.categories;
                        state.settings = parsed.settings;
                        
                        localStorage.setItem('sa_products', JSON.stringify(state.products));
                        localStorage.setItem('sa_categories', JSON.stringify(state.categories));
                        localStorage.setItem('sa_settings', JSON.stringify(state.settings));
                        
                        initializeDatabaseEngine();
                        hydrateAdminDashboard();
                        spawnToastNotification("Platform configuration snapshot schema loaded successfully.");
                    } else {
                        alert("Invalid JSON data schema structure missing necessary array mapping sets.");
                    }
                } catch(err) {
                    alert("Fatal validation parse sequence tracking error across uploaded asset file lines.");
                }
            };
            reader.readAsText(event.target.files[0]);
        }

        function purgeSystemClear() {
            if(confirm("CRITICAL WARNING: Absolute destructive nuclear wipe operation initialization. Roll back all properties state elements to default vendor layout maps?")) {
                localStorage.clear();
                window.location.reload();
            }
        }
    </script>
</body>
</html>
"""

# Save file locally inside the execution environment to offer down to client cleanly
with open("smart_aqua_cart_boutique.html", "w", encoding="utf-8") as f:
    f.write(html_content)

print("FILE GENERATED SUCCESSFULLY: smart_aqua_cart_boutique.html") Smartaquacart-html
