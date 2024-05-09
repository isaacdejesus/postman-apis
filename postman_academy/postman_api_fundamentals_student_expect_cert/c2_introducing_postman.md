# An API Platform
- Postman is an API platform for building and using APIs. 
- Postman simplifies each step of API lifecycle to make creation of better APIs faster.
## working with APIs then and now: cURL vs Postman
- Prior to postman cURL was used for making HTTP requests
- API calls with curl: `curl https://api.github.com/users/postmanlabs`
- API calls with Postman: Postman shows response with clean indents, colors and allows to save, organize and share
  requests. 
# Getting started with Postman
- Navigate to https://www.postman.com/
- Sign in
- Install Postman client
- Create a new workspace
- Create a new collection
## Make first request
- Click add request, name it get books.
- Set request method to GET
- Request URL to https://library-api.postmanlabs.com/books
- Save and hit send to submit request
- Response can be viewed in lower half of postman

## Request methods
- When making call to server, must specify a request method that indicates type of operation 
  want to perform. Also called HTTP verbs
- Common HTTP request methods correspond to CRUD operations
    - GET: (Read) Retrieve data
    - POST: (Create) Send data
    - PUT/PATCH: (Update) Update data. 
        - PUT replaces entire resource
        - PATCH is for partial updates
    - DELETE: (Delete) Delete data
- Always read documentation of API being used. This is the API we are using for library/books
  https://documenter.getpostman.com/view/15567703/UVyxRtng#a2f33f71-de38-42fb-97fe-dccac7516e73
## Request URL
- In addition to request method, a request must include request URL that indicates where to make API call to.
  A request URL has 3 parts:
    - Protocol: Such as `http://` or `https://`
    - Host: Location of server `library-api.postmanlabs.com`
    - Path: Route on the server `/books`
- Paths and complete URLs are called API endpoints
## Response status codes
- Status codes are indicators of whether a request failed or succeeded
    - 2xx: Success
        - 200 Ok. 
        - 201 Created. 
        - 204 No content
    - 3xx: Redirection
        - 301 Moved
    - 4xx: Client error
        - 400 Bad request. 
        - 401 Unauthorized. 
        - 403 Not permitted
        - 404 Not found
    - 5xx: Server error
        - 500 Internal server error
        - 502 Bad gateway
        - 504 Gateway timeout
- In postman, hovering over response code tells you what it means!
# Request-Response pattern
- Request-Response pattern represents how computers communicate over a network. 
- API interface lets us know what kind of response to expect depending on call to server
- Client is agent making a request: Could be browser or an app. In this case, Postman is client.
- Request is sent over network to a server. In our case, server is https://library-api.postmanlabs.com
- Server recieved GET request and sent appropiate response back to Postman client: A list of books


