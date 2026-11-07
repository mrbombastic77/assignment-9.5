HTML
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DevScale — Final Responsive Landing Page</title>
    <meta name="description" content="A fully responsive, portfolio-ready modern landing page built using CSS Grid, Flexbox, media queries, and fluid typography.">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- Semantic Header & Navigation -->
    <header class="site-header">
        <div class="nav-container">
            <div class="logo">
                <a href="#">DevScale</a>
            </div>
            <nav class="nav-menu">
                <ul class="nav-links">
                    <li><a href="#hero" class="active">Home</a></li>
                    <li><a href="#features">Features</a></li>
                    <li><a href="#showcase">Showcase</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
            <div class="header-action">
                <a href="#contact" class="btn btn-primary">Get Started</a>
            </div>
        </div>
    </header>

    <!-- Main Content Area -->
    <main class="site-main">
        <!-- Hero Section -->
        <section id="hero" class="hero-section">
            <div class="hero-container">
                <div class="hero-text">
                    <span class="badge">Portfolio Ready</span>
                    <h1>Build Enterprise-Ready Web Applications</h1>
                    <p>Leverage modular design systems, advanced CSS layout engines, and semantic markup to deliver exceptional digital experiences across all devices.</p>
                    <div class="hero-buttons">
                        <a href="#features" class="btn btn-primary btn-lg">Explore Features</a>
                        <a href="https://github.com/AtimAkhtar" target="_blank" rel="noopener" class="btn btn-outline btn-lg">View GitHub</a>
                    </div>
                </div>
                <div class="hero-image-wrapper">
                    <img src="images/hero-illustration.jpg" alt="Developer illustration showcasing responsive web layout design" class="hero-img">
                </div>
            </div>
        </section>

        <!-- Feature Cards Section -->
        <section id="features" class="features-section">
            <div class="section-header">
                <h2>Core Platform Capabilities</h2>
                <p>Engineered for high performance, maintainability, and seamless scalability.</p>
            </div>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="card-icon">⚡</div>
                    <h3>CSS Grid Architecture</h3>
                    <p>Construct complex two-dimensional macro layouts with precise column tracks, auto-fit flows, and named grid areas.</p>
                </div>
                <div class="feature-card">
                    <div class="card-icon">🎯</div>
                    <h3>Flexbox Micro Alignment</h3>
                    <p>Manage flexible component alignments, navigation bars, and responsive wrapping with robust one-dimensional controls.</p>
                </div>
                <div class="feature-card">
                    <div class="card-icon">📱</div>
                    <h3>Mobile-First Scaling</h3>
                    <p>Ensure fluid adaptability across mobile devices, tablets, and ultra-wide desktop displays using progressive breakpoints.</p>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer Section -->
    <footer id="contact" class="site-footer">
        <div class="footer-container">
            <div class="footer-info">
                <h3>DevScale</h3>
                <p>Department of Computer Science Engineering, Invertis University, Bareilly</p>
            </div>
            <ul class="footer-links">
                <li><a href="#hero">Home</a></li>
                <li><a href="#features">Features</a></li>
                <li><a href="https://github.com/AtimAkhtar" target="_blank" rel="noopener">GitHub Repository</a></li>
            </ul>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2026 Atim Akhtar. All rights reserved.</p>
        </div>
    </footer>
</body>
</html>
CSS
/* style.css — Mobile-First Responsive Architecture */
:root {
    --primary-color: #0284c7;
    --primary-hover: #0369a1;
    --secondary-color: #0f172a;
    --bg-color: #f8fafc;
    --surface-color: #ffffff;
    --text-color: #334155;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
    
    /* Fluid Typography via clamp() */
    --font-size-hero: clamp(2rem, 5vw, 3rem);
    --font-size-h2: clamp(1.5rem, 3vw, 2.25rem);
    --font-size-body: clamp(0.95rem, 1.2vw, 1.125rem);

    --space-sm: 8px;
    --space-md: 16px;
    --space-lg: 24px;
    --space-xl: 40px;
    
    --radius-md: 8px;
    --radius-lg: 12px;
    --shadow-sm: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
    --shadow-md: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    line-height: 1.6;
    font-size: var(--font-size-body);
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    overflow-x: hidden;
}

/* Header & Navigation (Mobile First) */
.site-header {
    background-color: var(--secondary-color);
    color: var(--surface-color);
    padding: var(--space-md);
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.nav-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: var(--space-md);
}

.logo a {
    font-size: 1.25rem;
    font-weight: bold;
    color: var(--surface-color);
    text-decoration: none;
}

.nav-menu {
    display: none; /* Collapsed on small mobile viewports */
}

.nav-links {
    list-style: none;
    display: flex;
    gap: var(--space-lg);
}

.nav-links a {
    color: #94a3b8;
    text-decoration: none;
    font-weight: 500;
    font-size: 0.95rem;
    transition: color 0.2s ease;
}

.nav-links a:hover,
.nav-links a.active {
    color: #38bdf8;
}

.header-action {
    display: flex;
    align-items: center;
}

/* Main Content Area */
.site-main {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    gap: 3.5rem;
    padding: 2rem 0;
}

/* Hero Section (Mobile First) */
.hero-section {
    padding: 0 var(--space-md);
}

.hero-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 2.5rem;
    text-align: center;
}

.hero-text {
    max-width: 600px;
}

.badge {
    display: inline-block;
    background-color: #e0f2fe;
    color: var(--primary-color);
    font-size: 0.75rem;
    font-weight: bold;
    padding: 4px 12px;
    border-radius: 20px;
    text-transform: uppercase;
    margin-bottom: var(--space-md);
}

.hero-text h1 {
    font-size: var(--font-size-hero);
    color: var(--secondary-color);
    line-height: 1.2;
    margin-bottom: var(--space-md);
}

.hero-text p {
    color: var(--text-muted);
    margin-bottom: var(--space-lg);
}

.hero-buttons {
    display: flex;
    justify-content: center;
    gap: var(--space-md);
    flex-wrap: wrap;
}

.hero-image-wrapper {
    width: 100%;
    max-width: 520px;
    background-color: var(--border-color);
    border-radius: var(--radius-lg);
    overflow: hidden;
    box-shadow: var(--shadow-md);
}

.hero-img {
    width: 100%;
    height: auto;
    max-width: 100%;
    display: block;
    object-fit: cover;
}

/* Features Section (Mobile First CSS Grid) */
.features-section {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 var(--space-md);
    width: 100%;
}

.section-header {
    text-align: center;
    margin-bottom: 2.5rem;
}

.section-header h2 {
    font-size: var(--font-size-h2);
    color: var(--secondary-color);
    margin-bottom: 0.5rem;
}

.section-header p {
    color: var(--text-muted);
}

.features-grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--space-lg);
}

.feature-card {
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
    border-radius: var(--radius-lg);
    padding: 2rem var(--space-md);
    box-shadow: var(--shadow-sm);
    display: flex;
    flex-direction: column;
    gap: var(--space-md);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.feature-card:hover {
    transform: translateY(-3px);
    box-shadow: var(--shadow-md);
}

.card-icon {
    font-size: 2.25rem;
    background-color: #f1f5f9;
    width: 56px;
    height: 56px;
    border-radius: var(--radius-md);
    display: flex;
    justify-content: center;
    align-items: center;
}

.feature-card h3 {
    font-size: 1.15rem;
    color: var(--secondary-color);
}

.feature-card p {
    color: var(--text-muted);
}

/* Footer Section */
.site-footer {
    background-color: var(--secondary-color);
    color: var(--surface-color);
    padding: 2.5rem var(--space-md) 1.5rem var(--space-md);
    margin-top: auto;
    border-top: 1px solid var(--border-color);
}

.footer-container {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    gap: var(--space-lg);
    padding-bottom: 2rem;
    border-bottom: 1px solid #1e293b;
    text-align: center;
}

.footer-info h3 {
    font-size: 1.15rem;
    margin-bottom: 4px;
}

.footer-info p {
    color: var(--text-muted);
    font-size: 0.85rem;
}

.footer-links {
    list-style: none;
    display: flex;
    justify-content: center;
    gap: var(--space-lg);
    flex-wrap: wrap;
}

.footer-links a {
    color: var(--text-muted);
    text-decoration: none;
    font-size: 0.9rem;
    transition: color 0.2s ease;
}

.footer-links a:hover {
    color: var(--surface-color);
}

.footer-bottom {
    max-width: 1200px;
    margin: 1.5rem auto 0 auto;
    text-align: center;
    color: var(--text-muted);
    font-size: 0.85rem;
}

/* Buttons */
.btn {
    padding: 0.6rem 1.25rem;
    font-size: 0.95rem;
    font-weight: bold;
    border-radius: var(--radius-md);
    text-decoration: none;
    cursor: pointer;
    transition: background-color 0.2s ease;
    display: inline-block;
    text-align: center;
    border: none;
}

.btn-primary {
    background-color: var(--primary-color);
    color: var(--surface-color);
}

.btn-primary:hover {
    background-color: var(--primary-hover);
}

.btn-outline {
    background-color: transparent;
    border: 1px solid var(--border-color);
    color: var(--secondary-color);
}

.btn-outline:hover {
    background-color: #f1f5f9;
    border-color: var(--text-muted);
}

.btn-lg {
    padding: 0.75rem 1.5rem;
    font-size: 1rem;
}


/* ==========================================
   Media Query: Tablet View (min-width: 768px)
   ================================---------- */
@media (min-width: 768px) {
    .site-header {
        padding: var(--space-md) var(--space-xl);
    }

    .nav-menu {
        display: block;
    }

    .hero-section,
    .features-section {
        padding: 0 var(--space-xl);
    }

    .features-grid {
        grid-template-columns: repeat(2, 1fr);
        gap: var(--space-xl);
    }

    .feature-card {
        padding: 2.5rem 2rem;
    }

    .site-footer {
        padding: 3rem var(--space-xl) 1.5rem var(--space-xl);
    }

    .footer-container {
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        text-align: left;
    }

    .footer-links {
        justify-content: flex-end;
    }
}


/* ==========================================
   Media Query: Desktop View (min-width: 1024px)
   ================================---------- */
@media (min-width: 1024px) {
    .hero-container {
        flex-direction: row;
        justify-content: space-between;
        text-align: left;
    }

    .hero-text {
        text-align: left;
    }

    .hero-buttons {
        justify-content: flex-start;
    }

    .features-grid {
        grid-template-columns: repeat(3, 1fr);
    }
}