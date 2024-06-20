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

# Geo Location

```javascript
if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(success, error);
}
else {
    console.log('Geolocation is not supported by this browser.');
}

function success(position) {
    var latitude = position.coords.latitude;
    var longitude = position.coords.longitude;
    console.log('Latitude: ' + latitude + ', Longitude: ' + longitude);
}

function error(error) {
    console.log('Error getting geolocation: ' + error.message);
}
```

# CSS Navbar 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        nav{
            display: flex;
            align-items: center;
            justify-content: center;
            height: 50px;
            background-color: black;
        }
        nav ul li{
            padding: 40px;
            color: white;
            display: inline;
            list-style: none;
        }
    </style>
</head>
<body>
    <nav>
        <ul>
            <li>Home</li>
            <li>About</li>
            <li>Contact</li>
        </ul>
    </nav>
</body>
</html>
```

# CSS Navbar with Bootstrap 

```html
<html>
<head>
    <title>Document</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
    <style>
        .navbar{
            display: flex;
            align-items: center;
            justify-content: center;
        }
    </style>
</head>
<body>
    <nav class="navbar bg-dark text-white">
        <ul class="nav">
            <li class="nav-item">Home</li>
            <li class="nav-item mx-2">About</li>
            <li class="nav-item mx-1">Contact</li>
        </ul>
    </nav>
</body>
</html>
```

<img src = "Screenshot 2024-06-20 232109.png">
