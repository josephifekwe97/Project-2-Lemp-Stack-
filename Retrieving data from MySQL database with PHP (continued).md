



<span style = "color:orange">  i was unable to complete the last part of the project mainly because  i was i had perviouly installed mySql and when i am re-running all this command the are giving me issues i would realy apperciate a seasion to sort this out </span>


`sudo mysql`

![Ngnix Status](/Project-2-Lemp-Stack-/Images/sudoMysql.png))             

[MySql Link  for this error](https://stackoverflow.com/questions/21944936/error-1045-28000-access-denied-for-user-rootlocalhost-using-password-y)

` CREATE DATABASE example_database`
`CREATE USER 'example_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';`


`GRANT ALL ON example_database.* TO 'example_user'@'%';`

`exit`

`mysql -u example_user -p`


![Ngnix Status](Project-2-Lemp-Stack-/Images/user-p.png)

`mysql> SHOW DATABASES;`


`CREATE TABLE example_database.todo_list (
mysql>     item_id INT AUTO_INCREMENT,
mysql>     content VARCHAR(255),
mysql>     PRIMARY KEY(item_id)
mysql> );`


`mysql> INSERT INTO example_database.todo_list (content) VALUES ("My first important item");`

`mysql>  SELECT * FROM example_database.todo_list;`

`mysql> exit`

`<?php
$user = "example_user";
$password = "password";
$database = "example_database";
$table = "todo_list";

try {
  $db = new PDO("mysql:host=localhost;dbname=$database", $user, $password);
  echo "<h2>TODO</h2><ol>";
  foreach($db->query("SELECT content FROM $table") as $row) {
    echo "<li>" . $row['content'] . "</li>";
  }
  echo "</ol>";
} catch (PDOException $e) {
    print "Error!: " . $e->getMessage() . "<br/>";
    die();
}`




![Ngnix Status](/Project-2-Lemp-Stack-/Images/Create%20db%20and%20user.png)
