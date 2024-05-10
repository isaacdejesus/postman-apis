# Variables in postman: Continued
- Variables allow to reuse values and hide sensitive values like API keys from being shared publicly
## Variable scopes
- Variables can live at various scopes. Postman resolves to value at nearest and narrowest scope
- From broadest to narrowest: global, collection, environment, data, local.
- If var with same name is declared at dif scopes value stored in variable with narrowest scope will
  be used. Ex. if there is a global username and a local username, the local value will be used.
- Collection var can be accessed anywhere inside collection
# Setting variables programmatically
## Scripting in postman
- Adding automation and dynamic behaviors to collections with scripts
- Postman automatically executes scripts during two events in request flow:
    1. Immediately before a request is sent: _pre-request script_ 
    2. Immediately after a response comes back: _post-request script_
## PM object
- Helper object named pm gives access to data about Postman environment, requests, responses, variables
  and resting utilities.
- Ex. can access json response body from API with:
    - `pm.response.json()`
- Programmatically get collection variables like value of base_url with:
    - `pm.collectionVariables.get("base_url")`
- Can also set variables with:
    - `pm.collectionVariables.set("var_name", "var_value")`
    - `pm.collectionVariables.set("my_var", "foo")`
# TASK: First script
## Add script to request
- Note: Latest version of postman merged Pre-requests and Tests tab into a single Scripts tab. Both
  pre and post scripts are placed in there. 
- From now on in course, we will only be writing post-request scripts
1. In "add book" request, change payload to a new book
2. Open _Tests_ tab of request or _post-response_ tab within scripts
3. Add `console.log(pm.response.json())`
4. Save and send
5. Open console and scroll to bottom to see logs. Data from API is logged bc code in tests tab 
# TASK: Grab new book id
- Saving values as variable allows to use it in other requests. 
- Using post-response scripts, grab id of newly added book and save it for future requests
## Setting and getting collection variables
- pm object allows to set and get collection variables
- To set collection variable, use .set() method with 2 parameters: variable name and variable value
    - `pm.collectionVariables.set("variable_name", value)`
- To get collection variable, use .get() methods and specify name of variable want to retrieve
    - `p,.collectionVariables.get("variable_name")`
## Local variables
- Local variables can be stores inside Post-response script
## Set new book _id_ as a variable
1. In body of "add a book" request, change payload to new book
2. In post-response tab in scripts of "add a book" request, replace console.log() with
```
// save the value of the "id" value from the API JSON response to a const variable named "id"
const id = pm.response.json().id
// set the value of the "id" variable to a collection variable also called "id".
pm.collectionVariables.set("id", id)
```
3. Save and send. When 201 response returns, the test script will run and save the book's id as
   a collection variable. 
4. View collection variables: click collection > variables tab
   Now there is an id variable that maps to id of newly added book. Value can be accessed {{id}}
# Halfway Test:
1. Fork test collection into workspace by visiting: 
- https://www.postman.com/postman-student-programs/workspace/postman-api-fundamentals-student-expert-test-your-collection/overview
- Hover over collection, 3 dots and select _create fork_
- Should have 2 collections: _Postman Library API v2_ and _Collection Test_ 
2. Get API link for _Postman Library API v2_ collection
- Hover collection, click 3 dots, select share > Via API > Generate New Key > copy
- NOTE: I don't have api option on linux. Had to use web version.
3. Navigate to forked _Collection Test_ and open variables tab and paste API link from above
   to both columns for value "submission"
4. Navigate to halfway test and send request

