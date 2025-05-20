```
<?php
$link=mysqli_connet("username","root","");

if($link===false){
	die("ERROR: COlud not connect.", myaqli_connect error());
}

$sql = "CREATE DATABASE demo";
if($mysqli_query($link,$sql)){
	echo "Database created successfully";
}else{
echo "ERROR: Could not be able to execute $sql" .mysql_query error($link);
}
?>

```
