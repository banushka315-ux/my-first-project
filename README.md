# my-first-project
This is my first git repository.
<br>
Author - Anushka Bhardwaj
https://codepen.io/Anushka-Bhardwaj-the-sans/pen/EagaLqg
<!DOCTYPE html>
<html>
<head>
    <title>Fake News Detection System</title>
    <style>
        body {
            font-family: Arial;
            background: linear-gradient(to right, #000428, #004e92);
            color: white;
            text-align: center;
            padding: 40px;
        }

        textarea {
            width: 60%;
            height: 120px;
            padding: 10px;
            border-radius: 8px;
        }

        button {
            padding: 10px 20px;
            background: #00c6ff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 10px;
        }

        #result {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
        }
    </style>
</head>

<body>

    <h1>📰 Fake News Detection System</h1>
    <p>Hackathon Frontend Version 🚀</p>

    <textarea id="newsInput" placeholder="Enter news text here..."></textarea>
    <br>
    <button onclick="checkNews()">Check News</button>

    <div id="result"></div>

    <script>
        function checkNews() {
            let text = document.getElementById("newsInput").value.toLowerCase();

            let fakeKeywords = ["alien", "cure instantly", "100% guarantee", "miracle", "bleach", "click here"];
            let score = 0;

            fakeKeywords.forEach(word => {
                if (text.includes(word)) {
                    score++;
                }
            });

            let resultDiv = document.getElementById("result");

            if (score > 0) {
                resultDiv.innerHTML = "❌ This News is Likely Fake.<br>Suspicious Score: " + score;
                resultDiv.style.color = "red";
            } else {
                resultDiv.innerHTML = "✅ This News is Likely Real.";
                resultDiv.style.color = "lightgreen";
            }
        }
    </script>

</body>
</html>
