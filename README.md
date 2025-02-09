#crrency converter
## Introduction
This Spring Boot application provides real-time currency conversion functionality by integrating with a public API.

## Prerequisites
- JDK 8 or above
- Maven 3.6+ (for building the project)
- Git (for cloning the repository)

## Installation

1. Clone the repository:
2. Build the application 
   (mvn clean install)
3. Run the application(i was using eclipse so right click the main method file and run as springboot application)
   mvn spring-boot:run
4.The application will run on http://localhost:8080.
## API Endpoints
(use postman )
1.GET /api/rates?base=USD
Fetches the exchange rates for the given base currency (default: USD).
use postman or run
"curl -X GET "http://localhost:8080/api/rates?base=USD"
2.POST /api/convert
Converts an amount from one currency to another using the fetched exchange rates.
Request Body:
{
  "from": "USD",
  "to": "EUR",
  "amount": 100
}
on postman or run 
"curl -X POST "http://localhost:8080/api/convert" -H "Content-Type: application/json" -d '{"from": "USD", "to": "EUR", "amount": 100}'"

## Error Handling
If the external API is unavailable, the system will return a 503 status code with an error message.
If invalid currency codes are provided, the system will return a 400 status code with a relevant error message.
## Unittest
Make sure to run the tests to verify that your service layer works correctly, especially for currency conversion logic and error handling.
for testing "mvn test"
right click and run as junit test
This setup will make it easy to run and test your currency converter application.
