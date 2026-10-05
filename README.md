<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
            scroll-behavior: smooth;
        }

        body {
            background-color: #0f172a;
            color: #f8fafc;
            line-height: 1.6;
        }

        /* Header / Navbar */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: rgba(15, 23, 42, 0.9);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 10%;
            z-index: 1000;
            border-bottom: 1px solid #1e293b;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #38bdf8;
        }

        nav a {
            color: #cbd5e1;
            text-decoration: none;
            margin-left: 25px;
            font-weight: 400;
            transition: 0.3s;
        }

        nav a:hover {
            color: #38bdf8;
        }

        /* Hero Section */
        .hero {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 160px 10% 100px;
            min-height: 100vh;
        }

        .hero-content {
            max-width: 600px;
        }

        .hero-content h3 {
            font-size: 1.5rem;
            color: #94a3b8;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin: 10px 0;
            color: #f8fafc;
        }

        .hero-content h1 span {
            color: #38bdf8;
        }

        .hero-content p {
            color: #94a3b8;
            font-size: 1.1rem;
            margin-bottom: 25px;
        }

        .btn {
            display: inline-block;
            background: #38bdf8;
            color: #0f172a;
            padding: 12px 30px;
            border-radius: 5px;
            font-weight: 600;
            text-decoration: none;
            transition: 0.3s;
        }

        .btn:hover {
            background: #0ea5e9;
            box-shadow: 0 0 15px rgba(56, 189, 248, 0.4);
        }

        /* Sections General */
        section {
            padding: 100px 10%;
            border-bottom: 1px solid #1e293b;
        }

        section h2 {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            color: #f8fafc;
        }

        section h2 span {
            color: #38bdf8;
        }

        /* About Section */
        .about-text {
            max-width: 800px;
            margin: 0 auto;
            text-align: center;
            color: #94a3b8;
            font-size: 1.1rem;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
        }

        .skill-card {
            background: #1e293b;
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            transition: 0.3s;
            border: 1px solid #334155;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            border-color: #38bdf8;
        }

        .skill-card i {
            font-size: 2.5rem;
            color: #38bdf8;
            margin-bottom: 15px;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .project-card {
            background: #1e293b;
            border-radius: 10px;
            overflow: hidden;
            border: 1px solid #334155;
            transition: 0.3s;
        }

        .project-card:hover {
            transform: translateY(-5px);
            border-color: #38bdf8;
        }

        .project-info {
            padding: 20px;
        }

        .project-info h3 {
            margin-bottom: 10px;
            color: #f8fafc;
        }

        .project-info p {
            color: #94a3b8;
            font-size: 0.95rem;
            margin-bottom: 15px;
        }

        .project-link {
            color: #38bdf8;
            text-decoration: none;
            font-weight: 600;
        }

        /* Contact Section */
        .contact-content {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }

        .contact-content p {
            color: #94a3b8;
            margin-bottom: 25px;
        }

        .social-icons {
            margin-top: 20px;
        }

        .social-icons a {
            display: inline-flex;
            justify-content: center;
            align-items: center;
            width: 45px;
            height: 45px;
            background: #1e293b;
            color: #38bdf8;
            border-radius: 50%;
            margin: 0 10px;
            font-size: 1.2rem;
            border: 1px solid #334155;
            transition: 0.3s;
            text-decoration: none;
        }

        .social-icons a:hover {
            background: #38bdf8;
            color: #0f172a;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 20px;
            color: #64748b;
            font-size: 0.9rem;
            background: #090d16;
        }

        /* Responsive Design */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .hero-content {
            animation: fadeIn 1s ease-out;
        }

        @media (max-width: 768px) {
            .hero {
                flex-direction: column;
                text-align: center;
                padding-top: 130px;
            }
            .hero-content h1 {
                font-size: 2.5rem;
            }
            nav {
                display: none; /* মোবাইল ডিভাইসের জন্য সিম্পল রাখতে মেনু হাইড করা হয়েছে, চাইলে রাখতে পারেন */
            }
        }
    </style>
</head>
<body>

    <!-- Header / Navbar -->
    <header>
        <div class="logo">Portfolio.</div>
        <nav>
            <a href="#about">About</a>
            <a href="#skills">Skills</a>
            <a href="#projects">Projects</a>
            <a href="#contact">Contact</a>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h3>Hello, I'm</h3>
            <h1><span>আপনার নাম</span></h1>
            <p>আমি একজন ফ্রন্ট-এন্ড ওয়েব ডেভেলপার। আধুনিক এবং আকর্ষণীয় ওয়েবসাইট তৈরি করতে ভালোবাসি।</p>
            <a href="#contact" class="btn">Get in Touch</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about">
        <h2>About <span>Me</span></h2>
        <div class="about-text">
            <p>আমি প্রযুক্তির প্রতি apasionado এবং ওয়েব ডেভেলপমেন্ট নিয়ে কাজ করছি। ব্যবহারকারী-বান্ধব (User-friendly) এবং রেসপন্সিভ ডিজাইন তৈরি করা আমার মূল লক্ষ্য। নতুন কিছু শেখা এবং জটিল সমস্যার সমাধান করতে আমার ভালো লাগে।</p>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <h2>My <span>Skills</span></h2>
        <div class="skills-grid">
            <div class="skill-card">
                <i class="fab fa-html5"></i>
                <h3>HTML5</h3>
            </div>
            <div class="skill-card">
                <i class="fab fa-css3-alt"></i>
                <h3>CSS3</h3>
            </div>
            <div class="skill-card">
                <i class="fab fa-js"></i>
                <h3>JavaScript</h3>
            </div>
            <div class="skill-card">
                <i class="fab fa-git-alt"></i>
                <h3>Git & GitHub</h3>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects">
        <h2>My <span>Projects</span></h2>
        <div class="projects-grid">
            <div class="project-card">
                <div class="project-info">
                    <h3>প্রজেক্ট নাম ১</h3>
                    <p>এটি একটি আধুনিক ল্যান্ডিং পেজ যা HTML ও CSS দিয়ে তৈরি করা হয়েছে। এতে রেসপন্সিভ ডিজাইন ব্যবহার করা হয়েছে।</p>
                    <a href="#" class="project-link">View Project <i class="fas fa-arrow-right"></i></a>
                </div>
            </div>
            <div class="project-card">
                <div class="project-info">
                    <h3/২</h3>
                    <p>জাভাস্ক্রিপ্ট ব্যবহার করে তৈরি একটি ইন্টারঅ্যাক্টিভ ওয়েব অ্যাপ্লিকেশন বা টুল।</p>
                    <a href="#" class="project-link">View Project <i class="fas fa-arrow-right"></i></a>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <h2>Contact <span>Me</span></h2>
        <div class="contact-content">
            <p>আমার সাথে যোগাযোগ করতে চাইলে নিচের সোশ্যাল মিডিয়াগুলো ব্যবহার করতে পারেন অথবা সরাসরি ইমেইল পাঠাতে পারেন।</p>
            <a href="mailto:your-email@example.com" class="btn">Send Email</a>
            <div class="social-icons">
                <a href="#"><i class="fab fa-github"></i></a>
                <a href="#"><i class="fab fa-linkedin-in"></i></a>
                <a href="#"><i class="fab fa-twitter"></i></a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <p>&copy; 2026 আপনার নাম। All Rights Reserved.</p>
    </footer>

</body>
</html>
