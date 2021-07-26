## After Cloning
After cloning the repo, make sure to run `npm install` in the root of the project directory.

## Running the application
From the command line, in the root of the project, run `npm run start:dev` this will start the server on port 3000

## Rest

APIs are protected, use authentication token, i.e.
see ./server/routes/index.js for implementation

#List all books
```
curl --location --request GET 'localhost:3000/books' \
--header 'G-TOKEN: ROM831ESV'
```

#Search for books
```
curl --location --request GET 'localhost:3000/books/search?title=waste' \
--header 'G-TOKEN: ROM831ESV'
```

#Create a book
```
curl --location --request POST 'localhost:3000/books' \
--header 'G-TOKEN: ROM831ESV' \
--header 'Content-Type: application/json' \
--data-raw '{
    "title": "BOOK",
    "author": "Abc Cde",
    "releaseDate": "2021-01-01",
    "isbn": "1234567890"
}'
```

#Delete
Authorization is required (basic admin/admin)
see ./app.js
```
curl --location --request DELETE 'localhost:3000/books/28' \
--header 'G-TOKEN: ROM831ESV' \
--header 'Authorization: Basic YWRtaW46YWRtaW4='
```

