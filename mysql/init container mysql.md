docker run -d --name mysql -h mysql -p 3306:3306 -v -e MYSQL_ROOT_PASSWORD="matkhau" mysql 


- ket noi voi mysql tren database voi mysql workbench tren windows

#vao mysql
-mysql -uroot -pmatkhau

CREATE USER 'testuser'@'%' IDENTIFIED BY 'testpass';

#Tạo db có tên db_testdb
create database db_testdb;

#Cấp quyền cho user testuser trên db - db_testdb
GRANT ALL PRIVILEGES ON db_testdb.* TO 'testuser'@'%';
flush privileges;

show database; 



- mo mysql workbench nhap ip voi user and passwork: roi nhan connect