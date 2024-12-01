This project is a Go-based API that provides the current time in Toronto and logs each request to a MySQL database. The application is containerized using Docker Compose.

Main Features
API Endpoint:

/current-time returns the current time in Toronto in JSON format.
Logs the timestamp of each request to the time_log table in a MySQL database.
MySQL Integration:

MySQL database is used to store the timestamps in the time_log table.
Time Zone Handling:

The API provides time adjusted to Toronto's timezone using Go's time package.
Error Handling:

The application includes error handling for both database operations and time zone conversions.
How to Run
Prerequisites
Ensure that you have Docker and Docker Compose installed on your machine.

Steps to Run
Clone the Repository:

bash
Copy code
git clone <repository-url>
cd project
Build and Start the Containers: Use Docker Compose to build and run the application:

bash
Copy code
docker-compose up --build
This will start both the Go API server and the MySQL container.

Access the API: Once the containers are running, you can access the API at:

bash
Copy code
http://localhost:8080/current-time
Verify MySQL Logs: To verify that requests are being logged in the MySQL database, run the following command to access the MySQL container:

bash
Copy code
docker exec -it mysql_db mysql -uroot -prootpassword time_api
Then, run the query to check the time_log table:

sql
Copy code
SELECT * FROM time_log;