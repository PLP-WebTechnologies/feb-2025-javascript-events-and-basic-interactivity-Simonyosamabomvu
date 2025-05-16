<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Playground</title>
    <style>
        /* Base Styles */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f5f5f5;
        }

        header {
            text-align: center;
            margin-bottom: 40px;
        }

        h1, h2 {
            color: #2c3e50;
        }

        section {
            background: white;
            border-radius: 8px;
            padding: 20px;
            margin-bottom: 30px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        /* Event Handling Styles */
        .event-box {
            border: 1px solid #ddd;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        .hover-box:hover {
            background-color: #f0f8ff;
            transform: translateY(-3px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .secret-box {
            cursor: pointer;
            background-color: #fffaf0;
        }

        /* Interactive Elements Styles */
        .interactive-box {
            margin-bottom: 20px;
        }

        #color-changer {
            padding: 10px 20px;
            background-color: #3498db;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .image-gallery {
            position: relative;
            max-width: 400px;
            margin: 0 auto;
        }

        .image-gallery img {
            display: none;
            width: 100%;
            border-radius: 5px;
        }

        .image-gallery img.active {
            display: block;
            animation: fadeIn 0.5s;
        }

        .gallery-controls {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
        }

        .tabs {
            border: 1px solid #ddd;
            border-radius: 5px;
            overflow: hidden;
        }

        .tab-buttons {
            display: flex;
            background-color: #f1f1f1;
        }

        .tab-btn {
            padding: 10px 20px;
            border: none;
            background: none;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .tab-btn.active {
            background-color: #3498db;
            color: white;
        }

        .tab-content {
            padding: 15px;
            display: none;
        }

        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s;
        }

        /* Form Validation Styles */
        #user-form {
            max-width: 500px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }

        input {
            width: 100%;
            padding: 8px;
            border: 1px solid #ddd;
            border-radius: 4px;
            box-sizing: border-box;
        }

        input:focus {
            outline: none;
            border-color: #3498db;
            box-shadow: 0 0 5px rgba(52, 152, 219, 0.5);
        }

        .error-message {
            color: #e74c3c;
            font-size: 0.8em;
            height: 18px;
            display: block;
        }

        .password-strength {
            margin-top: 5px;
        }

        .strength-bar {
            display: block;
            height: 5px;
            background-color: #eee;
            border-radius: 2px;
            margin-bottom: 3px;
            transition: width 0.3s, background-color 0.3s;
        }

        .strength-text {
            font-size: 0.8em;
            color: #7f8c8d;
        }

        button[type="submit"] {
            background-color: #2ecc71;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button[type="submit"]:hover {
            background-color: #27ae60;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            body {
                padding: 10px;
            }
        
            .tab-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <header>
        <h1>JavaScript Playground 🎪</h1>
    </header>

    <main>
        <!-- Event Handling Section -->
        <section id="event-handling">
            <h2>Event Handling 🎈</h2>
            
            <div class="event-box">
                <button id="click-button">Click Me!</button>
                <p id="click-output">Button not clicked yet</p>
            </div>
            
            <div class="event-box hover-box">
                <p>Hover over me!</p>
                <p id="hover-output">Waiting for hover...</p>
            </div>
            
            <div class="event-box">
                <input type="text" id="keypress-input" placeholder="Type something...">
                <p id="keypress-output">No keypress detected yet</p>
            </div>
            
            <div class="event-box secret-box">
                <p>Double click or long press me for a secret!</p>
                <p id="secret-output">🤫</p>
            </div>
        </section>

        <!-- Interactive Elements Section -->
        <section id="interactive-elements">
            <h2>Interactive Elements 🎮</h2>
            
            <div class="interactive-box">
                <button id="color-changer">Change My Color!</button>
            </div>
            
            <div class="interactive-box">
                <div class="image-gallery">
                    <img src="https://picsum.photos/id/237/400/300" alt="Gallery image" class="active">
                    <img src="https://picsum.photos/id/238/400/300" alt="Gallery image">
                    <img src="https://picsum.photos/id/239/400/300" alt="Gallery image">
                    <div class="gallery-controls">
                        <button id="prev-btn">← Previous</button>
                        <button id="next-btn">Next →</button>
                    </div>
                </div>
            </div>
            
            <div class="interactive-box">
                <div class="tabs">
                    <div class="tab-buttons">
                        <button class="tab-btn active" data-tab="tab1">Tab 1</button>
                        <button class="tab-btn" data-tab="tab2">Tab 2</button>
                        <button class="tab-btn" data-tab="tab3">Tab 3</button>
                    </div>
                    <div class="tab-content active" id="tab1">
                        <p>Content for Tab 1 goes here.</p>
                    </div>
                    <div class="tab-content" id="tab2">
                        <p>Content for Tab 2 goes here.</p>
                    </div>
                    <div class="tab-content" id="tab3">
                        <p>Content for Tab 3 goes here.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Form Validation Section -->
        <section id="form-validation">
            <h2>Form Validation 📋✅</h2>
            
            <form id="user-form">
                <div class="form-group">
                    <label for="username">Username (required):</label>
                    <input type="text" id="username" name="username">
                    <span class="error-message" id="username-error"></span>
                </div>
                
                <div class="form-group">
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email">
                    <span class="error-message" id="email-error"></span>
                </div>
                
                <div class="form-group">
                    <label for="password">Password (min 8 chars):</label>
                    <input type="password" id="password" name="password">
                    <span class="error-message" id="password-error"></span>
                    <div class="password-strength">
                        <span class="strength-bar"></span>
                        <span class="strength-text">Password strength</span>
                    </div>
                </div>
                
                <button type="submit">Submit</button>
            </form>
        </section>
    </main>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // Event Handling
            const clickButton = document.getElementById('click-button');
            const clickOutput = document.getElementById('click-output');
            clickButton.addEventListener('click', function() {
                clickOutput.textContent = 'Button was clicked! 🎉';
                clickOutput.style.color = '#2ecc71';
            });
            
            const hoverBox = document.querySelector('.hover-box');
            const hoverOutput = document.getElementById('hover-output');
            hoverBox.addEventListener('mouseenter', function() {
                hoverOutput.textContent = 'Hover detected! ✨';
                hoverOutput.style.color = '#3498db';
            });
            hoverBox.addEventListener('mouseleave', function() {
                hoverOutput.textContent = 'Waiting for hover...';
                hoverOutput.style.color = '';
            });
            
            const keypressInput = document.getElementById('keypress-input');
            const keypressOutput = document.getElementById('keypress-output');
            keypressInput.addEventListener('keypress', function(e) {
                keypressOutput.textContent = `Key pressed: ${e.key} (Code: ${e.keyCode})`;
                keypressOutput.style.color = '#9b59b6';
            });
            
            const secretBox = document.querySelector('.secret-box');
            const secretOutput = document.getElementById('secret-output');
            let pressTimer;
            secretBox.addEventListener('dblclick', function() {
                secretOutput.textContent = 'You found the double-click secret! 🎊';
                animateSecretOutput();
            });
            secretBox.addEventListener('mousedown', function() {
                pressTimer = setTimeout(function() {
                    secretOutput.textContent = 'You found the long press secret! 🎁';
                    animateSecretOutput();
                }, 1000);
            });
            secretBox.addEventListener('mouseup', function() {
                clearTimeout(pressTimer);
            });
            secretBox.addEventListener('mouseleave', function() {
                clearTimeout(pressTimer);
            });
            function animateSecretOutput() {
                secretOutput.style.transition = 'all 0.3s';
                secretOutput.style.color = '#e74c3c';
                secretOutput.style.fontWeight = 'bold';
                secretOutput.style.transform = 'scale(1.1)';
                setTimeout(function() {
                    secretOutput.style.transform = 'scale(1)';
                }, 300);
            }
            
            // Interactive Elements
            const colorChanger = document.getElementById('color-changer');
            const colors = ['#3498db', '#2ecc71', '#e74c3c', '#9b59b6', '#f1c40f'];
            let colorIndex = 0;
            colorChanger.addEventListener('click', function() {
                colorIndex = (colorIndex + 1) % colors.length;
                this.style.backgroundColor = colors[colorIndex];
                this.textContent = `Color Changed! (${colorIndex + 1}/${colors.length})`;
                this.style.transform = 'scale(1.05)';
                setTimeout(() => {
                    this.style.transform = 'scale(1)';
                }, 200);
            });
            
            const images = document.querySelectorAll('.image-gallery img');
            const prevBtn = document.getElementById('prev-btn');
            const nextBtn = document.getElementById('next-btn');
            let currentImageIndex = 0;
            function showImage(index) {
                images.forEach(img => img.classList.remove('active'));
                images[index].classList.add('active');
            }
            prevBtn.addEventListener('click', function() {
                currentImageIndex = (currentImageIndex - 1 + images.length) % images.length;
                showImage(currentImageIndex);
            });
            nextBtn.addEventListener('click', function() {
                currentImageIndex = (currentImageIndex + 1) % images.length;
                showImage(currentImageIndex);
            });
            setInterval(function() {
                currentImageIndex = (currentImageIndex + 1) % images.length;
                showImage(currentImageIndex);
            }, 3000);
            
            const tabButtons = document.querySelectorAll('.tab-btn');
            const tabContents = document.querySelectorAll('.tab-content');
            tabButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const tabId = this.getAttribute('data-tab');
                    tabButtons.forEach(btn => btn.classList.remove('active'));
                    tabContents.forEach(content => content.classList.remove('active'));
                    this.classList.add('active');
                    document.getElementById(tabId).classList.add('active');
                });
            });
            
            // Form Validation
            const userForm = document.getElementById('user-form');
            const usernameInput = document.getElementById('username');
            const emailInput = document.getElementById('email');
            const passwordInput = document.getElementById('password');
            const usernameError = document.getElementById('username-error');
            const emailError = document.getElementById('email-error');
            const passwordError = document.getElementById('password-error');
            const strengthBar = document.querySelector('.strength-bar');
            const strengthText = document.querySelector('.strength-text');
            
            usernameInput.addEventListener('input', validateUsername);
            emailInput.addEventListener('input', validateEmail);
            passwordInput.addEventListener('input', validatePassword);
            
            userForm.addEventListener('submit', function(e) {
                e.preventDefault();
                if (validateUsername() && validateEmail() && validatePassword()) {
                    alert('Form submitted successfully!');
                    userForm.reset();
                    resetFormValidation();
                } else {
                    alert('Please fix the errors before submitting.');
                }
            });
            
            function validateUsername() {
                const value = usernameInput.value.trim();
                if (value === '') {
                    usernameError.textContent = 'Username is required';
                    usernameInput.style.borderColor = '#e74c3c';
                    return false;
                } else if (value.length < 3) {
                    usernameError.textContent = 'Username must be at least 3 characters';
                    usernameInput.style.borderColor = '#e74c3c';
                    return false;
                } else {
                    usernameError.textContent = '';
                    usernameInput.style.borderColor = '#2ecc71';
                    return true;
                }
            }
            
            function validateEmail() {
                const value = emailInput.value.trim();
                const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
                if (value === '') {
                    emailError.textContent = 'Email is required';
                    emailInput.style.borderColor = '#e74c3c';
                    return false;
                } else if (!emailRegex.test(value)) {
                    emailError.textContent = 'Please enter a valid email';
                    emailInput.style.borderColor = '#e74c3c';
                    return false;
                } else {
                    emailError.textContent = '';
                    emailInput.style.borderColor = '#2ecc71';
                    return true;
                }
            }
            
            function validatePassword() {
                const value = passwordInput.value;
                let isValid = true;
                let strength = 0;
                let messages = [];
                
                if (value === '') {
                    passwordError.textContent = 'Password is required';
                    passwordInput.style.borderColor = '#e74c3c';
                    updatePasswordStrength(0);
                    return false;
                }
                
                if (value.length < 8) {
                    messages.push('Password must be at least 8 characters');
                    isValid = false;
                } else strength += 1;
                
                if (!/\d/.test(value)) {
                    messages.push('Add at least one number');
                    isValid = false;
                } else strength += 1;
                
                if (!/[a-zA-Z]/.test(value)) {
                    messages.push('Add at least one letter');
                    isValid = false;
                } else strength += 1;
                
                if (!/[^a-zA-Z0-9]/.test(value)) {
                    messages.push('Add at least one special character');
                    isValid = false;
                } else strength += 1;
                
                passwordError.textContent = messages.join('. ');
                passwordInput.style.borderColor = isValid ? '#2ecc71' : '#e74c3c';
                updatePasswordStrength(strength);
                return isValid;
            }
            
            function updatePasswordStrength(strength) {
                const strengthColors = ['#e74c3c', '#f39c12', '#f1c40f', '#2ecc71'];
                const strengthLabels = ['Weak', 'Fair', 'Good', 'Strong'];
                strengthBar.style.width = `${strength * 25}%`;
                strengthBar.style.backgroundColor = strengthColors[strength - 1] || '#e74c3c';
                strengthText.textContent = strength > 0 ? strengthLabels[strength - 1] : '';
                strengthText.style.color = strengthColors[strength - 1] || '#e74c3c';
            }
            
            function resetFormValidation() {
                usernameError.textContent = '';
                emailError.textContent = '';
                passwordError.textContent = '';
                strengthBar.style.width = '0';
                strengthText.textContent = 'Password strength';
                strengthText.style.color = '#7f8c8d';
                usernameInput.style.borderColor = '#ddd';
                emailInput.style.borderColor = '#ddd';
                passwordInput.style.borderColor = '#ddd';
            }
        });
    </script>
</body>
</html>
