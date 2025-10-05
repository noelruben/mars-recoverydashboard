<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mars recovery dashboard</title>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mars Recovery Station - Login</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(rgba(10, 10, 30, 0.9), rgba(10, 10, 30, 0.9)),
                        url('https://images.unsplash.com/photo-1615430535007-94da764325d0?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80');
            background-size: cover;
            background-position: center;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
        }

        .login-container {
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            width: 100%;
            max-width: 400px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid rgba(255, 255, 255, 0.1);
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .login-container::before {
            content: "";
            position: absolute;
            top: -50px;
            left: -50px;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle, rgba(255, 107, 107, 0.3) 0%, transparent 70%);
            border-radius: 50%;
        }

        .login-container::after {
            content: "";
            position: absolute;
            bottom: -30px;
            right: -30px;
            width: 80px;
            height: 80px;
            background: radial-gradient(circle, rgba(78, 205, 196, 0.2) 0%, transparent 70%);
            border-radius: 50%;
        }

        .login-header h1 {
            font-size: 2.2rem;
            margin-bottom: 10px;
            color: #ff6b6b;
            text-shadow: 0 0 10px rgba(255, 107, 107, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .login-header p {
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 30px;
            font-size: 0.95rem;
        }

        .form-group {
            margin-bottom: 20px;
            text-align: left;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 500;
        }

        .form-group input {
            width: 100%;
            padding: 12px 15px;
            border-radius: 8px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            background: rgba(255, 255, 255, 0.1);
            color: white;
            font-size: 1rem;
            transition: all 0.3s;
        }

        .form-group input:focus {
            outline: none;
            border-color: #ff6b6b;
            background: rgba(255, 255, 255, 0.15);
            box-shadow: 0 0 0 2px rgba(255, 107, 107, 0.3);
        }

        .form-group input::placeholder {
            color: rgba(255, 255, 255, 0.6);
        }

        .btn {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            border: none;
            background: linear-gradient(135deg, #ff6b6b, #e94560);
            color: white;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.3);
        }

        .btn i {
            font-size: 1.1rem;
        }

        /* Google Sign-In Button Container */
        .google-signin-container {
            margin-bottom: 20px;
            display: flex;
            justify-content: center;
        }

        /* Style for the Google Sign-In button */
        #googleSignInButton {
            width: 100%;
            height: 44px;
            border-radius: 8px;
            border: none;
            background: white;
            color: #757575;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: all 0.3s;
        }

        #googleSignInButton:hover {
            background: #f5f5f5;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        .divider {
            display: flex;
            align-items: center;
            margin: 20px 0;
            color: rgba(255, 255, 255, 0.5);
            font-size: 0.9rem;
        }

        .divider::before, .divider::after {
            content: "";
            flex: 1;
            border-bottom: 1px solid rgba(255, 255, 255, 0.2);
        }

        .signup-link {
            text-align: center;
            margin-top: 20px;
            color: rgba(255, 255, 255, 0.8);
            font-size: 0.9rem;
        }

        .signup-link a {
            color: #4ecdc4;
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        .signup-link a:hover {
            color: #ff6b6b;
            text-decoration: underline;
        }

        .mars-icon {
            font-size: 2.5rem;
            color: #ff6b6b;
            margin-bottom: 15px;
            text-shadow: 0 0 10px rgba(255, 107, 107, 0.3);
        }

        /* Fix for Google Sign-In button positioning */
        .g_id_signin {
            width: 100% !important;
            height: 44px !important;
            margin: 0 auto !important;
        }

        /* Make sure Google's iframe has proper styling */
        iframe {
            border-radius: 8px !important;
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Sign-In API -->
    <script src="https://accounts.google.com/gsi/client" async defer></script>
</head>
<body>
    <div class="login-container">
        <div class="login-header">
            <i class="fas fa-rocket mars-icon"></i>
            <h1>
                <i class="fas fa-recycle"></i> Mars Recovery
            </h1>
            <p>Sign in to access the waste recycling dashboard</p>
        </div>

        <!-- Google Sign-In Button Container -->
        <div class="google-signin-container">
            <!-- Google Sign-In Button will be inserted here by the API -->
            <div id="g_id_onload"
                 data-client_id="YOUR_GOOGLE_CLIENT_ID.apps.googleusercontent.com"
                 data-context="signin"
                 data-ux_mode="popup"
                 data-callback="handleGoogleSignIn"
                 data-auto_prompt="false">
            </div>

            <div class="g_id_signin"
                 data-type="standard"
                 data-shape="rectangular"
                 data-theme="filled_blue"
                 data-text="signin_with"
                 data-size="large"
                 data-logo_alignment="left"
                 id="googleSignInButton">
            </div>
        </div>

        <div class="divider">or</div>

        <!-- Email/Password Form with Sign Up Link -->
        <form id="loginForm">
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" placeholder="Enter your email" required>
            </div>

            <div class="form-group">
                <label for="password">Password</label>
                <input type="password" id="password" placeholder="Enter your password" required>
            </div>

            <button type="submit" class="btn">
                <i class="fas fa-sign-in-alt"></i> Sign In
            </button>
        </form>

        <div class="signup-link">
            Don't have an account? <a href="#" onclick="showSignup()">Sign up</a>
        </div>

        <!-- Sign Up Form (hidden by default) -->
        <form id="signupForm" style="display: none;">
            <div class="form-group">
                <label for="signupName">Full Name</label>
                <input type="text" id="signupName" placeholder="Enter your full name" required>
            </div>

            <div class="form-group">
                <label for="signupEmail">Email</label>
                <input type="email" id="signupEmail" placeholder="Enter your email" required>
            </div>

            <div class="form-group">
                <label for="signupPassword">Password</label>
                <input type="password" id="signupPassword" placeholder="Create a password" required>
            </div>

            <div class="form-group">
                <label for="confirmPassword">Confirm Password</label>
                <input type="password" id="confirmPassword" placeholder="Confirm your password" required>
            </div>

            <button type="submit" class="btn">
                <i class="fas fa-user-plus"></i> Create Account
            </button>
        </form>

        <div class="login-link" style="display: none;" id="backToLogin">
            Already have an account? <a href="#" onclick="showLogin()">Log in</a>
        </div>
    </div>

    <script>
        // Show signup form
        function showSignup() {
            document.getElementById('loginForm').style.display = 'none';
            document.getElementById('signupForm').style.display = 'block';
            document.getElementById('backToLogin').style.display = 'block';
            document.querySelector('.signup-link').style.display = 'none';
            document.querySelector('.divider').style.display = 'none';
            document.querySelector('.google-signin-container').style.display = 'none';
        }

        // Show login form
        function showLogin() {
            document.getElementById('loginForm').style.display = 'block';
            document.getElementById('signupForm').style.display = 'none';
            document.getElementById('backToLogin').style.display = 'none';
            document.querySelector('.signup-link').style.display = 'block';
            document.querySelector('.divider').style.display = 'block';
            document.querySelector('.google-signin-container').style.display = 'block';
        }

        // Handle login form submission
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            const email = document.getElementById('email').value;
            const password = document.getElementById('password').value;

            // Simple validation for demo
            if (email && password) {
                localStorage.setItem('isLoggedIn', 'true');
                window.location.href = 'dashboard.html';
            }
        });

        // Handle signup form submission
        document.getElementById('signupForm').addEventListener('submit', function(e) {
            e.preventDefault();

            const name = document.getElementById('signupName').value;
            const email = document.getElementById('signupEmail').value;
            const password = document.getElementById('signupPassword').value;
            const confirmPassword = document.getElementById('confirmPassword').value;

            // Simple validation for demo
            if (password !== confirmPassword) {
                alert('Passwords do not match!');
                return;
            }

            if (name && email && password) {
                localStorage.setItem('isLoggedIn', 'true');
                localStorage.setItem('userName', name);
                alert('Account created successfully!');
                window.location.href = 'dashboard.html';
            }
        });

        // Handle Google Sign-In
        function handleGoogleSignIn(response) {
            console.log('Google Sign-In response:', response);
            // In a real app, you would handle the response and authenticate the user
            localStorage.setItem('isLoggedIn', 'true');
            window.location.href = 'dashboard.html';
        }

        // Initialize Google Sign-In
        function initializeGoogleSignIn() {
            google.accounts.id.initialize({
                client_id: 'YOUR_GOOGLE_CLIENT_ID.apps.googleusercontent.com',
                callback: handleGoogleSignIn
            });

            // Render the Google Sign-In button
            google.accounts.id.renderButton(
                document.getElementById('googleSignInButton'),
                {
                    theme: 'filled_blue',
                    size: 'large',
                    text: 'signin_with',
                    shape: 'rectangular',
                    logo_alignment: 'left'
                }
            );
        }

        // Check if user is already logged in
        if (localStorage.getItem('isLoggedIn') === 'true') {
            window.location.href = 'dashboard.html';
        }

        // Load Google Sign-In API properly
        window.onload = function() {
            initializeGoogleSignIn();
        };
    </script>
</body>
</html>
