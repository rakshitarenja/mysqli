Comment: this program is for fetching the entire row, but any specific single row at a time. You just have to write the email id(as i have code), you can also choose anyother field if you want.

<html>
<body>
<form action="" method="get">
Enter ID <input type="text" name="id" /><br /><br />
<input type="submit" name="submit" value="submit" />
</form>
</body>
</html>

<?php
if(isset($_GET['submit']))
	{
	$id=$_GET['id'];
	include('connect.php');
	$que=mysqli_query($con,"select * from info where id='$id'");
		if(mysqli_num_rows($que)>0)
		{
//we can code any of the four fetching codes to get the result.
			while($r=mysqli_fetch_object($que))
				{
				echo("$r->name")." email_id=";
				echo("$r->id")."<br>";
				}
		}
		else
		{
			echo("record not found");
		}
	}
?>
