<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bilel - Cybersecurity Portfolio</title>
    <style>
        :root {
            --primary-dark: #f5f5f7; /* Light background */
            --secondary-dark: #e8e8ed; /* Slightly darker for cards */
            --accent-teal: #0070c9; /* Professional blue accent */
            --text-dark: #333333; /* Dark text for light background */
            --text-medium: #555555; /* Medium text for light background */
            --card-bg: #ffffff; /* White card background */
            --border-color: rgba(0, 112, 201, 0.2); /* Subtle border color */
            --shadow-color: rgba(0, 0, 0, 0.1); /* Subtle shadow */
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Calibri', 'San Francisco', 'SF Pro Text', -apple-system, BlinkMacSystemFont, sans-serif;
            background-color: var(--primary-dark);
            color: var(--text-medium);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            padding: 20px 0;
            background-color: rgba(245, 245, 247, 0.95); /* Slightly transparent */
            backdrop-filter: blur(10px);
            z-index: 1000;
            transition: top 0.3s;
            box-shadow: 0 2px 10px var(--shadow-color);
        }

        nav .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .nav-logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent-teal);
        }

        .nav-links {
            list-style: none;
            display: flex;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            color: var(--text-dark);
            text-decoration: none;
            font-size: 0.9rem;
            letter-spacing: 0.5px;
            transition: color 0.3s ease;
        }

        .nav-links a:hover, .nav-links a.active {
            color: var(--accent-teal);
        }
        
        .nav-toggle {
            display: none;
            font-size: 1.5rem;
            color: var(--accent-teal);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: left;
            padding: 100px 20px;
            background: linear-gradient(135deg, var(--primary-dark) 0%, var(--secondary-dark) 100%);
        }

        .hero-content {
            max-width: 800px;
        }

        .hero-greeting {
            color: var(--accent-teal);
            font-size: 1.1rem;
            margin-bottom: 20px;
            font-family: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace;
        }

        .hero-name {
            font-size: clamp(40px, 8vw, 70px);
            color: var(--text-dark);
            font-weight: 700;
            margin-bottom: 10px;
            line-height: 1.1;
        }

        .hero-title {
            font-size: clamp(30px, 6vw, 60px);
            color: var(--text-medium);
            font-weight: 700;
            margin-bottom: 25px;
            line-height: 1.1;
        }

        .hero-tagline {
            font-size: 1.1rem;
            max-width: 550px;
            margin-bottom: 40px;
            color: var(--text-medium);
        }

        .btn {
            display: inline-block;
            padding: 12px 25px;
            background-color: transparent;
            color: var(--accent-teal);
            border: 1px solid var(--accent-teal);
            border-radius: 4px;
            text-decoration: none;
            font-size: 1rem;
            transition: background-color 0.3s ease, color 0.3s ease;
            font-family: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace;
        }

        .btn:hover {
            background-color: rgba(0, 112, 201, 0.1);
        }

        /* General Section Styling */
        .section {
            padding: 100px 0;
        }

        .section-title {
            font-size: 2rem;
            color: var(--text-dark);
            margin-bottom: 50px;
            text-align: center;
            position: relative;
            padding-bottom: 15px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 3px;
            background-color: var(--accent-teal);
            border-radius: 2px;
        }
        
        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 3fr 2fr;
            gap: 50px;
            align-items: center;
        }

        .about-text p {
            margin-bottom: 15px;
        }
        
        .about-image-container {
            position: relative;
            max-width: 300px;
            margin: auto;
        }

        .about-image {
            width: 100%;
            border-radius: 4px;
            position: relative;
            z-index: 1;
            box-shadow: 0 5px 15px var(--shadow-color);
        }
        
        .about-image-container::after {
            content: '';
            display: block;
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 4px;
            border: 2px solid var(--accent-teal);
            top: 15px;
            left: 15px;
            z-index: 0;
            transition: all 0.25s cubic-bezier(0.645,0.045,0.355,1);
        }

        .about-image-container:hover::after {
            top: 10px;
            left: 10px;
        }

        /* Expertise Section */
        .expertise-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
        }

        .expertise-card {
            background-color: var(--card-bg);
            padding: 30px;
            border-radius: 8px;
            border-left: 3px solid var(--accent-teal);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            box-shadow: 0 5px 15px var(--shadow-color);
        }

        .expertise-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px var(--shadow-color);
        }

        .expertise-card h3 {
            color: var(--text-dark);
            font-size: 1.3rem;
            margin-bottom: 15px;
        }

        /* Experience Section - Timeline */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }

        .timeline::after {
            content: '';
            position: absolute;
            width: 3px;
            background-color: var(--accent-teal);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -1.5px;
            opacity: 0.3;
        }

        .timeline-item {
            padding: 10px 40px;
            position: relative;
            background-color: inherit;
            width: 50%;
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            right: -10px;
            background-color: var(--primary-dark);
            border: 3px solid var(--accent-teal);
            top: 20px;
            border-radius: 50%;
            z-index: 1;
        }

        .timeline-item.left {
            left: 0;
        }

        .timeline-item.right {
            left: 50%;
        }

        .timeline-item.left::before {
            content: " ";
            height: 0;
            position: absolute;
            top: 25px;
            width: 0;
            z-index: 1;
            right: 30px;
            border: medium solid var(--card-bg);
            border-width: 10px 0 10px 10px;
            border-color: transparent transparent transparent var(--card-bg);
        }

        .timeline-item.right::before {
            content: " ";
            height: 0;
            position: absolute;
            top: 25px;
            width: 0;
            z-index: 1;
            left: 30px;
            border: medium solid var(--card-bg);
            border-width: 10px 10px 10px 0;
            border-color: transparent var(--card-bg) transparent transparent;
        }

        .timeline-item.right::after {
            left: -10px;
        }

        .timeline-content {
            padding: 20px;
            background-color: var(--card-bg);
            position: relative;
            border-radius: 8px;
            box-shadow: 0 5px 15px var(--shadow-color);
        }
        
        .timeline-content h3 {
            color: var(--text-dark);
            font-size: 1.2rem;
            margin-bottom: 5px;
        }
        
        .timeline-content .period {
            color: var(--accent-teal);
            font-size: 0.9rem;
            margin-bottom: 10px;
            font-family: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace;
        }

        /* Certifications Section */
        .certifications-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
        }

        .certification-card {
            background-color: var(--card-bg);
            padding: 25px;
            border-radius: 8px;
            box-shadow: 0 5px 15px var(--shadow-color);
        }

        .certification-card h3 {
            color: var(--accent-teal);
            font-size: 1.3rem;
            margin-bottom: 15px;
        }

        .certification-card ul {
            list-style: none;
        }

        .certification-card li {
            margin-bottom: 8px;
            padding-left: 20px;
            position: relative;
        }

        .certification-card li::before {
            content: '›';
            position: absolute;
            left: 0;
            color: var(--accent-teal);
        }

        /* Contact Section */
        .contact-content p {
            max-width: 600px;
            margin: 0 auto 40px auto;
            text-align: center;
            font-size: 1.1rem;
        }

        .contact-btn-container {
            text-align: center;
        }

        /* Footer */
        footer {
            padding: 30px 0;
            text-align: center;
            font-size: 0.9rem;
            color: var(--text-medium);
            font-family: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace;
            background-color: var(--secondary-dark);
        }

        footer a {
            color: var(--accent-teal);
            text-decoration: none;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
                flex-direction: column;
                width: 100%;
                position: absolute;
                top: 70px;
                left: 0;
                background-color: rgba(245, 245, 247, 0.95);
            }
            .nav-links.active {
                display: flex;
            }
            .nav-links li {
                margin: 15px 0;
                text-align: center;
            }
            .nav-toggle {
                display: block;
            }

            .hero {
                text-align: center;
            }
            .hero-content {
                padding: 0 10px;
            }
            .hero-tagline {
                margin-left: auto;
                margin-right: auto;
            }

            .about-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            .about-image-container {
                order: -1; /* Image on top on mobile */
            }

            .timeline::after {
                left: 20px;
            }
            .timeline-item {
                width: 100%;
                padding-left: 50px;
                padding-right: 10px;
            }
            .timeline-item.right, .timeline-item.left {
                left: 0;
            }
            .timeline-item::after {
                left: 10px;
            }
            .timeline-item.left::before, .timeline-item.right::before {
                left: 40px;
                border-color: transparent var(--card-bg) transparent transparent;
                border-width: 10px 10px 10px 0;
            }
            .certifications-grid {
                grid-template-columns: 1fr;
            }
        }

    </style>
</head>
<body>
    <nav id="navbar">
        <div class="container">
            <div class="nav-logo">Bilel</div>
            <ul class="nav-links" id="navMenu">
                <li><a href="#about" class="active">About</a></li>
                <li><a href="#expertise">Expertise</a></li>
                <li><a href="#experience">Experience</a></li>
                <li><a href="#certifications">Certifications</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="nav-toggle" id="navToggle">☰</div>
        </div>
    </nav>

    <header class="hero" id="hero">
        <div class="hero-content">
            <p class="hero-greeting">Hi, my name is</p>
            <h1 class="hero-name">Bilel.</h1>
            <h2 class="hero-title">I build things for security.</h2>
            <p class="hero-tagline">
                I'm a Security Architect & Penetration Tester specializing in uncovering vulnerabilities and designing robust defenses for enterprise organizations.
            </p>
            <a href="#contact" class="btn">Get In Touch</a>
        </div>
    </header>

    <main>
        <section class="section" id="about">
            <div class="container">
                <h2 class="section-title">About Me</h2>
                <div class="about-content">
                    <div class="about-text">
                        <p>With over 12 years of experience at organizations like Microsoft, IBM, Splunk, and BlueVoyant, I've built a career focused on identifying vulnerabilities and implementing effective security solutions. My expertise spans MSSP and MDR services, having worked across the EU, US, Asia, and UAE with clients ranging from financial institutions to manufacturing giants.</p>
                        <p>I specialize in translating complex security challenges into practical, implementable solutions. My approach combines deep technical knowledge with business acumen, ensuring security measures enhance rather than hinder operations. I've led SIEM implementations, SOC operations, and threat hunting initiatives that have measurably improved clients' security postures.</p>
                        <p>When I'm not immersed in cybersecurity, I train in Brazilian Jiu-Jitsu—a discipline that, like security work, requires strategy, patience, and adaptability. I also enjoy fishing and spearfishing, activities that provide both the thrill of the hunt and moments of reflection.</p>
                        <p>Key focus areas: Security Architecture, Penetration Testing, SIEM Implementation, SOC Operations, Threat Hunting.</p>
                    </div>
                    <div class="about-image-container">
                        <!-- Placeholder for an image. User can replace this. -->
                        <img src="https://via.placeholder.com/300x300.png?text=Bilel" alt="Bilel - Security Professional" class="about-image">
                    </div>
                </div>
            </div>
        </section>

        <section class="section" id="expertise">
            <div class="container">
                <h2 class="section-title">Areas of Expertise</h2>
                <div class="expertise-grid">
                    <div class="expertise-card">
                        <h3>Security Architecture</h3>
                        <p>Designing and implementing robust security infrastructures that align with business objectives and mitigate risks effectively.</p>
                    </div>
                    <div class="expertise-card">
                        <h3>Penetration Testing</h3>
                        <p>Conducting thorough penetration tests to identify vulnerabilities in networks, applications, and cloud environments.</p>
                    </div>
                    <div class="expertise-card">
                        <h3>SIEM Implementation</h3>
                        <p>Deploying and optimizing SIEM solutions (Splunk, Sentinel) for advanced threat detection and incident response.</p>
                    </div>
                    <div class="expertise-card">
                        <h3>SOC Operations</h3>
                        <p>Building and leading high-performing Security Operations Centers, focusing on efficiency and rapid response.</p>
                    </div>
                    <div class="expertise-card">
                        <h3>Threat Hunting</h3>
                        <p>Proactively searching for and neutralizing advanced threats that may evade traditional security defenses.</p>
                    </div>
                    <div class="expertise-card">
                        <h3>Security Compliance</h3>
                        <p>Guiding organizations through GDPR, PCI DSS, ISO 27001, and other regulatory frameworks to ensure adherence.</p>
                    </div>
                </div>
            </div>
        </section>

        <section class="section" id="experience">
            <div class="container">
                <h2 class="section-title">Professional Experience</h2>
                <div class="timeline">
                    <div class="timeline-item left">
                        <div class="timeline-content">
                            <h3>Senior Security Architect</h3>
                            <p class="period">BlueVoyant | 2021 - Present</p>
                            <p>Lead security architecture for key clients, design MDR solutions, and oversee complex Splunk/Sentinel deployments.</p>
                        </div>
                    </div>
                    <div class="timeline-item right">
                        <div class="timeline-content">
                            <h3>Cybersecurity Consultant</h3>
                            <p class="period">IBM | 2018 - 2021</p>
                            <p>Provided expert consulting on SIEM, SOC optimization, and threat intelligence for enterprise clients.</p>
                        </div>
                    </div>
                    <div class="timeline-item left">
                        <div class="timeline-content">
                            <h3>Splunk Professional Services</h3>
                            <p class="period">Splunk | 2016 - 2018</p>
                            <p>Delivered Splunk implementation, administration, and architecture services to a wide range of customers.</p>
                        </div>
                    </div>
                     <div class="timeline-item right">
                        <div class="timeline-content">
                            <h3>Security Analyst</h3>
                            <p class="period">Microsoft | 2014 - 2016</p>
                            <p>Focused on threat detection, incident response, and vulnerability management within Microsoft's security operations.</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="section" id="certifications">
            <div class="container">
                <h2 class="section-title">Certifications</h2>
                <div class="certifications-grid">
                    <div class="certification-card">
                        <h3>OffSec</h3>
                        <ul>
                            <li>Offensive Security Certified Professional – 2014</li>
                            <li>Offensive Security Wireless Professional – 2014</li>
                            <li>Offensive Security Web Application Professional – 2015</li>
                        </ul>
                    </div>
                    <div class="certification-card">
                        <h3>CompTIA</h3>
                        <ul>
                            <li>CompTIA Linux+ – 2016</li>
                            <li>CompTIA Linux Network Professional – 2019</li>
                            <li>CompTIA Network+ – 2019</li>
                            <li>CompTIA Network Vulnerability Assessment Professional – CNVP Stackable Certification – 2019</li>
                            <li>CompTIA PenTest+ ce Certification – 2020</li>
                            <li>CompTIA Security+ ce Certification – 2020</li>
                            <li>CompTIA Security+ – 2020</li>
                        </ul>
                    </div>
                    <div class="certification-card">
                        <h3>ISC² & Palo Alto</h3>
                        <ul>
                            <li>CISSP Certification – 2017</li>
                            <li>Palo Alto Networks Accredited Configuration Engineer (ACE) – 2016</li>
                        </ul>
                    </div>
                    <div class="certification-card">
                        <h3>Splunk</h3>
                        <ul>
                            <li>Splunk Knowledge Objects – Onsite – 2016</li>
                            <li>Splunk Using Enterprise Security – 2016</li>
                            <li>Splunk Architect – 2017</li>
                            <li>Splunk Consultant I – 2017</li>
                            <li>Splunk Consultant II – 2017</li>
                            <li>Splunk Admin – 2017</li>
                            <li>Searching and Reporting with Splunk 6.x – eLearning – 2017</li>
                            <li>Splunk Accredited Consultant – 2018</li>
                            <li>Splunk Administration – Virtual – 2018</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section class="section" id="contact">
            <div class="container">
                <h2 class="section-title">Get In Touch</h2>
                <div class="contact-content">
                    <p>I'm always open to discussing new projects, security challenges, or opportunities to collaborate. Whether you have a question or just want to say hi, feel free to reach out!</p>
                    <div class="contact-btn-container">
                         <a href="mailto:your.email@example.com" class="btn">Say Hello</a>
                         <!-- User should replace your.email@example.com with their actual email -->
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <p>Designed & Built by Manus AI for Bilel</p>
            <p><a href="https://github.com/secnnet" target="_blank" rel="noopener noreferrer">GitHub</a> | <a href="https://linkedin.com/in/bilel" target="_blank" rel="noopener noreferrer">LinkedIn</a></p>
        </div>
    </footer>

    <script>
        // Mobile Nav Toggle
        const navToggle = document.getElementById('navToggle');
        const navMenu = document.getElementById('navMenu');
        navToggle.addEventListener('click', () => {
            navMenu.classList.toggle('active');
        });

        // Smooth scroll & active link highlighting
        const navLinks = document.querySelectorAll('.nav-links a');
        const sections = document.querySelectorAll('section, header.hero');

        window.addEventListener('scroll', () => {
            let current = '';
            sections.forEach(section => {
                const sectionTop = section.offsetTop;
                if (pageYOffset >= sectionTop - 75) { // 70px navbar height + 5px buffer
                    current = section.getAttribute('id');
                }
            });

            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === current) {
                    link.classList.add('active');
                }
            });
            
            // Sticky Nav
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
            } else {
                navbar.style.boxShadow = 'none';
            }
        });

        // Initial active link check
        // (Simplified for this example, more robust solution might be needed for edge cases)
        if(window.location.hash) {
            const currentHash = window.location.hash.substring(1);
            navLinks.forEach(link => {
                link.classList.remove('active');
                if (link.getAttribute('href').substring(1) === currentHash) {
                    link.classList.add('active');
                }
            });
        } else {
             // Default to 'About' or first link if no hash
            if(navLinks.length > 0) navLinks[0].classList.add('active');
        }

    </script>
</body>
</html>
