# feb-2025-avasjcript-events-and-basic-interactivity

HTML Structure

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JavaScript Events and Basic Interactivity</title>
  <style>
    /* Simple styling */
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
    }
    #successMessage {
      color: green;
      display: none;
    }
    #errorMessage {
      color: red;
      display: none;
    }
  </style>
</head>
<body>

  <h1>Interactive Form</h1>

  <!-- Simple form with a text input and submit button -->
  <form id="userForm">
    <label for="username">Username:</label>
    <input type="text" id="username" name="username" required>
    <span id="errorMessage">Username cannot be empty!</span><br><br>
    
    <button type="submit">Submit</button>
  </form>

  <p id="successMessage">Form submitted successfully!</p>

  <!-- Interactive Button -->
  <button id="toggleMessageBtn">Click to Toggle Message</button>
  <p id="toggleMessage" style="display: none;">You toggled the message!</p>

  <script src="app.js"></script>
</body>
</html>

JavaScript (app.js)

// Event listener to handle form submission and validation
document.getElementById("userForm").addEventListener("submit", function(event) {
  event.preventDefault(); // Prevent form from submitting

  let username = document.getElementById("username").value.trim();
  
  if (username === "") {
    // Display error message if the username is empty
    document.getElementById("errorMessage").style.display = "inline";
    document.getElementById("successMessage").style.display = "none";
  } else {
    // Display success message if the username is valid
    document.getElementById("errorMessage").style.display = "none";
    document.getElementById("successMessage").style.display = "inline";
  }
});

// Event listener for the interactive button to toggle message visibility
document.getElementById("toggleMessageBtn").addEventListener("click", function() {
  let message = document.getElementById("toggleMessage");
  if (message.style.display === "none") {
    message.style.display = "block";
  } else {
    message.style.display = "none";
  }
});
