#HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    

    <title>Calculator - By Code Traversal</title>
  </head>
  <body>
    <div class="container">
      <div class="calculator">
        <input type="text" id="inputBox" placeholder="0" />
        <div>
          <button class="button operator">AC</button>
          <button class="button operator">DEL</button>
          <button class="button operator">%</button>
          <button class="button operator">/</button>
        </div>
        <div>
          <button class="button">7</button>
          <button class="button">8</button>
          <button class="button">9</button>
          <button class="button operator">*</button>
        </div>
        <div>
          <button class="button">4</button>
          <button class="button">5</button>
          <button class="button">6</button>
          <button class="button operator">-</button>
        </div>
        <div>
          <button class="button">1</button>
          <button class="button">2</button>
          <button class="button">3</button>
          <button class="button operator">+</button>
        </div>

        <div>
          <button class="button">00</button>
          <button class="button">0</button>
          <button class="button">.</button>
          <button class="button equalBtn">=</button>
        </div>
      </div>
    </div>

    <script src="script.js"></script>
  </body>
</html><!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="style.css" />
    

    <title>Calculator - By Code Traversal</title>
  </head>
  <body>
    <div class="container">
      <div class="calculator">
        <input type="text" id="inputBox" placeholder="0" />
        <div>
          <button class="button operator">AC</button>
          <button class="button operator">DEL</button>
          <button class="button operator">%</button>
          <button class="button operator">/</button>
        </div>
        <div>
          <button class="button">7</button>
          <button class="button">8</button>
          <button class="button">9</button>
          <button class="button operator">*</button>
        </div>
        <div>
          <button class="button">4</button>
          <button class="button">5</button>
          <button class="button">6</button>
          <button class="button operator">-</button>
        </div>
        <div>
          <button class="button">1</button>
          <button class="button">2</button>
          <button class="button">3</button>
          <button class="button operator">+</button>
        </div>

        <div>
          <button class="button">00</button>
          <button class="button">0</button>
          <button class="button">.</button>
          <button class="button equalBtn">=</button>
        </div>
      </div>
    </div>

    <script src="script.js"></script>
  </body>
</html>
#CSS
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background:rgb(40, 39, 39)
}

.calculator{
    border: 3px solid #e8edf3;
    padding: 20px;
    border-radius: 16px;
    background: transparent;
    box-shadow: 0px 3px 15px rgba(238, 214, 214, 0.5);

}

input{
    width: 320px;
    border: none;
    padding: 24px;
    margin: 10px;
    background: transparent;
    box-shadow: 0px 3px 15px rgbs(84, 84, 84, 0.1);
    font-size: 40px;
    text-align: right;
    cursor: pointer;
    color: #5c4141;
}

input::placeholder{
    color: #f7f3f3;
}

button{
    border: none;
    width: 60px;
    height: 60px;
    margin: 10px;
   
   
    color: #252424;
    font-size: 20px;
    box-shadow: -8px -8px 15px rgba(156, 52, 52, 0.1);
    cursor: pointer;
}

.equalBtn{
    background-color: #ef7918;
}

.operator{
    color: hsl(94, 71%, 54%);
}
#JS
let input = document.getElementById('inputBox');
let buttons = document.querySelectorAll('button');

let string = "";
let arr = Array.from(buttons);
arr.forEach(button => {
    button.addEventListener('click', (e) =>{
        if(e.target.innerHTML == '='){
            string = eval(string);
            input.value = string;
        }

        else if(e.target.innerHTML == 'AC'){
            string = "";
            input.value = string;
        }
        else if(e.target.innerHTML == 'DEL'){
            string = string.substring(0, string.length-1);
            input.value = string;
        }
        else{
            string += e.target.innerHTML;
            input.value = string;
        }
        
    })
})
