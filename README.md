<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>System Override</title>
    <style>
        body {
            background-color: black;
            color: #00ff00; /* Hacker Green */
            font-family: 'Courier New', Courier, monospace;
            padding: 20px;
            margin: 0;
            overflow: hidden;
        }
        #console {
            font-size: 1.2rem;
            white-space: pre-wrap;
        }
        .cursor {
            font-weight: bold;
            animation: blink 1s step-end infinite;
        }
        @keyframes blink {
            50% { opacity: 0; }
        }
    </style>
</head>
<body>

    <div id="console"></div><span class="cursor">_</span>

    <script>
        const textLines = [
            "Initializing connection...",
            "Bypassing security protocols...",
            "Accessing mainframe directory...",
            "Decrypting encrypted files...",
            "[ WARNING: UNAUTHORIZED ACCESS DETECTED ]",
            "Disabling firewall...",
            "SYSTEM COMPROMISED.",
            "YOUR MOBILE WAS HACKED!",
            "Downloading data: 100% Complete."
        ];

        let lineIndex = 0;
        let charIndex = 0;
        const consoleDiv = document.getElementById("console");

        function typeText() {
            if (lineIndex < textLines.length) {
                if (charIndex < textLines[lineIndex].length) {
                    consoleDiv.innerHTML += textLines[lineIndex].charAt(charIndex);
                    charIndex++;
                    setTimeout(typeText, 30); // Typing speed
                } else {
                    consoleDiv.innerHTML += "<br><br>";
                    lineIndex++;
                    charIndex = 0;
                    setTimeout(typeText, 800); // Delay between lines
                }
            } else {
                // Change color to red at the end for dramatic effect
                document.body.style.color = "red";
            }
        }

        window.onload = () => {
            setTimeout(typeText, 1000);
        };
    </script>

</body>
</html>
