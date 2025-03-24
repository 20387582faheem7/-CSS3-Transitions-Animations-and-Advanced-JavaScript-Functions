# -CSS3-Transitions-Animations-and-Advanced-JavaScript-Functions
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Webpage</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
            margin: 0;
            padding: 20px;
        }

        h1 {
            color: #333;
        }

        button {
            padding: 10px 20px;
            font-size: 18px;
            border: none;
            cursor: pointer;
            background-color: #28a745;
            color: white;
            border-radius: 5px;
            transition: transform 0.3s ease-in-out, background-color 0.3s;
        }

        button:hover {
            background-color: #218838;
            transform: scale(1.1);
        }

        .box {
            width: 100px;
            height: 100px;
            background-color: #007bff;
            margin: 20px auto;
            animation: fadeIn 2s ease-in-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        img {
            width: 200px;
            border-radius: 10px;
            transition: transform 0.5s ease-in-out;
        }

        img:hover {
            transform: rotate(10deg) scale(1.1);
        }
    </style>
</head>
<body>

    <h1>Interactive Webpage</h1>

    <button onclick="toggleBox()">Toggle Box</button>

    <div class="box" id="animatedBox"></div>

    <button onclick="savePreference()">Save Theme</button>
    <button onclick="loadPreference()">Load Theme</button>

    <p>Hover over the image:</p>
    <img src="https://via.placeholder.com/200" alt="Sample Image">

    <script>
        function toggleBox() {
            let box = document.getElementById("animatedBox");
            if (box.style.display === "none") {
                box.style.display = "block";
            } else {
                box.style.display = "none";
            }
        }

        function savePreference() {
            localStorage.setItem("theme", "dark");
            alert("Theme preference saved!");
        }

        function loadPreference() {
            let theme = localStorage.getItem("theme");
            if (theme) {
                alert("Stored theme: " + theme);
            } else {
                alert("No theme saved!");
            }
        }
    </script>

</body>
</html>
