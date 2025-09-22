<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EduCalc Hub – Student Calculators & Converters</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4a6fa5;
            --secondary: #166088;
            --accent: #4fc3a1;
            --light: #f8f9fa;
            --dark: #343a40;
            --gray: #6c757d;
            --success: #28a745;
            --warning: #ffc107;
            --danger: #dc3545;
            --info: #17a2b8;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo i {
            font-size: 2rem;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            gap: 1.5rem;
        }
        
        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: opacity 0.3s;
        }
        
        nav a:hover {
            opacity: 0.8;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(74, 111, 165, 0.9), rgba(22, 96, 136, 0.9)), url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><rect width="100" height="100" fill="%234a6fa5" opacity="0.2"/><path d="M0 0L100 100" stroke="white" stroke-width="2" opacity="0.1"/><path d="M100 0L0 100" stroke="white" stroke-width="2" opacity="0.1"/></svg>');
            color: white;
            text-align: center;
            padding: 4rem 1rem;
            margin-bottom: 2rem;
        }
        
        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 2rem;
        }
        
        .search-box {
            max-width: 600px;
            margin: 0 auto;
            position: relative;
        }
        
        .search-box input {
            width: 100%;
            padding: 1rem 1.5rem;
            border-radius: 50px;
            border: none;
            font-size: 1rem;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }
        
        .search-box button {
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translateY(-50%);
            background: var(--accent);
            border: none;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            color: white;
            cursor: pointer;
        }
        
        /* Category Navigation */
        .category-nav {
            background: white;
            padding: 1rem 0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
            margin-bottom: 2rem;
            overflow-x: auto;
            white-space: nowrap;
        }
        
        .category-nav ul {
            display: flex;
            list-style: none;
            justify-content: center;
            gap: 1.5rem;
            padding: 0 1rem;
        }
        
        .category-nav a {
            color: var(--gray);
            text-decoration: none;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 50px;
            transition: all 0.3s;
        }
        
        .category-nav a:hover, .category-nav a.active {
            background: var(--primary);
            color: white;
        }
        
        /* Tools Grid */
        .section-title {
            text-align: center;
            margin-bottom: 2rem;
            color: var(--secondary);
            position: relative;
            padding-bottom: 0.5rem;
        }
        
        .section-title:after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: var(--accent);
            border-radius: 2px;
        }
        
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-bottom: 3rem;
        }
        
        .tool-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .tool-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
        }
        
        .tool-card-header {
            background: var(--primary);
            color: white;
            padding: 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .tool-card-body {
            padding: 1.5rem;
        }
        
        .tool-card-body p {
            color: var(--gray);
            margin-bottom: 1.5rem;
        }
        
        .btn {
            display: inline-block;
            background: var(--accent);
            color: white;
            padding: 0.6rem 1.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 500;
            transition: background 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background: #3da58a;
        }
        
        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 3rem 0 1.5rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }
        
        .footer-column h3 {
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 0.8rem;
        }
        
        .footer-column a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-column a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 1.5rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
            color: #aaa;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }
            
            nav ul {
                gap: 1rem;
            }
            
            .hero h2 {
                font-size: 2rem;
            }
            
            .tools-grid {
                grid-template-columns: 1fr;
            }
            
            .category-nav ul {
                justify-content: flex-start;
            }
        }
        
        /* Tool Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            overflow-y: auto;
        }
        
        .modal-content {
            background: white;
            margin: 2rem auto;
            width: 90%;
            max-width: 800px;
            border-radius: 10px;
            padding: 2rem;
            position: relative;
        }
        
        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1rem;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--gray);
        }
        
        .tool-interface {
            margin-top: 1.5rem;
        }
        
        .input-group {
            margin-bottom: 1rem;
        }
        
        .input-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .input-group input, .input-group select {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        .results {
            margin-top: 1.5rem;
            padding: 1rem;
            background: #f8f9fa;
            border-radius: 5px;
            display: none;
        }
        
        .results.show {
            display: block;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <i class="fas fa-calculator"></i>
                <h1>EduCalc Hub</h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#tools">All Tools</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h2>Student Calculators & Converters</h2>
            <p>Your all-in-one platform for academic tools - converters, calculators, generators, and trackers to make student life easier.</p>
            <div class="search-box">
                <input type="text" placeholder="Search for tools...">
                <button><i class="fas fa-search"></i></button>
            </div>
        </div>
    </section>

    <!-- Category Navigation -->
    <div class="category-nav">
        <div class="container">
            <ul>
                <li><a href="#converters" class="active">Converters</a></li>
                <li><a href="#calculators">Calculators</a></li>
                <li><a href="#generators">Generators</a></li>
                <li><a href="#trackers">Trackers</a></li>
                <li><a href="#document-tools">Document Tools</a></li>
            </ul>
        </div>
    </div>

    <!-- Main Content -->
    <main class="container">
        <!-- Converters Section -->
        <section id="converters">
            <h2 class="section-title">Converters</h2>
            <div class="tools-grid">
                <!-- Percentage Converter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-percentage"></i>
                        <h3>Percentage Converter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Convert marks to percentage and vice versa with this easy-to-use tool.</p>
                        <button class="btn use-tool" data-tool="percentage-converter">Use Tool</button>
                    </div>
                </div>

                <!-- CGPA/GPA/Percentage Converter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-graduation-cap"></i>
                        <h3>CGPA/GPA/Percentage Converter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Convert CGPA to GPA or percentage formats for various grading systems.</p>
                        <button class="btn use-tool" data-tool="cgpa-converter">Use Tool</button>
                    </div>
                </div>

                <!-- Grade to Percentage Converter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-exchange-alt"></i>
                        <h3>Grade to Percentage Converter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Change letter grades into percentage equivalents based on your grading system.</p>
                        <button class="btn use-tool" data-tool="grade-converter">Use Tool</button>
                    </div>
                </div>

                <!-- Unit Converter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-ruler-combined"></i>
                        <h3>Unit Converter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Convert between units like cm-inch, kg-lb, °C-°F and many more.</p>
                        <button class="btn use-tool" data-tool="unit-converter">Use Tool</button>
                    </div>
                </div>

                <!-- Currency Converter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-money-bill-wave"></i>
                        <h3>Currency Converter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Convert currencies for students studying abroad or making international transactions.</p>
                        <button class="btn use-tool" data-tool="currency-converter">Use Tool</button>
                    </div>
                </div>

                <!-- Number System Converter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-superscript"></i>
                        <h3>Number System Converter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Convert numbers between binary, decimal, hexadecimal, and octal systems.</p>
                        <button class="btn use-tool" data-tool="number-converter">Use Tool</button>
                    </div>
                </div>

                <!-- Language Transliteration Converter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-language"></i>
                        <h3>Language Transliteration Converter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Convert text between English, Hindi, and regional scripts with accurate transliteration.</p>
                        <button class="btn use-tool" data-tool="language-converter">Use Tool</button>
                    </div>
                </div>

                <!-- File Converters -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-file-contract"></i>
                        <h3>File Converters</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Convert PDFs into Word, PPT, or images and vice versa while preserving formatting.</p>
                        <button class="btn use-tool" data-tool="file-converter">Use Tool</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Calculators Section -->
        <section id="calculators">
            <h2 class="section-title">Calculators</h2>
            <div class="tools-grid">
                <!-- GPA/CGPA Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-calculator"></i>
                        <h3>GPA/CGPA Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Calculate GPA or CGPA from your grades with customizable credit systems.</p>
                        <button class="btn use-tool" data-tool="gpa-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Weighted Grade Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-balance-scale"></i>
                        <h3>Weighted Grade Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Calculate weighted grades across subjects based on their credit values.</p>
                        <button class="btn use-tool" data-tool="weighted-grade-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Final Exam Percentage Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-chart-line"></i>
                        <h3>Final Exam Percentage Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Find final exam percentage from scores with different weighting systems.</p>
                        <button class="btn use-tool" data-tool="final-exam-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Cut-off Marks Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-cut"></i>
                        <h3>Cut-off Marks Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Calculate admission cut-off marks for various colleges and universities.</p>
                        <button class="btn use-tool" data-tool="cutoff-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Attendance Percentage Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-user-check"></i>
                        <h3>Attendance Percentage Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Calculate attendance percentage from classes attended and missed.</p>
                        <button class="btn use-tool" data-tool="attendance-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Algebra Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-square-root-alt"></i>
                        <h3>Algebra Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Solve algebraic equations and expressions with step-by-step solutions.</p>
                        <button class="btn use-tool" data-tool="algebra-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Trigonometry Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-project-diagram"></i>
                        <h3>Trigonometry Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Calculate trigonometric values and identities with visual representations.</p>
                        <button class="btn use-tool" data-tool="trigonometry-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Geometry Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-shapes"></i>
                        <h3>Geometry Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Calculate area, perimeter, and volume for various geometric shapes.</p>
                        <button class="btn use-tool" data-tool="geometry-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Probability & Statistics Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-chart-bar"></i>
                        <h3>Probability & Statistics Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Perform mean, median, mode, and probability calculations for data sets.</p>
                        <button class="btn use-tool" data-tool="stats-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Physics Formula Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-atom"></i>
                        <h3>Physics Formula Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Calculate physics equations like force, energy, velocity, and more.</p>
                        <button class="btn use-tool" data-tool="physics-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Chemistry Molarity/Normality Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-vial"></i>
                        <h3>Chemistry Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Solve chemistry problems like molarity, normality, and concentration calculations.</p>
                        <button class="btn use-tool" data-tool="chemistry-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- JEE Rank Predictor -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-chart-pie"></i>
                        <h3>JEE Rank Predictor</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Predict JEE ranks based on exam scores using historical data and algorithms.</p>
                        <button class="btn use-tool" data-tool="jee-predictor">Use Tool</button>
                    </div>
                </div>

                <!-- NEET Rank Predictor -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-stethoscope"></i>
                        <h3>NEET Rank Predictor</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Predict NEET ranks based on exam scores to help with college selection.</p>
                        <button class="btn use-tool" data-tool="neet-predictor">Use Tool</button>
                    </div>
                </div>

                <!-- GATE Score/Rank Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-cogs"></i>
                        <h3>GATE Score/Rank Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Convert GATE exam scores to ranks and predict admission chances.</p>
                        <button class="btn use-tool" data-tool="gate-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- UPSC Age Eligibility Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-user-tie"></i>
                        <h3>UPSC Age Eligibility Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Check age eligibility for UPSC exams based on category and educational qualifications.</p>
                        <button class="btn use-tool" data-tool="upsc-calculator">Use Tool</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Generators Section -->
        <section id="generators">
            <h2 class="section-title">Generators</h2>
            <div class="tools-grid">
                <!-- Quiz/MCQ Generator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-question-circle"></i>
                        <h3>Quiz/MCQ Generator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Generate practice quizzes or MCQs from your study material or topics.</p>
                        <button class="btn use-tool" data-tool="quiz-generator">Use Tool</button>
                    </div>
                </div>

                <!-- Flashcard Generator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-sticky-note"></i>
                        <h3>Flashcard Generator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Create digital flashcards for efficient studying and memorization.</p>
                        <button class="btn use-tool" data-tool="flashcard-generator">Use Tool</button>
                    </div>
                </div>

                <!-- Essay/Paragraph Generator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-pen-fancy"></i>
                        <h3>Essay/Paragraph Generator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Generate essays or paragraphs using AI based on your topic and requirements.</p>
                        <button class="btn use-tool" data-tool="essay-generator">Use Tool</button>
                    </div>
                </div>

                <!-- Study Plan/Timetable Generator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-calendar-alt"></i>
                        <h3>Study Plan Generator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Generate a custom study timetable based on your subjects and available time.</p>
                        <button class="btn use-tool" data-tool="timetable-generator">Use Tool</button>
                    </div>
                </div>

                <!-- Citation/Reference Generator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-quote-right"></i>
                        <h3>Citation/Reference Generator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Generate citations in APA, MLA, Chicago, or other academic styles.</p>
                        <button class="btn use-tool" data-tool="citation-generator">Use Tool</button>
                    </div>
                </div>

                <!-- Bibliography Generator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-book"></i>
                        <h3>Bibliography Generator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Generate complete bibliographies from your sources in various citation styles.</p>
                        <button class="btn use-tool" data-tool="bibliography-generator">Use Tool</button>
                    </div>
                </div>

                <!-- Flowchart Generator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-project-diagram"></i>
                        <h3>Flowchart Generator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Generate flowcharts for projects, presentations, or process documentation.</p>
                        <button class="btn use-tool" data-tool="flowchart-generator">Use Tool</button>
                    </div>
                </div>

                <!-- LaTeX Equation Generator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-square-root-alt"></i>
                        <h3>LaTeX Equation Generator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Generate LaTeX equations for academic papers and technical documents.</p>
                        <button class="btn use-tool" data-tool="latex-generator">Use Tool</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Trackers Section -->
        <section id="trackers">
            <h2 class="section-title">Trackers</h2>
            <div class="tools-grid">
                <!-- Attendance Tracker -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-user-check"></i>
                        <h3>Attendance Tracker</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Track your attendance to ensure you meet the 75% requirement for exams.</p>
                        <button class="btn use-tool" data-tool="attendance-tracker">Use Tool</button>
                    </div>
                </div>

                <!-- Study Hours Tracker -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-clock"></i>
                        <h3>Study Hours Tracker</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Track study hours daily or weekly to maintain consistent study habits.</p>
                        <button class="btn use-tool" data-tool="study-tracker">Use Tool</button>
                    </div>
                </div>

                <!-- Exam Countdown Timer -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-hourglass-half"></i>
                        <h3>Exam Countdown Timer</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Countdown timer for upcoming exams to help with preparation planning.</p>
                        <button class="btn use-tool" data-tool="countdown-timer">Use Tool</button>
                    </div>
                </div>

                <!-- Backlog Subject Tracker -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-tasks"></i>
                        <h3>Backlog Subject Tracker</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Track pending backlog subjects and plan your preparation strategy.</p>
                        <button class="btn use-tool" data-tool="backlog-tracker">Use Tool</button>
                    </div>
                </div>

                <!-- Pomodoro Study Timer -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-hourglass-start"></i>
                        <h3>Pomodoro Study Timer</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Use the Pomodoro technique timer for focused study sessions with breaks.</p>
                        <button class="btn use-tool" data-tool="pomodoro-timer">Use Tool</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Document Tools Section -->
        <section id="document-tools">
            <h2 class="section-title">Document Tools</h2>
            <div class="tools-grid">
                <!-- Word Counter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-font"></i>
                        <h3>Word Counter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Count words in assignments or essays to meet specific requirements.</p>
                        <button class="btn use-tool" data-tool="word-counter">Use Tool</button>
                    </div>
                </div>

                <!-- Character Counter -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-text-width"></i>
                        <h3>Character Counter</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Count characters in texts or essays for applications with character limits.</p>
                        <button class="btn use-tool" data-tool="character-counter">Use Tool</button>
                    </div>
                </div>

                <!-- Reading Time Calculator -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-book-reader"></i>
                        <h3>Reading Time Calculator</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Estimate reading time from text length to plan your study sessions.</p>
                        <button class="btn use-tool" data-tool="reading-time-calculator">Use Tool</button>
                    </div>
                </div>

                <!-- Plagiarism Checker -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-search"></i>
                        <h3>Plagiarism Checker</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Check documents for plagiarism to ensure academic integrity.</p>
                        <button class="btn use-tool" data-tool="plagiarism-checker">Use Tool</button>
                    </div>
                </div>

                <!-- PDF Tools -->
                <div class="tool-card">
                    <div class="tool-card-header">
                        <i class="fas fa-file-pdf"></i>
                        <h3>PDF Tools</h3>
                    </div>
                    <div class="tool-card-body">
                        <p>Manage PDFs by merging, splitting, or annotating for better organization.</p>
                        <button class="btn use-tool" data-tool="pdf-tools">Use Tool</button>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>EduCalc Hub</h3>
                    <p>Your all-in-one platform for academic tools to make student life easier and more productive.</p>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#converters">Converters</a></li>
                        <li><a href="#calculators">Calculators</a></li>
                        <li><a href="#generators">Generators</a></li>
                        <li><a href="#trackers">Trackers</a></li>
                        <li><a href="#document-tools">Document Tools</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Support</h3>
                    <ul>
                        <li><a href="#">Help Center</a></li>
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Contact Us</a></li>
                        <li><a href="#">Feedback</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Connect With Us</h3>
                    <ul>
                        <li><a href="#"><i class="fab fa-facebook"></i> Facebook</a></li>
                        <li><a href="#"><i class="fab fa-twitter"></i> Twitter</a></li>
                        <li><a href="#"><i class="fab fa-instagram"></i> Instagram</a></li>
                        <li><a href="#"><i class="fab fa-linkedin"></i> LinkedIn</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 EduCalc Hub. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Tool Modal -->
    <div class="modal" id="toolModal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <h2 id="modalTitle">Tool Interface</h2>
            <div class="tool-interface" id="toolInterface">
                <!-- Tool interface will be loaded here -->
            </div>
        </div>
    </div>

    <script>
        // Modal functionality
        const modal = document.getElementById('toolModal');
        const modalTitle = document.getElementById('modalTitle');
        const toolInterface = document.getElementById('toolInterface');
        const closeModal = document.querySelector('.close-modal');
        
        document.querySelectorAll('.use-tool').forEach(button => {
            button.addEventListener('click', function() {
                const tool = this.getAttribute('data-tool');
                openToolModal(tool);
            });
        });
        
        closeModal.addEventListener('click', function() {
            modal.style.display = 'none';
        });
        
        window.addEventListener('click', function(event) {
            if (event.target === modal) {
                modal.style.display = 'none';
            }
        });
        
        function openToolModal(tool) {
            // Set modal title based on tool
            modalTitle.textContent = document.querySelector(`[data-tool="${tool}"]`).closest('.tool-card').querySelector('h3').textContent;
            
            // Load appropriate tool interface
            switch(tool) {
                case 'percentage-converter':
                    toolInterface.innerHTML = `
                        <div class="input-group">
                            <label for="marks">Marks Obtained</label>
                            <input type="number" id="marks" placeholder="Enter marks">
                        </div>
                        <div class="input-group">
                            <label for="total">Total Marks</label>
                            <input type="number" id="total" placeholder="Enter total marks">
                        </div>
                        <button class="btn" onclick="calculatePercentage()">Calculate Percentage</button>
                        <div class="results" id="percentageResult"></div>
                    `;
                    break;
                    
                case 'gpa-calculator':
                    toolInterface.innerHTML = `
                        <div id="gpa-courses">
                            <div class="course">
                                <div class="input-group">
                                    <label>Course Name</label>
                                    <input type="text" placeholder="Course name">
                                </div>
                                <div class="input-group">
                                    <label>Credits</label>
                                    <input type="number" placeholder="Credits">
                                </div>
                                <div class="input-group">
                                    <label>Grade</label>
                                    <select>
                                        <option value="4">A (4.0)</option>
                                        <option value="3.7">A- (3.7)</option>
                                        <option value="3.3">B+ (3.3)</option>
                                        <option value="3">B (3.0)</option>
                                        <option value="2.7">B- (2.7)</option>
                                        <option value="2.3">C+ (2.3)</option>
                                        <option value="2">C (2.0)</option>
                                        <option value="1.7">C- (1.7)</option>
                                        <option value="1.3">D+ (1.3)</option>
                                        <option value="1">D (1.0)</option>
                                        <option value="0">F (0.0)</option>
                                    </select>
                                </div>
                            </div>
                        </div>
                        <button class="btn" onclick="addCourse()">Add Another Course</button>
                        <button class="btn" onclick="calculateGPA()">Calculate GPA</button>
                        <div class="results" id="gpaResult"></div>
                    `;
                    break;
                    
                // Add cases for other tools here
                default:
                    toolInterface.innerHTML = `
                        <p>This tool is coming soon! We're working hard to bring you this functionality.</p>
                        <p>In the meantime, check out our other available tools.</p>
                    `;
            }
            
            modal.style.display = 'block';
        }
        
        // Example tool functions
        function calculatePercentage() {
            const marks = parseFloat(document.getElementById('marks').value);
            const total = parseFloat(document.getElementById('total').value);
            
            if (isNaN(marks) || isNaN(total) || total === 0) {
                alert('Please enter valid values for marks and total');
                return;
            }
            
            const percentage = (marks / total) * 100;
            document.getElementById('percentageResult').innerHTML = `
                <h3>Result: ${percentage.toFixed(2)}%</h3>
                <p>You scored ${marks} out of ${total} marks.</p>
            `;
            document.getElementById('percentageResult').classList.add('show');
        }
        
        function addCourse() {
            const coursesDiv = document.getElementById('gpa-courses');
            const newCourse = document.createElement('div');
            newCourse.className = 'course';
            newCourse.innerHTML = `
                <hr>
                <div class="input-group">
                    <label>Course Name</label>
                    <input type="text" placeholder="Course name">
                </div>
                <div class="input-group">
                    <label>Credits</label>
                    <input type="number" placeholder="Credits">
                </div>
                <div class="input-group">
                    <label>Grade</label>
                    <select>
                        <option value="4">A (4.0)</option>
                        <option value="3.7">A- (3.7)</option>
                        <option value="3.3">B+ (3.3)</option>
                        <option value="3">B (3.0)</option>
                        <option value="2.7">B- (2.7)</option>
                        <option value="2.3">C+ (2.3)</option>
                        <option value="2">C (2.0)</option>
                        <option value="1.7">C- (1.7)</option>
                        <option value="1.3">D+ (1.3)</option>
                        <option value="1">D (1.0)</option>
                        <option value="0">F (0.0)</option>
                    </select>
                </div>
            `;
            coursesDiv.appendChild(newCourse);
        }
        
        function calculateGPA() {
            const courses = document.querySelectorAll('.course');
            let totalCredits = 0;
            let totalGradePoints = 0;
            
            courses.forEach(course => {
                const credits = parseFloat(course.querySelector('input[type="number"]').value) || 0;
                const grade = parseFloat(course.querySelector('select').value) || 0;
                
                totalCredits += credits;
                totalGradePoints += credits * grade;
            });
            
            if (totalCredits === 0) {
                alert('Please enter valid course information');
                return;
            }
            
            const gpa = totalGradePoints / totalCredits;
            document.getElementById('gpaResult').innerHTML = `
                <h3>Your GPA: ${gpa.toFixed(2)}</h3>
                <p>Based on ${courses.length} courses and ${totalCredits} total credits.</p>
            `;
            document.getElementById('gpaResult').classList.add('show');
        }
    </script>
</body>
</html>
