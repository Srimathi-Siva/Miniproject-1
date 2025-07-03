<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Portal - Find Your Dream Job</title>
    <style>
        /* Basic CSS for demonstration */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }
        .header {
            text-align: center;
            margin-bottom: 30px;
        }
        .search-section {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            margin-bottom: 30px;
            text-align: center;
        }
        .search-section input[type="text"] {
            width: 70%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-right: 10px;
            font-size: 16px;
        }
        .search-section button {
            padding: 12px 25px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .categories-section {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
        }
        .category-card {
            background-color: #e9f5ff;
            padding: 20px;
            border-radius: 8px;
            text-align: center;
            flex: 1;
            min-width: 150px;
            max-width: 200px;
            box-shadow: 0 1px 3px rgba(0,0,0,0.08);
            text-decoration: none;
            color: #333;
            transition: transform 0.2s;
        }
        .category-card:hover {
            transform: translateY(-5px);
        }
        .category-card h3 {
            margin-top: 0;
            font-size: 1.1em;
            color: #0056b3;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>Welcome to Our Job Portal</h1>
        <p>Your next career move starts here.</p>
    </div>

    <div class="search-section">
        <form action="/job-listings" method="GET">
            <input type="text" name="q" placeholder="Search for jobs (e.g., 'Software Engineer', 'Marketing Manager')">
            <button type="submit">Search</button>
        </form>
    </div>

    <div class="categories-section">
        <h2>Browse by Category</h2>
        <a href="/job-listings?category=it" class="category-card">
            <h3>IT & Software</h3>
            <p>1200+ Jobs</p>
        </a>
        <a href="/job-listings?category=marketing" class="category-card">
            <h3>Marketing</h3>
            <p>550+ Jobs</p>
        </a>
        <a href="/job-listings?category=finance" class="category-card">
            <h3>Finance</h3>
            <p>300+ Jobs</p>
        </a>
        <a href="/job-listings?category=healthcare" class="category-card">
            <h3>Healthcare</h3>
            <p>780+ Jobs</p>
        </a>
        <a href="/job-listings?category=education" class="category-card">
            <h3>Education</h3>
            <p>420+ Jobs</p>
        </a>
        <a href="/job-listings?category=sales" class="category-card">
            <h3>Sales</h3>
            <p>610+ Jobs</p>
        </a>
    </div>

    </body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Listings - Find Your Next Career | Job Portal</title>
    <style>
        /* Basic Reset & Body Styling */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f2f5;
            color: #333;
            line-height: 1.6;
        }

        .header {
            background-color: #007bff;
            color: white;
            padding: 20px 0;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            margin-bottom: 25px;
        }

        .header h1 {
            margin: 0;
            font-size: 2.5em;
        }

        .header p {
            margin: 5px 0 0;
            font-size: 1.1em;
            opacity: 0.9;
        }

        .container {
            max-width: 1300px;
            margin: 0px auto;
            padding: 0 20px;
            display: flex;
            gap: 25px;
            flex-wrap: wrap; /* Allows stacking on smaller screens */
            align-items: flex-start; /* Align items to the top */
        }

        /* Filter Section (Sidebar) */
        .filters-sidebar {
            flex: 0 0 280px; /* Fixed width for filters */
            background-color: #ffffff;
            padding: 25px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
            position: sticky; /* Makes filters stick while scrolling jobs */
            top: 20px; /* Distance from top when sticky */
            align-self: flex-start; /* Ensure it starts at the top */
        }

        .filters-sidebar h2 {
            color: #007bff;
            margin-top: 0;
            margin-bottom: 25px;
            font-size: 1.6em;
            border-bottom: 2px solid #e0f2ff;
            padding-bottom: 10px;
        }

        .filter-group {
            margin-bottom: 25px;
        }

        .filter-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: bold;
            color: #555;
            font-size: 1.05em;
        }

        .filter-group input[type="text"],
        .filter-group select {
            width: calc(100% - 20px); /* Adjust for padding */
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1em;
            margin-bottom: 10px;
        }

        .filter-group .checkbox-group label {
            font-weight: normal;
            display: flex;
            align-items: center;
            margin-bottom: 8px;
            cursor: pointer;
        }

        .filter-group .checkbox-group input[type="checkbox"] {
            margin-right: 8px;
            transform: scale(1.1);
        }

        .filter-group button {
            width: 100%;
            padding: 12px;
            background-color: #28a745; /* Green for apply */
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1.1em;
            transition: background-color 0.3s ease;
        }

        .filter-group button:hover {
            background-color: #218838;
        }

        /* Main Job Listings Area */
        .job-listings-main {
            flex: 1; /* Takes up remaining space */
            min-width: 600px; /* Ensures it doesn't get too narrow */
        }

        .job-listings-main h2 {
            color: #2c3e50;
            margin-top: 0;
            margin-bottom: 25px;
            font-size: 2em;
            border-bottom: 2px solid #eee;
            padding-bottom: 10px;
        }

        /* Job Card Styling (List View) */
        .job-list {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        /* If you want a Grid View:
        .job-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 20px;
        }
        */

        .job-card {
            background-color: #ffffff;
            padding: 25px;
            border-radius: 8px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.06);
            border-left: 6px solid #007bff; /* Accent border */
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .job-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 18px rgba(0, 0, 0, 0.1);
        }

        .job-card h3 {
            margin-top: 0;
            margin-bottom: 10px;
            color: #2c3e50;
            font-size: 1.7em;
        }

        .job-card .company-location {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 12px;
            font-size: 1.1em;
            color: #555;
        }

        .job-card .company-location span {
            display: flex;
            align-items: center;
        }

        .job-card .company-location span strong {
            margin-left: 5px; /* Space for icon if using */
        }

        .job-card .description {
            color: #666;
            font-size: 1em;
            margin-bottom: 15px;
            overflow: hidden;
            text-overflow: ellipsis;
            display: -webkit-box;
            -webkit-line-clamp: 3; /* Show max 3 lines */
            -webkit-box-orient: vertical;
        }

        .job-card .tags {
            margin-bottom: 15px;
        }

        .job-card .tag {
            display: inline-block;
            background-color: #e0f2ff;
            color: #007bff;
            padding: 6px 12px;
            border-radius: 20px;
            font-size: 0.85em;
            margin-right: 8px;
            margin-bottom: 8px;
            font-weight: 500;
        }

        .job-card .footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-top: 1px solid #eee;
            padding-top: 15px;
            margin-top: 15px;
        }

        .job-card .posted-date {
            font-size: 0.9em;
            color: #888;
        }

        .job-card .actions a {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s ease;
        }

        .job-card .actions a:hover {
            background-color: #0056b3;
        }

        /* Pagination */
        .pagination {
            display: flex;
            justify-content: center;
            margin-top: 30px;
            padding: 20px 0;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }

        .pagination a {
            text-decoration: none;
            color: #007bff;
            padding: 10px 15px;
            margin: 0 5px;
            border: 1px solid #ddd;
            border-radius: 5px;
            transition: background-color 0.3s, color 0.3s;
        }

        .pagination a.active,
        .pagination a:hover {
            background-color: #007bff;
            color: white;
            border-color: #007bff;
        }

        /* Responsive Adjustments */
        @media (max-width: 992px) {
            .container {
                flex-direction: column;
                padding: 0 15px;
            }
            .filters-sidebar {
                position: static; /* Remove sticky on smaller screens */
                width: 100%;
                flex: none;
                margin-bottom: 20px;
            }
            .job-listings-main {
                min-width: unset;
                width: 100%;
            }
            .job-card {
                padding: 20px;
            }
            .job-card h3 {
                font-size: 1.5em;
            }
            .job-card .company-location {
                flex-direction: column;
                align-items: flex-start;
                gap: 5px;
            }
        }

        @media (max-width: 600px) {
            .header h1 {
                font-size: 2em;
            }
            .filters-sidebar, .job-card, .pagination {
                padding: 15px;
            }
            .job-card .footer {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }
            .job-card .actions {
                width: 100%;
                text-align: center;
            }
            .job-card .actions a {
                display: block;
                width: 100%;
                box-sizing: border-box;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <h1>Find Your Perfect Job</h1>
        <p>Explore thousands of opportunities from top companies.</p>
    </header>

    <div class="container">
        <aside class="filters-sidebar">
            <h2>Filter Jobs</h2>
            <form id="jobFiltersForm">
                <div class="filter-group">
                    <label for="keywords">Keywords</label>
                    <input type="text" id="keywords" placeholder="e.g., 'Software Engineer', 'Marketing'">
                </div>

                <div class="filter-group">
                    <label for="location">Location</label>
                    <input type="text" id="location" placeholder="e.g., 'Bengaluru', 'Remote'">
                </div>

                <div class="filter-group">
                    <label for="jobType">Job Type</label>
                    <select id="jobType">
                        <option value="">All Types</option>
                        <option value="full-time">Full-time</option>
                        <option value="part-time">Part-time</option>
                        <option value="contract">Contract</option>
                        <option value="freelance">Freelance</option>
                        <option value="internship">Internship</option>
                    </select>
                </div>

                <div class="filter-group">
                    <label for="experience">Experience Level</label>
                    <select id="experience">
                        <option value="">Any Level</option>
                        <option value="entry">Entry Level</option>
                        <option value="mid">Mid-Senior Level</option>
                        <option value="senior">Director</option>
                        <option value="executive">Executive</option>
                    </select>
                </div>

                <div class="filter-group">
                    <label>Salary Range (Annual)</label>
                    <select id="salaryRange">
                        <option value="">Any Salary</option>
                        <option value="0-3">₹0 - ₹3 Lacs</option>
                        <option value="3-6">₹3 - ₹6 Lacs</option>
                        <option value="6-10">₹6 - ₹10 Lacs</option>
                        <option value="10-15">₹10 - ₹15 Lacs</option>
                        <option value="15-25">₹15 - ₹25 Lacs</option>
                        <option value="25+">₹25 Lacs +</option>
                    </select>
                </div>

                <div class="filter-group">
                    <button type="submit">Apply Filters</button>
                </div>
            </form>
        </aside>

        <main class="job-listings-main">
            <h2>Showing 1500+ Jobs</h2>
            <div class="job-list" id="jobListings">
                <div class="job-card">
                    <h3>Frontend Developer (React.js)</h3>
                    <div class="company-location">
                        <span><strong>Tech Solutions Pvt. Ltd.</strong></span>
                        <span>Chennai, Tamil Nadu</span>
                        <span>Full-time</span>
                    </div>
                    <p class="description">
                        We are looking for a skilled Frontend Developer with strong expertise in React.js to join our dynamic team. You will be responsible for developing and implementing user interface components using React.js concepts and workflows such as Redux, Webpack, and Babel.
                    </p>
                    <div class="tags">
                        <span class="tag">React.js</span>
                        <span class="tag">JavaScript</span>
                        <span class="tag">HTML5</span>
                        <span class="tag">CSS3</span>
                        <span class="tag">UI/UX</span>
                    </div>
                    <div class="footer">
                        <span class="posted-date">Posted 2 days ago</span>
                        <div class="actions">
                            <a href="/job-detail/frontend-react-123">View Details</a>
                        </div>
                    </div>
                </div>

                <div class="job-card">
                    <h3>Senior Data Scientist</h3>
                    <div class="company-location">
                        <span><strong>InnovateAI Labs</strong></span>
                        <span>Bengaluru, Karnataka (Hybrid)</span>
                        <span>Full-time</span>
                    </div>
                    <p class="description">
                        Seeking a Senior Data Scientist to lead our data analysis initiatives. The ideal candidate will have strong experience in machine learning, statistical modeling, and big data technologies (Spark, Hadoop). Proficiency in Python or R is required.
                    </p>
                    <div class="tags">
                        <span class="tag">Python</span>
                        <span class="tag">Machine Learning</span>
                        <span class="tag">SQL</span>
                        <span class="tag">Big Data</span>
                    </div>
                    <div class="footer">
                        <span class="posted-date">Posted 5 days ago</span>
                        <div class="actions">
                            <a href="/job-detail/data-scientist-456">View Details</a>
                        </div>
                    </div>
                </div>

                <div class="job-card">
                    <h3>Marketing Manager</h3>
                    <div class="company-location">
                        <span><strong>Brand Builders India</strong></span>
                        <span>Mumbai, Maharashtra</span>
                        <span>Full-time</span>
                    </div>
                    <p class="description">
                        We need an experienced Marketing Manager to develop and execute comprehensive marketing strategies. Responsibilities include market research, campaign management, digital marketing, and team leadership.
                    </p>
                    <div class="tags">
                        <span class="tag">Digital Marketing</span>
                        <span class="tag">SEO/SEM</span>
                        <span class="tag">Content Marketing</span>
                        <span class="tag">Brand Management</span>
                    </div>
                    <div class="footer">
                        <span class="posted-date">Posted 1 week ago</span>
                        <div class="actions">
                            <a href="/job-detail/marketing-manager-789">View Details</a>
                        </div>
                    </div>
                </div>

                <div class="job-card">
                    <h3>UI/UX Designer (Entry Level)</h3>
                    <div class="company-location">
                        <span><strong>Creative Sparks Design</strong></span>
                        <span>Pune, Maharashtra</span>
                        <span>Full-time</span>
                    </div>
                    <p class="description">
                        An exciting opportunity for a passionate UI/UX Designer to contribute to innovative digital products. You'll work on wireframes, prototypes, user flows, and visual designs. Fresh graduates with strong portfolios are encouraged to apply.
                    </p>
                    <div class="tags">
                        <span class="tag">UI/UX</span>
                        <span class="tag">Figma</span>
                        <span class="tag">Adobe XD</span>
                        <span class="tag">Prototyping</span>
                    </div>
                    <div class="footer">
                        <span class="posted-date">Posted 3 days ago</span>
                        <div class="actions">
                            <a href="/job-detail/ui-ux-designer-012">View Details</a>
                        </div>
                    </div>
                </div>

                </div>

            <div class="pagination">
                <a href="#">&laquo; Previous</a>
                <a href="#" class="active">1</a>
                <a href="#">2</a>
                <a href="#">3</a>
                <a href="#">4</a>
                <a href="#">5</a>
                <a href="#">Next &raquo;</a>
            </div>
        </main>
    </div>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Job Detail - Frontend Developer</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">

  
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">

  
  <style>
    body {
      background: linear-gradient(to right, #e3f2fd, #fffafc);
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      padding: 0;
    }

    .job-container {
      max-width: 960px;
      margin: 50px auto;
      background-color: #ffffff;
      padding: 40px;
      border-radius: 16px;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
      animation: fadeInUp 1s ease-in-out;
    }

    @keyframes fadeInUp {
      0% { opacity: 0; transform: translateY(50px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    .company-name {
      font-size: 28px;
      font-weight: bold;
      color: #0d6efd;
      margin-bottom: 15px;
    }

    h3 {
      font-weight: 600;
      color: #2c3e50;
    }

    .info-row p {
      margin-bottom: 6px;
    }

    .section-title {
      font-size: 20px;
      font-weight: 600;
      margin-top: 30px;
      padding: 6px 12px;
      border-left: 6px solid;
      background-color: #f8f9fa;
      border-radius: 5px;
    }

    .about { border-color: #0d6efd; color: #0d6efd; }
    .role { border-color: #dc3545; color: #dc3545; }
    .responsibilities { border-color: #20c997; color: #20c997; }
    .skills { border-color: #6610f2; color: #6610f2; }
    .preferred { border-color: #6c757d; color: #6c757d; }
    .apply { border-color: #198754; color: #198754; }

    .badge-skill {
      font-size: 14px;
      padding: 6px 12px;
      border-radius: 20px;
      display: inline-block;
      margin: 6px 5px 0 0;
      transition: transform 0.3s;
    }

    .badge-skill:hover {
      transform: scale(1.1);
    }


    .bg-blue { background-color: #cce5ff; color: #004085; }
    .bg-red { background-color: #f8d7da; color: #721c24; }
    .bg-green { background-color: #d4edda; color: #155724; }
    .bg-teal { background-color: #d1f5f0; color: #0f766e; }
    .bg-gray { background-color: #e2e3e5; color: #383d41; }
    .bg-purple { background-color: #e6d4ff; color: #4b0082; }

    .apply-button {
      margin-top: 40px;
      padding: 12px 30px;
      font-size: 16px;
      background-color: #0d6efd;
      border: none;
      transition: all 0.3s ease;
    }

    .apply-button:hover {
      background-color: #084298;
      transform: scale(1.05);
    }

    hr {
      opacity: 0.15;
    }
  </style>
</head>
<body>

<div class="container job-container">
  <div class="company-name">TechNova Solutions Pvt. Ltd.</div>
  <h3 class="mb-3">Frontend Developer</h3>

  <div class="row info-row">
    <div class="col-md-6">
      <p><strong>Location:</strong> Chennai, Tamil Nadu (Hybrid)</p>
      <p><strong>Type:</strong> Full-Time</p>
      <p><strong>Experience:</strong> 0–2 Years</p>
    </div>
    <div class="col-md-6">
      <p><strong>Salary:</strong> ₹4 LPA – ₹6 LPA</p>
      <p><strong>Education:</strong> B.E/B.Tech – CSE, IT or Related</p>
      <p><strong>Posted:</strong> July 3, 2025</p>
    </div>
  </div>

  <hr>

  <div class="section-title about">About the Company</div>
  <p>
    TechNova Solutions is a dynamic tech company specializing in web development, cloud platforms, and AI-driven software. We create modern digital experiences for global clients with innovation at our core.
  </p>

  <div class="section-title role">Role Overview</div>
  <p>
    The Frontend Developer will be responsible for building intuitive, pixel-perfect, and user-friendly web interfaces. You’ll work closely with our design and backend team to bring ideas to life.
  </p>

  <div class="section-title responsibilities">Key Responsibilities</div>
  <ul>
    <li>Convert UI/UX designs to responsive HTML/CSS/JS code.</li>
    <li>Ensure browser compatibility and mobile responsiveness.</li>
    <li>Collaborate with designers and backend developers.</li>
    <li>Maintain code versioning using Git.</li>
    <li>Optimize site speed and performance.</li>
  </ul>

  <div class="section-title skills">Required Skills</div>
  <div>
    <span class="badge-skill bg-blue">HTML5</span>
    <span class="badge-skill bg-red">CSS3</span>
    <span class="badge-skill bg-green">Bootstrap</span>
    <span class="badge-skill bg-teal">JavaScript</span>
    <span class="badge-skill bg-purple">Git</span>
    <span class="badge-skill bg-gray">Responsive Design</span>
  </div>

  <div class="section-title preferred">Preferred Qualifications</div>
  <ul>
    <li>Knowledge of React or Vue.js.</li>
    <li>Experience with Figma or Adobe XD.</li>
    <li>Basic understanding of REST APIs.</li>
  </ul>

  <div class="section-title apply">How to Apply</div>
  <p>
    To apply, click the button below and fill out the form. Ensure you upload your resume in PDF format. We’ll get in touch with shortlisted candidates within 7 working days.
  </p>

 <a href="apllication.html" class="btn apply-button">Apply Now</a>

</div>



</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Dashboard - Job Portal</title>
    <style>
        /* Basic Reset & Body Styling */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f2f5;
            color: #333;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 20px;
            background-color: #ffffff;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08);
            display: flex;
            gap: 25px;
            flex-wrap: wrap; /* Allows wrapping on smaller screens */
        }

        /* Sidebar Navigation (Optional, but good for dashboards) */
        .sidebar {
            flex: 0 0 220px; /* Fixed width sidebar */
            background-color: #fdfdfd;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
            align-self: flex-start; /* Stick to the top */
        }

        .sidebar h2 {
            color: #007bff;
            margin-top: 0;
            margin-bottom: 25px;
            font-size: 1.5em;
        }

        .sidebar ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .sidebar ul li {
            margin-bottom: 15px;
        }

        .sidebar ul li a {
            text-decoration: none;
            color: #555;
            display: block;
            padding: 10px 15px;
            border-radius: 5px;
            transition: background-color 0.3s, color 0.3s;
            font-weight: 500;
        }

        .sidebar ul li a:hover,
        .sidebar ul li a.active {
            background-color: #e0f2ff;
            color: #007bff;
        }

        /* Main Content Area */
        .main-content {
            flex: 1; /* Takes up remaining space */
            min-width: 600px; /* Ensures it doesn't get too narrow */
        }

        .main-content section {
            background-color: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
            margin-bottom: 25px;
        }

        .main-content h1 {
            color: #2c3e50;
            margin-top: 0;
            margin-bottom: 30px;
            font-size: 2.2em;
            text-align: center;
        }

        .main-content h2 {
            color: #007bff;
            margin-top: 0;
            margin-bottom: 20px;
            border-bottom: 2px solid #e0f2ff;
            padding-bottom: 10px;
            font-size: 1.8em;
        }

        /* Job Card Styling */
        .job-list {
            display: grid;
            gap: 20px;
            /* Responsive grid: 1 column on small screens, 2 on larger */
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        }

        .job-card {
            background-color: #f9f9f9;
            border: 1px solid #eee;
            border-left: 5px solid #007bff; /* Accent color */
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 1px 5px rgba(0, 0, 0, 0.05);
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .job-card h3 {
            margin-top: 0;
            margin-bottom: 10px;
            color: #2c3e50;
            font-size: 1.4em;
        }

        .job-card p {
            margin-bottom: 8px;
            color: #666;
            font-size: 0.95em;
        }

        .job-card .company {
            font-weight: bold;
            color: #444;
        }

        .job-card .location {
            font-style: italic;
            color: #777;
        }

        .job-card .status {
            font-weight: bold;
            padding: 5px 10px;
            border-radius: 4px;
            display: inline-block;
            margin-top: 10px;
            font-size: 0.85em;
            text-transform: uppercase;
        }

        /* Status Specific Colors */
        .status.applied { background-color: #d4edda; color: #155724; } /* Green for applied */
        .status.pending { background-color: #fff3cd; color: #856404; } /* Yellow for pending */
        .status.interview { background-color: #cce5ff; color: #004085; } /* Blue for interview */
        .status.rejected { background-color: #f8d7da; color: #721c24; } /* Red for rejected */

        .job-card .date {
            font-size: 0.85em;
            color: #888;
            text-align: right;
            margin-top: auto; /* Pushes date to the bottom if content varies */
        }

        .job-card .actions {
            margin-top: 15px;
            display: flex;
            gap: 10px;
            justify-content: flex-end;
        }

        .job-card .actions a {
            background-color: #007bff;
            color: white;
            padding: 8px 15px;
            border-radius: 5px;
            text-decoration: none;
            font-size: 0.9em;
            transition: background-color 0.3s ease;
        }

        .job-card .actions a.view-details {
            background-color: #007bff;
        }

        .job-card .actions a.remove-saved {
            background-color: #dc3545; /* Red for remove */
        }

        .job-card .actions a:hover {
            opacity: 0.9;
        }

        /* Responsive Adjustments */
        @media (max-width: 900px) {
            .container {
                flex-direction: column;
                margin: 15px;
                padding: 15px;
            }
            .sidebar {
                flex: none; /* Remove fixed width */
                width: 100%; /* Take full width */
                margin-bottom: 20px;
            }
            .main-content {
                min-width: unset; /* Remove min-width for smaller screens */
                width: 100%;
            }
            .job-list {
                grid-template-columns: 1fr; /* Single column on smaller screens */
            }
            .main-content h1 {
                font-size: 1.8em;
                margin-bottom: 20px;
            }
            .main-content h2 {
                font-size: 1.5em;
            }
        }

        @media (max-width: 500px) {
            .container {
                padding: 10px;
            }
            .main-content section {
                padding: 20px;
            }
        }

    </style>
</head>
<body>
    <div class="container">
        <aside class="sidebar">
            <h2>Dashboard Menu</h2>
            <ul>
                <li><a href="#" class="active">My Dashboard</a></li>
                <li><a href="#saved-jobs">Saved Jobs</a></li>
                <li><a href="#applied-history">Applied History</a></li>
                <li><a href="#">Profile Settings</a></li>
                <li><a href="#">Notifications</a></li>
                <li><a href="#">Logout</a></li>
            </ul>
        </aside>

        <main class="main-content">
            <h1>Welcome, [User Name]!</h1>

            <section id="saved-jobs">
                <h2><i class="icon-bookmark"></i> My Saved Jobs</h2>
                <div class="job-list">
                    <div class="job-card">
                        <div>
                            <h3>Senior Software Engineer</h3>
                            <p class="company">Tech Innovators Inc.</p>
                            <p class="location">Bengaluru, India</p>
                        </div>
                        <div class="actions">
                            <a href="/job/details/123" class="view-details">View Details</a>
                            <a href="#" class="remove-saved">Remove</a>
                        </div>
                        <p class="date">Saved on: 2025-07-01</p>
                    </div>

                    <div class="job-card">
                        <div>
                            <h3>Marketing Specialist</h3>
                            <p class="company">Global Solutions Co.</p>
                            <p class="location">Chennai, India</p>
                        </div>
                        <div class="actions">
                            <a href="/job/details/124" class="view-details">View Details</a>
                            <a href="#" class="remove-saved">Remove</a>
                        </div>
                        <p class="date">Saved on: 2025-06-28</p>
                    </div>

                    <div class="job-card">
                        <div>
                            <h3>Data Scientist</h3>
                            <p class="company">Analytics Hub</p>
                            <p class="location">Pune, India</p>
                        </div>
                        <div class="actions">
                            <a href="/job/details/125" class="view-details">View Details</a>
                            <a href="#" class="remove-saved">Remove</a>
                        </div>
                        <p class="date">Saved on: 2025-06-25</p>
                    </div>

                    </div>
            </section>

            <section id="applied-history">
                <h2><i class="icon-history"></i> My Application History</h2>
                <div class="job-list">
                    <div class="job-card">
                        <div>
                            <h3>Full Stack Developer</h3>
                            <p class="company">Web Solutions Ltd.</p>
                            <p class="location">Hyderabad, India</p>
                        </div>
                        <p class="status applied">Applied</p>
                        <p class="date">Applied on: 2025-06-30</p>
                        <div class="actions">
                            <a href="/job/details/126" class="view-details">View Details</a>
                            </div>
                    </div>

                    <div class="job-card">
                        <div>
                            <h3>Product Manager</h3>
                            <p class="company">Innovate Corp.</p>
                            <p class="location">Mumbai, India</p>
                        </div>
                        <p class="status pending">Pending Review</p>
                        <p class="date">Applied on: 2025-06-20</p>
                        <div class="actions">
                            <a href="/job/details/127" class="view-details">View Details</a>
                        </div>
                    </div>

                    <div class="job-card">
                        <div>
                            <h3>Graphic Designer</h3>
                            <p class="company">Creative Minds Studio</p>
                            <p class="location">Delhi, India</p>
                        </div>
                        <p class="status interview">Interview Scheduled</p>
                        <p class="date">Applied on: 2025-06-10</p>
                        <div class="actions">
                            <a href="/job/details/128" class="view-details">View Details</a>
                        </div>
                    </div>

                    <div class="job-card">
                        <div>
                            <h3>Customer Support Executive</h3>
                            <p class="company">Service Pro</p>
                            <p class="location">Bengaluru, India</p>
                        </div>
                        <p class="status rejected">Rejected</p>
                        <p class="date">Applied on: 2025-05-25</p>
                        <div class="actions">
                            <a href="/job/details/129" class="view-details">View Details</a>
                        </div>
                    </div>
                    </div>
            </section>
        </main>
    </div>
</body>
</html>
