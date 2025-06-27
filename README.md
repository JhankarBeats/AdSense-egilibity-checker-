<!DOCTYPE html>
<html>
<head>
  <title>AdSense Eligibility Checker Tool</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      padding: 20px;
    }
    .container {
      max-width: 600px;
      margin: auto;
      background: #fff;
      padding: 20px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h2 {
      text-align: center;
      color: #333;
    }
    label {
      display: block;
      margin: 10px 0 5px;
    }
    input[type="checkbox"] {
      margin-right: 10px;
    }
    button {
      display: block;
      width: 100%;
      padding: 10px;
      background: #28a745;
      color: white;
      font-size: 16px;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background: #218838;
    }
    .result {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
      text-align: center;
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>AdSense Eligibility Checker</h2>
    <form id="eligibilityForm">
      <label><input type="checkbox" id="domainAge"> Website is at least 6 months old</label>
      <label><input type="checkbox" id="sufficientContent"> Website has sufficient original content</label>
      <label><input type="checkbox" id="privacyPolicy"> Website has a Privacy Policy page</label>
      <label><input type="checkbox" id="copyrightFree"> No copyrighted material is used</label>
      <label><input type="checkbox" id="goodDesign"> Website has a clean, user-friendly design</label>
      <label><input type="checkbox" id="tldDomain"> Using a top-level domain (e.g., .com, .net)</label>

      <button type="button" onclick="checkEligibility()">Check Eligibility</button>
    </form>
    <div class="result" id="resultText"></div>
  </div>

  <script>
    function checkEligibility() {
      const checks = [
        document.getElementById('domainAge').checked,
        document.getElementById('sufficientContent').checked,
        document.getElementById('privacyPolicy').checked,
        document.getElementById('copyrightFree').checked,
        document.getElementById('goodDesign').checked,
        document.getElementById('tldDomain').checked
      ];

      const passed = checks.filter(Boolean).length;

      const resultText = document.getElementById('resultText');
      if (passed === 6) {
        resultText.innerHTML = "✅ Your website is eligible for Google AdSense!";
        resultText.style.color = "green";
      } else if (passed >= 4) {
        resultText.innerHTML = "⚠️ Your website is partially eligible. Improve the missing areas.";
        resultText.style.color = "orange";
      } else {
        resultText.innerHTML = "❌ Your website is not eligible for Google AdSense. Please meet all the requirements.";
        resultText.style.color = "red";
      }
    }
  </script>
</body>
</html>
