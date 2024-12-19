# Movie Review Application Backend

This is the backend service for the Movie Review Application, built using Java and Spring Boot with MongoDB as the database.

## Technologies Used
- **Java**: Core programming language.
- **Spring Boot**: Framework for building RESTful APIs.
- **MongoDB**: NoSQL database for storing movie and review data.

## Features
- **Movie Management**: CRUD operations for movies.
- **Review Management**: Add, update, and retrieve reviews for movies.
- **RESTful Endpoints**: Well-structured API endpoints for seamless integration.
- **CORS Enabled**: Allows frontend communication.

## Prerequisites
- Java 17 or later
- MongoDB installed locally or hosted
- Postman for API testing (optional but recommended)

## Running the Application

1. Clone the repository:
   - git clone https://github.com/yourusername/movie-review-backend.git
   - cd movie-review-backend
2. Update application.properties:
   - spring.data.mongodb.uri=mongodb://localhost:27017/moviedb
   - server.port=8080
3. Start the backend:
   - ./mvnw spring-boot:run

# API Endpoints
## Base URL
 
* **Local:** `http://localhost:8080` 

## Endpoints

**1. Get All Movies**

* **Endpoint:** `/api/v1/movies`
* **Method:** `GET`
* **Description:** Fetches a list of all movies from the database.

**2. Get Movie by ID**

* **Endpoint:** `/api/v1/movies/{imdbId}` 
* **Method:** `GET`
* **Description:** Retrieves details of a specific movie based on its ID.
* **Parameters:**
    * `{imdbId}`: The unique identifier of the movie.

**3. Add a Review**

* **Endpoint:** `/api/v1/review`
* **Method:** `POST`
* **Description:** Creates a new review for a movie.
* **Request Body (JSON):**

```json
{
  "reviewBody": "This is a review.", 
  "imdbId": "movie123" 
}
```
## Fields

- **reviewBody** : The text content of the review.
- **imdbId** : The unique identifier of the movie (e.g., IMDb ID). This field may be replaced with a different identifier depending on your specific implementation.

---

## Testing with Postman

Follow these steps to test the API with Postman:

### 1. Install Postman

Download and install Postman from [https://www.getpostman.com/](https://www.getpostman.com/).

### 2. Create a New Request

1. Open Postman.
2. Click the **New Request** button (`+`).

### 3. Set Request URL

Enter the desired endpoint URL in the address bar. For example:

```
http://localhost:8080/api/v1/movies
```

### 4. Set Request Method

Select the appropriate HTTP method for your request:

- **GET**: Retrieve data.
- **POST**: Submit data.

### 5. Configure Request Body (for POST requests)

1. Go to the **Body** tab.
2. Select **raw**.
3. Set the type to **JSON**.
4. Paste the required JSON payload, e.g.,

```json
{
  "reviewBody": "This movie was fantastic! A must-watch for everyone.",
  "imdbId": "tt1234567"
}
```

### 6. Send Request

Click the **Send** button to submit your request.

### 7. View Response

Examine the response body for the requested data or confirmation of submission.

---

## Example JSON Payload

For a POST request, use the following example JSON payload:

```json
{
  "reviewBody": "The storyline was captivating and the performances were exceptional.",
  "imdbId": "tt7654321"
}
```

---

## Notes

- Ensure your API server is running at the specified URL.
- Use the appropriate headers (e.g., `Content-Type: application/json`) for your requests.
