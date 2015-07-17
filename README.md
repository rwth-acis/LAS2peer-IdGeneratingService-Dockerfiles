# LAS2peer-IdGeneratingService-Dockerfiles
Contains all runtime dockerfiles for [IdGeneratingService](https://github.com/rwth-acis/LAS2peer-IdGeneratingService).

# How to Run 
1. Create volumes for the mysql server `docker run -d --name mysql-data learninglayers/mysql-data` 
2. Run dockerfile for the mysql server `docker run -d -p 3306:3306 -e "MYSQL_ROOT_PASSWORD=password" --volumes-from mysql-data --name mysql learninglayers/mysql`. Replace password with your root password.
3. Create the database and the user. 
	```
	ID_PASS=`docker run --link mysql:mysql learninglayers/mysql-create -ppassword --new-database idgeneration --new-user $idUser | grep "mysql" | awk '{split($0,a," "); print a[3]}' | cut -c3-`
	```
	It will return the user password.
4. Run idGenerating-data
	```
	Run command here
	```
5. Run idGenerating
	```
	Run command here
	```