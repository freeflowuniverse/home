### GridJS

<head>
<meta charset="UTF-8" />
<script src="https://unpkg.com/gridjs/dist/gridjs.umd.js"></script>
<link href="https://cdn.jsdelivr.net/npm/gridjs/dist/theme/mermaid.min.css" rel="stylesheet" />
</head>

<body>

<div id="wrapper"></div>

<script>
new gridjs.Grid({
  columns: [{
        name: "Name",
        sort: true,
      }, "Email", "Phone Number"],
  data: [
    ["John", "john@example.com", "(353) 01 222 3333"],
    ["Mark", "mark@gmail.com", "(01) 22 888 4444"],
    ["Eoin", "eoin@gmail.com", "0097 22 654 00033"],
    ["Sarah", "sarahcdd@gmail.com", "+322 876 1233"],
    ["Afshin", "afshin@mail.com", "(353) 22 87 8356"]
  ],
  search: {
    enabled: true
  }
}).render(document.getElementById("wrapper"));
</script>
</body>

