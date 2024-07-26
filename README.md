# API Documentation

## Endpoint: /getFavorites

**Description:**
Retrieves favorite questions from the `favorites.json` file.

**Method:** GET

**Expected Input:** None

**Output:**
- **Status Code:** 200
- **Response Model:** `FavoriteQuestions`
  - **Datatype:** JSON
  - **Content:**
    - `questions`: dict

**Error Responses:**
- **Status Code:** 404
- **Detail:** "No favorites found"

## Endpoint: /addFavorites

**Description:**
Adds a question to the list of favorite questions.

**Method:** POST

**Expected Input:**
- **Request Body:** `Question`
  - **Datatype:** JSON
  - **Content:**
    - `question`: str
    - `sql_query`: dict
    - `history`: list of dicts

**Output:**
- **Status Code:** 200
- **Content:**
  - `message`: str

## Endpoint: /deleteFavorites

**Description:**
Removes a question from the list of favorite questions.

**Method:** DELETE

**Expected Input:**
- **Query Parameter:** `question`
  - **Datatype:** str

**Output:**
- **Status Code:** 200
- **Content:**
  - `message`: str

## Endpoint: /generateAnswer

**Description:**
Generates an answer for a given question, including executing SQL queries and processing the result.

**Method:** POST

**Expected Input:**
- **Request Body:** `Question`
  - **Datatype:** JSON
  - **Content:**
    - `question`: str
    - `sql_query`: dict
    - `history`: list of dicts

**Output:**
- **Status Code:** 200
- **Content:**
  - `answer`: str
  - `sql_query`: dict
  - `history`: list of dicts

## Endpoint: /feedback

**Description:**
Handles user feedback for generated answers and SQL queries.

**Method:** POST

**Expected Input:**
- **Request Body:** `FeedbackRequest`
  - **Datatype:** JSON
  - **Content:**
    - `user_query`: str
    - `sql`: str
    - `response`: str
    - `feedback_received`: bool
    - `feedback_type`: str
    - `comment`: str

**Output:**
- **Status Code:** 200
- **Content:**
  - `message`: str

**Error Responses:**
- **Status Code:** 500
- **Detail:** "Error processing feedback: {error message}"
