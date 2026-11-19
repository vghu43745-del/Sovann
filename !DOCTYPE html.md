<!DOCTYPE html>  
<html lang="km">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>បណ្ណាល័យ ជុំ សុវណ្ណ - Sovann Library</title>  
    <style>  
        :root {  
            --primary: #6b4c9a;  
            --secondary: #e28e7c;  
            --bg: #fdf5f6;  
            --text: #222;  
        }  
        body { font-family: 'Kantumruy Pro', sans-serif; background-color: var(--bg); color: var(--text); margin: 0; padding: 0; }  
        header { background: var(--primary); color: white; padding: 1rem; text-align: center; }  
        nav { display: flex; justify-content: center; background: #fff; padding: 0.5rem; box-shadow: 0 2px 4px rgba(0,0,0,0.1); }  
        nav a { margin: 0 1rem; text-decoration: none; color: var(--primary); font-weight: bold; }  
        .container { padding: 2rem; max-width: 1000px; margin: auto; }  
        .card { background: white; padding: 1.5rem; border-radius: 10px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); margin-bottom: 1.5rem; }  
        button { background: var(--secondary); color: white; border: none; padding: 0.8rem 1.5rem; border-radius: 5px; cursor: pointer; }  
        #admin-panel { display: none; background: #eee; padding: 1rem; border-radius: 5px; }  
    </style>  
</head>  
<body>  
  
<header>  
    <h1>បណ្ណាល័យ ជុំ សុវណ្ណ</h1>  
    <p>Sovan Sensei - Digital Library</p>  
</header>  
  
<nav>  
    <a href="#" onclick="showSection('home')">ទំព័រដើម</a>  
    <a href="#" onclick="showSection('library')">បណ្ណាល័យ</a>  
    <a href="#" onclick="showSection('admin')" id="admin-nav" style="display:none;">Admin</a>  
    <a href="#" onclick="loginWithGoogle()" id="login-btn">Login with Google</a>  
</nav>  
  
<div class="container">  
    <div id="home" class="section">  
        <div class="card">  
            <h2>ស្វាគមន៍មកកាន់បណ្ណាល័យអនឡាញ</h2>  
            <p>ជ្រើសរើសសៀវភៅសម្រាប់អាន និងសិក្សាភាសាជប៉ុន**。**</p>  
        </div>  
    </div>  
  
    <div id="library" class="section" style="display:none;">  
        <h2>បញ្ជីសៀវភៅ</h2>  
        <div class="card">  
            <h3>ដោះសោភាសា (N5 - N1)</h3>  
            <button onclick="openBook('សៀវភៅកម្រិត N5')">អានសៀវភៅ</button>  
        </div>  
    </div>  
  
    <div id="admin" class="section" style="display:none;">  
        <div class="card">  
            <h2>ផ្ទាំងគ្រប់គ្រង Admin</h2>  
            <p>បន្ថែម ឬកែសម្រួលសៀវភៅនៅទីនេះ។</p>  
            <input type="text" id="bookTitle" placeholder="ឈ្មោះសៀវភៅថ្មី">  
            <button onclick="addBook()">បន្ថែម</button>  
        </div>  
    </div>  
</div>  
  
<script>  
    function showSection(sectionId) {  
        document.querySelectorAll('.section').forEach(s => s.style.display = 'none');  
        document.getElementById(sectionId).style.display = 'block';  
    }  
  
    function openBook(title) {  
        alert('កំពុងបើក៖ ' + title);  
    }  
  
    function loginWithGoogle() {  
        // Mock login for demonstration  
        const userEmail = prompt("បញ្ចូល Email របស់អ្នកដើម្បីធ្វើតេស្ត (ឧទាហរណ៍ admin@gmail.com):");  
        if (userEmail === "admin@gmail.com") {  
            alert("ចូលក្នុងប្រព័ន្ធជោគជ័យក្នុងនាមជា Admin!");  
            document.getElementById('admin-nav').style.display = 'inline';  
            document.getElementById('login-btn').innerText = 'Log out';  
        } else if (userEmail) {  
            alert("ចូលក្នុងប្រព័ន្ធជោគជ័យ!");  
            document.getElementById('login-btn').innerText = 'Log out';  
        }  
    }  
  
    function addBook() {  
        const title = document.getElementById('bookTitle').value;  
        if (title) {  
            alert("បានបន្ថែម៖ " + title);  
            document.getElementById('bookTitle').value = '';  
        } else {  
            alert("សូមបញ្ចូលឈ្មោះសៀវភៅ");  
        }  
    }  
</script>  
  
</body>  
</html>  
