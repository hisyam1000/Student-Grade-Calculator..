function calculateBMI() {

    let weight = Number(document.getElementById("weight").value);
    let heightCm = Number(document.getElementById("height").value);

    if (weight <= 0 || heightCm <= 0) {
        document.getElementById("result").innerHTML =
            "Please enter valid weight and height!";
        return;
    }

    let heightM = heightCm / 100;
    let bmi = weight / (heightM * heightM);

    let category;
    if (bmi < 18.5) {
        category = "Underweight";
    } else if (bmi < 25) {
        category = "Normal weight";
    } else if (bmi < 30) {
        category = "Overweight";
    } else {
        category = "Obese";
    }

    document.getElementById("result").innerHTML =
        "BMI: " + bmi.toFixed(2) + "<br>Category: " + category;

    localStorage.setItem("lastBMI", bmi.toFixed(2));
}
