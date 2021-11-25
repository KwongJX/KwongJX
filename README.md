- 👋 Hi, I’m @KwongJX
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
KwongJX/KwongJX is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
---><html>
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Guess Game</title>
        <style>
            #container{
                margin:auto;
                border:5px solid lightBlue;
                font-size:30px;
                padding:10px;
                text-align:center;
                height:260px;
                width:600px;
                background-color:#0e2431;
            }

            p{
                color:white;
            }

            #userInput{
                width:170px;
                height:23px;
            
            }
            #outputText{
                color:red;
            }
        </style>
    </head>
    <body>
        <div id="container">
            <p>Guess a number between 1 and 100</p>
            <p id="outputText">Enter a number below</p>
            <input id="userInput">
            <button id="enterButton">Enter</button>
            <button id="againButton">Play again</button>
        </div>

        <script>
            var enterButton = document.getElementById('enterButton');
            var againButton = document.getElementById('againButton');
            var output = document.getElementById('outputText');
        
            var randomNumber = Math.ceil(Math.random()*100);
        
            function checkNumber(){
            var input = document.getElementById('userInput').value;
            if(input == randomNumber){
                output.innerHTML="You guessed right "+ ", "+ " it was "+ randomNumber;
                output.style.color="green";
            }
            else if(input>randomNumber && input<100){
                output.innerHTML="You guessed too high";
            }
            else if(input<randomNumber && input>1){
                output.innerHTML="You guessed too low";
            }
            else if(input>100){
                output.innerHTML="Higher, it has to be between 1 and 100";
            }
            else if(isNaN(input)){
                output.innerHTML="That's not a number!";
            }
            else if(input<1){
                output.innerHTML="Lower, it has to be between 1 and 100";
            }
        
            }
        
            enterButton.addEventListener('click', checkNumber);
            againButton.addEventListener('click', function(){
            location.reload();
            })
        </script>
    </body>
</html>
