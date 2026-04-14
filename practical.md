 
 
Slip no :- 1 q1  
## Student Profile Webpage (HTML & CSS)

```html
<!DOCTYPE html>
<html>
<head>
 <title>Student Profile</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 }
 .container {
 display: flex;
 width: 80%;
 margin: auto;
 border: 1px solid black;
 }

 .column1 {
 width: 25%;
 background-color: #f2f2f2;
 padding: 20px;
 }

 .column2 {
 width: 75%;
 padding: 20px;
 }

 a {
 display: block;
 margin: 10px 0;
 text-decoration: none;
 color: blue;
 font-weight: bold;
 }

 img {
 width: 150px;
 height: 150px;
 border: 1px solid black;
 }

 </style>
</head>	
<body>
<h2 align="center">Student Profile Page</h2>
<div class="container">
 <!-- Column 1 -->
 <div class="column1">
 <h3>Menu</h3>

 <a href="#">Home</a>
 <a href="#">Contact Us</a>
 <a href="#">About Us</a>
 </div>

 <!-- Column 2 -->
 <div class="column2">
 <h3>Student Details</h3>
 <p><b>Roll Number:</b> 101</p>
 <p><b>Name:</b> Nikita</p>
 <p><b>Contact:</b> 9876543210</p>
 <p><b>Class:</b> TYBSc IT</p>
 <p><b>Area of Interest:</b> Web Development</p>
 <p><b>Photo:</b></p>
 <img src="student.jpg" alt="Student Photo">
 </div>
</div>
</body>
</html>
```
q2-->
## Simple Login Form (HTML, CSS, JavaScript)

```html
<!DOCTYPE html>
<html>
<head>
<title>Login</title>
<style>
body{
  display:flex;
  justify-content:center;
  align-items:center;
  height:100vh;
  font-family:Arial;
}
.box{
  border:1px solid black;
  padding:20px;
  text-align:center;
}
</style>
</head>
<body>

<div class="box">
  <h3>Login</h3>
  <form onsubmit="login(event)">
    <input type="text" id="u" placeholder="Username"><br><br>
    <input type="password" id="p" placeholder="Password"><br><br>
    <button>Login</button>
  </form>
</div>

<script>
function login(e){
  e.preventDefault();
  var u=document.getElementById("u").value;
  var p=document.getElementById("p").value;

  if(u==p && u!="")
    alert("Welcome");
  else
    alert("Wrong");
}
</script>

</body>
</html>
```
slip5 q1-->
## User Registration System (MySQL + HTML + PHP)

### Step 1: Create Database and Table

```sql
CREATE DATABASE userdb;

CREATE TABLE users (
 id INT AUTO_INCREMENT PRIMARY KEY,
 fullname VARCHAR(100),
 contact VARCHAR(15),
 email VARCHAR(100),
 password VARCHAR(255)
);
```

---

### Step 2: Registration Form (register.html)

```html
<html>
<head>
 <title>User Registration</title>
</head>
<body>

<h2>User Registration Form</h2>

<form method="post" action="register.php">
Full Name:
<input type="text" name="fullname" required>
<br><br>

Contact No:
<input type="text" name="contact" required>
<br><br>

Email:
<input type="email" name="email" required>
<br><br>

Password:
<input type="password" name="password" required>
<br><br>

Confirm Password:
<input type="password" name="confirm_password" required>
<br><br>

<input type="submit" name="submit" value="Register">
</form>

</body>
</html>
```

---

### Step 3: PHP Backend (register.php)

```php
<?php
// Database connection
$conn = mysqli_connect("localhost", "root", "", "userdb");

// Check connection
if (!$conn) {
    echo "Connection Failed: " . mysqli_connect_error();
}

// Check form submit
if (isset($_POST['submit'])) {

    // Get form data
    $fullname = $_POST['fullname'];
    $contact = $_POST['contact'];
    $email = $_POST['email'];
    $password = $_POST['password'];
    $confirm_password = $_POST['confirm_password'];

    // Check password match
    if ($password != $confirm_password) {
        echo "Password and Confirm Password do not match!";
        exit();
    }

    // Encrypt password
    $encrypted_password = password_hash($password, PASSWORD_DEFAULT);

    // Insert query
    $sql = "INSERT INTO users (fullname, contact, email, password)
            VALUES ('$fullname', '$contact', '$email', '$encrypted_password')";

    // Execute query
    if (mysqli_query($conn, $sql)) {
        echo "Registration Successful!";
    } else {
        echo "Error: " . mysqli_error($conn);
    }
}

// Close connection
mysqli_close($conn);
?>
```
q2-->
## Student Profile Webpage (HTML & CSS)

```html
<!DOCTYPE html>
<html>
<head>
 <title>Student Profile</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 }
 .container {
 display: flex;
 width: 80%;
 margin: auto;
 border: 1px solid black;
 }

 .column1 {
 width: 25%;
 background-color: #f2f2f2;
 padding: 20px;
 }

 .column2 {
 width: 75%;
 padding: 20px;
 }

 a {
 display: block;
 margin: 10px 0;
 text-decoration: none;
 color: blue;
 font-weight: bold;
 }

 img {
 width: 150px;
 height: 150px;
 border: 1px solid black;
 }
 </style>
</head>	
<body>

<h2 align="center">Student Profile Page</h2>

<div class="container">

 <!-- Column 1 -->
 <div class="column1">
 <h3>Menu</h3>

 <a href="#">Home</a>
 <a href="#">Contact Us</a>
 <a href="#">About Us</a>
 </div>

 <!-- Column 2 -->
 <div class="column2">
 <h3>Student Details</h3>
 <p><b>Roll Number:</b> 101</p>
 <p><b>Name:</b> Nikita</p>
 <p><b>Contact:</b> 9876543210</p>
 <p><b>Class:</b> TYBSc IT</p>
 <p><b>Area of Interest:</b> Web Development</p>
 <p><b>Photo:</b></p>
 <img src="student.jpg" alt="Student Photo">
 </div>

</div>

</body>
</html>
```
Slip8 --> q1  
## HTML Program for Seven Colored Lines

```html
<!DOCTYPE html>
<html>
<head>
 <title>Seven Colored Lines</title>
 <style>
  body{
    text-align:center;
    font-family: Arial, sans-serif;
  }
  p{
    font-size:18px;
    font-weight:bold;
  }
 </style>
</head>
<body>

<h2>Seven Colored Lines</h2>

<p style="color:red;">This line is Red</p>
<p style="color:blue;">This line is Blue</p>
<p style="color:green;">This line is Green</p>
<p style="color:orange;">This line is Orange</p>
<p style="color:purple;">This line is Purple</p>
<p style="color:brown;">This line is Brown</p>
<p style="color:black;">This line is Black</p>

</body>
</html>
```
q2-->
## PHP Program for Password Validation

```php
<?php
$message = "";

if ($_SERVER["REQUEST_METHOD"] == "POST") {

    $username = $_POST['username'];
    $password = $_POST['password'];

    // Validation
    $hasLetter = preg_match('/[a-zA-Z]/', $password);
    $hasNumber = preg_match('/[0-9]/', $password);
    $hasSpecial = preg_match('/[!@#$%^&*(),.?":{}|<>]/', $password);
    $isLongEnough = strlen($password) > 8;

    if ($hasLetter && $hasNumber && $hasSpecial && $isLongEnough) {
        $message = "<p style='color:green;'>You entered a strong password</p>";
    } else {
        $message = "<p style='color:red;'>Enter complex password</p>";
    }
}
?>

<!DOCTYPE html>
<html>
<head>
    <title>Password Validation</title>
</head>
<body>

<h2>Login</h2>

<form method="POST">
    Username: <input type="text" name="username" required><br><br>
    
    Password: <input type="password" name="password" required><br><br>
    
    <button type="submit">Submit</button>
</form>

<!-- Display message -->
<?php echo $message; ?>

</body>
</html>
```
Slip no 9 :- q1 
 ## Bus Ticket Reservation Form (HTML & CSS)

```html
<!DOCTYPE html>
<html>
<head>
 <title>Bus Ticket Reservation</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 }
 table {
 margin: auto;
 border-collapse: collapse;
 }
 td {
 padding: 8px;
 }
 h2 {
 text-align: center;
 }
 </style>
</head>
<body>

<h2>Bus Ticket Reservation Form</h2>

<form>
<table border="1">

 <tr>
 <td>Name</td>
 <td><input type="text" name="name"></td>
 </tr>

 <tr>
 <td>Address</td>
 <td><textarea name="address" rows="3" cols="20"></textarea></td>
 </tr>

 <tr>
 <td>Contact No</td>
 <td><input type="tel" name="contact"></td>
 </tr>

 <tr>
 <td>Source Station</td>
 <td>
 <select name="source">
 <option>Select</option>
 <option>Mumbai</option>
 <option>Pune</option>
 <option>Nashik</option>
 <option>Nagpur</option>
 </select>
 </td>
 </tr>

 <tr>
 <td>Destination Station</td>
 <td>
 <select name="destination">
 <option>Select</option>
 <option>Mumbai</option>
 <option>Pune</option>
 <option>Nashik</option>
 <option>Nagpur</option>
 </select>
 </td>
 </tr>

 <tr>
 <td>Date of Booking</td>
 <td><input type="date" name="booking_date"></td>
 </tr>

 <tr>
 <td>Date of Journey</td>
 <td><input type="date" name="journey_date"></td>
 </tr>

 <tr>
 <td>No. of Passengers</td>
 <td><input type="number" name="passengers"></td>
 </tr>

 <tr>
 <td>Name of Passenger</td>
 <td><input type="text" name="passenger_name"></td>
 </tr>

 <tr>
 <td>Gender of Passenger</td>
 <td>
 <input type="radio" name="gender"> Male
 <input type="radio" name="gender"> Female
 </td>
 </tr>

 <tr>
 <td colspan="2" align="center">
 <input type="submit" value="Book Ticket">
 <input type="reset" value="Reset">
 </td>
 </tr>

</table>
</form>

</body>
</html>
```
q2-->
## Customer Registration Form (HTML & CSS)

```html
<!DOCTYPE html>
<html>
<head>
 <title>Customer Registration Form</title>
 <style>
 body {
 font-family: Arial, sans-serif;
 }
 table {
 margin: auto;
 border-collapse: collapse;
 }
 td {
 padding: 8px;
 }
 h2 {
 text-align: center;
 }
 </style>
</head>

<body>
<h2>Departmental Store Customer Registration</h2>

<form>
<table border="1">

 <tr>
 <td>Name</td>
 <td><input type="text" name="name"></td>
 </tr>

 <tr>
 <td>Contact No</td>
 <td><input type="tel" name="contact"></td>
 </tr>

 <tr>
 <td>Gender</td>
 <td>
 <input type="radio" name="gender"> Male
 <input type="radio" name="gender"> Female
 <input type="radio" name="gender"> Other
 </td>
 </tr>

 <tr>
 <td>Preferred Days of Purchasing</td>
 <td>
 <input type="checkbox" name="day"> Monday
 <input type="checkbox" name="day"> Tuesday
 <input type="checkbox" name="day"> Wednesday
 <input type="checkbox" name="day"> Thursday
 <input type="checkbox" name="day"> Friday
 <input type="checkbox" name="day"> Saturday
 <input type="checkbox" name="day"> Sunday
 </td>
 </tr>

 <tr>
 <td>Favorite Item</td>
 <td>
 <select name="item">
 <option>Select Item</option>
 <option>Groceries</option>
 <option>Clothes</option>
 <option>Electronics</option>
 <option>Stationery</option>
 <option>Cosmetics</option>
 </select>
 </td>
 </tr>

 <tr>
 <td>Suggestions</td>
 <td>
 <textarea name="suggestions" rows="4" cols="25"></textarea>
 </td>
 </tr>

 <tr>
 <td colspan="2" align="center">
 <input type="submit" value="Submit">
 <input type="reset" value="Reset">
 </td>
 </tr>

</table>
</form>

</body>
</html>
```
Slip 10  → 
## PHP Program to Create XML File (Student Data)

```php
<?php
// Create XML document
$xml = new DOMDocument("1.0", "UTF-8");
$xml->formatOutput = true;

// Root element
$root = $xml->createElement("root");
$xml->appendChild($root);

// Student 1
$student = $xml->createElement("Student");
$student->appendChild($xml->createElement("StudentID", "101"));
$student->appendChild($xml->createElement("Name", "Amit"));
$student->appendChild($xml->createElement("Age", "20"));
$student->appendChild($xml->createElement("Gender", "Male"));
$student->appendChild($xml->createElement("Program", "BSc"));
$root->appendChild($student);

// Student 2
$student = $xml->createElement("Student");
$student->appendChild($xml->createElement("StudentID", "102"));
$student->appendChild($xml->createElement("Name", "Priya"));
$student->appendChild($xml->createElement("Age", "21"));
$student->appendChild($xml->createElement("Gender", "Female"));
$student->appendChild($xml->createElement("Program", "BCA"));
$root->appendChild($student);

// Student 3
$student = $xml->createElement("Student");
$student->appendChild($xml->createElement("StudentID", "103"));
$student->appendChild($xml->createElement("Name", "Rahul"));
$student->appendChild($xml->createElement("Age", "22"));
$student->appendChild($xml->createElement("Gender", "Male"));
$student->appendChild($xml->createElement("Program", "BSc"));
$root->appendChild($student);

// Student 4
$student = $xml->createElement("Student");
$student->appendChild($xml->createElement("StudentID", "104"));
$student->appendChild($xml->createElement("Name", "Sneha"));
$student->appendChild($xml->createElement("Age", "20"));
$student->appendChild($xml->createElement("Gender", "Female"));
$student->appendChild($xml->createElement("Program", "BBA"));
$root->appendChild($student);

// Student 5
$student = $xml->createElement("Student");
$student->appendChild($xml->createElement("StudentID", "105"));
$student->appendChild($xml->createElement("Name", "Karan"));
$student->appendChild($xml->createElement("Age", "23"));
$student->appendChild($xml->createElement("Gender", "Male"));
$student->appendChild($xml->createElement("Program", "BCom"));
$root->appendChild($student);

// Save XML file
$xml->save("Studentt.xml");

echo "Studentt.xml file created successfully!";
?>
```
Q2→ 
## PHP Program to Create XML File (Employee Data)

```php
<?php
// Create XML document
$xml = new DOMDocument("1.0", "UTF-8");
$xml->formatOutput = true;

// Root element
$employees = $xml->createElement("Employees");
$xml->appendChild($employees);

// Employee 1
$emp = $xml->createElement("Employee");
$emp->appendChild($xml->createElement("EmployeeID", "1"));
$emp->appendChild($xml->createElement("Name", "Rahul"));
$emp->appendChild($xml->createElement("Position", "Manager"));
$emp->appendChild($xml->createElement("Department", "HR"));
$emp->appendChild($xml->createElement("DateOfJoining", "2022-01-10"));
$employees->appendChild($emp);

// Employee 2
$emp = $xml->createElement("Employee");
$emp->appendChild($xml->createElement("EmployeeID", "2"));
$emp->appendChild($xml->createElement("Name", "Priya"));
$emp->appendChild($xml->createElement("Position", "Developer"));
$emp->appendChild($xml->createElement("Department", "IT"));
$emp->appendChild($xml->createElement("DateOfJoining", "2021-06-15"));
$employees->appendChild($emp);

// Employee 3
$emp = $xml->createElement("Employee");
$emp->appendChild($xml->createElement("EmployeeID", "3"));
$emp->appendChild($xml->createElement("Name", "Amit"));
$emp->appendChild($xml->createElement("Position", "Analyst"));
$emp->appendChild($xml->createElement("Department", "Finance"));
$emp->appendChild($xml->createElement("DateOfJoining", "2020-03-20"));
$employees->appendChild($emp);

// Employee 4
$emp = $xml->createElement("Employee");
$emp->appendChild($xml->createElement("EmployeeID", "4"));
$emp->appendChild($xml->createElement("Name", "Sneha"));
$emp->appendChild($xml->createElement("Position", "Designer"));
$emp->appendChild($xml->createElement("Department", "Marketing"));
$emp->appendChild($xml->createElement("DateOfJoining", "2023-07-05"));
$employees->appendChild($emp);

// Employee 5
$emp = $xml->createElement("Employee");
$emp->appendChild($xml->createElement("EmployeeID", "5"));
$emp->appendChild($xml->createElement("Name", "Karan"));
$emp->appendChild($xml->createElement("Position", "Support"));
$emp->appendChild($xml->createElement("Department", "Customer Care"));
$emp->appendChild($xml->createElement("DateOfJoining", "2019-11-25"));
$employees->appendChild($emp);

// Save XML file
$xml->save("Employees.xml");

echo "Employees.xml file created successfully!";
?>
```
Slip 11 →q1 Login.php —> save file 
## PHP Login System with Session (3 Attempt Limit)

### Step 1: Login Page (login.php)

```php
<?php
session_start();

// Set default attempts
if(!isset($_SESSION['attempt'])){
    $_SESSION['attempt'] = 0;
}

$message = "";

if(isset($_POST['login'])){
    $username = $_POST['username'];
    $password = $_POST['password'];

    // Set Correct Credentials
    $correct_user = "admin";
    $correct_pass = "1234";

    if($username == $correct_user && $password == $correct_pass){
        $_SESSION['login'] = true;
        header("Location: welcome.php");
        exit();
    }else{
        $_SESSION['attempt']++;

        if($_SESSION['attempt'] >= 3){
            $message = "Maximum login attempts reached!";
        }else{
            $message = "Invalid Username or Password";
        }
    }
}
?>

<html>
<head>
<title>Login</title>
</head>

<body>

<h2>Login Form</h2>

<?php echo $message; ?>

<?php if($_SESSION['attempt'] < 3){ ?>
<form method="post">
Username: <input type="text" name="username" required><br><br>
Password: <input type="password" name="password" required><br><br>
<input type="submit" name="login" value="Login">
</form>
<?php } ?>

</body>
</html>
```

---

### Step 2: Welcome Page (welcome.php)

```php
<?php
session_start();

if(!isset($_SESSION['login'])){
    header("Location: login.php");
    exit();
}
?>

<html>
<head>
<title>Welcome</title>
</head>

<body>
<h2>Welcome! Login Successful</h2>
</body>
</html>
```
Q2→ 
Emp1.php 
## PHP Employee Management using Session (3 Pages)

---

### Step 1: Employee Details (emp1.php)

```php
<?php
session_start();

if(isset($_POST['next'])){
    $_SESSION['eno'] = $_POST['eno'];
    $_SESSION['ename'] = $_POST['ename'];
    $_SESSION['address'] = $_POST['address'];
    header("Location: emp2.php");
}
?>

<html>
<body>

<h2>Employee Details</h2>

<form method="post">
Employee No: <input type="text" name="eno" required><br><br>
Employee Name: <input type="text" name="ename" required><br><br>
Address: <textarea name="address" required></textarea><br><br>

<input type="submit" name="next" value="Next">
</form>

</body>
</html>
```

---

### Step 2: Employee Earnings (emp2.php)

```php
<?php
session_start();

if(isset($_POST['next'])){
    $_SESSION['basic'] = $_POST['basic'];
    $_SESSION['da'] = $_POST['da'];
    $_SESSION['hra'] = $_POST['hra'];
    header("Location: emp3.php");
}
?>

<html>
<body>

<h2>Employee Earnings</h2>

<form method="post">
Basic: <input type="number" name="basic" required><br><br>
DA: <input type="number" name="da" required><br><br>
HRA: <input type="number" name="hra" required><br><br>

<input type="submit" name="next" value="Next">
</form>

</body>
</html>
```

---

### Step 3: Display Employee Data (emp3.php)

```php
<?php
session_start();

$eno = $_SESSION['eno'];
$ename = $_SESSION['ename'];
$address = $_SESSION['address'];
$basic = $_SESSION['basic'];
$da = $_SESSION['da'];
$hra = $_SESSION['hra'];

$total = $basic + $da + $hra;
?>

<html>
<body>

<h2>Employee Information</h2>

Employee No: <?php echo $eno; ?><br><br>
Employee Name: <?php echo $ename; ?><br><br>
Address: <?php echo $address; ?><br><br>
Basic: <?php echo $basic; ?><br><br>
DA: <?php echo $da; ?><br><br>
HRA: <?php echo $hra; ?><br><br>

<b>Total Salary: <?php echo $total; ?></b>

</body>
</html>
```
  Slip 12 →q1 
 
Run as localhost/s12q1.html 
 ## PHP Program to Calculate Area and Volume of Cylinder

```php
<html>
<body>

<form method="post" action="s12q1.php">
    Radius: <input type="text" name="r"><br><br>
    Height: <input type="text" name="h"><br><br>
    <input type="submit" value="Calculate">
</form>

</body>
</html>

<?php

function cylinder($r, $h)
{
    $area = 2 * pi() * $r * ($r + $h);
    $volume = pi() * $r * $r * $h;

    echo "Area = " . $area . "<br>";
    echo "Volume = " . $volume;
}

// Check if form is submitted
if ($_SERVER["REQUEST_METHOD"] == "POST") {

    $r = $_POST['r'];
    $h = $_POST['h'];

    cylinder($r, $h);
}

?>
```
Q2→ 
## PHP Program for String Operations

```php
<?php
$message = "";
if ($_SERVER['REQUEST_METHOD']=='POST'){
    
    $string1 = $_POST["string1"];
    $string2 = $_POST["string2"];
    $operation = $_POST["operation"];

    switch($operation){
        case "compare":
            if ($string1==$string2){
                $message = "Both Strings are Equal";
            }else{
                $message = "<p>Strings are Different</p>";
            }
            break;

        case "upper":
            $upp_str1 = strtoupper($string1);
            $upp_str2 = strtoupper($string2);
            $message = "<p>Upper string 1 : $upp_str1 <br> Upper string 2 : $upp_str2</p>";
            break;

        case "lower":
            $low_str1 = strtolower($string1);
            $low_str2 = strtolower($string2);
            $message = "<p>Lower string 1 : $low_str1 <br> Lower string 2 : $low_str2</p>";
            break;
    }
}
?>

<html>
<head>
<title>Operations on strings</title>

<style>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-family: Arial;
}

.box {
    border: 1px solid black;
    padding: 30px;
    text-align: center;
    width: 350px;
    margin: auto;
    border-radius: 10px;
}
</style>

</head>

<body>

<div class="box">
    <h1 style="color:red">Operations on String</h1>

    <form method="post">
        <h3>Enter Details</h3>
        String 1: <input type="text" name="string1" required><br><br>
        String 2: <input type="text" name="string2" required><br><br>

        Operations: <br>
        <input type="radio" name="operation" value="compare" required>a. Compare string <br>
        <input type="radio" name="operation" value="upper"> b. convert to Upper<br>
        <input type="radio" name="operation" value="lower"> c.convert to Lower<br><br>

        <button type="submit">Check</button>
    </form>

    <br>
    <?php echo $message; ?>
</div>

</body>
</html>
```
Slip no 13:- q1 
## PHP Program to Convert Digits into Words

```php
<html>
<head>
    <title>Digit in Words</title>

    <style>
    body{
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        font-family: Arial;
        background: #f9f9f9;
    }

    .box{
        background: white;
        width: 300px;
        padding: 20px;
        border: 1px solid black;
        margin: auto;
        box-shadow: 1px 1px 10px pink;
        text-align: center;
        border-radius: 10px;
    } 

    input {
        padding: 8px;
        margin: 5px;
        width: 80%;
    }
    </style>
</head>

<body>

<div class="box">
<h3>Enter a digit</h3>

<form method="post">
    <input type="text" name="number" placeholder="Enter number" required><br>
    <input type="submit" value="Convert">
</form>

<?php
if($_SERVER['REQUEST_METHOD'] == "POST") {

    $number = $_POST['number'];

    // Check if input is numeric
    if(!ctype_digit($number)){
        echo "<p style='color:red;'>Please enter only digits (0-9)</p>";
    } else {

        $digits = str_split($number);

        $words = array(
            "0" => "Zero",
            "1" => "One",
            "2" => "Two",
            "3" => "Three",
            "4" => "Four",
            "5" => "Five",
            "6" => "Six",
            "7" => "Seven",
            "8" => "Eight",
            "9" => "Nine"
        );

        echo "<strong>Entered Number:</strong> $number <br><br>";
        echo "<strong>Digits in Words:</strong><br>";

        foreach($digits as $digit) {
            echo $words[$digit] . " ";
        }
    }
}
?>

</div>

</body>
</html>
```
## PHP Program to Convert Digits into Words (Using Array)

```php
<html>
<head>
    <title>digit in words</title>
    <style>
    body{
        display: flex;
        margin: auto;
    }
    .box{
        background: white;
        width: 20%;
        padding: 20px;
        border: 1px solid black;
        margin: auto;
        box-shadow: 1px 1px 10px pink;
    } 
    input {
        padding: 8px;
        margin: 5px;
    }
    </style>
</head>
<body>

<div class="box">
<h3>Enter a digits</h3>

<form method="post">
    Enter Number: <input type="text" name="number" required>
    <input type="submit" value="Convert">
</form>

<?php
if(isset($_POST['number'])) {
    $number = $_POST['number'];

    $digits = str_split($number);

    $words = array(
        "0" => "Zero",
        "1" => "One",
        "2" => "Two",
        "3" => "Three",
        "4" => "Four",
        "5" => "Five",
        "6" => "Six",
        "7" => "Seven",
        "8" => "Eight",
        "9" => "Nine"
    );

    echo "<strong>Entered Number:</strong> " . $number . "<br><br>";
    echo "<strong>Digits in Words:</strong><br>";

    foreach($digits as $digit) {
        if(array_key_exists($digit, $words)) {
            echo $words[$digit] . " ";
        }
    }
}
?>

</div>

</body>
</html>
```
 Slip14 q1 
## HTML Form for Product Selection

```html
<html>
<head>
<title>Product Selection</title>
</head>
<body>

<h2 style="text-align:center;">Select Products</h2>

<form method="post" action="bill.php" 
      style="width:300px; margin:auto; border:1px solid black; padding:10px;">

    Books (200):<br>
    <input type="number" name="book_qty" value="0"><br><br>

    Pens (10):<br>
    <input type="number" name="pen_qty" value="0"><br><br>

    Bags (500):<br>
    <input type="number" name="bag_qty" value="0"><br><br>

    <input type="submit" value="Generate Bill">

</form>

</body>
</html>
```

bill.php → file name 
## PHP Program to Calculate Bill

```php
<?php
// Prices
$book_price = 200;
$pen_price = 10;
$bag_price = 500;

// Quantities from form
$book_qty = $_POST['book_qty'];
$pen_qty = $_POST['pen_qty'];
$bag_qty = $_POST['bag_qty'];

// Calculate totals
$book_total = $book_qty * $book_price;
$pen_total = $pen_qty * $pen_price;
$bag_total = $bag_qty * $bag_price;
$grand_total = $book_total + $pen_total + $bag_total;

echo "<h2>Bill Details</h2>";
echo "Books: $book_qty × 200 = $book_total <br><br>";
echo "Pens: $pen_qty × 10 = $pen_total <br><br>";
echo "Bags: $bag_qty × 500 = $bag_total <br><br>";
echo "<h3>Grand Total: $grand_total</h3>";
?>
```
  Q2: OWASP Top 10 Threats for Web Applications
Introduction

The OWASP (Open Web Application Security Project) is an international organization that works to improve the security of software and web applications. It provides a list called the OWASP Top 10, which shows the most common and dangerous security risks found in web applications.

In today’s world, many services like banking, shopping, and social media run on web applications. If these applications are not secure, attackers (hackers) can steal user data, change information, or even take control of the system.

So, OWASP Top 10 helps developers understand these risks and build safer applications.

OWASP Top 10 Threats (Explained in Simple Words)
1. Broken Access Control

This happens when users can access things that they are not allowed to see or use.

👉 Example: A normal user can open an admin page just by changing the URL. This means access control is broken.

2. Cryptographic Failures

This happens when sensitive data like passwords or credit card details are not properly protected.

👉 Example: If a website stores passwords in plain text instead of encryption, anyone can read them if data is leaked.

3. Injection Attacks

In this attack, hackers enter harmful code into input fields like login forms.

👉 Example: In SQL Injection, a hacker enters special code in username/password field and gets access without correct login.

4. Insecure Design

This problem comes when the application is not designed with proper security rules.

👉 Example: A website does not limit login attempts, so attackers can try many passwords until they guess the correct one.

5. Security Misconfiguration

This happens when security settings are not set correctly.

👉 Example: Server shows error messages with full details, which helps attackers understand system structure.

6. Vulnerable and Outdated Components

Using old software, libraries, or plugins that have known security issues.

👉 Example: A website uses an old version of software that hackers already know how to attack.

7. Identification and Authentication Failures

Weak login system or poor password handling.

👉 Example: Allowing very simple passwords like “12345” or not using proper session control.

8. Software and Data Integrity Failures

When the system does not verify if the software or data is safe and unchanged.

👉 Example: Installing updates from unknown sources can allow attackers to insert malware.

9. Security Logging and Monitoring Failures

System does not properly track or record suspicious activities.

👉 Example: If many wrong login attempts happen but no alert is generated, the attack may continue unnoticed.

10. Server-Side Request Forgery (SSRF)

In this attack, the hacker tricks the server into making requests to internal or private systems.

👉 Example: The server is forced to access internal data which should not be available to outside users.
  
 Slip no 15 q1 

# Slip No 15 - Q1

## Q1. Write a short report explaining [15M]

---

### a) The Identified Threat – SQL Injection

The identified threat is SQL Injection, which is a common and dangerous attack on web applications. In this attack, a hacker inserts malicious SQL code into input fields like login forms, search boxes, or contact forms.

This problem occurs when the application does not properly validate or filter user input. Instead of treating the input as normal data, the system executes it as part of a database query. Because of this, attackers can manipulate the query and gain unauthorized access to the database.

SQL Injection can lead to serious problems such as data theft, data modification, or even deletion of important information. Attackers can view sensitive details like usernames, passwords, and personal data.

Example:
' OR '1'='1

This makes the condition always true and allows login without a correct password.

---

### b) How the Threat Was Exploited

The attacker exploited the vulnerability by taking advantage of weak input validation in the login form. The application did not properly check or filter the user input before sending it to the database.

Instead of entering a valid username and password, the attacker entered special SQL code like:

' OR '1'='1

This condition is always true. When the application includes this input in the SQL query, the database returns all records as valid. Because of this, the system does not verify the correct password and allows the attacker to log in successfully.

In this way, the attacker bypassed the authentication process and gained unauthorized access to the system. After logging in, the attacker could access sensitive data, and may also modify or delete important information from the database.

---

### c) Steps Taken to Mitigate the Vulnerability

- Input Validation and Sanitization  
  All user inputs are checked carefully. Only valid characters are allowed, and harmful inputs are removed.

- Use of Prepared Statements (Parameterized Queries)  
  Prepared statements are used instead of directly writing SQL queries. This ensures that user input is treated only as data, not as executable code.

- Use of Strong Password Security  
  Passwords are stored in encrypted (hashed) form, so even if data is accessed, it cannot be easily understood.

- Limiting Database Permissions  
  The database user is given only limited permissions. This reduces the damage even if an attack happens.

- Error Handling  
  Detailed error messages are hidden from users, so attackers cannot get useful information about the database.

- Regular Testing and Updates  
  The application is tested regularly to find and fix security issues.

- Use of Web Application Firewall (WAF)  
  A firewall is used to detect and block malicious requests before they reach the application.

- Use of Stored Procedures  
  Stored procedures are used to execute database queries safely, reducing direct interaction with SQL queries.

- Session Management Security  
  Proper session handling is implemented, such as automatic logout and secure session IDs, to prevent misuse after login.

- Use of Latest Software and Updates  
  Keeping software, frameworks, and databases updated helps fix known vulnerabilities and improves security.
  
Q2→ 
<?php  
// Create XML document 
$xml = new DOMDocument("1.0", "UTF-8"); 
$xml->formatOutput = true; 
 
// Root element 
$root = $xml->createElement("Timetable"); 
$xml->appendChild($root); 
 
// Record 1 
$class = $xml->createElement("Class"); 
$class->appendChild($xml->createElement("Day", "Monday")); 
$class->appendChild($xml->createElement("ClassName", "Mathematics")); 
$class->appendChild($xml->createElement("Instructor", "Mr. Sharma")); 
$class->appendChild($xml->createElement("TimeSlot", "10:00 AM - 11:00 AM")); 
$class->appendChild($xml->createElement("Classroom", "Room 101")); 
$root->appendChild($class); 
 
// Record 2 
$class = $xml->createElement("Class"); 
$class->appendChild($xml->createElement("Day", "Wednesday")); 
$class->appendChild($xml->createElement("ClassName", "Computer Science")); 
$class->appendChild($xml->createElement("Instructor", "Ms. Gupta")); 
$class->appendChild($xml->createElement("TimeSlot", "11:00 AM - 12:00 PM")); 
$class->appendChild($xml->createElement("Classroom", "Lab 2")); 
$root->appendChild($class); 
 
// Record 3 
$class = $xml->createElement("Class"); 
$class->appendChild($xml->createElement("Day", "Friday")); 
$class->appendChild($xml->createElement("ClassName", "Physics")); $class->appendChild($xml->createElement("Instructor", "Dr. Verma")); 
$class->appendChild($xml->createElement("TimeSlot", "1:00 PM - 2:00 PM")); 
$class->appendChild($xml->createElement("Classroom", "Room 202")); 
$root->appendChild($class); 
 
// Save XML file 
$xml->save("Timetable.xml"); 
 
echo "Timetable.xml file created successfully!"; 
?> 
  
Slip no 17 q1 → Create.html file 
<html> 
<head> 
<title>Product Selection</title> 
</head> 
<body> 
 
<h2 style="text-align:center;">Select Products</h2> 
 
<form method="post" action="s14q1bill.php"        style="width:300px; margin:auto; border:1px solid black; padding:10px;"> 
 
    Books (200):<br> 
    <input type="number" name="book_qty" value="0"><br><br> 
 
    Pens (10):<br> 
    <input type="number" name="pen_qty" value="0"><br><br> 
 
    Bags (500):<br> 
    <input type="number" name="bag_qty" value="0"><br><br> 
 
    <input type="submit" value="Generate Bill"> 
 
</form> 
 
</body> </html> bill.php → file name 
<?php 
// Prices 
$book_price = 200; 
$pen_price = 10; 
$bag_price = 500; 
// Quantities from form 
$book_qty = $_POST['book_qty']; 
$pen_qty = $_POST['pen_qty']; 
$bag_qty = $_POST['bag_qty']; 
// Calculate totals 
$book_total = $book_qty * $book_price; 
$pen_total = $pen_qty * $pen_price; 
$bag_total = $bag_qty * $bag_price; 
$grand_total = $book_total + $pen_total + $bag_total; echo "<h2>Bill Details</h2>"; echo "Books: $book_qty × 200 = $book_total <br><br>"; 
 
echo "Pens: $pen_qty × 10 = $pen_total <br><br>"; echo "Bags: $bag_qty × 500 = $bag_total <br><br>"; echo "<h3>Grand Total: $grand_total</h3>"; 
?> 
 
s17 Q2→ 
# PHP XML Creation - Course Registrations

## Code

~~~php
<?php 
// Create XML document
$xml = new DOMDocument("1.0", "UTF-8");
$xml->formatOutput = true;

// Root element
$root = $xml->createElement("CourseRegistrations");
$xml->appendChild($root);

// Record 1
$reg = $xml->createElement("Registration");
$reg->appendChild($xml->createElement("RegistrationID", "1"));
$reg->appendChild($xml->createElement("StudentName", "Amit"));
$reg->appendChild($xml->createElement("CourseName", "Cyber Security"));
$reg->appendChild($xml->createElement("Instructor", "Mr. Sharma"));
$reg->appendChild($xml->createElement("DateOfRegistration", "2026-04-10"));
$root->appendChild($reg);

// Record 2
$reg = $xml->createElement("Registration");
$reg->appendChild($xml->createElement("RegistrationID", "2"));
$reg->appendChild($xml->createElement("StudentName", "Priya"));
$reg->appendChild($xml->createElement("CourseName", "Web Development"));
$reg->appendChild($xml->createElement("Instructor", "Ms. Gupta"));
$reg->appendChild($xml->createElement("DateOfRegistration", "2026-04-11"));
$root->appendChild($reg);

// Record 3
$reg = $xml->createElement("Registration");
$reg->appendChild($xml->createElement("RegistrationID", "3"));
$reg->appendChild($xml->createElement("StudentName", "Rahul"));
$reg->appendChild($xml->createElement("CourseName", "Data Science"));
$reg->appendChild($xml->createElement("Instructor", "Dr. Verma"));
$reg->appendChild($xml->createElement("DateOfRegistration", "2026-04-12"));
$root->appendChild($reg);

// Record 4
$reg = $xml->createElement("Registration");
$reg->appendChild($xml->createElement("RegistrationID", "4"));
$reg->appendChild($xml->createElement("StudentName", "Sneha"));
$reg->appendChild($xml->createElement("CourseName", "Artificial Intelligence"));
$reg->appendChild($xml->createElement("Instructor", "Mr. Khan"));
$reg->appendChild($xml->createElement("DateOfRegistration", "2026-04-13"));
$root->appendChild($reg);

// Record 5
$reg = $xml->createElement("Registration");
$reg->appendChild($xml->createElement("RegistrationID", "5"));
$reg->appendChild($xml->createElement("StudentName", "Karan"));
$reg->appendChild($xml->createElement("CourseName", "Networking"));
$reg->appendChild($xml->createElement("Instructor", "Ms. Patel"));
$reg->appendChild($xml->createElement("DateOfRegistration", "2026-04-14"));
$root->appendChild($reg);

// Save XML file
$xml->save("CourseRegistrations.xml");

echo "CourseRegistrations.xml file created successfully!";
?>
~~~

 
Slip no 21 q1→ 
# Factorial Program (PHP)

## Code

~~~html
<!DOCTYPE html>
<html>
<head>
    <title>Factorial</title>
    <style>
        body {
            font-family: Arial;
            text-align: center;
            background-color: #f2f2f2;
        }
        .box {
            background: white;
            width: 250px;
            margin: auto;
            margin-top: 100px;
            padding: 15px;
            border: 1px solid gray;
        }
           </style>
</head>

<body>

<div class="box">
    <h3>Factorial</h3>

    <form method="post">
        <input type="number" name="num" placeholder="Enter number" required> <br>
        <input type="submit" value="Find">
    </form>

    <?php
    function fact($n)
    {
        $f = 1;
        for($i = 1; $i <= $n; $i++)
        {
            $f = $f * $i;
        }
        return $f;
    }

    if(isset($_POST['num']))
    {
        $num = $_POST['num'];
        echo "<div class='result'>";
        echo "Factorial = " . fact($num);
        echo "</div>";
    }
    ?>
</div>

</body>
</html>
~~~
   
Q2→ 
OWASP ZAP Scanner (Short Note) 
Introduction: 
 The OWASP ZAP (Zed Attack Proxy) is a free and open-source web application security scanner. It is widely used by developers and testers to find security vulnerabilities in web applications. 
ZAP is designed to be easy for beginners but powerful enough for professionals. It helps in identifying common security issues like SQL Injection, Cross-Site Scripting (XSS), Broken Authentication, and other OWASP Top 10 vulnerabilities. 
  
Features of OWASP ZAP: 
1.	Automatic Scanning: ZAP can automatically crawl a website and check for vulnerabilities. 
2.	Intercepting Proxy: It allows you to intercept requests and responses between your browser and the server to analyze or modify them. 
3.	Active and Passive Scanning: 
○ Passive Scan: Monitors traffic without affecting the website. 
○ Active Scan: Actively tries to attack the application to find vulnerabilities. 
4.	Reports: Generates detailed reports showing vulnerabilities, their severity, and possible solutions. 
5.	Add-ons and Plugins: ZAP has many plugins to extend its features and scan more effectively. 
  
How It Works (Simple Understanding): 
●	ZAP acts like a middleman between your browser and the web application. 
●	It observes all the requests your browser sends and the responses from the server. ● Based on this, it identifies potential security weaknesses and reports them. 
  
Example of Using OWASP ZAP: 
Suppose you have a website with a login page. You want to check if it is vulnerable to SQL Injection. 
1.	You run ZAP and browse your login page through it. 
2.	ZAP captures the login request and analyzes the input fields. 
3.	It detects that the username field is vulnerable to SQL Injection. 
4.	ZAP generates a report showing the vulnerability, its risk level, and suggestions to fix it (e.g., using prepared statements). 
Advantages of OWASP ZAP: 
1.	Free and open-source tool. 
2.	Easy to use, even for beginners. 
3.	Detects multiple types of vulnerabilities. 
4.	Generates detailed and easy-to-understand reports. 
5.	Supports automation for continuous security testing. 
  
Disadvantages of OWASP ZAP: 
1.	Active scanning may slow down the website temporarily. 
2.	Some complex vulnerabilities may not be detected automatically. 
3.	Requires basic knowledge to interpret reports correctly. 
4.	May generate false positives that need manual verification. 
  
Applications of OWASP ZAP: 
1.	Security testing of web applications during development. 
2.	Identifying vulnerabilities before deploying a website to production. 
3.	Continuous security monitoring of live websites. 
4.	Training and learning tool for beginners in web security. 
5.	Testing compliance with OWASP Top 10 standards. 
  
Slip no 22  q1-> 
OWASP Top 10 API Security Threats 
Introduction 
OWASP (Open Web Application Security Project) is a globally recognized organization that focuses on improving software security. 
 With the rapid growth of modern applications, APIs (Application Programming Interfaces) have become a crucial part of communication between systems. 
However, insecure APIs can expose sensitive data, allow unauthorized access, and lead to serious security breaches. 
 To address these risks, OWASP has identified the Top 10 API Security Threats, which help developers build secure applications. 
  
🔟 OWASP Top 10 API Security Risks 
  
1. Broken Object Level Authorization (BOLA) 
This occurs when an API does not properly verify whether a user has permission to access a specific object. 
Example: 
 A user modifies an ID in the URL to access another user’s data. 
Impact: 
●	Data leakage 
●	Unauthorized access 
Prevention: 
●	Implement proper authorization checks 
●	Validate user identity for every request 
  
2. Broken Authentication 
Weak authentication mechanisms allow attackers to compromise user accounts. 
Example: 
 Use of weak passwords or absence of multi-factor authentication. 
Impact: 
●	Account takeover 
●	Unauthorized system access 
Prevention: 
●	Enforce strong password policies 
●	Use Multi-Factor Authentication (MFA) 
  
3. Broken Object Property Level Authorization 
APIs expose or allow modification of sensitive object properties without proper control. 
Example: 
 User changes their role from “user” to “admin”. 
Impact: 
●	Privilege escalation 
Prevention: 
●	Restrict access to sensitive fields 
●	Validate input data 
  
4. Unrestricted Resource Consumption 
APIs do not limit the number or size of requests, leading to resource exhaustion. 
Example: 
 Sending unlimited requests to crash the server. 
Impact: 
●	Denial of Service (DoS) 
●	System slowdown 
Prevention: 
●	Apply rate limiting 
●	Restrict request size 
  
5. Broken Function Level Authorization 
Users can access functions they are not authorized to use. 
Example: 
 A normal user accessing admin-level APIs. 
Impact: 
●	Unauthorized operations 
Prevention: 
●	Implement role-based access control (RBAC) 
●	Validate permissions for each function 
  
6. Unrestricted Access to Sensitive Business Flows 
Critical business operations lack proper restrictions. 
Example: 
 Unlimited OTP requests or repeated transactions. 
Impact: 
●	Fraud 
●	Financial loss 
Prevention: 
●	Apply workflow validation 
●	Limit sensitive operations 
  
7. Server-Side Request Forgery (SSRF) 
The API fetches resources from attacker-controlled input without validation. 
Example: 
 Accessing internal server resources through API. 
Impact: 
●	Exposure of internal systems 
Prevention: 
●	Validate and sanitize URLs 
●	Restrict internal network access 
  
8. Security Misconfiguration 
Improper configuration of servers, frameworks, or APIs leads to vulnerabilities. 
Example: 
 Default passwords, exposed debug information. 
Impact: 
●	System compromise 
Prevention: 
●	Secure default settings 
●	Regular updates and patches 
  
9. Improper Inventory Management 
Lack of proper tracking of APIs leads to exposure of outdated or unused APIs. 
Example: 
 Old APIs still active and accessible. 
Impact: 
●	Hidden vulnerabilities 
Prevention: 
●	Maintain proper API documentation 
●	Remove unused APIs 
  
10. Unsafe Consumption of APIs 
Trusting third-party APIs without validation can introduce risks. 
Example: 
 Receiving malicious data from external APIs. 
Impact: 
●	Data corruption 
●	Security breaches 
Prevention: 
●	Validate external inputs 
●	Use secure integration practices 
 
q2→ 
<?php 
$message = ""; 
 
if ($_SERVER["REQUEST_METHOD"] == "POST") { 
 
    $username = $_POST['username']; 
    $password = $_POST['password']; 
 
    // Validation 
    $hasLetter = preg_match('/[a-zA-Z]/', $password); 
    $hasNumber = preg_match('/[0-9]/', $password); 
    $hasSpecial = preg_match('/[!@#$%^&*(),.?":{}|<>]/', $password); 
    $isLongEnough = strlen($password) > 8; 
 
    if ($hasLetter && $hasNumber && $hasSpecial && $isLongEnough) { 
        $message = "<p style='color:green;'>You entered a strong password</p>"; 
    } else { 
        $message = "<p style='color:red;'>Enter complex password</p>"; 
    } 
} 
?> 
 
<!DOCTYPE html> 
<html> 
<head> 
    <title>Password Validation</title> 
</head> 
<body> 
 
<h2>Login</h2> 
 
<form method="POST"> 
    Username: <input type="text" name="username" required><br><br> 
     
    Password: <input type="password" name="password" required><br><br> 
     
    <button type="submit">Submit</button> 
</form> 
 
<!-- Display message --> 
<?php echo $message; ?> 
 
</body> 
</html> 
 

 slip23 
 q1->
 ## Employee Profile Webpage (HTML, CSS, JavaScript)

```html
<!DOCTYPE html>
<html>
<head>
 <title>Employee Profile</title>
 <style>
 body{
 font-family: Arial, sans-serif;
 }
 .container{
 width:80%;
 margin:auto;
 display:flex;
 border:1px solid black;
 }
 .menu{
 width:25%;
 background:#f2f2f2;
 padding:20px;
 }

 .content{
 width:75%;
 padding:20px;
 }
 a{
 display:block;
 margin:10px 0;
 font-weight:bold;
 text-decoration:none;
 color:blue;
 cursor:pointer;
 }
 img{
 width:150px;
 height:150px;
 border:1px solid black;
 }
 table{
 border-collapse:collapse;
 margin-top:20px;
 }
 td{
 padding:8px;

 }
 .hidden{
 display:none;
 }
 </style>
 <script>
 function showHR(){
 document.getElementById("hrdetails").style.display="block";
 }
 </script>
</head>
<body>
<h2 align="center">Employee Profile Page</h2>
<div class="container">
 <!-- Column 1 -->
 <div class="menu">
 <h3>Menu</h3>
 <a href="#">Home</a>
 <a href="#">About Us</a>
 <a onclick="showHR()">Contact HR</a>
 </div>
 <!-- Column 2 -->
 <div class="content">

 <h3>Employee Details</h3>
 <p><b>Employee ID:</b> EMP101</p>
 <p><b>Name:</b> Rahul Sharma</p>
 <p><b>Designation:</b> Software Developer</p>
 <p><b>Department:</b> IT</p>
 <p><b>Email:</b> rahul@gmail.com</p>
 <p><b>Photo:</b></p>
 <img src="employee.jpg" alt="Employee Photo">

 <!-- HR Details -->
 <div id="hrdetails" class="hidden">
 <h3>HR Contact Details</h3>
 <p><b>Department:</b> Human Resource</p>
 <p><b>Email:</b> hr@company.com</p>
 <p><b>Phone:</b> 9876543210</p>
 </div>

 <!-- New Employee Form -->
 <h3>Add New Employee</h3>
 <form>
 <table border="1">
 <tr>
 <td>Name</td>
 <td><input type="text"></td>
 </tr>

 <tr>
 <td>Employee ID</td>
 <td><input type="text"></td>
 </tr>
 <tr>
 <td>Designation</td>
 <td><input type="text"></td>
 </tr>
 <tr>
 <td>Department</td>
 <td><input type="text"></td>
 </tr>
 <tr>
 <td>Email</td>
 <td><input type="email"></td>
 </tr>
 <tr>
 <td>Phone Number</td>
 <td><input type="tel"></td>
 </tr>
 <tr>
 <td colspan="2" align="center">
 <input type="submit" value="Submit">
 <input type="reset" value="Reset">
 </td>
 </tr>
 </table>
 </form>

 </div>
</div>
</body>
</html>
```
q2--->
## Feedback Form (HTML, CSS, JavaScript)

```html
<!DOCTYPE html>
<html>
<head>
<title>Feedback Form</title>

<style>
body{
    font-family: Arial;
    background:#f2f2f2;
}

form{
    width:300px;
    margin:auto;
    padding:15px;
    background:white;
    border:1px solid black;
}

input, textarea, select{
    width:100%;
    padding:5px;
}

#output{
    width:300px;
    margin:auto;
    margin-top:20px;
    padding:10px;
    border:1px solid black;
    background:white;
}
</style>

</head>

<body>

<h2 align="center">Feedback Form</h2>

<form onsubmit="return showFeedback()">

Name:<br>
<input type="text" id="name" required><br><br>

Email:<br>
<input type="email" id="email" required><br><br>

Feedback:<br>
<textarea id="message" required></textarea><br><br>

Rating:<br>
<select id="rating">
<option value="1">1 Star</option>
<option value="2">2 Stars</option>
<option value="3">3 Stars</option>
<option value="4">4 Stars</option>
<option value="5">5 Stars</option>
</select><br><br>

<input type="submit" value="Submit">

</form>

<div id="output" style="display:none;">
<h3>Submitted Feedback</h3>

<p><b>Name:</b> <span id="outName"></span></p>
<p><b>Email:</b> <span id="outEmail"></span></p>
<p><b>Feedback:</b> <span id="outMessage"></span></p>
<p><b>Rating:</b> <span id="outStars"></span></p>

</div>

<script>
function showFeedback() {

var name = document.getElementById("name").value;
var email = document.getElementById("email").value;
var message = document.getElementById("message").value;
var rating = document.getElementById("rating").value;

var stars = "";
for(var i=0; i<rating; i++){
    stars += "*";
}

document.getElementById("outName").innerHTML = name;
document.getElementById("outEmail").innerHTML = email;
document.getElementById("outMessage").innerHTML = message;
document.getElementById("outStars").innerHTML = stars;

document.getElementById("output").style.display = "block";

return false;
}
</script>

</body>
</html>
```
 
