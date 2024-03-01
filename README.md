# project-4
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1 class="heading">Calculator</h1>
    <div class="container">
        <div class="input">
            <input type="text" class="output">
        </div>
        <div class="row">
            <button class="button">7</button>
            <button class="button">8</button>
            <button class="button">9</button>
            <button class="button">/</button>
        </div>
        <div class="row">
            <button class="button">4</button>
            <button class="button">5</button>
            <button class="button">6</button>
            <button class="button">*</button>
        </div>
        <div class="row">
            <button class="button">1</button>
            <button class="button">2</button>
            <button class="button">3</button>
            <button class="button">+</button>
        </div>
        <div class="row">
            <button class="button">0</button>
            <button class="button">.</button>
            <button class="button">%</button>
            <button class="button">-</button>
        </div>
        <div class="row">
            <button class="button">(</button>
            <button class="button">)</button>
            <button class="button">AC</button>
            <button class="button">=</button>
        </div>
    </div>
    <script src="jscode.js"></script>
</body>
</html>


Css
.heading{
    text-align:right;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    color:rgb(224, 45, 45);
}
body{
    justify-content: center;
    display: grid;
    background-color: #1f2021;
    place-items: center;
}

.container {
    padding: 1.5rem;
    background-color: #777777;
    height: 380px;
    width: 250px;
    justify-content: center;
    border-radius: 6px;
}
.row {
    align-items: center;
    justify-content: center;
    display: flex;
    gap: 1rem;
    padding: 6px 0;
}
.button{
    text-align: center;
    font-size: large;
    height: 50px;
    width: 50px;
    box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px, rgba(60, 64, 67, 0.15) 0px 2px 6px 2px;
    border-radius: 6px;
    cursor: pointer;
}
button:hover{
    background-color: rgb(245, 220, 242);
}
.input{

    align-items: center;
    display: flex;
    justify-content: center;
    width: auto;
}
.output{
    height: 45px;
    width: 242px;
    box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px, rgba(60, 64, 67, 0.15) 0px 2px 6px 2px;
    font-size: large;
    font-weight: 400;
    text-align: right;
    padding-right: 15px;
    margin-bottom: 1rem;
}

js
let ans = "";
let buttons = document.getElementsByClassName("button");
let op = document.querySelector(".output");
Array.from(buttons).forEach((button) => {
    button.addEventListener('click', (e) => {
        if (e.target.innerHTML === '=') {
            try {
                ans = eval(ans);
                // console.log(ans);
                if (ans !== Infinity) op.value = ans;
                else alert("Error input acceptable values to proceed");
                // ans="";
            }
            catch (e) {
                ans = "";
                op.value = ans;
                alert("Error ", e);
            }
        }
        else if (e.target.innerHTML === 'AC') {
            ans = "";
            op.value = ans;
        }
        else {
            ans = ans + e.target.innerHTML;
            console.log(ans);
            op.value = ans;
        }
    })
})

