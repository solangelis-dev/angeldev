<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Angel's Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #4f46e5;
            --primary-hover: #4338ca;
            --secondary: #10b981;
            --dark: #111827;
            --dark-lighter: #1f2937;
            --light: #f9fafb;
            --gray: #9ca3af;
            --border: #374151;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background-color: var(--dark);
            font-family: 'Poppins', sans-serif;
            color: var(--light);
            line-height: 1.6;
            padding: 0;
            margin: 0;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }
        
        .header {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
            padding-bottom: 20px;
        }
        
        .header::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 3px;
        }
        
        .title {
            font-size: 3rem;
            font-weight: 700;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            margin-bottom: 15px;
            letter-spacing: 1px;
        }
        
        .button {
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 12px 28px;
            border-radius: 8px;
            font-weight: 600;
            cursor: pointer;
            margin: 25px 0;
            font-size: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(79, 70, 229, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 16px rgba(79, 70, 229, 0.4);
        }
        
        .button::before {
            content: "";
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: all 0.6s ease;
        }
        
        .button:hover::before {
            left: 100%;
        }
        
        .intro-box {
            background-color: var(--dark-lighter);
            border-radius: 16px;
            padding: 35px;
            margin-bottom: 40px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            border: 1px solid var(--border);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .intro-box::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
        }
        
        .intro-box:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .intro-box p {
            margin-bottom: 15px;
            font-size: 1.05rem;
        }
        
        .intro-box p:last-child {
            margin-bottom: 0;
        }
        
        .panels-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-top: 30px;
        }
        
        @media (max-width: 768px) {
            .panels-container {
                grid-template-columns: 1fr;
            }
        }
        
        .panel {
            background-color: var(--dark-lighter);
            border-radius: 16px;
            padding: 35px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            border: 1px solid var(--border);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            height: 100%;
            position: relative;
            overflow: hidden;
        }
        
        .panel::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 3px;
            height: 100%;
            background: linear-gradient(180deg, var(--primary), var(--secondary));
        }
        
        .panel:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.3);
        }
        
        .panel-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--light);
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 12px;
            position: relative;
            padding-bottom: 15px;
        }
        
        .panel-title::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 2px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 2px;
        }
        
        .panel-content ul {
            list-style-type: none;
            padding-left: 0;
        }
        
        .panel-content li {
            margin-bottom: 15px;
            position: relative;
            padding-left: 28px;
            font-size: 1.05rem;
        }
        
        .panel-content li::before {
            content: "•";
            color: var(--secondary);
            position: absolute;
            left: 0;
            font-size: 1.5rem;
            line-height: 1;
        }
        
        .panel-content p {
            margin-top: 20px;
            font-style: italic;
            color: var(--gray);
        }
        
        .highlight {
            color: var(--secondary);
            font-weight: 500;
        }
        
        .availability {
            display: inline-block;
            background-color: rgba(16, 185, 129, 0.1);
            border: 1px solid rgba(16, 185, 129, 0.3);
            color: var(--secondary);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.9rem;
            margin-top: 10px;
        }
        
        .footer {
            text-align: center;
            margin-top: 60px;
            color: var(--gray);
            font-size: 0.9rem;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }
        
        .social-link {
            color: var(--gray);
            font-size: 1.5rem;
            transition: color 0.3s ease, transform 0.3s ease;
        }
        
        .social-link:hover {
            color: var(--primary);
            transform: translateY(-3px);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1 class="title">Angel <3</h1>
            <button class="button">Contact Me</button>
        </div>
        
        <div class="intro-box">
            <p>Hello! I'm <span class="highlight">Angel</span> — a skilled and experienced developer proficient in a wide range of programming languages and technologies.</p>
            <p>My time zone is <span class="highlight">MST (Mountain Standard Time)</span>, and I'm available daily between 10:00 AM and 7:00 PM.</p>
            <p>Feel free to reach out if you need assistance or want to collaborate on a project!</p>
            <div class="availability"><i class="fas fa-clock"></i> Available for new projects</div>
        </div>
        
        <div class="panels-container">
            <div class="panel">
                <div class="panel-title">
                    <i class="fas fa-tools"></i>
                    <span>Experience & Skills</span>
                </div>
                <div class="panel-content">
                    <p>I'm proficient in a wide variety of programming languages and frameworks, including:</p>
                    <ul>
                        <li>HTML</li>
                        <li>CSS</li>
                        <li>JavaScript</li>
                        <li>Python</li>
                        <li>Java</li>
                        <li>C++</li>
                        <li>…and many more.</li>
                    </ul>
                </div>
            </div>
            
            <div class="panel">
                <div class="panel-title">
                    <i class="fas fa-folder-open"></i>
                    <span>Notable Projects</span>
                </div>
                <div class="panel-content">
                    <ul>
                        <li>Full-stack web applications using HTML/CSS/JS</li>
                        <li>Discord bots with advanced automation (Python & JavaScript)</li>
                        <li>License key authentication systems</li>
                    </ul>
                    <p>Always learning, always building. Let me know if you want a more tailored version for something specific like your horror game or license tool work.</p>
                </div>
            </div>
        </div>
        
        <div class="footer">
            <p>© 2025 Angel. All rights reserved.</p>
            <div class="social-links">
                <a href="#" class="social-link"><i class="fab fa-github"></i></a>
                <a href="#" class="social-link"><i class="fab fa-linkedin"></i></a>
                <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                <a href="#" class="social-link"><i class="fab fa-discord"></i></a>
            </div>
        </div>
    </div>
</body>
</html>
