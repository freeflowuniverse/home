## chart      

<head>
<meta charset="UTF-8" />
<script src="https://cdn.jsdelivr.net/npm/chart.js@3.9.1/dist/chart.min.js"></script>
</head>

<body>


<canvas id="myChart" width="400" height="400"></canvas>
<script>
const ctx = document.getElementById('myChart');
const myChart = new Chart(ctx, {
        type: 'radar',
        data: {
            labels: ['Running', 'Swimming', 'Eating', 'Cycling','test'],
            datasets: [{
                data: [20, 10, 4, 2,3]
            }]
        }
    }
    );
</script>
</body>

