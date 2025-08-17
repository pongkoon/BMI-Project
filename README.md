# BMI-Project

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMI Project</title>

    <style>
        body{
            font-family: prompt, sans-serif;
            text-align: center;
            background: linear-gradient(to right, #FCCBF0, #FF5A57);
        
        }

        button{
            width: 100px;
            height: 40px;
            border: 1px solid black;
            border-radius: 8px;
            font-size: 16px;
            background: linear-gradient(to right, #0033FF);
            color: white;
        }

        input{
            display: flex;
            flex-wrap: wrap;
            text-align: center;
            width: 200px;
            padding: 10px;
            margin: 10px;
            border-radius: 5px;
            border: 1px solid black;
           
        }

        .input-height, .input-weight {
            width: 200px;
            padding: 10px;
            margin: 10px auto;
            border-radius: 12px;
            border: 1px solid black;
            
        }

        .BMI{
            font-size: 18px;
        }
    </style>
</head>
<body>
    <h3>โปรแกรมคำณวน BMI</h3>
    <input type="text" id="height" placeholder="Enter Height (cm)" class="input-height">
    <br>
    <input type="text" id="weight" placeholder="Enter Weight (kg)" class="input-weight">
    <br>
    <button onclick="tobmi()">คำณวน</button>
    <div id="result"></div>
    <div id="BMI"></div>

   <script>
function tobmi() {
    var height = document.getElementById('height').value;
    var weight = document.getElementById('weight').value;

    if (height && weight) {
        var heightInMeters = height / 100;
        var bmi = weight / (heightInMeters * heightInMeters);

        var resultText = "";

        if (bmi < 18.5) {
            resultText = "ผอมเกินไป: " + bmi.toFixed(2);
        } 
        else if (bmi >= 18.5 && bmi < 24.9) {
            resultText = "น้ำหนักปกติ: " + bmi.toFixed(2);
        } 
        else if (bmi >= 25 && bmi < 29.9) {
            resultText = "	เริ่มอ้วน: " + bmi.toFixed(2);
        } 
        else if (bmi >= 30) {
            resultText = "อ้วนมากผิดปกติ: " + bmi.toFixed(2);
        }

        document.getElementById('BMI').innerHTML = resultText;
    } 
    else {
        document.getElementById('BMI').innerHTML = "⚠️ กรุณากรอกส่วนสูงและน้ำหนักให้ถูกต้อง";
    }
}
</script>
</body>
</html>
