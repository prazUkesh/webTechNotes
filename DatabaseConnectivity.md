```
<?php
/* Attempt MYSQL sever conncetion.Assuming your are running MYSQL server with default setting (user root with no password)*/
$link = mysqli_connect("localhost","root","","demo");
//Check Connection
if($link===false){
    die("EOOR:Could not Connect.".mysqli_connect_error());
} 
//Attempt create database query execution
$sql="CREATE DATABASE demo";
if(mysqli_query($link,$sql)){
    echo"DATABASE created successfully";
}
else{
echo"ERROR: Could not able to execute $sql.".mysqli_error($link);
}
//Close connection
```
### creating table
```
<?php

$link = mysqli_connect("localhost", "root", "","demo");

if($link === false){
    die("ERROR: Could not connect. " . mysqli_connect_error());
}

$sql = "CREATE TABLE persons(
id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
first_name VARCHAR(30) NOT NULL,
last_name VARCHAR(30) NOT NULL,
email VARCHAR(70) NOT NULL UNIQUE
)
";
if(mysqli_query($link, $sql)){
    echo "Table created successfully.";
} else{
    echo "ERROR: Could not execute $sql. " . mysqli_error($link);
}

mysqli_close($link);
```

## data insertion
```
<?php

$link = mysqli_connect("localhost", "root", "","demo");

if($link === false){
    die("ERROR: Could not connect. " . mysqli_connect_error());
}

$sql = "INSERT INTO persons (first_name, last_name, email) VALUE ('esh','pra','esh3cc@gmail.com')";
if(mysqli_query($link, $sql)){
    echo "data inserted successfully.";
} else{
    echo "ERROR: Could not execute $sql. " . mysqli_error($link);
}

mysqli_close($link);
```
