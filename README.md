### Spring Boot API Placeholder Application

This is a simple Spring Boot web application that serves as a placeholder for sending and receiving JSON data while providing functionality to adjust and view specific server configurations such as delay, rate limit, and error rate.

#### Features

**Send JSON:**<br>
Accepts JSON input via a form and displays the response along with server statistics and configurations.
**Configuration Settings:**<br>
  • Allows users to modify server behavior by adjusting:<br>
  • Response delay (in milliseconds)<br>
  •	Rate limit for requests<br>
  •	Error rate (percentage of responses returning a simulated error)

#### Application Endpoints

**1. Homepage (GET /)**

The main page displays:
	•	Current server configurations (delay, rate limit, error rate)<br>
	•	Success rate statistics<br>
	•	Forms for updating settings and sending JSON data.<br>

**2. Update Settings (POST /settings)**

Updates the server configuration. Accepts form data:<br>
	•	delay (long): Response delay in milliseconds.<br>
	•	rateLimit (int): Maximum number of requests before throttling.<br>
	•	errorRate (int): Percentage of requests that will return a simulated error.<br>

**3. Send JSON (POST /api/json)**

Accepts a JSON payload and responds with:
	•	The original JSON input
	•	Server statistics
	•	Any errors, if applicable (based on configuration).

#### How to Run

**1. Clone the Repository**
```
git clone https://github.com/InitGvdSelf/TheNewStubService
cd TheNewStubService
```
**2. Build the Project**
```
mvn clean install
```
**3. Run the Application**
Start the Spring Boot application:
```
mvn spring-boot:run
```

#### Monitoring and Metrics with Micrometer

This application includes monitoring capabilities using Micrometer and Spring Boot Actuator. It exposes both standard JVM and system metrics as well as custom application-specific metrics.

**Access:**
```
http://localhost:8080/actuator/metrics
http://localhost:8080/actuator/prometheus
```



