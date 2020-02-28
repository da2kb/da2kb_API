**Document restful_API**
**Dina Ahmed**

This API has the ability to create a new document, read (retrieve) the document, update document information, or delete a document.  it might also need the web API to support the following if you are going to use it to develop an application.

**GET/documents**
get a list of documents that were created in a particular date range, that were written by a particular author, etc.

```json
HTTP/1.1 200 OK
Content-Type: application/json

[{
  "id": "101",
 "author": "Arthur Conan Doyle",
 "title": "Sherlock Holmes",
 "genre": "crimes",
 "location": "Baker St",
 "dateCreated": "22-02-2013",
 "dateLastUpdated": "27-02-2016"
},
{
  "id": "202",
 "author": "Paulo Coelho",
 "title": "The Alchemist",
 "genre": "wisdom",
 "location":"island",
 "dateCreated": "11-01-2011",
 "dateLastUpdated": "12-20-2017"

}
]
```
  **GET/document?author=Arthur Conan Doyle**
  This will get the number of documents that meet certain criteria (like in this case, novels or books written by Arthur Conan Doyle) in the JSON
  ```json
  HTTP/1.1 200
Content-Type: application/json
  {
    "id": "101",
   "author": "Arthur Conan Doyle",
   "title": "Sherlock Holmes",
   "genre": "crimes",
   "location": "Baker St",
   "dateCreated": "20-02-2019",
   "dateLastUpdated": "20-20-2020"
  }
  ```
**DELETE/document?genre=crimes**
  this function is used to delete a collection of documents that meet certain criteria, in this case what suites the genre crimes, the json response
  ```json
HTTP/1.1 202 Accepted
```
**POST/document**
create a new document that can be named and all information filled by the user entries.
```json

{
  "author": "Suzanne Collins",
  "title": "Hunger games",
  "genre": "sci-fi",
  "location":"Panem"
}
```
This is what JSON will return:
```json

{
  "id": "303",
  "author": "Suzanne Collins",
  "title": "Hunger games",
  "genre": "sci-fi",
  "location":"Panem",
  "dateCreated": "27-02-2020",
 "dateLastUpdated": "27-02-2020"
}
```
**PATCH/document?id=202**
this allow user to change and modify details for an already existing function by looking up the function by a special attribute while changing the date of last updated
``` json
{
  "id": "202",
 "author": "Paulo Coelho",
 "title": "Brida",
 "genre": "wisdom",
 "location":"island",
 "dateCreated": "11-01-2011",
 "dateLastUpdated": "27-02-2020"
}
```
**GET/document?dateUpdated=2020-02-27**
Will return all documents that were updated on February 27, 2020(Today's Date)

``` json
    HTTP/1.1 200 OK
    Content-Type: application/json
    Content: 2  
[{
    "id": "202",
   "author": "Paulo Coelho",
   "title": "Brida",
   "genre": "wisdom",
   "location":"island",
   "dateCreated": "11-01-2011",
   "dateLastUpdated": "27-02-2020"
 },
 {
   "id": "303",
   "author": "Suzanne Collins",
   "title": "Hunger games",
   "genre": "sci-fi",
   "location":"Panem",
   "dateCreated": "27-02-2020",
  "dateLastUpdated": "27-02-2020"
 }
]
 ```
