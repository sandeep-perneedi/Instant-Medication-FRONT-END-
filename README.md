<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Instant Medical delivery </title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5fd;
            color: #e0e0e0;
        }

        header {
            background: linear-gradient(90deg, #3d8ce0, #3d8ce0);
            color: #ffffff;
            padding: 20px 0;
            text-align: center;
            box-shadow: 0 4px 6px rgba(241, 240, 240, 0.852);
        }

        nav ul {
            display: flex;
            justify-content: center;
            background: #054a8f;
            list-style: none;
            padding: 10px 0;
            margin: 0;
        }

        nav ul li {
            margin: 0 15px;
        }

        nav ul li a {
            color: #ffffff;
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s ease;
        }

        nav ul li a:hover {
            color: #0808089c;
        }

        main {
            padding: 20px;
            animation: fadeIn 1s ease-in-out;
        }

        section {
            margin-bottom: 30px;
            background: #3d8ce0;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
            transition: transform 0.3s ease;
        }

        section:hover {
            transform: scale(1.02);
        }

        input[type="text"],
        input[type="password"],
        select {
            width: 98%;
            padding: 12px;
            margin-bottom: 20px;
            border: none;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            background-color: #d9e7d9;
            color: #0c0101;
        }

        input::placeholder {
            color: #a9a9b5;
        }

        button {
            padding: 12px;
            background-color: #dde3e1;
            color: #01060b;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.3s ease;
        }

        button:hover {
            background-color: #57afca;
            transform: scale(1.05);
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        table, th, td {
            border: 1px solid #efeded;
        }

        th, td {
            padding: 15px;
            text-align: left;
        }

        th {
            background: linear-gradient(90deg, #3262e7, #66abf4);
            color: #ffffff;
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 100;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            animation: fadeIn 0.5s ease;
        }

        .modal-content {
            background-color: #fefefe;
            margin: 15% auto;
            padding: 20px;
            border: 1px solid #797979;
            width: 60%;
            border-radius: 12px;
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            transition: color 0.3s ease;
        }

        .close:hover,
        .close:focus {
            color: #f7f7f7;
            cursor: pointer;
        }

        footer {
            text-align: center;
            padding: 20px 0;
            background: #3d8ce0;
            color: #ffffff;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @media (max-width: 768px) {
            .modal-content {
                width: 90%;
            }

            nav ul {
                flex-direction: column;
                padding: 0;
            }

            nav ul li {
                margin-bottom: 15px;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>Instant Medication</h1>
    </header>

    <nav id="navbar">
        <ul>
            <li><a href="#login" onclick="showSection('login')">Login</a></li>           
            <li><a href="#home" onclick="showSection('home')">Home</a></li>
            <li><a href="#exam-seating-plan" onclick="showSection('exam-seating-plan')">customer details</a></li>
            <li><a href="#student-list" onclick="showSection('student-list')">your orders </a></li>
            <li><a href="#settings" onclick="showSection('settings')">Settings</a></li>
            <li><a href="#logout" id="logoutBtn" style="display:none;" onclick="logout()">Logout</a></li>

        </ul>
    </nav>
    <main>
        <!-- Home Section -->
        <section id="home" style="display:none;">
            <h2>Welcome to the Instant Medical Delivery Application</h2>
            <p>Our system ensures efficient and fast Delivery arrangements, minimizing Time and maximizing Quality of product for customers. The system offers:</p>
            <ul>
                <li>Fast and secure delivery </li>
                <li>User-Friendly Interface</li>
                <li>Automated bill generation</li>
                <li>Smart Refill Reminders </li>
                <li>Comprehensive Medicine Database</li>
            </ul>
            <p>Click on the <strong>customer Details</strong> or <strong>your orders</strong> tabs above to get started!</p>
        </section>`

        <!-- customer details -->
        <section id="exam-seating-plan" style="display:none;">
            <h2>Our Customer</h2>
            <input type="text" id="searchExam" placeholder="Search by Name" onkeyup="searchTable('exam')">
            <table>
                <thead>
                    <tr>
                        <th>Customer Name</th>
                        <th>Phone Number</th>
                        <th>Delivery Adress</th>

                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Sheik Arif</td>
                        <td>9546375849</td>
                        <td>flatno:5163,Estentia towers,gudivanchery,chennai</td>
                    </tr>
                    <tr>
                        <td>Sai Venkata Charan</td>
                        <td>7023847281</td>
                        <td>Room 102,abode valley,kakinada,andra pradesh</td>
                        
                    </tr>
                    <tr>
                        <td>Manendra</td>
                        <td>6302278273</td>
                        <td>villa No:103A,avitha residency,mahendra world city,mm nagar,chennai</td>
                    
                    </tr>
                </tbody>
            </table>
        </section>

        <!-- orders placed -->
        <section id="student-list" style="display:none;">
            <h2>Student List</h2>
            <input type="text" id="searchStudent" placeholder="Search by Student Name" onkeyup="searchTable('student')">
            <table>
                <thead>
                    <tr>
                        <th>Customer Name</th>
                        <th>Medicines Needed</th>
                        <th>Quantity</th>
                        <th>Description</th>
                        
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Sheik Arif</td>
                        <td>Prastamol,

                            Mitronidazole,
                            Methionine,
                            Desprine,
                            Cefixime
                            
                            </td>
                            <td>  Eachone 1 sheet </td>
                            <td>for basic travelling medication kit</td>
                       
                    </tr>
                    <tr>
                        <td>venkata sai charan</td>
                        <td>Azithromycin,
                            Agmentin,
                            Diclofenac</td>
                        <td>Eachone 2 sheets</td>
                        <td>for cold and coaf</td>
                    
                    </tr>
                    <tr>
                        <td>Manendra</td>
                        <td>Cefixime,Azithromycin,Agmentin,Diclofenac,Mitoclopramide,Silicazib</td>
                        <td>Eachone 1 sheet,Agmentin is 2 sheets,</td>
                        <td>for backpain,through pain</td>
                       
                    
                    </tr>
                </tbody>
            </table>
        </section>

        <!-- Settings Section -->
        <section id="settings" style="display:none;">
            <h2>Settings</h2>
            <p>Customize your experience. Choose preferred settings:</p>
            <form>
                <label for="theme">Select Theme:</label>
                <select id="theme" name="theme">
                    <option value="light">Light</option>
                    <option value="dark">Dark</option>
                    <option value="blue">Blue</option>
                </select>
                <label for="notifications">Enable Notifications:</label>
                <select id="notifications" name="notifications">
                    <option value="yes">Yes</option>
                    <option value="no">No</option>
                </select>
                <button type="submit">Save Settings</button>
            </form>
        </section>

        <!-- Login Section -->
        <section id="login" class="active">
            <h2>Login</h2>
            <p id="loginMessage" style="color:rgb(239, 239, 239);"></p>
            <form onsubmit="login(event)">
                <label for="username">Username:</label>
                <input type="text" id="username" placeholder="Enter username" required>
                <label for="password">Password:</label>
                <input type="password" id="password" placeholder="Enter password" required>
                <button type="submit">Login</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; YOUR HEALTH , DELIVERED IN MINUTES!!</p>
    </footer>

    <script>
        let isLoggedIn = false;

        function showSection(sectionId) {
            const sections = document.querySelectorAll('main section');
            sections.forEach(section => {
                section.style.display = 'none';
            });
            document.getElementById(sectionId).style.display = 'block';

            if (sectionId === 'login') {
                document.getElementById('logoutBtn').style.display = 'none';
            } else if (isLoggedIn) {
                document.getElementById('logoutBtn').style.display = 'block';
            }
        }

        function searchTable(type) {
            const input = type === 'exam' ? document.getElementById('searchExam') : document.getElementById('searchStudent');
            const filter = input.value.toLowerCase();
            const table = type === 'exam' ? document.querySelector('#exam-seating-plan table tbody') : document.querySelector('#student-list table tbody');
            const rows = table.getElementsByTagName("tr");

            for (let i = 0; i < rows.length; i++) {
                const cells = rows[i].getElementsByTagName("td");
                let found = false;
                for (let j = 0; j < cells.length; j++) {
                    if (cells[j].textContent.toLowerCase().includes(filter)) {
                        found = true;
                        break;
                    }
                }
                rows[i].style.display = found ? "" : "none";
            }
        }

        function login(event) {
            event.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Simple login check (replace with real authentication)
            if (username === "admin" && password === "password") {
                isLoggedIn = true;
                document.getElementById('loginMessage').textContent = '';
                showSection('home');
                document.getElementById('navbar').style.display = 'flex';
            } else {
                document.getElementById('loginMessage').textContent = 'Invalid credentials. Please try again.';
            }
            
        }

        function logout() {
            isLoggedIn = false;
            document.getElementById('logoutBtn').style.display = 'none';
            showSection('login');
        }
    </script>
</body>
</html>
