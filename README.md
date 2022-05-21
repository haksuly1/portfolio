<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8" />
    <title>My Portfolio Page</title>
  </head>

<body>
<h1>myFlix-app Documentation</h1>
<br>
<h2>This is my portfolio documentation page.It was built using HTML5 & CSS</h2>
<p>
  Project built as part of CareerFoundry's Full-Stack-Web-Development-Course to demonstrate the mastery of full-stack JavaScript develpoment with MERN stack.

  This README contains technical and content-related details about the server-side and client-side component of a React application called "myFlix". The REST API for "myFlix" is hosted online on Heroku and provides logged in users with access to information about different movies, directors, and genres. For detailed information about all the provided features, see Features sector. The server-side of the application (server, business logic, business layers) consists of a REST API and architected database built using JavaScript, Node.js, Express, and MongoDB.

  The REST API can be accessed via commonly used HTTP methods (GET, POST, PUT, DELETE). CRUD is used to retrieve data from the database and store that data in a non-relational way.
</p>

<h1>Server-Side</h1>
<br>
<h2>Features</h2>
  <p>
        - Allows users to see a list of all movies in the database
    <br>- Allows users to get detailed information about a single movie by movie title
    <br>- Allows users to get detailed information about a genre by genre name
    <br>- Allows users to get detailed information about a director by name
    <br>- Allows new users to create an user account
    <br>- Allows existing users to update their user info or to delete their account
    <br>- Allows existing users to add or remove movies to and from their list of favorites
    </p>

<h2>Dependencies</h2>
        - bcrypt
    <br>- body-parser
    <br>- cors
    <br>- express
    <br>- express-validator
    <br>- jsonwebtoken
    <br>- mongoose
    <br>- morgan
    <br>- passport
    <br>- passport-jwt
    <br>- passport-local
    <br>- uuid

<h1>End Points</h1>
<br>
<h2>Get List of All Movies</h2>
    <h3>Endpoint: /movies</h3>
    <br>HTTP Method: GET
    <br>Request body data format: None
    <br>Response body data format: JSON Object holding data about all movies
    <br>Get data about a single movie by title
    <br>
    <h3>Endpoint: /movies/[Title]</h3>
        Query Parameters: [Title] of movie
    <br>HTTP Method: GET
    <br>Request body data format: None
    <h3>Response body data format:</h3> JSON object holding data about a single movie, containing title, description, genre, director, imageURL, featured or not.

<h2>Response Example:</h2>
    <br>

    {
        "Genre": {
            "Name": "Drama",
            "Description": "In film and television drama is a category of narrative fiction or semi-fiction intended to be more serious than humorous in tone."
        },
        "Director": {
            "Name": "Sidney Lumet",
            "Bio": "Sidney Lumet was a master of cinema, best known for his technical knowledge and his skill at getting first-rate performances from his actors and for shooting most of his films in his beloved New York. He made over 40 movies, often complex and emotional, but seldom overly sentimental.",
            "Birth": "1924-06-25T00:00:00.000Z",
            "Death": "2011-04-09"
        },
        "Actors": [],
        "_id": "61dbd273a51ffbd65ec81db2",
        "Title": "The Fugitive Kind",
        "Description": "Valentine “Snakeskin” Xavier, a trouble-prone drifter trying to go straight, wanders into a small Mississippi town looking for a simple and honest life but finds himself embroiled with problem-filled women.",
        "ImagePath": "https://upload.wikimedia.org/wikipedia/en/b/bb/FugitiveKind.JPG",
        "ReleaseYear": "1960",
        "Feature": true
    }

    <h2>Get data about a genre by name</h2>
    <br>
        - Endpoint: /movies/directors/[Name]
    <br>- Query Parameters: [Name] of director
    <br>- HTTP Method: GET
    <br>- Request body data format: None
    <h3>Response body data format:</h3> JSON object holding data about a director, containing name, bio, date of birth and death if existing.
  
<h2>Response Example:</h2>
<br>

 "Genre": {
            "Name": "Drama",
            "Description": "In film and television drama is a category of narrative fiction or semi-fiction intended to be more serious than humorous in tone."
        }

<h2>Get a list of all users<h2>
        - Get a list of all users
    <br>- Endpoint: /users
    <br>- HTTP Method: GET
    <br>- Request body data format: None
    <h3>Response body data format:</h3> JSON object holding data about all users.

<h2>Response Example:</h2>
    <br>

    {
        "_id": "61dbd745a51ffbd65ec81dc1",
        "Username": "Tatiana Obtu",
        "Password": "Obtu123",
        "Email": "obtutatiana@gmail.com",
        "Birthday": "1995-06-29T00:00:00.000Z",
        "FavoriteMovies": []
    },
    {
        "_id": "61dbd6f5a51ffbd65ec81dbd",
        "Username": "festus ade",
        "Password": "Festus123",
        "Email": "festusade@gmail.com",
        "Birthday": "1975-03-17T00:00:00.000Z",
        "FavoriteMovies": []
    },
    {
        "_id": "61dbd71ea51ffbd65ec81dbf",
        "Username": "Judge Kroos",
        "Password": "Kroos123",
        "Email": "kroosjudge@gmail.com",
        "Birthday": "1980-09-06T00:00:00.000Z",
        "FavoriteMovies": []
    }

<h2>Get a user by username</h2>
        - Endpoint: /users/[Username]
    <br>- Query Parameters: [Username] of user
    <br>- HTTP Method: GET
    <br>- Request body data format: None
    <h3>Response body data format:</h3> JSON object holding data about a single user.

<h2>Response Example:</h2>
<br>

<h2>Add a new user<h2>
        - Endpoint: /users
    <br>- HTTP Method: POST
    <h3>Request body data format:</h3> JSON object holding data about a user, structured like:

<h2>Response Example:</h2>
<br>
{
    "Username": "nabeel01",
    "Password": "$2b$10$4OgyjgP..RZZr9To9PP4Gem91MDEhTNeVDcI0XqZmvYbFEP.7dSdm",
    "Email": "nabeel@gmail.com",
    "Birthday": "1960-09-30T23:00:00.000Z",
    "FavoriteMovies": [],
    "_id": "6286bff1db051c7c44d0e52d",
    "__v": 0
}

<h3>Response body data format:</h3> JSON object holding data about the user that was added, including an ID and a "Favorites" key.

<h2>Response Example:</h2>
<br>

{
    "user": {
        "_id": "6286d3b5ca6a0622bfed7c4c",
        "Username": "simisola01",
        "Password": "$2b$10$4Lvi0S5vD5IoBpjCLuwN5.XIq39YsaNLJSEYtyzKoz7rHwMRmLbWa",
        "Email": "simisola@gmail.com",
        "Birthday": "1960-10-01T00:00:00.000Z",
        "FavoriteMovies": [],
        "__v": 0
    },
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI2Mjg2ZDNiNWNhNmEwNjIyYmZlZDdjNGMiLCJVc2VybmFtZSI6InNpbWlzb2xhMDEiLCJQYXNzd29yZCI6IiQyYiQxMCQ0THZpMFM1dkQ1SW9CcGpDTHV3TjUuWElxMzlZc2FOTEpTRVl0eXpLb3o3ckh3TVJtTGJXYSIsIkVtYWlsIjoic2ltaXNvbGFAZ21haWwuY29tIiwiQmlydGhkYXkiOiIxOTYwLTEwLTAxVDAwOjAwOjAwLjAwMFoiLCJGYXZvcml0ZU1vdmllcyI6W10sIl9fdiI6MCwiaWF0IjoxNjUzMDAzMjcxLCJleHAiOjE2NTM2MDgwNzEsInN1YiI6InNpbWlzb2xhMDEifQ.2-reV6kutYVCAYfTP6JyTXKmjNL8Xvi5B9P5cp0lFls"
}

<h2>Update user information by userName</h2>
        - Endpoint: /users/[Username]
    <br>- Query Parameter: [Username] of user
    <br>- HTTP Method: PUT
    <h3>- Request body data format:</h3> JSON object holding data to be updated, structured like:

<h2>Response Example:</h2>
<br>

{
    "Username": "nabeel01",
    "Password": "$2b$10$4OgyjgP..RZZr9To9PP4Gem91MDEhTNeVDcI0XqZmvYbFEP.7dSdm",
    "Email": "nabeel@gmail.com",
    "Birthday": "1960-09-30T23:00:00.000Z",
    "FavoriteMovies": [],
    "_id": "6286bff1db051c7c44d0e52d",
    "__v": 0
}

<h3>Response body data format:</h3> JSON data holding updated user info.

<h2>Add a movie to list of favorites by movie ID</h2>
        - Endpoint: /users/[Username]/Movies/[MovieID]
    <br>- Query Parameter: [Username] of user and [MovieID]
    <br>- HTTP Method: POST
    <br>- Request body data format: None
    <h3>Response body data format: A text message indicating the movie was added to the list of favorites and the updated list of favorites.</h3>

<h2>Response Example:</h2>
<br

<h2>Delete a movie from list of favorites by movie ID</h2>
        - Endpoint: /users/[Username]/Movies/[MovieID]
    <br>- Query Parameter: [Username] of user and [MovieID]
    <br>- HTTP Method: DELETE
    <br>- Request body data format: None
    <h3>Response body data format:</h3> A text message indicating whether the movie was successfully removed and the updated list of favorites.

<h2>Response Example:</h2>
<br

<h2>Delete user by username<h2>
        - Endpoint: /users/[Username]
    <br>- Query Parameter: [Username] of user
    <br>- HTTP Method: DELETE
    <br>- Request body data format: None
    <h3>Response body data format:</h3> A text message indicating whether the user account was successfully deleted.

<h2>Response Example:</h2>
<br

ramar02 was deleted

<h1>Client-side</h1>
The UI of myFlix is built using the React library. The interface views will handle data requested by the user through the REST API endpoints defined above.

<h2>Technical Details</h2>
<h3>The application...</h3>
      - is a single-page application
  <br>- uses state routing to navigate between views and share URLs
  <br>- gives users option to filter movies
  <br>- gives users option to sort movies
  <br>- initially uses Parcel as its built tool
  <br>- is migrated to create-react-app
  <br>- is written using React library and ES2015+
  <br>- is written with React Redux
  <br>- uses Bootstrap as a UI library for styling and responsiveness
  <br>- contains a mix of class components and function components
  <br>- is hosted online: myFlix
  <br>
<h1>Essential Views and Features</h1>
<h2>Main view</h2>
      - returns a list of all movies to the user (each listed item with image, title, description)
  <br>- sorting and filtering
  <br>- ability to select a movie for more details
  <br>- provides links/buttons to see profile data and to log out

<h2>Movie view</h2>
      - returns data (description, genre, director, image) about a single movie to the user
  <br>- allows users to add a movie to their list of favorites
  <br>- Login view
  <br>- allows users to login with username and password
  <br>- provides a link for new users registration view
  <br>- Registration view
  <br>- allows new users to sign in (username, password, email, birthday)

<h2>Genre view</h2>
      - returns data about a genre (name, description)
  <br>- displays example movies

<h2>Director view</h2>
      - returns data about a director (name, bio, birth year, death year if existing)
  <br>- displays example movies

<h2>Profile view</h2>
      - allows users to see their profile data (username, email, birthday)
  <br>- displays favorite movies
  <br>- allows users to remove a movie from their list of favorites
  <br>- provides buttons to either update or delete existing account

<h2>Update profile</h2>
      - allows users to update their user info
</body>
</html>
