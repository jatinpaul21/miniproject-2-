<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Data Management System</title>
    <link href="[fonts.googleapis.com](https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap)" rel="stylesheet">
    <link rel="stylesheet" href="[cdnjs.cloudflare.com](https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css)">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #4f46e5;
            --primary-dark: #4338ca;
            --primary-light: #818cf8;
            --secondary: #0ea5e9;
            --success: #10b981;
            --warning: #f59e0b;
            --danger: #ef4444;
            --dark: #1e293b;
            --gray: #64748b;
            --light: #f1f5f9;
            --white: #ffffff;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1);
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }

        /* Auth Pages */
        .auth-container {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            padding: 20px;
        }

        .auth-box {
            background: var(--white);
            border-radius: 20px;
            box-shadow: var(--shadow-lg);
            width: 100%;
            max-width: 450px;
            padding: 40px;
        }

        .auth-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .auth-header .logo {
            width: 70px;
            height: 70px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
        }

        .auth-header .logo i {
            font-size: 32px;
            color: var(--white);
        }

        .auth-header h1 {
            font-size: 24px;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 8px;
        }

        .auth-header p {
            color: var(--gray);
            font-size: 14px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--dark);
            font-size: 14px;
        }

        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 12px 16px;
            border: 2px solid var(--light);
            border-radius: 10px;
            font-size: 14px;
            transition: all 0.3s ease;
            font-family: inherit;
        }

        .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.1);
        }

        .btn {
            padding: 12px 24px;
            border: none;
            border-radius: 10px;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: var(--white);
            width: 100%;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(79, 70, 229, 0.4);
        }

        .btn-secondary {
            background: var(--light);
            color: var(--dark);
        }

        .btn-secondary:hover {
            background: #e2e8f0;
        }

        .btn-success {
            background: var(--success);
            color: var(--white);
        }

        .btn-danger {
            background: var(--danger);
            color: var(--white);
        }

        .btn-sm {
            padding: 8px 16px;
            font-size: 12px;
        }

        .auth-footer {
            text-align: center;
            margin-top: 24px;
            font-size: 14px;
            color: var(--gray);
        }

        .auth-footer a {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
        }

        .auth-footer a:hover {
            text-decoration: underline;
        }

        .tabs {
            display: flex;
            margin-bottom: 24px;
            background: var(--light);
            border-radius: 10px;
            padding: 4px;
        }

        .tab {
            flex: 1;
            padding: 12px;
            text-align: center;
            border: none;
            background: none;
            font-size: 14px;
            font-weight: 600;
            color: var(--gray);
            cursor: pointer;
            border-radius: 8px;
            transition: all 0.3s ease;
        }

        .tab.active {
            background: var(--white);
            color: var(--primary);
            box-shadow: var(--shadow);
        }

        /* Dashboard */
        .dashboard {
            display: none;
        }

        .dashboard.active {
            display: block;
        }

        .sidebar {
            position: fixed;
            left: 0;
            top: 0;
            width: 260px;
            height: 100vh;
            background: var(--white);
            box-shadow: var(--shadow);
            z-index: 100;
            transition: transform 0.3s ease;
        }

        .sidebar-header {
            padding: 24px;
            border-bottom: 1px solid var(--light);
        }

        .sidebar-header .logo-text {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .sidebar-header .logo-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .sidebar-header .logo-icon i {
            color: var(--white);
            font-size: 18px;
        }

        .sidebar-header h2 {
            font-size: 18px;
            font-weight: 700;
            color: var(--dark);
        }

        .sidebar-header span {
            font-size: 12px;
            color: var(--gray);
        }

        .sidebar-menu {
            padding: 20px 12px;
        }

        .menu-label {
            font-size: 11px;
            font-weight: 600;
            color: var(--gray);
            text-transform: uppercase;
            letter-spacing: 0.5px;
            padding: 0 12px;
            margin-bottom: 8px;
            margin-top: 20px;
        }

        .menu-label:first-child {
            margin-top: 0;
        }

        .menu-item {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 12px 16px;
            border-radius: 10px;
            color: var(--gray);
            text-decoration: none;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-bottom: 4px;
        }

        .menu-item:hover {
            background: var(--light);
            color: var(--dark);
        }

        .menu-item.active {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: var(--white);
        }

        .menu-item i {
            width: 20px;
            text-align: center;
        }

        .main-content {
            margin-left: 260px;
            min-height: 100vh;
        }

        .top-bar {
            background: var(--white);
            padding: 16px 30px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 50;
        }

        .top-bar h1 {
            font-size: 20px;
            font-weight: 700;
            color: var(--dark);
        }

        .user-info {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .user-avatar {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--white);
            font-weight: 600;
        }

        .user-details h4 {
            font-size: 14px;
            font-weight: 600;
            color: var(--dark);
        }

        .user-details span {
            font-size: 12px;
            color: var(--gray);
        }

        .logout-btn {
            background: none;
            border: none;
            color: var(--danger);
            cursor: pointer;
            padding: 8px;
            border-radius: 8px;
            transition: all 0.3s ease;
        }

        .logout-btn:hover {
            background: #fef2f2;
        }

        .content-area {
            padding: 30px;
        }

        .page-section {
            display: none;
        }

        .page-section.active {
            display: block;
        }

        /* Stats Cards */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 24px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: var(--white);
            border-radius: 16px;
            padding: 24px;
            box-shadow: var(--shadow);
        }

        .stat-card .stat-icon {
            width: 48px;
            height: 48px;
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 16px;
        }

        .stat-card .stat-icon.blue {
            background: rgba(79, 70, 229, 0.1);
            color: var(--primary);
        }

        .stat-card .stat-icon.green {
            background: rgba(16, 185, 129, 0.1);
            color: var(--success);
        }

        .stat-card .stat-icon.orange {
            background: rgba(245, 158, 11, 0.1);
            color: var(--warning);
        }

        .stat-card .stat-icon.red {
            background: rgba(239, 68, 68, 0.1);
            color: var(--danger);
        }

        .stat-card h3 {
            font-size: 28px;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 4px;
        }

        .stat-card p {
            font-size: 14px;
            color: var(--gray);
        }

        /* Cards */
        .card {
            background: var(--white);
            border-radius: 16px;
            box-shadow: var(--shadow);
            overflow: hidden;
        }

        .card-header {
            padding: 20px 24px;
            border-bottom: 1px solid var(--light);
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .card-header h3 {
            font-size: 16px;
            font-weight: 600;
            color: var(--dark);
        }

        .card-body {
            padding: 24px;
        }

        /* Tables */
        .table-responsive {
            overflow-x: auto;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 14px 16px;
            text-align: left;
            border-bottom: 1px solid var(--light);
        }

        th {
            background: var(--light);
            font-weight: 600;
            font-size: 13px;
            color: var(--gray);
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        td {
            font-size: 14px;
            color: var(--dark);
        }

        tr:hover {
            background: #fafafa;
        }

        .badge {
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 600;
        }

        .badge-success {
            background: rgba(16, 185, 129, 0.1);
            color: var(--success);
        }

        .badge-warning {
            background: rgba(245, 158, 11, 0.1);
            color: var(--warning);
        }

        .badge-danger {
            background: rgba(239, 68, 68, 0.1);
            color: var(--danger);
        }

        .badge-info {
            background: rgba(14, 165, 233, 0.1);
            color: var(--secondary);
        }

        /* Attendance */
        .attendance-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            gap: 12px;
        }

        .attendance-card {
            background: var(--light);
            border-radius: 12px;
            padding: 16px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }

        .attendance-card:hover {
            transform: translateY(-2px);
        }

        .attendance-card.present {
            background: rgba(16, 185, 129, 0.1);
            border-color: var(--success);
        }

        .attendance-card.absent {
            background: rgba(239, 68, 68, 0.1);
            border-color: var(--danger);
        }

        .attendance-card .student-name {
            font-weight: 600;
            color: var(--dark);
            margin-bottom: 4px;
        }

        .attendance-card .roll-no {
            font-size: 12px;
            color: var(--gray);
        }

        /* Holidays */
        .holiday-list {
            display: grid;
            gap: 12px;
        }

        .holiday-item {
            display: flex;
            align-items: center;
            gap: 16px;
            padding: 16px;
            background: var(--light);
            border-radius: 12px;
            transition: all 0.3s ease;
        }

        .holiday-item:hover {
            background: #e8edf5;
        }

        .holiday-date {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 12px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            color: var(--white);
        }

        .holiday-date .day {
            font-size: 20px;
            font-weight: 700;
        }

        .holiday-date .month {
            font-size: 11px;
            text-transform: uppercase;
        }

        .holiday-info h4 {
            font-weight: 600;
            color: var(--dark);
            margin-bottom: 4px;
        }

        .holiday-info p {
            font-size: 13px;
            color: var(--gray);
        }

        /* Fee Details */
        .fee-summary {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 24px;
        }

        .fee-card {
            background: var(--light);
            border-radius: 12px;
            padding: 20px;
            text-align: center;
        }

        .fee-card h4 {
            font-size: 13px;
            color: var(--gray);
            margin-bottom: 8px;
            text-transform: uppercase;
        }

        .fee-card .amount {
            font-size: 24px;
            font-weight: 700;
            color: var(--dark);
        }

        .fee-card .amount.paid {
            color: var(--success);
        }

        .fee-card .amount.pending {
            color: var(--danger);
        }

        /* Progress Bar */
        .progress-bar {
            height: 8px;
            background: var(--light);
            border-radius: 4px;
            overflow: hidden;
        }

        .progress-bar .progress {
            height: 100%;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 4px;
            transition: width 0.5s ease;
        }

        /* Marks Card */
        .subject-marks {
            display: grid;
            gap: 16px;
        }

        .subject-card {
            background: var(--light);
            border-radius: 12px;
            padding: 20px;
        }

        .subject-card .subject-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
        }

        .subject-card h4 {
            font-weight: 600;
            color: var(--dark);
        }

        .subject-card .marks {
            font-size: 18px;
            font-weight: 700;
            color: var(--primary);
        }

        /* Modal */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.5);
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s ease;
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal {
            background: var(--white);
            border-radius: 20px;
            width: 90%;
            max-width: 500px;
            max-height: 90vh;
            overflow-y: auto;
            transform: scale(0.9);
            transition: all 0.3s ease;
        }

        .modal-overlay.active .modal {
            transform: scale(1);
        }

        .modal-header {
            padding: 20px 24px;
            border-bottom: 1px solid var(--light);
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .modal-header h3 {
            font-size: 18px;
            font-weight: 600;
        }

        .modal-close {
            background: none;
            border: none;
            font-size: 20px;
            color: var(--gray);
            cursor: pointer;
        }

        .modal-body {
            padding: 24px;
        }

        .modal-footer {
            padding: 16px 24px;
            border-top: 1px solid var(--light);
            display: flex;
            justify-content: flex-end;
            gap: 12px;
        }

        /* Remarks */
        .remarks-list {
            display: grid;
            gap: 16px;
        }

        .remark-card {
            background: var(--light);
            border-radius: 12px;
            padding: 20px;
            border-left: 4px solid var(--primary);
        }

        .remark-card.positive {
            border-left-color: var(--success);
        }

        .remark-card.negative {
            border-left-color: var(--danger);
        }

        .remark-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
        }

        .remark-header .teacher {
            font-weight: 600;
            color: var(--dark);
        }

        .remark-header .date {
            font-size: 12px;
            color: var(--gray);
        }

        .remark-content {
            color: var(--gray);
            font-size: 14px;
        }

        /* Mobile Responsive */
        .mobile-toggle {
            display: none;
            background: none;
            border: none;
            font-size: 24px;
            color: var(--dark);
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .sidebar {
                transform: translateX(-100%);
            }

            .sidebar.active {
                transform: translateX(0);
            }

            .main-content {
                margin-left: 0;
            }

            .mobile-toggle {
                display: block;
            }

            .stats-grid {
                grid-template-columns: 1fr;
            }

            .attendance-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        /* Toast Notification */
        .toast {
            position: fixed;
            bottom: 30px;
            right: 30px;
            background: var(--dark);
            color: var(--white);
            padding: 16px 24px;
            border-radius: 12px;
            box-shadow: var(--shadow-lg);
            display: flex;
            align-items: center;
            gap: 12px;
            transform: translateY(100px);
            opacity: 0;
            transition: all 0.3s ease;
            z-index: 2000;
        }

        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }

        .toast.success {
            background: var(--success);
        }

        .toast.error {
            background: var(--danger);
        }

        /* Empty State */
        .empty-state {
            text-align: center;
            padding: 60px 20px;
        }

        .empty-state i {
            font-size: 64px;
            color: var(--light);
            margin-bottom: 20px;
        }

        .empty-state h3 {
            color: var(--dark);
            margin-bottom: 8px;
        }

        .empty-state p {
            color: var(--gray);
            font-size: 14px;
        }

        /* Action buttons */
        .action-buttons {
            display: flex;
            gap: 8px;
        }

        .action-btn {
            width: 32px;
            height: 32px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .action-btn.edit {
            background: rgba(79, 70, 229, 0.1);
            color: var(--primary);
        }

        .action-btn.delete {
            background: rgba(239, 68, 68, 0.1);
            color: var(--danger);
        }

        .action-btn:hover {
            transform: scale(1.1);
        }

        /* Filter & Search */
        .toolbar {
            display: flex;
            align-items: center;
            gap: 16px;
            flex-wrap: wrap;
            margin-bottom: 24px;
        }

        .search-box {
            flex: 1;
            min-width: 200px;
            position: relative;
        }

        .search-box input {
            width: 100%;
            padding: 12px 16px 12px 44px;
            border: 2px solid var(--light);
            border-radius: 10px;
            font-size: 14px;
        }

        .search-box i {
            position: absolute;
            left: 16px;
            top: 50%;
            transform: translateY(-50%);
            color: var(--gray);
        }

        .filter-select {
            padding: 12px 16px;
            border: 2px solid var(--light);
            border-radius: 10px;
            font-size: 14px;
            min-width: 150px;
        }
    </style>
</head>
<body>

    <!-- Auth Container -->
    <div class="auth-container" id="authContainer">
        <div class="auth-box">
            <div class="auth-header">
                <div class="logo">
                    <i class="fas fa-graduation-cap"></i>
                </div>
                <h1>Student Management</h1>
                <p>Manage your academic journey</p>
            </div>

            <div class="tabs">
                <button class="tab active" onclick="switchAuthTab('login')">Login</button>
                <button class="tab" onclick="switchAuthTab('signup')">Sign Up</button>
            </div>

            <!-- Login Form -->
            <form id="loginForm" onsubmit="handleLogin(event)">
                <div class="form-group">
                    <label>Email Address</label>
                    <input type="email" id="loginEmail" placeholder="Enter your email" required>
                </div>
                <div class="form-group">
                    <label>Password</label>
                    <input type="password" id="loginPassword" placeholder="Enter your password" required>
                </div>
                <div class="form-group">
                    <label>Login As</label>
                    <select id="loginRole">
                        <option value="student">Student</option>
                        <option value="admin">Admin</option>
                    </select>
                </div>
                <button type="submit" class="btn btn-primary">
                    <i class="fas fa-sign-in-alt"></i>
                    Login
                </button>
            </form>

            <!-- Signup Form -->
            <form id="signupForm" style="display: none;" onsubmit="handleSignup(event)">
                <div class="form-group">
                    <label>Full Name</label>
                    <input type="text" id="signupName" placeholder="Enter your full name" required>
                </div>
                <div class="form-group">
                    <label>Email Address</label>
                    <input type="email" id="signupEmail" placeholder="Enter your email" required>
                </div>
                <div class="form-group">
                    <label>Password</label>
                    <input type="password" id="signupPassword" placeholder="Create a password" required>
                </div>
                <div class="form-group">
                    <label>Confirm Password</label>
                    <input type="password" id="signupConfirm" placeholder="Confirm your password" required>
                </div>
                <div class="form-group">
                    <label>Register As</label>
                    <select id="signupRole">
                        <option value="student">Student</option>
                        <option value="admin">Admin</option>
                    </select>
                </div>
                <button type="submit" class="btn btn-primary">
                    <i class="fas fa-user-plus"></i>
                    Create Account
                </button>
            </form>

            <div class="auth-footer">
                <p>Demo: admin@school.edu / admin123</p>
            </div>
        </div>
    </div>

    <!-- Dashboard -->
    <div class="dashboard" id="dashboard">
        <!-- Sidebar -->
        <aside class="sidebar" id="sidebar">
            <div class="sidebar-header">
                <div class="logo-text">
                    <div class="logo-icon">
                        <i class="fas fa-graduation-cap"></i>
                    </div>
                    <div>
                        <h2>EduManage</h2>
                        <span>Management System</span>
                    </div>
                </div>
            </div>
            <nav class="sidebar-menu">
                <div class="menu-label">Main</div>
                <a class="menu-item active" onclick="showSection('overview')">
                    <i class="fas fa-home"></i>
                    Dashboard
                </a>
                <a class="menu-item" onclick="showSection('students')">
                    <i class="fas fa-users"></i>
                    Students
                </a>
                <a class="menu-item" onclick="showSection('attendance')">
                    <i class="fas fa-calendar-check"></i>
                    Attendance
                </a>

                <div class="menu-label">Academic</div>
                <a class="menu-item" onclick="showSection('academics')">
                    <i class="fas fa-book"></i>
                    Academic Records
                </a>
                <a class="menu-item" onclick="showSection('marks')">
                    <i class="fas fa-chart-line"></i>
                    Marks History
                </a>
                <a class="menu-item" onclick="showSection('remarks')">
                    <i class="fas fa-comment-alt"></i>
                    Remarks
                </a>

                <div class="menu-label">Finance & Info</div>
                <a class="menu-item" onclick="showSection('fees')">
                    <i class="fas fa-rupee-sign"></i>
                    Fee Details
                </a>
                <a class="menu-item" onclick="showSection('holidays')">
                    <i class="fas fa-umbrella-beach"></i>
                    Holidays
                </a>
            </nav>
        </aside>

        <!-- Main Content -->
        <main class="main-content">
            <header class="top-bar">
                <div style="display: flex; align-items: center; gap: 16px;">
                    <button class="mobile-toggle" onclick="toggleSidebar()">
                        <i class="fas fa-bars"></i>
                    </button>
                    <h1 id="pageTitle">Dashboard</h1>
                </div>
                <div class="user-info">
                    <div class="user-avatar" id="userAvatar">A</div>
                    <div class="user-details">
                        <h4 id="userName">Admin User</h4>
                        <span id="userRole">Administrator</span>
                    </div>
                    <button class="logout-btn" onclick="handleLogout()">
                        <i class="fas fa-sign-out-alt"></i>
                    </button>
                </div>
            </header>

            <div class="content-area">
                <!-- Overview Section -->
                <section class="page-section active" id="section-overview">
                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-icon blue">
                                <i class="fas fa-users"></i>
                            </div>
                            <h3 id="totalStudents">156</h3>
                            <p>Total Students</p>
                        </div>
                        <div class="stat-card">
                            <div class="stat-icon green">
                                <i class="fas fa-user-check"></i>
                            </div>
                            <h3 id="presentToday">142</h3>
                            <p>Present Today</p>
                        </div>
                        <div class="stat-card">
                            <div class="stat-icon orange">
                                <i class="fas fa-rupee-sign"></i>
                            </div>
                            <h3 id="feeCollected">₹4.2L</h3>
                            <p>Fee Collected</p>
                        </div>
                        <div class="stat-card">
                            <div class="stat-icon red">
                                <i class="fas fa-exclamation-triangle"></i>
                            </div>
                            <h3 id="pendingFees">23</h3>
                            <p>Pending Payments</p>
                        </div>
                    </div>

                    <div style="display: grid; grid-template-columns: 2fr 1fr; gap: 24px;">
                        <div class="card">
                            <div class="card-header">
                                <h3>Recent Students</h3>
                                <button class="btn btn-secondary btn-sm" onclick="showSection('students')">View All</button>
                            </div>
                            <div class="table-responsive">
                                <table>
                                    <thead>
                                        <tr>
                                            <th>Name</th>
                                            <th>Class</th>
                                            <th>Roll No</th>
                                            <th>Status</th>
                                        </tr>
                                    </thead>
                                    <tbody id="recentStudentsTable">
                                    </tbody>
                                </table>
                            </div>
                        </div>
                        <div class="card">
                            <div class="card-header">
                                <h3>Upcoming Holidays</h3>
                            </div>
                            <div class="card-body">
                                <div class="holiday-list" id="upcomingHolidays">
                                </div>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- Students Section -->
                <section class="page-section" id="section-students">
                    <div class="toolbar">
                        <div class="search-box">
                            <i class="fas fa-search"></i>
                            <input type="text" placeholder="Search students..." id="studentSearch" oninput="filterStudents()">
                        </div>
                        <select class="filter-select" id="classFilter" onchange="filterStudents()">
                            <option value="">All Classes</option>
                            <option value="10">Class 10</option>
                            <option value="11">Class 11</option>
                            <option value="12">Class 12</option>
                        </select>
                        <button class="btn btn-primary" onclick="openModal('addStudent')">
                            <i class="fas fa-plus"></i>
                            Add Student
                        </button>
                    </div>

                    <div class="card">
                        <div class="table-responsive">
                            <table>
                                <thead>
                                    <tr>
                                        <th>Roll No</th>
                                        <th>Name</th>
                                        <th>Class</th>
                                        <th>Email</th>
                                        <th>Phone</th>
                                        <th>Status</th>
                                        <th>Actions</th>
                                    </tr>
                                </thead>
                                <tbody id="studentsTable">
                                </tbody>
                            </table>
                        </div>
                    </div>
                </section>

                <!-- Attendance Section -->
                <section class="page-section" id="section-attendance">
                    <div class="toolbar">
                        <div class="form-group" style="margin: 0;">
                            <input type="date" id="attendanceDate" onchange="loadAttendance()">
                        </div>
                        <select class="filter-select" id="attendanceClass" onchange="loadAttendance()">
                            <option value="10">Class 10</option>
                            <option value="11">Class 11</option>
                            <option value="12">Class 12</option>
                        </select>
                        <button class="btn btn-success" onclick="saveAttendance()">
                            <i class="fas fa-save"></i>
                            Save Attendance
                        </button>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <h3>Mark Attendance</h3>
                            <div>
                                <span class="badge badge-success">Present: <span id="presentCount">0</span></span>
                                <span class="badge badge-danger" style="margin-left: 8px;">Absent: <span id="absentCount">0</span></span>
                            </div>
                        </div>
                        <div class="card-body">
                            <p style="margin-bottom: 16px; color: var(--gray);">Click on a student card to toggle attendance</p>
                            <div class="attendance-grid" id="attendanceGrid">
                            </div>
                        </div>
                    </div>

                    <div class="card" style="margin-top: 24px;">
                        <div class="card-header">
                            <h3>Attendance History</h3>
                        </div>
                        <div class="table-responsive">
                            <table>
                                <thead>
                                    <tr>
                                        <th>Date</th>
                                        <th>Class</th>
                                        <th>Present</th>
                                        <th>Absent</th>
                                        <th>Percentage</th>
                                    </tr>
                                </thead>
                                <tbody id="attendanceHistory">
                                </tbody>
                            </table>
                        </div>
                    </div>
                </section>

                <!-- Academics Section -->
                <section class="page-section" id="section-academics">
                    <div class="stats-grid">
                        <div class="stat-card">
                            <div class="stat-icon blue">
                                <i class="fas fa-book-open"></i>
                            </div>
                            <h3>6</h3>
                            <p>Total Subjects</p>
                        </div>
                        <div class="stat-card">
                            <div class="stat-icon green">
                                <i class="fas fa-clipboard-check"></i>
                            </div>
                            <h3>3</h3>
                            <p>Exams Completed</p>
                        </div>
                        <div class="stat-card">
                            <div class="stat-icon orange">
                                <i class="fas fa-trophy"></i>
                            </div>
                            <h3>85%</h3>
                            <p>Average Score</p>
                        </div>
                        <div class="stat-card">
                            <div class="stat-icon red">
                                <i class="fas fa-medal"></i>
                            </div>
                            <h3>5th</h3>
                            <p>Class Rank</p>
                        </div>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <h3>Subject-wise Performance</h3>
                            <select class="filter-select" id="examFilter" onchange="loadAcademics()">
                                <option value="midterm">Mid-Term Exam</option>
                                <option value="quarterly">Quarterly Exam</option>
                                <option value="halfyearly">Half-Yearly Exam</option>
                                <option value="annual">Annual Exam</option>
                            </select>
                        </div>
                        <div class="card-body">
                            <div class="subject-marks" id="subjectMarks">
                            </div>
                        </div>
                    </div>

                    <div class="card" style="margin-top: 24px;">
                        <div class="card-header">
                            <h3>Academic Calendar</h3>
                        </div>
                        <div class="table-responsive">
                            <table>
                                <thead>
                                    <tr>
                                        <th>Event</th>
                                        <th>Date</th>
                                        <th>Type</th>
                                        <th>Status</th>
                                    </tr>
                                </thead>
                                <tbody id="academicCalendar">
                                </tbody>
                            </table>
                        </div>
                    </div>
                </section>

                <!-- Marks History Section -->
                <section class="page-section" id="section-marks">
                    <div class="toolbar">
                        <select class="filter-select" id="marksStudent" onchange="loadMarksHistory()">
                            <option value="">Select Student</option>
                        </select>
                        <select class="filter-select" id="marksExam" onchange="loadMarksHistory()">
                            <option value="">All Exams</option>
                            <option value="midterm">Mid-Term</option>
                            <option value="quarterly">Quarterly</option>
                            <option value="halfyearly">Half-Yearly</option>
                            <option value="annual">Annual</option>
                        </select>
                        <button class="btn btn-primary" onclick="openModal('addMarks')">
                            <i class="fas fa-plus"></i>
                            Add Marks
                        </button>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <h3>Marks History</h3>
                        </div>
                        <div class="table-responsive">
                            <table>
                                <thead>
                                    <tr>
                                        <th>Student</th>
                                        <th>Exam</th>
                                        <th>Subject</th>
                                        <th>Marks</th>
                                        <th>Max Marks</th>
                                        <th>Grade</th>
                                        <th>Actions</th>
                                    </tr>
                                </thead>
                                <tbody id="marksTable">
                                </tbody>
                            </table>
                        </div>
                    </div>
                </section>

                <!-- Remarks Section -->
                <section class="page-section" id="section-remarks">
                    <div class="toolbar">
                        <div class="search-box">
                            <i class="fas fa-search"></i>
                            <input type="text" placeholder="Search remarks..." id="remarkSearch" oninput="filterRemarks()">
                        </div>
                        <select class="filter-select" id="remarkType" onchange="filterRemarks()">
                            <option value="">All Types</option>
                            <option value="positive">Positive</option>
                            <option value="negative">Negative</option>
                            <option value="neutral">Neutral</option>
                        </select>
                        <button class="btn btn-primary" onclick="openModal('addRemark')">
                            <i class="fas fa-plus"></i>
                            Add Remark
                        </button>
                    </div>

                    <div class="card">
                        <div class="card-body">
                            <div class="remarks-list" id="remarksList">
                            </div>
                        </div>
                    </div>
                </section>

                <!-- Fees Section -->
                <section class="page-section" id="section-fees">
                    <div class="fee-summary">
                        <div class="fee-card">
                            <h4>Total Fee</h4>
                            <div class="amount">₹85,000</div>
                        </div>
                        <div class="fee-card">
                            <h4>Paid Amount</h4>
                            <div class="amount paid">₹62,000</div>
                        </div>
                        <div class="fee-card">
                            <h4>Pending Amount</h4>
                            <div class="amount pending">₹23,000</div>
                        </div>
                        <div class="fee-card">
                            <h4>Due Date</h4>
                            <div class="amount">15 Jul 2026</div>
                        </div>
                    </div>

                    <div class="toolbar">
                        <select class="filter-select" id="feeStudent" onchange="loadFeeDetails()">
                            <option value="">Select Student</option>
                        </select>
                        <select class="filter-select" id="feeStatus" onchange="filterFees()">
                            <option value="">All Status</option>
                            <option value="paid">Paid</option>
                            <option value="pending">Pending</option>
                            <option value="overdue">Overdue</option>
                        </select>
                        <button class="btn btn-primary" onclick="openModal('addPayment')">
                            <i class="fas fa-plus"></i>
                            Record Payment
                        </button>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <h3>Fee Payment History</h3>
                        </div>
                        <div class="table-responsive">
                            <table>
                                <thead>
                                    <tr>
                                        <th>Receipt No</th>
                                        <th>Student</th>
                                        <th>Fee Type</th>
                                        <th>Amount</th>
                                        <th>Date</th>
                                        <th>Status</th>
                                        <th>Actions</th>
                                    </tr>
                                </thead>
                                <tbody id="feeTable">
                                </tbody>
                            </table>
                        </div>
                    </div>
                </section>

                <!-- Holidays Section -->
                <section class="page-section" id="section-holidays">
                    <div class="toolbar">
                        <select class="filter-select" id="holidayMonth" onchange="filterHolidays()">
                            <option value="">All Months</option>
                            <option value="1">January</option>
                            <option value="2">February</option>
                            <option value="3">March</option>
                            <option value="4">April</option>
                            <option value="5">May</option>
                            <option value="6">June</option>
                            <option value="7">July</option>
                            <option value="8">August</option>
                            <option value="9">September</option>
                            <option value="10">October</option>
                            <option value="11">November</option>
                            <option value="12">December</option>
                        </select>
                        <button class="btn btn-primary" onclick="openModal('addHoliday')">
                            <i class="fas fa-plus"></i>
                            Add Holiday
                        </button>
                    </div>

                    <div class="card">
                        <div class="card-header">
                            <h3>Holiday Calendar 2026</h3>
                        </div>
                        <div class="card-body">
                            <div class="holiday-list" id="holidayList">
                            </div>
                        </div>
                    </div>
                </section>
            </div>
        </main>
    </div>

    <!-- Add Student Modal -->
    <div class="modal-overlay" id="modal-addStudent">
        <div class="modal">
            <div class="modal-header">
                <h3>Add New Student</h3>
                <button class="modal-close" onclick="closeModal('addStudent')">&times;</button>
            </div>
            <form onsubmit="addStudent(event)">
                <div class="modal-body">
                    <div class="form-group">
                        <label>Full Name</label>
                        <input type="text" id="newStudentName" required>
                    </div>
                    <div class="form-group">
                        <label>Email</label>
                        <input type="email" id="newStudentEmail" required>
                    </div>
                    <div class="form-group">
                        <label>Phone</label>
                        <input type="tel" id="newStudentPhone" required>
                    </div>
                    <div class="form-group">
                        <label>Class</label>
                        <select id="newStudentClass" required>
                            <option value="10">Class 10</option>
                            <option value="11">Class 11</option>
                            <option value="12">Class 12</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Parent/Guardian Name</label>
                        <input type="text" id="newStudentParent">
                    </div>
                    <div class="form-group">
                        <label>Address</label>
                        <textarea id="newStudentAddress" rows="2"></textarea>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" onclick="closeModal('addStudent')">Cancel</button>
                    <button type="submit" class="btn btn-primary">Add Student</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Add Marks Modal -->
    <div class="modal-overlay" id="modal-addMarks">
        <div class="modal">
            <div class="modal-header">
                <h3>Add Marks</h3>
                <button class="modal-close" onclick="closeModal('addMarks')">&times;</button>
            </div>
            <form onsubmit="addMarks(event)">
                <div class="modal-body">
                    <div class="form-group">
                        <label>Student</label>
                        <select id="marksStudentSelect" required></select>
                    </div>
                    <div class="form-group">
                        <label>Exam</label>
                        <select id="marksExamSelect" required>
                            <option value="midterm">Mid-Term</option>
                            <option value="quarterly">Quarterly</option>
                            <option value="halfyearly">Half-Yearly</option>
                            <option value="annual">Annual</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Subject</label>
                        <select id="marksSubject" required>
                            <option value="Mathematics">Mathematics</option>
                            <option value="Physics">Physics</option>
                            <option value="Chemistry">Chemistry</option>
                            <option value="English">English</option>
                            <option value="Computer Science">Computer Science</option>
                            <option value="Biology">Biology</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Marks Obtained</label>
                        <input type="number" id="marksObtained" min="0" max="100" required>
                    </div>
                    <div class="form-group">
                        <label>Maximum Marks</label>
                        <input type="number" id="marksMax" value="100" min="1" required>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" onclick="closeModal('addMarks')">Cancel</button>
                    <button type="submit" class="btn btn-primary">Save Marks</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Add Remark Modal -->
    <div class="modal-overlay" id="modal-addRemark">
        <div class="modal">
            <div class="modal-header">
                <h3>Add Remark</h3>
                <button class="modal-close" onclick="closeModal('addRemark')">&times;</button>
            </div>
            <form onsubmit="addRemark(event)">
                <div class="modal-body">
                    <div class="form-group">
                        <label>Student</label>
                        <select id="remarkStudent" required></select>
                    </div>
                    <div class="form-group">
                        <label>Type</label>
                        <select id="remarkTypeSelect" required>
                            <option value="positive">Positive</option>
                            <option value="neutral">Neutral</option>
                            <option value="negative">Negative</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Subject/Category</label>
                        <input type="text" id="remarkSubject" placeholder="e.g., Academics, Behavior, Sports">
                    </div>
                    <div class="form-group">
                        <label>Remark</label>
                        <textarea id="remarkContent" rows="4" required placeholder="Enter your remark here..."></textarea>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" onclick="closeModal('addRemark')">Cancel</button>
                    <button type="submit" class="btn btn-primary">Add Remark</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Add Payment Modal -->
    <div class="modal-overlay" id="modal-addPayment">
        <div class="modal">
            <div class="modal-header">
                <h3>Record Payment</h3>
                <button class="modal-close" onclick="closeModal('addPayment')">&times;</button>
            </div>
            <form onsubmit="addPayment(event)">
                <div class="modal-body">
                    <div class="form-group">
                        <label>Student</label>
                        <select id="paymentStudent" required></select>
                    </div>
                    <div class="form-group">
                        <label>Fee Type</label>
                        <select id="paymentType" required>
                            <option value="Tuition Fee">Tuition Fee</option>
                            <option value="Exam Fee">Exam Fee</option>
                            <option value="Library Fee">Library Fee</option>
                            <option value="Lab Fee">Lab Fee</option>
                            <option value="Sports Fee">Sports Fee</option>
                            <option value="Transport Fee">Transport Fee</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Amount (₹)</label>
                        <input type="number" id="paymentAmount" min="1" required>
                    </div>
                    <div class="form-group">
                        <label>Payment Date</label>
                        <input type="date" id="paymentDate" required>
                    </div>
                    <div class="form-group">
                        <label>Payment Method</label>
                        <select id="paymentMethod">
                            <option value="Cash">Cash</option>
                            <option value="Card">Card</option>
                            <option value="UPI">UPI</option>
                            <option value="Bank Transfer">Bank Transfer</option>
                        </select>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" onclick="closeModal('addPayment')">Cancel</button>
                    <button type="submit" class="btn btn-primary">Record Payment</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Add Holiday Modal -->
    <div class="modal-overlay" id="modal-addHoliday">
        <div class="modal">
            <div class="modal-header">
                <h3>Add Holiday</h3>
                <button class="modal-close" onclick="closeModal('addHoliday')">&times;</button>
            </div>
            <form onsubmit="addHoliday(event)">
                <div class="modal-body">
                    <div class="form-group">
                        <label>Holiday Name</label>
                        <input type="text" id="holidayName" required>
                    </div>
                    <div class="form-group">
                        <label>Date</label>
                        <input type="date" id="holidayDate" required>
                    </div>
                    <div class="form-group">
                        <label>Type</label>
                        <select id="holidayType">
                            <option value="National">National Holiday</option>
                            <option value="Religious">Religious Holiday</option>
                            <option value="School">School Holiday</option>
                            <option value="Vacation">Vacation</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Description (Optional)</label>
                        <textarea id="holidayDescription" rows="2"></textarea>
                    </div>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" onclick="closeModal('addHoliday')">Cancel</button>
                    <button type="submit" class="btn btn-primary">Add Holiday</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Toast Notification -->
    <div class="toast" id="toast">
        <i class="fas fa-check-circle"></i>
        <span id="toastMessage">Success!</span>
    </div>

    <script>
        // Initialize Data
        let currentUser = null;
        let students = JSON.parse(localStorage.getItem('students')) || [
            { id: 1, rollNo: 'STU001', name: 'Aarav Sharma', class: '10', email: 'aarav@school.edu', phone: '9876543210', parent: 'Mr. Sharma', status: 'active' },
            { id: 2, rollNo: 'STU002', name: 'Priya Patel', class: '10', email: 'priya@school.edu', phone: '9876543211', parent: 'Mr. Patel', status: 'active' },
            { id: 3, rollNo: 'STU003', name: 'Arjun Singh', class: '11', email: 'arjun@school.edu', phone: '9876543212', parent: 'Mr. Singh', status: 'active' },
            { id: 4, rollNo: 'STU004', name: 'Ananya Gupta', class: '11', email: 'ananya@school.edu', phone: '9876543213', parent: 'Mrs. Gupta', status: 'active' },
            { id: 5, rollNo: 'STU005', name: 'Rohan Kumar', class: '12', email: 'rohan@school.edu', phone: '9876543214', parent: 'Mr. Kumar', status: 'active' },
            { id: 6, rollNo: 'STU006', name: 'Sneha Reddy', class: '12', email: 'sneha@school.edu', phone: '9876543215', parent: 'Mr. Reddy', status: 'inactive' }
        ];

        let attendance = JSON.parse(localStorage.getItem('attendance')) || {};

        let marks = JSON.parse(localStorage.getItem('marks')) || [
            { id: 1, studentId: 1, studentName: 'Aarav Sharma', exam: 'midterm', subject: 'Mathematics', marks: 85, maxMarks: 100 },
            { id: 2, studentId: 1, studentName: 'Aarav Sharma', exam: 'midterm', subject: 'Physics', marks: 78, maxMarks: 100 },
            { id: 3, studentId: 2, studentName: 'Priya Patel', exam: 'midterm', subject: 'Mathematics', marks: 92, maxMarks: 100 },
            { id: 4, studentId: 2, studentName: 'Priya Patel', exam: 'midterm', subject: 'Chemistry', marks: 88, maxMarks: 100 },
            { id: 5, studentId: 3, studentName: 'Arjun Singh', exam: 'quarterly', subject: 'English', marks: 75, maxMarks: 100 }
        ];

        let remarks = JSON.parse(localStorage.getItem('remarks')) || [
            { id: 1, studentId: 1, studentName: 'Aarav Sharma', type: 'positive', subject: 'Academics', content: 'Excellent performance in Mathematics. Shows great problem-solving skills.', teacher: 'Mrs. Verma', date: '2026-06-15' },
            { id: 2, studentId: 2, studentName: 'Priya Patel', type: 'positive', subject: 'Behavior', content: 'Very helpful to classmates. Great team player.', teacher: 'Mr. Rao', date: '2026-06-18' },
            { id: 3, studentId: 3, studentName: 'Arjun Singh', type: 'negative', subject: 'Attendance', content: 'Frequently late to class. Needs improvement.', teacher: 'Mrs. Sharma', date: '2026-06-20' }
        ];

        let fees = JSON.parse(localStorage.getItem('fees')) || [
            { id: 1, receiptNo: 'RCP001', studentId: 1, studentName: 'Aarav Sharma', type: 'Tuition Fee', amount: 25000, date: '2026-04-15', status: 'paid', method: 'UPI' },
            { id: 2, receiptNo: 'RCP002', studentId: 2, studentName: 'Priya Patel', type: 'Tuition Fee', amount: 25000, date: '2026-04-10', status: 'paid', method: 'Card' },
            { id: 3, receiptNo: 'RCP003', studentId: 3, studentName: 'Arjun Singh', type: 'Lab Fee', amount: 5000, date: '2026-05-01', status: 'pending', method: '' },
            { id: 4, receiptNo: 'RCP004', studentId: 1, studentName: 'Aarav Sharma', type: 'Exam Fee', amount: 2000, date: '2026-06-01', status: 'paid', method: 'Cash' }
        ];

        let holidays = JSON.parse(localStorage.getItem('holidays')) || [
            { id: 1, name: 'Republic Day', date: '2026-01-26', type: 'National', description: 'National holiday' },
            { id: 2, name: 'Holi', date: '2026-03-14', type: 'Religious', description: 'Festival of colors' },
            { id: 3, name: 'Good Friday', date: '2026-04-03', type: 'Religious', description: '' },
            { id: 4, name: 'Summer Vacation', date: '2026-05-15', type: 'Vacation', description: 'Summer break begins' },
            { id: 5, name: 'Independence Day', date: '2026-08-15', type: 'National', description: 'National holiday' },
            { id: 6, name: 'Gandhi Jayanti', date: '2026-10-02', type: 'National', description: 'Birth anniversary of Mahatma Gandhi' },
            { id: 7, name: 'Diwali', date: '2026-10-20', type: 'Religious', description: 'Festival of lights' },
            { id: 8, name: 'Christmas', date: '2026-12-25', type: 'Religious', description: 'Christmas day' }
        ];

        let users = JSON.parse(localStorage.getItem('users')) || [
            { email: 'admin@school.edu', password: 'admin123', name: 'Admin User', role: 'admin' },
            { email: 'student@school.edu', password: 'student123', name: 'Aarav Sharma', role: 'student' }
        ];

        // Auth Functions
        function switchAuthTab(tab) {
            document.querySelectorAll('.tabs .tab').forEach(t => t.classList.remove('active'));
            event.target.classList.add('active');
            
            if (tab === 'login') {
                document.getElementById('loginForm').style.display = 'block';
                document.getElementById('signupForm').style.display = 'none';
            } else {
                document.getElementById('loginForm').style.display = 'none';
                document.getElementById('signupForm').style.display = 'block';
            }
        }

        function handleLogin(e) {
            e.preventDefault();
            const email = document.getElementById('loginEmail').value;
            const password = document.getElementById('loginPassword').value;
            const role = document.getElementById('loginRole').value;

            const user = users.find(u => u.email === email && u.password === password && u.role === role);
            
            if (user) {
                currentUser = user;
                localStorage.setItem('currentUser', JSON.stringify(user));
                showDashboard();
                showToast('Login successful!', 'success');
            } else {
                showToast('Invalid credentials', 'error');
            }
        }

        function handleSignup(e) {
            e.preventDefault();
            const name = document.getElementById('signupName').value;
            const email = document.getElementById('signupEmail').value;
            const password = document.getElementById('signupPassword').value;
            const confirm = document.getElementById('signupConfirm').value;
            const role = document.getElementById('signupRole').value;

            if (password !== confirm) {
                showToast('Passwords do not match', 'error');
                return;
            }

            if (users.find(u => u.email === email)) {
                showToast('Email already exists', 'error');
                return;
            }

            const newUser = { email, password, name, role };
            users.push(newUser);
            localStorage.setItem('users', JSON.stringify(users));
            
            showToast('Account created! Please login.', 'success');
            switchAuthTab('login');
            document.getElementById('loginEmail').value = email;
        }

        function handleLogout() {
            currentUser = null;
            localStorage.removeItem('currentUser');
            document.getElementById('authContainer').style.display = 'flex';
            document.getElementById('dashboard').classList.remove('active');
            showToast('Logged out successfully', 'success');
        }

        function showDashboard() {
            document.getElementById('authContainer').style.display = 'none';
            document.getElementById('dashboard').classList.add('active');
            
            document.getElementById('userName').textContent = currentUser.name;
            document.getElementById('userRole').textContent = currentUser.role === 'admin' ? 'Administrator' : 'Student';
            document.getElementById('userAvatar').textContent = currentUser.name.charAt(0).toUpperCase();
            
            initializeDashboard();
        }

        // Navigation
        function showSection(section) {
            document.querySelectorAll('.page-section').forEach(s => s.classList.remove('active'));
            document.querySelectorAll('.menu-item').forEach(m => m.classList.remove('active'));
            
            document.getElementById(`section-${section}`).classList.add('active');
            event.target.closest('.menu-item').classList.add('active');
            
            const titles = {
                'overview': 'Dashboard',
                'students': 'Students',
                'attendance': 'Attendance',
                'academics': 'Academic Records',
                'marks': 'Marks History',
                'remarks': 'Remarks',
                'fees': 'Fee Details',
                'holidays': 'Holidays'
            };
            document.getElementById('pageTitle').textContent = titles[section] || 'Dashboard';
            
            // Load section-specific data
            if (section === 'attendance') loadAttendance();
            if (section === 'academics') loadAcademics();
            if (section === 'marks') loadMarksHistory();
            if (section === 'holidays') renderHolidays();
            if (section === 'fees') loadFeeDetails();
            if (section === 'remarks') renderRemarks();
            if (section === 'students') renderStudents();

            // Close sidebar on mobile
            document.getElementById('sidebar').classList.remove('active');
        }

        function toggleSidebar() {
            document.getElementById('sidebar').classList.toggle('active');
        }

        // Initialize Dashboard
        function initializeDashboard() {
            // Set today's date for attendance
            document.getElementById('attendanceDate').value = new Date().toISOString().split('T')[0];
            document.getElementById('paymentDate').value = new Date().toISOString().split('T')[0];
            
            // Update stats
            document.getElementById('totalStudents').textContent = students.length;
            document.getElementById('presentToday').textContent = Math.floor(students.length * 0.9);
            
            // Render recent students
            renderRecentStudents();
            renderUpcomingHolidays();
            renderStudents();
            populateStudentDropdowns();
        }

        function renderRecentStudents() {
            const tbody = document.getElementById('recentStudentsTable');
            tbody.innerHTML = students.slice(0, 5).map(s => `
                <tr>
                    <td>${s.name}</td>
                    <td>Class ${s.class}</td>
                    <td>${s.rollNo}</td>
                    <td><span class="badge ${s.status === 'active' ? 'badge-success' : 'badge-danger'}">${s.status}</span></td>
                </tr>
            `).join('');
        }

        function renderUpcomingHolidays() {
            const today = new Date();
            const upcoming = holidays
                .filter(h => new Date(h.date) >= today)
                .sort((a, b) => new Date(a.date) - new Date(b.date))
                .slice(0, 3);

            document.getElementById('upcomingHolidays').innerHTML = upcoming.map(h => {
                const date = new Date(h.date);
                return `
                    <div class="holiday-item">
                        <div class="holiday-date">
                            <span class="day">${date.getDate()}</span>
                            <span class="month">${date.toLocaleString('default', { month: 'short' })}</span>
                        </div>
                        <div class="holiday-info">
                            <h4>${h.name}</h4>
                            <p>${h.type}</p>
                        </div>
                    </div>
                `;
            }).join('');
        }

        // Students
        function renderStudents() {
            const tbody = document.getElementById('studentsTable');
            tbody.innerHTML = students.map(s => `
                <tr>
                    <td>${s.rollNo}</td>
                    <td>${s.name}</td>
                    <td>Class ${s.class}</td>
                    <td>${s.email}</td>
                    <td>${s.phone}</td>
                    <td><span class="badge ${s.status === 'active' ? 'badge-success' : 'badge-danger'}">${s.status}</span></td>
                    <td>
                        <div class="action-buttons">
                            <button class="action-btn edit" onclick="editStudent(${s.id})"><i class="fas fa-edit"></i></button>
                            <button class="action-btn delete" onclick="deleteStudent(${s.id})"><i class="fas fa-trash"></i></button>
                        </div>
                    </td>
                </tr>
            `).join('');
        }

        function filterStudents() {
            const search = document.getElementById('studentSearch').value.toLowerCase();
            const classFilter = document.getElementById('classFilter').value;
            
            const filtered = students.filter(s => {
                const matchSearch = s.name.toLowerCase().includes(search) || s.rollNo.toLowerCase().includes(search);
                const matchClass = !classFilter || s.class === classFilter;
                return matchSearch && matchClass;
            });

            const tbody = document.getElementById('studentsTable');
            tbody.innerHTML = filtered.map(s => `
                <tr>
                    <td>${s.rollNo}</td>
                    <td>${s.name}</td>
                    <td>Class ${s.class}</td>
                    <td>${s.email}</td>
                    <td>${s.phone}</td>
                    <td><span class="badge ${s.status === 'active' ? 'badge-success' : 'badge-danger'}">${s.status}</span></td>
                    <td>
                        <div class="action-buttons">
                            <button class="action-btn edit" onclick="editStudent(${s.id})"><i class="fas fa-edit"></i></button>
                            <button class="action-btn delete" onclick="deleteStudent(${s.id})"><i class="fas fa-trash"></i></button>
                        </div>
                    </td>
                </tr>
            `).join('');
        }

        function addStudent(e) {
            e.preventDefault();
            const newStudent = {
                id: Date.now(),
                rollNo: `STU${String(students.length + 1).padStart(3, '0')}`,
                name: document.getElementById('newStudentName').value,
                email: document.getElementById('newStudentEmail').value,
                phone: document.getElementById('newStudentPhone').value,
                class: document.getElementById('newStudentClass').value,
                parent: document.getElementById('newStudentParent').value,
                status: 'active'
            };

            students.push(newStudent);
            saveData();
            renderStudents();
            populateStudentDropdowns();
            closeModal('addStudent');
            showToast('Student added successfully!', 'success');
            e.target.reset();
        }

        function deleteStudent(id) {
            if (confirm('Are you sure you want to delete this student?')) {
                students = students.filter(s => s.id !== id);
                saveData();
                renderStudents();
                populateStudentDropdowns();
                showToast('Student deleted!', 'success');
            }
        }

        // Attendance
        function loadAttendance() {
            const date = document.getElementById('attendanceDate').value;
            const classFilter = document.getElementById('attendanceClass').value;
            
            const classStudents = students.filter(s => s.class === classFilter && s.status === 'active');
            const dayAttendance = attendance[date] || {};

            const grid = document.getElementById('attendanceGrid');
            grid.innerHTML = classStudents.map(s => {
                const status = dayAttendance[s.id] || 'present';
                return `
                    <div class="attendance-card ${status}" onclick="toggleAttendance(${s.id}, '${date}')">
                        <div class="student-name">${s.name}</div>
                        <div class="roll-no">${s.rollNo}</div>
                        <i class="fas fa-${status === 'present' ? 'check-circle' : 'times-circle'}" style="margin-top: 8px; color: ${status === 'present' ? 'var(--success)' : 'var(--danger)'}"></i>
                    </div>
                `;
            }).join('');

            updateAttendanceCounts();
            loadAttendanceHistory();
        }

        function toggleAttendance(studentId, date) {
            if (!attendance[date]) attendance[date] = {};
            attendance[date][studentId] = attendance[date][studentId] === 'absent' ? 'present' : 'absent';
            loadAttendance();
        }

        function updateAttendanceCounts() {
            const date = document.getElementById('attendanceDate').value;
            const dayAttendance = attendance[date] || {};
            
            let present = 0, absent = 0;
            Object.values(dayAttendance).forEach(status => {
                if (status === 'present') present++;
                else absent++;
            });

            document.getElementById('presentCount').textContent = present;
            document.getElementById('absentCount').textContent = absent;
        }

        function saveAttendance() {
            localStorage.setItem('attendance', JSON.stringify(attendance));
            showToast('Attendance saved successfully!', 'success');
        }

        function loadAttendanceHistory() {
            const dates = Object.keys(attendance).sort().reverse().slice(0, 10);
            const tbody = document.getElementById('attendanceHistory');
            
            tbody.innerHTML = dates.map(date => {
                const dayData = attendance[date];
                const present = Object.values(dayData).filter(s => s === 'present').length;
                const absent = Object.values(dayData).filter(s => s === 'absent').length;
                const total = present + absent;
                const percentage = total > 0 ? Math.round((present / total) * 100) : 0;
                
                return `
                    <tr>
                        <td>${new Date(date).toLocaleDateString('en-IN', { day: 'numeric', month: 'short', year: 'numeric' })}</td>
                        <td>All Classes</td>
                        <td><span class="badge badge-success">${present}</span></td>
                        <td><span class="badge badge-danger">${absent}</span></td>
                        <td>
                            <div style="display: flex; align-items: center; gap: 8px;">
                                <div class="progress-bar" style="flex: 1;">
                                    <div class="progress" style="width: ${percentage}%"></div>
                                </div>
                                <span>${percentage}%</span>
                            </div>
                        </td>
                    </tr>
                `;
            }).join('');
        }

        // Academics
        function loadAcademics() {
            const subjects = [
                { name: 'Mathematics', marks: 85, maxMarks: 100 },
                { name: 'Physics', marks: 78, maxMarks: 100 },
                { name: 'Chemistry', marks: 82, maxMarks: 100 },
                { name: 'English', marks: 88, maxMarks: 100 },
                { name: 'Computer Science', marks: 95, maxMarks: 100 },
                { name: 'Biology', marks: 72, maxMarks: 100 }
            ];

            const container = document.getElementById('subjectMarks');
            container.innerHTML = subjects.map(s => {
                const percentage = (s.marks / s.maxMarks) * 100;
                return `
                    <div class="subject-card">
                        <div class="subject-header">
                            <h4>${s.name}</h4>
                            <span class="marks">${s.marks}/${s.maxMarks}</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress" style="width: ${percentage}%"></div>
                        </div>
                    </div>
                `;
            }).join('');

            // Academic Calendar
            const events = [
                { event: 'Mid-Term Examination', date: '2026-07-15', type: 'Exam', status: 'upcoming' },
                { event: 'Science Fair', date: '2026-08-10', type: 'Event', status: 'upcoming' },
                { event: 'Quarterly Examination', date: '2026-09-20', type: 'Exam', status: 'upcoming' },
                { event: 'Annual Sports Day', date: '2026-10-15', type: 'Event', status: 'upcoming' }
            ];

            document.getElementById('academicCalendar').innerHTML = events.map(e => `
                <tr>
                    <td>${e.event}</td>
                    <td>${new Date(e.date).toLocaleDateString('en-IN', { day: 'numeric', month: 'short', year: 'numeric' })}</td>
                    <td><span class="badge ${e.type === 'Exam' ? 'badge-warning' : 'badge-info'}">${e.type}</span></td>
                    <td><span class="badge badge-success">${e.status}</span></td>
                </tr>
            `).join('');
        }

        // Marks
        function loadMarksHistory() {
            const tbody = document.getElementById('marksTable');
            tbody.innerHTML = marks.map(m => {
                const percentage = (m.marks / m.maxMarks) * 100;
                let grade = 'F';
                if (percentage >= 90) grade = 'A+';
                else if (percentage >= 80) grade = 'A';
                else if (percentage >= 70) grade = 'B+';
                else if (percentage >= 60) grade = 'B';
                else if (percentage >= 50) grade = 'C';
                else if (percentage >= 40) grade = 'D';

                return `
                    <tr>
                        <td>${m.studentName}</td>
                        <td>${m.exam.charAt(0).toUpperCase() + m.exam.slice(1)}</td>
                        <td>${m.subject}</td>
                        <td>${m.marks}</td>
                        <td>${m.maxMarks}</td>
                        <td><span class="badge ${percentage >= 60 ? 'badge-success' : percentage >= 40 ? 'badge-warning' : 'badge-danger'}">${grade}</span></td>
                        <td>
                            <div class="action-buttons">
                                <button class="action-btn edit"><i class="fas fa-edit"></i></button>
                                <button class="action-btn delete" onclick="deleteMarks(${m.id})"><i class="fas fa-trash"></i></button>
                            </div>
                        </td>
                    </tr>
                `;
            }).join('');
        }

        function addMarks(e) {
            e.preventDefault();
            const studentId = parseInt(document.getElementById('marksStudentSelect').value);
            const student = students.find(s => s.id === studentId);
            
            const newMark = {
                id: Date.now(),
                studentId: studentId,
                studentName: student.name,
                exam: document.getElementById('marksExamSelect').value,
                subject: document.getElementById('marksSubject').value,
                marks: parseInt(document.getElementById('marksObtained').value),
                maxMarks: parseInt(document.getElementById('marksMax').value)
            };

            marks.push(newMark);
            saveData();
            loadMarksHistory();
            closeModal('addMarks');
            showToast('Marks added successfully!', 'success');
            e.target.reset();
        }

        function deleteMarks(id) {
            if (confirm('Are you sure you want to delete this record?')) {
                marks = marks.filter(m => m.id !== id);
                saveData();
                loadMarksHistory();
                showToast('Marks deleted!', 'success');
            }
        }

        // Remarks
        function renderRemarks() {
            const container = document.getElementById('remarksList');
            container.innerHTML = remarks.map(r => `
                <div class="remark-card ${r.type}">
                    <div class="remark-header">
                        <span class="teacher">${r.teacher} - ${r.studentName}</span>
                        <span class="date">${new Date(r.date).toLocaleDateString('en-IN', { day: 'numeric', month: 'short', year: 'numeric' })}</span>
                    </div>
                    <div style="margin-bottom: 8px;">
                        <span class="badge ${r.type === 'positive' ? 'badge-success' : r.type === 'negative' ? 'badge-danger' : 'badge-info'}">${r.type}</span>
                        <span style="margin-left: 8px; color: var(--gray); font-size: 12px;">${r.subject}</span>
                    </div>
                    <div class="remark-content">${r.content}</div>
                </div>
            `).join('');
        }

        function filterRemarks() {
            const search = document.getElementById('remarkSearch').value.toLowerCase();
            const type = document.getElementById('remarkType').value;
            
            const filtered = remarks.filter(r => {
                const matchSearch = r.content.toLowerCase().includes(search) || r.studentName.toLowerCase().includes(search);
                const matchType = !type || r.type === type;
                return matchSearch && matchType;
            });

            const container = document.getElementById('remarksList');
            container.innerHTML = filtered.map(r => `
                <div class="remark-card ${r.type}">
                    <div class="remark-header">
                        <span class="teacher">${r.teacher} - ${r.studentName}</span>
                        <span class="date">${new Date(r.date).toLocaleDateString('en-IN', { day: 'numeric', month: 'short', year: 'numeric' })}</span>
                    </div>
                    <div style="margin-bottom: 8px;">
                        <span class="badge ${r.type === 'positive' ? 'badge-success' : r.type === 'negative' ? 'badge-danger' : 'badge-info'}">${r.type}</span>
                        <span style="margin-left: 8px; color: var(--gray); font-size: 12px;">${r.subject}</span>
                    </div>
                    <div class="remark-content">${r.content}</div>
                </div>
            `).join('');
        }

        function addRemark(e) {
            e.preventDefault();
            const studentId = parseInt(document.getElementById('remarkStudent').value);
            const student = students.find(s => s.id === studentId);
            
            const newRemark = {
                id: Date.now(),
                studentId: studentId,
                studentName: student.name,
                type: document.getElementById('remarkTypeSelect').value,
                subject: document.getElementById('remarkSubject').value,
                content: document.getElementById('remarkContent').value,
                teacher: currentUser.name,
                date: new Date().toISOString().split('T')[0]
            };

            remarks.push(newRemark);
            saveData();
            renderRemarks();
            closeModal('addRemark');
            showToast('Remark added successfully!', 'success');
            e.target.reset();
        }

        // Fees
        function loadFeeDetails() {
            const tbody = document.getElementById('feeTable');
            tbody.innerHTML = fees.map(f => `
                <tr>
                    <td>${f.receiptNo}</td>
                    <td>${f.studentName}</td>
                    <td>${f.type}</td>
                    <td>₹${f.amount.toLocaleString()}</td>
                    <td>${new Date(f.date).toLocaleDateString('en-IN', { day: 'numeric', month: 'short', year: 'numeric' })}</td>
                    <td><span class="badge ${f.status === 'paid' ? 'badge-success' : f.status === 'pending' ? 'badge-warning' : 'badge-danger'}">${f.status}</span></td>
                    <td>
                        <div class="action-buttons">
                            <button class="action-btn edit"><i class="fas fa-print"></i></button>
                            <button class="action-btn delete" onclick="deleteFee(${f.id})"><i class="fas fa-trash"></i></button>
                        </div>
                    </td>
                </tr>
            `).join('');
        }

        function filterFees() {
            const status = document.getElementById('feeStatus').value;
            const filtered = status ? fees.filter(f => f.status === status) : fees;
            
            const tbody = document.getElementById('feeTable');
            tbody.innerHTML = filtered.map(f => `
                <tr>
                    <td>${f.receiptNo}</td>
                    <td>${f.studentName}</td>
                    <td>${f.type}</td>
                    <td>₹${f.amount.toLocaleString()}</td>
                    <td>${new Date(f.date).toLocaleDateString('en-IN', { day: 'numeric', month: 'short', year: 'numeric' })}</td>
                    <td><span class="badge ${f.status === 'paid' ? 'badge-success' : f.status === 'pending' ? 'badge-warning' : 'badge-danger'}">${f.status}</span></td>
                    <td>
                        <div class="action-buttons">
                            <button class="action-btn edit"><i class="fas fa-print"></i></button>
                            <button class="action-btn delete" onclick="deleteFee(${f.id})"><i class="fas fa-trash"></i></button>
                        </div>
                    </td>
                </tr>
            `).join('');
        }

        function addPayment(e) {
            e.preventDefault();
            const studentId = parseInt(document.getElementById('paymentStudent').value);
            const student = students.find(s => s.id === studentId);
            
            const newPayment = {
                id: Date.now(),
                receiptNo: `RCP${String(fees.length + 1).padStart(3, '0')}`,
                studentId: studentId,
                studentName: student.name,
                type: document.getElementById('paymentType').value,
                amount: parseInt(document.getElementById('paymentAmount').value),
                date: document.getElementById('paymentDate').value,
                status: 'paid',
                method: document.getElementById('paymentMethod').value
            };

            fees.push(newPayment);
            saveData();
            loadFeeDetails();
            closeModal('addPayment');
            showToast('Payment recorded successfully!', 'success');
            e.target.reset();
        }

        function deleteFee(id) {
            if (confirm('Are you sure you want to delete this record?')) {
                fees = fees.filter(f => f.id !== id);
                saveData();
                loadFeeDetails();
                showToast('Record deleted!', 'success');
            }
        }

        // Holidays
        function renderHolidays() {
            const container = document.getElementById('holidayList');
            const sortedHolidays = [...holidays].sort((a, b) => new Date(a.date) - new Date(b.date));
            
            container.innerHTML = sortedHolidays.map(h => {
                const date = new Date(h.date);
                return `
                    <div class="holiday-item">
                        <div class="holiday-date">
                            <span class="day">${date.getDate()}</span>
                            <span class="month">${date.toLocaleString('default', { month: 'short' })}</span>
                        </div>
                        <div class="holiday-info" style="flex: 1;">
                            <h4>${h.name}</h4>
                            <p>${h.type}${h.description ? ' - ' + h.description : ''}</p>
                        </div>
                        <button class="action-btn delete" onclick="deleteHoliday(${h.id})"><i class="fas fa-trash"></i></button>
                    </div>
                `;
            }).join('');
        }

        function filterHolidays() {
            const month = document.getElementById('holidayMonth').value;
            const filtered = month ? holidays.filter(h => new Date(h.date).getMonth() + 1 === parseInt(month)) : holidays;
            
            const container = document.getElementById('holidayList');
            const sortedHolidays = [...filtered].sort((a, b) => new Date(a.date) - new Date(b.date));
            
            container.innerHTML = sortedHolidays.map(h => {
                const date = new Date(h.date);
                return `
                    <div class="holiday-item">
                        <div class="holiday-date">
                            <span class="day">${date.getDate()}</span>
                            <span class="month">${date.toLocaleString('default', { month: 'short' })}</span>
                        </div>
                        <div class="holiday-info" style="flex: 1;">
                            <h4>${h.name}</h4>
                            <p>${h.type}${h.description ? ' - ' + h.description : ''}</p>
                        </div>
                        <button class="action-btn delete" onclick="deleteHoliday(${h.id})"><i class="fas fa-trash"></i></button>
                    </div>
                `;
            }).join('');
        }

        function addHoliday(e) {
            e.preventDefault();
            const newHoliday = {
                id: Date.now(),
                name: document.getElementById('holidayName').value,
                date: document.getElementById('holidayDate').value,
                type: document.getElementById('holidayType').value,
                description: document.getElementById('holidayDescription').value
            };

            holidays.push(newHoliday);
            saveData();
            renderHolidays();
            renderUpcomingHolidays();
            closeModal('addHoliday');
            showToast('Holiday added successfully!', 'success');
            e.target.reset();
        }

        function deleteHoliday(id) {
            if (confirm('Are you sure you want to delete this holiday?')) {
                holidays = holidays.filter(h => h.id !== id);
                saveData();
                renderHolidays();
                renderUpcomingHolidays();
                showToast('Holiday deleted!', 'success');
            }
        }

        // Modal Functions
        function openModal(type) {
            document.getElementById(`modal-${type}`).classList.add('active');
        }

        function closeModal(type) {
            document.getElementById(`modal-${type}`).classList.remove('active');
        }

        // Populate Student Dropdowns
        function populateStudentDropdowns() {
            const dropdowns = ['marksStudent', 'marksStudentSelect', 'remarkStudent', 'paymentStudent', 'feeStudent'];
            const options = students.map(s => `<option value="${s.id}">${s.name} (${s.rollNo})</option>`).join('');
            
            dropdowns.forEach(id => {
                const el = document.getElementById(id);
                if (el) {
                    const firstOption = el.querySelector('option');
                    el.innerHTML = (firstOption ? firstOption.outerHTML : '') + options;
                }
            });
        }

        // Toast Notification
        function showToast(message, type = 'success') {
            const toast = document.getElementById('toast');
            const toastMessage = document.getElementById('toastMessage');
            
            toast.className = `toast ${type}`;
            toastMessage.textContent = message;
            toast.classList.add('show');
            
            setTimeout(() => {
                toast.classList.remove('show');
            }, 3000);
        }

        // Save Data
        function saveData() {
            localStorage.setItem('students', JSON.stringify(students));
            localStorage.setItem('marks', JSON.stringify(marks));
            localStorage.setItem('remarks', JSON.stringify(remarks));
            localStorage.setItem('fees', JSON.stringify(fees));
            localStorage.setItem('holidays', JSON.stringify(holidays));
            localStorage.setItem('attendance', JSON.stringify(attendance));
        }

        // Check for existing session
        window.onload = function() {
            const savedUser = localStorage.getItem('currentUser');
            if (savedUser) {
                currentUser = JSON.parse(savedUser);
                showDashboard();
            }
        };

        // Close modal when clicking outside
        document.querySelectorAll('.modal-overlay').forEach(overlay => {
            overlay.addEventListener('click', function(e) {
                if (e.target === this) {
                    this.classList.remove('active');
                }
            });
        });
    </script>
</body>
</html>
