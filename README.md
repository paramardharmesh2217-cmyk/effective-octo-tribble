# effective-octo-tribble
This Website is a cool and stylist.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modern Login Portal</title>
    <style>
        /* ==========================================================================
           1. RESET & BASE STYLES
           ========================================================================== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #0f0c20 0%, #15102a 50%, #06040a 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
        }

        /* ==========================================================================
           2. DYNAMIC AMBIENT BACKGROUND ORBS
           ========================================================================== */
        body::before, body::after {
            content: '';
            position: absolute;
            width: 320px;
            height: 320px;
            border-radius: 50%;
            filter: blur(90px);
            z-index: 0;
            opacity: 0.45;
        }

        body::before {
            background: #7f00ff;
            top: 15%;
            left: 20%;
            animation: floatingGlow 8s ease-in-out infinite alternate;
        }

        body::after {
            background: #00f0ff;
            bottom: 15%;
            right: 20%;
            animation: floatingGlow 8s ease-in-out infinite alternate-reverse;
        }

        @keyframes floatingGlow {
            0% { transform: translateY(0px) scale(1); }
            100% { transform: translateY(40px) scale(1.15); }
        }

        /* ==========================================================================
           3. GLASSMORPHISM LOGIN CONTAINER
           ========================================================================== */
        .login-container {
            position: relative;
            z-index: 10;
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08);
            width: 100%;
            max-width: 420px;
            padding: 3rem 2.5rem;
            border-radius: 24px;
            box-shadow: 0 24px 50px rgba(0, 0, 0, 0.5);
            text-align: center;
        }

        /* Header Accent */
        h2 {
            color: #ffffff;
            font-size: 2.2rem;
            margin-bottom: 0.5rem;
            font-weight: 600;
            letter-spacing: 0.5px;
        }

        .subtitle {
            color: #8e8ca2;
            font-size: 0.9rem;
            margin-bottom: 2.5rem;
        }

        /* ==========================================================================
           4. FORM FIELDS & LABELS
           ========================================================================== */
        .input-group {
            position: relative;
            margin-bottom: 1.6rem;
            text-align: left;
        }

        .input-group label {
            display: block;
            color: #a3a1b8;
            font-size: 0.85rem;
            margin-bottom: 0.6rem;
            font-weight: 500;
            padding-left: 4px;
        }

        .input-wrapper {
            position: relative;
            display: flex;
            align-items: center;
        }

        .input-group input {
            width: 100%;
            padding: 15px 16px;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            outline: none;
            border-radius: 14px;
            color: #ffffff;
            font-size: 0.95rem;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        /* Focus States with Clean Neon Accent Rings */
        .input-group input:focus {
            border-color: #00f0ff;
            background: rgba(255, 255, 255, 0.07);
            box-shadow: 0 0 18px rgba(0, 240, 255, 0.2);
        }

        /* Interactive Password Visibility Toggle */
        .toggle-password {
            position: absolute;
            right: 18px;
            color: #8e8ca2;
            cursor: pointer;
            font-size: 0.75rem;
            font-weight: 700;
            letter-spacing: 1px;
            user-select: none;
            transition: color 0.2s ease;
        }

        .toggle-password:hover {
            color: #00f0ff;
        }

        /* ==========================================================================
           5. FORM OPTIONS & RECOVERY
           ========================================================================== */
        .form-utils {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2.2rem;
            font-size: 0.85rem;
        }

        .remember-me {
            display: flex;
            align-items: center;
            color: #8e8ca2;
            cursor: pointer;
            user-select: none;
        }

        .remember-me input {
            margin-right: 8px;
            accent-color: #7f00ff;
            cursor: pointer;
            width: 15px;
            height: 15px;
        }

        .forgot-pass {
            color: #00f0ff;
            text-decoration: none;
            transition: opacity 0.2s ease;
        }

        .forgot-pass:hover {
            text-decoration: underline;
            opacity: 0.85;
        }

        /* ==========================================================================
           6. GRADIENT BUTTON & FOOTER LINKS
           ========================================================================== */
        .login-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(90deg, #7f00ff, #00f0ff);
            border: none;
            outline: none;
            color: #ffffff;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 14px;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 4px 20px rgba(127, 0, 255, 0.35);
        }

        .login-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 25px rgba(0, 240, 255, 0.45);
        }

        .login-btn:active {
            transform: translateY(1px);
        }

        .signup-text {
            margin-top: 2.2rem;
            color: #8e8ca2;
            font-size: 0.85rem;
        }

        .signup-text a {
            color: #ffffff;
            text-decoration: none;
            font-weight: 600;
            margin-left: 4px;
            transition: color 0.2s ease;
        }

        .signup-text a:hover {
            color: #00f0ff;
        }
    </style>
</head>
<body>

    <div class="login-container">
        <h2>Welcome Back</h2>
        <p class="subtitle">Enter your credentials to access your portal</p>

        <form onsubmit="event.preventDefault(); alert('Sign-in requested successfully!');">
            
            <div class="input-group">
                <label for="email">Email Address</label>
                <div class="input-wrapper">
                    <input type="email" id="email" placeholder="name@example.com" required autocomplete="email">
                </div>
            </div>

            <div class="input-group">
                <label for="password">Password</label>
                <div class="input-wrapper">
                    <input type="password" id="password" placeholder="••••••••" required autocomplete="current-password">
                    <span class="toggle-password" id="togglePassword">SHOW</span>
                </div>
            </div>

            <div class="form-utils">
                <label class="remember-me">
                    <input type="checkbox"> Remember me
                </label>
                <a href="#" class="forgot-pass">Forgot Password?</a>
            </div>

            <button type="submit" class="login-btn">Sign In</button>
        </form>

        <p class="signup-text">
            Don't have an account? <a href="#">Create one</a>
        </p>
    </div>

    <script>
        const passwordField = document.getElementById('password');
        const toggleBtn = document.getElementById('togglePassword');

        toggleBtn.addEventListener('click', function() {
            if (passwordField.type === 'password') {
                passwordField.type = 'text';
                toggleBtn.textContent = 'HIDE';
            } else {
                passwordField.type = 'password';
                toggleBtn.textContent = 'SHOW';
            }
        });
    </script>

</body>
</html>
