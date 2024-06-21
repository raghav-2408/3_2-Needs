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


# Events

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <button id="btn">click</button>

    <button id="btn1">click</button>

    <input type="text" id="inp">
</body>
<script>
    let btn = document.getElementById('btn');
    btn.addEventListener('click', () => {
        alert("Clicked")
    })


    // let btn = document.getElementById('btn');
    // btn.addEventListener('dblclick', () => {
    //     alert("Double Clicked")
    // })


    // let btn1 = document.getElementById('btn1');
    // btn1.addEventListener('mousemove', (e) => {
    //     console.log(e.clientX, e.clientY)
    //})
    

    let btn1 = document.getElementById('btn1');
    btn1.addEventListener('mouseover', (e) => {
        alert("Mouse hover")
    })


    // let inp = document.getElementById('inp');
    // inp.addEventListener('keydown', () => {
    //     alert("Key down Pressed")
    // })


    let inp = document.getElementById('inp');
    inp.addEventListener('keyup', () => {
        alert("Key up Pressed")
    })


    // let inp = document.getElementById('inp');
    // inp.addEventListener('keypress', () => {
    //     alert("Key Pressed")
    // })
</script>

</html>
```

# AJAX to Show user details

```html
<!DOCTYPE html>
<html>
<head>
    <title>AJAX Example</title>
    <script>
        function loadUserDetails() {
            let userId = document.getElementById('userId').value;
            let xhr = new XMLHttpRequest();
            xhr.onreadystatechange = function() {
                if (xhr.readyState === 4 && xhr.status === 200) {
                    let user = JSON.parse(xhr.responseText);
                    document.getElementById('userDetails').innerHTML =
                        'Name: ' + user.name + '<br>' +
                        'Email: ' + user.email + '<br>' +
                        'Phone: ' + user.phone;
                }
            };
            xhr.open('GET', 'https://jsonplaceholder.typicode.com/users/' + userId, true);
            xhr.send();
        }
    </script>
</head>
<body>
    <h1>Fetch User Details</h1>
    <input type="text" id="userId" placeholder="Enter User ID">
    <button onclick="loadUserDetails()">Get User Details</button>
    <div id="userDetails"></div>
</body>
</html>
```


# jQuery Events and Selectors 

```html
<html>
<head>
    <title>jQuery Selectors and Mouse Events</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
</head>
<body>
    <h1>jQuery Selectors and Mouse Events</h1>
    
    <!-- Selectors Example -->
    <p>This is a paragraph.</p>
    <div>
        <p>This is another paragraph.</p>
        <p>This is another descendent of div</p>
    </div>
    <p id="para3">This is a third paragraph.</p>
    <p class="myClass">This is a paragraph with class "myClass".</p>
    
    <!-- Mouse Events Example -->
    <button id="btnClick" class="button">Click me</button>
    <button id="btnDblClick" class="button">Double-click me</button>
    <button id="btnHover" class="button">Hover over me</button>
    
    <script>
        // jQuery document ready function
        $(document).ready(function() {
            // Selectors
            $('div p').css('color', 'violet'); // Change color of all <p> elements
            $('#para3').css('font-weight', 'bold'); // Change font weight of <p> with id="para3"
            $('.myClass').css('background-color', 'yellow'); // Change background color of elements with class "myClass"
            
            // Mouse Events
            $('#btnClick').click(function() {
                alert('Button clicked');
            });
            
            $('#btnDblClick').dblclick(function() {
                alert('Button double-clicked');
            });
            
            $('#btnHover').mouseenter(function() {
                $(this).css('background-color', 'red');
            })

            $('#btnHover').mouseleave(function() {
                $(this).css('background-color', '#007bff');
            });
        });
    </script>
</body>
</html>
```
