# docker-compose-database
web:
  image: tomcat:7.0
  container_name: tomcat-container
  ports:
   - "80:8080"
  hostname: docker-tomcat
  volumes:
   - /home/webapps:/usr/local/tomcat/webapps
  links:
   - db:container-mysql
db:
  image: mysql
  container_name: mysql-container
  environment:
   MYSQL_ROOT_PASSWORD: Mysqlpassword1
   MYSQL_DATABASE: tracker
  volumes:
   - /home/mysqlDB:/var/lib/mysql
