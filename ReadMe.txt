Vehicle Traffic Violation Notification System

PLEASE READ THROUGH THIS FILE COMPLETELY BEFORE STARTING THE APPLICATION

Step 1: Unzip the .zip file to local folder
Step 2: Create the database schema in my sql as below with user as "root" and password as "admin"
		CREATE DATABASE `vehicle_violation`
		CREATE DATABASE `vehicle_violation_notification` 
Step 3: Import all three projects into eclipse or any development tool as Existing Maven Project
Step 4: Run all three project as Java Application in below order
		VehicleTrafficViolationDiscoveryServer
		VehicleTrafficViolationNotificationService
		VehicleTrafficViolationService
Once the application is started, all the tables get created and pre-data (vehicle data) will be loaded
Step 5: APPLICATION is ready
Step 6: Use the url http://localhost:8761/ to verify the spring boot microservice application
Step 7: Open Postman and run a below requests to get the mail as a POST request
		Url : http://localhost:8082/sendAllVehicleViolations
		Post Request raw Body : {
								  "vehicleList" : ["IN8","IN1"],
								  "signalPolice" : {
												   "name":"Tom",
												   "signalAddrs":"RR Nagar -1",
												   "emailId":"vehicleviolationnotify1@outlook.com"
												   }
								}
		Content-Type: application/json
Step 8: Verify the outlook mails
		Sender Details  mail/password : vehicleviolationnotify@outlook.com/Welcome123$
		Receiver Details mail/password: vehicleviolationnotify1@outlook.com/Welcome123$
Step 9: Successful

Assumptions:
This service "http://localhost:8082/sendAllVehicleViolations" will be triggered by the scanner with all the listed vehciles present in the signal