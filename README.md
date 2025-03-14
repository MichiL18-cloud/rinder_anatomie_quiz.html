<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rinderanatomie Quiz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        #image-container {
            position: relative;
            display: inline-block;
        }
        .marker {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: red;
            border-radius: 50%;
            cursor: pointer;
        }
        #quiz-container {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Rinderanatomie Quiz</h1>
    <p>Klicke auf einen markierten Punkt und wähle die richtige Bezeichnung.</p>
    
    <div id="image-container">
        <img src="rinder_anatomie.jpg" alt="Rinder Anatomie" width="800">
        <div class="marker" style="top: 40%; left: 30%;" onclick="showQuestion(0)"></div>
        <div class="marker" style="top: 50%; left: 50%;" onclick="showQuestion(1)"></div>
        <div class="marker" style="top: 60%; left: 70%;" onclick="showQuestion(2)"></div>
    </div>
    
    <div id="quiz-container"></div>
    
    <script>
        const questions = [
            { text: "Was ist dieses Körperteil?", options: ["Herz", "Leber", "Lunge"], answer: "Herz" },
            { text: "Was ist dieses Körperteil?", options: ["Magen", "Milz", "Zwerchfell"], answer: "Zwerchfell" },
            { text: "Was ist dieses Körperteil?", options: ["Speiseröhre", "Blättermagen", "Pansen"], answer: "Pansen" }
        ];

        function showQuestion(index) {
            let question = questions[index];
            let optionsHtml = question.options.map(option => `<button onclick='checkAnswer("${option}", "${question.answer}")'>${option}</button>`).join(" ");
            document.getElementById("quiz-container").innerHTML = `<p>${question.text}</p>${optionsHtml}`;
        }

        function checkAnswer(selected, correct) {
            if (selected === correct) {
                alert("Richtig!");
            } else {
                alert("Falsch, versuche es erneut.");
            }
        }
    </script>
</body>
</html>
