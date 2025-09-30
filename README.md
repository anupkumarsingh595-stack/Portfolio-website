# Portfolio-website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anup Kumar Singh - Network Professional</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #0a0e27;
            color: #333;
            line-height: 1.6;
        }

        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(10, 14, 39, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 2px 20px rgba(0,0,0,0.3);
            z-index: 1000;
            padding: 1rem 0;
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 2rem;
            flex-wrap: wrap;
        }

        nav a {
            text-decoration: none;
            color: #fff;
            font-weight: 600;
            transition: color 0.3s;
            position: relative;
        }

        nav a:after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #00d9ff;
            transition: width 0.3s;
        }

        nav a:hover:after {
            width: 100%;
        }

        nav a:hover {
            color: #00d9ff;
        }

        section {
            min-height: 100vh;
            padding: 6rem 2rem 4rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .container {
            max-width: 1200px;
            width: 100%;
        }

        #hero {
            text-align: center;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1f4d 100%);
            position: relative;
            overflow: hidden;
        }

        #hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                linear-gradient(45deg, transparent 30%, rgba(0, 217, 255, 0.1) 50%, transparent 70%),
                linear-gradient(-45deg, transparent 30%, rgba(0, 123, 255, 0.1) 50%, transparent 70%);
            animation: shimmer 3s infinite;
        }

        @keyframes shimmer {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }

        .hero-content {
            position: relative;
            z-index: 1;
        }

        #hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            color: #fff;
            animation: fadeInUp 1s ease;
        }

        #hero .title {
            font-size: 1.8rem;
            color: #00d9ff;
            margin-bottom: 1rem;
            font-weight: 600;
            animation: fadeInUp 1s ease 0.2s;
            animation-fill-mode: both;
        }

        #hero p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #b8c5d6;
            animation: fadeInUp 1s ease 0.4s;
            animation-fill-mode: both;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .profile-image {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            margin: 0 auto 2rem;
            border: 5px solid #00d9ff;
            box-shadow: 0 0 30px rgba(0, 217, 255, 0.5);
            animation: fadeInUp 1s ease;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #1a1f4d, #2a3f5f);
            overflow: hidden;
        }

        .profile-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .btn {
            display: inline-block;
            padding: 1rem 2.5rem;
            background: linear-gradient(135deg, #00d9ff, #007bff);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: transform 0.3s, box-shadow 0.3s;
            animation: fadeInUp 1s ease 0.6s;
            animation-fill-mode: both;
            margin: 0.5rem;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 217, 255, 0.4);
        }

        .btn-secondary {
            background: transparent;
            border: 2px solid #00d9ff;
        }

        #about, #skills, #projects, #certifications, #contact {
            background: #f8f9fa;
        }

        #about {
            background: white;
        }

        h2 {
            font-size: 2.5rem;
            margin-bottom: 3rem;
            text-align: center;
            color: #0a0e27;
            position: relative;
            padding-bottom: 1rem;
        }

        h2:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(135deg, #00d9ff, #007bff);
            border-radius: 2px;
        }

        .about-content {
            max-width: 900px;
            margin: 0 auto;
            font-size: 1.1rem;
            color: #555;
            text-align: center;
            line-height: 1.8;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .skill-category {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 123, 255, 0.2);
        }

        .skill-category h3 {
            color: #007bff;
            margin-bottom: 1rem;
            font-size: 1.4rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .skill-category ul {
            list-style: none;
        }

        .skill-category li {
            padding: 0.5rem 0;
            color: #555;
            position: relative;
            padding-left: 1.5rem;
        }

        .skill-category li:before {
            content: '▹';
            position: absolute;
            left: 0;
            color: #00d9ff;
            font-weight: bold;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .project-card {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s, box-shadow 0.3s;
            border-top: 4px solid #007bff;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 123, 255, 0.3);
        }

        .project-card h3 {
            color: #0a0e27;
            margin-bottom: 1rem;
            font-size: 1.4rem;
        }

        .project-card p {
            color: #666;
            line-height: 1.6;
        }

        .cert-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
            max-width: 900px;
            margin: 0 auto;
        }

        .cert-card {
            background: linear-gradient(135deg, #007bff, #00d9ff);
            color: white;
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            font-weight: 600;
            font-size: 1.1rem;
            box-shadow: 0 5px 20px rgba(0, 123, 255, 0.3);
            transition: transform 0.3s;
        }

        .cert-card:hover {
            transform: scale(1.05);
        }

        .contact-section {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
            gap: 2rem;
            margin-top: 2rem;
        }

        .contact-item {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.1);
        }

        .contact-item h3 {
            color: #007bff;
            margin-bottom: 0.5rem;
        }

        .contact-item a {
            color: #00d9ff;
            text-decoration: none;
            font-size: 1.2rem;
            transition: color 0.3s;
        }

        .contact-item a:hover {
            color: #007bff;
        }

        footer {
            background: #0a0e27;
            color: white;
            text-align: center;
            padding: 2rem;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            #hero h1 {
                font-size: 2.5rem;
            }

            #hero .title {
                font-size: 1.4rem;
            }

            nav ul {
                gap: 1rem;
                padding: 0 1rem;
            }

            h2 {
                font-size: 2rem;
            }

            .skills-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li><a href="#hero">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#certifications">Certifications</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section id="hero">
        <div class="container">
            <div class="hero-content">
                <div class="profile-image">
                    <img src="photo1.jpg" alt="Anup Kumar Singh">
                </div>
                <h1>Anup Kumar Singh</h1>
                <p class="title">Computer Networking Professional</p>
                <p>Designing, configuring, and securing networks to enhance connectivity and organizational productivity</p>
                <a href="#contact" class="btn">Get In Touch</a>
                <a href="#projects" class="btn btn-secondary">View Projects</a>
            </div>
        </div>
    </section>

    <section id="about">
        <div class="container">
            <h2>About Me</h2>
            <div class="about-content">
                <p>
                    I am a passionate and detail-oriented Computer Networking Professional with strong knowledge 
                    in designing, configuring, and troubleshooting networks. Skilled in LAN/WAN, Routing, Switching, 
                    Network Security, Wireless Networking, and Cloud Networking, I aim to build efficient and secure 
                    networks that enhance connectivity and organizational productivity.
                </p>
            </div>
        </div>
    </section>

    <section id="skills">
        <div class="container">
            <h2>Technical Skills</h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>🌐 Networking Fundamentals</h3>
                    <ul>
                        <li>TCP/IP, OSI Model, Subnetting</li>
                        <li>DHCP, DNS, NAT, VLAN</li>
                        <li>IPv4/IPv6 configuration</li>
                    </ul>
                </div>

                <div class="skill-category">
                    <h3>🔀 Routing & Switching</h3>
                    <ul>
                        <li>Static & Dynamic Routing</li>
                        <li>RIP, OSPF, EIGRP, BGP</li>
                        <li>Cisco Routers & Switches</li>
                        <li>STP, VTP, EtherChannel</li>
                    </ul>
                </div>

                <div class="skill-category">
                    <h3>🔒 Network Security</h3>
                    <ul>
                        <li>Firewalls (Cisco ASA, Fortinet, pfSense)</li>
                        <li>VPN (Site-to-Site, Remote Access)</li>
                        <li>IDS/IPS Implementation</li>
                        <li>Access Control Lists (ACLs)</li>
                    </ul>
                </div>

                <div class="skill-category">
                    <h3>📡 Wireless Networking</h3>
                    <ul>
                        <li>WLAN configuration & troubleshooting</li>
                        <li>Wi-Fi security (WPA2/WPA3)</li>
                        <li>Wireless controller setup</li>
                    </ul>
                </div>

                <div class="skill-category">
                    <h3>🖥️ Servers & Virtualization</h3>
                    <ul>
                        <li>Windows Server (AD, DNS, DHCP)</li>
                        <li>Linux Networking (CentOS/Ubuntu)</li>
                        <li>VMware/VirtualBox environments</li>
                    </ul>
                </div>

                <div class="skill-category">
                    <h3>🛠️ Tools & Monitoring</h3>
                    <ul>
                        <li>Wireshark, Cisco Packet Tracer</li>
                        <li>GNS3, SolarWinds</li>
                        <li>Network Performance Monitoring</li>
                        <li>CLI tools (Ping, Traceroute, Netstat)</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <section id="projects">
        <div class="container">
            <h2>Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>Enterprise Network Design</h3>
                    <p>Designed a secure LAN/WAN network for a medium-size organization. Implemented OSPF routing, VLAN segmentation, and comprehensive firewall policies to ensure optimal security and performance.</p>
                </div>

                <div class="project-card">
                    <h3>Campus Wi-Fi Deployment</h3>
                    <p>Deployed a wireless network across a campus with centralized controller integration and secure authentication system, providing seamless connectivity for thousands of users.</p>
                </div>

                <div class="project-card">
                    <h3>Firewall & VPN Configuration</h3>
                    <p>Configured Cisco ASA firewall with advanced security rules. Set up Site-to-Site and Remote VPN connections to enable secure remote access for distributed teams.</p>
                </div>

                <div class="project-card">
                    <h3>VoIP Implementation</h3>
                    <p>Implemented IP Telephony system with QoS policies to optimize voice traffic, ensuring clear communication and minimal latency across the organization.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="certifications">
        <div class="container">
            <h2>Certifications</h2>
            <div class="cert-grid">
                <div class="cert-card">
                    🎓 CCNA<br>Cisco Certified Network Associate
                </div>
                <div class="cert-card">
                    🎓 CompTIA Network+
                </div>
                <div class="cert-card">
                    🎓 CCNP<br>Cisco Certified Network Professional
                </div>
                <div class="cert-card">
                    🎓 Cybersecurity Fundamentals
                </div>
            </div>
        </div>
    </section>

    <section id="contact">
        <div class="container">
            <h2>Get In Touch</h2>
            <div class="contact-section">
                <p style="font-size: 1.2rem; margin-bottom: 2rem; color: #666;">
                    I'm always interested in hearing about new projects and opportunities. 
                    Feel free to reach out!
                </p>
                <div class="contact-info">
                    <div class="contact-item">
                        <h3>📧 Email</h3>
                        <a href="mailto:anupkumar595@gmail.com">anupkumar595@gmail.com</a>
                    </div>
                    <div class="contact-item">
                        <h3>💼 LinkedIn</h3>
                        <a href="https://www.linkedin.com/public-profile/settings?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_self_edit_contact-info%3BJrvYDce7REKL%2FkE9ClzmWg%3D%3D" target="_blank">Connect on LinkedIn</a>
                    </div>
                    <div class="contact-item">
                        <h3>👤 Name</h3>
                        <p style="font-size: 1.2rem; color: #333; margin: 0;">Anup Kumar Singh</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <p>&copy; 2025 Anup Kumar Singh. All rights reserved.</p>
    </footer>

    <script>
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                target.scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Add scroll animation effect
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, { threshold: 0.1 });

        document.querySelectorAll('.skill-category, .project-card, .cert-card').forEach(el => {
            el.style.opacity = '0';
            el.style.transform = 'translateY(20px)';
            el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
            observer.observe(el);
        });
    </script>
</body>
</html>
