# Imitating GitHub API for our for a blog site

- #### User Login into the Blog site 

  ```shell
  curl -u username:password https://api.example.com
  ```

  When the password and username matches, then successfully Login, otherwise return an error 

  ```
  404 not Found
  ```

- #### View users' published blogs

  ```json
  GET /username/articles
  ```

  And the response should be :

  ```json
  {
    "username":"user1"
      "total_num":100,
      "articles":[
          {
                "articleID": 17343132,
                "title":"title1",
                "href":"https://api.example.com/username/articles/1",
                "private": false,
                "description": "...",
                "created_at": "2018-01-01T00:31:50Z",
                "updated_at": "2019-01-05T17:58:47Z",
                "action":"GET",
                "status":"original"
                "words": 1234,
                "visits": 50
          },
        ...
      ]
  }
  
  ```

- Get the details of a blog

  - By `articleID`

    ```json
    GET /username/articles/articleID
    curl -u -i https://api.example.com/username/articles/1
    ```

  - By `articleTitle`

    ```json
    GET /username/articles/articleTitle
    curl -u -i https://api.example.com/username/articles/test
    ```

The response should be: 

```json
{
     "articleID": 1,
     "title":"title1",
     "href":"https://api.example.com/username/articles/1",
     "private": false,
     "description": "...",
     "created_at": "2018-01-01T00:31:50Z",
     "updated_at": "2019-01-05T17:58:47Z",
     "action":"GET",
     "status":"original"
     "words": 1234,
     "visits": 50，
     "content":"article contents...."
}
```

- #### Get a comments of a blog

  ```shell
  GET /username/articles/articleID/comments
  curl -u -i https://api.example.com/username/articles/1/comments
  
  GET /username/articles/articleTitle/comments
  curl -u -i https://api.example.com/username/articles/test/comments
  
  ```

  The response:

  ```json
  {
      "id": 1,
      "author": "username",
      "href": "https://api.example.com/username/articles/1",
      items:[{
             "contents":xxx,
             "user": {
                "name":"user2"
                "href": "xxx",
               },
             "created_at": "2018-01-01T00:31:50Z"
           }
             ....
      ]
  }
  
  ```

- #### Publish new blog

  ```shell
  POST /username/publish/articles
  
  data 
  {
  	"title":"",
  	"content":"",
  	"private": true/false,
  	"description":""
  }
  
  curl -u -i -d '{"title":"xxx","content":"xxx","private":false,"description":"xxx"}'https://api.example.com/username/articles
  
  ```

  Response:

  ```json
  {
   	"articleID": 1,
   	"title":"title1",
   	"href":"https://api.example.com/username/articles/1",
   	"private": false,
   	"description": "...",
   	"created_at": "2018-01-01T00:31:50Z",
   	"updated_at": "2018-01-01T00:31:50Z",
   	"action":"POST",
   	"status":"original"
   	"words": 1234,
   	"visits": 0，
   	"content":"article contents...."
  }
  ```

- #### Delete some blog 

  ```shell
  DELETE /username/articles/articleID
  curl -u -i https://api.example.com/username/articles/1
  
  DELETE /username/articles/articleTitle
  curl -u -i https://api.example.com/username/articles/test
  ```

  Response:

  ```json
  {
       "isDeleted":true / false,
       "title":"test",
       "id" : 1
  }
  ```

- #### Add a comment

  ```shell
  POST /username/articles/articleID/comment
  curl -u -i https://api.example.com/username/articles/1
  
  POST /username/articles/articleTitle/comment
  curl -u -i https://api.example.com/username/articles/test
  
  data 
  {
  	"content":"xxx"
  }
  ```

  Response:

  ```json
  {
  	"id": 1,
  	"author": "username",
  	"href": "https://api.example.com/username/articles/1",
  	items:[{
         		"contents":xxx,
         		"user": {
            		"name":"user2"
            		"href": "xxx",
           		},
         		"created_at": "2018-01-01T00:31:50Z"
       		}
  	]	
  }
  
  ```

  