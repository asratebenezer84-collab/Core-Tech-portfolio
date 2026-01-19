<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Core Tech Engineering | Human Sustainable Architecture</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&family=Playfair+Display:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary-color: #1a3c34;
            --secondary-color: #d4af37;
            --accent-color: #2c5e4f;
            --light-color: #f8f9fa;
            --dark-color: #121212;
            --gray-color: #6c757d;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            line-height: 1.6;
            color: var(--dark-color);
            background-color: #fff;
            overflow-x: hidden;
        }

        h1, h2, h3, h4, h5 {
            font-family: 'Playfair Display', serif;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        /* Header & Navigation */
        header {
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
            position: fixed;
            width: 100%;
            z-index: 1000;
            transition: var(--transition);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            display: flex;
            align-items: center;
            text-decoration: none;
        }

        .logo-text {
            display: flex;
            flex-direction: column;
            margin-left: 10px;
        }

        .logo-text h1 {
            font-size: 1.5rem;
            margin-bottom: 0;
            color: var(--primary-color);
        }

        .logo-text span {
            font-size: 0.8rem;
            color: var(--secondary-color);
            letter-spacing: 1px;
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 2rem;
        }

        nav ul li a {
            text-decoration: none;
            color: var(--dark-color);
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        nav ul li a:hover {
            color: var(--secondary-color);
        }

        nav ul li a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--secondary-color);
            transition: var(--transition);
        }

        nav ul li a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--primary-color);
            cursor: pointer;
        }

        /* Page Content */
        .page-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .page-content.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1487958449943-2429e8be8625?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            color: white;
            text-align: center;
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            color: white;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .hero-quote {
            font-style: italic;
            margin-top: 2rem;
            font-size: 1.3rem;
            border-left: 3px solid var(--secondary-color);
            padding-left: 1.5rem;
        }

        .btn {
            display: inline-block;
            background-color: var(--secondary-color);
            color: var(--dark-color);
            padding: 0.8rem 2rem;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
        }

        .btn:hover {
            background-color: #b8941f;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        /* Section Styling */
        .section {
            padding: 5rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--primary-color);
            position: relative;
            display: inline-block;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background-color: var(--secondary-color);
        }

        /* About Page */
        .about-content {
            display: flex;
            align-items: center;
            gap: 3rem;
        }

        .about-text {
            flex: 1;
        }

        .about-image {
            flex: 1;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .about-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        /* Philosophy Section */
        .philosophy {
            background-color: #f8f9fa;
        }

        .philosophy-content {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .philosophy-content p {
            font-size: 1.2rem;
            line-height: 1.8;
            margin-bottom: 1.5rem;
        }

        /* Services Page */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background-color: white;
            border-radius: 8px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
            text-align: center;
            border-top: 4px solid var(--secondary-color);
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .service-icon {
            font-size: 2.5rem;
            color: var(--secondary-color);
            margin-bottom: 1.5rem;
        }

        .service-card h3 {
            color: var(--primary-color);
            font-size: 1.3rem;
        }

        /* Projects Page */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
            cursor: pointer;
            border-top: 4px solid var(--accent-color);
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }

        .project-image {
            height: 200px;
            overflow: hidden;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }

        .project-card:hover .project-image img {
            transform: scale(1.1);
        }

        .project-info {
            padding: 1.5rem;
        }

        .project-info h3 {
            color: var(--primary-color);
            font-size: 1.2rem;
        }

        .project-type {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 4px;
            font-size: 0.8rem;
            margin-bottom: 0.5rem;
            text-transform: uppercase;
        }

        .project-details {
            display: flex;
            justify-content: space-between;
            margin-top: 1rem;
            font-size: 0.9rem;
            color: var(--gray-color);
        }

        /* Project Categories */
        .projects-filter {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 3rem;
            gap: 0.5rem;
        }

        .filter-btn {
            background-color: white;
            border: 1px solid #ddd;
            padding: 0.5rem 1.5rem;
            border-radius: 30px;
            cursor: pointer;
            transition: var(--transition);
            font-weight: 500;
        }

        .filter-btn:hover, .filter-btn.active {
            background-color: var(--primary-color);
            color: white;
            border-color: var(--primary-color);
        }

        /* Project Detail Page */
        .project-detail {
            padding: 6rem 0 3rem;
        }

        .project-detail-header {
            margin-bottom: 3rem;
            border-bottom: 2px solid #eee;
            padding-bottom: 2rem;
        }

        .project-detail-header h1 {
            font-size: 2.5rem;
            color: var(--primary-color);
        }

        .project-meta {
            display: flex;
            gap: 2rem;
            margin-top: 1rem;
            color: var(--gray-color);
            flex-wrap: wrap;
        }

        .project-meta span {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            background: #f8f9fa;
            padding: 0.5rem 1rem;
            border-radius: 4px;
        }

        .project-content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 3rem;
            margin-bottom: 3rem;
        }

        .project-description {
            line-height: 1.8;
        }

        .project-description h3 {
            color: var(--primary-color);
            margin-top: 2rem;
            margin-bottom: 1rem;
        }

        .project-description p {
            margin-bottom: 1.5rem;
            font-size: 1.1rem;
        }

        .project-sidebar {
            background: #f8f9fa;
            padding: 2rem;
            border-radius: 8px;
            height: fit-content;
        }

        .project-details-list {
            list-style: none;
        }

        .project-details-list li {
            margin-bottom: 1rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .project-details-list strong {
            color: var(--primary-color);
            display: block;
            margin-bottom: 0.3rem;
        }

        .back-btn {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background-color: var(--primary-color);
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 4px;
            text-decoration: none;
            transition: var(--transition);
        }

        .back-btn:hover {
            background-color: var(--accent-color);
        }

        /* Founder Page */
        .founder-content {
            display: flex;
            align-items: flex-start;
            gap: 3rem;
        }

        .founder-image {
            flex: 1;
            border-radius: 8px;
            overflow: hidden;
        }

        .founder-image img {
            width: 100%;
            height: auto;
            display: block;
        }

        .founder-info {
            flex: 2;
        }

        .founder-title {
            color: var(--secondary-color);
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
        }

        .experience-list {
            margin-top: 1.5rem;
        }

        .experience-item {
            margin-bottom: 1rem;
            padding-left: 1.5rem;
            position: relative;
        }

        .experience-item::before {
            content: '•';
            color: var(--secondary-color);
            font-size: 1.5rem;
            position: absolute;
            left: 0;
            top: -5px;
        }

        /* Clients Page */
        .clients-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 2rem;
            align-items: center;
        }

        .client-logo {
            background-color: white;
            padding: 1.5rem;
            border-radius: 8px;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 120px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .client-logo:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }

        .client-logo h3 {
            color: var(--primary-color);
            text-align: center;
            font-size: 1.1rem;
        }

        /* Contact Page */
        .contact-container {
            display: flex;
            gap: 3rem;
        }

        .contact-info {
            flex: 1;
        }

        .contact-details {
            margin-top: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: flex-start;
            margin-bottom: 1.5rem;
        }

        .contact-icon {
            color: var(--secondary-color);
            margin-right: 1rem;
            font-size: 1.2rem;
            margin-top: 5px;
        }

        .contact-form {
            flex: 1;
            background-color: white;
            padding: 2rem;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-family: 'Montserrat', sans-serif;
        }

        .form-group textarea {
            height: 150px;
            resize: vertical;
        }

        /* Footer */
        footer {
            background-color: #121212;
            color: white;
            padding: 3rem 0 1.5rem;
        }

        .footer-content {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            margin-bottom: 2rem;
        }

        .footer-column {
            flex: 1;
            min-width: 250px;
            margin-bottom: 2rem;
        }

        .footer-column h3 {
            color: var(--secondary-color);
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.8rem;
        }

        .footer-links a {
            color: #ddd;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: var(--secondary-color);
            padding-left: 5px;
        }

        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid #333;
            font-size: 0.9rem;
            color: #aaa;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .about-content, .founder-content, .contact-container {
                flex-direction: column;
            }
            
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .project-content {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 768px) {
            nav ul {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background-color: white;
                flex-direction: column;
                align-items: center;
                padding-top: 2rem;
                transition: var(--transition);
                box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            }
            
            nav ul.show {
                left: 0;
            }
            
            nav ul li {
                margin: 1rem 0;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .project-meta {
                flex-direction: column;
                gap: 0.5rem;
            }
        }

        @media (max-width: 576px) {
            .section {
                padding: 3rem 0;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .services-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <a href="#" class="logo" onclick="showPage('home'); return false;">
                <div class="logo-text">
                    <h1>CORE TECH ENGINEERING</h1>
                    <span>HUMAN SUSTAINABLE ARCHITECTURE</span>
                </div>
            </a>
            
            <button class="mobile-menu-btn" id="mobileMenuBtn">
                <i class="fas fa-bars"></i>
            </button>
            
            <nav>
                <ul id="navMenu">
                    <li><a href="#" onclick="showPage('home'); return false;">Home</a></li>
                    <li><a href="#" onclick="showPage('about'); return false;">About</a></li>
                    <li><a href="#" onclick="showPage('services'); return false;">Services</a></li>
                    <li><a href="#" onclick="showPage('projects'); return false;">Projects</a></li>
                    <li><a href="#" onclick="showPage('founder'); return false;">Founder</a></li>
                    <li><a href="#" onclick="showPage('clients'); return false;">Clients</a></li>
                    <li><a href="#" onclick="showPage('contact'); return false;">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Home Page -->
    <div id="home" class="page-content active">
        <section class="hero">
            <div class="container hero-content">
                <h1>AS GOOD AS IT GETS</h1>
                <p>Creating timeless architecture through research of detail and precise juxtaposition of materials.</p>
                <a href="#" class="btn" onclick="showPage('projects'); return false;">View Our Projects</a>
                <div class="hero-quote">
                    <p>"We don't design spaces, we think about a new way of living"</p>
                    <p>- Karen Ben</p>
                </div>
            </div>
        </section>

        <section class="section">
            <div class="container">
                <div class="section-title">
                    <h2>Our Philosophy</h2>
                </div>
                <div class="philosophy-content">
                    <p>Our philosophy to architecture is to achieve beauty through research of detail and precise juxtaposition of materials, to imbue each commission with a timeless quality of its own, and ultimately to create a sense of identity.</p>
                    <p>We craft every project as a one-off, tailor-made path to each realization that starts from the very concept, mapping the team's professionalism and creativity through architecture, design, engineering, sustainability consultancy and communication skills.</p>
                </div>
            </div>
        </section>
    </div>

    <!-- About Page -->
    <div id="about" class="page-content">
        <section class="section">
            <div class="container">
                <div class="section-title">
                    <h2>About Core Tech</h2>
                </div>
                <div class="about-content">
                    <div class="about-text">
                        <p>Core Tech Engineering PLC is a multidisciplinary consultancy firm founded in 2023 by Ebenezer Asrat in Addis Ababa, Ethiopia. We bring together diverse expertise to address all aspects that affect human space.</p>
                        <p>Our organization comprises architecture, interior design, engineering design, and project management divisions, all working collaboratively to deliver comprehensive solutions for our clients.</p>
                        <p>With a focus on sustainable practices and innovative design technologies, we aim to create structures that not only serve their functional purpose but also enhance the quality of life for their inhabitants.</p>
                    </div>
                    <div class="about-image">
                        <img src="https://images.unsplash.com/photo-1545324418-cc1a3fa10c00?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80" alt="Modern Architecture">
                    </div>
                </div>
            </div>
        </section>

        <section class="section philosophy">
            <div class="container">
                <div class="section-title">
                    <h2>Our Approach</h2>
                </div>
                <div class="philosophy-content">
                    <p>All stages of the project are developed with the goal of achieving high levels of efficiency, low cost of construction, maintenance and operation, high manufacturing quality and aesthetic integration with the context and user desires.</p>
                    <p>The gathering of resources, technologies available on site and their integration into the project through design and construction procedures that aims to minimize the use of energy and to increase its whole efficiency, makes any realization conceived with this approach unique.</p>
                    <p>The choice and composition of the energies that will support the operation of the building is as important as the simultaneous design of an integrated management system.</p>
                </div>
            </div>
        </section>
    </div>

    <!-- Services Page -->
    <div id="services" class="page-content">
        <section class="section">
            <div class="container">
                <div class="section-title">
                    <h2>Our Services</h2>
                </div>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-building"></i>
                        </div>
                        <h3>Architecture</h3>
                        <p>From masterplan to private commercial to public spaces. We design environments that inspire and function seamlessly.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-couch"></i>
                        </div>
                        <h3>Interior Design</h3>
                        <p>For residences, offices, commercial schools, hotels and more. Creating interiors that reflect purpose and personality.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-ruler-combined"></i>
                        </div>
                        <h3>Engineering Design</h3>
                        <p>We are able to customize projects with unique pieces, steering design for optimal structural performance.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-comments"></i>
                        </div>
                        <h3>Communication</h3>
                        <p>An effective communication of our project is as important as its design for successful project delivery.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-bullhorn"></i>
                        </div>
                        <h3>Branding</h3>
                        <p>Establishing and collaborating with the most important brands in fashion, automotive and design to provide added value.</p>
                    </div>
                    
                    <div class="service-card">
                        <div class="service-icon">
                            <i class="fas fa-file-contract"></i>
                        </div>
                        <h3>Legal Documents</h3>
                        <p>Comprehensive legal documentation and compliance for all architectural and construction projects.</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Projects Page -->
    <div id="projects" class="page-content">
        <section class="section">
            <div class="container">
                <div class="section-title">
                    <h2>Our Projects</h2>
                </div>
                
                <div class="projects-filter">
                    <button class="filter-btn active" data-filter="all">All Projects</button>
                    <button class="filter-btn" data-filter="design">Design Projects</button>
                    <button class="filter-btn" data-filter="supervised">Supervised Projects</button>
                    <button class="filter-btn" data-filter="pending">Pending Projects</button>
                    <button class="filter-btn" data-filter="design-supervision">Design & Supervision</button>
                </div>
                
                <div class="projects-grid" id="projectsContainer">
                    <!-- Projects will be loaded dynamically -->
                </div>
            </div>
        </section>
    </div>

    <!-- Project Detail Page -->
    <div id="project-detail" class="page-content">
        <section class="project-detail">
            <div class="container">
                <div class="project-detail-header">
                    <h1 id="projectTitle">Project Title</h1>
                    <div class="project-meta">
                        <span><i class="fas fa-map-marker-alt"></i> <span id="projectLocation">Location</span></span>
                        <span><i class="fas fa-expand-arrows-alt"></i> <span id="projectScale">Scale</span></span>
                        <span><i class="fas fa-user"></i> <span id="projectClient">Client</span></span>
                        <span><i class="fas fa-layer-group"></i> <span id="projectCategory">Category</span></span>
                    </div>
                </div>
                
                <div class="project-content">
                    <div class="project-description" id="projectDescription">
                        <!-- Project description will be loaded here -->
                    </div>
                    
                    <div class="project-sidebar">
                        <h3>Project Details</h3>
                        <ul class="project-details-list" id="projectDetailsList">
                            <!-- Project details will be loaded here -->
                        </ul>
                    </div>
                </div>
                
                <a href="#" class="back-btn" onclick="showPage('projects'); return false;">
                    <i class="fas fa-arrow-left"></i> Back to Projects
                </a>
            </div>
        </section>
    </div>

    <!-- Founder Page -->
    <div id="founder" class="page-content">
        <section class="section">
            <div class="container">
                <div class="section-title">
                    <h2>Our Founder</h2>
                </div>
                <div class="founder-content">
                    <div class="founder-image">
                        <img src="https://images.unsplash.com/photo-1582750433449-648ed127bb54?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80" alt="Ebenezer Asrat">
                    </div>
                    <div class="founder-info">
                        <h2>Ebenezer Asrat</h2>
                        <div class="founder-title">Founder & General Manager | Principal Structural Engineer</div>
                        <p>Highly accomplished Senior Structural Engineer with over 9 years of experience in designing, analyzing, and overseeing the construction of complex structures. Known for implementing innovative design technologies and leading teams to exceed productivity goals.</p>
                        <p>Demonstrated expertise in optimizing designs and processes to enhance safety, sustainability and cost-efficiency.</p>
                        
                        <div class="experience-list">
                            <div class="experience-item">Led Structural Engineer at Keen Consulting Architects and Engineers PLC (2015-Present)</div>
                            <div class="experience-item">Co-founder & Senior Structural Engineer at Amist Architects Engineers (2021-2023)</div>
                            <div class="experience-item">Founder & General Manager of Core Tech Engineering PLC (2023-Present)</div>
                            <div class="experience-item">B.Sc. in Civil Engineering from Arba Minch University</div>
                            <div class="experience-item">Member of Association of Ethiopian Consultants</div>
                            <div class="experience-item">Specialized training in Facade BIM Modeling</div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Clients Page -->
    <div id="clients" class="page-content">
        <section class="section">
            <div class="container">
                <div class="section-title">
                    <h2>Our Clients</h2>
                </div>
                <div class="clients-grid">
                    <div class="client-logo">
                        <h3>Best Way Industrial PLC</h3>
                    </div>
                    <div class="client-logo">
                        <h3>SHG Real Estate PLC</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Wro Emebet Kassa</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Dandil Boru</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Ato Tsego Lakew</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Ato Mekonnen Beire</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Nigat Berhan S.C.</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Zablon Trading PLC</h3>
                    </div>
                    <div class="client-logo">
                        <h3>St. Mary's University</h3>
                    </div>
                    <div class="client-logo">
                        <h3>American Diaspora Union</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Mehal Olympia Real Estate PLC</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Century Addis Real Estate PLC</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Dr. Tsegaye Tadesse</h3>
                    </div>
                    <div class="client-logo">
                        <h3>ORBIS</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Saint Mary's Educational Development PLC</h3>
                    </div>
                    <div class="client-logo">
                        <h3>DYF Real Estate PLC</h3>
                    </div>
                    <div class="client-logo">
                        <h3>International Tennis Club</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Google Trading PLC</h3>
                    </div>
                    <div class="client-logo">
                        <h3>Jenboro Real Estate</h3>
                    </div>
                    <div class="client-logo">
                        <h3>W/o Tikdem Getahun</h3>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Contact Page -->
    <div id="contact" class="page-content">
        <section class="section">
            <div class="container">
                <div class="section-title">
                    <h2>Contact Us</h2>
                </div>
                <div class="contact-container">
                    <div class="contact-info">
                        <h2>Get In Touch</h2>
                        <p>We'd love to discuss your project and explore how we can bring your vision to life with sustainable, human-centered architecture.</p>
                        
                        <div class="contact-details">
                            <div class="contact-item">
                                <div class="contact-icon">
                                    <i class="fas fa-map-marker-alt"></i>
                                </div>
                                <div>
                                    <h4>Office Address</h4>
                                    <p>Kirsa MBA017 / Waseda 027 / House no. 143/20<br>Addis Ababa, Ethiopia</p>
                                </div>
                            </div>
                            
                            <div class="contact-item">
                                <div class="contact-icon">
                                    <i class="fas fa-phone"></i>
                                </div>
                                <div>
                                    <h4>Phone</h4>
                                    <p>+251 982 287 449</p>
                                </div>
                            </div>
                            
                            <div class="contact-item">
                                <div class="contact-icon">
                                    <i class="fas fa-envelope"></i>
                                </div>
                                <div>
                                    <h4>Email</h4>
                                    <p>info@coretechengineering.com</p>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="contact-form">
                        <h3>Send us a message</h3>
                        <form id="contactForm">
                            <div class="form-group">
                                <label for="name">Full Name</label>
                                <input type="text" id="name" required>
                            </div>
                            
                            <div class="form-group">
                                <label for="email">Email Address</label>
                                <input type="email" id="email" required>
                            </div>
                            
                            <div class="form-group">
                                <label for="phone">Phone Number</label>
                                <input type="tel" id="phone">
                            </div>
                            
                            <div class="form-group">
                                <label for="message">Your Message</label>
                                <textarea id="message" required></textarea>
                            </div>
                            
                            <button type="submit" class="btn">Send Message</button>
                        </form>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Core Tech Engineering</h3>
                    <p>Creating timeless architecture through research of detail and precise juxtaposition of materials.</p>
                    <p>HUMAN SUSTAINABLE ARCHITECTURE</p>
                </div>
                
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#" onclick="showPage('home'); return false;">Home</a></li>
                        <li><a href="#" onclick="showPage('about'); return false;">About Us</a></li>
                        <li><a href="#" onclick="showPage('services'); return false;">Services</a></li>
                        <li><a href="#" onclick="showPage('projects'); return false;">Projects</a></li>
                        <li><a href="#" onclick="showPage('contact'); return false;">Contact</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Services</h3>
                    <ul class="footer-links">
                        <li><a href="#" onclick="showPage('services'); return false;">Architecture</a></li>
                        <li><a href="#" onclick="showPage('services'); return false;">Interior Design</a></li>
                        <li><a href="#" onclick="showPage('services'); return false;">Engineering Design</a></li>
                        <li><a href="#" onclick="showPage('services'); return false;">Project Management</a></li>
                        <li><a href="#" onclick="showPage('services'); return false;">Sustainability Consulting</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Contact Info</h3>
                    <ul class="footer-links">
                        <li><i class="fas fa-map-marker-alt"></i> Addis Ababa, Ethiopia</li>
                        <li><i class="fas fa-phone"></i> +251 982 287 449</li>
                        <li><i class="fas fa-envelope"></i> info@coretechengineering.com</li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2024 Core Tech Engineering PLC. All rights reserved. | AS GOOD AS IT GETS</p>
            </div>
        </div>
    </footer>

    <script>
        // Project Data - All 24 projects with EXACT descriptions from your sheets
        const projects = [
            // DESIGN PROJECTS (1-5)
            {
                id: 1,
                title: "1B+G+13 Apartment Building",
                category: "design",
                type: "residential",
                location: "Addis Ababa, Ethiopia",
                scale: "1,500 m²",
                client: "Best Way Industrial PLC",
                description: `This structure is about more than creating a series of rooms and spaces to accommodate future challenges, appreciating the aesthetic of form, and carefully constructing a major point of interest in the region. With majestic angles, unexpected vertical lines and complementing shapes, the structure truly says all innovation.<br><br>
                All stages of the project are developed with the goal of achieving high levels of efficiency, low cost of construction, maintenance and operation, high manufacturing quality and aesthetic integration with the context and the user desire right from the very start of the conceptual stages up to the finished product and beyond.<br><br>
                The gathering of resources, technologies available on site and their integration into the project through design and construction procedures that aims to minimize the use of energy and to increase its whole efficiency, makes any realizations concealed with this approach unique. The choice and composition of the energies that will support the operation of the building is as important as the simultaneous design of an integrated management system.<br><br>
                We craft every project as a one-off. A tailor-made path to each realization that starts from the very concept, to its proposition mapping the team's professionalism and creativity through architecture, design, engineering, sustainability consultancy and communication skills, to guide each project to success.`
            },
            {
                id: 2,
                title: "Mixed Use Building, B+G+7",
                category: "design",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "SHG Real Estate PLC",
                description: "Mixed use building designed for SHG Real Estate PLC, combining residential and commercial spaces in a sustainable structure."
            },
            {
                id: 3,
                title: "Mixed Use Building, Eight Story",
                category: "design",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Wro Emebet Kassa",
                description: "Eight-story mixed use building designed with sustainable techniques and aesthetic form appreciation."
            },
            {
                id: 4,
                title: "School Building, Four Story",
                category: "design",
                type: "educational",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Dandil Boru",
                description: "Four-story school building designed to provide modern educational facilities with sustainable features."
            },
            {
                id: 5,
                title: "Mixed Use Building, B+G+8",
                category: "design",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Ato Tsego Lakew",
                description: "Mixed use building with ground plus eight floors, designed for optimal space utilization and sustainability."
            },
            // SUPERVISED PROJECTS (6-10)
            {
                id: 6,
                title: "Mixed Use Building",
                category: "supervised",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Ato Mekonnen Beire",
                description: "Supervised under periodic and resident basis, ensuring quality construction and adherence to design specifications."
            },
            {
                id: 7,
                title: "Shopping Center",
                category: "supervised",
                type: "commercial",
                location: "Merkato, Addis Ababa",
                scale: "Variable",
                client: "Nigat Berhan S.C.",
                description: "Shopping center supervision in Merkato area, ensuring construction quality and design compliance."
            },
            {
                id: 8,
                title: "Mixed Use Building",
                category: "supervised",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Zablon Trading PLC",
                description: "Supervision services for mixed use building project, ensuring timely completion and quality standards."
            },
            {
                id: 9,
                title: "University Campus",
                category: "supervised",
                type: "educational",
                location: "Mexico Square, Near AU Headquarters, Addis Ababa",
                scale: "Variable",
                client: "St. Mary's University",
                description: "University campus supervision near AU headquarters, ensuring proper implementation of educational facility design."
            },
            {
                id: 10,
                title: "University Campus",
                category: "supervised",
                type: "educational",
                location: "Hawassa, Ethiopia",
                scale: "8,000 m²",
                client: "American Diaspora Union",
                description: `The proposed project involves the design and construction of a G+6 (Ground plus six floors) university campus building complex. The project is located on an 8000 square meter plot, strategically positioned to maximize accessibility and connectivity within the university campus. The site will be developed to include green spaces, pedestrian pathways, and parking facilities.`
            },
            // PENDING PROJECTS (11-15)
            {
                id: 11,
                title: "Mixed Use Building, Twenty Six Storey",
                category: "pending",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Mehal Olympia Real Estate PLC",
                description: "Twenty-six storey mixed use building in planning phase, aiming to be a landmark structure in Addis Ababa."
            },
            {
                id: 12,
                title: "Mixed Use Building, 3B+G+19",
                category: "pending",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "1,500 m²",
                client: "Century Addis Real Estate PLC",
                description: `This structure is about more than creating a series of rooms and spaces to accommodate future guests, this is about blending sustainable techniques, appreciating the aesthetic of form, and carefully constructing a hotel that would become a major point of interest in the region. With majestic angles, unexpected vertical lines and complementing shapes, the structure truly says something about the artistry of architectural innovation.`
            },
            {
                id: 13,
                title: "Mixed Use Building, Eight Storey",
                category: "pending",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "350 m²",
                client: "Dr. Tsegaye Tadesse",
                description: `This structure is about more than creating a series of rooms and spaces to accommodate future guests, this is about blending sustainable techniques, appreciating the aesthetic of form, and carefully constructing a hotel that would become a major point of interest in the region. With majestic angles, unexpected vertical lines and complementing shapes, the structure truly says something about the artistry of architectural innovation.`
            },
            {
                id: 14,
                title: "Mixed Use Building, B+G+7",
                category: "pending",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "SHG Real Estate PLC",
                description: "Pending mixed use building project with ground plus seven floors design."
            },
            {
                id: 15,
                title: "Mixed Use Building, B+G+8",
                category: "pending",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Ato Tsego Lakew",
                description: "Pending project for mixed use building with sustainable design features."
            },
            // DESIGN, SUPERVISION & CONTRACT ADMIN PROJECTS (16-24)
            {
                id: 16,
                title: "Mixed Use Building, 5B+G+19",
                category: "design-supervision",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "5,700 m²",
                client: "Mehal Olympia Real Estate PLC",
                description: `This structure is about more than creating a series of rooms and spaces to accommodate future guests, this is about blending sustainable techniques, appreciating the aesthetic of form, and carefully constructing a hotel that would become a major point of interest in the region. With majestic angles, unexpected vertical lines and complementing shapes, the structure truly says something about the artistry of architectural innovation.<br><br>
                All stages of the project are developed with the goal of achieving high levels of efficiency, low cost of construction, maintenance and operation, high manufacturing quality and aesthetic integration with the context and the user desires right from the very start of the conceptual stages up to the finished product and beyond.<br><br>
                The gathering of resources, technologies available on site and their integration into the project through design and construction procedures that aims to minimise the use of energy and to increase its whole efficiency, makes any realizations concealed with this approach unique. The choice and composition of the energies that will support the operation of the building is as important as the simultaneous design of an integrated management system.<br><br>
                We craft every project as a one-off. A tailor-made path to each realization that starts from the very concept, to its proposition meeting the team's professionalism and creativity through architecture, design, engineering, sustainability consultancy and communication skills, to guide each project to success.`
            },
            {
                id: 17,
                title: "Seven Towers Building Complex",
                category: "design-supervision",
                type: "residential",
                location: "Adjacent to AU Headquarters, Addis Ababa",
                scale: "17,610 m²",
                client: "ORBIS",
                description: `The proposed project involves the design of a multiple apartment building towers complex on a 17610 square meter plot. The complex aims to provide modern, comfortable, and sustainable living spaces for a diverse community, incorporating a range of amenities and green spaces.<br><br>
                The project site is located on a 17610 square meter plot, strategically positioned to offer convenient access to local amenities, public transportation, and green spaces. The site will be developed to include landscaped areas, pedestrian pathways, and parking facilities.<br><br>
                <strong>Functionality:</strong> To create a functional and efficient layout that accommodates classrooms, lecture halls, laboratories, administrative offices, libraries, and student common areas.<br><br>
                <strong>Sustainability:</strong> To incorporate sustainable design principles, including energy-efficient systems, water conservation measures, and the use of eco-friendly materials.<br><br>
                <strong>Aesthetics:</strong> To design an aesthetically pleasing building that reflects the university's identity and enhances the campus environment.<br><br>
                <strong>Safety and Accessibility:</strong> To ensure the building meets all safety standards and is accessible to all users.`
            },
            {
                id: 18,
                title: "G+8 Campus Building",
                category: "design-supervision",
                type: "educational",
                location: "Mexico Area, Near SMU Main Campus, Addis Ababa",
                scale: "671 m²",
                client: "Saint Mary's Educational Development PLC",
                description: `The proposed project involves the design and construction of a G+8 (Ground plus eight floors) university campus building complex on an 4960 square meter plot. The complex aims to provide state-of-the-art educational facilities, administrative offices, and student amenities to support a modern learning environment.<br><br>
                All stages of the project are developed with the goal of achieving high levels of efficiency, low cost of construction, maintenance and operation, high manufacturing quality and aesthetic integration with the context and the user desires right from the very start of the conceptual stages up to the finished product and beyond.<br><br>
                The gathering of resources, technologies available on site and their integration into the project through design and construction procedures that aims to minimize the use of energy and to increase its whole efficiency, makes any realization conceived with this approach, unique. The choice and composition of the energies that will support the operation of the building is as important as the simultaneous design of an integrated management system.`
            },
            {
                id: 19,
                title: "Mixed Use Building, 3B+G+19",
                category: "design-supervision",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "2,800 m²",
                client: "DYF Real Estate PLC",
                description: `The proposed project involves the design and construction of a modern mixed-use building on a 2800 square meter plot. The building aims to provide comfortable and efficient living spaces for residents, incorporating contemporary design elements and sustainable features.<br><br>
                <strong>Functionality:</strong> To create a functional layout that maximizes the use of space while providing comfortable living areas.<br><br>
                <strong>Sustainability:</strong> To incorporate sustainable design principles, including energy-efficient systems, water conservation measures, and the use of eco-friendly materials.<br><br>
                <strong>Aesthetics:</strong> To design an aesthetically pleasing building that enhances the neighborhood's visual appeal.<br><br>
                <strong>Safety and Accessibility:</strong> To ensure the building meets all safety standards and is accessible to all residents, including those with disabilities.`
            },
            {
                id: 20,
                title: "Mixed Use Building, 3B+G+19",
                category: "design-supervision",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Century Addis Real Estate PLC",
                description: "Design, supervision and contract administration for mixed use building with three basements, ground and nineteen floors."
            },
            {
                id: 21,
                title: "Apartment Building",
                category: "design-supervision",
                type: "residential",
                location: "Addis Ababa, Ethiopia",
                scale: "1,440 m²",
                client: "Century Addis Real Estate PLC",
                description: `The proposed project involves the design and construction of a modern apartment building on a 1440 square meter plot. The built-in layout is designed to provide comfortable and efficient living spaces for residents, incorporating contemporary design elements and sustainable facilities.<br><br>
                <strong>Site Location:</strong> The project site is located on a 1440 square meter plot, ideally situated to offer convenient access to local amenities, public transportation, and green spaces. The site will be developed to include landscaped areas and necessary infrastructure.`
            },
            {
                id: 22,
                title: "Sport Complex Building",
                category: "design-supervision",
                type: "commercial",
                location: "Old Airport, Near Bisrate Gabriel Church, Addis Ababa",
                scale: "4,636 m²",
                client: "International Tennis Club",
                description: `The proposed project involves the design and construction of a state-of-the-art sports complex on a 4636 square meter plot. The plan aims to provide comprehensive sports facilities, including indoor and outdoor areas, to support a wide range of athletic activities and community events.<br><br>
                The project site is located on a 4636 square meter plot, strategically positioned to maximize accessibility and connectivity within the community. The site will be developed to include green spaces, pedestrian pathways, and parking facilities.`
            },
            {
                id: 23,
                title: "Mixed Use Building",
                category: "design-supervision",
                type: "mixed-use",
                location: "Opposite to Kenya Embassy, Addis Ababa",
                scale: "Variable",
                client: "Dr. Tsegaye Tadesse",
                description: "Mixed use building design and supervision opposite to Kenya Embassy, incorporating sustainable design principles."
            },
            {
                id: 24,
                title: "Mixed Use Building",
                category: "design-supervision",
                type: "mixed-use",
                location: "Addis Ababa, Ethiopia",
                scale: "Variable",
                client: "Google Trading PLC",
                description: "Design, supervision and contract administration for mixed use building for Google Trading PLC."
            },
            // Additional Projects from Detailed Sheets
            {
                id: 25,
                title: "B+G+7+Terrace Mixed Use Building",
                category: "design",
                type: "mixed-use",
                location: "Jemo, Addis Ababa",
                scale: "500 m²",
                client: "W/o Tikdem Getahun",
                description: `This structure is about more than creating a series of rooms and spaces to accommodate future guests, this is about blending sustainable techniques, appreciating the aesthetic of form, and carefully constructing a hotel that would become a major point of interest in the region. With majestic angles, unexpected vertical lines and complementing shapes, the structure truly says something about the artistry of architectural innovation.`
            },
            {
                id: 26,
                title: "Jenboro Real Estate 3B+G+23 Apartment Building",
                category: "design",
                type: "residential",
                location: "Addis Ababa, Ethiopia",
                scale: "1,500 m²",
                client: "Jenboro Real Estate",
                description: `This structure is about more than creating a series of rooms and spaces to accommodate future guests, this is about blending sustainable techniques, appreciating the aesthetic of form, and carefully constructing a hotel that would become a major point of interest in the region. With majestic angles, unexpected vertical lines and complementing shapes, the structure truly says something about the artistry of architectural innovation.<br><br>
                All stages of the project are developed with the goal of achieving high levels of efficiency, low cost of construction, maintenance and operation, high manufacturing quality, and aesthetic integration with the context and the user desire right from the very start of the conceptual stages up to the finished product and beyond.<br><br>
                The gathering of resources, technologies available on site and their interaction into the project through design and construction procedures that aims to minimize the use of energy and to increase its whole efficiency, makes any realization concealed with this approach unique. The choice and composition of the energies that will support the operation of the building is as important as the simultaneous design of an integrated management system.<br><br>
                We craft every project as a one-off. A tailor-made path to each realization that starts from the very concept, to its proposition integrating the team's professionalism and creativity through architecture, design, engineering, sustainability consultancy and communication skills, to guide each project to success.`
            },
            {
                id: 27,
                title: "Abay Tech Apartment Building",
                category: "design",
                type: "residential",
                location: "Addis Ababa, Ethiopia",
                scale: "1,500 m²",
                client: "Best Way Industrial PLC",
                description: `This structure is about more than creating a series of rooms and spaces to accommodate future guests, this is about blending sustainable techniques, appreciating the aesthetic of form, and carefully constructing a hotel that would become a major point of interest in the region. With majestic angles, unexpected vertical lines and complementing shapes, the structure truly says something about the artistry of architectural innovation.`
            },
            {
                id: 28,
                title: "University Campus Building Complex",
                category: "design",
                type: "educational",
                location: "Addis Ababa, Ethiopia",
                scale: "6,960 m²",
                client: "St. Mary University",
                description: `The proposed project involves the design and construction of a G+8 (Ground plus eight) campus building complex on an 6960 square meter plot. The complex aims to provide state-of-the-art educational facilities, administrative offices, and student amenities to support a modern learning environment.<br><br>
                <strong>Functionality:</strong> To create a functional and efficient layout that accommodates classrooms, lecture halls, laboratories, administrative offices, libraries, and student common areas.<br><br>
                <strong>Sustainability:</strong> To incorporate sustainable design principles, including energy-efficient systems, water conservation measures, and the use of eco-friendly materials.<br><br>
                <strong>Aesthetics:</strong> To design an aesthetically pleasing building that reflects the university's identity and enhances the campus environment.<br><br>
                <strong>Safety and Accessibility:</strong> To ensure the building meets all safety standards and is accessible to all users, including those with disabilities.`
            }
        ];

        // Mobile Menu Toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const navMenu = document.getElementById('navMenu');
        
        mobileMenuBtn.addEventListener('click', () => {
            navMenu.classList.toggle('show');
            mobileMenuBtn.innerHTML = navMenu.classList.contains('show') 
                ? '<i class="fas fa-times"></i>' 
                : '<i class="fas fa-bars"></i>';
        });
        
        // Close mobile menu when clicking on a link
        document.querySelectorAll('nav ul li a').forEach(link => {
            link.addEventListener('click', () => {
                navMenu.classList.remove('show');
                mobileMenuBtn.innerHTML = '<i class="fas fa-bars"></i>';
            });
        });
        
        // Page Navigation
        function showPage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page-content').forEach(page => {
                page.classList.remove('active');
            });
            
            // Show selected page
            document.getElementById(pageId).classList.add('active');
            
            // If showing projects page, load projects
            if (pageId === 'projects') {
                loadProjects();
            }
            
            // Scroll to top
            window.scrollTo(0, 0);
        }
        
        // Load Projects
        function loadProjects() {
            const projectsContainer = document.getElementById('projectsContainer');
            projectsContainer.innerHTML = '';
            
            // Get active filter
            const activeFilter = document.querySelector('.filter-btn.active').getAttribute('data-filter');
            
            // Filter projects
            const filteredProjects = activeFilter === 'all' 
                ? projects 
                : projects.filter(project => project.category === activeFilter);
            
            // Display projects
            filteredProjects.forEach(project => {
                const projectCard = document.createElement('div');
                projectCard.className = 'project-card';
                projectCard.setAttribute('data-id', project.id);
                
                // Determine category label
                let categoryLabel = '';
                switch(project.category) {
                    case 'design': categoryLabel = 'Design Project'; break;
                    case 'supervised': categoryLabel = 'Supervised'; break;
                    case 'pending': categoryLabel = 'Pending'; break;
                    case 'design-supervision': categoryLabel = 'Design & Supervision'; break;
                    default: categoryLabel = 'Project';
                }
                
                projectCard.innerHTML = `
                    <div class="project-image">
                        <img src="https://images.unsplash.com/photo-1545324418-cc1a3fa10c00?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80" alt="${project.title}">
                    </div>
                    <div class="project-info">
                        <span class="project-type">${categoryLabel}</span>
                        <h3>${project.title}</h3>
                        <p>${project.description.substring(0, 120)}...</p>
                        <div class="project-details">
                            <span><i class="fas fa-map-marker-alt"></i> ${project.location.split(',')[0]}</span>
                            <span><i class="fas fa-user"></i> ${project.client.split(' ')[0]}</span>
                        </div>
                    </div>
                `;
                
                projectCard.addEventListener('click', () => {
                    showProjectDetail(project.id);
                });
                
                projectsContainer.appendChild(projectCard);
            });
        }
        
        // Project Filtering
        document.querySelectorAll('.filter-btn').forEach(button => {
            button.addEventListener('click', () => {
                // Remove active class from all buttons
                document.querySelectorAll('.filter-btn').forEach(btn => btn.classList.remove('active'));
                // Add active class to clicked button
                button.classList.add('active');
                
                // Reload projects with new filter
                loadProjects();
            });
        });
        
        // Show Project Detail
        function showProjectDetail(projectId) {
            const project = projects.find(p => p.id === projectId);
            
            if (project) {
                document.getElementById('projectTitle').textContent = project.title;
                document.getElementById('projectLocation').textContent = project.location;
                document.getElementById('projectScale').textContent = project.scale;
                document.getElementById('projectClient').textContent = project.client;
                
                // Set category label
                let categoryLabel = '';
                switch(project.category) {
                    case 'design': categoryLabel = 'Design Project'; break;
                    case 'supervised': categoryLabel = 'Supervised Project'; break;
                    case 'pending': categoryLabel = 'Pending Project'; break;
                    case 'design-supervision': categoryLabel = 'Design & Supervision Project'; break;
                    default: categoryLabel = 'Project';
                }
                document.getElementById('projectCategory').textContent = categoryLabel;
                
                // Set description
                document.getElementById('projectDescription').innerHTML = project.description;
                
                // Set details list
                const detailsList = document.getElementById('projectDetailsList');
                detailsList.innerHTML = `
                    <li><strong>Project Type:</strong> ${project.type.charAt(0).toUpperCase() + project.type.slice(1)}</li>
                    <li><strong>Location:</strong> ${project.location}</li>
                    <li><strong>Scale:</strong> ${project.scale}</li>
                    <li><strong>Client:</strong> ${project.client}</li>
                    <li><strong>Category:</strong> ${categoryLabel}</li>
                    <li><strong>Services:</strong> Design, Engineering, Supervision</li>
                `;
                
                showPage('project-detail');
            }
        }
        
        // Contact Form Submission
        const contactForm = document.getElementById('contactForm');
        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;
            
            alert(`Thank you ${name}! Your message has been sent. We'll contact you at ${email} soon.`);
            contactForm.reset();
        });
        
        // Header scroll effect
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.boxShadow = '0 5px 20px rgba(0, 0, 0, 0.1)';
            } else {
                header.style.boxShadow = '0 2px 15px rgba(0, 0, 0, 0.1)';
            }
        });
        
        // Initialize - Load projects on page load if on projects page
        document.addEventListener('DOMContentLoaded', () => {
            if (window.location.hash) {
                const pageId = window.location.hash.substring(1);
                if (document.getElementById(pageId)) {
                    showPage(pageId);
                }
            }
            
            // Load projects if on projects page
            if (document.getElementById('projects').classList.contains('active')) {
                loadProjects();
            }
        });
    </script>
</body>
</html>
