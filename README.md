# hyaqe<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>gourav(Tinku Bhai) | Construction Cards & CITB Test Booking Desk</title>
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>

    <header class="main-header">
        <div class="container header-flex">
            <div class="logo">
                <h1>gourav<span>(Tinku Bhai)</span></h1>
            </div>
            <nav class="nav-links">
                <a href="#services">Cards & Tests</a>
                <a href="#booking-form">Book Now</a>
                <a href="#faqs">FAQs</a>
                <a href="tel:+442033862000" class="btn-call"><i class="fa-solid fa-phone"></i> +44 (20) 3386 2000</a>
            </nav>
        </div>
    </header>

    <section class="hero-section">
        <div class="container hero-grid">
            <div class="hero-text">
                <span class="badge">10 Minute Fast Booking Service</span>
                <h2>Unlock Your Construction Career With CSCS Cards & CITB Tests</h2>
                <p>Get your CSCS Card in 7 Days, 1-Day Course Certificates within 24 Hours, and full premium revision material. Fast, trusted, and hassle-free processing.</p>
                <div class="hero-features">
                    <div class="feat-item"><i class="fa-solid fa-circle-check"></i> 75k+ Processed</div>
                    <div class="feat-item"><i class="fa-solid fa-circle-check"></i> 24/7 Support</div>
                    <div class="feat-item"><i class="fa-solid fa-circle-check"></i> Nationwide Venues</div>
                </div>
            </div>
            
            <div class="form-wrapper" id="booking-form">
                <h3>Secure Online Booking Desk</h3>
                <form action="#" method="POST" class="booking-form">
                    <div class="form-group">
                        <label>Select Required Service</label>
                        <select required>
                            <option value="">-- Choose Option --</option>
                            <option value="cscs">CITB Test & CSCS Card</option>
                            <option value="citb">CITB Touch Screen Test Only</option>
                            <option value="cpcs">CPCS / NPORS Courses</option>
                            <option value="nvq">NVQ Training Assessment</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Full Name</label>
                        <input type="text" placeholder="John Doe" required>
                    </div>
                    <div class="form-group">
                        <label>Phone Number</label>
                        <input type="tel" placeholder="+44 7123 456789" required>
                    </div>
                    <button type="submit" class="btn-submit">Apply Now <i class="fa-solid fa-arrow-right"></i></button>
                </form>
            </div>
        </div>
    </section>

    <section class="services-section" id="services">
        <div class="container">
            <div class="section-title">
                <h2>Choose Your Construction Booking Service</h2>
                <p>We provide instant test confirmations and seamless document compliance paths across the UK.</p>
            </div>
            <div class="services-grid">
                <div class="service-card">
                    <div class="card-icon"><i class="fa-solid fa-id-card"></i></div>
                    <h3>CSCS Cards</h3>
                    <p>Green Labourer, Gold Supervisor, Black Manager, and Red Trainee temporary or structural site pass procurement applications.</p>
                </div>
                <div class="service-card">
                    <div class="card-icon"><i class="fa-solid fa-laptop-code"></i></div>
                    <h3>CITB Test Booking</h3>
                    <p>Secure rapid scheduling at official local UK touch screen testing centers. Free dynamic text preparation material provided.</p>
                </div>
                <div class="service-card">
                    <div class="card-icon"><i class="fa-solid fa-helmet-safety"></i></div>
                    <h3>Health & Safety Courses</h3>
                    <p>Full classroom or structural remote online interactive courses including 1-day HSA, SMSTS, and critical SSSTS certification schemes.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="faq-section" id="faqs">
        <div class="container standard-width">
            <div class="section-title">
                <h2>Frequently Asked Questions</h2>
            </div>
            <div class="faq-accordion">
                <div class="faq-item">
                    <button class="faq-toggle">How can I book a CITB test in the UK? <i class="fa-solid fa-chevron-down"></i></button>
                    <div class="faq-content">
                        <p>You can quickly apply using our online application gateway above or contact our help desk via telephone line directly to lock down an immediate open date slot near you.</p>
                    </div>
                </div>
                <div class="faq-item">
                    <button class="faq-toggle">Which CITB test should I book? <i class="fa-solid fa-chevron-down"></i></button>
                    <div class="faq-content">
                        <p>General site workers and trades require the basic Operatives Test. If you hold a specialized supervisory or site managerial job status, you will require the specialized advanced tests.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer class="main-footer">
        <div class="container footer-flex">
            <p>&copy; 2026 <strong>gourav(Tinku Bhai)</strong>. All rights reserved.</p>
            <p>Support Email: <a href="mailto:support@constructionhelpdesks.com">support@constructionhelpdesks.com</a></p>
        </div>
    </footer>

    <script>
        const faqToggles = document.querySelectorAll('.faq-toggle');
        faqToggles.forEach(toggle => {
            toggle.addEventListener('click', () => {
                const item = toggle.parentElement;
                item.classList.toggle('active');
            });
        });
    </script>
</body>
</html>

/* GLOBAL CONFIGURATIONS */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

:root {
    --primary-color: #f25c05; /* Safety Construction Orange */
    --secondary-color: #1a2530; /* Dark Premium Navy Carbon */
    --light-bg: #f8f9fa;
    --text-dark: #333333;
    --white: #ffffff;
}

body {
    color: var(--text-dark);
    background-color: var(--white);
    line-height: 1.6;
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 0 auto;
}

.standard-width {
    max-width: 800px;
}

/* BRANDING NAVIGATION */
.main-header {
    background-color: var(--white);
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    position: sticky;
    top: 0;
    z-index: 1000;
    padding: 15px 0;
}

.header-flex {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo h1 {
    font-size: 1.5rem;
    color: var(--secondary-color);
    font-weight: 800;
    text-transform: uppercase;
}

.logo h1 span {
    color: var(--primary-color);
    font-size: 1.2rem;
    text-transform: none;
    margin-left: 5px;
}

.nav-links a {
    text-decoration: none;
    color: var(--secondary-color);
    margin-left: 20px;
    font-weight: 600;
    transition: color 0.3s;
}

.nav-links a:hover {
    color: var(--primary-color);
}

.nav-links .btn-call {
    background-color: var(--primary-color);
    color: var(--white);
    padding: 10px 20px;
    border-radius: 4px;
}

.nav-links .btn-call:hover {
    background-color: #d44b00;
    color: var(--white);
}

/* HERO CONVERSION BLOCK */
.hero-section {
    background: linear-gradient(rgba(26, 37, 48, 0.9), rgba(26, 37, 48, 0.95)), url('https://images.unsplash.com/photo-1541888946425-d81bb19240f5?q=80&w=1200') no-repeat center center/cover;
    padding: 80px 0;
    color: var(--white);
}

.hero-grid {
    display: grid;
    grid-template-columns: 1.2fr 0.8fr;
    gap: 40px;
    align-items: center;
}

.badge {
    background-color: var(--primary-color);
    padding: 5px 12px;
    border-radius: 20px;
    font-size: 0.85rem;
    font-weight: bold;
    display: inline-block;
    margin-bottom: 15px;
}

.hero-text h2 {
    font-size: 2.8rem;
    line-height: 1.2;
    margin-bottom: 20px;
}

.hero-text p {
    font-size: 1.1rem;
    margin-bottom: 30px;
    color: #cbd5e1;
}

.hero-features {
    display: flex;
    gap: 20px;
}

.feat-item i {
    color: var(--primary-color);
    margin-right: 5px;
}

/* CAPTURE HOOK FORM */
.form-wrapper {
    background: var(--white);
    padding: 30px;
    border-radius: 8px;
    color: var(--text-dark);
    box-shadow: 0 10px 25px rgba(0,0,0,0.2);
}

.form-wrapper h3 {
    margin-bottom: 20px;
    font-size: 1.4rem;
    color: var(--secondary-color);
    border-bottom: 2px solid var(--light-bg);
    padding-bottom: 10px;
}

.form-group {
    margin-bottom: 15px;
}

.form-group label {
    display: block;
    font-size: 0.9rem;
    font-weight: bold;
    margin-bottom: 5px;
}

.form-group input, .form-group select {
    width: 100%;
    padding: 12px;
    border: 1px solid #cccccc;
    border-radius: 4px;
    font-size: 1rem;
}

.btn-submit {
    width: 100%;
    background-color: var(--primary-color);
    color: var(--white);
    border: none;
    padding: 14px;
    font-size: 1.1rem;
    font-weight: bold;
    border-radius: 4px;
    cursor: pointer;
    transition: background 0.3s;
}

.btn-submit:hover {
    background-color: #d44b00;
}

/* MARKETING SERVICES SECTIONS */
.services-section {
    padding: 80px 0;
    background-color: var(--light-bg);
}

.section-title {
    text-align: center;
    margin-bottom: 50px;
}

.section-title h2 {
    font-size: 2.2rem;
    color: var(--secondary-color);
    margin-bottom: 10px;
}

.services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
}

.service-card {
    background: var(--white);
    padding: 40px 30px;
    border-radius: 6px;
    box-shadow: 0 5px 15px rgba(0,0,0,0.05);
    text-align: center;
    transition: transform 0.3s;
}

.service-card:hover {
    transform: translateY(-5px);
}

.card-icon {
    font-size: 2.5rem;
    color: var(--primary-color);
    margin-bottom: 20px;
}

.service-card h3 {
    margin-bottom: 15px;
    color: var(--secondary-color);
}

/* ACCORDION (FAQ) ENGINE */
.faq-section {
    padding: 80px 0;
}

.faq-accordion {
    margin-top: 30px;
}

.faq-item {
    border-bottom: 1px solid #e2e8f0;
    padding: 15px 0;
}

.faq-toggle {
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: none;
    border: none;
    font-size: 1.1rem;
    font-weight: 600;
    text-align: left;
    color: var(--secondary-color);
    cursor: pointer;
    padding: 10px 0;
}

.faq-content {
    max-height: 0;
    overflow: hidden;
    transition: max-height 0.3s ease-out;
}

.faq-content p {
    padding: 10px 0;
    color: #666666;
}

.faq-item.active .faq-content {
    max-height: 200px;
}

.faq-item.active .faq-toggle i {
    transform: rotate(180deg);
    color: var(--primary-color);
}

/* FOOTER ARCHITECTURE */
.main-footer {
    background-color: var(--secondary-color);
    color: #94a3b8;
    padding: 30px 0;
    font-size: 0.9rem;
    border-top: 4px solid var(--primary-color);
}

.footer-flex {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 15px;
}

.footer-flex a {
    color: var(--white);
    text-decoration: none;
}

/* MOBILE SYSTEM STYLES */
@media (max-width: 768px) {
    .hero-grid {
        grid-template-columns: 1fr;
    }
    .header-flex, .footer-flex {
        flex-direction: column;
        text-align: center;
        gap: 15px;
    }
    .nav-links a {
        display: block;
        margin: 10px 0;
    }
    .hero-text h2 {
        font-size: 2rem;
    }
}
