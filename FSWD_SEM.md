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

# DOM Manipulation 
### Document Object Model

```html
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM Manipulation Example</title>
</head>
<body>
    <h1>DOM Manipulation Example</h1>

    <p id="demo">This is a paragraph.</p>

    <button onclick="changeText()">Change Text</button>
    <button onclick="changeStyle()">Change Style</button>
    <button onclick="addHighlight()">Add Highlight</button>
    <button onclick="removeHighlight()">Remove Highlight</button>

    <script>
        function changeText() {
            document.getElementById('demo').innerHTML = 'Text changed!';
        }

        function changeStyle() {
            document.getElementById('demo').style.color = 'blue';
            document.getElementById('demo').style.fontSize = '20px';
        }
        
        function addHighlight() {
            document.getElementById('demo').style.backgroundColor = 'yellow';
        }
        
        function removeHighlight() {
            document.getElementById('demo').style.backgroundColor = 'white';
        }
    </script>
</body>
</html>
```


# jQuery Effects and Animations :

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Effects and Animations in jQuery</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <style>
        #box {
            width: 200px;
            height: 200px;
            background-color: #007bff;
            color: white;
            text-align: center;
            line-height: 200px;
            margin: 20px;
        }
    </style>
</head>
<body>

    <h1>Effects and Animations in jQuery</h1>

    <button id="btnShow">Show</button>
    <button id="btnHide">Hide</button>
    <button id="btnToggle">Toggle</button>
    <button id="btnFadeIn">Fade In</button>
    <button id="btnFadeOut">Fade Out</button>
    <button id="btnFadeToggle">Fade Toggle</button>
    <button id="btnSlideDown">Slide Down</button>
    <button id="btnSlideUp">Slide Up</button>
    <button id="btnSlideToggle">Slide Toggle</button>
    <button id="btnAnimate">Animate</button>

    <div id="box">Box</div>

    <script>
        $(document).ready(function() {
            $('#btnShow').click(function() {
                $('#box').show();
            });

            $('#btnHide').click(function() {
                $('#box').hide();
            });

            $('#btnToggle').click(function() {
                $('#box').toggle();
            });

            $('#btnFadeIn').click(function() {
                $('#box').fadeIn();
            });

            $('#btnFadeOut').click(function() {
                $('#box').fadeOut();
            });

            $('#btnFadeToggle').click(function() {
                $('#box').fadeToggle();
            });

            $('#btnSlideDown').click(function() {
                $('#box').slideDown();
            });

            $('#btnSlideUp').click(function() {
                $('#box').slideUp();
            });

            $('#btnSlideToggle').click(function() {
                $('#box').slideToggle();
            });

            $('#btnAnimate').click(function() {
                $('#box').animate({
                    opacity: 0.5,
                    width: '200px',
                    height: '200px',
                    backgroundColor: 'red'
                }, 1000, 'easeOutQuad');
            });
        });
    </script>

</body>
</html>
```


# Only animation part

```html
<html lang="en">

<head>
    <title>Simple Animation Example with jQuery</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <style>
        #box {
            width: 200px;
            height: 200px;
            background-color: #007bff;
            color: white;
        }
    </style>
</head>

<body>

    <button id="btnAnimate">Animate</button>
    <div id="box"></div>

    <script>
        $(document).ready(function () {
            $('#btnAnimate').click(function () {
                $('#box').animate({
                    width: 'toggle'
                });
            });
        });
    </script>

</body>

</html>
```


# Basic Effect code :
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

    <style>
        #box{
            height: 100px;
            width: 100px;
            background-color: red;
        }
    </style>
</head>
<body>
    <button id = "btn1">Hide</button>
    <button id = "btn2">Show</button>
    <div id="box"></div>
</body>
<script>
    $(document).ready(function(){
        $('#btn1').click(function(){
            $('#box').hide();
        })
        $('#btn2').click(function(){
            $('#box').show();
        })
    })
</script>
</html>
```


# Traversing in jQuery

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

    <title>Document</title>
</head>
<body>
    <div class="container">
        <li class="item1">Item1</li>
        <li class="item2">Item2</li>
        <li class="item3">Item3</li>
    </div>
</body>
<script>
    $(document).ready(function(){
        let e1 = $('.container').parent()
        console.log(e1.prop('tagName')) // container ka maa ya baap : BODY 

        let e2 = $('.item1').next()
        console.log(e2.text()) // item 1 ka next Item2 

        let e3 = $('.item2').prev()
        console.log(e3.text()) // item2 ka previous Item1

        let e4 = $('div').children()
        console.log(e4.prop("tagName")); // div ka children : LI

        let first = $('div').children().first()
        console.log(first.text()) // div ke pehle bacche ka naam : Item1

        let last = $('div').children().last()
        console.log(last.text()) // div ke aakri bacche ka naam : Item3

        let all = $('div').find('li')
        console.log(all.text()) // div ke saare bacchon ka naam : Item1, Item2, Item3

    })


</script>
</html>
```

# Filtering :

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Filtering Elements in jQuery</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <style>
        .list-item {
            margin: 5px;
            padding: 10px;
            background-color: #f0f0f0;
            border: 1px solid #ccc;
        }
        .selected {
            background-color: #007bff;
            color: white;
        }
    </style>
</head>
<body>

    <h1>Filtering Elements in jQuery</h1>

    <ul id="myList">
        <li class="list-item">Hello</li>
        <li class="list-item">Item 2</li>
        <li class="list-item">Item 3</li>
        <li class="list-item">Item 4</li>
        <li class="list-item">Item 5</li>
        <li class="list-item">Item 6</li>
    </ul>

    <script>
        $(document).ready(function() {
            // Basic Filters
            var e1 = $('li:first');
            console.log('First item:', e1.text());

            // considers indices as (even / odd) confuse ni hona so output :item{Hello, 3, 5 }
            let even = $('li:even');
            console.log("Even Items : ", even.text());

            var e2 = $('li:odd');
            console.log('Odd items:', e2.text());

            // Content Filters
            var e3 = $('li:contains("Hello")');
            console.log('Items containing "Hello":', e3.text());

            var e4 = $('ul:has(li)');
            console.log('Items with <li> element:', e4.text());
        });
    </script>

</body>
</html>
```
