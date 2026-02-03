# ignite
<!DOCTYPE html>
<html>
<head>
  <title>IGNITE – Freshers Party</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>🔥 IGNITE – Freshers Party 🔥</h1>
  <h2>Ticket Price: ₹300</h2>

  <div class="stats">
    <p id="students">Students Paid: 0</p>
    <p id="amount">Total Collected: ₹0</p>
  </div>

  <script src="app.js"></script>
</body>
</html>

<!DOCTYPE html>
<html>
<head>
  <title>IGNITE Admin</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<div id="login">
  <h2>Admin Login</h2>
  <input type="password" id="pin" placeholder="Enter PIN">
  <button onclick="login()">Login</button>
</div>

<div id="panel" style="display:none;">
  <h2>Admin Panel</h2>
  <button onclick="addStudent()">➕ Add Paid Student</button>
  <button onclick="removeStudent()">➖ Remove Student</button>
</div>

<script src="app.js"></script>
</body>
</html>

body {
  background: #020617;
  color: white;
  font-family: Arial;
  text-align: center;
}

.stats {
  background: #0f172a;
  padding: 20px;
  margin: 20px;
  border-radius: 10px;
}

button, input {
  padding: 10px;
  margin: 5px;
}

let students = localStorage.getItem("students") || 0;
students = parseInt(students);

function update() {
  document.getElementById("students").innerText =
    "Students Paid: " + students;
  document.getElementById("amount").innerText =
    "Total Collected: ₹" + (students * 300);
}

update();

// ADMIN
function login() {
  if (document.getElementById("pin").value === "6969") {
    document.getElementById("login").style.display = "none";
    document.getElementById("panel").style.display = "block";
  } else {
    alert("Wrong PIN");
  }
}

function addStudent() {
  students++;
  localStorage.setItem("students", students);
  update();
}

function removeStudent() {
  if (students > 0) students--;
  localStorage.setItem("students", students);
  update();
}

your-link/admin.html
