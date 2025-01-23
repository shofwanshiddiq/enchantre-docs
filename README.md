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

* Initialize server connection   <a href="myconnAll.php" target="_blank">myconnAll.php</a>


Consume from database
```php
include "myconnAll.php";
$sql = "SELECT 00_ID FROM WD01 WHERE 00_ID = '$id' AND 01_Active = '1'";
$hasil = mysqli_query($conn, $sql);
```

* Posting to server-side <a href="SubmitRSVP.php" target="_blank">SubmitRSVP.php</a>

Initialize POST from page
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







