# FSJ_second_haha
this project contains the two page html +javascript project that takes login from the user and make the list just niche
<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <title>स्वागत पृष्ठ</title>
  <style>
    body {
      font-family: sans-serif;
      text-align: center;
      padding: 50px;
      background: #f0f0f0;
    }
    .hidden {
      display: none;
    }
    .card {
      background: white;
      padding: 30px;
      margin: 20px auto;
      width: 300px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    input {
      padding: 10px;
      width: 90%;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      padding: 10px 20px;
      margin-top: 10px;
      background: #28a745;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    ul {
      list-style-type: none;
      padding: 0;
    }
  </style>
</head>
<body>

  <!-- Page 1: Greeting and Login -->
  <div id="page1" class="card">
    <h2>नमस्ते! आपका स्वागत है।</h2>
    <button onclick="goToLogin()">लॉगिन करें</button>
  </div>

  <!-- Page 2: Login Form and User List -->
  <div id="page2" class="card hidden">
    <h2>लॉगिन विवरण दर्ज करें</h2>
    <input type="text" id="username" placeholder="उपयोगकर्ता नाम" required>
    <input type="password" id="password" placeholder="पासवर्ड" required>
    <br>
    <button onclick="submitForm()">सबमिट करें</button>

    <h3>यूज़र सूची:</h3>
    <ul id="userList"></ul>
  </div>

  <script>
    function goToLogin() {
      document.getElementById('page1').classList.add('hidden');
      document.getElementById('page2').classList.remove('hidden');
    }

    const userList = [];

    function submitForm() {
      const username = document.getElementById('username').value.trim();
      const password = document.getElementById('password').value;

      if (username === '' || password === '') {
        alert("कृपया दोनों फ़ील्ड भरें।");
        return;
      }

      userList.push(username);
      updateUserList();
      document.getElementById('username').value = '';
      document.getElementById('password').value = '';
    }

    function updateUserList() {
      const list = document.getElementById('userList');
      list.innerHTML = '';
      userList.forEach(user => {
        const li = document.createElement('li');
        li.textContent = user;
        list.appendChild(li);
      });
    }
  </script>
</body>
</html>
