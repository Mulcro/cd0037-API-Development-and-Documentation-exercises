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
Now, add an Error Handling section to your documentation. It should include the format of the error responses the client can expect as well as which status codes you use.
- Response codes
- Messages
- Error types

The bookshelf API uses HTTP response codes to display the success or failure of an API call. 

### Response - Meaning
200 - OK
400 - Bad request
404 - Resource not found
405 - Method not allowed
422 - Unprocessed

## Endpoint Library
Now, add an Endpoint Library section to your documentation. Make sure that endpoints, methods and returned data are all clear. Consider including sample requests for clarity

- Organized by resource
- Include each endpoint
- Sample request 
- Arguments including data types
- Response object including status codes and data types 

### Get All Books
endpoint call: 127.0.0.1/books


response: {
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

### Update Book rating

Arguments required: book id, rating object
endpoint: 127.0.0.1/books/id, {'rating': 1-5}
example: 127.0.0.1/books/3, {'rating': 3}
response: {
    'success': True
}

### Delete book
method: DELETE
Arguments required: book id
endpoint: 127.0.0.1/books/id
example: 127.0.0.1/books/3
response: {
    'success': True,
    "deleted": book_id,
    "books": current_books,
    "total_books": len(Book.query.all()
}


### Create Book
method: POST
Arguments required: book id, book object
endpoint: 127.0.0.1/books/id, {'title':bookTitle, 'Author': bookAuthor, rating': 1-5}
example: 127.0.0.1/books/3, {'title':bookTitle, 'Author': bookAuthor, rating': 1-5}
response: {
        "success": True,
        "created": book.id,
        "books": current_books,
        "total_books": len(Book.query.all())
}
