# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨



    TASK FOR WEEK 7
HTML. BASIC STRUCTURE    
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Animation with localStorage</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <button id="animateBtn">Click to Animate</button>
        <p id="statusMessage">Welcome! Click the button to trigger animation.</p>
    </div>
    <script src="script.js"></script>
</body>
</html>

CSS: CREATING AMINATION AND BUTTON              STYLE
/* Basic styling */
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
}

.container {
    text-align: center;
}

/* Button Style */
button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    border: none;
    border-radius: 5px;
    background-color: #3498db;
    color: white;
    transition: transform 0.3s ease;
}

/* Animation Keyframes */
@keyframes buttonAnimation {
    0% {
        transform: scale(1);
        opacity: 1;
    }
    50% {
        transform: scale(1.2);
        opacity: 0.7;
    }
    100% {
        transform: scale(1);
        opacity: 1;
    }
}

/* Applied animation class */
.animate {
    animation: buttonAnimation 0.5s ease-out forwards;
}

/* Button clicked style */
.clicked {
    background-color: #2ecc71;
}

JAVASCRIPT: HANDLING BUTTON CLICK AND LOCAL STORAGE.

// Get DOM elements
const animateBtn = document.getElementById('animateBtn');
const statusMessage = document.getElementById('statusMessage');

// Check if the animation has been triggered before
if (localStorage.getItem('buttonClicked') === 'true') {
    animateBtn.classList.add('clicked');
    statusMessage.innerText = 'You have already clicked the button!';
}

// Add event listener to the button
animateBtn.addEventListener('click', () => {
    // Trigger the animation
    animateBtn.classList.add('animate');
    animateBtn.classList.add('clicked');
    statusMessage.innerText = 'Button clicked! Animation triggered!';

    // Store data in localStorage to remember the user preference
    localStorage.setItem('buttonClicked', 'true');
});
