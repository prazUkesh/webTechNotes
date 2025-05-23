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
## multi data insertion
```
<?php

$link = mysqli_connect("localhost", "root", "","demo");

if($link === false){
    die("ERROR: Could not connect. " . mysqli_connect_error());
}

$sql = "INSERT INTO persons (first_name, last_name, email) 
VALUES
 ('ee','ee','ajsdh@gmail.com'),
 ('sagam','peee','eggg3cc@gmail.com'),
 ('eslkrih','sip','ekresh3cc@gmail.com')";
if(mysqli_query($link, $sql)){
    echo "data inserted successfully.";
} else{
    echo "ERROR: Could not execute $sql. " . mysqli_error($link);
}

mysqli_close($link);
```


## displaying
```


<?php
// Attempt MySQL server connection.
$link = mysqli_connect("localhost", "root", "", "demo");

// Check connection
if ($link === false) {
    die("ERROR: Could not connect. " . mysqli_connect_error());
}

// Corrected SQL query (SELECT needs column names)
$sql = "SELECT id, first_name, last_name, email FROM persons";

if ($result = mysqli_query($link, $sql)) {
    if (mysqli_num_rows($result) > 0) {
        echo "<table border='1'>";
        echo "<tr>";
        echo "<th>id</th>";
        echo "<th>first_name</th>";
        echo "<th>last_name</th>";
        echo "<th>email</th>";
        echo "</tr>";

        while ($row = mysqli_fetch_assoc($result)) {
            echo "<tr>";
            echo "<td>" . $row['id'] . "</td>";
            echo "<td>" . $row['first_name'] . "</td>";
            echo "<td>" . $row['last_name'] . "</td>";
            echo "<td>" . $row['email'] . "</td>";
            echo "</tr>";
        }
        echo "</table>";
    } else {
        echo "No records found.";
    }

    // Free resudglt set
    mysqli_free_result($result);
} else {
    echo "ERROR: Coeuld not execute $sql. " . mysqli_error($link);
}

// Close connection
mysqli_close($link);
?>  
```

## updating
```
<?php

$link = mysqli_connect("localhost","root","","demo");

if($link===false){
    die("EOOR:Could not Connect.".mysqli_connect_error());
} 

$sql="UPDATE persons SET email='peeee@gmail.com' WHERE id=1";
if(mysqli_query($link,$sql)){
    echo"records updated successfully";
}
else{
echo"ERROR: Could not able to execute $sql.".mysqli_error($link);
}
//Close connection
```
## delete
```
<?php

$link = mysqli_connect("localhost","root","","demo");

if($link===false){
    die("EOOR:Could not Connect.".mysqli_connect_error());
} 

$sql="DELETE FROM persons WHERE id=2";
if(mysqli_query($link,$sql)){
    echo"data deleted successfully";
}
else{
echo"ERROR: Could not able to execute $sql.".mysqli_error($link);
}
//Close connection
```

### delete table
```
<?php

$link = mysqli_connect("localhost","root","","demo");

if($link===false){
    die("EOOR:Could not Connect.".mysqli_connect_error());
} 

$sql="DROPTABLE persons WHERE id=2";
if(mysqli_query($link,$sql)){
    echo"table deleted successfully";
}
else{
echo"ERROR: Could not able to execute $sql.".mysqli_error($link);
}
//Close connection
```
## creating cookies
 run file -> open file in browser -> inspect -> applications -> cookies -> https:localhoset/dir/filename
 
```
<?php

setcookie('username','eshii',time()+30*24*60*60);
echo 'Cookie haas been set';

```
```

## deleting cookies
```

```
