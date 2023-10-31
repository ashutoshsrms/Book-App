Book Management RESTful API
This is a RESTful API for managing books. It provides endpoints for creating, retrieving, updating, and deleting books.

API Endpoints and Usage
Add a New Book

Endpoint: /addBook
Method: POST
Request Body:
{
    "title": "Iron Man",
    "author": "Stan Lee",
    "summary": "Super Hero Comic"
}
Response:
{
    "message": "New Book Added Sucessfully",
    "data": {
        "title": "Iron Man",
        "author": "Stan Lee",
        "summary": "Super Hero Comic",
        "_id": "6540d1cbbf0165464b800944",
        "__v": 0
    }
}

Get All Books

Endpoint: /getAllBooks
Method: GET
Response:

{
    "data": [
        {
            "_id": "6540ccc792595a0bdbe803c6",
            "title": "Avengres",
            "author": "Stan Lee",
            "summary": "Super Hero Comic",
            "__v": 0
        },
        {
            "_id": "6540cddf399eb9ec2956e59c",
            "title": "Spider Man",
            "author": "Stan Lee",
            "summary": "Super Hero Comic",
            "__v": 0
        },
        {
            "_id": "6540cdf6399eb9ec2956e59e",
            "title": "Loki",
            "author": "Stan Lee",
            "summary": "Super Hero Comic",
            "__v": 0
        },
        {
            "_id": "6540d1cbbf0165464b800944",
            "title": "Iron Man",
            "author": "Stan Lee",
            "summary": "Super Hero Comic",
            "__v": 0
        }
    ]
}

Get Book by ID

Endpoint: /getBookById/:id
Method: GET
Response:
{
    "_id": "6540ccc792595a0bdbe803c6",
    "title": "Avengres",
    "author": "Stan Lee",
    "summary": "Super Hero Comic",
    "__v": 0
}

Update Book

Endpoint: /updateBook/:id
Method: PUT
Request Body:
{
    "title": "Avengres",
    "author": "Stan Lee",
    "summary": "Super Hero Comic"
}
Response:
{
    "message": "Updated",
    "data": {
        "_id": "6540ccc792595a0bdbe803c6",
        "title": "Avengres",
        "author": "Stan Lee",
        "summary": "Super Hero Comic",
        "__v": 0
    }
}

Delete Book

Endpoint: /deleteBook/:id
Method: DELETE
Response:
{
  "message": "Book deleted successfully"
}

Setup and Run Locally

1)Clone the Repository:

2)git clone <repository-url>
cd book-api

npm install

3)Set Up MongoDB:

Ensure you have a MongoDB instance running.
If You want Update the MongoDB connection URL in db.js to point to your MongoDB instance.

4)Run the Application:
npm start

Decisions and Assumptions
MongoDB: MongoDB was chosen as the database due to its flexibility and scalability, allowing easy storage and retrieval of JSON-like documents.
Error Handling: The API handles various error scenarios, such as invalid requests, missing data, or non-existing resources, and returns appropriate HTTP status codes and error messages for client understanding.
Validation: Basic validation for input data (required fields, empty strings) is implemented. For more advanced validation, additional libraries or middleware can be added based on specific project requirements.
