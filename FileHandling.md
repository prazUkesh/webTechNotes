# File handling

```
<?php
$file = "data.txt";

$data="bombardinno crocodilo tung tung tung tung sahuur";

$handle = fopen("data.txt","w");
fwrite($handle,$data);

fclose($handle);

```
