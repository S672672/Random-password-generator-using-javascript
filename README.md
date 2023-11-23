# Random-password-generator-using-javascript

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random password creator</title>
    <style>
        body{
            background-color: blueviolet;
            font-family: Arial, sans-serif;
            text-align: center;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container{
            width: 60vh;
            height: 40vh;
           background-color: white;
           border-radius: 5vh;
           background-color: aqua;
        }
        #btn{
            cursor: pointer;
        } 
        .container2{
            background-color: white;
            width: 80%;
            height: 50px;
            margin-top: 50px;
            margin-bottom: 50px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 29px 29;
            margin-left:10%;
            border-radius: 5px;

        }
        .container2 img{
            width: 100px;
            cursor: pointer;
        }
        .container2 input{
            border: 0;
            outline: 0;
            font-size: 25px;
        }
        .container img{
            width: 20px;
            margin-right: 10px;
        }
        .container button{
            border: 0;
            outline: 0;
            font-size: 25px;
            font-weight: 300;
            display: center;
            border-radius: 10px;
            align-items: center;
            justify-content: center;
            padding: 10px 26px;
            background-color: yellow;
            
        }
        #head1 span{
            color: goldenrod;
        }

    </style>
</head>
<body>
    <div class = "container">
    <h1 id="head1">Generate a <br> <span>Random Password</span></h1>
    <div class="container2">
        <input type="text" placeholder = "password" id="password">
        <img src="/home/smith/Downloads/greenimg.png" alt="" id="copy">
    </div>
    <button id="btn"><img src="/home/smith/Downloads/light.png" alt="">Generate password</button>
    </div>
    <script>
        const btn = document.getElementById("btn");
        const copy = document.getElementById("copy");
        const password = document.getElementById("password");

        const length = 10;

        const uppercase = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
        const lowercase = "abcdefghijklmnopqrstuvwxyz";
        const number = "1234567890";
        const symbol = "@!#$%^&";
        const totalPassword = uppercase + lowercase + number + symbol;

        const newPassword = () =>{
            let PassWord = "";
            PassWord += uppercase[Math.floor(Math.random()*uppercase.length)];
            PassWord += lowercase[Math.floor(Math.random()*lowercase.length)];
            PassWord += number[Math.floor(Math.random()*number.length)];
            PassWord += symbol[Math.floor(Math.random()*symbol.length)];

            while(length>=PassWord.length){
                PassWord += totalPassword[Math.floor(Math.random()*totalPassword.length)];
            }
            password.value = PassWord;
        }
        btn.addEventListener("click",newPassword);
        copy.addEventListener('click',copyText);

        function copyText(){
            password.select();
            document.execCommand("copy");
        }

    </script>
</body>
</html>
