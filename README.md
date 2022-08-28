<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>Login</title>
    <link rel="stylesheet" href="login.css">
</head>

<body>
  
   <?php 

  if(isset($_POST['Sign_up']))
  
   {
    $servername = "localhost";
    $username = "root";
    $password = "";
    $dbname = "user_login";

    $Name = $_POST['user_name'];
    $Email  = $_POST['user_email'];
    $Date = $_POST['user_dob'];
    $Contact = $_POST['user_contact'];
    $Password = $_POST['user_password'];

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);
// Check connection
if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}

$sql = "INSERT INTO user_details (Name, Email, Date, Contact, Password)
VALUES ('$Name','$Email', '$Date', '$Contact', '$Password')";

if ($conn->query($sql) === TRUE) {
  echo "New record created successfully";
} else {
  echo "Error: " . $sql . "<br>" . $conn->error;
  } 

  }
  else
  {
    echo "Login to Access";
  }
?>
      

<div class="login-box">
  <h2>Register</h2>
  <form method="POST" action="#">
    <div class="user-box">
      <input type="text" name="user_name">
      <label>Name</label>
    </div>
    <div class="user-box">
      <input type="email" name="user_email" class="form-control" id="user_email" aria-describedby="emailHelp">
      <label>Email</label>
    </div>
    <div class="user-box">
      <input type="password" name="user_password">
      <label>Password</label>
    </div>
    <div class="user-box">
      <input type="Contact" name="user_contact">
      <label>Contact</label>
    </div>
    <div class="user-box">
      <input type="date" name="user_dob">
      <label>Select D.O.B</label>
    </div>
    <a href="">
      <span></span>
      <span></span>
      <span></span>
      <span></span>
      <input type="submit" value="submit" name="Sign_up"> 
      click here
    </a> 
  </form>
</div>
  </body>

