# B.-Tech
this is my privet project

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>B.Tech Exam Papers Repository</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
        }

        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1.5rem 0;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo i {
            font-size: 2.5rem;
            color: var(--light);
        }

        .logo h1 {
            font-size: 1.8rem;
        }

        .logo span {
            color: #f1c40f;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 20px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 600;
            padding: 8px 12px;
            border-radius: 4px;
            transition: background 0.3s;
        }

        nav a:hover, nav a.active {
            background: rgba(255, 255, 255, 0.2);
        }

        .hero {
            background: linear-gradient(rgba(44, 62, 80, 0.9), rgba(52, 152, 219, 0.9)), url('https://images.unsplash.com/photo-1523050854058-8df90110c9f1?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 4rem 0;
            text-align: center;
        }

        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
        }

        .search-box {
            max-width: 600px;
            margin: 0 auto;
            display: flex;
            gap: 10px;
        }

        .search-box input {
            flex: 1;
            padding: 15px;
            border: none;
            border-radius: 50px;
            font-size: 1rem;
        }

        .search-box button {
            background: var(--accent);
            color: white;
            border: none;
            border-radius: 50px;
            padding: 0 25px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s;
        }

        .search-box button:hover {
            background: #c0392b;
        }

        .main-content {
            padding: 3rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 2.5rem;
            color: var(--primary);
            position: relative;
        }

        .section-title:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: var(--secondary);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }

        .branches {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 3rem;
        }

        .branch-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }

        .branch-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .branch-icon {
            background: var(--secondary);
            color: white;
            padding: 20px;
            text-align: center;
            font-size: 2.5rem;
        }

        .branch-info {
            padding: 20px;
        }

        .branch-info h3 {
            margin-bottom: 10px;
            color: var(--primary);
        }

        .branch-info p {
            color: #666;
            font-size: 0.9rem;
        }

        .years {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 3rem;
        }

        .year-card {
            background: white;
            border-radius: 10px;
            padding: 25px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: all 0.3s;
            cursor: pointer;
        }

        .year-card:hover {
            background: var(--secondary);
            color: white;
            transform: scale(1.05);
        }

        .year-card h3 {
            font-size: 1.8rem;
            margin-bottom: 10px;
        }

        .papers-container {
            background: white;
            border-radius: 10px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
            margin-bottom: 3rem;
            display: none;
        }

        .papers-container.active {
            display: block;
            animation: fadeIn 0.5s;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .semester {
            margin-bottom: 30px;
        }

        .semester h3 {
            color: var(--primary);
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
            margin-bottom: 15px;
        }

        .paper-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 15px;
        }

        .paper-item {
            background: #f9f9f9;
            border-left: 4px solid var(--secondary);
            padding: 15px;
            border-radius: 5px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .paper-item:hover {
            background: #f0f7ff;
        }

        .paper-info h4 {
            margin-bottom: 5px;
            color: var(--dark);
        }

        .paper-info p {
            font-size: 0.9rem;
            color: #666;
        }

        .download-btn {
            background: var(--accent);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s;
        }

        .download-btn:hover {
            background: #c0392b;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 3rem;
        }

        .stat-card {
            background: white;
            padding: 25px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
        }

        .stat-card i {
            font-size: 2.5rem;
            color: var(--secondary);
            margin-bottom: 15px;
        }

        .stat-card h3 {
            font-size: 2rem;
            color: var(--primary);
            margin-bottom: 5px;
        }

        footer {
            background: var(--primary);
            color: white;
            padding: 3rem 0 1.5rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 20px;
            font-size: 1.3rem;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 10px;
        }

        .footer-section a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-section a:hover {
            color: var(--secondary);
        }

        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #aaa;
            font-size: 0.9rem;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                text-align: center;
                gap: 20px;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h2 {
                font-size: 2rem;
            }
            
            .search-box {
                flex-direction: column;
            }
            
            .search-box button {
                padding: 15px;
            }
            
            .branches, .years {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
            
            .mobile-menu-btn {
                display: block;
                position: absolute;
                top: 25px;
                right: 20px;
            }
            
            nav {
                width: 100%;
                display: none;
            }
            
            nav.active {
                display: block;
            }
            
            nav ul {
                flex-direction: column;
                margin-top: 20px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <i class="fas fa-graduation-cap"></i>
                    <h1>B.Tech <span>Exam Papers</span></h1>
                </div>
                <button class="mobile-menu-btn" id="mobileMenuBtn">
                    <i class="fas fa-bars"></i>
                </button>
                <nav id="mainNav">
                    <ul>
                        <li><a href="#" class="active">Home</a></li>
                        <li><a href="#branches">Branches</a></li>
                        <li><a href="#years">Years</a></li>
                        <li><a href="#papers">Papers</a></li>
                        <li><a href="#about">About</a></li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h2>B.Tech Exam Papers Repository</h2>
            <p>Access previous year question papers for all B.Tech branches and years. Prepare effectively with our comprehensive collection of exam papers from various universities.</p>
            <div class="search-box">
                <input type="text" id="searchInput" placeholder="Search for papers by subject, branch, or year...">
                <button id="searchBtn"><i class="fas fa-search"></i> Search</button>
            </div>
        </div>
    </section>

    <main class="main-content container">
        <section id="branches">
            <h2 class="section-title">Browse by Branch</h2>
            <div class="branches" id="branchContainer">
                <!-- Branches will be loaded by JavaScript -->
            </div>
        </section>

        <section id="years">
            <h2 class="section-title">Browse by Year</h2>
            <div class="years" id="yearContainer">
                <!-- Years will be loaded by JavaScript -->
            </div>
        </section>

        <section id="papers">
            <h2 class="section-title">Exam Papers</h2>
            <div class="papers-container" id="papersContainer">
                <!-- Papers will be loaded by JavaScript -->
            </div>
        </section>

        <section id="stats">
            <h2 class="section-title">Repository Statistics</h2>
            <div class="stats">
                <div class="stat-card">
                    <i class="fas fa-book-open"></i>
                    <h3 id="totalPapers">0</h3>
                    <p>Total Papers</p>
                </div>
                <div class="stat-card">
                    <i class="fas fa-university"></i>
                    <h3>8</h3>
                    <p>B.Tech Branches</p>
                </div>
                <div class="stat-card">
                    <i class="fas fa-calendar-alt"></i>
                    <h3>4</h3>
                    <p>Academic Years</p>
                </div>
                <div class="stat-card">
                    <i class="fas fa-download"></i>
                    <h3 id="totalDownloads">0</h3>
                    <p>Total Downloads</p>
                </div>
            </div>
        </section>
    </main>

    <footer id="about">
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>B.Tech Exam Papers</h3>
                    <p>A comprehensive repository of previous year question papers for B.Tech students across all branches and years.</p>
                </div>
                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#branches">Browse by Branch</a></li>
                        <li><a href="#years">Browse by Year</a></li>
                        <li><a href="#papers">All Papers</a></li>
                        <li><a href="#about">About Us</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Popular Branches</h3>
                    <ul>
                        <li><a href="#" data-branch="CSE">Computer Science</a></li>
                        <li><a href="#" data-branch="ECE">Electronics & Communication</a></li>
                        <li><a href="#" data-branch="ME">Mechanical Engineering</a></li>
                        <li><a href="#" data-branch="CE">Civil Engineering</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Contact Info</h3>
                    <p><i class="fas fa-envelope"></i> smithsaikia1@gmail.com</p>
                    <p><i class="fas fa-phone"></i> +91 7086362206</p>
                    <div class="social-icons" style="margin-top: 15px;">
                        <a href="#" style="color: white; margin-right: 10px;"><i class="fab fa-facebook"></i></a>
                        <a href="#" style="color: white; margin-right: 10px;"><i class="fab fa-twitter"></i></a>
                        <a href="#" style="color: white; margin-right: 10px;"><i class="fab fa-linkedin"></i></a>
                        <a href="#" style="color: white;"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; 2023 B.Tech Exam Papers Repository. All rights reserved.</p>
                <p>Disclaimer: This website is for educational purposes only. Papers are collected from various public sources.</p>
            </div>
        </div>
    </footer>

    <script>
        // Sample data for B.Tech branches
        const branches = [
            { id: "CSE", name: "Computer Science & Engineering", icon: "fas fa-laptop-code", papers: 245 },
            { id: "ECE", name: "Electronics & Communication Engineering", icon: "fas fa-microchip", papers: 198 },
            { id: "ME", name: "Mechanical Engineering", icon: "fas fa-cogs", papers: 187 },
            { id: "CE", name: "Civil Engineering", icon: "fas fa-hard-hat", papers: 165 },
            { id: "EE", name: "Electrical Engineering", icon: "fas fa-bolt", papers: 156 },
            { id: "IT", name: "Information Technology", icon: "fas fa-server", papers: 178 },
            { id: "CHE", name: "Chemical Engineering", icon: "fas fa-flask", papers: 134 },
            { id: "AE", name: "Automobile Engineering", icon: "fas fa-car", papers: 98 }
        ];

        // Years
        const years = [
            { id: 1, name: "First Year", papers: 320 },
            { id: 2, name: "Second Year", papers: 285 },
            { id: 3, name: "Third Year", papers: 310 },
            { id: 4, name: "Fourth Year", papers: 295 }
        ];

        // Sample papers data
        const papersData = {
            "CSE": {
                1: {
                    1: [
                        { name: "Engineering Mathematics-I", code: "MATH101", year: "2022", downloads: 1245 },
                        { name: "Engineering Physics", code: "PHYS101", year: "2022", downloads: 987 },
                        { name: "Programming in C", code: "CSE101", year: "2022", downloads: 1543 },
                        { name: "Engineering Graphics", code: "MECH101", year: "2022", downloads: 765 }
                    ],
                    2: [
                        { name: "Engineering Mathematics-II", code: "MATH102", year: "2022", downloads: 1123 },
                        { name: "Engineering Chemistry", code: "CHEM101", year: "2022", downloads: 876 },
                        { name: "Data Structures", code: "CSE102", year: "2022", downloads: 1765 },
                        { name: "Basic Electrical Engineering", code: "EEE101", year: "2022", downloads: 654 }
                    ]
                },
                2: {
                    1: [
                        { name: "Discrete Mathematics", code: "MATH201", year: "2022", downloads: 987 },
                        { name: "Digital Electronics", code: "CSE201", year: "2022", downloads: 1234 },
                        { name: "Object Oriented Programming", code: "CSE202", year: "2022", downloads: 1876 },
                        { name: "Engineering Mechanics", code: "MECH201", year: "2022", downloads: 765 }
                    ],
                    2: [
                        { name: "Probability & Statistics", code: "MATH202", year: "2022", downloads: 876 },
                        { name: "Computer Organization", code: "CSE203", year: "2022", downloads: 1098 },
                        { name: "Operating Systems", code: "CSE204", year: "2022", downloads: 1654 },
                        { name: "Database Management Systems", code: "CSE205", year: "2022", downloads: 1987 }
                    ]
                },
                3: {
                    1: [
                        { name: "Design & Analysis of Algorithms", code: "CSE301", year: "2022", downloads: 1432 },
                        { name: "Computer Networks", code: "CSE302", year: "2022", downloads: 1321 },
                        { name: "Software Engineering", code: "CSE303", year: "2022", downloads: 987 },
                        { name: "Theory of Computation", code: "CSE304", year: "2022", downloads: 876 }
                    ],
                    2: [
                        { name: "Artificial Intelligence", code: "CSE305", year: "2022", downloads: 1765 },
                        { name: "Compiler Design", code: "CSE306", year: "2022", downloads: 987 },
                        { name: "Machine Learning", code: "CSE307", year: "2022", downloads: 2109 },
                        { name: "Web Technologies", code: "CSE308", year: "2022", downloads: 1543 }
                    ]
                },
                4: {
                    1: [
                        { name: "Data Mining", code: "CSE401", year: "2022", downloads: 1234 },
                        { name: "Cloud Computing", code: "CSE402", year: "2022", downloads: 1432 },
                        { name: "Internet of Things", code: "CSE403", year: "2022", downloads: 1654 },
                        { name: "Cyber Security", code: "CSE404", year: "2022", downloads: 1321 }
                    ],
                    2: [
                        { name: "Big Data Analytics", code: "CSE405", year: "2022", downloads: 987 },
                        { name: "Blockchain Technology", code: "CSE406", year: "2022", downloads: 1765 },
                        { name: "Project Work", code: "CSE407", year: "2022", downloads: 876 },
                        { name: "Seminar", code: "CSE408", year: "2022", downloads: 654 }
                    ]
                }
            },
            "ECE": {
                1: {
                    1: [
                        { name: "Engineering Mathematics-I", code: "MATH101", year: "2022", downloads: 987 },
                        { name: "Engineering Physics", code: "PHYS101", year: "2022", downloads: 765 },
                        { name: "Basic Electronics", code: "ECE101", year: "2022", downloads: 1234 },
                        { name: "Engineering Graphics", code: "MECH101", year: "2022", downloads: 654 }
                    ],
                    2: [
                        { name: "Engineering Mathematics-II", code: "MATH102", year: "2022", downloads: 876 },
                        { name: "Engineering Chemistry", code: "CHEM101", year: "2022", downloads: 765 },
                        { name: "Circuit Theory", code: "ECE102", year: "2022", downloads: 1098 },
                        { name: "Basic Electrical Engineering", code: "EEE101", year: "2022", downloads: 987 }
                    ]
                }
            }
            
        };

        // Current selected branch and year
        let currentBranch = "CSE";
        let currentYear = 1;

        // DOM elements
        const branchContainer = document.getElementById('branchContainer');
        const yearContainer = document.getElementById('yearContainer');
        const papersContainer = document.getElementById('papersContainer');
        const searchInput = document.getElementById('searchInput');
        const searchBtn = document.getElementById('searchBtn');
        const totalPapersElement = document.getElementById('totalPapers');
        const totalDownloadsElement = document.getElementById('totalDownloads');
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const mainNav = document.getElementById('mainNav');

        // Initialize the page
        function initPage() {
            renderBranches();
            renderYears();
            showPapers(currentBranch, currentYear);
            updateStats();
            
            // Set up event listeners for footer branch links
            document.querySelectorAll('[data-branch]').forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault();
                    const branchId = this.getAttribute('data-branch');
                    selectBranch(branchId);
                    // Scroll to papers section
                    document.getElementById('papers').scrollIntoView({ behavior: 'smooth' });
                });
            });
        }

        // Render branches
        function renderBranches() {
            branchContainer.innerHTML = '';
            
            branches.forEach(branch => {
                const branchCard = document.createElement('div');
                branchCard.className = 'branch-card';
                branchCard.innerHTML = `
                    <div class="branch-icon">
                        <i class="${branch.icon}"></i>
                    </div>
                    <div class="branch-info">
                        <h3>${branch.name}</h3>
                        <p>${branch.papers} papers available</p>
                    </div>
                `;
                
                branchCard.addEventListener('click', () => {
                    selectBranch(branch.id);
                    // Scroll to papers section
                    document.getElementById('papers').scrollIntoView({ behavior: 'smooth' });
                });
                
                branchContainer.appendChild(branchCard);
            });
        }

        // Render years
        function renderYears() {
            yearContainer.innerHTML = '';
            
            years.forEach(year => {
                const yearCard = document.createElement('div');
                yearCard.className = 'year-card';
                yearCard.innerHTML = `
                    <h3>Year ${year.id}</h3>
                    <p>${year.name}</p>
                    <p>${year.papers} papers</p>
                `;
                
                yearCard.addEventListener('click', () => {
                    selectYear(year.id);
                    // Scroll to papers section
                    document.getElementById('papers').scrollIntoView({ behavior: 'smooth' });
                });
                
                yearContainer.appendChild(yearCard);
            });
        }

        // Show papers for selected branch and year
        function showPapers(branch, year) {
            if (!papersData[branch] || !papersData[branch][year]) {
                papersContainer.innerHTML = '<p>No papers available for this selection.</p>';
                papersContainer.classList.add('active');
                return;
            }
            
            const branchData = papersData[branch][year];
            let papersHTML = '';
            
            // Add branch and year header
            papersHTML += `<h2 style="margin-bottom: 20px; color: var(--primary);">${getBranchName(branch)} - Year ${year}</h2>`;
            
            // Loop through semesters
            for (const semester in branchData) {
                papersHTML += `
                    <div class="semester">
                        <h3>Semester ${semester}</h3>
                        <div class="paper-list">
                `;
                
                // Loop through papers in this semester
                branchData[semester].forEach(paper => {
                    papersHTML += `
                        <div class="paper-item">
                            <div class="paper-info">
                                <h4>${paper.name}</h4>
                                <p>Code: ${paper.code} | Year: ${paper.year} | Downloads: ${paper.downloads}</p>
                            </div>
                            <button class="download-btn" data-paper="${paper.code}">
                                <i class="fas fa-download"></i> Download
                            </button>
                        </div>
                    `;
                });
                
                papersHTML += `
                        </div>
                    </div>
                `;
            }
            
            papersContainer.innerHTML = papersHTML;
            papersContainer.classList.add('active');
            
            // Add event listeners to download buttons
            document.querySelectorAll('.download-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const paperCode = this.getAttribute('data-paper');
                    downloadPaper(paperCode);
                });
            });
        }

        // Select branch
        function selectBranch(branchId) {
            currentBranch = branchId;
            showPapers(currentBranch, currentYear);
            
            // Update active state in branch cards
            document.querySelectorAll('.branch-card').forEach(card => {
                card.classList.remove('active');
            });
        }

        // Select year
        function selectYear(yearId) {
            currentYear = yearId;
            showPapers(currentBranch, currentYear);
            
            // Update active state in year cards
            document.querySelectorAll('.year-card').forEach(card => {
                card.classList.remove('active');
            });
        }

        // Get branch name by ID
        function getBranchName(branchId) {
            const branch = branches.find(b => b.id === branchId);
            return branch ? branch.name : branchId;
        }

        // Download paper simulation
        function downloadPaper(paperCode) {
            // In a real app, this would trigger a file download
            alert(`Downloading paper: ${paperCode}.pdf\n\nIn a real application, this would start the file download.`);
            
            // Update download count in UI
            updateStats();
        }

        // Update statistics
        function updateStats() {
            // Calculate total papers
            let totalPapers = 0;
            let totalDownloads = 0;
            
            // Count papers and downloads from papersData
            for (const branch in papersData) {
                for (const year in papersData[branch]) {
                    for (const semester in papersData[branch][year]) {
                        totalPapers += papersData[branch][year][semester].length;
                        papersData[branch][year][semester].forEach(paper => {
                            totalDownloads += paper.downloads;
                        });
                    }
                }
            }
            
            // Update UI
            totalPapersElement.textContent = totalPapers;
            totalDownloadsElement.textContent = totalDownloads.toLocaleString();
        }

        // Search functionality
        function searchPapers() {
            const query = searchInput.value.toLowerCase().trim();
            
            if (!query) {
                // If search is empty, show current selection
                showPapers(currentBranch, currentYear);
                return;
            }
            
            // Search in papers
            let resultsHTML = '<h2 style="margin-bottom: 20px; color: var(--primary);">Search Results</h2>';
            let foundResults = false;
            
            for (const branch in papersData) {
                for (const year in papersData[branch]) {
                    for (const semester in papersData[branch][year]) {
                        const semesterPapers = papersData[branch][year][semester];
                        const matchingPapers = semesterPapers.filter(paper => 
                            paper.name.toLowerCase().includes(query) || 
                            paper.code.toLowerCase().includes(query)
                        );
                        
                        if (matchingPapers.length > 0) {
                            foundResults = true;
                            resultsHTML += `
                                <div class="semester">
                                    <h3>${getBranchName(branch)} - Year ${year}, Semester ${semester}</h3>
                                    <div class="paper-list">
                            `;
                            
                            matchingPapers.forEach(paper => {
                                resultsHTML += `
                                    <div class="paper-item">
                                        <div class="paper-info">
                                            <h4>${paper.name}</h4>
                                            <p>Code: ${paper.code} | Year: ${paper.year} | Downloads: ${paper.downloads}</p>
                                        </div>
                                        <button class="download-btn" data-paper="${paper.code}">
                                            <i class="fas fa-download"></i> Download
                                        </button>
                                    </div>
                                `;
                            });
                            
                            resultsHTML += `
                                    </div>
                                </div>
                            `;
                        }
                    }
                }
            }
            
            if (!foundResults) {
                resultsHTML = '<p>No papers found matching your search.</p>';
            }
            
            papersContainer.innerHTML = resultsHTML;
            papersContainer.classList.add('active');
            
            // Add event listeners to download buttons in search results
            document.querySelectorAll('.download-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const paperCode = this.getAttribute('data-paper');
                    downloadPaper(paperCode);
                });
            });
        }

        // Event Listeners
        searchBtn.addEventListener('click', searchPapers);
        searchInput.addEventListener('keyup', function(e) {
            if (e.key === 'Enter') {
                searchPapers();
            }
        });

        // Mobile menu toggle
        mobileMenuBtn.addEventListener('click', function() {
            mainNav.classList.toggle('active');
        });

        // Close mobile menu when clicking on a link
        document.querySelectorAll('nav a').forEach(link => {
            link.addEventListener('click', () => {
                if (window.innerWidth <= 768) {
                    mainNav.classList.remove('active');
                }
            });
        });

        // Initialize the page when DOM is loaded
        document.addEventListener('DOMContentLoaded', initPage);
    </script>
</body>
</html>
