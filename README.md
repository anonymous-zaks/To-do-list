document.querySelector('#push').onclick= function() {
    if(document.querySelector('#newtask input').value.length == 0) {
        alert("Please Enter a Task");
    } else {
        document.querySelector('#tasks').innerHTML += `
            <div class="task">
                <span id="taskname">
                    ${document.querySelector('#newtask input').value}
                </span>
                <button class="delete">
                    <i class="bi bi-trash-fill"></i>
                </button>
            </div>
        `;
        
        var current_tasks = document.querySelectorAll('.delete');
        for(var i=0; i<current_tasks.length; i++) {
            current_tasks[i].onclick = function() {
                this.parentNode.remove();
            }
        }
        
       
        var tasks = document.querySelectorAll('.task');
        for(var i=0; i<tasks.length; i++) {
            tasks[i].onclick = function() {
                this.classList.toggle('completed');
            }
        }
         document.querySelector('#newtask input').value = "";
    }

}
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  height: 100vh;
  background-image: linear-gradient(
    135deg,
    #8052ec,
    #d161ff
  );
}
.container {
   
    width: 40%;
    min-width: 450px;
    position: absolute;
    transform: translate(-50%, -50%);
    top: 50%;
    left: 50%;
    padding: 30px 40px;
}
#newtask{
    background-color: white;
    padding:  30px 20px;
    position: relative;
    border-radius: 5px;
    box-shadow:0 15px 30px rgba(0, 0, 0, 0.3);
}
#newtask input {
    width: 80%;
    padding: 10px;
    border: 2px solid #d1d3d4;
    border-radius: 5px;
    font-size: 16px;
    position: relative;
    font-weight: 500;
    color: #111111;
}
#newtask input:focus {
    outline: none;
    border-color: #8052ec;
}
#newtask button {
    position: relative;
    background-color: #8052ec;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    float: right;
    font-family: poppins, sans-serif;
    font-weight: 500;
    width: 20%;
    height: 45px;
}
#tasks{
    margin-top: 60px;
    padding: 30px 20px;
    background-color: white;
    border-radius: 10px;
    box-shadow:0 15px 30px rgba(0, 0, 0, 0.3);
    position: relative;
}
.task{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 5px 10px;
    border-bottom: 1px solid #d1d3d4;
    height: 50px;
    margin-top: 10px;
    background-color: white;
    border-bottom: 2px solid #d1d3d4;
}
.task span{
    font-size: 18px;
    font-weight: 500;
    font-family: poppins, sans-serif;
}
.task button{
    background-color: #8052ec;
    border: none;
    color:white;
    cursor: pointer;
    outline: none;
    height: 100%;
    width: 40px;
}
.completed {
    text-decoration: line-through;
    color: #1397d9;
}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple To Do list</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500&display=swap" rel="stylesheet">
  
     <link href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css" rel="stylesheet">


</head>
<body>
    <div class="container">
        <div id="newtask">
            <input type="text" placeholder="Task To Be done">
            <button id="push">Add</button>
        </div>
        <div id="tasks">
            
        </div>
    </div>

    <script src="main.js"></script>
</body>
</html>
