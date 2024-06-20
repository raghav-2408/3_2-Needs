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
