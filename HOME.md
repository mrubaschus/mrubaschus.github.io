layout: page
title: "Home"
permalink: /home


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My Simple Web Page</title>
    <style>
        body {
            font-family: Arial, Helvetica, sans-serif;
        }
        .header {
            padding: 80px;
            text-align: center;
            background: #1abc9c;
            color: white;
        }
        .header h1 {
            font-size: 40px;
        }
        .navbar {
            overflow: hidden;
            background-color: #333;
        }
        .navbar a {
            float: left;
            display: block;
            color: white;
        }
    </style>
</head>
<body>
    <div class="header">
        <h1>My Website</h1>
        <p>A website created by me.</p>
    </div>
    <div class="navbar">
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Services</a>
        <a href="#" class="right">Contact</a>
    </div>
    <div class="main-content">
        <h2>Welcome to My Web Page</h2>
        <p>This is a simple example of an HTML webpage. Feel free to customize it further!</p>
    </div>
    <div class="footer">
        <p>© 2024 MyWebsite.com</p>
    </div>
</body>
</html>
