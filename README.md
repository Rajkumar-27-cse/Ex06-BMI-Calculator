# Ex06-BMI-Calculator
## Date:31.8.26
## NAME : RAJKUMAR T
# REG .NO:212224040263

## AIM
To develop a responsive and interactive Body Mass Index (BMI) Calculator using React that allows users to input their height and weight, and calculates their BMI to categorize their health status (e.g., Underweight, Normal, Overweight, Obese).


## ALGORITHM
### STEP 1
Create a new React app using create-react-app.
Install React Router using:
npm install react-router-dom

### STEP 2
Create routing structure with react-router-dom:

Home route (/) – Intro or Navigation
BMI Calculator route (/bmi)
Result route (/result)

### STEP 3
Create a form to accept Height (in cm or m) and Weight (in kg).
On form submit, navigate to the result page with entered values via URL query params or context/state.

### STEP 4
Add structured sections for introduction, about, projects, and contact details.

### STEP 5
In the result component:
Extract height and weight from the route (URL or passed state).​

Convert height from cm to m if needed.

### STEP 6
Show calculated BMI.
Show category based on BMI range:
Underweight, Normal, Overweight, Obese, etc

### STEP 7
Provide a button to go back to the BMI form to calculate again.

### STEP 8
Add styling using CSS or Tailwind.



## PROGRAM
App.jsx

```
import React, { useState } from 'react';
import './App.css';

function App() {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState('');

  const calculateBMI = () => {
    if (weight && height) {
      const heightInMeters = height / 100;
      const calculatedBMI = (weight / (heightInMeters * heightInMeters)).toFixed(2);
      setBmi(calculatedBMI);
      getBMICategory(calculatedBMI);
    } else {
      alert('Please enter valid height and weight.');
    }
  };

  const getBMICategory = (bmi) => {
    if (bmi < 18.5) setMessage('Underweight');
    else if (bmi >= 18.5 && bmi < 24.9) setMessage('Normal weight');
    else if (bmi >= 25 && bmi < 29.9) setMessage('Overweight');
    else setMessage('Obese');
  };

  const resetFields = () => {
    setWeight('');
    setHeight('');
    setBmi(null);
    setMessage('');
  };

  return (
    <div className="container">
      <h1>BMI Calculator</h1>
      <div className="input-group">
        <label>Weight (kg):</label>
        <input
          type="number"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
          placeholder="Enter weight"
        />
      </div>
      <div className="input-group">
        <label>Height (cm):</label>
        <input
          type="number"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
          placeholder="Enter height"
        />
      </div>
      <button onClick={calculateBMI}>Calculate</button>
      <button className="reset" onClick={resetFields}>Reset</button>
      
      {bmi && (
        <div className="result">
          <h2>Your BMI: {bmi}</h2>
          <p className="message">{message}</p>
        </div>
      
      )}
    </div>
  );
}

export default App;
```

App.css
```
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(135deg, #fae0e0, #ffffff);
  margin: 0;
  padding: 0;
}

.container {
  max-width: 420px;
  margin: 80px auto;
  padding: 35px 25px;
  background-color: #ffffff;
  border-radius: 16px;
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.15);
  text-align: center;
  transition: transform 0.2s ease-in-out;
}

.container:hover {
  transform: translateY(-5px);
}

h1 {
  margin-bottom: 25px;
  font-size: 28px;
  color: #502c2c;
}

.input-group {
  margin-bottom: 20px;
  text-align: left;
}

.input-group label {
  display: block;
  margin-bottom: 6px;
  font-weight: 600;
  color: #5e3434;
}

.input-group input {
  width: 100%;
  padding: 12px;
  font-size: 16px;
  border: 2px solid #dfe6e9;
  border-radius: 10px;
  background-color: #f9f9f9;
  outline: none;
  transition: border-color 0.3s;
  box-sizing: border-box;
}

.input-group input:focus {
  border-color: #d40000;
}

button {
  padding: 12px 24px;
  font-size: 16px;
  margin: 12px 6px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  background-color: #d40000;
  color: white;
  transition: background-color 0.3s ease, transform 0.2s ease;
}

button:hover {
  background-color: #a70000;
  transform: scale(1.05);
}

button.reset {
  background-color: #a69595;
}

button.reset:hover {
  background-color: #8d7f7f;
}

.result {
  margin-top: 30px;
  padding: 20px;
  border-radius: 10px;
  background-color: #f1ecec;
  border-left: 5px solid #d40000;
  text-align: center;
}

.result h2 {
  margin-bottom: 10px;
  color: #502c2c;
}
.message {
  font-size: 18px;
  font-weight: bold;
  color: #502c2c;
}

footer {
  margin-top: 40px;
  font-size: 14px;
  color: #8d7f7f;
  font-weight: 500;
}
```

## OUTPUT

<img width="797" height="447" alt="image" src="https://github.com/user-attachments/assets/999149e7-0b6d-4b5b-b95f-cdf0c12d3cec" />
<img width="803" height="458" alt="image" src="https://github.com/user-attachments/assets/23bf1677-7ea9-4c21-96e8-ca09fa12692c" />



## RESULT
The program for creating Portfolio using HTML and CSS is executed successfully.



