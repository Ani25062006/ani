# ani
web depvelopment basic code
 <!DOCTYPE html> 
<html lang="en"> 
<head> 
    <meta charset="UTF-8"> 
    <meta name="viewport" content="width=device-width, initialscale=1.0"> 
    <title>Counter with setTimeout and clearTimeout</title> 
    <style>         body { 
            font-family: Arial, sans-serif;             display: flex;             justify-content: center;             align-items: center;             height: 100vh;             margin: 0; 
            background-color: #f0f0f0; 
        }  
 
            margin: 5px;             cursor: pointer;             border: none;             border-radius: 5px;             background-color: #007bff;             color: white; 
        }  
        button:hover { 
            background-color: #0056b3; 
        } 
    </style> 
</head> 
<body> 
    <div class="container"> 
        <h1>Counter</h1> 
        <div id="counter">0</div> 
        <button id="startButton">Start</button> 
        <button id="stopButton">Stop</button> 
    </div>     <script>         let count = 0;         let timerId;  
 const counterElement = document.getElementById('counter');         const startButton = document.getElementById('startButton');         const stopButton = document.getElementById('stopButton'); 
 
        function updateCounter() {             count++; 
            counterElement.textContent = count;             timerId = setTimeout(updateCounter, 1000); 
        }          function startCounter() {             if (!timerId) {                 updateCounter(); 
            } 
        }          function stopCounter() {             clearTimeout(timerId);             timerId = null; 
        }          startButton.addEventListener('click', startCounter);         stopButton.addEventListener('click', stopCounter); 
    </script> 
 
ANANYA 
AIM: Add JavaScript validations in registration form. Name text field should not accept any digit, age text field should not accept characters, perform validations on email on lost focus of text field. Empty fields should not be allowed. 
CODE: 
<!DOCTYPE html> 
<html> 
<head> 
        } 
        } 
<body> 
        <input type="text" id="age" name="age"> 
        <span id="ageError" class="error"></span><br><br> 
        <label for="email">Email:</label> 
        <input type="text" id="email" name="email" onblur="validateEmail()"> 
        <span id="emailError" class="error"></span><br><br> 
        <label>Gender:</label> 
        <input type="radio" id="male" name="gender" value="male"> 
        <label for="male">Male</label> 
 
        <input type="radio" id="female" name="gender" value="female"> 
        <label for="female">Female</label> 
        <span id="genderError" class="error"></span><br><br> 
        <label for="address">Address:</label> 
        <input type="text" id="address" name="address"> 
        <span id="addressError" class="error"></span><br><br> 
       <label for="class">Class:</label> 
 
            // Name validation 
            const name = document.getElementById('name').value;             const nameError = document.getElementById('nameError'); 
            if (name === "") {                 nameError.textContent = "Name is required"; 
                isValid = false; 
            } else if (/\d/.test(name)) {                 nameError.textContent = "Name should not contain any digits"; 
                isValid = false; 
            } else { 
                nameError.textContent = ""; 
            } 
             } 
                emailError.textContent = ""; 
            } 
            // Gender validation 
            const gender = document.querySelector('input[name="gender"]:checked');             const genderError = document.getElementById('genderError'); 
            if (!gender) { 
                genderError.textContent = "Gender is required"; 
                isValid = false; 
            } else { 
                genderError.textContent = ""; 
            } 
            // Address validation             const address = document.getElementById('address').value;             const addressError = document.getElementById('addressError'); 
            } 
            } 
                document.getElementById('successMessage').textContent = "Thanks, successful registration!"; 
            } 
            return isValid; 
        } 
        function validateEmail() {             const email = document.getElementById('email').value;             const emailError = document.getElementById('emailError');             const emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$/; 
            if (!emailPattern.test(email)) {                 emailError.textContent = "Invalid email format"; 
            } else { 
                emailError.textContent = ""; 
</html> 

 
 
