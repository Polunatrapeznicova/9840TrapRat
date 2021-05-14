<?php
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "master-klass";
$conn = mysqli_connect($servername, $username, $password,
$dbname);
mysql_select_db('master-klass');
mysql_query('SET NAMES utf8') or die ("Не удалось установить
кодировку");
if (!$conn) {
 die("Подключение не выполнено: " . mysqli_connect_error() );}

$sql = "INSERT INTO register_data (name, familiya, factAddress, parolNotify, pol, dateBirth, phoneNotify, podpiska)
VALUES ('".$_POST['name']."','".$_POST['sname']."','".$_POST['email']."','".$_POST['password']."','".$_POST['sex']."','".$_POST['date']."','".$_POST['phone']."','".$_POST['checkbox']."')";

{
if (mysqli_query($conn, $sql)) {
echo "<h2>Вы ввели:</h2>";
echo $_POST['name'];
echo "<br>";
echo $_POST['sname'];
echo "<br>";
echo $_POST['email'];
echo "<br>";
echo $_POST['password'];
echo "<br>";
echo $_POST['sex'];
echo "<br>";
echo $_POST['date'];
echo "<br>";
echo $_POST['phone'];
echo "<br>";
echo $_POST['checkbox'];
echo "<br>";
echo "<a href='master.html'> На главную </a>"; 
}
else {
 echo "Ошибка добавления записи: " . $sql . "<br>" .
mysqli_error($conn);
}
}
mysqli_close($conn);
?>
