<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Join Our Network</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f4f8;
      margin: 0;
      padding: 0;
    }
    .container {
      max-width: 500px;
      margin: 50px auto;
      padding: 20px;
      background: white;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      border-radius: 10px;
    }
    h1 {
      text-align: center;
      color: #2c3e50;
    }
    input, button {
      width: 100%;
      padding: 10px;
      margin-top: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      background-color: #3498db;
      color: white;
      font-weight: bold;
      border: none;
      cursor: pointer;
    }
    button:hover {
      background-color: #2980b9;
    }
    .message {
      text-align: center;
      margin-top: 20px;
      color: green;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Join Our Network</h1>
    <form id="leadForm">
      <input type="text" id="name" name="name" placeholder="Your Name" required />
      <input type="text" id="place" name="place" placeholder="Your Location" required />
      <input type="tel" id="mobile" name="mobile" placeholder="Mobile Number" required />
      <button type="submit">Submit</button>
    </form>
    <div class="message" id="message"></div>
  </div>  <script>
    document.getElementById("leadForm").addEventListener("submit", function (e) {
      e.preventDefault();
      const name = document.getElementById("name").value;
      const place = document.getElementById("place").value;
      const mobile = document.getElementById("mobile").value;

      // Example of sending data securely (replace with your backend URL)
      fetch("https://your-backend-endpoint.com/submit", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({ name, place, mobile }),
      })
        .then((res) => res.json())
        .then((data) => {
          document.getElementById("message").textContent = "Thank you! We will contact you soon.";
          document.getElementById("leadForm").reset();
        })
        .catch((err) => {
          console.error("Error:", err);
        });
    });
  </script></body>
</html>
