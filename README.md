# Flask-Restful-blueprint
Splitting up API library into multiple files 

Struct of project:

```
├── app.py
└── api
    ├── __init__.py
    ├── HelloWorld.py
```


Call Restful method from `HelloWorld`

Get all message:
```html
$ curl http://127.0.0.1:5002/api/helloworld
{
    "1": "Hello",
    "2": "Thanks",
    "3": "Goodbye",
    "4": "Please"
}

```

Get single message:
```html
$ curl http://127.0.0.1:5002/api/helloworld/1
"Hello"

```

Delete a message:
```html
$ curl http://127.0.0.1:5002/api/helloworld/2 -X DELETE -v
*   Trying 127.0.0.1...
* TCP_NODELAY set
* Connected to 127.0.0.1 (127.0.0.1) port 5002 (#0)
> DELETE /api/helloworld/2 HTTP/1.1
> Host: 127.0.0.1:5002
> User-Agent: curl/7.54.0
> Accept: */*
> 
* HTTP 1.0, assume close after body
< HTTP/1.0 204 NO CONTENT
< Content-Type: application/json
< Content-Length: 9
< Server: Werkzeug/0.14.1 Python/3.6.4
< Date: Sun, 14 Jan 2018 17:27:14 GMT
< 
* Closing connection 0


$ curl http://127.0.0.1:5002/api/helloworld
{
    "1": "Hello",
    "3": "Goodbye",
    "4": "Please"
}

```

....