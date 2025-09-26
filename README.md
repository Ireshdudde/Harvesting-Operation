<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Harvesting Operation Dashboard</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 1200px;
            margin: 20px auto;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .header {
            background: #f5e8c7;
            padding: 10px;
            text-align: center;
            border-radius: 5px;
            margin-bottom: 20px;
        }
        .header h1 {
            margin: 0;
            color: #333;
        }
        .header p {
            margin: 5px 0 0;
            color: #020202;
            font-size: larger;
        }
        nav {
            margin-bottom: 20px;
        }
        nav button {
            padding: 10px 20px;
            margin-right: 10px;
            background: #00796b;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        nav button:hover {
            background: #004d40;
        }
        .page {
            display: none;
        }
        .active {
            display: block;
        }
        .cards {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            margin-bottom: 20px;
        }
        .card {
            background: #d0f9f7;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(1, 1, 134, 0.1);
            text-align: center;
            min-width: 200px;
            margin: 10px;
        }
        .card h3 {
            color: #00695c;
            margin-bottom: 10px;
        }
        .card p {
            font-size: 24px;
            font-weight: bold;
            color: #333;
        }
        .charts {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
        }
        .chart-container {
            width: 45%;
            min-width: 300px;
            margin: 10px;
            height: 400px; /* Adjusted height for both charts */
        }
        .village-section {
            margin-bottom: 30px;
        }
        .village-header {
            background: #b0bec5;
            padding: 10px;
            border-radius: 5px;
            text-align: center;
            margin-bottom: 10px;
        }
        .village-cards {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Harvesting Operation</h1>
            <p>September 25, 2025</p>
        </div>
        <nav>
            <button onclick="showPage('home')">Home</button>
            <button onclick="showPage('villages')">Villages</button>
        </nav>
        <div id="home" class="page active">
            <div class="cards">
                <div class="card">
                    <h3>Total Packed Boxes</h3>
                    <p>6440</p>
                </div>
                <div class="card">
                    <h3>Total Rejection QTY (Kg)</h3>
                    <p>2915</p>
                </div>
                <div class="card">
                    <h3>Recovery Rate</h3>
                    <p>71.20 %</p>
                </div>
                <div class="card">
                    <h3>Rejection (%)</h3>
                    <p>3.40 %</p>
                </div>
            </div>
            <div class="charts">
                <div class="chart-container">
                    <canvas id="recoveryChart"></canvas>
                </div>
                <div class="chart-container">
                    <canvas id="packedChart"></canvas>
                </div>
            </div>
        </div>
        <div id="villages" class="page">
            <div class="village-section">
                <div class="village-header">Akluj</div>
                <div class="village-cards">
                    <div class="card">
                        <h3>Packed Boxes</h3>
                        <p>2570</p>
                    </div>
                    <div class="card">
                        <h3>Rejection QTY (Kg)</h3>
                        <p>1624</p>
                    </div>
                    <div class="card">
                        <h3>Recovery Rate</h3>
                        <p>73.25 %</p>
                    </div>
                    <div class="card">
                        <h3>Rejection (%)</h3>
                        <p>4.63 %</p>
                    </div>
                </div>
            </div>
            <!-- <div class="village-section">
                <div class="village-header">Narayangaon</div>
                <div class="village-cards">
                    <div class="card">
                        <h3>Packed Boxes</h3>
                        <p>649</p>
                    </div>
                    <div class="card">
                        <h3>Rejection QTY (Kg)</h3>
                        <p>281</p>
                    </div>
                    <div class="card">
                        <h3>Recovery Rate</h3>
                        <p>66.26%</p>
                    </div>
                    <div class="card">
                        <h3>Rejection (%)</h3>
                        <p>3.31%</p>
                    </div>
                </div>
            </div> -->
            <div class="village-section">
                <div class="village-header">Shirpur</div>
                <div class="village-cards">
                    <div class="card">
                        <h3>Packed Boxes</h3>
                        <p>921</p>
                    </div>
                    <div class="card">
                        <h3>Rejection QTY (Kg)</h3>
                        <p>150</p>
                    </div>
                    <div class="card">
                        <h3>Recovery Rate</h3>
                        <p>80.48 %</p>
                    </div>
                    <div class="card">
                        <h3>Rejection (%)</h3>
                        <p>1.24 %</p>
                    </div>
                </div>
            </div>
            <div class="village-section">
                <div class="village-header">Indapur</div>
                <div class="village-cards">
                    <div class="card">
                        <h3>Packed Boxes</h3>
                        <p>1517</p>
                    </div>
                    <div class="card">
                        <h3>Rejection QTY (Kg)</h3>
                        <p>750</p>
                    </div>
                    <div class="card">
                        <h3>Recovery Rate</h3>
                        <p>64.78 %</p>
                    </div>
                    <div class="card">
                        <h3>Rejection (%)</h3>
                        <p>3.31 %</p>
                    </div>
                </div>
            </div>
            <div class="village-section">
                <div class="village-header">Jamner</div>
                <div class="village-cards">
                    <div class="card">
                        <h3>Packed Boxes</h3>
                        <p>1441</p>
                    </div>
                    <div class="card">
                        <h3>Rejection QTY (Kg)</h3>
                        <p>391</p>
                    </div>
                    <div class="card">
                        <h3>Recovery Rate</h3>
                        <p>72.11%</p>
                    </div>
                    <div class="card">
                        <h3>Rejection (%)</h3>
                        <p>2.17%</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <script>
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById(pageId).classList.add('active');
        }

        const regions = ['Akluj', 'Shirpur', 'Indapur', 'Jamner'];
        const recoveryRates = [73.25, 80.48, 64.78, 72.11];
        const packedBoxes = [2570, 921, 1517, 1441];

        const recoveryCtx = document.getElementById('recoveryChart').getContext('2d');
        new Chart(recoveryCtx, {
            type: 'bar',
            data: {
                labels: regions,
                datasets: [{
                    label: 'Recovery Rate (%)',
                    data: recoveryRates,
                    backgroundColor: '#4caf50',
                    borderColor: '#388e3c',
                    borderWidth: 1
                }]
            },
            options: {
                scales: {
                    y: {
                        beginAtZero: true,
                        max: 100
                    }
                },
                maintainAspectRatio: false,
                responsive: true,
                plugins: {
                    legend: {
                        display: true
                    },
                    title: {
                        display: true,
                        text: 'Village Wise Recovery Rate'
                    }
                }
            }
        });

        const packedCtx = document.getElementById('packedChart').getContext('2d');
        new Chart(packedCtx, {
            type: 'doughnut',
            data: {
                labels: regions,
                datasets: [{
                    label: 'Packed Boxes',
                    data: packedBoxes,
                    backgroundColor: ['#ff6384', '#36a2eb', '#ffce56', '#4bc0c0', '#9966ff'],
                    hoverOffset: 4
                }]
            },
            options: {
                maintainAspectRatio: false,
                responsive: true,
                plugins: {
                    legend: {
                        position: 'top'
                    },
                    title: {
                        display: true,
                        text: 'Village Wise Packed Boxes'
                    }
                }
            }
        });
    </script>
</body>
</html>
