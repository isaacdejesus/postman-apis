# TASK: Checkout your  book
- Someone wants to check out the newly added book
- Need to update the db to mark the book's checkedOut status from false to true
- Doc indicate book can be update by id, by making request with updated info to
`PATCH https://library-api.postmanlabs.com/books/:id`
## Make a request to update the book
1. Hover "Postman Library API v2" collection, click 3 dots and select add request name it "checkout a book"
2. Set request method to PATCH
3. Set request URL to _{{baseUrl}}/books/:id_
4. Under params tab, set value of path variable id to {{id}}
   This will replace id with collection variable named id which was set by test script when last back was added
5. Add raw json in body with following payload
```
{
    "checkedOut": true
}
```
6. Save and send request
- Should result in 200 ok as response. Notice how the "checkedOut" field is not true
# TASK: Delete your book
- Delete the book with `DELETE /books/:id` path
## Make new request
- DELETE request is similar to PATCH request. So duplicate PATCH request!
1. Hover collection, click 3 dots and select add request named "delete a book"
2. Set request method to DELETE
3. Set request URL to {{baseUrl}}/books/:id
4. In params tab of request set path variable id to {{id}}
5. Save and send
- Should result in 204 no content response from API. Meaning server successfully deleted book
# Postman codegen feature
## Generating code snippets
- Each request has a code generation tab accessed by clicking </> icon to the right
- Click and select language. Will generate code snipped in selected language to create the call

