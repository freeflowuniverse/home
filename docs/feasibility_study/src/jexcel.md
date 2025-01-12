## jexcel

<script src="https://bossanova.uk/jspreadsheet/v4/jexcel.js"></script>
<link rel="stylesheet" href="https://bossanova.uk/jspreadsheet/v4/jexcel.css" type="text/css" />
 
<script src="https://jsuites.net/v4/jsuites.js"></script>
<link rel="stylesheet" href="https://jsuites.net/v4/jsuites.css" type="text/css" />
 
<div id="spreadsheet"></div>
 
<script>
var data = [
    ['Jazz', 'Honda', '2019-02-12', 'https://threefold.io/assets/static/become_farmer_new.333ed37.2a45beb3f2bcd85958ad286faeabe77e.jpg', true, '$ 3.000,00', '#777700'],
    ['Civic', 'Honda', '2018-07-11', '', true, '$ 4.000,01', '#007777'],
];
var changed = function(instance, cell, x, y, value) {
        var cellName = jexcel.getColumnNameFromId([x,y]);
       console.log('New change on cell ' + cellName + ' to: ' + value);
    };
jspreadsheet(document.getElementById('spreadsheet'), {
    data:data,
    columns: [
        {
            type: 'text',
            title:'Car',
            width:90
        },
        {
            type: 'dropdown',
            title:'Make',
            width:120,
            source:[
                "Alfa Romeo",
                "Audi",
                "Bmw",
                "Chevrolet",
                "Chrystler",
                // (...)
              ]
        },
        {
            type: 'calendar',
            title:'Available',
            width:120
        },
        {
            type: 'image',
            title:'Photo',
            width:120
        },
        {
            type: 'checkbox',
            title:'Stock',
            width:80
        },
        {
            type: 'numeric',
            title:'Price',
            mask:'$ #.##,00',
            width:80,
            decimal:','
        },
        {
            type: 'color',
            width:80,
            render:'square',
        },
     ],
    onchange: changed,

});
</script>

> https://bossanova.uk/jspreadsheet/v4/examples/events

