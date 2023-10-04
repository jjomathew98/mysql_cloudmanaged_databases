# mysql_cloudmanaged_databases

## MySQL setup documentation for both Azure and GCP

1. First of all, we created the Azure and GCP account with Stony Brook student account
2. From both Azure and GCP settings, we build our own connections which have the hostname, username and password.
3. Also, we use the following requirements while creating each connection:

#### Azure:
Azure Database for MySQL
Deployment option: Flexible,
Tier: Burstable
Compute: B1S [$6.21 p/month] or B1MS [$12.41 p/month]

#### GCP
DB-standard-1 (vCPU 1, RAM 3.75GB)
10gb storage
No backups [$9.37 month]

5. We then make sure that the instance is properly configured to allow inbound traffic from the World Wide Web. for example: (0.0.0.0/0)
6. Then we installed the mySQL workbench application on the local laptop
7. Followingly, we filled out the information that we already had while setting up the Azure and GCP connections, then clicked on test connection
8. Now, we have connected the GCP and Azure mySQL database connection to MySQL workbench


## GCP and Azure MySQL connections are created

9. Now we go to each connection that we created and input the codes below
   
### SHOW DATABASES;
### CREATE DATABASE database_name;
### USE database_name;

-- Create the 'users' table

### CREATE TABLE users (
###     user_id INT PRIMARY KEY,
###     username VARCHAR(255),
###     email VARCHAR(255)
### );

-- Create the 'posts' table with a foreign key reference to 'users' table
CREATE TABLE posts (
    post_id INT PRIMARY KEY,
    user_id INT,
    content TEXT,
    FOREIGN KEY (user_id) REFERENCES users(user_id)
);

### 10. Then codes we should work well and now we are able to access the ERD visualization
### 11. Now, we go to the top taskbar and select the database and hit reverse engineer to access the ERD generated with MySQL Workbench and follow the instructions, select NEXT options
### 12. Then we will be able to see the ERD generated with MySQL Workbench
