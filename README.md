<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f4f6f9;
            color: #333;
        }

        .dashboard {
            display: flex;
            min-height: 100vh;
        }

        /* Sidebar */
        .sidebar {
            width: 240px;
            background: #1e293b;
            color: white;
            padding: 25px 15px;
        }

        .sidebar h2 {
            text-align: center;
            margin-bottom: 30px;
        }

        .sidebar ul {
            list-style: none;
        }

        .sidebar li {
            padding: 14px 15px;
            margin: 8px 0;
            border-radius: 8px;
            cursor: pointer;
        }

        .sidebar li:hover,
        .sidebar .active {
            background: #3b82f6;
        }

        /* Main content */
        .main {
            flex: 1;
            padding: 25px;
        }

        .topbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 25px;
        }

        .topbar h1 {
            font-size: 28px;
        }

        .profile {
            background: white;
            padding: 10px 15px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }

        /* Cards */
        .cards {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            margin-bottom: 25px;
        }

        .card {
            background: white;
            padding: 22px;
            border-radius: 12px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.08);
        }

        .card h3 {
            color: #64748b;
            font-size: 15px;
            margin-bottom: 10px;
        }

        .card .number {
            font-size: 28px;
            font-weight: bold;
        }

        .green {
            color: #16a34a;
        }

        .blue {
            color: #2563eb;
        }

        .orange {
            color: #ea580c;
        }

        .red {
            color: #dc2626;
        }

        /* Content grid */
        .content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 20px;
        }

        .panel {
            background: white;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.08);
        }

        .panel h2 {
            margin-bottom: 20px;
        }

        /* Chart */
        .chart {
            height: 280px;
            display: flex;
            align-items: flex-end;
            gap: 20px;
            padding: 20px 10px;
            border-bottom: 2px solid #ddd;
        }

        .bar {
            flex: 1;
            background: #3b82f6;
            border-radius: 6px 6px 0 0;
            position: relative;
        }

        .bar:hover {
            background: #2563eb;
        }

        .bar span {
            position: absolute;
            bottom: -25px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 12px;
            color: #555;
        }

        /* Orders */
        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 14px 10px;
            text-align: left;
            border-bottom: 1px solid #eee;
        }

        th {
            color: #64748b;
        }

        .status {
            padding: 5px 10px;
            border-radius: 15px;
            font-size: 12px;
        }

        .completed {
            background: #dcfce7;
            color: #15803d;
        }

        .pending {
            background: #fef3c7;
            color: #b45309;
        }

        /* Responsive */
        @media (max-width: 1000px) {
            .cards {
                grid-template-columns: repeat(2, 1fr);
            }

            .content {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 700px) {
            .sidebar {
                width: 70px;
            }

            .sidebar h2 {
                font-size: 0;
            }

            .sidebar h2::after {
                content: "D";
                font-size: 25px;
            }

            .sidebar li {
                text-align: center;
                font-size: 0;
            }

            .sidebar li::first-letter {
                font-size: 20px;
            }

            .main {
                padding: 15px;
            }

            .cards {
                grid-template-columns: 1fr;
            }

            .topbar {
                flex-direction: column;
                align-items: flex-start;
                gap: 10px;
            }

            table {
                font-size: 12px;
            }
        }
    </style>
</head>

<body>

<div class="dashboard">

    <!-- Sidebar -->
    <aside class="sidebar">
        <h2>My Dashboard</h2>

        <ul>
            <li class="active">🏠 Dashboard</li>
            <li>📊 Analytics</li>
            <li>👥 Users</li>
            <li>🛒 Orders</li>
            <li>📦 Products</li>
            <li>⚙️ Settings</li>
            <li>🚪 Logout</li>
        </ul>
    </aside>

    <!-- Main -->
    <main class="main">

        <!-- Top bar -->
        <div class="topbar">
            <h1>Dashboard</h1>

            <div class="profile">
                👤 Admin
            </div>
        </div>

        <!-- Statistics -->
        <section class="cards">

            <div class="card">
                <h3>Total Sales</h3>
                <div class="number blue">₹85,420</div>
            </div>

            <div class="card">
                <h3>Total Users</h3>
                <div class="number green">12,540</div>
            </div>

            <div class="card">
                <h3>Total Orders</h3>
                <div class="number orange">1,250</div>
            </div>

            <div class="card">
                <h3>Pending Orders</h3>
                <div class="number red">86</div>
            </div>

        </section>

        <!-- Charts and summary -->
        <section class="content">

            <div class="panel">
                <h2>Monthly Sales</h2>

                <div class="chart">
                    <div class="bar" style="height: 45%;">
                        <span>Jan</span>
                    </div>

                    <div class="bar" style="height: 65%;">
                        <span>Feb</span>
                    </div>

                    <div class="bar" style="height: 50%;">
                        <span>Mar</span>
                    </div>

                    <div class="bar" style="height: 80%;">
                        <span>Apr</span>
                    </div>

                    <div class="bar" style="height: 70%;">
                        <span>May</span>
                    </div>

                    <div class="bar" style="height: 90%;">
                        <span>Jun</span>
                    </div>
                </div>
            </div>

            <div class="panel">
                <h2>Quick Summary</h2>

                <p>📈 Sales Growth: <strong class="green">+18%</strong></p>
                <br>

                <p>👥 New Users: <strong>+320</strong></p>
                <br>

                <p>🛒 New Orders: <strong>+125</strong></p>
                <br>

                <p>💰 Revenue: <strong>₹25,400</strong></p>
            </div>

        </section>

        <br>

        <!-- Recent Orders -->
        <div class="panel">
            <h2>Recent Orders</h2>

            <table>
                <thead>
                    <tr>
                        <th>Order ID</th>
                        <th>Customer</th>
                        <th>Product</th>
                        <th>Amount</th>
                        <th>Status</th>
                    </tr>
                </thead>

                <tbody>
                    <tr>
                        <td>#1001</td>
                        <td>Rahul</td>
                        <td>Laptop</td>
                        <td>₹55,000</td>
                        <td>
                            <span class="status completed">
                                Completed
                            </span>
                        </td>
                    </tr>

                    <tr>
                        <td>#1002</td>
                        <td>Priya</td>
                        <td>Phone</td>
                        <td>₹25,000</td>
                        <td>
                            <span class="status pending">
                                Pending
                            </span>
                        </td>
                    </tr>

                    <tr>
                        <td>#1003</td>
                        <td>Amit</td>
                        <td>Headphones</td>
                        <td>₹3,500</td>
                        <td>
                            <span class="status completed">
                                Completed
                            </span>
                        </td>
                    </tr>

                    <tr>
                        <td>#1004</td>
                        <td>Neha</td>
                        <td>Tablet</td>
                        <td>₹18,000</td>
                        <td>
                            <span class="status pending">
                                Pending
                            </span>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>

    </main>
</div>

</body>
</html>
