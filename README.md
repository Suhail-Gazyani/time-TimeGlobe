<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Country Time Finder</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f4f8;
      padding: 20px;
      text-align: center;
    }

    h1 {
      color: #333;
    }

    input, button {
      padding: 10px;
      font-size: 16px;
      margin: 10px;
    }

    #result {
      margin-top: 20px;
      font-size: 24px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <h1>🌍 Country Time Finder</h1>

  <input type="text" id="countryInput" placeholder="Enter a country (e.g., USA)">
  <button onclick="getTime()">Get Time</button>

  <div id="result"></div>

  <script>
    const countryTimezones = {
      "Usa": "America/New_York",
      "Pakistan": "Asia/Karachi",
      "India": "Asia/Kolkata",
      "UK": "Europe/London",
      "Uae": "Asia/Dubai",
      "Japan": "Asia/Tokyo",
      "China": "Asia/Shanghai",
      "Germany": "Europe/Berlin",
      "France": "Europe/Paris",
      "Australia": "Australia/Sydney",
      "Canada": "America/Toronto",
      "Malasyia": "Asia/Kuala_Lumpur"
    };

    function getTime() {
      const country = document.getElementById("countryInput").value.trim();
      const timezone = countryTimezones[country];

      if (!timezone) {
        document.getElementById("result").innerText = "❌ Country not found. Try another.";
        return;
      }

      const now = new Date().toLocaleString("en-US", { timeZone: timezone });
      document.getElementById("result").innerText = `🕒 Time in ${country}: ${now}`;
    }
  </script>
</body>
</html>
