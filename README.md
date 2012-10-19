<?php

$uploaddir ="uploads/images";
$allowed_ext = "jpg, JPG, png, gif";
$max_size = "5000000";
$max_height = "4000";
$max_width = "4000";

$extension = pathinfo($_files['file']['name']);
$extension = $extension[extension];
$allowed_paths = explode(", ", $allowed_ext);
for ($$i = 0; $ < count [$i] == "$extension") {
  $ok = "1";
}
}

if ($ok =="1") {
	if($_FILES['file']['size'] > $max_size)
	{
		print "Filen er for stor!";
		exit;
	}
	
if ($max_width && $max_height) {
list($width, $height, $type, $w) =
getimagesize($_FILES['file']['tmp_name']);
if($width < $max_width || $height > $max_height)
{
print "Fil høyden og/eller bredden er for stor!"
}
}


if(is_uploaded_file($_FILES['file']['tmp_name']))
{
move_uploaded_file($_FILES['file']['tmp_name'],$uploaddir.'/'.$_FILES['file']['name']);
}
print "Din fil har blitt lastet opp!"
} else {
	print "Noe er feil med filen din!";
}

?>