# Sale-dashboard

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sales Analysis Dashboard</title>
    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body class="bg-gray-100 text-gray-800">
    <header class="bg-white shadow p-4 mb-6">
        <h1 class="text-2xl font-bold text-center">Sales Analysis Dashboard</h1>
    </header>

    <main class="px-4 max-w-7xl mx-auto">
        <section class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4 mb-6">
            <div class="bg-white p-4 rounded-2xl shadow">
                <h2 class="text-xl font-semibold mb-2">Total Sales</h2>
                <p class="text-3xl font-bold text-green-600">$25,000</p>
            </div>
            <div class="bg-white p-4 rounded-2xl shadow">
                <h2 class="text-xl font-semibold mb-2">Monthly Revenue</h2>
                <p class="text-3xl font-bold text-blue-500">$3,200</p>
            </div>
            <div class="bg-white p-4 rounded-2xl shadow">
                <h2 class="text-xl font-semibold mb-2">Top Product</h2>
                <p class="text-lg font-medium">Wireless Earbuds</p>
            </div>
            <div class="bg-white p-4 rounded-2xl shadow">
                <h2 class="text-xl font-semibold mb-2">Returning Customers</h2>
                <p class="text-3xl font-bold text-purple-500">68%</p>
            </div>
        </section>

        <section class="grid grid-cols-1 lg:grid-cols-2 gap-6 mb-6">
            <div class="bg-white p-4 rounded-2xl shadow">
                <h2 class="text-lg font-semibold mb-4">Monthly Sales Overview</h2>
                <canvas id="salesChart"></canvas>
            </div>
            <div class="bg-white p-4 rounded-2xl shadow">
                <h2 class="text-lg font-semibold mb-4">Product Category Breakdown</h2>
                <canvas id="categoryChart"></canvas>
            </div>
        </section>

        <section class="bg-white p-4 rounded-2xl shadow">
            <h2 class="text-lg font-semibold mb-4">Recent Transactions</h2>
            <table class="w-full table-auto">
                <thead>
                    <tr class="bg-gray-100">
                        <th class="text-left p-2">Date</th>
                        <th class="text-left p-2">Product</th>
                        <th class="text-left p-2">Amount</th>
                        <th class="text-left p-2">Customer</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="p-2">2025-04-01</td>
                        <td class="p-2">Smart Watch</td>
                        <td class="p-2">$199</td>
                        <td class="p-2">John Doe</td>
                    </tr>
                    <tr class="bg-gray-50">
                        <td class="p-2">2025-04-02</td>
                        <td class="p-2">Bluetooth Speaker</td>
                        <td class="p-2">$89</td>
                        <td class="p-2">Jane Smith</td>
                    </tr>
                    <tr>
                        <td class="p-2">2025-04-03</td>
                        <td class="p-2">Wireless Earbuds</td>
                        <td class="p-2">$129</td>
                        <td class="p-2">Alice Johnson</td>
                    </tr>
                </tbody>
            </table>
        </section>
    </main>

    <script>
        const salesCtx = document.getElementById('salesChart').getContext('2d');
        const salesChart = new Chart(salesCtx, {
            type: 'line',
            data: {
                labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'],
                datasets: [{
                    label: 'Sales',
                    data: [3000, 4000, 3200, 5000, 4600, 4800],
                    backgroundColor: 'rgba(59, 130, 246, 0.2)',
                    borderColor: 'rgba(59, 130, 246, 1)',
                    borderWidth: 2,
                    fill: true,
                    tension: 0.4
                }]
            }
        });

        const categoryCtx = document.getElementById('categoryChart').getContext('2d');
        const categoryChart = new Chart(categoryCtx, {
            type: 'doughnut',
            data: {
                labels: ['Audio', 'Wearables', 'Accessories', 'Others'],
                datasets: [{
                    label: 'Category Sales',
                    data: [45, 25, 20, 10],
                    backgroundColor: [
                        'rgba(59, 130, 246, 0.6)',
                        'rgba(96, 165, 250, 0.6)',
                        'rgba(147, 197, 253, 0.6)',
                        'rgba(191, 219, 254, 0.6)'
                    ],
                    borderWidth: 1
                }]
            }
        });
    </script>
</body>
</html>
