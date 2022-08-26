# API Documentation Practice
In this exercise, your task is to practice writing documentation for the bookstore app we created earlier.

You'll soon be writing documentation for your final project (the Trivia API), after which you'll get feedback from a reviewer. You can think of this as some rudimentary practice to prepare for that.

At each step, you can compare what you've written with our own version. Of course, **there isn't a single correct way to write a piece of documentation**, so your version may look quite different. However, there are principles and practices you should follow in order to produce quality documentation, and we'll point this out so you can check whether you've incorporated them in what you wrote.

## Getting started
Now, add a Getting Started section to your documentation. Remember, this should include at least your base URL and an explanation of authentication. Feel free to provide other information that is relevant for your API

The Bookshelf API is built following the REST principles. It returns various books by different authors with their ratings. The Bookshelf API accepts form-encoded request bodies and returns JSON-encoded reponses. 

### Base URL
The base URL is 127.0.0.1/books

### Authentification
This API does not implement any authentification

## Error Handling
The bookshelf API uses HTTP response codes to display the success or failure of an API call. 

### Response - Meaning
- 200 - OK
- 400 - Bad request
- 404 - Resource not found
- 405 - Method not allowed
- 422 - Unprocessed

## Endpoint Library
These are all the endpoints supported by the Bookshelf API

### Get All Books
- General:
    - This endpoint will return all the books in our database, success and total books
    - Results are paginated in groups of 8

- Sample: `curl -X "GET" http://127.0.0.1:5000/books`

- Response:
```
{
  "books": [
    {
      "author": "Stephen King",
      "id": 1,
      "rating": 5,
      "title": "The Outsider: A Novel"
    },
    {
      "author": "Lisa Halliday",
      "id": 2,
      "rating": 4,
      "title": "Asymmetry: A Novel"
    },
    {
      "author": "Kristin Hannah",
      "id": 3,
      "rating": 4,
      "title": "The Great Alone"
    },
    {
      "author": "Tara Westover",
      "id": 4,
      "rating": 5,
      "title": "Educated: A Memoir"
    },
    {
      "author": "Jojo Moyes",
      "id": 5,
      "rating": 5,
      "title": "Still Me: A Novel"
    },
    {
      "author": "Leila Slimani",
      "id": 6,
      "rating": 1,
      "title": "Lullaby"
    },
    {
      "author": "Amitava Kumar",
      "id": 7,
      "rating": 5,
      "title": "Immigrant, Montana"
    },
    {
      "author": "Madeline Miller",
      "id": 8,
      "rating": 5,
      "title": "CIRCE"
    }
  ],
  "success": true,
  "total_books": 16
}
```
### Update Book rating
- General:
    - This endpoint will update the rating of specified book and returns the success value and id of the modified book. 
    - A rating and book id must be provided

- Sample: `curl http://127.0.0.1:5000/books -X PATCH -H "Content-Type: application/json" -d '{"rating": 3}'` 

- Response:
```
 {
    'success': True
}
```
### Delete book
- General:
    - This endpoint will delete the specified book if it exists and returns the id of the deleted book, success value, total books, and book list based on current page number to update the frontend. 
    - Book Id must be provided

- Sample: `curl -X "DELETE" http://127.0.0.1:5000/books/2`

- Response:

```
"books" : [
    {
      "author": "Gina Apostol",
      "id": 9,
      "rating": 5,
      "title": "Insurrecto: A Novel"
    },
    {
      "author": "Tayari Jones",
      "id": 10,
      "rating": 5,
      "title": "An American Marriage"
    },
    {
      "author": "Jordan B. Peterson",
      "id": 11,
      "rating": 5,
      "title": "12 Rules for Life: An Antidote to Chaos"
    },
    {
      "author": "Kiese Laymon",
      "id": 12,
      "rating": 1,
      "title": "Heavy: An American Memoir"
    },
    {
      "author": "Emily Giffin",
      "id": 13,
      "rating": 4,
      "title": "All We Ever Wanted"
    },
    {
      "author": "Jose Andres",
      "id": 14,
      "rating": 4,
      "title": "We Fed an Island"
    },
    {
      "author": "Rachel Kushner",
      "id": 15,
      "rating": 1,
      "title": "The Mars Room"
    }
  ],
  "deleted": 16,
  "success": true,
  "total_books": 15
}
```

### Create Book
- General:
    - This endpoint will add a book to the database as long as a title, author and rating are provided returns the id of the created book, success value, total books, and book list based on current page number to update the frontend.
    - A book object must be provided

- Sample: `curl http://127.0.0.1:5000/books -X POST -H "Content-Type: application/json" -d {"title": "A new beginning", "author": "John Savy", "rating": 3}

- Response:
```
  "books": [
    {
      "author": "Neil Gaiman",
      "id": 24,
      "rating": 5,
      "title": "Neverwhere"
    }
  ],
  "created": 24,
  "success": true,
  "total_books": 17
}
```