#Variables in Postman
- Postman allows usage of variables to store data and easily hide sens info like API keys
- Variable data can be accessed using {{variable_name}}
- Create variable by selecting text and clicking create var
- https://library-api.postmanlabs.com
- Highlight and hover above url and make it a var named base_url
- Then can be used: `{{base_url}}/books`
## Where are my variables?
- Click collections> select current_collection >  variables tab
- From there you can view and edit variables
- Note there are two colums:
    - initial value: The value ini set when someone forks or imports the collection
      If collection is shared, they can see this value. Don't put secrets here
    - current value: variable resolves to this value. It is local and not public.
      Good to keep secrets like API keys. Use this column for secrets, not initial
      column
# Query params
- Recall minimun reqs to make a request are:
    - Request method: GET, POST, PUT, PATCH, DELETE, ETC
    - A request URL
- Some APIs allow refining request using key-value pairs called query parameters
## Query params syntax
- Query params are added to end of path
    - They start with ?, followed by key-value pairs in format `<key>=<value>`
    - Ex. to fetch all photos that have landscape orientation
    `GET https://some-api.com/photos?orientation=landscape`
    - If multiple query params, they are separated by `&`
    `GET https://some-api.com/photos?orientation=landscape&size=500x400`
## Search Google with query params
- https://www.google.com/search?q=postman
    - paste the above url into browser or as GET request in Postman to make a Google search for "Postman"
    - In Postman, click "preview" tab in response to view rendered html
    - Request adds a search term as query param `q=postman`, `q` refers to query to the GET/search path on 
      Google's server
    - Due to params in rquest, server returns html doc with search results page with hits for 'Postman'
    - Search can be changed directly from URL by changing value for query params: `q=<something>` 
## When to use query params
- Read API docs to know when and how to use query params for the given API
# TASK: Search books by genre
- Filter book results to show only fiction books
- API allows to add query params to GET /books request to filter the results
- Link to docs: https://documenter.getpostman.com/view/15567703/UVyxRtng
1. Hover over existing `get books` request, click 3 dots and select duplicate. 
2. Re-name duplicate `get fiction books` 
3. Using params tab add query param with key `genre` and value `fiction` to the `get fiction books`  request
4. Save and Send reques
# TASK: Multiple query params
- Add second query param to GET /books only to list books where the checkedOut property is false.
1. In same "get fiction books" request, add a second query param with key `checkedOut` and value `false`
2. Save and Send request
# Path variable
- Another way of passing request data to API is via _path variable_ ("path params"). A path variable is dynamic
  section of a path and is used for IDs and entity names such as usernames
## Path variable syntax
- Path variable comes after a _/_ in the path. 
- Ex. github API allows search for users by providing username in place of {username} below
    - GET https://api.github.com/users/{username}
    - Making API call with a value for {username} fetches data about user
    - GET https://api.github.com/users/isaacdejesus
- Possible to have multiple path variables in single request
    - GET https://api.github.com/repos/{owner}/{repoName}
    - GET https://api.github.com/repos/isaacdejesus/interview-prep
## Path vs query params
- Path variable
    - Ex. _/books/abc123_
    - Located directly after slash in path. It can be anywhere on path
    - Accepts dynamic values
    - Often used for IDs or entity names
- Query params
    - ex _/books?search=borges&checkedOut=false_
    - Located only at end of path, right after a _?_
    - Accepts defined query keys with potentially dynamic vals
    - Often used for options and filters
- When to use path variable? Read API doc
# TASK: Get a book by id
- Check whether "Ficciones" by Jorge Luis Borges is avaiable with id _29cd820f-82f9-4b45-a7f4-0924111b5b89_
## Get book by id
- Specific book can by visiting _GET /books/:id_ Where :id is book's id
1. Hover over collection, click 3 dots and _add_request_ with name _get book by id_
2. Set request method to GET and url _{{base_url}}/books/:id_
   _Path variables_ can be found under the params tab of request. 
3. In Params tab of request, paste id for "Ficciones" _29cd820f-82f9-4b45-a7f4-0924111b5b89_ as value for
   path variable named id
4. Save and Send request
## Debugging request in Postman console
- Raw request sent by Postman to API can be viewed by opening Postman console located in lower left
- Postman inserted the book _id_ as path parameter in place of _:id_ placeholder when making request
- If errors, check the postman console to make sure raw request was sent as expected
