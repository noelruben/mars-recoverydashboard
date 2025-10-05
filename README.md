# mars-recoverydashboard
<video autoplay muted loop>
  <source src="Website_Explanation_Video_Ready.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
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
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mars Recovery Station - Dashboard</title>
    <style>
        :root {
            --primary: #1a1a2e;
            --secondary: #16213e;
            --accent: #ff6b6b;
            --highlight: #4ecdc4;
            --space-bg: linear-gradient(rgba(10, 10, 30, 0.8), rgba(10, 10, 30, 0.8)),
                        url('https://images.unsplash.com/photo-1615430535007-94da764325d0?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80');
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: var(--space-bg);
            background-size: cover;
            background-position: center;
            color: white;
            min-height: 100vh;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
            background: rgba(0, 0, 0, 0.5);
        }

        .header h1 {
            font-size: 1.8rem;
            color: white;
            text-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
        }

        .logout-btn {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .logout-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        .dashboard-container {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
            max-width: 1400px;
            margin: 20px auto;
            padding: 0 20px;
        }

        .control-panel, .results-panel {
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .panel-title {
            color: var(--accent);
            margin-top: 0;
            margin-bottom: 20px;
            font-size: 1.4rem;
            border-bottom: 1px solid var(--highlight);
            padding-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 5px;
            color: rgba(255, 255, 255, 0.9);
            font-weight: 500;
        }

        .form-group input {
            width: 100%;
            padding: 10px;
            border-radius: 8px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            background: rgba(255, 255, 255, 0.1);
            color: white;
            font-size: 1rem;
        }

        .btn {
            background: linear-gradient(135deg, var(--accent), #e94560);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            width: 100%;
            margin-top: 10px;
            transition: all 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.3);
        }

        #threejs-container {
            width: 100%;
            height: 300px;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 10px;
            margin: 20px 0;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .results-container {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .next-page-btn {
            background: var(--highlight);
            margin-top: 20px;
            display: inline-block;
            width: auto;
            padding: 10px 20px;
        }

        @media (max-width: 768px) {
            .dashboard-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/build/three.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/examples/js/controls/OrbitControls.js"></script>
</head>
<body>
    <div class="header">
        <h1>Mars Recovery Station</h1>
        <button class="logout-btn" onclick="logout()">Logout</button>
    </div>

    <div class="dashboard-container">
        <!-- Control Panel -->
        <div class="control-panel">
            <h2 class="panel-title"><i class="fas fa-cogs"></i> Control Panel</h2>

            <h3>Material Intake</h3>
            <div class="form-group">
                <label for="eva-suit">EVA Suit Fabric (kg)</label>
                <input type="number" id="eva-suit" placeholder="e.g., 12" value="12">
            </div>

            <div class="form-group">
                <label for="air-filters">Used Air Filters (kg)</label>
                <input type="number" id="air-filters" placeholder="e.g., 30" value="30">
            </div>

            <div class="form-group">
                <label for="carbon-scraps">Carbon Scraps (kg)</label>
                <input type="number" id="carbon-scraps" placeholder="e.g., 5" value="5">
            </div>

            <button class="btn" onclick="optimizeRecycling()">
                <i class="fas fa-recycle"></i> Optimize Recycling
            </button>

            <h3 style="margin-top: 30px;">3D Recovery Station Overview</h3>
            <div id="threejs-container"></div>

            <button class="btn next-page-btn" onclick="window.location.href='results.html'">
                View Detailed Results <i class="fas fa-arrow-right"></i>
            </button>
        </div>

        <!-- Results Preview -->
        <div class="results-panel">
            <h2 class="panel-title"><i class="fas fa-chart-line"></i> Quick Results Preview</h2>
            <div id="previewResults">
                <p style="text-align: center; color: rgba(255, 255, 255, 0.7);">
                    Enter material quantities and click "Optimize Recycling" to see a preview.
                </p>
            </div>
        </div>
    </div>

    <script>
        // Check if user is logged in
        if (localStorage.getItem('isLoggedIn') !== 'true') {
            window.location.href = 'index.html';
        }

        // Logout function
        function logout() {
            localStorage.removeItem('isLoggedIn');
            window.location.href = 'index.html';
        }

        // Initialize Three.js Mars Visualization
        document.addEventListener('DOMContentLoaded', function() {
            initThreeJS();
        });

        function initThreeJS() {
            const container = document.getElementById('threejs-container');

            // Scene setup
            const scene = new THREE.Scene();
            scene.background = new THREE.Color(0x000000);

            // Camera setup
            const camera = new THREE.PerspectiveCamera(75, container.clientWidth / container.clientHeight, 0.1, 1000);
            camera.position.z = 10;

            // Renderer setup
            const renderer = new THREE.WebGLRenderer({ antialias: true });
            renderer.setSize(container.clientWidth, container.clientHeight);
            container.appendChild(renderer.domElement);

            // Controls for orbiting the 3D model
            const controls = new THREE.OrbitControls(camera, renderer.domElement);
            controls.enableDamping = true;
            controls.dampingFactor = 0.05;

            // Lighting - Sunlight simulation
            const ambientLight = new THREE.AmbientLight(0x404040, 0.5);
            scene.add(ambientLight);

            const directionalLight = new THREE.DirectionalLight(0xffffff, 1);
            directionalLight.position.set(5, 10, 7);
            directionalLight.castShadow = true;
            directionalLight.shadow.mapSize.width = 1024;
            directionalLight.shadow.mapSize.height = 1024;
            scene.add(directionalLight);

            // Create Mars surface with improved texture
            const marsTexture = new THREE.TextureLoader().load('https://upload.wikimedia.org/wikipedia/commons/thumb/0/02/OSIRIS_Mars_true_color.jpg/1200px-OSIRIS_Mars_true_color.jpg');
            const marsBumpMap = new THREE.TextureLoader().load('https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Mars_topography.jpg/1200px-Mars_topography.jpg');

            const marsGeometry = new THREE.SphereGeometry(5, 64, 64);
            const marsMaterial = new THREE.MeshStandardMaterial({
                map: marsTexture,
                bumpMap: marsBumpMap,
                bumpScale: 0.05,
                metalness: 0.1,
                roughness: 0.7
            });

            const mars = new THREE.Mesh(marsGeometry, marsMaterial);
            mars.receiveShadow = true;
            scene.add(mars);

            // Add atmosphere effect
            const atmosphereGeometry = new THREE.SphereGeometry(5.2, 64, 64);
            const atmosphereMaterial = new THREE.MeshStandardMaterial({
                color: 0x3366cc,
                transparent: true,
                opacity: 0.2,
                side: THREE.BackSide
            });
            const atmosphere = new THREE.Mesh(atmosphereGeometry, atmosphereMaterial);
            scene.add(atmosphere);

            // Create a more detailed recovery station
            createRecoveryStation(scene);

            // Animation loop
            function animate() {
                requestAnimationFrame(animate);
                controls.update();
                renderer.render(scene, camera);
                mars.rotation.y += 0.001;
            }

            // Handle window resize
            window.addEventListener('resize', function() {
                camera.aspect = container.clientWidth / container.clientHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(container.clientWidth, container.clientHeight);
            });

            animate();
        }

        function createRecoveryStation(scene) {
            // Base platform
            const baseGeometry = new THREE.CylinderGeometry(2, 2, 0.3, 32);
            const baseMaterial = new THREE.MeshStandardMaterial({
                color: 0x333333,
                metalness: 0.3,
                roughness: 0.7
            });
            const base = new THREE.Mesh(baseGeometry, baseMaterial);
            base.position.y = 0.15;
            base.position.z = -6;
            base.receiveShadow = true;
            base.castShadow = true;
            scene.add(base);

            // Main habitat dome
            const domeGeometry = new THREE.SphereGeometry(1.2, 32, 32, 0, Math.PI * 2, 0, Math.PI / 2);
            const domeMaterial = new THREE.MeshStandardMaterial({
                color: 0xaaaaaa,
                metalness: 0.2,
                roughness: 0.5,
                transparent: true,
                opacity: 0.8
            });
            const dome = new THREE.Mesh(domeGeometry, domeMaterial);
            dome.position.y = 1.2;
            dome.position.z = -6;
            dome.receiveShadow = true;
            dome.castShadow = true;
            scene.add(dome);

            // Solar panels
            const panelGeometry = new THREE.BoxGeometry(0.8, 0.05, 0.3);
            const panelMaterial = new THREE.MeshStandardMaterial({
                color: 0x222233,
                metalness: 0.7,
                roughness: 0.3
            });

            for (let i = 0; i < 4; i++) {
                const panel1 = new THREE.Mesh(panelGeometry, panelMaterial);
                panel1.position.set(-6 + i * 3, 1.5, -4);
                panel1.rotation.y = Math.PI / 4;
                panel1.castShadow = true;
                scene.add(panel1);

                const panel2 = new THREE.Mesh(panelGeometry, panelMaterial);
                panel2.position.set(-6 + i * 3, 1.5, -8);
                panel2.rotation.y = -Math.PI / 4;
                panel2.castShadow = true;
                scene.add(panel2);
            }

            // Processing units
            const unitGeometry = new THREE.CylinderGeometry(0.4, 0.4, 0.8, 32);

            // Thermal processor (red)
            const thermalMaterial = new THREE.MeshStandardMaterial({
                color: 0xff5555,
                metalness: 0.6,
                roughness: 0.4
            });
            const thermalUnit = new THREE.Mesh(unitGeometry, thermalMaterial);
            thermalUnit.position.set(-6, 0.8, -5);
            thermalUnit.castShadow = true;
            scene.add(thermalUnit);

            // Chemical processor (green)
            const chemicalMaterial = new THREE.MeshStandardMaterial({
                color: 0x55ff55,
                metalness: 0.6,
                roughness: 0.4
            });
            const chemicalUnit = new THREE.Mesh(unitGeometry, chemicalMaterial);
            chemicalUnit.position.set(-6, 0.8, -7);
            chemicalUnit.castShadow = true;
            scene.add(chemicalUnit);

            // Mechanical processor (blue)
            const mechanicalMaterial = new THREE.MeshStandardMaterial({
                color: 0x5555ff,
                metalness: 0.6,
                roughness: 0.4
            });
            const mechanicalUnit = new THREE.Mesh(unitGeometry, mechanicalMaterial);
            mechanicalUnit.position.set(-4, 0.8, -6);
            mechanicalUnit.castShadow = true;
            scene.add(mechanicalUnit);

            // Storage tanks
            const tankGeometry = new THREE.SphereGeometry(0.5, 32, 32);

            // Oxygen tank
            const oxygenMaterial = new THREE.MeshStandardMaterial({
                color: 0xaaaaff,
                metalness: 0.3,
                roughness: 0.7,
                transparent: true,
                opacity: 0.7
            });
            const oxygenTank = new THREE.Mesh(tankGeometry, oxygenMaterial);
            oxygenTank.position.set(-3, 1, -6);
            oxygenTank.castShadow = true;
            scene.add(oxygenTank);

            // Material storage tank
            const materialMaterial = new THREE.MeshStandardMaterial({
                color: 0xffaaaa,
                metalness: 0.3,
                roughness: 0.7,
                transparent: true,
                opacity: 0.7
            });
            const materialTank = new THREE.Mesh(tankGeometry, materialMaterial);
            materialTank.position.set(-3, 1, -7);
            materialTank.castShadow = true;
            scene.add(materialTank);

            // Add labels (simplified for this example)
            // In a real app, you might use CSS2DRenderer for better text rendering
        }

        // Optimize Recycling Function
        function optimizeRecycling() {
            const evaSuit = parseFloat(document.getElementById('eva-suit').value) || 0;
            const airFilters = parseFloat(document.getElementById('air-filters').value) || 0;
            const carbonScraps = parseFloat(document.getElementById('carbon-scraps').value) || 0;

            // Calculate results (simplified for demo)
            const totalInput = evaSuit + airFilters + carbonScraps;
            const oxygenRecovered = Math.round((evaSuit * 0.4 + carbonScraps * 0.6) * 10) / 10;
            const materialsRecovered = Math.round((evaSuit * 0.6 + airFilters * 0.3 + carbonScraps * 0.2) * 10) / 10;
            const dailyNeedPercentage = Math.min(Math.round((oxygenRecovered / 30) * 100), 100);

            // Update preview results
            const previewResults = document.getElementById('previewResults');
            previewResults.innerHTML = `
                <div style="background: rgba(255, 255, 255, 0.1); padding: 15px; border-radius: 10px;">
                    <h3>Quick Results</h3>
                    <p><strong>Total Input:</strong> ${totalInput} kg</p>
                    <p><strong>Oxygen Recovered:</strong> ${oxygenRecovered} kg (${dailyNeedPercentage}% of daily need)</p>
                    <p><strong>Materials Recovered:</strong> ${materialsRecovered} kg</p>
                    <p style="font-size: 0.9rem; color: rgba(255, 255, 255, 0.7);">
                        Click "View Detailed Results" for full analysis and visualizations.
                    </p>
                </div>
            `;

            // Store results for the results page
            localStorage.setItem('recyclingResults', JSON.stringify({
                evaSuit, airFilters, carbonScraps,
                oxygenRecovered, materialsRecovered, dailyNeedPercentage, totalInput
            }));
        }
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mars Recovery Station - Results</title>
    <style>
        :root {
            --primary: #1a1a2e;
            --secondary: #16213e;
            --accent: #ff6b6b;
            --highlight: #4ecdc4;
            --space-bg: linear-gradient(rgba(10, 10, 30, 0.8), rgba(10, 10, 30, 0.8)),
                        url('https://images.unsplash.com/photo-1615430535007-94da764325d0?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80');
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: var(--space-bg);
            background-size: cover;
            background-position: center;
            color: white;
            min-height: 100vh;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
            background: rgba(0, 0, 0, 0.5);
        }

        .header h1 {
            font-size: 1.8rem;
            color: white;
            text-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
        }

        .back-btn, .logout-btn {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            margin-left: 10px;
        }

        .back-btn:hover, .logout-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 0 20px;
        }

        .results-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .results-header h2 {
            font-size: 2rem;
            color: var(--accent);
            margin-bottom: 10px;
            text-shadow: 0 0 10px rgba(255, 107, 107, 0.3);
        }

        .results-header p {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
        }

        .results-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .result-card {
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
            max-height: 500px;
            overflow-y: auto;
        }

        .result-card h3 {
            color: var(--accent);
            margin-top: 0;
            margin-bottom: 15px;
            font-size: 1.3rem;
            border-bottom: 1px solid var(--highlight);
            padding-bottom: 10px;
        }

        .big-number {
            font-size: 2.5rem;
            font-weight: bold;
            color: white;
            text-align: center;
            margin: 20px 0;
            background: linear-gradient(135deg, var(--accent), var(--highlight));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
        }

        .big-number small {
            font-size: 1rem;
            color: rgba(255, 255, 255, 0.7);
            display: block;
            margin-top: 5px;
            background: none;
            -webkit-text-fill-color: initial;
        }

        .process-steps {
            margin-top: 15px;
        }

        .process-step {
            background: rgba(255, 255, 255, 0.1);
            padding: 10px 15px;
            border-radius: 8px;
            margin-bottom: 10px;
            font-size: 0.9rem;
        }

        .process-step h4 {
            color: var(--highlight);
            margin-bottom: 5px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .chart-container {
            background: rgba(0, 0, 0, 0.5);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 30px;
        }

        .chart-container h3 {
            color: var(--accent);
            margin-top: 0;
            margin-bottom: 20px;
            text-align: center;
            text-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
        }

        .navigation {
            display: flex;
            justify-content: space-between;
            margin-top: 30px;
            padding-bottom: 20px;
        }

        #resultsContent {
            max-width: 100%;
            overflow: hidden;
        }

        canvas {
            max-width: 100%;
            max-height: 400px;
            display: block;
            margin: 0 auto;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 8px;
            padding: 10px;
        }

        @media (max-width: 768px) {
            .results-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body>
    <div class="header">
        <div>
            <button class="back-btn" onclick="window.location.href='dashboard.html'">
                <i class="fas fa-arrow-left"></i> Back to Dashboard
            </button>
        </div>
        <h1>Mars Recovery Station</h1>
        <button class="logout-btn" onclick="logout()">Logout</button>
    </div>

    <div class="container">
        <div class="results-header">
            <h2>Recycling Optimization Results</h2>
            <p>Detailed analysis of your waste recycling process</p>
        </div>

        <div id="resultsContent">
            <p style="text-align: center; color: rgba(255, 255, 255, 0.7);">
                Loading results...
            </p>
        </div>

        <div class="navigation">
            <button class="back-btn" onclick="window.location.href='dashboard.html'">
                <i class="fas fa-arrow-left"></i> Back to Input
            </button>
            <button class="back-btn" onclick="window.location.href='visualization.html'">
                3D Visualization <i class="fas fa-arrow-right"></i>
            </button>
        </div>
    </div>

    <script>
        // Check if user is logged in
        if (localStorage.getItem('isLoggedIn') !== 'true') {
            window.location.href = 'index.html';
        }

        // Logout function
        function logout() {
            localStorage.removeItem('isLoggedIn');
            window.location.href = 'index.html';
        }

        // Load results when page loads
        document.addEventListener('DOMContentLoaded', function() {
            const results = JSON.parse(localStorage.getItem('recyclingResults'));

            if (results) {
                displayResults(results);
            } else {
                document.getElementById('resultsContent').innerHTML = `
                    <div style="text-align: center; color: rgba(255, 255, 255, 0.7);">
                        <p>No results found. Please go back to the dashboard and run an optimization first.</p>
                    </div>
                `;
            }
        });

        function displayResults(results) {
            const content = document.getElementById('resultsContent');

            content.innerHTML = `
                <div class="results-grid">
                    <!-- Oxygen Recovery Card -->
                    <div class="result-card">
                        <h3>Oxygen Recovery</h3>
                        <div class="big-number">${results.oxygenRecovered}<small>kg</small></div>
                        <p style="text-align: center; color: rgba(255, 255, 255, 0.8);">
                            ${results.dailyNeedPercentage}% of daily crew needs
                        </p>
                        <div class="process-steps">
                            <div class="process-step">
                                <h4><i class="fas fa-lungs"></i> Life Support Impact</h4>
                                <p>Sufficient for ${Math.round(results.oxygenRecovered / 0.8)} crew members for 24 hours</p>
                            </div>
                        </div>
                    </div>

                    <!-- Materials Recovery Card -->
                    <div class="result-card">
                        <h3>Materials Recovery</h3>
                        <div class="big-number">${results.materialsRecovered}<small>kg</small></div>
                        <p style="text-align: center; color: rgba(255, 255, 255, 0.8);">
                            Available for 3D printing and repairs
                        </p>
                        <div class="process-steps">
                            <div class="process-step">
                                <h4><i class="fas fa-cubes"></i> Potential Uses</h4>
                                <p>• Habitat repairs<br>• Tool manufacturing<br>• Equipment upgrades</p>
                            </div>
                        </div>
                    </div>

                    <!-- Energy Efficiency Card -->
                    <div class="result-card">
                        <h3>Energy Efficiency</h3>
                        <div class="big-number">${Math.round(results.totalInput * 1.8)}<small>kWh</small></div>
                        <p style="text-align: center; color: rgba(255, 255, 255, 0.8);">
                            Estimated energy consumption
                        </p>
                        <div class="process-steps">
                            <div class="process-step">
                                <h4><i class="fas fa-bolt"></i> Power Source</h4>
                                <p>Solar panels (primary)<br>Battery backup (secondary)</p>
                            </div>
                            <div class="process-step">
                                <h4><i class="fas fa-sun"></i> Recommendation</h4>
                                <p>Run high-energy processes during peak solar hours (10:00-14:00 Mars time)</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Process Breakdown -->
                <div class="result-card">
                    <h3>Process Breakdown</h3>

                    <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 15px; margin-top: 20px;">
                        <!-- EVA Suit Process -->
                        <div class="process-step" style="margin-bottom: 0;">
                            <h4><i class="fas fa-space-suit"></i> EVA Suit Processing (${results.evaSuit} kg)</h4>
                            <p>✅ Shredding: 100% of material</p>
                            <p>✅ Thermal processing: ${Math.round(results.evaSuit * 0.6)} kg polymer</p>
                            <p>✅ Oxygen extraction: ${Math.round(results.evaSuit * 0.4)} kg O₂</p>
                            <p style="color: var(--highlight); font-size: 0.9rem;">
                                <i class="fas fa-info-circle"></i> Polymer can be used for 3D printing new suit components
                            </p>
                        </div>

                        <!-- Air Filters Process -->
                        <div class="process-step" style="margin-bottom: 0;">
                            <h4><i class="fas fa-filter"></i> Air Filter Recycling (${results.airFilters} kg)</h4>
                            <p>✅ Mechanical separation: 100% of material</p>
                            <p>✅ Metal recovery: ${Math.round(results.airFilters * 0.3)} kg</p>
                            <p>✅ Carbon recovery: ${Math.round(results.airFilters * 0.5)} kg</p>
                            <p style="color: var(--highlight); font-size: 0.9rem;">
                                <i class="fas fa-info-circle"></i> Recovered metals can be used for structural repairs
                            </p>
                        </div>

                        <!-- Carbon Scraps Process -->
                        <div class="process-step" style="margin-bottom: 0;">
                            <h4><i class="fas fa-atom"></i> Carbon Processing (${results.carbonScraps} kg)</h4>
                            <p>✅ Chemical treatment: 100% of material</p>
                            <p>✅ Oxygen extraction: ${Math.round(results.carbonScraps * 0.6)} kg O₂</p>
                            <p>✅ Carbon fiber: ${Math.round(results.carbonScraps * 0.4)} kg for composites</p>
                            <p style="color: var(--highlight); font-size: 0.9rem;">
                                <i class="fas fa-info-circle"></i> Carbon fiber ideal for lightweight structural components
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Results Chart Container with fixed height -->
                <div class="chart-container">
                    <h3>Resource Recovery Summary</h3>
                    <div style="height: 350px;">
                        <canvas id="resultsChart"></canvas>
                    </div>
                </div>

                <!-- Pie Chart Container with fixed height -->
                <div class="chart-container">
                    <h3>Resource Distribution</h3>
                    <div style="height: 350px;">
                        <canvas id="pieChart"></canvas>
                    </div>
                </div>
            `;

            // Create charts after the elements exist in the DOM
            setTimeout(() => {
                createResultsChart(results);
            }, 100);
        }

        function createResultsChart(results) {
            // Bar Chart
            const barCtx = document.getElementById('resultsChart');
            if (barCtx) {
                new Chart(barCtx, {
                    type: 'bar',
                    data: {
                        labels: ['Oxygen Recovered', 'Materials Recovered', 'Total Input', 'Energy Used'],
                        datasets: [{
                            label: 'Quantity',
                            data: [
                                results.oxygenRecovered,
                                results.materialsRecovered,
                                results.totalInput,
                                Math.round(results.totalInput * 1.8)
                            ],
                            backgroundColor: [
                                'rgba(78, 205, 196, 0.7)',
                                'rgba(255, 107, 107, 0.7)',
                                'rgba(100, 149, 237, 0.7)',
                                'rgba(255, 206, 86, 0.7)'
                            ],
                            borderColor: [
                                'rgba(78, 205, 196, 1)',
                                'rgba(255, 107, 107, 1)',
                                'rgba(100, 149, 237, 1)',
                                'rgba(255, 206, 86, 1)'
                            ],
                            borderWidth: 1
                        }]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        scales: {
                            y: {
                                beginAtZero: true,
                                title: {
                                    display: true,
                                    text: 'Quantity (kg or kWh)',
                                    color: 'white'
                                },
                                ticks: {
                                    color: 'rgba(255, 255, 255, 0.8)'
                                },
                                grid: {
                                    color: 'rgba(255, 255, 255, 0.1)'
                                }
                            },
                            x: {
                                ticks: {
                                    color: 'rgba(255, 255, 255, 0.8)'
                                },
                                grid: {
                                    color: 'rgba(255, 255, 255, 0.1)'
                                }
                            }
                        },
                        plugins: {
                            legend: {
                                display: false
                            }
                        }
                    }
                });
            }

            // Pie Chart
            const pieCtx = document.getElementById('pieChart');
            if (pieCtx) {
                new Chart(pieCtx, {
                    type: 'doughnut',
                    data: {
                        labels: ['Oxygen', 'Materials', 'Waste'],
                        datasets: [{
                            data: [
                                results.oxygenRecovered,
                                results.materialsRecovered,
                                results.totalInput - results.oxygenRecovered - results.materialsRecovered
                            ],
                            backgroundColor: [
                                'rgba(78, 205, 196, 0.7)',
                                'rgba(255, 107, 107, 0.7)',
                                'rgba(100, 149, 237, 0.7)'
                            ],
                            borderColor: [
                                'rgba(78, 205, 196, 1)',
                                'rgba(255, 107, 107, 1)',
                                'rgba(100, 149, 237, 1)'
                            ],
                            borderWidth: 1
                        }]
                    },
                    options: {
                        responsive: true,
                        maintainAspectRatio: false,
                        plugins: {
                            legend: {
                                position: 'right',
                                labels: {
                                    color: 'white',
                                    boxWidth: 12,
                                    padding: 20,
                                    font: {
                                        size: 12
                                    }
                                }
                            },
                            title: {
                                display: true,
                                text: 'Resource Distribution',
                                color: 'white',
                                font: {
                                    size: 16
                                }
                            }
                        }
                    }
                });
            }
        }
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mars Recovery Station - 3D Visualization</title>
    <style>
        :root {
            --primary: #1a1a2e;
            --secondary: #16213e;
            --accent: #ff6b6b;
            --highlight: #4ecdc4;
            --space-bg: linear-gradient(rgba(10, 10, 30, 0.8), rgba(10, 10, 30, 0.8)),
                        url('https://images.unsplash.com/photo-1615430535007-94da764325d0?ixlib=rb-1.2.1&auto=format&fit=crop&w=1920&q=80');
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background: var(--space-bg);
            background-size: cover;
            background-position: center;
            color: white;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 40px;
            background: rgba(0, 0, 0, 0.5);
        }

        .header h1 {
            font-size: 1.8rem;
            color: white;
            text-shadow: 0 2px 5px rgba(0, 0, 0, 0.5);
        }

        .back-btn, .logout-btn {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s;
            margin-left: 10px;
        }

        .back-btn:hover, .logout-btn:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 0 20px;
        }

        .visualization-header {
            text-align: center;
            margin-bottom: 30px;
        }

        .visualization-header h2 {
            font-size: 2rem;
            color: var(--accent);
            margin-bottom: 10px;
            text-shadow: 0 0 10px rgba(255, 107, 107, 0.3);
        }

        .visualization-header p {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
        }

        #visualization-container {
            width: 100%;
            height: 600px;
            background: rgba(0, 0, 0, 0.5);
            border-radius: 15px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .stats-panel {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .stat-card {
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .stat-card h3 {
            color: var(--accent);
            margin-top: 0;
            margin-bottom: 15px;
            font-size: 1.3rem;
            border-bottom: 1px solid var(--highlight);
            padding-bottom: 10px;
        }

        .stat-value {
            font-size: 2rem;
            font-weight: bold;
            color: white;
            text-align: center;
            margin: 15px 0;
            background: linear-gradient(135deg, var(--accent), var(--highlight));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .stat-value small {
            font-size: 1rem;
            color: rgba(255, 255, 255, 0.7);
            display: block;
            margin-top: 5px;
            background: none;
            -webkit-text-fill-color: initial;
        }

        .navigation {
            display: flex;
            justify-content: space-between;
            margin-top: 20px;
        }

        .info-panel {
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            padding: 20px;
            margin-top: 20px;
        }

        .info-panel h3 {
            color: var(--accent);
            margin-top: 0;
            margin-bottom: 15px;
            border-bottom: 1px solid var(--highlight);
            padding-bottom: 10px;
        }

        @media (max-width: 768px) {
            #visualization-container {
                height: 400px;
            }

            .stats-panel {
                grid-template-columns: 1fr;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/build/three.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/examples/js/controls/OrbitControls.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/examples/js/loaders/GLTFLoader.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.132.2/examples/js/loaders/TextureLoader.js"></script>
</head>
<body>
    <div class="header">
        <div>
            <button class="back-btn" onclick="window.location.href='results.html'">
                <i class="fas fa-arrow-left"></i> Back to Results
            </button>
        </div>
        <h1>Mars Recovery Station</h1>
        <button class="logout-btn" onclick="logout()">Logout</button>
    </div>

    <div class="container">
        <div class="visualization-header">
            <h2>3D Recovery Station Visualization</h2>
            <p>Interactive model of the Mars waste recovery facility with realistic terrain</p>
        </div>

        <div id="visualization-container"></div>

        <div class="stats-panel">
            <div class="stat-card">
                <h3>Oxygen Production</h3>
                <div class="stat-value" id="oxygenStat">0<small>kg/day</small></div>
                <p style="text-align: center; color: rgba(255, 255, 255, 0.8); font-size: 0.9rem;">
                    From EVA suits and carbon scraps
                </p>
            </div>

            <div class="stat-card">
                <h3>Material Recovery</h3>
                <div class="stat-value" id="materialStat">0<small>kg/day</small></div>
                <p style="text-align: center; color: rgba(255, 255, 255, 0.8); font-size: 0.9rem;">
                    For 3D printing and repairs
                </p>
            </div>

            <div class="stat-card">
                <h3>Energy Efficiency</h3>
                <div class="stat-value" id="energyStat">0<small>kWh</small></div>
                <p style="text-align: center; color: rgba(255, 255, 255, 0.8); font-size: 0.9rem;">
                    Per processing cycle
                </p>
            </div>
        </div>

        <div class="info-panel">
            <h3>Facility Components</h3>
            <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px;">
                <div>
                    <h4 style="color: var(--highlight); margin-bottom: 10px;"><i class="fas fa-industry"></i> Processing Plant</h4>
                    <p style="font-size: 0.9rem; color: rgba(255, 255, 255, 0.8);">
                        Thermal, chemical, and mechanical processing units for waste conversion.
                    </p>
                </div>
                <div>
                    <h4 style="color: var(--highlight); margin-bottom: 10px;"><i class="fas fa-print"></i> 3D Printing Bay</h4>
                    <p style="font-size: 0.9rem; color: rgba(255, 255, 255, 0.8);">
                        Uses recovered materials to manufacture tools and parts on-demand.
                    </p>
                </div>
                <div>
                    <h4 style="color: var(--highlight); margin-bottom: 10px;"><i class="fas fa-solar-panel"></i> Power Station</h4>
                    <p style="font-size: 0.9rem; color: rgba(255, 255, 255, 0.8);">
                        Solar arrays with battery backup for continuous operation.
                    </p>
                </div>
            </div>
        </div>

        <div class="navigation">
            <button class="back-btn" onclick="window.location.href='results.html'">
                <i class="fas fa-arrow-left"></i> Back to Results
            </button>
            <button class="back-btn" onclick="window.location.href='dashboard.html'">
                New Analysis <i class="fas fa-redo"></i>
            </button>
        </div>
    </div>

    <script>
        // Check if user is logged in
        if (localStorage.getItem('isLoggedIn') !== 'true') {
            window.location.href = 'index.html';
        }

        // Logout function
        function logout() {
            localStorage.removeItem('isLoggedIn');
            window.location.href = 'index.html';
        }

        // Load results data
        function loadResultsData() {
            const results = JSON.parse(localStorage.getItem('recyclingResults'));

            if (results) {
                document.getElementById('oxygenStat').textContent = `${results.oxygenRecovered}`;
                document.getElementById('materialStat').textContent = `${results.materialsRecovered}`;
                document.getElementById('energyStat').textContent = `${Math.round(results.totalInput * 1.8)}`;
            }
        }

        // Initialize 3D Visualization with enhanced Mars surface
        document.addEventListener('DOMContentLoaded', function() {
            initEnhanced3DVisualization();
            loadResultsData();
        });

        function initEnhanced3DVisualization() {
            const container = document.getElementById('visualization-container');

            // Scene setup
            const scene = new THREE.Scene();
            scene.background = new THREE.Color(0x000000);

            // Camera setup - wider view for better perspective
            const camera = new THREE.PerspectiveCamera(60, container.clientWidth / container.clientHeight, 0.1, 2000);
            camera.position.set(20, 15, 20);

            // Renderer setup with shadows
            const renderer = new THREE.WebGLRenderer({
                antialias: true,
                alpha: true
            });
            renderer.setSize(container.clientWidth, container.clientHeight);
            renderer.shadowMap.enabled = true;
            renderer.shadowMap.type = THREE.PCFSoftShadowMap;
            container.appendChild(renderer.domElement);

            // Controls for orbiting the 3D model
            const controls = new THREE.OrbitControls(camera, renderer.domElement);
            controls.enableDamping = true;
            controls.dampingFactor = 0.05;
            controls.target.set(0, 2, 0);
            controls.maxDistance = 100;
            controls.minDistance = 10;

            // Lighting - simulate Martian sunlight
            const ambientLight = new THREE.AmbientLight(0x404050, 0.3);
            scene.add(ambientLight);

            const directionalLight = new THREE.DirectionalLight(0xffddcc, 1.2);
            directionalLight.position.set(20, 30, 10);
            directionalLight.castShadow = true;
            directionalLight.shadow.mapSize.width = 2048;
            directionalLight.shadow.mapSize.height = 2048;
            directionalLight.shadow.camera.near = 0.5;
            directionalLight.shadow.camera.far = 500;
            directionalLight.shadow.camera.left = -50;
            directionalLight.shadow.camera.right = 50;
            directionalLight.shadow.camera.top = 50;
            directionalLight.shadow.camera.bottom = -50;
            scene.add(directionalLight);

            // Add subtle red light for Mars atmosphere effect
            const marsLight = new THREE.HemisphereLight(0xffaaaa, 0x000055, 0.3);
            scene.add(marsLight);

            // Create enhanced Mars surface with elevation
            createEnhancedMars(scene);

            // Create detailed recovery station
            createDetailedRecoveryStation(scene);

            // Add stars to the background
            createStarfield(scene, 2000);

            // Animation loop
            function animate() {
                requestAnimationFrame(animate);
                controls.update();
                renderer.render(scene, camera);
            }

            // Handle window resize
            window.addEventListener('resize', function() {
                camera.aspect = container.clientWidth / container.clientHeight;
                camera.updateProjectionMatrix();
                renderer.setSize(container.clientWidth, container.clientHeight);
            });

            animate();
        }

        function createEnhancedMars(scene) {
            // High-resolution Mars texture
            const marsTexture = new THREE.TextureLoader().load('https://upload.wikimedia.org/wikipedia/commons/thumb/0/02/OSIRIS_Mars_true_color.jpg/1200px-OSIRIS_Mars_true_color.jpg');

            // Mars elevation map for realistic terrain
            const marsElevation = new THREE.TextureLoader().load('https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Mars_topography.jpg/1200px-Mars_topography.jpg');

            // Create Mars sphere with bump mapping for realistic terrain
            const marsGeometry = new THREE.SphereGeometry(15, 128, 128);
            const marsMaterial = new THREE.MeshStandardMaterial({
                map: marsTexture,
                bumpMap: marsElevation,
                bumpScale: 0.05,
                metalness: 0.1,
                roughness: 0.8,
                color: 0xcc9966
            });

            const mars = new THREE.Mesh(marsGeometry, marsMaterial);
            mars.receiveShadow = true;
            scene.add(mars);

            // Add subtle atmosphere effect
            const atmosphereGeometry = new THREE.SphereGeometry(15.2, 64, 64);
            const atmosphereMaterial = new THREE.MeshStandardMaterial({
                color: 0x3366cc,
                transparent: true,
                opacity: 0.1,
                side: THREE.BackSide,
                roughness: 0.1
            });
            const atmosphere = new THREE.Mesh(atmosphereGeometry, atmosphereMaterial);
            scene.add(atmosphere);

            // Add some surface features (craters)
            addSurfaceFeatures(scene, mars);
        }

        function addSurfaceFeatures(scene, mars) {
            // Add some random craters to make the surface more realistic
            const craterGeometry = new THREE.CircleGeometry(0.3, 32);
            const craterMaterial = new THREE.MeshStandardMaterial({
                color: 0x555555,
                side: THREE.DoubleSide,
                roughness: 0.9
            });

            for (let i = 0; i < 50; i++) {
                const crater = new THREE.Mesh(craterGeometry, craterMaterial);

                // Random position on Mars surface
                const theta = Math.random() * Math.PI * 2;
                const phi = Math.acos(2 * Math.random() - 1);
                const radius = 15 + (Math.random() * 0.2 - 0.1);

                crater.position.x = radius * Math.sin(phi) * Math.cos(theta);
                crater.position.y = radius * Math.sin(phi) * Math.sin(theta);
                crater.position.z = radius * Math.cos(phi);

                // Orient crater to face away from Mars center
                crater.lookAt(0, 0, 0);

                // Random size variation
                const scale = 0.5 + Math.random() * 0.5;
                crater.scale.set(scale, scale, scale);

                // Random depth
                crater.position.x += (Math.random() - 0.5) * 0.1;
                crater.position.y += (Math.random() - 0.5) * 0.1;
                crater.position.z += (Math.random() - 0.5) * 0.1;

                scene.add(crater);
            }
        }

        function createDetailedRecoveryStation(scene) {
            // Base platform with more detail
            const baseGroup = new THREE.Group();
            baseGroup.position.set(0, 0.1, 0);

            // Main base
            const baseGeometry = new THREE.CylinderGeometry(3, 3, 0.5, 32);
            const baseMaterial = new THREE.MeshStandardMaterial({
                color: 0x333333,
                metalness: 0.3,
                roughness: 0.7
            });
            const base = new THREE.Mesh(baseGeometry, baseMaterial);
            base.receiveShadow = true;
            base.castShadow = true;
            baseGroup.add(base);

            // Add support legs
            const legGeometry = new THREE.CylinderGeometry(0.2, 0.2, 1.5, 16);
            const legMaterial = new THREE.MeshStandardMaterial({
                color: 0x444444,
                metalness: 0.5,
                roughness: 0.6
            });

            for (let i = 0; i < 4; i++) {
                const angle = (i * Math.PI * 2) / 4;
                const leg = new THREE.Mesh(legGeometry, legMaterial);
                leg.position.x = Math.cos(angle) * 2.5;
                leg.position.z = Math.sin(angle) * 2.5;
                leg.position.y = -0.75;
                leg.rotation.x = Math.PI / 4;
                leg.castShadow = true;
                baseGroup.add(leg);
            }

            // Main habitat dome with more detail
            const domeGroup = new THREE.Group();
            domeGroup.position.y = 1.5;

            // Dome base
            const domeBaseGeometry = new THREE.CylinderGeometry(1.5, 1.5, 0.3, 32);
            const domeBaseMaterial = new THREE.MeshStandardMaterial({
                color: 0xaaaaaa,
                metalness: 0.2,
                roughness: 0.5
            });
            const domeBase = new THREE.Mesh(domeBaseGeometry, domeBaseMaterial);
            domeBase.castShadow = true;
            domeGroup.add(domeBase);

            // Dome itself
            const domeGeometry = new THREE.SphereGeometry(1.5, 32, 32, 0, Math.PI * 2, 0, Math.PI / 2);
            const domeMaterial = new THREE.MeshStandardMaterial({
                color: 0xaaaaaa,
                metalness: 0.2,
                roughness: 0.5,
                transparent: true,
                opacity: 0.7
            });
            const dome = new THREE.Mesh(domeGeometry, domeMaterial);
            dome.position.y = 0.3;
            dome.castShadow = true;
            domeGroup.add(dome);

            // Add airlock
            const airlockGeometry = new THREE.CylinderGeometry(0.5, 0.5, 0.8, 32);
            const airlockMaterial = new THREE.MeshStandardMaterial({
                color: 0x888888,
                metalness: 0.4,
                roughness: 0.5
            });
            const airlock = new THREE.Mesh(airlockGeometry, airlockMaterial);
            airlock.position.set(1.8, 0.5, 0);
            airlock.rotation.z = Math.PI / 2;
            airlock.castShadow = true;
            domeGroup.add(airlock);

            baseGroup.add(domeGroup);

            // Solar panels array with more detail
            const solarArray = new THREE.Group();
            solarArray.position.set(0, 2, -4);

            const panelGeometry = new THREE.BoxGeometry(1.5, 0.02, 0.5);
            const panelMaterial = new THREE.MeshStandardMaterial({
                color: 0x222233,
                metalness: 0.7,
                roughness: 0.2,
                side: THREE.DoubleSide
            });

            // Create an array of solar panels
            for (let row = 0; row < 3; row++) {
                for (let col = 0; col < 5; col++) {
                    const panel = new THREE.Mesh(panelGeometry, panelMaterial);
                    panel.position.x = col * 1.6 - 3.2;
                    panel.position.z = row * 0.6 - 0.6;
                    panel.rotation.x = Math.PI / 4 + (Math.random() - 0.5) * 0.1;
                    panel.castShadow = true;
                    solarArray.add(panel);
                }
            }

            baseGroup.add(solarArray);

            // Processing units with more detail
            const processingGroup = new THREE.Group();
            processingGroup.position.set(0, 0.5, 3);

            // Thermal processor
            createProcessorUnit(processingGroup, -1.5, 0, 0, 0xff5555, 'Thermal Processor');
            // Chemical processor
            createProcessorUnit(processingGroup, 0, 0, 1.5, 0x55ff55, 'Chemical Processor');
            // Mechanical processor
            createProcessorUnit(processingGroup, 1.5, 0, 0, 0x5555ff, 'Mechanical Processor');

            baseGroup.add(processingGroup);

            // Storage tanks with pipes
            const storageGroup = new THREE.Group();
            storageGroup.position.set(4, 0.5, 0);

            // Oxygen tank
            createStorageTank(storageGroup, 0, 0, 0.8, 'Oxygen Tank');
            // Material tank
            createStorageTank(storageGroup, 0, 0, -0.8, 'Material Tank');

            // Connecting pipes
            createPipe(storageGroup, -0.5, 0.5, 0, 0.5, 0.5, -0.8, 0.1);
            createPipe(storageGroup, 0.5, 0.5, 0, 0.5, 0.5, -0.8, 0.1);

            baseGroup.add(storageGroup);

            // Add the complete base group to the scene
            scene.add(baseGroup);

            // Add some rovers for scale
            addRovers(scene);
        }

        function createProcessorUnit(group, x, y, z, color, name) {
            const unitGroup = new THREE.Group();
            unitGroup.position.set(x, y, z);

            // Main cylinder
            const cylinderGeometry = new THREE.CylinderGeometry(0.6, 0.6, 1.2, 32);
            const cylinderMaterial = new THREE.MeshStandardMaterial({
                color: color,
                metalness: 0.6,
                roughness: 0.3
            });
            const cylinder = new THREE.Mesh(cylinderGeometry, cylinderMaterial);
            cylinder.castShadow = true;
            unitGroup.add(cylinder);

            // Top sphere
            const sphereGeometry = new THREE.SphereGeometry(0.4, 32, 32);
            const sphereMaterial = new THREE.MeshStandardMaterial({
                color: color,
                metalness: 0.7,
                roughness: 0.2
            });
            const sphere = new THREE.Mesh(sphereGeometry, sphereMaterial);
            sphere.position.y = 0.7;
            sphere.castShadow = true;
            unitGroup.add(sphere);

            // Add some pipes
            const pipeGeometry = new THREE.CylinderGeometry(0.08, 0.08, 0.8, 16);
            const pipeMaterial = new THREE.MeshStandardMaterial({
                color: 0x666666,
                metalness: 0.8,
                roughness: 0.3
            });

            // Input pipe
            const inputPipe = new THREE.Mesh(pipeGeometry, pipeMaterial);
            inputPipe.position.set(0.4, 0, 0);
            inputPipe.rotation.z = Math.PI / 2;
            unitGroup.add(inputPipe);

            // Output pipe
            const outputPipe = new THREE.Mesh(pipeGeometry, pipeMaterial);
            outputPipe.position.set(-0.4, 0, 0);
            outputPipe.rotation.z = Math.PI / 2;
            unitGroup.add(outputPipe);

            group.add(unitGroup);
        }

        function createStorageTank(group, x, y, z, name) {
            const tankGroup = new THREE.Group();
            tankGroup.position.set(x, y, z);

            // Main sphere
            const sphereGeometry = new THREE.SphereGeometry(0.7, 32, 32);
            const sphereMaterial = new THREE.MeshStandardMaterial({
                color: name.includes('Oxygen') ? 0xaaaaff : 0xffaaaa,
                metalness: 0.3,
                roughness: 0.7,
                transparent: true,
                opacity: 0.8
            });
            const sphere = new THREE.Mesh(sphereGeometry, sphereMaterial);
            sphere.castShadow = true;
            tankGroup.add(sphere);

            // Support legs
            const legGeometry = new THREE.CylinderGeometry(0.08, 0.08, 0.5, 16);
            const legMaterial = new THREE.MeshStandardMaterial({
                color: 0x444444,
                metalness: 0.5,
                roughness: 0.6
            });

            for (let i = 0; i < 3; i++) {
                const angle = (i * Math.PI * 2) / 3;
                const leg = new THREE.Mesh(legGeometry, legMaterial);
                leg.position.x = Math.cos(angle) * 0.6;
                leg.position.z = Math.sin(angle) * 0.6;
                leg.position.y = -0.7;
                leg.rotation.x = Math.PI / 4;
                leg.castShadow = true;
                tankGroup.add(leg);
            }

            // Input/output pipes
            const pipeGeometry = new THREE.CylinderGeometry(0.08, 0.08, 0.5, 16);
            const pipeMaterial = new THREE.MeshStandardMaterial({
                color: 0x666666,
                metalness: 0.8,
                roughness: 0.3
            });

            const topPipe = new THREE.Mesh(pipeGeometry, pipeMaterial);
            topPipe.position.y = 0.8;
            topPipe.rotation.x = Math.PI / 2;
            tankGroup.add(topPipe);

            group.add(tankGroup);
        }

        function createPipe(group, x1, y1, z1, x2, y2, z2, radius) {
            const curve = new THREE.QuadraticBezierCurve3(
                new THREE.Vector3(x1, y1, z1),
                new THREE.Vector3((x1 + x2) / 2, (y1 + y2) / 2 + 0.3, (z1 + z2) / 2),
                new THREE.Vector3(x2, y2, z2)
            );

            const points = curve.getPoints(50);
            const pipeGeometry = new THREE.TubeGeometry(
                new THREE.CatmullRomCurve3(points),
                50,
                radius,
                8,
                false
            );

            const pipeMaterial = new THREE.MeshStandardMaterial({
                color: 0x666666,
                metalness: 0.8,
                roughness: 0.3
            });

            const pipe = new THREE.Mesh(pipeGeometry, pipeMaterial);
            pipe.castShadow = true;
            group.add(pipe);
        }

        function addRovers(scene) {
            // Simple rover model
            const roverGroup1 = new THREE.Group();
            roverGroup1.position.set(8, 0.5, -5);
            roverGroup1.rotation.y = Math.PI / 4;

            // Rover body
            const bodyGeometry = new THREE.BoxGeometry(0.8, 0.3, 0.5);
            const bodyMaterial = new THREE.MeshStandardMaterial({
                color: 0x555555,
                metalness: 0.3,
                roughness: 0.7
            });
            const body = new THREE.Mesh(bodyGeometry, bodyMaterial);
            body.castShadow = true;
            roverGroup1.add(body);

            // Rover wheels
            const wheelGeometry = new THREE.CylinderGeometry(0.15, 0.15, 0.1, 16);
            const wheelMaterial = new THREE.MeshStandardMaterial({
                color: 0x333333,
                metalness: 0.4,
                roughness: 0.6
            });

            // Front wheels
            const frontLeftWheel = new THREE.Mesh(wheelGeometry, wheelMaterial);
            frontLeftWheel.position.set(0.3, -0.2, 0.2);
            frontLeftWheel.rotation.z = Math.PI / 2;
            roverGroup1.add(frontLeftWheel);

            const frontRightWheel = new THREE.Mesh(wheelGeometry, wheelMaterial);
            frontRightWheel.position.set(0.3, -0.2, -0.2);
            frontRightWheel.rotation.z = Math.PI / 2;
            roverGroup1.add(frontRightWheel);

            // Rear wheels
            const rearLeftWheel = new THREE.Mesh(wheelGeometry, wheelMaterial);
            rearLeftWheel.position.set(-0.3, -0.2, 0.2);
            rearLeftWheel.rotation.z = Math.PI / 2;
            roverGroup1.add(rearLeftWheel);

            const rearRightWheel = new THREE.Mesh(wheelGeometry, wheelMaterial);
            rearRightWheel.position.set(-0.3, -0.2, -0.2);
            rearRightWheel.rotation.z = Math.PI / 2;
            roverGroup1.add(rearRightWheel);

            // Solar panel
            const panelGeometry = new THREE.BoxGeometry(0.6, 0.02, 0.3);
            const panelMaterial = new THREE.MeshStandardMaterial({
                color: 0x222233,
                metalness: 0.7,
                roughness: 0.2
            });
            const panel = new THREE.Mesh(panelGeometry, panelMaterial);
            panel.position.set(0, 0.2, 0);
            panel.rotation.x = Math.PI / 4;
            roverGroup1.add(panel);

            scene.add(roverGroup1);

            // Second rover
            const roverGroup2 = new THREE.Group();
            roverGroup2.position.set(-10, 0.5, 3);
            roverGroup2.rotation.y = -Math.PI / 3;

            const body2 = new THREE.Mesh(bodyGeometry, bodyMaterial);
            body2.castShadow = true;
            roverGroup2.add(body2);

            // Wheels for second rover
            const flWheel2 = new THREE.Mesh(wheelGeometry, wheelMaterial);
            flWheel2.position.set(0.3, -0.2, 0.2);
            flWheel2.rotation.z = Math.PI / 2;
            roverGroup2.add(flWheel2);

            const frWheel2 = new THREE.Mesh(wheelGeometry, wheelMaterial);
            frWheel2.position.set(0.3, -0.2, -0.2);
            frWheel2.rotation.z = Math.PI / 2;
            roverGroup2.add(frWheel2);

            const rlWheel2 = new THREE.Mesh(wheelGeometry, wheelMaterial);
            rlWheel2.position.set(-0.3, -0.2, 0.2);
            rlWheel2.rotation.z = Math.PI / 2;
            roverGroup2.add(rlWheel2);

            const rrWheel2 = new THREE.Mesh(wheelGeometry, wheelMaterial);
            rrWheel2.position.set(-0.3, -0.2, -0.2);
            rrWheel2.rotation.z = Math.PI / 2;
            roverGroup2.add(rrWheel2);

            const panel2 = new THREE.Mesh(panelGeometry, panelMaterial);
            panel2.position.set(0, 0.2, 0);
            panel2.rotation.x = Math.PI / 4;
            roverGroup2.add(panel2);

            scene.add(roverGroup2);
        }

        function createStarfield(scene, count) {
            const starsGeometry = new THREE.BufferGeometry();
            const starsMaterial = new THREE.PointsMaterial({
                color: 0xffffff,
                size: 0.1,
                transparent: true,
                opacity: 0.8
            });

            const positions = new Float32Array(count * 3);

            for (let i = 0; i < count; i++) {
                const i3 = i * 3;

                // Random position in a sphere
                const theta = Math.random() * Math.PI * 2;
                const phi = Math.acos(2 * Math.random() - 1);
                const radius = 800 + Math.random() * 200;

                positions[i3] = radius * Math.sin(phi) * Math.cos(theta);
                positions[i3 + 1] = radius * Math.sin(phi) * Math.sin(theta);
                positions[i3 + 2] = radius * Math.cos(phi);
            }

            starsGeometry.setAttribute('position', new THREE.BufferAttribute(positions, 3));
            const stars = new THREE.Points(starsGeometry, starsMaterial);
            scene.add(stars);
        }
    </script>
</body>
</html>

