html:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Chain reaction</title>
    <meta charset="utf-8" />
</head>
<body onload="main();">
    <table></table>
</body>
</html>
```

css:
```css
td {
    width: 50px;
    height: 50px;
    border: 1px solid black;
}
```

js:
```js
function main() {
    var table = document.querySelector("table");

    for (var i = 0; i < 6; i++) {
        var row = document.createElement("tr");

        for (var j = 0; j < 6; j++) {
            var cell = document.createElement("td");
            row.appendChild(cell);
        }
        table.appendChild(row);
    }

    document.addEventListener("click", function (e) {
        var node = e.target;
        if (node.nodeName == "TD") {
            update(node)
        };
    });

    function update(cell) {
        cell.innerHTML += "o";
    }
}
```