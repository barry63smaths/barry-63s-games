<!DOCTYPE html>
<html lang="en-GB">
<head>
    <!-- Google tag (gtag.js) -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-Z0DW0ZG97K"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());

        gtag('config', 'G-Z0DW0ZG97K');
    </script>

    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="default">
    <meta name="apple-mobile-web-app-title" content="Barry 63 Fullscreen">
    <meta name="theme-color" content="#000000">

    <!-- App Icon -->
    <link rel="apple-touch-icon" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">
    <link rel="icon" type="image/png" sizes="192x192" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">
    <link rel="icon" type="image/png" sizes="512x512" href="https://avatars.cloudflare.steamstatic.com/8508f3bec17102cdbbc768b4184ace4ae42d3756_full.jpg">

    <title>Barry 63 Fullscreen</title>

    <style>
        /* Body and General Design */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            position: relative;
            background: #000;
        }

        .container {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
            z-index: -1;
            background: repeating-conic-gradient(
                    from 30deg,
                    #0000 0 120deg,
                    #3c3c3c 0 180deg
                )
                calc(0.5 * 200px) calc(0.5 * 200px * 0.577),
            repeating-conic-gradient(
                from 30deg,
                #1d1d1d 0 60deg,
                #4e4f51 0 120deg,
                #3c3c3c 0 180deg
            );
            background-size: 200px calc(200px * 0.577);
        }

        .content {
            text-align: center;
            z-index: 2;
            color: white;
            padding: 20px;
            backdrop-filter: blur(8px);
            background: rgba(0, 0, 0, 0.4);
            border-radius: 12px;
        }

        h1 {
            font-size: 2.8em;
            margin-bottom: 20px;
        }

        button {
            display: block;
            width: 100%;
            max-width: 300px;
            padding: 15px;
            margin: 15px auto;
            font-size: 1em;
            font-weight: bold;
            color: white;
            background: linear-gradient(90deg, #32CD32, #7FFF00);
            border: none;
            border-radius: 8px;
            cursor: pointer;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease-in-out;
        }

        button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 200%;
            height: 100%;
            background: rgba(255, 255, 255, 0.2);
            transform: skewX(-45deg);
            transition: all 0.6s ease-in-out;
        }

        button:hover::before {
            left: 100%;
        }

        button:hover {
            transform: translateY(-5px);
            box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.3);
        }

        button:active {
            transform: translateY(2px);
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
        }

        button span {
            position: relative;
            z-index: 1;
            animation: bounceText 0.3s ease-in-out;
        }

        button:hover span {
            animation: bounceText 0.6s ease-in-out;
        }

        @keyframes bounceText {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.1);
            }
        }

        /* Cookie Consent Banner */
        #cookie-banner {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background-color: rgba(0, 0, 0, 0.7);
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            z-index: 10;
            display: none; /* Initially hidden */
        }

        #cookie-banner p {
            font-size: 1.1em;
            margin: 0;
            padding: 10px 0;
        }

        #cookie-banner button {
            background: linear-gradient(90deg, #32CD32, #7FFF00);
            border: none;
            padding: 10px 20px;
            font-size: 1.1em;
            color: white;
            border-radius: 8px;
            cursor: pointer;
            box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease-in-out;
        }

        #cookie-banner button:hover {
            transform: translateY(-5px);
            box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.3);
        }

        /* Game iframe */
        iframe {
            width: 100%;
            height: 100%;
            border: none;
            display: none; /* Initially hidden */
            position: absolute;
            top: 0;
            left: 0;
            z-index: 3;
        }

        /* Back button tab */
        .back-tab {
            position: fixed;
            top: 20px;
            left: -80px;
            width: 100px;
            height: 40px;
            background: #333;
            color: white;
            font-size: 1em;
            font-weight: bold;
            border-radius: 5px 0 0 5px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease-in-out;
            z-index: 2;
        }

        .back-tab:hover {
            left: 0;
        }

        .back-tab span {
            margin-left: 5px;
        }
    </style>
</head>
<body>

    <!-- Background container -->
    <div class="container"></div>

    <!-- Cookie Consent Banner -->
    <div id="cookie-banner">
        <p>This website uses cookies to save your game progress. By continuing, you agree to our use of cookies.</p>
        <button onclick="acceptCookies()">Accept Cookies</button>
    </div>

    <!-- Back button tab -->
    <div class="back-tab" onclick="closeGame()">
        ← <span>Back</span>
    </div>

    <!-- Main content with buttons -->
    <div class="content">
        <h1>Barry 63 Fullscreen</h1>

        <button onclick="startGame('./polytrack.html');"><span>Polytrack Fullscreen</span></button>
        <button onclick="startGame('./polytrack_server2.html');"><span>Polytrack (Server 2) Fullscreen</span></button>
        <button onclick="startGame('./ovo.html');"><span>OvO Fullscreen</span></button>
        <button onclick="startGame('./snowrider.html');"><span>Snow Rider Fullscreen</span></button>
        <button onclick="startGame('./run3.html');"><span>Run 3 Fullscreen</span></button>
    </div>

    <script>
        // Check if the user has accepted the cookies
        function checkCookieConsent() {
            if (!getCookie("cookieConsent")) {
                document.getElementById('cookie-banner').style.display = 'block';
            }
        }

        // Function to accept cookies and save consent
        function acceptCookies() {
            setCookie("cookieConsent", "true", 365); // Cookie will expire in 1 year
            document.getElementById('cookie-banner').style.display = 'none';
        }

        // Utility function to set a cookie
        function setCookie(name, value, days) {
            const date = new Date();
            date.setTime(date.getTime() + (days * 24 * 60 * 60 * 1000));
            let expires = "expires=" + date.toUTCString();
            document.cookie = name + "=" + value + ";" + expires + ";path=/";
        }

        // Utility function to get a cookie
        function getCookie(name) {
            let nameEQ = name + "=";
            let ca = document.cookie.split(';');
            for (let i = 0; i < ca.length; i++) {
                let c = ca[i];
                while (c.charAt(0) === ' ') c = c.substring(1, c.length);
                if (c.indexOf(nameEQ) === 0) return c.substring(nameEQ.length, c.length);
            }
            return null;
        }

        // Save the game progress in a cookie
        function saveProgress(gameName, level) {
            const progress = {
                level: level
            };

            setCookie(gameName + "-progress", JSON.stringify(progress), 365); // Save progress for 1 year
        }

        // Load the game progress from the cookie
        function loadProgress(gameName) {
            const savedProgress = getCookie(gameName + "-progress");

            if (savedProgress) {
                const progress = JSON.parse(savedProgress);
                return progress.level; // Return saved level
            }
            return 1; // If no saved progress, start from level 1
        }

        // Function to start a game
        function startGame(gameUrl) {
            let iframe = document.querySelector('iframe');
            if (!iframe) {
                iframe = document.createElement('iframe');
                document.body.appendChild(iframe);
            }

            const content = document.querySelector('.content');
            const backTab = document.querySelector('.back-tab');

            // Hide the home menu
            content.style.display = 'none';

            // Set iframe source to the game URL
            iframe.src = gameUrl;

            // Load the saved progress and pass the level to the game
            const savedLevel = loadProgress(gameUrl);
            console.log("Starting game at level: " + savedLevel);

            // Show the game iframe and back button
            iframe.style.display = 'block';
            backTab.style.display = 'flex';
        }

        // Function to close the game and return to the homepage
        function closeGame() {
            const iframe = document.querySelector('iframe');
            const content = document.querySelector('.content');
            const backTab = document.querySelector('.back-tab');

            if (iframe) {
                // Remove iframe from the DOM
                iframe.remove();
            }

            // Show the home menu again
            content.style.display = 'block';

            // Hide the back button
            backTab.style.display = 'none';
        }

        // Run the check when the page loads
        window.onload = function() {
            checkCookieConsent();
        };
    </script>

</body>
</html>
