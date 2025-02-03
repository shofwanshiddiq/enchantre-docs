# Enchantre Digital Invitations
![Post1](https://github.com/user-attachments/assets/c5da1d16-64ab-410f-b4f4-133e68c67c73)

Digital invitation for wedding features D-day countdown, reservation system, brides' wishes, background music, and a customer dashboard to view reservation information and wishes message, and an customable design for a more extensive pricing package.

<a href="https://www.enchantre.com" target="_blank">Visit Website</a>


Enchantre's consist of 5 different mesmerizing themes with different design approach. 

<a href="https://enchantre.com/FairyTale_Demo.php?id=bulanbumi&guest=tamu_undangan" target="_blank">Fairytale Fortress</a></br>
<a href="https://enchantre.com/SimpleMono_Demo.php?id=bulanbumi&guest=tamu_undangan" target="_blank">Classic Charcoal</a></br>
<a href="https://enchantre.com/Forest_Demo.php?id=bulanbumi&guest=tamu_undangan" target="_blank">Evergreen Enchantment</a></br>
<a href="https://enchantre.com/SecretGarden_Demo.php?id=bulanbumi&guest=tamu_undangan" target="_blank">Serenity Sanctuary</a></br>
<a href="https://enchantre.com/RedFairyTale_Demo.php?id=bulanbumi&guest=tamu_undangan" target="_blank">Fairytale Fortress II</a></br>


# Technologies

Uses HTML5 and CSS3 for the front-end website to develop an engaging and dynamic digital invitation design that is responsive for both mobile and webview. Utilize PHP and cPanel for backend communication with MySQL databases managed by phpMyAdmin.

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)  ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)  ![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white)  ![cPanel](https://img.shields.io/badge/cPanel-%23FF6C2C.svg?style=for-the-badge&logo=cpanel&logoColor=white)  ![MySQL](https://img.shields.io/badge/mysql-%234479A1.svg?style=for-the-badge&logo=mysql&logoColor=white)  ![phpMyAdmin](https://img.shields.io/badge/phpMyAdmin-%23669933.svg?style=for-the-badge&logo=phpmyadmin&logoColor=white)

# Database 
Consist table for
* Client's Master Data 
* Guest's Master Data  
* Client's Invitation Data
* Guest's Wishes Master Data
* Client's User Data for Dashboard Login

### Setup Databases

Database setup for table and data samples. 
<a href="enchantr_ENCH01.sql" target="_blank">See here</a></br>

# Architecture

Utilize PHP in client's side to handle data request to cPanel API

* Initialize server connection
```php
<?php
// Enable error reporting
error_reporting(E_ALL);
ini_set('display_errors', 1);

$servername = "localhost";
$database = "database";
$username = "usernamee";
$password = "password";
$conn = mysqli_connect($servername, $username, $password, $database);
if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
  }
?>
```


* Consume from database
```php
include "myconnAll.php";
$sql = "SELECT 00_ID FROM WD01 WHERE 00_ID = '$id' AND 01_Active = '1'";
$hasil = mysqli_query($conn, $sql);
```

* Posting to server-side 
```php
<?php
session_start();
include('myconnAll.php'); // Ensure this includes your DB connection details

if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // Retrieve form data and session variables
    $id = isset($_SESSION['id']) ? $_SESSION['id'] : ''; // to 00_ID and 03_CreateBy
    // Other data from form  

    // Establish database connection
    $conn = new mysqli($servername, $username, $password, $database);

    // Check connection
    if ($conn->connect_error) {
        die("Connection failed: " . $conn->connect_error);
    }

    // Prepare SQL query to get the next sequence number
    $sql = "QUERY FOR GET MAX SEQ";
    $result = $conn->query($sql);

    // Check if query was successful
    if ($result && $result->num_rows > 0) {
        $row = $result->fetch_assoc();
        $nextSeq = $row['next_seq'];

        // Prepare SQL query to insert data into WD04
        $insertSql = "INSERT INTO MYSQL TABLE";

        // Execute insert query
        if ($conn->query($insertSql) === TRUE) {
            echo "Reservation Submitted Sucess";
        } else {
            echo "Failed to Submit on Insert PHP";
        }
    } else {
        echo "Failed to Submit on Submit";
    }

    // Close connection
    $conn->close();
} else {
    echo "Invalid request method";
}
?>
```

* Initialize POST from page
```php
var formData = new FormData(this);
var xhr = new XMLHttpRequest();
xhr.open('POST', 'SubmitRSVP.php', true);
xhr.onload = function () {
    if (xhr.status === 200) {
        // Success
    } else {
        // Error
    }
};
xhr.send(formData);
```

# Galleries
Enchantre digital invitation support both mobile, desktop and other screen resolution with responsive view
### Mobile View
<img src="https://github.com/user-attachments/assets/d3dd84b6-7ee3-483e-b27b-3e3e33f12a06" alt="Capture9" width="250" style="border-radius: 20px;">
<img src="https://github.com/user-attachments/assets/3ba11aad-6b1a-4089-853d-95854c8939fa" alt="Capture9" width="250" style="border-radius: 20px;">
<img src="https://github.com/user-attachments/assets/f7ba4e9c-39e8-450a-820a-148194b1097d" alt="Capture9" width="250" style="border-radius: 20px;">
<img src="https://github.com/user-attachments/assets/c1455eda-5e94-4f71-8240-ee6fd30b9362" alt="Capture9" width="250" style="border-radius: 20px;">
<img src="https://github.com/user-attachments/assets/b6f18a54-a1b9-4966-985a-777d31c22ddf" alt="Capture9" width="250" style="border-radius: 20px;">

### Desktop View
<img src="https://github.com/user-attachments/assets/b5f72de1-c575-4ca1-b702-18f9f32a9d20" alt="Capture9" width="500" style="border-radius: 20px;">
<img src="https://github.com/user-attachments/assets/6a6a76e5-8a5c-44ba-abd6-0650d8d40a3e" alt="Capture9" width="500" style="border-radius: 20px;">
<img src="https://github.com/user-attachments/assets/060ec658-e366-434c-9e09-4248d44c5f4a" alt="Capture9" width="500" style="border-radius: 20px;">
<img src="https://github.com/user-attachments/assets/cfec69a3-18cf-4cb0-82e6-001b4228159f" alt="Capture9" width="500" style="border-radius: 20px;">
<img src="https://github.com/user-attachments/assets/cfce44c9-9616-4119-b455-f3e043a822f4" alt="Capture9" width="500" style="border-radius: 20px;">



