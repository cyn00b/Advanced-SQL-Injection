```php
<?php include_once("db.php");?>
<?php include('session.php')?>

<?php include('db.php');
$query = "SELECT firstname FROM users WHERE email='$login_session'";
$result = mysqli_query($conn, $query) or die(mysql_error());
while($row=mysqli_fetch_array($result))
{
	$fname = $row['firstname'];
}
mysqli_close($conn);
?>


<html>
<head>
<script>
function validateForm()
{
	var x = document.forms["form1"]["empname"].value;
		if(x==null||x=="")
		{
			alert("Enter a Keyword..!");
			return false;
		}
		else{}
}</script>
<div class="left"><h1><font color="green">Employee Management System</font></h1></div>
<div class="right">Welcome <b> <?php echo ucfirst($fname);?></b></div>
</div>
<style>
body {
    
    text-align: center;
}
.left{display:inline-block;}
.right{display:inline-block; float:right}
</style>
</style>
<style>
.main ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #333;
}

.main li {
    float: left;
	border-right:1px solid #bbb;
}
.main li:last-child {border-right:none;}
.main li a {
    display: block;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
}

.main li a:hover:not(.active) {
    background-color: #111;
}

.active {
    background-color: #4CAF50;
	h1 {
    border-style: dashed;
    border-width: 3px;
    border-left-width: 10px;
    border-right-width: 10px;
    border-color: red;
}
}
</style>
</head>

<body>
<div class="main">
<ul>
  <li><a  href="employeesite.php">Home</a></li>
  <li><a class="active" href="searchemp.php">Search</a></li>
 
  <ul style="float:right;list-style-type:none;">
    <body>
	<ul>
        <li><a href="profile.php">My Profile</a></li>
       
        <li><a href="settings.php">Account Settings</a></li>
		 
        <li><a href="comment.php">Feedback</a></li>
        <li><a href="logout.php">Logout</a></li>
      </ul>
    

   
  </ul>
</ul></div>
<title>Employee Management System</title></head><center>

					<center>
			<marquee direction="left">
                                            
                       <b><a href=""><font style="color:#8B008B; text-transform:uppercase;">***Welcome To Employee Management System..! </font></a> </b>
				 &nbsp&nbsp<b><a href=""><font style="color:#8B008B; text-transform:uppercase;">Employee Login Portal..! </font></a> 
				    &nbsp&nbsp<a href=""><font style="color:#8B008B; text-transform:uppercase;">This is the place where Employee Met their Requirement..!*** </font></a> </b>
					 </marquee>
                
 <head><br />
 <style>
.sub body {
    margin: 0;
}

.sub ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    width: 15%;
    background-color: #f1f1f1;
    position: fixed;
    height: 75%;
    overflow: auto;
}

.sub li a {
    display: block;
    color: #000;
    padding: 8px 0 8px 16px;
    text-decoration: none;
}

.sub li a.active {
    background-color:#f1f1f1 ;
    color: #000;
}

.sub li a:hover:not(.active) {
    background-color: #4CAF50;
    color: white;
}
</style>
</head>
<body>
<div class="sub"><div style="margin-left:0%;padding:1px 1px;height:20px;">
<ul>
 
  <li><a href="ijp.php">IJP</a></li>
  <li><a href="leave.php"> Leave Request</a></li>
  <li><a href="leavestatus.php"> Leave Status</a></li>
  <li><a href="attendance.php">Attendance</a></li>
  <li><a href="attendance1.php">Attendance Status</a></li>
  <li><a href="contact.php">Contact</a></li>
  <li><a href="Buddychat.php">Chat</a></li>
</ul></div>


 </head>
 <title>Search Database</title></head>
<form name="form1" method="post" action="" onsubmit="return validateForm();">
<table width="35%" border="0" cellpadding="2px">
<tr>
<td align="top">
<font color="green"><img src="employee_search.gif" style="width:150px;height:150px"></font><font color="#"><b></td>
<td align="center">Enter Keyword : <input type="text" placeholder="Enter Employee Name" style="text-align:center" name="empname" id="empname"><br/>&nbsp&nbsp<br/>
<input type="submit" name="submit" value="Search" style="width:80px;height:25px;"></td></tr></table></form>
<?php 
include('db.php');
// Database Connection String
$conn=mysqli_connect("localhost", "root", "");
          $db  =mysqli_select_db($conn, "testapp");
if (!$conn)
  {
  die('Could not connect: ' . mysqli_error($conn));
  }

mysqli_select_db($conn, "testapp");



if (!empty($_REQUEST['empname'])) {

$empname =$_REQUEST['empname'];     

$sql = "SELECT * FROM users WHERE sno LIKE '%".$empname."%' OR  firstname LIKE '%".$empname."%' OR lastname LIKE '%".$empname."%' OR email LIKE '%".$empname."%' "; 

$r_query = mysqli_query($conn, $sql) or die(mysqli_error($conn)); 

while($row = mysqli_fetch_array($r_query)){  
echo'<center><h1><font color="green"></h1><br></br></font><table width="350" border="0" cellpadding="3" cellspacing="2">';
echo '<tr><td align="right"><b> <font color="green">Empcode: ';echo'<td align="center" ><font color="black">' . $row['sno'];echo '</td></tr>';  
echo '<tr><td align="right" ><b><font color="green">FirstName: ';echo'<td align="center">'; echo'<font color="black">'. $row['firstname']; echo '</td></tr>';   
echo '<tr><td align="right"><b><font color="green"> LastName : ';echo'<td align="center">';echo'<font color="black">'.  $row['lastname'];echo '</td></tr>';  
echo '<tr><td align="right"><b> <font color="green">Email-ID : ';echo'<td align="center">';echo'<font color="black">'.  $row['email']; echo '</td></tr>'; 
echo '<tr><td align="right"><b> <font color="green">Contact : ';echo'<td align="center">';echo'<font color="black">'.  $row['Contact'];echo '</td></tr>'; 
echo '<tr><td align="right"><b><font color="green"> DateofBirth : ';echo'<td align="center">';echo'<font color="black">'.  $row['DateofBirth'];echo '</td></tr>'; 
echo '<tr><td align="right"><b> <font color="green">Address : ';echo'<td align="center">';echo'<font color="black">'.  $row['Address'];echo '</td></tr>'; 
echo '</br></td></tr></table>';

}}

?></form>
</html>

 
</html>
```