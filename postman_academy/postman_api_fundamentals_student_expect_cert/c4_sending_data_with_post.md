# TASK: Add a book
- Add a book via POST request with a JSON body to submit book data to API database.
- Documentation for endpoint https://documenter.getpostman.com/view/15567703/UVyxRtng#e0dbc14c-371d-4813-97c3-281de36fad0c
## What is the body?
- Sending data in body of request is needed when have to add or update data. Body data needed for GET, POST and PATCH requests
- Body tab in Postman enables to add data to be sent with request. 
- Select format of data sent in Postman: Select Body tab > Raw > Text 
## Make POST request
1. Hover over collection, click 3 dots and add request named _add book_
2. Set request method to POST and request URL to _{{base_url}}/books_
3. Endpoint requires adding a body to request to send as payload. Payload will be json object containing info about book
   want to add. 
   - Click body tab of request and select data type raw > json
   - Inside body editor add:
   ```
    {
        "title": "To Kill a Mockingbird",
        "author": "Harper Lee",
        "genre": "fiction",
        "yearPublished": 1960
    } 
   ```
   - NOTE: Above results in error! "Invalid or missing credentials!" .:. Need to add an api key to headers of request
# Task: Add authorization header
- Some APIs require Authorization/Auth for certain endpoints in order to access request
## Authorization
- Ways of authorizing a request
    - Basic Auth: Username and password
    - OAuth: Delegated authorization
    - API keys: Secret string registered to a dev 
## Getting API key
- Generally have to sign up in order to be assigned an API key which allows org to track who makes requests.
- Current API doesn't require registration, just need to know the API key
    - Header name: _api-key_
    - Header value:_postmanrulz_
- Current API requires adding this header to any requests to add, update or delete books. bc these operations
  change data in db.
## Headers
- Headers is way of adding metadata to requests. Metadata such as authorization or specify data type want to 
  receive as response. This is dif from payload data sent in body of request. 
- Think of headers as outside of envelope when sending a letter. Envelope has info about delivering letter, 
  like proof of paid postage. The actual payload is the letter inside the envelope!
## Add API key to request header
1. On "add a book" request, click headers tab
2. In headers helper table, add key _api-key_ with value _postmanrulz_
3. Save and Send request
- Above should result in 201 created response with response body that is an object containing newly added book.
- !!! Don't forget to check console and select request to view more info about request. Can view headers 
  body of request, as well as response body!
# TASK: Use postman Auth
- Postman has Auth helper to make authorizing requests easier
## Delete _api-key_ header
- Go to headers, hover over api-key and click x to delete the header and save
## Add Auth to collection
- Postman Auth helper can add authorization to request, folder or collection level
- Adding api-key to entire collection so all requests will send the key
    1. Select collection > Authorization or Auth tab
    2. Select API Key as Auth type from menu
    3. Enter API key details: key _api-key_ and value _postmanrulz_ and Add to: Header
    4. Save
## Add a new book
    1. Go to "add a book" request and add another book by changing payload of body tab
    2. Ensure Auth method in Authorization tab is set to _inherit from parent_ 
    3. Save and send
    4. Open console in lower left to view headers

