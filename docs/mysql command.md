# mysql command

* 查看指定的存储过程内容：
`select body from mysql.proc where name='procedurename';`

* 查看所有的存储过程：
`show procedure status;`

* 导出MySQL的存储过程
`mysqldump -uroot -p -hlocalhost -P3306 -n -d -t -R DBName > procedurename.sql`

* 导入MySQL的存储过程
`mysql -hhostname -uusername - ppassword databasename < backupfile.sql`