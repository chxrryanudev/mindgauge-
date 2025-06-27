<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MindGauge IQ - Professional Free IQ Test</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Montserrat:wght@700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #FF7A00;
            --primary-dark: #e06c00;
            --secondary: #004AAD;
            --light: #f8f9fa;
            --dark: #212529;
            --gray: #6c757d;
            --light-gray: #e9ecef;
            --success: #28a745;
            --danger: #dc3545;
            --border-radius: 12px;
            --box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            color: var(--dark);
            background-color: #ffffff;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header & Navigation */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo img {
            height: 40px;
        }

        .logo-text {
            font-family: 'Montserrat', sans-serif;
            font-weight: 800;
            font-size: 24px;
            color: var(--primary);
        }

        .logo-text span {
            color: var(--secondary);
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 500;
            transition: var(--transition);
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: var(--border-radius);
            font-weight: 500;
            cursor: pointer;
            transition: var(--transition);
        }

        .nav-btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            padding: 160px 0 100px;
            background: linear-gradient(135deg, rgba(255,122,0,0.1) 0%, rgba(0,74,173,0.1) 100%);
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: "";
            position: absolute;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: radial-gradient(circle, var(--primary) 0%, transparent 70%);
            top: -150px;
            right: -150px;
            opacity: 0.2;
        }

        .hero::after {
            content: "";
            position: absolute;
            width: 200px;
            height: 200px;
            border-radius: 50%;
            background: radial-gradient(circle, var(--secondary) 0%, transparent 70%);
            bottom: -100px;
            left: -100px;
            opacity: 0.2;
        }

        .hero-content {
            max-width: 600px;
            position: relative;
            z-index: 1;
        }

        .hero-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 3.5rem;
            line-height: 1.2;
            margin-bottom: 20px;
        }

        .hero-title span {
            color: var(--primary);
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 30px;
        }

        .hero-btn {
            background-color: var(--primary);
            color: white;
            font-size: 1.1rem;
            padding: 15px 30px;
            border: none;
            border-radius: var(--border-radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .hero-btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(255,122,0,0.3);
        }

        .hero-image {
            position: absolute;
            right: 0;
            top: 50%;
            transform: translateY(-50%);
            width: 45%;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            overflow: hidden;
        }

        .hero-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        /* Features Section */
        .section {
            padding: 100px 0;
        }

        .section-title {
            text-align: center;
            font-family: 'Montserrat', sans-serif;
            font-size: 2.5rem;
            margin-bottom: 15px;
        }

        .section-subtitle {
            text-align: center;
            color: var(--gray);
            max-width: 700px;
            margin: 0 auto 60px;
        }

        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--box-shadow);
            text-align: center;
            transition: var(--transition);
        }

        .feature-card:hover {
            transform: translateY(-10px);
        }

        .feature-icon {
            background-color: rgba(255,122,0,0.1);
            width: 80px;
            height: 80px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            color: var(--primary);
            font-size: 30px;
        }

        .feature-title {
            font-size: 1.3rem;
            margin-bottom: 15px;
        }

        /* Testimonials */
        .testimonials {
            background-color: var(--light);
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .testimonial-card {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 30px;
            box-shadow: var(--box-shadow);
            position: relative;
        }

        .testimonial-card::before {
            content: """;
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 60px;
            color: rgba(255,122,0,0.1);
            font-family: Georgia, serif;
            line-height: 1;
        }

        .testimonial-content {
            margin-bottom: 20px;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            overflow: hidden;
            background-color: var(--light-gray);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary);
            font-weight: bold;
        }

        .author-info h4 {
            margin-bottom: 5px;
        }

        .author-info p {
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* Quiz Section */
        .quiz-container {
            display: none;
            max-width: 800px;
            margin: 0 auto;
            padding: 30px;
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
        }

        .quiz-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
            align-items: center;
        }

        .question-count {
            font-weight: 600;
            color: var(--primary);
        }

        .timer {
            background-color: rgba(255,122,0,0.1);
            color: var(--primary);
            padding: 5px 15px;
            border-radius: 20px;
            font-weight: 600;
        }

        .difficulty {
            font-size: 0.9rem;
            padding: 3px 10px;
            border-radius: 5px;
            font-weight: 600;
        }

        .difficulty.easy {
            background-color: rgba(40, 167, 69, 0.1);
            color: var(--success);
        }

        .difficulty.medium {
            background-color: rgba(255, 193, 7, 0.1);
            color: #ffc107;
        }

        .difficulty.hard {
            background-color: rgba(220, 53, 69, 0.1);
            color: var(--danger);
        }

        .question {
            font-size: 1.3rem;
            margin-bottom: 25px;
            font-weight: 500;
        }

        .options {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        .option {
            padding: 15px;
            border: 2px solid var(--light-gray);
            border-radius: var(--border-radius);
            cursor: pointer;
            transition: var(--transition);
        }

        .option:hover {
            border-color: var(--primary);
            background-color: rgba(255,122,0,0.05);
        }

        .option.selected {
            border-color: var(--primary);
            background-color: rgba(255,122,0,0.1);
        }

        .quiz-footer {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
        }

        .quiz-btn {
            padding: 12px 25px;
            border: none;
            border-radius: var(--border-radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
        }

        .prev-btn {
            background-color: var(--light-gray);
        }

        .next-btn {
            background-color: var(--primary);
            color: white;
        }

        .next-btn:hover {
            background-color: var(--primary-dark);
        }

        /* Results Section */
        .results-container {
            display: none;
            max-width: 800px;
            margin: 0 auto;
            padding: 40px;
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            text-align: center;
        }

        .results-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .iq-score {
            font-size: 5rem;
            font-weight: 800;
            color: var(--primary);
            margin: 20px 0;
        }

        .badge {
            display: inline-block;
            padding: 10px 25px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 1.2rem;
            margin-bottom: 30px;
        }

        .badge-genius {
            background-color: rgba(255, 215, 0, 0.2);
            color: #ffd700;
        }

        .share-section {
            margin: 30px 0;
        }

        .share-title {
            margin-bottom: 15px;
            font-weight: 500;
        }

        .share-buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        .share-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            text-decoration: none;
            transition: var(--transition);
        }

        .share-btn:hover {
            transform: translateY(-5px);
        }

        .whatsapp {
            background-color: #25D366;
        }

        .instagram {
            background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888);
        }

        .twitter {
            background-color: #1DA1F2;
        }

        .action-buttons {
            margin-top: 30px;
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .action-btn {
            padding: 15px 30px;
            border-radius: var(--border-radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            border: none;
        }

        .retake-btn {
            background-color: var(--light-gray);
            color: var(--dark);
        }

        .certificate-btn {
            background-color: var(--primary);
            color: white;
        }

        .certificate-btn:hover {
            background-color: var(--primary-dark);
        }

        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-logo {
            font-family: 'Montserrat', sans-serif;
            font-size: 1.8rem;
            margin-bottom: 15px;
        }

        .footer-logo span {
            color: var(--primary);
        }

        .footer-links h3 {
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #adb5bd;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--primary);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255,255,255,0.1);
            color: #adb5bd;
        }

        /* Ad Placeholders */
        .ad-container {
            margin: 40px 0;
            background-color: var(--light-gray);
            border-radius: var(--border-radius);
            padding: 20px;
            text-align: center;
            color: var(--gray);
            font-size: 0.9rem;
        }

        /* Adsterra Popunder */
        .adsterra-popunder {
            display: none;
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: white;
            border: 1px solid #ddd;
            border-radius: 8px;
            padding: 10px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
            z-index: 9999;
            max-width: 300px;
        }
        
        .popunder-close {
            position: absolute;
            top: 5px;
            right: 10px;
            cursor: pointer;
            color: #999;
        }
        
        .popunder-content {
            padding: 10px;
        }

        /* Free Launch Banner */
        .free-launch-banner {
            background: linear-gradient(90deg, #FF7A00, #004AAD);
            color: white;
            text-align: center;
            padding: 15px;
            font-size: 0.9rem;
            position: relative;
        }
        
        .close-banner {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            cursor: pointer;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .hero {
                padding: 140px 0 80px;
            }
            .hero-title {
                font-size: 2.8rem;
            }
            .hero-image {
                position: relative;
                width: 100%;
                margin-top: 50px;
                transform: none;
            }
        }

        @media (max-width: 768px) {
            .navbar {
                flex-wrap: wrap;
            }
            .nav-links {
                order: 3;
                width: 100%;
                justify-content: center;
                margin-top: 20px;
            }
            .hero-title {
                font-size: 2.3rem;
            }
            .section {
                padding: 70px 0;
            }
            .section-title {
                font-size: 2rem;
            }
            .action-buttons {
                flex-direction: column;
            }
            .adsterra-popunder {
                max-width: 250px;
                right: 10px;
                bottom: 10px;
            }
        }

        @media (max-width: 576px) {
            .hero-title {
                font-size: 2rem;
            }
            .hero-subtitle {
                font-size: 1rem;
            }
            .hero-btn {
                width: 100%;
                justify-content: center;
            }
            .quiz-container, .results-container {
                padding: 20px;
            }
            .iq-score {
                font-size: 4rem;
            }
            .free-launch-banner {
                font-size: 0.8rem;
                padding: 10px 30px 10px 10px;
            }
        }
    </style>
</head>
<body>
    <!-- Free Launch Banner -->
    <div class="free-launch-banner">
        <strong>FREE IQ TEST!</strong> No registration required - Start now and discover your intelligence level!
        <span class="close-banner" onclick="this.parentElement.style.display='none'">✕</span>
    </div>

    <!-- Header & Navigation -->
    <header>
        <div class="container">
            <nav class="navbar">
                <div class="logo">
                    <div class="logo-text">Mind<span>Gauge</span> IQ</div>
                </div>
                <div class="nav-links">
                    <a href="#home">Home</a>
                    <a href="#features">Features</a>
                    <a href="#testimonials">Testimonials</a>
                    <a href="#about">About</a>
                    <a href="#contact">Contact</a>
                </div>
                <button class="nav-btn" id="startQuizBtn">Start IQ Test</button>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title">Measure Your Cognitive Abilities with <span>Precision</span></h1>
                <p class="hero-subtitle">Take our scientifically designed IQ test and discover your true intellectual potential. Get instant results with detailed analysis and a shareable certificate.</p>
                <button class="hero-btn" id="heroQuizBtn">
                    Start Free Test <i class="fas fa-arrow-right"></i>
                </button>
                <div class="ad-container" style="margin-top: 30px;">
                    <p>Advertisement Space for Google AdSense (728x90)</p>
                    <div style="width: 100%; height: 90px; background: linear-gradient(45deg, #f1f1f1, #e0e0e0); border-radius: 6px; display: flex; align-items: center; justify-content: center; color: #999; font-size: 0.9rem;">
                        AdSense Banner
                    </div>
                </div>
            </div>
            <div class="hero-image">
                <div style="background: linear-gradient(45deg, #FF7A00, #004AAD); height: 400px; border-radius: 12px; display: flex; align-items: center; justify-content: center; color: white; font-size: 1.5rem; text-align: center; padding: 20px;">
                    Professional IQ Test Visualization<br>
                    <small style="font-size: 1rem; opacity: 0.8;">Pattern Recognition • Logical Reasoning • Problem Solving</small>
                </div>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="section" id="
