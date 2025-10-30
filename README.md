<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Simple Nutrient Analyzer (No API)</title>
<style>
  body { font-family: Arial, sans-serif; max-width: 400px; margin: 20px; }
  input, button { padding: 8px; width: 100%; margin: 5px 0; }
  #result { margin-top: 20px; }
</style>
</head>
<body>
<h2>Simple Nutrient Analyzer (No API)</h2>
<input type="text" id="foodInput" placeholder="Enter food name (e.g. apple)" />
<button onclick="analyzeNutrition()">Analyze</button>
<div id="result"></div>

<script>
const nutritionData = {
  "apple": { calories: 52, protein: 0.3, fat: 0.2, carbs: 14 },
  "banana": { calories: 96, protein: 1.3, fat: 0.3, carbs: 27 },
  "orange": { calories: 47, protein: 0.9, fat: 0.1, carbs: 12 },
  "rice": { calories: 130, protein: 2.4, fat: 0.3, carbs: 28 },
  "egg": { calories: 155, protein: 13, fat: 11, carbs: 1.1 }
  // You can add more foods and their nutrients here
};

function analyzeNutrition() {
  const input = document.getElementById('foodInput').value.trim().toLowerCase();
  if (!input) {
    alert("Please enter a food name");
    return;
  }
  const result = nutritionData[input];
  if (result) {
    document.getElementById('result').innerHTML = `
      <h3>Nutrition for ${input.charAt(0).toUpperCase() + input.slice(1)} (per 100g):</h3>
      <p>Calories: ${result.calories} kcal</p>
      <p>Protein: ${result.protein} g</p>
      <p>Fat: ${result.fat} g</p>
      <p>Carbohydrates: ${result.carbs} g</p>
    `;
  } else {
    document.getElementById('result').textContent = "Sorry, nutrient data for this food is not in the database.";
  }
}
</script>
</body>
</html> 
