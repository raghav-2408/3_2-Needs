# Web Storage 

```javascript
// Set local storage
localStorage.setItem('username', 'JohnDoe');

// Get local storage
const username = localStorage.getItem('username');
console.log(username); // Output: JohnDoe

// Remove item from local storage
localStorage.removeItem('username');

// Clear all local storage
localStorage.clear();
```

```javascript
// Set session storage
sessionStorage.setItem('city', 'New York');

// Get session storage
const city = sessionStorage.getItem('city');
console.log(city); // Output: New York

// Remove item from session storage
sessionStorage.removeItem('city');

// Clear all session storage
sessionStorage.clear();
```

# Drag and Drop

```html
<html>

<head>
    <title>Drag and Drop Example</title>
    <style>
        #item1 {
            width: 100px;
            height: 50px;
            background-color: red;
        }
        #item2 {
            width: 100px;
            height: 50px;
            background-color: greenyellow;
        }
    </style>
</head>

<body>

    <h2>Drag and Drop Example</h2>

    <div class="container" ondrop="drop(event)" ondragover="allowDrop(event)">
        <div id="item1" class="item" draggable="true" ondragstart="drag(event)">item1</div>
        <div id="item2" class="item" draggable="true" ondragstart="drag(event)">item2</div>
    </div>

    <script>
        function allowDrop(event) {
            event.preventDefault();
        }

        function drag(event) {
            event.dataTransfer.setData("text", event.target.id);
        }

        function drop(event) {
            event.preventDefault();
            var data = event.dataTransfer.getData("text");
            event.target.appendChild(document.getElementById(data));
        }
    </script>

</body>

</html>
```

