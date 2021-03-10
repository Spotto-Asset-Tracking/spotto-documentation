---
title: Spotto-API v0.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: [mqtt]
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="spotto-api">Spotto-API v0.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

<h1 id="spotto-api-users">Users</h1>

## CurrentUser

<a id="opIdCurrentUser"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /users/current \
  -H 'Accept: application/json'

```

```http
GET /users/current HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/users/current',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/users/current',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/users/current', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/users/current', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/users/current");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/users/current", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users/current`

> Example responses

> 200 Response

```json
{
  "id": "string",
  "email": "string",
  "name": "string",
  "role": {
    "permissions": [
      "string"
    ],
    "id": "string",
    "name": "string"
  },
  "organisation": {
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="currentuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[CurrentUserResponse](#schemacurrentuserresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## DeleteUser

<a id="opIdDeleteUser"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /users/{id} \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
DELETE /users/{id} HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/users/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.delete '/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.delete('/users/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/users/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/users/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /users/{id}`

<h3 id="deleteuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{}
```

<h3 id="deleteuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[DeleteResponse](#schemadeleteresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetUser

<a id="opIdGetUser"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /users/{id} \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /users/{id} HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/users/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/users/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/users/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/users/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users/{id}`

<h3 id="getuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|withKey|query|boolean|false|If you have the API admin permissions you can view the API key|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**withKey**: If you have the API admin permissions you can view the API key
of external users.

> Example responses

> 200 Response

```json
{
  "type": "EXTERNAL",
  "key": "string",
  "id": "string",
  "name": "string",
  "role": {
    "id": "string",
    "name": "string"
  },
  "organisation": {
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="getuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetUserResponse](#schemagetuserresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## UpdateUser

<a id="opIdUpdateUser"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /users/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
PATCH /users/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "name": "string",
  "role": "string",
  "organisation": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/users/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.patch '/users/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.patch('/users/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/users/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/users/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /users/{id}`

> Body parameter

```json
{
  "name": "string",
  "role": "string",
  "organisation": "string"
}
```

<h3 id="updateuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[UpdateUserRequest](#schemaupdateuserrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "type": "EXTERNAL",
  "key": "string",
  "id": "string",
  "name": "string",
  "role": {
    "id": "string",
    "name": "string"
  },
  "organisation": {
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="updateuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetUserResponse](#schemagetuserresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetKey

<a id="opIdGetKey"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /users/{id}/key \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /users/{id}/key HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/users/{id}/key',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/users/{id}/key',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/users/{id}/key', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/users/{id}/key', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/users/{id}/key");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/users/{id}/key", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users/{id}/key`

<h3 id="getkey-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "key": "string"
}
```

<h3 id="getkey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetKeyResponse](#schemagetkeyresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetUsers

<a id="opIdGetUsers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /users \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /users HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/users',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/users', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users`

<h3 id="getusers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|embed|query|array[string]|false|Attach additional user information:|
|ids|query|array[string]|false|Lookup specific users by passing an array of valid Spotto IDs.|
|limit|query|number(float)|false|**Pagination:** Max number of results to return in the request. The default is 20.|
|page|query|number(float)|false|**Pagination:** What page of results, assuming the limit (defaulting to 20)|
|role|query|array[string]|false|Lookup users belonging to specific roles by passing an array of valid Spotto IDs.|
|sort|query|[StandardSortFields](#schemastandardsortfields)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|
|type|query|[UserType](#schemausertype)|false|Lookup only internal or external API users|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**embed**: Attach additional user information:

**meta** attaches basic CRUD status information.

**page**: **Pagination:** What page of results, assuming the limit (defaulting to 20)
to start from. The default is page 0 (the first page of results).

e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|meta|
|sort|name|
|sort|updated|
|sort|created|
|sortOrder|asc|
|sortOrder|desc|
|type|INTERNAL|
|type|EXTERNAL|

> Example responses

> 200 Response

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "role": [
      "string"
    ],
    "type": "INTERNAL",
    "sort": "name",
    "sortOrder": "asc",
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "type": "EXTERNAL",
      "key": "string",
      "id": "string",
      "name": "string",
      "role": {
        "id": "string",
        "name": "string"
      },
      "organisation": {
        "id": "string",
        "name": "string"
      },
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}
```

<h3 id="getusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetUsersResponse](#schemagetusersresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PostUser

<a id="opIdPostUser"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /users \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /users HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "type": "EXTERNAL",
  "name": "string",
  "role": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/users',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/users', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /users`

> Body parameter

```json
{
  "type": "EXTERNAL",
  "name": "string",
  "role": "string"
}
```

<h3 id="postuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[PostUserRequest](#schemapostuserrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "type": "EXTERNAL",
  "key": "string",
  "id": "string",
  "name": "string",
  "role": {
    "id": "string",
    "name": "string"
  },
  "organisation": {
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="postuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetUserResponse](#schemagetuserresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-organisations">Organisations</h1>

## DeleteOrganisation

<a id="opIdDeleteOrganisation"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /organisations/{id}?name=string \
  -H 'Accept: application/json'

```

```http
DELETE /organisations/{id}?name=string HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/organisations/{id}?name=string',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete '/organisations/{id}',
  params: {
  'name' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/organisations/{id}', params={
  'name': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/organisations/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations/{id}?name=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/organisations/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /organisations/{id}`

<h3 id="deleteorganisation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|name|query|string|true|Validates that you're deleting the correct account|

> Example responses

> 200 Response

```json
{
  "success": true,
  "deleted": {
    "assets": 0,
    "locations": 0,
    "readers": 0,
    "events": 0,
    "users": 0
  }
}
```

<h3 id="deleteorganisation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[DeleteOrganisationResponse](#schemadeleteorganisationresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetOrganisation

<a id="opIdGetOrganisation"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /organisations/{id} \
  -H 'Accept: application/json'

```

```http
GET /organisations/{id} HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/organisations/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/organisations/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/organisations/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/organisations/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/organisations/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /organisations/{id}`

<h3 id="getorganisation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "preferences": {
    "tags": {
      "ble": true,
      "rfid": true
    },
    "readers": {
      "type": {
        "default": "FIXED",
        "enabled": [
          "FIXED"
        ]
      },
      "manufacturer": {
        "default": "ZEBRA",
        "enabled": [
          "ZEBRA"
        ]
      }
    }
  },
  "integrations": {
    "mqtt": {
      "enabled": true,
      "username": "string"
    }
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="getorganisation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetOrganisationResponse](#schemagetorganisationresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## UpdateOrganisation

<a id="opIdUpdateOrganisation"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /organisations/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH /organisations/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "string",
  "networks": [
    {
      "deleteNetwork": true,
      "name": "string",
      "username": "string",
      "password": "string"
    }
  ],
  "preferences": {
    "tags": {
      "ble": true,
      "rfid": true
    },
    "readers": {
      "type": {
        "default": "FIXED",
        "enabled": [
          "FIXED"
        ]
      },
      "manufacturer": {
        "default": "ZEBRA",
        "enabled": [
          "ZEBRA"
        ]
      }
    }
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/organisations/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.patch '/organisations/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/organisations/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/organisations/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/organisations/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /organisations/{id}`

> Body parameter

```json
{
  "name": "string",
  "networks": [
    {
      "deleteNetwork": true,
      "name": "string",
      "username": "string",
      "password": "string"
    }
  ],
  "preferences": {
    "tags": {
      "ble": true,
      "rfid": true
    },
    "readers": {
      "type": {
        "default": "FIXED",
        "enabled": [
          "FIXED"
        ]
      },
      "manufacturer": {
        "default": "ZEBRA",
        "enabled": [
          "ZEBRA"
        ]
      }
    }
  }
}
```

<h3 id="updateorganisation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|body|body|[UpdateOrganisationRequest](#schemaupdateorganisationrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "preferences": {
    "tags": {
      "ble": true,
      "rfid": true
    },
    "readers": {
      "type": {
        "default": "FIXED",
        "enabled": [
          "FIXED"
        ]
      },
      "manufacturer": {
        "default": "ZEBRA",
        "enabled": [
          "ZEBRA"
        ]
      }
    }
  },
  "integrations": {
    "mqtt": {
      "enabled": true,
      "username": "string"
    }
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="updateorganisation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetOrganisationResponse](#schemagetorganisationresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetNetworks

<a id="opIdGetNetworks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /organisations/{id}/wifi \
  -H 'Accept: application/json'

```

```http
GET /organisations/{id}/wifi HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/organisations/{id}/wifi',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/organisations/{id}/wifi',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/organisations/{id}/wifi', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/organisations/{id}/wifi', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations/{id}/wifi");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/organisations/{id}/wifi", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /organisations/{id}/wifi`

<h3 id="getnetworks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|search|query|string|false|none|

> Example responses

> 200 Response

```json
{
  "networks": [
    "string"
  ]
}
```

<h3 id="getnetworks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetNetworksResponse](#schemagetnetworksresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetOrganisations

<a id="opIdGetOrganisations"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /organisations \
  -H 'Accept: application/json'

```

```http
GET /organisations HTTP/1.1

Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('/organisations',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/organisations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/organisations', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/organisations', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/organisations", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /organisations`

<h3 id="getorganisations-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|embed|query|array[string]|false|Attach additional user information:|
|ids|query|array[string]|false|Lookup specific organisations by passing an array of valid Spotto IDs.|
|limit|query|number(float)|false|**Pagination:** Max number of results to return in the request. The default is 20.|
|names|query|array[string]|false|Lookup specific organisations by passing an array of names.|
|page|query|number(float)|false|**Pagination:** What page of results, assuming the limit (defaulting to 20)|
|sort|query|[StandardSortFields](#schemastandardsortfields)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|

#### Detailed descriptions

**embed**: Attach additional user information:

**meta** attaches basic CRUD status information.

**page**: **Pagination:** What page of results, assuming the limit (defaulting to 20)
to start from. The default is page 0 (the first page of results).

e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|meta|
|sort|name|
|sort|updated|
|sort|created|
|sortOrder|asc|
|sortOrder|desc|

> Example responses

> 200 Response

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "names": [
      "string"
    ],
    "sort": "name",
    "sortOrder": "asc",
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "preferences": {
        "tags": {
          "ble": true,
          "rfid": true
        },
        "readers": {
          "type": {
            "default": "FIXED",
            "enabled": [
              "FIXED"
            ]
          },
          "manufacturer": {
            "default": "ZEBRA",
            "enabled": [
              "ZEBRA"
            ]
          }
        }
      },
      "integrations": {
        "mqtt": {
          "enabled": true,
          "username": "string"
        }
      },
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}
```

<h3 id="getorganisations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetOrganisationsResponse](#schemagetorganisationsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PostOrganisation

<a id="opIdPostOrganisation"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /organisations \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /organisations HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('/organisations',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '/organisations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/organisations', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/organisations', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/organisations", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /organisations`

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="postorganisation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PostOrganisationRequest](#schemapostorganisationrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "preferences": {
    "tags": {
      "ble": true,
      "rfid": true
    },
    "readers": {
      "type": {
        "default": "FIXED",
        "enabled": [
          "FIXED"
        ]
      },
      "manufacturer": {
        "default": "ZEBRA",
        "enabled": [
          "ZEBRA"
        ]
      }
    }
  },
  "integrations": {
    "mqtt": {
      "enabled": true,
      "username": "string"
    }
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="postorganisation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetOrganisationResponse](#schemagetorganisationresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-triggers">Triggers</h1>

## DeleteTrigger

<a id="opIdDeleteTrigger"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE /triggers/{id} \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
DELETE /triggers/{id} HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/triggers/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.delete '/triggers/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.delete('/triggers/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/triggers/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/triggers/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/triggers/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /triggers/{id}`

<h3 id="deletetrigger-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{}
```

<h3 id="deletetrigger-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[DeleteResponse](#schemadeleteresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetTrigger

<a id="opIdGetTrigger"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /triggers/{id} \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /triggers/{id} HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/triggers/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/triggers/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/triggers/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/triggers/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/triggers/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/triggers/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /triggers/{id}`

<h3 id="gettrigger-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "type": "ArrivedAt",
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "id": "string",
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="gettrigger-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetTriggerResponse](#schemagettriggerresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## UpdateTrigger

<a id="opIdUpdateTrigger"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /triggers/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
PATCH /triggers/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/triggers/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.patch '/triggers/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.patch('/triggers/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/triggers/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/triggers/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/triggers/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /triggers/{id}`

> Body parameter

```json
{
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ]
}
```

<h3 id="updatetrigger-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[UpdateTriggerRequest](#schemaupdatetriggerrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "type": "ArrivedAt",
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "id": "string",
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="updatetrigger-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetTriggerResponse](#schemagettriggerresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetTriggers

<a id="opIdGetTriggers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /triggers \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /triggers HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/triggers',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/triggers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/triggers', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/triggers', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/triggers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/triggers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /triggers`

<h3 id="gettriggers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|embed|query|array[string]|false|Attach additional trigger information:|
|enabled|query|boolean|false|Lookup triggers that are only enabled or disabled.|
|ids|query|array[string]|false|Lookup specific triggers by passing an array of valid Spotto IDs.|
|limit|query|number(float)|false|**Pagination:** Max number of results to return in the request. The default is 20.|
|page|query|number(float)|false|**Pagination:** What page of results, assuming the limit (defaulting to 20)|
|sort|query|[StandardSortFields](#schemastandardsortfields)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|
|type|query|[TriggerType](#schematriggertype)|false|Filter based on the trigger type|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**embed**: Attach additional trigger information:

**meta** attaches basic CRUD status information.

**page**: **Pagination:** What page of results, assuming the limit (defaulting to 20)
to start from. The default is page 0 (the first page of results).

e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|meta|
|sort|name|
|sort|updated|
|sort|created|
|sortOrder|asc|
|sortOrder|desc|
|type|ArrivedAt|
|type|Moved|
|type|WentOnline|
|type|WentOffline|

> Example responses

> 200 Response

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "enabled": true,
    "type": "ArrivedAt",
    "sort": "name",
    "sortOrder": "asc",
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "type": "ArrivedAt",
      "locationRules": [
        {
          "type": "MatchName",
          "match": "string"
        }
      ],
      "id": "string",
      "name": "string",
      "enabled": true,
      "actions": [
        {
          "type": "Webhook",
          "endpoint": "string"
        }
      ],
      "subjectRules": [
        {
          "type": "MatchName",
          "match": "string"
        }
      ],
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}
```

<h3 id="gettriggers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetTriggersResponse](#schemagettriggersresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PostTriggers

<a id="opIdPostTriggers"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /triggers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /triggers HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '[
  {
    "type": "ArrivedAt",
    "locationRules": [
      {
        "type": "MatchName",
        "match": "string"
      }
    ],
    "name": "string",
    "actions": [
      {
        "type": "Webhook",
        "endpoint": "string"
      }
    ],
    "subjectRules": [
      {
        "type": "MatchName",
        "match": "string"
      }
    ]
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/triggers',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/triggers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/triggers', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/triggers', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/triggers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/triggers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /triggers`

> Body parameter

```json
[
  {
    "type": "ArrivedAt",
    "locationRules": [
      {
        "type": "MatchName",
        "match": "string"
      }
    ],
    "name": "string",
    "actions": [
      {
        "type": "Webhook",
        "endpoint": "string"
      }
    ],
    "subjectRules": [
      {
        "type": "MatchName",
        "match": "string"
      }
    ]
  }
]
```

<h3 id="posttriggers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[PostTriggersRequest](#schemaposttriggersrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "inserted": 0,
  "items": [
    {
      "type": "ArrivedAt",
      "locationRules": [
        {
          "type": "MatchName",
          "match": "string"
        }
      ],
      "id": "string",
      "name": "string",
      "enabled": true,
      "actions": [
        {
          "type": "Webhook",
          "endpoint": "string"
        }
      ],
      "subjectRules": [
        {
          "type": "MatchName",
          "match": "string"
        }
      ],
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}
```

<h3 id="posttriggers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[PostTriggersResponse](#schemaposttriggersresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-events">Events</h1>

## DownloadEvents

<a id="opIdDownloadEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /events/download \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /events/download HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/events/download',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/events/download',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/events/download', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/events/download', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/events/download");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/events/download", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /events/download`

<h3 id="downloadevents-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|assets|query|array[string]|false|Lookup events for specific assets by passing an array of valid Spotto IDs.|
|embed|query|array[string]|false|Attach additional event information:|
|limit|query|number(float)|false|Max number of rows to include in the CSV. The default and maximum is 50, 000.|
|locations|query|array[string]|false|Lookup events for specific locations by passing an array of valid Spotto IDs.|
|readers|query|array[string]|false|Lookup events for specific readers by passing an array of valid Spotto IDs.|
|sort|query|[EventSortField](#schemaeventsortfield)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|
|timeFrom|query|number(float)|false|Filter events from a given timestamp. It will yield events up until the|
|timeTo|query|number(float)|false|Filter events until a given timestamp. It will yield all events prior to the specified time,|
|timestampFormat|query|[TimestampFormat](#schematimestampformat)|false|Control the timestamp format printed to the CSV, the default is a|
|type|query|array[string]|false|Lookup events for specific event types, e.g. only show Reader Online/Offline events.|
|withEntityLinks|query|boolean|false|Replace entity IDs with the Spotto URL to easily access assets, locations and readers|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**embed**: Attach additional event information:

**asset** attaches the asset name to items with an asset ID<br>
**location** attaches the location name to items with an location ID<br>
**reader** attaches the reader name to items with an reader ID

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

**timeFrom**: Filter events from a given timestamp. It will yield events up until the
current server time, unless otherwise specified by *timeTo*.

**timeTo**: Filter events until a given timestamp. It will yield all events prior to the specified time,
unless otherwise specified by *timeFrom*

**timestampFormat**: Control the timestamp format printed to the CSV, the default is a
Unix Epoch timestamp:

**epoch** Unix numeric format representing the total Milliseconds since Epoch<br>
**iso** ISO 8601 string format "YYYY-MM-DDTHH:mm:ss.sssZ"

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|asset|
|embed|location|
|embed|reader|
|sort|timestamp|
|sort|asset|
|sort|location|
|sort|reader|
|sortOrder|asc|
|sortOrder|desc|
|timestampFormat|epoch|
|timestampFormat|iso|
|type|ReaderArrived|
|type|ReaderExited|
|type|Arrived|
|type|ExplicitArrived|
|type|Exited|
|type|ReaderOnline|
|type|ReaderOffline|

> Example responses

> 200 Response

```json
{
  "path": "string"
}
```

<h3 id="downloadevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[DownloadEventsResponse](#schemadownloadeventsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetEvents

<a id="opIdGetEvents"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /events \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /events HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/events', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/events', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/events");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /events`

<h3 id="getevents-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|assets|query|array[string]|false|Lookup events for specific assets by passing an array of valid Spotto IDs.|
|embed|query|array[string]|false|Attach additional event information:|
|limit|query|number(float)|false|*Pagination:** Max number of results to return in the request. The default is 20.|
|locations|query|array[string]|false|Lookup events for specific locations by passing an array of valid Spotto IDs.|
|page|query|number(float)|false|**Pagination:** What page of results, assuming the limit (defaulting to 20)|
|readers|query|array[string]|false|Lookup events for specific readers by passing an array of valid Spotto IDs.|
|sort|query|[EventSortField](#schemaeventsortfield)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|
|timeFrom|query|number(float)|false|Filter events from a given timestamp. It will yield events up until the|
|timeTo|query|number(float)|false|Filter events until a given timestamp. It will yield all events prior to the specified time,|
|type|query|array[string]|false|Lookup events for specific event types, e.g. only show Reader Online/Offline events.|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**embed**: Attach additional event information:

**asset** attaches the asset name to items with an asset ID<br>
**location** attaches the location name to items with an location ID<br>
**reader** attaches the reader name to items with an reader ID

**page**: **Pagination:** What page of results, assuming the limit (defaulting to 20)
to start from. The default is page 0 (the first page of results).

e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

**timeFrom**: Filter events from a given timestamp. It will yield events up until the
current server time, unless otherwise specified by *timeTo*.

**timeTo**: Filter events until a given timestamp. It will yield all events prior to the specified time,
unless otherwise specified by *timeFrom*

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|asset|
|embed|location|
|embed|reader|
|sort|timestamp|
|sort|asset|
|sort|location|
|sort|reader|
|sortOrder|asc|
|sortOrder|desc|
|type|ReaderArrived|
|type|ReaderExited|
|type|Arrived|
|type|ExplicitArrived|
|type|Exited|
|type|ReaderOnline|
|type|ReaderOffline|

> Example responses

> 200 Response

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "readers": [
      "string"
    ],
    "locations": [
      "string"
    ],
    "assets": [
      "string"
    ],
    "type": [
      "ReaderArrived"
    ],
    "timeFrom": 0,
    "timeTo": 0,
    "sort": "timestamp",
    "sortOrder": "asc",
    "embed": [
      "asset"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "timestamp": 0,
      "type": "ReaderArrived",
      "asset": "string",
      "location": "string",
      "reader": "string"
    }
  ]
}
```

<h3 id="getevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetEventsResponse](#schemageteventsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-assets">Assets</h1>

## GetAsset

<a id="opIdGetAsset"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /assets/{id} \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /assets/{id} HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/assets/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/assets/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/assets/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/assets/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/assets/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/assets/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /assets/{id}`

<h3 id="getasset-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "tagIds": [
    "string"
  ],
  "score": 0,
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  },
  "lastLocation": {
    "firstSeen": 0,
    "lastSeen": 0,
    "id": "string",
    "name": "string"
  }
}
```

<h3 id="getasset-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetAssetResponse](#schemagetassetresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## UpdateAsset

<a id="opIdUpdateAsset"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /assets/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
PATCH /assets/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "name": "string",
  "archived": true,
  "tagIds": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/assets/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.patch '/assets/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.patch('/assets/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/assets/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/assets/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/assets/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /assets/{id}`

> Body parameter

```json
{
  "name": "string",
  "archived": true,
  "tagIds": [
    "string"
  ]
}
```

<h3 id="updateasset-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[UpdateAssetRequest](#schemaupdateassetrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "tagIds": [
    "string"
  ],
  "score": 0,
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  },
  "lastLocation": {
    "firstSeen": 0,
    "lastSeen": 0,
    "id": "string",
    "name": "string"
  }
}
```

<h3 id="updateasset-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetAssetResponse](#schemagetassetresponse)|
|default|Default|default response|[UpdateAssetErrorResponse](#schemaupdateasseterrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## GetAssetLastLocation

<a id="opIdGetAssetLastLocation"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /assets/{id}/location \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /assets/{id}/location HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/assets/{id}/location',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/assets/{id}/location',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/assets/{id}/location', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/assets/{id}/location', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/assets/{id}/location");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/assets/{id}/location", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /assets/{id}/location`

<h3 id="getassetlastlocation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "lastLocation": {
    "firstSeen": 0,
    "lastSeen": 0,
    "id": "string",
    "name": "string"
  }
}
```

<h3 id="getassetlastlocation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetAssetLastLocationResponse](#schemagetassetlastlocationresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetAssetSuggestions

<a id="opIdGetAssetSuggestions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /assets/suggestions?search=string \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /assets/suggestions?search=string HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/assets/suggestions?search=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/assets/suggestions',
  params: {
  'search' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/assets/suggestions', params={
  'search': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/assets/suggestions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/assets/suggestions?search=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/assets/suggestions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /assets/suggestions`

<h3 id="getassetsuggestions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|true|Search query string|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "query": {
    "search": "string"
  },
  "suggestions": [
    "string"
  ],
  "matches": [
    {
      "id": "string",
      "name": "string"
    }
  ]
}
```

<h3 id="getassetsuggestions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetAssetSuggestionsResponse](#schemagetassetsuggestionsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetAssets

<a id="opIdGetAssets"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /assets \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /assets HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/assets',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/assets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/assets', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/assets', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/assets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/assets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /assets`

<h3 id="getassets-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|archived|query|boolean|false|Return deleted assets, the default is false.|
|embed|query|array[string]|false|Attach additional asset information:|
|hasTags|query|boolean|false|Only return assets that have tags registered.|
|ids|query|array[string]|false|Lookup specific assets by passing an array of valid Spotto IDs.|
|limit|query|number(float)|false|**Pagination:** Max number of results to return in the request. The default is 20.|
|page|query|number(float)|false|**Pagination:** What page of results, assuming the limit (defaulting to 20)|
|search|query|string|false|Search query string, for lucene based full text search.|
|searchFields|query|array[string]|false|Reduce the scope of fields to perform the search on.|
|searchFuzzy|query|boolean|false|Whether or not to run the search in *fuzzy* mode. The level of fuzziness|
|sort|query|[SearchableSortFields](#schemasearchablesortfields)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|
|tagIds|query|array[string]|false|Lookup assets with specific tag IDs e.g. Beacon MAC addresses and RFID EPC codes.|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**embed**: Attach additional asset information:

**meta** attaches basic CRUD status information.<br>
**tags** attaches the tag IDs attached to this asset.<br>
**lastLocation** attaches the last known time and location the asset was seen.

**page**: **Pagination:** What page of results, assuming the limit (defaulting to 20)
to start from. The default is page 0 (the first page of results).

e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).

**searchFields**: Reduce the scope of fields to perform the search on.
When left blank it will search all of these fields.

**searchFuzzy**: Whether or not to run the search in *fuzzy* mode. The level of fuzziness
depends on the character length of search terms:

1-2: Must match exactly<br>
3-5: Off by at most 1 character<br>
6+: Off by at most 2 characters

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|meta|
|embed|tagIds|
|embed|lastLocation|
|searchFields|name|
|searchFields|tagIds|
|sortOrder|asc|
|sortOrder|desc|

> Example responses

> 200 Response

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "tagIds": [
      "string"
    ],
    "hasTags": true,
    "archived": true,
    "sort": "name",
    "sortOrder": "asc",
    "search": "string",
    "searchFuzzy": true,
    "searchFields": [
      "name"
    ],
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "score": 0,
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "lastLocation": {
        "firstSeen": 0,
        "lastSeen": 0,
        "id": "string",
        "name": "string"
      }
    }
  ]
}
```

<h3 id="getassets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetAssetsResponse](#schemagetassetsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PostAssets

<a id="opIdPostAssets"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /assets \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /assets HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '[
  {
    "name": "string",
    "tagIds": [
      "string"
    ]
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/assets',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/assets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/assets', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/assets', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/assets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/assets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /assets`

> Body parameter

```json
[
  {
    "name": "string",
    "tagIds": [
      "string"
    ]
  }
]
```

<h3 id="postassets-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[PostAssetsRequest](#schemapostassetsrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "inserted": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "score": 0,
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "lastLocation": {
        "firstSeen": 0,
        "lastSeen": 0,
        "id": "string",
        "name": "string"
      }
    }
  ]
}
```

<h3 id="postassets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[PostAssetsResponse](#schemapostassetsresponse)|
|default|Default|default response|[PostAssetsErrorResponse](#schemapostassetserrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## UploadAssets

<a id="opIdUploadAssets"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /assets/upload \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /assets/upload HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "data": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/assets/upload',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/assets/upload',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/assets/upload', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/assets/upload', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/assets/upload");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/assets/upload", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /assets/upload`

> Body parameter

```json
{
  "data": "string"
}
```

<h3 id="uploadassets-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[UploadAssetsRequest](#schemauploadassetsrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "inserted": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "score": 0,
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "lastLocation": {
        "firstSeen": 0,
        "lastSeen": 0,
        "id": "string",
        "name": "string"
      }
    }
  ]
}
```

<h3 id="uploadassets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[PostAssetsResponse](#schemapostassetsresponse)|
|default|Default|default response|[UploadAssetsErrorResponse](#schemauploadassetserrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-levels">Levels</h1>

## GetLevels

<a id="opIdGetLevels"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /organisations/levels \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /organisations/levels HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/organisations/levels',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/organisations/levels',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/organisations/levels', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/organisations/levels', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations/levels");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/organisations/levels", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /organisations/levels`

<h3 id="getlevels-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "levels": [
    "string"
  ]
}
```

<h3 id="getlevels-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetLevelsResponse](#schemagetlevelsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PostLevel

<a id="opIdPostLevel"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /organisations/levels \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /organisations/levels HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "level": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/organisations/levels',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/organisations/levels',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/organisations/levels', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/organisations/levels', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations/levels");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/organisations/levels", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /organisations/levels`

> Body parameter

```json
{
  "level": "string"
}
```

<h3 id="postlevel-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[PostLevelRequest](#schemapostlevelrequest)|true|none|

> Example responses

> 201 Response

```json
{}
```

<h3 id="postlevel-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|201 response|[PostLevelResponse](#schemapostlevelresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PutLevels

<a id="opIdPutLevels"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /organisations/levels \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
PUT /organisations/levels HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "levels": [
    "string"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/organisations/levels',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.put '/organisations/levels',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.put('/organisations/levels', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/organisations/levels', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/organisations/levels");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/organisations/levels", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /organisations/levels`

> Body parameter

```json
{
  "levels": [
    "string"
  ]
}
```

<h3 id="putlevels-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[PutLevelsRequest](#schemaputlevelsrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "levels": [
    "string"
  ]
}
```

<h3 id="putlevels-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[PutLevelsResponse](#schemaputlevelsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-locations">Locations</h1>

## GetLocation

<a id="opIdGetLocation"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /locations/{id} \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /locations/{id} HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/locations/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/locations/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/locations/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/locations/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/locations/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/locations/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /locations/{id}`

<h3 id="getlocation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "tagIds": [
    "string"
  ],
  "readers": [
    {
      "id": "string",
      "name": "string"
    }
  ],
  "level": "string",
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="getlocation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetLocationResponse](#schemagetlocationresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## UpdateLocation

<a id="opIdUpdateLocation"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /locations/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
PATCH /locations/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "name": "string",
  "level": "string",
  "tagIds": [
    "string"
  ],
  "archived": true,
  "address": "string",
  "geoLocation": "GeoJSON"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/locations/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.patch '/locations/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.patch('/locations/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/locations/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/locations/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/locations/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /locations/{id}`

> Body parameter

```json
{
  "name": "string",
  "level": "string",
  "tagIds": [
    "string"
  ],
  "archived": true,
  "address": "string",
  "geoLocation": "GeoJSON"
}
```

<h3 id="updatelocation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[UpdateLocationRequest](#schemaupdatelocationrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "tagIds": [
    "string"
  ],
  "readers": [
    {
      "id": "string",
      "name": "string"
    }
  ],
  "level": "string",
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}
```

<h3 id="updatelocation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetLocationResponse](#schemagetlocationresponse)|
|default|Default|default response|[UpdateLocationErrorResponse](#schemaupdatelocationerrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

## GetLocationInventory

<a id="opIdGetLocationInventory"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /locations/{id}/inventory \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /locations/{id}/inventory HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/locations/{id}/inventory',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/locations/{id}/inventory',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/locations/{id}/inventory', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/locations/{id}/inventory', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/locations/{id}/inventory");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/locations/{id}/inventory", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /locations/{id}/inventory`

<h3 id="getlocationinventory-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "firstSeen": 0,
    "lastSeen": 0
  }
]
```

<h3 id="getlocationinventory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetLocationInventoryResponse](#schemagetlocationinventoryresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetLocationSuggestions

<a id="opIdGetLocationSuggestions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /locations/suggestions?search=string \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /locations/suggestions?search=string HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/locations/suggestions?search=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/locations/suggestions',
  params: {
  'search' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/locations/suggestions', params={
  'search': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/locations/suggestions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/locations/suggestions?search=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/locations/suggestions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /locations/suggestions`

<h3 id="getlocationsuggestions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|true|Search query string|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "query": {
    "search": "string"
  },
  "suggestions": [
    "string"
  ],
  "matches": [
    {
      "id": "string",
      "name": "string"
    }
  ]
}
```

<h3 id="getlocationsuggestions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetLocationSuggestionsResponse](#schemagetlocationsuggestionsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetLocations

<a id="opIdGetLocations"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /locations \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /locations HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/locations',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/locations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/locations', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/locations', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/locations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/locations", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /locations`

<h3 id="getlocations-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|archived|query|boolean|false|Return deleted locations, the default is false|
|embed|query|array[string]|false|Attach additional location information:|
|hasReaders|query|boolean|false|Only return locations that have readers attached.|
|hasTags|query|boolean|false|Only return locations that have tags registered.|
|ids|query|array[string]|false|Lookup specific locations by passing an array of valid Spotto IDs.|
|levels|query|array[string]|false|Lookup locations at specific floor levels, e.g. Ground and Level 1 ONLY.|
|limit|query|number(float)|false|*Pagination:** Max number of results to return in the request. The default is 20.|
|page|query|number(float)|false|**Pagination:** What page of results, assuming the limit (defaulting to 20)|
|search|query|string|false|Search query string, for lucene based full text search.|
|searchFields|query|array[string]|false|Reduce the scope of fields to perform the search on.|
|searchFuzzy|query|boolean|false|Whether or not to run the search in *fuzzy* mode. The level of fuzziness|
|sort|query|[SearchableSortFields](#schemasearchablesortfields)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|
|tagIds|query|array[string]|false|Lookup locations with specific tag IDs e.g. Beacon MAC addresses and RFID EPC codes.|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**embed**: Attach additional location information:

**meta** attaches basic CRUD status information.<br>
**tags** attaches the tag IDs attached to this location.<br>
**readers** attaches any readers configured at the given location.

**page**: **Pagination:** What page of results, assuming the limit (defaulting to 20)
to start from. The default is page 0 (the first page of results).

e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).

**searchFields**: Reduce the scope of fields to perform the search on.
When left blank it will search all of these fields.

**searchFuzzy**: Whether or not to run the search in *fuzzy* mode. The level of fuzziness
depends on the character length of search terms:

1-2: Must match exactly<br>
3-5: Off by at most 1 character<br>
6+: Off by at most 2 characters

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|meta|
|embed|tagIds|
|embed|readers|
|searchFields|name|
|sortOrder|asc|
|sortOrder|desc|

> Example responses

> 200 Response

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "tagIds": [
      "string"
    ],
    "levels": [
      "string"
    ],
    "hasTags": true,
    "hasReaders": true,
    "archived": true,
    "sort": "name",
    "sortOrder": "asc",
    "search": "string",
    "searchFuzzy": true,
    "searchFields": [
      "name"
    ],
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "readers": [
        {
          "id": "string",
          "name": "string"
        }
      ],
      "level": "string",
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}
```

<h3 id="getlocations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetLocationsResponse](#schemagetlocationsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PostLocations

<a id="opIdPostLocations"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /locations \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /locations HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '[
  {
    "name": "string",
    "level": "string",
    "tagIds": [
      "string"
    ],
    "address": "string",
    "geoLocation": "GeoJSON"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/locations',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/locations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/locations', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/locations', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/locations");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/locations", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /locations`

> Body parameter

```json
[
  {
    "name": "string",
    "level": "string",
    "tagIds": [
      "string"
    ],
    "address": "string",
    "geoLocation": "GeoJSON"
  }
]
```

<h3 id="postlocations-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[PostLocationsRequest](#schemapostlocationsrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "inserted": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "readers": [
        {
          "id": "string",
          "name": "string"
        }
      ],
      "level": "string",
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}
```

<h3 id="postlocations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[PostLocationsResponse](#schemapostlocationsresponse)|
|default|Default|default response|[PostLocationsErrorResponse](#schemapostlocationserrorresponse)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-mqtt">MQTT</h1>

## GetMQTTSettings

<a id="opIdGetMQTTSettings"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /integrations/mqtt \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /integrations/mqtt HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/integrations/mqtt',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/integrations/mqtt',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/integrations/mqtt', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/integrations/mqtt', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/integrations/mqtt");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/integrations/mqtt", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /integrations/mqtt`

<h3 id="getmqttsettings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "password": "string",
  "path": "string",
  "enabled": true,
  "username": "string"
}
```

<h3 id="getmqttsettings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[MQTTSettings](#schemamqttsettings)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## UpdateMQTTSettings

<a id="opIdUpdateMQTTSettings"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /integrations/mqtt \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /integrations/mqtt HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "enabled": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/integrations/mqtt',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/integrations/mqtt',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/integrations/mqtt', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/integrations/mqtt', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/integrations/mqtt");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/integrations/mqtt", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /integrations/mqtt`

> Body parameter

```json
{
  "enabled": true
}
```

<h3 id="updatemqttsettings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[UpdateMQTTSettingsRequest](#schemaupdatemqttsettingsrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "password": "string",
  "path": "string",
  "enabled": true,
  "username": "string"
}
```

<h3 id="updatemqttsettings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[MQTTSettings](#schemamqttsettings)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-readers">Readers</h1>

## GetReader

<a id="opIdGetReader"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /readers/{id} \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /readers/{id} HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/readers/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/readers/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/readers/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/readers/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/readers/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/readers/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /readers/{id}`

<h3 id="getreader-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "type": "FIXED",
  "manufacturer": "ZEBRA",
  "deviceId": "string",
  "endpoint": "string",
  "network": "string",
  "location": {
    "type": "FIXED",
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  },
  "status": {
    "online": true,
    "onlineTime": 0,
    "lastReportedTime": 0
  }
}
```

<h3 id="getreader-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetReaderResponse](#schemagetreaderresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## UpdateReader

<a id="opIdUpdateReader"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH /readers/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
PATCH /readers/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "name": "string",
  "type": "FIXED",
  "archived": true,
  "locationId": "string",
  "location": {
    "name": "string",
    "level": "string"
  },
  "deviceId": "string",
  "network": {
    "name": "string",
    "username": "string",
    "password": "string"
  },
  "saveNetwork": true,
  "antennas": [
    {
      "name": "string",
      "port": 0,
      "locationId": "string",
      "location": {
        "name": "string",
        "level": "string"
      }
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/readers/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.patch '/readers/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.patch('/readers/{id}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/readers/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/readers/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "/readers/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /readers/{id}`

> Body parameter

```json
{
  "name": "string",
  "type": "FIXED",
  "archived": true,
  "locationId": "string",
  "location": {
    "name": "string",
    "level": "string"
  },
  "deviceId": "string",
  "network": {
    "name": "string",
    "username": "string",
    "password": "string"
  },
  "saveNetwork": true,
  "antennas": [
    {
      "name": "string",
      "port": 0,
      "locationId": "string",
      "location": {
        "name": "string",
        "level": "string"
      }
    }
  ]
}
```

<h3 id="updatereader-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[UpdateReaderRequest](#schemaupdatereaderrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "type": "FIXED",
  "manufacturer": "ZEBRA",
  "deviceId": "string",
  "endpoint": "string",
  "network": "string",
  "location": {
    "type": "FIXED",
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  },
  "status": {
    "online": true,
    "onlineTime": 0,
    "lastReportedTime": 0
  }
}
```

<h3 id="updatereader-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetReaderResponse](#schemagetreaderresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetReaderForUser

<a id="opIdGetReaderForUser"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /readers/user \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /readers/user HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "deviceId": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/readers/user',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/readers/user',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/readers/user', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/readers/user', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/readers/user");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/readers/user", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /readers/user`

> Body parameter

```json
{
  "deviceId": "string"
}
```

<h3 id="getreaderforuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[GetReaderForUserRequest](#schemagetreaderforuserrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "endpoint": "string",
  "isNewReader": true,
  "deviceId": "string",
  "user": "string"
}
```

<h3 id="getreaderforuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetReaderForUserResponse](#schemagetreaderforuserresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetReaderInventory

<a id="opIdGetReaderInventory"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /readers/{id}/inventory \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /readers/{id}/inventory HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/readers/{id}/inventory',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/readers/{id}/inventory',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/readers/{id}/inventory', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/readers/{id}/inventory', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/readers/{id}/inventory");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/readers/{id}/inventory", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /readers/{id}/inventory`

<h3 id="getreaderinventory-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|windowSize|query|number(float)|false|Time in seconds to consider assets to be within the readers inventory|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "firstSeen": 0,
    "lastSeen": 0
  }
]
```

<h3 id="getreaderinventory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetReaderInventoryResponse](#schemagetreaderinventoryresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetReaderStatus

<a id="opIdGetReaderStatus"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /readers/{id}/status \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /readers/{id}/status HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/readers/{id}/status',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/readers/{id}/status',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/readers/{id}/status', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/readers/{id}/status', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/readers/{id}/status");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/readers/{id}/status", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /readers/{id}/status`

<h3 id="getreaderstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|Spotto ID|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "location": {
    "type": "ROVING",
    "firstSeen": 0,
    "lastSeen": 0,
    "id": "string",
    "name": "string"
  },
  "status": {
    "online": true,
    "onlineTime": 0,
    "lastReportedTime": 0
  }
}
```

<h3 id="getreaderstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetReaderStatusResponse](#schemagetreaderstatusresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetReaderSuggestions

<a id="opIdGetReaderSuggestions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /readers/suggestions?search=string \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /readers/suggestions?search=string HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/readers/suggestions?search=string',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/readers/suggestions',
  params: {
  'search' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/readers/suggestions', params={
  'search': 'string'
}, headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/readers/suggestions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/readers/suggestions?search=string");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/readers/suggestions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /readers/suggestions`

<h3 id="getreadersuggestions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|true|Search query string|
|x-organisation|header|string|false|Organisation Spotto ID|

> Example responses

> 200 Response

```json
{
  "query": {
    "search": "string"
  },
  "suggestions": [
    "string"
  ],
  "matches": [
    {
      "id": "string",
      "name": "string"
    }
  ]
}
```

<h3 id="getreadersuggestions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetReaderSuggestionsResponse](#schemagetreadersuggestionsresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## GetReaders

<a id="opIdGetReaders"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /readers \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /readers HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/readers',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/readers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/readers', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/readers', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/readers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/readers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /readers`

<h3 id="getreaders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|archived|query|boolean|false|Return deleted readers, the default is false.|
|deviceIds|query|array[string]|false|Lookup specific readers by passing an array of device IDs.|
|embed|query|array[string]|false|Attach additional reader information:|
|ids|query|array[string]|false|Lookup specific readers by passing an array of valid Spotto IDs.|
|limit|query|number(float)|false|*Pagination:** Max number of results to return in the request. The default is 20.|
|manufacturer|query|[Manufacturer](#schemamanufacturer)|false|Lookup readers belonging to a specific manufacturer.|
|page|query|number(float)|false|**Pagination:** What page of results, assuming the limit (defaulting to 20)|
|search|query|string|false|Search query string, for Lucene based full text search.|
|searchFields|query|array[string]|false|Reduce the scope of fields to perform the search on.|
|searchFuzzy|query|boolean|false|Whether or not to run the search in *fuzzy* mode. The level of fuzziness|
|sort|query|[SearchableSortFields](#schemasearchablesortfields)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|
|type|query|[ReaderType](#schemareadertype)|false|Filter based on the reader behavioural type.|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**deviceIds**: Lookup specific readers by passing an array of device IDs.
These are typically the MAC address of the reader.

**embed**: Attach additional reader information:

**meta** attaches basic CRUD status information.<br>
**status** attaches dynamic status information about the reader such as
the time it came online and when we last heard from it.

**page**: **Pagination:** What page of results, assuming the limit (defaulting to 20)
to start from. The default is page 0 (the first page of results).

e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).

**searchFields**: Reduce the scope of fields to perform the search on.
When left blank it will search all of these fields.

**searchFuzzy**: Whether or not to run the search in *fuzzy* mode. The level of fuzziness
depends on the character length of search terms:

1-2: Must match exactly<br>
3-5: Off by at most 1 character<br>
6+: Off by at most 2 characters

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|meta|
|embed|status|
|manufacturer|ZEBRA|
|manufacturer|ZEBRA_IOT_BRIDGE|
|manufacturer|IMPINJ|
|manufacturer|BLUECATS|
|manufacturer|TURCK|
|manufacturer|THING_MAGIC|
|manufacturer|IOTX3|
|manufacturer|OTHER|
|manufacturer|DETECT_APP|
|searchFields|name|
|searchFields|deviceId|
|sortOrder|asc|
|sortOrder|desc|
|type|FIXED|
|type|ROVING|
|type|VIRTUAL|
|type|PORTAL|

> Example responses

> 200 Response

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "deviceIds": [
      "string"
    ],
    "type": "FIXED",
    "manufacturer": "ZEBRA",
    "archived": true,
    "sort": "name",
    "sortOrder": "asc",
    "search": "string",
    "searchFuzzy": true,
    "searchFields": [
      "name"
    ],
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "type": "FIXED",
      "manufacturer": "ZEBRA",
      "deviceId": "string",
      "endpoint": "string",
      "network": "string",
      "location": {
        "type": "FIXED",
        "id": "string",
        "name": "string"
      },
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "status": {
        "online": true,
        "onlineTime": 0,
        "lastReportedTime": 0
      }
    }
  ]
}
```

<h3 id="getreaders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetReadersResponse](#schemagetreadersresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PostReaders

<a id="opIdPostReaders"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /readers \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /readers HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '[
  {
    "name": "string",
    "manufacturer": "ZEBRA",
    "type": "FIXED",
    "locationId": "string",
    "location": {
      "name": "string",
      "level": "string"
    },
    "deviceId": "string",
    "network": {
      "name": "string",
      "username": "string",
      "password": "string"
    },
    "saveNetwork": true,
    "antennas": [
      {
        "name": "string",
        "port": 0,
        "locationId": "string",
        "location": {
          "name": "string",
          "level": "string"
        }
      }
    ]
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/readers',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/readers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/readers', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/readers', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/readers");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/readers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /readers`

> Body parameter

```json
[
  {
    "name": "string",
    "manufacturer": "ZEBRA",
    "type": "FIXED",
    "locationId": "string",
    "location": {
      "name": "string",
      "level": "string"
    },
    "deviceId": "string",
    "network": {
      "name": "string",
      "username": "string",
      "password": "string"
    },
    "saveNetwork": true,
    "antennas": [
      {
        "name": "string",
        "port": 0,
        "locationId": "string",
        "location": {
          "name": "string",
          "level": "string"
        }
      }
    ]
  }
]
```

<h3 id="postreaders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[PostReadersRequest](#schemapostreadersrequest)|true|none|

> Example responses

> 200 Response

```json
{
  "inserted": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "type": "FIXED",
      "manufacturer": "ZEBRA",
      "deviceId": "string",
      "endpoint": "string",
      "network": "string",
      "location": {
        "type": "FIXED",
        "id": "string",
        "name": "string"
      },
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "status": {
        "online": true,
        "onlineTime": 0,
        "lastReportedTime": 0
      }
    }
  ]
}
```

<h3 id="postreaders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[PostReadersResponse](#schemapostreadersresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="spotto-api-roles">Roles</h1>

## GetRoles

<a id="opIdGetRoles"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /roles \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
GET /roles HTTP/1.1

Accept: application/json
x-organisation: string

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/roles',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.get '/roles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.get('/roles', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/roles', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/roles");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/roles", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /roles`

<h3 id="getroles-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|embed|query|array[string]|false|Attach additional user information:|
|sort|query|[StandardSortFields](#schemastandardsortfields)|false|**Sorting:** Which field the results are to be sorted by.|
|sortOrder|query|[SortOrders](#schemasortorders)|false|**Sorting:** Whether to sort the results in ascending or descending order.|
|x-organisation|header|string|false|Organisation Spotto ID|

#### Detailed descriptions

**embed**: Attach additional user information:

**meta** attaches basic CRUD status information.

**sort**: **Sorting:** Which field the results are to be sorted by.
Use in combination with *sortOrder*, the default is ascending.

**sortOrder**: **Sorting:** Whether to sort the results in ascending or descending order.
Use in combination with *sort* to determine the field this is acting on.

#### Enumerated Values

|Parameter|Value|
|---|---|
|embed|meta|
|sort|name|
|sort|updated|
|sort|created|
|sortOrder|asc|
|sortOrder|desc|

> Example responses

> 200 Response

```json
{
  "query": {
    "sort": "name",
    "sortOrder": "asc",
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "name": "string",
      "description": "string",
      "permissions": [
        "string"
      ],
      "default": true
    }
  ]
}
```

<h3 id="getroles-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetRolesResponse](#schemagetrolesresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

## PostRole

<a id="opIdPostRole"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /roles \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-organisation: string'

```

```http
POST /roles HTTP/1.1

Content-Type: application/json
Accept: application/json
x-organisation: string

```

```javascript
const inputBody = '{
  "name": "string",
  "description": "string",
  "permissions": [
    "string"
  ],
  "default": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-organisation':'string'
};

fetch('/roles',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-organisation' => 'string'
}

result = RestClient.post '/roles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-organisation': 'string'
}

r = requests.post('/roles', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-organisation' => 'string',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/roles', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("/roles");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        "x-organisation": []string{"string"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/roles", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /roles`

> Body parameter

```json
{
  "name": "string",
  "description": "string",
  "permissions": [
    "string"
  ],
  "default": true
}
```

<h3 id="postrole-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|x-organisation|header|string|false|Organisation Spotto ID|
|body|body|[PostRoleRequest](#schemapostrolerequest)|true|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  },
  "name": "string",
  "description": "string",
  "permissions": [
    "string"
  ],
  "default": true
}
```

<h3 id="postrole-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|200 response|[GetRoleResponse](#schemagetroleresponse)|
|default|Default|default response|[DefaultError](#schemadefaulterror)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Action">Action</h2>
<!-- backwards compatibility -->
<a id="schemaaction"></a>
<a id="schema_Action"></a>
<a id="tocSaction"></a>
<a id="tocsaction"></a>

```json
{
  "type": "Webhook",
  "endpoint": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[WebhookAction](#schemawebhookaction)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[MQTTAction](#schemamqttaction)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[EmailAction](#schemaemailaction)|false|none|none|

<h2 id="tocS_AssetEmbedField">AssetEmbedField</h2>
<!-- backwards compatibility -->
<a id="schemaassetembedfield"></a>
<a id="schema_AssetEmbedField"></a>
<a id="tocSassetembedfield"></a>
<a id="tocsassetembedfield"></a>

```json
"meta"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|meta|
|*anonymous*|tagIds|
|*anonymous*|lastLocation|

<h2 id="tocS_AssetSearchField">AssetSearchField</h2>
<!-- backwards compatibility -->
<a id="schemaassetsearchfield"></a>
<a id="schema_AssetSearchField"></a>
<a id="tocSassetsearchfield"></a>
<a id="tocsassetsearchfield"></a>

```json
"name"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|name|
|*anonymous*|tagIds|

<h2 id="tocS_CurrentUserResponse">CurrentUserResponse</h2>
<!-- backwards compatibility -->
<a id="schemacurrentuserresponse"></a>
<a id="schema_CurrentUserResponse"></a>
<a id="tocScurrentuserresponse"></a>
<a id="tocscurrentuserresponse"></a>

```json
{
  "id": "string",
  "email": "string",
  "name": "string",
  "role": {
    "permissions": [
      "string"
    ],
    "id": "string",
    "name": "string"
  },
  "organisation": {
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

Identical to GetUserResponse, with the addition of permissions

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique Spotto ID assigned to this User|
|email|string|true|none|The User's unique email address|
|name|string|true|none|The User's full name NOTE: We do not enforce unique names|
|role|[EmbeddedRole](#schemaembeddedrole)|true|none|none|
|organisation|[IEmbeddedEntity](#schemaiembeddedentity)|true|none|none|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

<h2 id="tocS_DefaultError">DefaultError</h2>
<!-- backwards compatibility -->
<a id="schemadefaulterror"></a>
<a id="schema_DefaultError"></a>
<a id="tocSdefaulterror"></a>
<a id="tocsdefaulterror"></a>

```json
{
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|true|none|none|

<h2 id="tocS_DeleteOrganisationResponse">DeleteOrganisationResponse</h2>
<!-- backwards compatibility -->
<a id="schemadeleteorganisationresponse"></a>
<a id="schema_DeleteOrganisationResponse"></a>
<a id="tocSdeleteorganisationresponse"></a>
<a id="tocsdeleteorganisationresponse"></a>

```json
{
  "success": true,
  "deleted": {
    "assets": 0,
    "locations": 0,
    "readers": 0,
    "events": 0,
    "users": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|boolean|true|none|none|
|deleted|[DeletedCounts](#schemadeletedcounts)|true|none|none|

<h2 id="tocS_DeleteResponse">DeleteResponse</h2>
<!-- backwards compatibility -->
<a id="schemadeleteresponse"></a>
<a id="schema_DeleteResponse"></a>
<a id="tocSdeleteresponse"></a>
<a id="tocsdeleteresponse"></a>

```json
{}

```

Standard deletion response is an empty object

### Properties

*None*

<h2 id="tocS_DeletedCounts">DeletedCounts</h2>
<!-- backwards compatibility -->
<a id="schemadeletedcounts"></a>
<a id="schema_DeletedCounts"></a>
<a id="tocSdeletedcounts"></a>
<a id="tocsdeletedcounts"></a>

```json
{
  "assets": 0,
  "locations": 0,
  "readers": 0,
  "events": 0,
  "users": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|assets|number(float)|false|none|none|
|locations|number(float)|false|none|none|
|readers|number(float)|false|none|none|
|events|number(float)|false|none|none|
|users|number(float)|false|none|none|

<h2 id="tocS_DownloadEventsResponse">DownloadEventsResponse</h2>
<!-- backwards compatibility -->
<a id="schemadownloadeventsresponse"></a>
<a id="schema_DownloadEventsResponse"></a>
<a id="tocSdownloadeventsresponse"></a>
<a id="tocsdownloadeventsresponse"></a>

```json
{
  "path": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|path|string|true|none|temporary URL to access the CSV download, expires after 1 minute|

<h2 id="tocS_EmailAction">EmailAction</h2>
<!-- backwards compatibility -->
<a id="schemaemailaction"></a>
<a id="schema_EmailAction"></a>
<a id="tocSemailaction"></a>
<a id="tocsemailaction"></a>

```json
{
  "type": "Email",
  "address": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|address|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|Email|

<h2 id="tocS_EmbeddedRole">EmbeddedRole</h2>
<!-- backwards compatibility -->
<a id="schemaembeddedrole"></a>
<a id="schema_EmbeddedRole"></a>
<a id="tocSembeddedrole"></a>
<a id="tocsembeddedrole"></a>

```json
{
  "permissions": [
    "string"
  ],
  "id": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|permissions|[string]|true|none|none|
|id|string|true|none|Unique ID of the embedded entity|
|name|string|true|none|Name of the embedded entity|

<h2 id="tocS_EventEmbedField">EventEmbedField</h2>
<!-- backwards compatibility -->
<a id="schemaeventembedfield"></a>
<a id="schema_EventEmbedField"></a>
<a id="tocSeventembedfield"></a>
<a id="tocseventembedfield"></a>

```json
"asset"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|asset|
|*anonymous*|location|
|*anonymous*|reader|

<h2 id="tocS_EventSortField">EventSortField</h2>
<!-- backwards compatibility -->
<a id="schemaeventsortfield"></a>
<a id="schema_EventSortField"></a>
<a id="tocSeventsortfield"></a>
<a id="tocseventsortfield"></a>

```json
"timestamp"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|timestamp|
|*anonymous*|asset|
|*anonymous*|location|
|*anonymous*|reader|

<h2 id="tocS_EventType">EventType</h2>
<!-- backwards compatibility -->
<a id="schemaeventtype"></a>
<a id="schema_EventType"></a>
<a id="tocSeventtype"></a>
<a id="tocseventtype"></a>

```json
"ReaderArrived"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|ReaderArrived|
|*anonymous*|ReaderExited|
|*anonymous*|Arrived|
|*anonymous*|ExplicitArrived|
|*anonymous*|Exited|
|*anonymous*|ReaderOnline|
|*anonymous*|ReaderOffline|

<h2 id="tocS_GetArrivedAtTriggerResponse">GetArrivedAtTriggerResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetarrivedattriggerresponse"></a>
<a id="schema_GetArrivedAtTriggerResponse"></a>
<a id="tocSgetarrivedattriggerresponse"></a>
<a id="tocsgetarrivedattriggerresponse"></a>

```json
{
  "type": "ArrivedAt",
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "id": "string",
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

Asset or Reader moved in relation to selected locations

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|locationRules|[[Rule](#schemarule)]|true|none|Location rules filter the possible events that cause this<br>trigger to fire.|
|id|string|true|none|Unique ID of this Trigger|
|name|string|true|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|enabled|boolean|true|none|Status of the trigger, disabled triggers will not fire|
|actions|[[Action](#schemaaction)]|true|none|The list of actions that fire for this trigger|
|subjectRules|[[Rule](#schemarule)]|true|none|Subject rules filter the possible events that cause this<br>trigger to fire.|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|ArrivedAt|

<h2 id="tocS_GetAssetLastLocationResponse">GetAssetLastLocationResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetassetlastlocationresponse"></a>
<a id="schema_GetAssetLastLocationResponse"></a>
<a id="tocSgetassetlastlocationresponse"></a>
<a id="tocsgetassetlastlocationresponse"></a>

```json
{
  "id": "string",
  "lastLocation": {
    "firstSeen": 0,
    "lastSeen": 0,
    "id": "string",
    "name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique ID of this Asset|
|lastLocation|[ILastLocation](#schemailastlocation)|true|none|none|

<h2 id="tocS_GetAssetResponse">GetAssetResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetassetresponse"></a>
<a id="schema_GetAssetResponse"></a>
<a id="tocSgetassetresponse"></a>
<a id="tocsgetassetresponse"></a>

```json
{
  "id": "string",
  "name": "string",
  "tagIds": [
    "string"
  ],
  "score": 0,
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  },
  "lastLocation": {
    "firstSeen": 0,
    "lastSeen": 0,
    "id": "string",
    "name": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique ID of this Asset|
|name|string|true|none|Asset name NOTE: We do not enforce unique names|
|tagIds|[string]|false|none|List of Tag IDs|
|score|number(float)|false|none|Lucene search score, added as an optional meta field when searching|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|
|lastLocation|[ILastLocation](#schemailastlocation)|false|none|none|

<h2 id="tocS_GetAssetSuggestionsQuery">GetAssetSuggestionsQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetassetsuggestionsquery"></a>
<a id="schema_GetAssetSuggestionsQuery"></a>
<a id="tocSgetassetsuggestionsquery"></a>
<a id="tocsgetassetsuggestionsquery"></a>

```json
{
  "search": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|search|string|true|none|Search query string|

<h2 id="tocS_GetAssetSuggestionsResponse">GetAssetSuggestionsResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetassetsuggestionsresponse"></a>
<a id="schema_GetAssetSuggestionsResponse"></a>
<a id="tocSgetassetsuggestionsresponse"></a>
<a id="tocsgetassetsuggestionsresponse"></a>

```json
{
  "query": {
    "search": "string"
  },
  "suggestions": [
    "string"
  ],
  "matches": [
    {
      "id": "string",
      "name": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetAssetSuggestionsQuery](#schemagetassetsuggestionsquery)|true|none|none|
|suggestions|[string]|true|none|none|
|matches|[[IEmbeddedEntity](#schemaiembeddedentity)]|true|none|none|

<h2 id="tocS_GetAssetsQuery">GetAssetsQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetassetsquery"></a>
<a id="schema_GetAssetsQuery"></a>
<a id="tocSgetassetsquery"></a>
<a id="tocsgetassetsquery"></a>

```json
{
  "page": 0,
  "limit": 0,
  "ids": [
    "string"
  ],
  "tagIds": [
    "string"
  ],
  "hasTags": true,
  "archived": true,
  "sort": "name",
  "sortOrder": "asc",
  "search": "string",
  "searchFuzzy": true,
  "searchFields": [
    "name"
  ],
  "embed": [
    "meta"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|page|number(float)|false|none|**Pagination:** What page of results, assuming the limit (defaulting to 20)<br>to start from. The default is page 0 (the first page of results).<br><br>e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).|
|limit|number(float)|false|none|**Pagination:** Max number of results to return in the request. The default is 20.|
|ids|[string]|false|none|Lookup specific assets by passing an array of valid Spotto IDs.|
|tagIds|[string]|false|none|Lookup assets with specific tag IDs e.g. Beacon MAC addresses and RFID EPC codes.|
|hasTags|boolean|false|none|Only return assets that have tags registered.|
|archived|boolean|false|none|Return deleted assets, the default is false.|
|sort|[SearchableSortFields](#schemasearchablesortfields)|false|none|none|
|sortOrder|[SortOrders](#schemasortorders)|false|none|Sort orders - ascending and descending|
|search|string|false|none|Search query string, for lucene based full text search.|
|searchFuzzy|boolean|false|none|Whether or not to run the search in *fuzzy* mode. The level of fuzziness<br>depends on the character length of search terms:<br><br>1-2: Must match exactly<br><br>3-5: Off by at most 1 character<br><br>6+: Off by at most 2 characters|
|searchFields|[[AssetSearchField](#schemaassetsearchfield)]|false|none|Reduce the scope of fields to perform the search on.<br>When left blank it will search all of these fields.|
|embed|[[AssetEmbedField](#schemaassetembedfield)]|false|none|Attach additional asset information:<br><br>**meta** attaches basic CRUD status information.<br><br>**tags** attaches the tag IDs attached to this asset.<br><br>**lastLocation** attaches the last known time and location the asset was seen.|

<h2 id="tocS_GetAssetsResponse">GetAssetsResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetassetsresponse"></a>
<a id="schema_GetAssetsResponse"></a>
<a id="tocSgetassetsresponse"></a>
<a id="tocsgetassetsresponse"></a>

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "tagIds": [
      "string"
    ],
    "hasTags": true,
    "archived": true,
    "sort": "name",
    "sortOrder": "asc",
    "search": "string",
    "searchFuzzy": true,
    "searchFields": [
      "name"
    ],
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "score": 0,
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "lastLocation": {
        "firstSeen": 0,
        "lastSeen": 0,
        "id": "string",
        "name": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetAssetsQuery](#schemagetassetsquery)|true|none|none|
|total|number(float)|true|none|Total number of records that match the query (without pagination)|
|items|[[GetAssetResponse](#schemagetassetresponse)]|true|none|This is the list of paginated results, which will be an array of 20 items<br>or less, unless another limit was specified in the query params|

<h2 id="tocS_GetEventResponse">GetEventResponse</h2>
<!-- backwards compatibility -->
<a id="schemageteventresponse"></a>
<a id="schema_GetEventResponse"></a>
<a id="tocSgeteventresponse"></a>
<a id="tocsgeteventresponse"></a>

```json
{
  "id": "string",
  "timestamp": 0,
  "type": "ReaderArrived",
  "asset": "string",
  "location": "string",
  "reader": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique ID of this Event|
|timestamp|number(float)|true|none|Numeric timestamp the event was recorded at|
|type|[EventType](#schemaeventtype)|true|none|none|
|asset|any|false|none|Asset ID if relevant to the type of event|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[IEmbeddedEntity](#schemaiembeddedentity)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|location|any|false|none|Location ID if relevant to the type of event|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[IEmbeddedEntity](#schemaiembeddedentity)|false|none|none|

continued

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reader|any|false|none|Reader ID if relevant to the type of event|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|string|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[IEmbeddedEntity](#schemaiembeddedentity)|false|none|none|

<h2 id="tocS_GetEventsQuery">GetEventsQuery</h2>
<!-- backwards compatibility -->
<a id="schemageteventsquery"></a>
<a id="schema_GetEventsQuery"></a>
<a id="tocSgeteventsquery"></a>
<a id="tocsgeteventsquery"></a>

```json
{
  "page": 0,
  "limit": 0,
  "readers": [
    "string"
  ],
  "locations": [
    "string"
  ],
  "assets": [
    "string"
  ],
  "type": [
    "ReaderArrived"
  ],
  "timeFrom": 0,
  "timeTo": 0,
  "sort": "timestamp",
  "sortOrder": "asc",
  "embed": [
    "asset"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|page|number(float)|false|none|**Pagination:** What page of results, assuming the limit (defaulting to 20)<br>to start from. The default is page 0 (the first page of results).<br><br>e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).|
|limit|number(float)|false|none|*Pagination:** Max number of results to return in the request. The default is 20.|
|readers|[string]|false|none|Lookup events for specific readers by passing an array of valid Spotto IDs.|
|locations|[string]|false|none|Lookup events for specific locations by passing an array of valid Spotto IDs.|
|assets|[string]|false|none|Lookup events for specific assets by passing an array of valid Spotto IDs.|
|type|[[EventType](#schemaeventtype)]|false|none|Lookup events for specific event types, e.g. only show Reader Online/Offline events.|
|timeFrom|number(float)|false|none|Filter events from a given timestamp. It will yield events up until the<br>current server time, unless otherwise specified by *timeTo*.|
|timeTo|number(float)|false|none|Filter events until a given timestamp. It will yield all events prior to the specified time,<br>unless otherwise specified by *timeFrom*|
|sort|[EventSortField](#schemaeventsortfield)|false|none|none|
|sortOrder|[SortOrders](#schemasortorders)|false|none|Sort orders - ascending and descending|
|embed|[[EventEmbedField](#schemaeventembedfield)]|false|none|Attach additional event information:<br><br>**asset** attaches the asset name to items with an asset ID<br><br>**location** attaches the location name to items with an location ID<br><br>**reader** attaches the reader name to items with an reader ID|

<h2 id="tocS_GetEventsResponse">GetEventsResponse</h2>
<!-- backwards compatibility -->
<a id="schemageteventsresponse"></a>
<a id="schema_GetEventsResponse"></a>
<a id="tocSgeteventsresponse"></a>
<a id="tocsgeteventsresponse"></a>

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "readers": [
      "string"
    ],
    "locations": [
      "string"
    ],
    "assets": [
      "string"
    ],
    "type": [
      "ReaderArrived"
    ],
    "timeFrom": 0,
    "timeTo": 0,
    "sort": "timestamp",
    "sortOrder": "asc",
    "embed": [
      "asset"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "timestamp": 0,
      "type": "ReaderArrived",
      "asset": "string",
      "location": "string",
      "reader": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetEventsQuery](#schemageteventsquery)|true|none|none|
|total|number(float)|true|none|Total number of records that match the query (without pagination)|
|items|[[GetEventResponse](#schemageteventresponse)]|true|none|This is the list of paginated results, which will be an array of 20 items<br>or less, unless another limit was specified in the query params|

<h2 id="tocS_GetExternalUserResponse">GetExternalUserResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetexternaluserresponse"></a>
<a id="schema_GetExternalUserResponse"></a>
<a id="tocSgetexternaluserresponse"></a>
<a id="tocsgetexternaluserresponse"></a>

```json
{
  "type": "EXTERNAL",
  "key": "string",
  "id": "string",
  "name": "string",
  "role": {
    "id": "string",
    "name": "string"
  },
  "organisation": {
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|User type for identifying external API users from internal users|
|key|string|false|none|The API key is returned when creating new External users, or where requested|
|id|string|true|none|Unique Spotto ID assigned to this User|
|name|string|true|none|The User's full name NOTE: We do not enforce unique names|
|role|[IEmbeddedEntity](#schemaiembeddedentity)|true|none|none|
|organisation|[IEmbeddedEntity](#schemaiembeddedentity)|true|none|none|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|EXTERNAL|

<h2 id="tocS_GetInternalUserResponse">GetInternalUserResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetinternaluserresponse"></a>
<a id="schema_GetInternalUserResponse"></a>
<a id="tocSgetinternaluserresponse"></a>
<a id="tocsgetinternaluserresponse"></a>

```json
{
  "type": "INTERNAL",
  "email": "string",
  "id": "string",
  "name": "string",
  "role": {
    "id": "string",
    "name": "string"
  },
  "organisation": {
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|User type for identifying internal users from external API users|
|email|string|true|none|The User's unique email address|
|id|string|true|none|Unique Spotto ID assigned to this User|
|name|string|true|none|The User's full name NOTE: We do not enforce unique names|
|role|[IEmbeddedEntity](#schemaiembeddedentity)|true|none|none|
|organisation|[IEmbeddedEntity](#schemaiembeddedentity)|true|none|none|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|INTERNAL|

<h2 id="tocS_GetKeyResponse">GetKeyResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetkeyresponse"></a>
<a id="schema_GetKeyResponse"></a>
<a id="tocSgetkeyresponse"></a>
<a id="tocsgetkeyresponse"></a>

```json
{
  "key": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|key|string|true|none|none|

<h2 id="tocS_GetLevelsResponse">GetLevelsResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetlevelsresponse"></a>
<a id="schema_GetLevelsResponse"></a>
<a id="tocSgetlevelsresponse"></a>
<a id="tocsgetlevelsresponse"></a>

```json
{
  "levels": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|levels|[string]|true|none|none|

<h2 id="tocS_GetLocationInventoryResponse">GetLocationInventoryResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetlocationinventoryresponse"></a>
<a id="schema_GetLocationInventoryResponse"></a>
<a id="tocSgetlocationinventoryresponse"></a>
<a id="tocsgetlocationinventoryresponse"></a>

```json
[
  {
    "id": "string",
    "name": "string",
    "firstSeen": 0,
    "lastSeen": 0
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[IInventoryItem](#schemaiinventoryitem)]|false|none|none|

<h2 id="tocS_GetLocationResponse">GetLocationResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetlocationresponse"></a>
<a id="schema_GetLocationResponse"></a>
<a id="tocSgetlocationresponse"></a>
<a id="tocsgetlocationresponse"></a>

```json
{
  "id": "string",
  "name": "string",
  "tagIds": [
    "string"
  ],
  "readers": [
    {
      "id": "string",
      "name": "string"
    }
  ],
  "level": "string",
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique ID of this Location|
|name|string|true|none|Location name NOTE: We do not enforce unique names|
|tagIds|[string]|false|none|List of Tag IDs|
|readers|[[IEmbeddedEntity](#schemaiembeddedentity)]|false|none|List of readers configured at this location|
|level|string|false|none|Name of the locations floor/level|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

<h2 id="tocS_GetLocationSuggestionsQuery">GetLocationSuggestionsQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetlocationsuggestionsquery"></a>
<a id="schema_GetLocationSuggestionsQuery"></a>
<a id="tocSgetlocationsuggestionsquery"></a>
<a id="tocsgetlocationsuggestionsquery"></a>

```json
{
  "search": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|search|string|true|none|Search query string|

<h2 id="tocS_GetLocationSuggestionsResponse">GetLocationSuggestionsResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetlocationsuggestionsresponse"></a>
<a id="schema_GetLocationSuggestionsResponse"></a>
<a id="tocSgetlocationsuggestionsresponse"></a>
<a id="tocsgetlocationsuggestionsresponse"></a>

```json
{
  "query": {
    "search": "string"
  },
  "suggestions": [
    "string"
  ],
  "matches": [
    {
      "id": "string",
      "name": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetLocationSuggestionsQuery](#schemagetlocationsuggestionsquery)|true|none|none|
|suggestions|[string]|true|none|none|
|matches|[[IEmbeddedEntity](#schemaiembeddedentity)]|true|none|none|

<h2 id="tocS_GetLocationsQuery">GetLocationsQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetlocationsquery"></a>
<a id="schema_GetLocationsQuery"></a>
<a id="tocSgetlocationsquery"></a>
<a id="tocsgetlocationsquery"></a>

```json
{
  "page": 0,
  "limit": 0,
  "ids": [
    "string"
  ],
  "tagIds": [
    "string"
  ],
  "levels": [
    "string"
  ],
  "hasTags": true,
  "hasReaders": true,
  "archived": true,
  "sort": "name",
  "sortOrder": "asc",
  "search": "string",
  "searchFuzzy": true,
  "searchFields": [
    "name"
  ],
  "embed": [
    "meta"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|page|number(float)|false|none|**Pagination:** What page of results, assuming the limit (defaulting to 20)<br>to start from. The default is page 0 (the first page of results).<br><br>e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).|
|limit|number(float)|false|none|*Pagination:** Max number of results to return in the request. The default is 20.|
|ids|[string]|false|none|Lookup specific locations by passing an array of valid Spotto IDs.|
|tagIds|[string]|false|none|Lookup locations with specific tag IDs e.g. Beacon MAC addresses and RFID EPC codes.|
|levels|[string]|false|none|Lookup locations at specific floor levels, e.g. Ground and Level 1 ONLY.|
|hasTags|boolean|false|none|Only return locations that have tags registered.|
|hasReaders|boolean|false|none|Only return locations that have readers attached.|
|archived|boolean|false|none|Return deleted locations, the default is false|
|sort|[SearchableSortFields](#schemasearchablesortfields)|false|none|none|
|sortOrder|[SortOrders](#schemasortorders)|false|none|Sort orders - ascending and descending|
|search|string|false|none|Search query string, for lucene based full text search.|
|searchFuzzy|boolean|false|none|Whether or not to run the search in *fuzzy* mode. The level of fuzziness<br>depends on the character length of search terms:<br><br>1-2: Must match exactly<br><br>3-5: Off by at most 1 character<br><br>6+: Off by at most 2 characters|
|searchFields|[[LocationSearchField](#schemalocationsearchfield)]|false|none|Reduce the scope of fields to perform the search on.<br>When left blank it will search all of these fields.|
|embed|[[LocationEmbedField](#schemalocationembedfield)]|false|none|Attach additional location information:<br><br>**meta** attaches basic CRUD status information.<br><br>**tags** attaches the tag IDs attached to this location.<br><br>**readers** attaches any readers configured at the given location.|

<h2 id="tocS_GetLocationsResponse">GetLocationsResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetlocationsresponse"></a>
<a id="schema_GetLocationsResponse"></a>
<a id="tocSgetlocationsresponse"></a>
<a id="tocsgetlocationsresponse"></a>

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "tagIds": [
      "string"
    ],
    "levels": [
      "string"
    ],
    "hasTags": true,
    "hasReaders": true,
    "archived": true,
    "sort": "name",
    "sortOrder": "asc",
    "search": "string",
    "searchFuzzy": true,
    "searchFields": [
      "name"
    ],
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "readers": [
        {
          "id": "string",
          "name": "string"
        }
      ],
      "level": "string",
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetLocationsQuery](#schemagetlocationsquery)|true|none|none|
|total|number(float)|true|none|Total number of records that match the query (without pagination)|
|items|[[GetLocationResponse](#schemagetlocationresponse)]|true|none|This is the list of paginated results, which will be an array of 20 items<br>or less, unless another limit was specified in the query params|

<h2 id="tocS_GetMovedTriggerResponse">GetMovedTriggerResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetmovedtriggerresponse"></a>
<a id="schema_GetMovedTriggerResponse"></a>
<a id="tocSgetmovedtriggerresponse"></a>
<a id="tocsgetmovedtriggerresponse"></a>

```json
{
  "type": "Moved",
  "id": "string",
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

Asset or Reader moved anywhere (No location rules)

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|id|string|true|none|Unique ID of this Trigger|
|name|string|true|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|enabled|boolean|true|none|Status of the trigger, disabled triggers will not fire|
|actions|[[Action](#schemaaction)]|true|none|The list of actions that fire for this trigger|
|subjectRules|[[Rule](#schemarule)]|true|none|Subject rules filter the possible events that cause this<br>trigger to fire.|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|Moved|

<h2 id="tocS_GetNetworksResponse">GetNetworksResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetnetworksresponse"></a>
<a id="schema_GetNetworksResponse"></a>
<a id="tocSgetnetworksresponse"></a>
<a id="tocsgetnetworksresponse"></a>

```json
{
  "networks": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|networks|[string]|true|none|none|

<h2 id="tocS_GetOrganisationResponse">GetOrganisationResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetorganisationresponse"></a>
<a id="schema_GetOrganisationResponse"></a>
<a id="tocSgetorganisationresponse"></a>
<a id="tocsgetorganisationresponse"></a>

```json
{
  "id": "string",
  "name": "string",
  "preferences": {
    "tags": {
      "ble": true,
      "rfid": true
    },
    "readers": {
      "type": {
        "default": "FIXED",
        "enabled": [
          "FIXED"
        ]
      },
      "manufacturer": {
        "default": "ZEBRA",
        "enabled": [
          "ZEBRA"
        ]
      }
    }
  },
  "integrations": {
    "mqtt": {
      "enabled": true,
      "username": "string"
    }
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique ID of this Organisation|
|name|string|true|none|Organisation name NOTE: We do not enforce unique names|
|preferences|[Preferences](#schemapreferences)|false|none|none|
|integrations|[Integrations](#schemaintegrations)|false|none|none|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

<h2 id="tocS_GetOrganisationsQuery">GetOrganisationsQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetorganisationsquery"></a>
<a id="schema_GetOrganisationsQuery"></a>
<a id="tocSgetorganisationsquery"></a>
<a id="tocsgetorganisationsquery"></a>

```json
{
  "page": 0,
  "limit": 0,
  "ids": [
    "string"
  ],
  "names": [
    "string"
  ],
  "sort": "name",
  "sortOrder": "asc",
  "embed": [
    "meta"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|page|number(float)|false|none|**Pagination:** What page of results, assuming the limit (defaulting to 20)<br>to start from. The default is page 0 (the first page of results).<br><br>e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).|
|limit|number(float)|false|none|**Pagination:** Max number of results to return in the request. The default is 20.|
|ids|[string]|false|none|Lookup specific organisations by passing an array of valid Spotto IDs.|
|names|[string]|false|none|Lookup specific organisations by passing an array of names.|
|sort|[StandardSortFields](#schemastandardsortfields)|false|none|Common sort fields across most GET endpoints|
|sortOrder|[SortOrders](#schemasortorders)|false|none|Sort orders - ascending and descending|
|embed|[[OrganisationEmbedField](#schemaorganisationembedfield)]|false|none|Attach additional user information:<br><br>**meta** attaches basic CRUD status information.|

<h2 id="tocS_GetOrganisationsResponse">GetOrganisationsResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetorganisationsresponse"></a>
<a id="schema_GetOrganisationsResponse"></a>
<a id="tocSgetorganisationsresponse"></a>
<a id="tocsgetorganisationsresponse"></a>

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "names": [
      "string"
    ],
    "sort": "name",
    "sortOrder": "asc",
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "preferences": {
        "tags": {
          "ble": true,
          "rfid": true
        },
        "readers": {
          "type": {
            "default": "FIXED",
            "enabled": [
              "FIXED"
            ]
          },
          "manufacturer": {
            "default": "ZEBRA",
            "enabled": [
              "ZEBRA"
            ]
          }
        }
      },
      "integrations": {
        "mqtt": {
          "enabled": true,
          "username": "string"
        }
      },
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetOrganisationsQuery](#schemagetorganisationsquery)|true|none|none|
|total|number(float)|true|none|Total number of records that match the query (without pagination)|
|items|[[GetOrganisationResponse](#schemagetorganisationresponse)]|true|none|This is the list of paginated results, which will be an array of 20 items<br>or less, unless another limit was specified in the query params|

<h2 id="tocS_GetReaderForUserRequest">GetReaderForUserRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetreaderforuserrequest"></a>
<a id="schema_GetReaderForUserRequest"></a>
<a id="tocSgetreaderforuserrequest"></a>
<a id="tocsgetreaderforuserrequest"></a>

```json
{
  "deviceId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|deviceId|string|true|none|none|

<h2 id="tocS_GetReaderForUserResponse">GetReaderForUserResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetreaderforuserresponse"></a>
<a id="schema_GetReaderForUserResponse"></a>
<a id="tocSgetreaderforuserresponse"></a>
<a id="tocsgetreaderforuserresponse"></a>

```json
{
  "id": "string",
  "name": "string",
  "endpoint": "string",
  "isNewReader": true,
  "deviceId": "string",
  "user": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|name|string|true|none|none|
|endpoint|string|true|none|none|
|isNewReader|boolean|true|none|none|
|deviceId|string|true|none|none|
|user|string|true|none|none|

<h2 id="tocS_GetReaderInventoryResponse">GetReaderInventoryResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetreaderinventoryresponse"></a>
<a id="schema_GetReaderInventoryResponse"></a>
<a id="tocSgetreaderinventoryresponse"></a>
<a id="tocsgetreaderinventoryresponse"></a>

```json
[
  {
    "id": "string",
    "name": "string",
    "firstSeen": 0,
    "lastSeen": 0
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[IInventoryItem](#schemaiinventoryitem)]|false|none|none|

<h2 id="tocS_GetReaderResponse">GetReaderResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetreaderresponse"></a>
<a id="schema_GetReaderResponse"></a>
<a id="tocSgetreaderresponse"></a>
<a id="tocsgetreaderresponse"></a>

```json
{
  "id": "string",
  "name": "string",
  "type": "FIXED",
  "manufacturer": "ZEBRA",
  "deviceId": "string",
  "endpoint": "string",
  "network": "string",
  "location": {
    "type": "FIXED",
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  },
  "status": {
    "online": true,
    "onlineTime": 0,
    "lastReportedTime": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique ID of this Reader|
|name|string|true|none|Reader name NOTE: We do not enforce unique names|
|type|[ReaderType](#schemareadertype)|true|none|none|
|manufacturer|[Manufacturer](#schemamanufacturer)|true|none|none|
|deviceId|string|false|none|Reader Device ID|
|endpoint|string|true|none|Connector Endpoint|
|network|string|false|none|Name of the network the reader is connected to|
|location|[ReaderLocation](#schemareaderlocation)|false|none|Reader Locations can either be:<br><br>FIXED: Are static and don't have a timestamp<br><br>ROVING: Are dynamic and have a lastSeen timestamp|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|
|status|[IReaderStatus](#schemaireaderstatus)|false|none|Reader online status information.<br><br>TODO: Add other IoT style status information here<br>e.g. Temperature, WiFi signal, Battery level (for portable readers)|

<h2 id="tocS_GetReaderStatusResponse">GetReaderStatusResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetreaderstatusresponse"></a>
<a id="schema_GetReaderStatusResponse"></a>
<a id="tocSgetreaderstatusresponse"></a>
<a id="tocsgetreaderstatusresponse"></a>

```json
{
  "location": {
    "type": "ROVING",
    "firstSeen": 0,
    "lastSeen": 0,
    "id": "string",
    "name": "string"
  },
  "status": {
    "online": true,
    "onlineTime": 0,
    "lastReportedTime": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|location|[IRovingReaderLocation](#schemairovingreaderlocation)|false|none|none|
|status|[IReaderStatus](#schemaireaderstatus)|true|none|Reader online status information.<br><br>TODO: Add other IoT style status information here<br>e.g. Temperature, WiFi signal, Battery level (for portable readers)|

<h2 id="tocS_GetReaderSuggestionsQuery">GetReaderSuggestionsQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetreadersuggestionsquery"></a>
<a id="schema_GetReaderSuggestionsQuery"></a>
<a id="tocSgetreadersuggestionsquery"></a>
<a id="tocsgetreadersuggestionsquery"></a>

```json
{
  "search": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|search|string|true|none|Search query string|

<h2 id="tocS_GetReaderSuggestionsResponse">GetReaderSuggestionsResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetreadersuggestionsresponse"></a>
<a id="schema_GetReaderSuggestionsResponse"></a>
<a id="tocSgetreadersuggestionsresponse"></a>
<a id="tocsgetreadersuggestionsresponse"></a>

```json
{
  "query": {
    "search": "string"
  },
  "suggestions": [
    "string"
  ],
  "matches": [
    {
      "id": "string",
      "name": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetReaderSuggestionsQuery](#schemagetreadersuggestionsquery)|true|none|none|
|suggestions|[string]|true|none|none|
|matches|[[IEmbeddedEntity](#schemaiembeddedentity)]|true|none|none|

<h2 id="tocS_GetReadersQuery">GetReadersQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetreadersquery"></a>
<a id="schema_GetReadersQuery"></a>
<a id="tocSgetreadersquery"></a>
<a id="tocsgetreadersquery"></a>

```json
{
  "page": 0,
  "limit": 0,
  "ids": [
    "string"
  ],
  "deviceIds": [
    "string"
  ],
  "type": "FIXED",
  "manufacturer": "ZEBRA",
  "archived": true,
  "sort": "name",
  "sortOrder": "asc",
  "search": "string",
  "searchFuzzy": true,
  "searchFields": [
    "name"
  ],
  "embed": [
    "meta"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|page|number(float)|false|none|**Pagination:** What page of results, assuming the limit (defaulting to 20)<br>to start from. The default is page 0 (the first page of results).<br><br>e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).|
|limit|number(float)|false|none|*Pagination:** Max number of results to return in the request. The default is 20.|
|ids|[string]|false|none|Lookup specific readers by passing an array of valid Spotto IDs.|
|deviceIds|[string]|false|none|Lookup specific readers by passing an array of device IDs.<br>These are typically the MAC address of the reader.|
|type|[ReaderType](#schemareadertype)|false|none|none|
|manufacturer|[Manufacturer](#schemamanufacturer)|false|none|none|
|archived|boolean|false|none|Return deleted readers, the default is false.|
|sort|[SearchableSortFields](#schemasearchablesortfields)|false|none|none|
|sortOrder|[SortOrders](#schemasortorders)|false|none|Sort orders - ascending and descending|
|search|string|false|none|Search query string, for Lucene based full text search.|
|searchFuzzy|boolean|false|none|Whether or not to run the search in *fuzzy* mode. The level of fuzziness<br>depends on the character length of search terms:<br><br>1-2: Must match exactly<br><br>3-5: Off by at most 1 character<br><br>6+: Off by at most 2 characters|
|searchFields|[[ReaderSearchField](#schemareadersearchfield)]|false|none|Reduce the scope of fields to perform the search on.<br>When left blank it will search all of these fields.|
|embed|[[ReaderEmbedField](#schemareaderembedfield)]|false|none|Attach additional reader information:<br><br>**meta** attaches basic CRUD status information.<br><br>**status** attaches dynamic status information about the reader such as<br>the time it came online and when we last heard from it.|

<h2 id="tocS_GetReadersResponse">GetReadersResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetreadersresponse"></a>
<a id="schema_GetReadersResponse"></a>
<a id="tocSgetreadersresponse"></a>
<a id="tocsgetreadersresponse"></a>

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "deviceIds": [
      "string"
    ],
    "type": "FIXED",
    "manufacturer": "ZEBRA",
    "archived": true,
    "sort": "name",
    "sortOrder": "asc",
    "search": "string",
    "searchFuzzy": true,
    "searchFields": [
      "name"
    ],
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "type": "FIXED",
      "manufacturer": "ZEBRA",
      "deviceId": "string",
      "endpoint": "string",
      "network": "string",
      "location": {
        "type": "FIXED",
        "id": "string",
        "name": "string"
      },
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "status": {
        "online": true,
        "onlineTime": 0,
        "lastReportedTime": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetReadersQuery](#schemagetreadersquery)|true|none|none|
|total|number(float)|true|none|Total number of records that match the query (without pagination)|
|items|[[GetReaderResponse](#schemagetreaderresponse)]|true|none|This is the list of paginated results, which will be an array of 20 items<br>or less, unless another limit was specified in the query params|

<h2 id="tocS_GetRoleResponse">GetRoleResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetroleresponse"></a>
<a id="schema_GetRoleResponse"></a>
<a id="tocSgetroleresponse"></a>
<a id="tocsgetroleresponse"></a>

```json
{
  "id": "string",
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  },
  "name": "string",
  "description": "string",
  "permissions": [
    "string"
  ],
  "default": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique Spotto ID of the role|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|
|name|string|true|none|Name of the role|
|description|string|true|none|Short description of the role including the scope of access|
|permissions|[string]|true|none|List of permissions this role has access to, following<br>the entity:action pattern|
|default|boolean|false|none|Whether or not this role is a default system role, available to all organisations|

<h2 id="tocS_GetRolesQuery">GetRolesQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetrolesquery"></a>
<a id="schema_GetRolesQuery"></a>
<a id="tocSgetrolesquery"></a>
<a id="tocsgetrolesquery"></a>

```json
{
  "sort": "name",
  "sortOrder": "asc",
  "embed": [
    "meta"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sort|[StandardSortFields](#schemastandardsortfields)|false|none|Common sort fields across most GET endpoints|
|sortOrder|[SortOrders](#schemasortorders)|false|none|Sort orders - ascending and descending|
|embed|[[RoleEmbedField](#schemaroleembedfield)]|false|none|Attach additional user information:<br><br>**meta** attaches basic CRUD status information.|

<h2 id="tocS_GetRolesResponse">GetRolesResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetrolesresponse"></a>
<a id="schema_GetRolesResponse"></a>
<a id="tocSgetrolesresponse"></a>
<a id="tocsgetrolesresponse"></a>

```json
{
  "query": {
    "sort": "name",
    "sortOrder": "asc",
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "id": "string",
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "name": "string",
      "description": "string",
      "permissions": [
        "string"
      ],
      "default": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetRolesQuery](#schemagetrolesquery)|true|none|none|
|total|number(float)|true|none|Total number of records that match the query (without pagination)|
|items|[[GetRoleResponse](#schemagetroleresponse)]|true|none|This is the list of paginated results, which will be an array of 20 items<br>or less, unless another limit was specified in the query params|

<h2 id="tocS_GetTriggerResponse">GetTriggerResponse</h2>
<!-- backwards compatibility -->
<a id="schemagettriggerresponse"></a>
<a id="schema_GetTriggerResponse"></a>
<a id="tocSgettriggerresponse"></a>
<a id="tocsgettriggerresponse"></a>

```json
{
  "type": "ArrivedAt",
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "id": "string",
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[GetArrivedAtTriggerResponse](#schemagetarrivedattriggerresponse)|false|none|Asset or Reader moved in relation to selected locations|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[GetMovedTriggerResponse](#schemagetmovedtriggerresponse)|false|none|Asset or Reader moved anywhere (No location rules)|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[GetWentOnlineTriggerResponse](#schemagetwentonlinetriggerresponse)|false|none|Reader went online after a given threshold|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[GetWentOfflineTriggerResponse](#schemagetwentofflinetriggerresponse)|false|none|Reader went online after a given threshold|

<h2 id="tocS_GetTriggersQuery">GetTriggersQuery</h2>
<!-- backwards compatibility -->
<a id="schemagettriggersquery"></a>
<a id="schema_GetTriggersQuery"></a>
<a id="tocSgettriggersquery"></a>
<a id="tocsgettriggersquery"></a>

```json
{
  "page": 0,
  "limit": 0,
  "ids": [
    "string"
  ],
  "enabled": true,
  "type": "ArrivedAt",
  "sort": "name",
  "sortOrder": "asc",
  "embed": [
    "meta"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|page|number(float)|false|none|**Pagination:** What page of results, assuming the limit (defaulting to 20)<br>to start from. The default is page 0 (the first page of results).<br><br>e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).|
|limit|number(float)|false|none|**Pagination:** Max number of results to return in the request. The default is 20.|
|ids|[string]|false|none|Lookup specific triggers by passing an array of valid Spotto IDs.|
|enabled|boolean|false|none|Lookup triggers that are only enabled or disabled.|
|type|[TriggerType](#schematriggertype)|false|none|==== TRIGGER TYPES ====|
|sort|[StandardSortFields](#schemastandardsortfields)|false|none|Common sort fields across most GET endpoints|
|sortOrder|[SortOrders](#schemasortorders)|false|none|Sort orders - ascending and descending|
|embed|[[TriggerEmbedField](#schematriggerembedfield)]|false|none|Attach additional trigger information:<br><br>**meta** attaches basic CRUD status information.|

<h2 id="tocS_GetTriggersResponse">GetTriggersResponse</h2>
<!-- backwards compatibility -->
<a id="schemagettriggersresponse"></a>
<a id="schema_GetTriggersResponse"></a>
<a id="tocSgettriggersresponse"></a>
<a id="tocsgettriggersresponse"></a>

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "enabled": true,
    "type": "ArrivedAt",
    "sort": "name",
    "sortOrder": "asc",
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "type": "ArrivedAt",
      "locationRules": [
        {
          "type": "MatchName",
          "match": "string"
        }
      ],
      "id": "string",
      "name": "string",
      "enabled": true,
      "actions": [
        {
          "type": "Webhook",
          "endpoint": "string"
        }
      ],
      "subjectRules": [
        {
          "type": "MatchName",
          "match": "string"
        }
      ],
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetTriggersQuery](#schemagettriggersquery)|true|none|none|
|total|number(float)|true|none|Total number of records that match the query (without pagination)|
|items|[[GetTriggerResponse](#schemagettriggerresponse)]|true|none|This is the list of paginated results, which will be an array of 20 items<br>or less, unless another limit was specified in the query params|

<h2 id="tocS_GetUserResponse">GetUserResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetuserresponse"></a>
<a id="schema_GetUserResponse"></a>
<a id="tocSgetuserresponse"></a>
<a id="tocsgetuserresponse"></a>

```json
{
  "type": "EXTERNAL",
  "key": "string",
  "id": "string",
  "name": "string",
  "role": {
    "id": "string",
    "name": "string"
  },
  "organisation": {
    "id": "string",
    "name": "string"
  },
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[GetExternalUserResponse](#schemagetexternaluserresponse)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[GetInternalUserResponse](#schemagetinternaluserresponse)|false|none|none|

<h2 id="tocS_GetUsersQuery">GetUsersQuery</h2>
<!-- backwards compatibility -->
<a id="schemagetusersquery"></a>
<a id="schema_GetUsersQuery"></a>
<a id="tocSgetusersquery"></a>
<a id="tocsgetusersquery"></a>

```json
{
  "page": 0,
  "limit": 0,
  "ids": [
    "string"
  ],
  "role": [
    "string"
  ],
  "type": "INTERNAL",
  "sort": "name",
  "sortOrder": "asc",
  "embed": [
    "meta"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|page|number(float)|false|none|**Pagination:** What page of results, assuming the limit (defaulting to 20)<br>to start from. The default is page 0 (the first page of results).<br><br>e.g. With a limit of 20, page 1 gets us results 20-39 (with zero based indexing).|
|limit|number(float)|false|none|**Pagination:** Max number of results to return in the request. The default is 20.|
|ids|[string]|false|none|Lookup specific users by passing an array of valid Spotto IDs.|
|role|[string]|false|none|Lookup users belonging to specific roles by passing an array of valid Spotto IDs.|
|type|[UserType](#schemausertype)|false|none|none|
|sort|[StandardSortFields](#schemastandardsortfields)|false|none|Common sort fields across most GET endpoints|
|sortOrder|[SortOrders](#schemasortorders)|false|none|Sort orders - ascending and descending|
|embed|[[UserEmbedField](#schemauserembedfield)]|false|none|Attach additional user information:<br><br>**meta** attaches basic CRUD status information.|

<h2 id="tocS_GetUsersResponse">GetUsersResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetusersresponse"></a>
<a id="schema_GetUsersResponse"></a>
<a id="tocSgetusersresponse"></a>
<a id="tocsgetusersresponse"></a>

```json
{
  "query": {
    "page": 0,
    "limit": 0,
    "ids": [
      "string"
    ],
    "role": [
      "string"
    ],
    "type": "INTERNAL",
    "sort": "name",
    "sortOrder": "asc",
    "embed": [
      "meta"
    ]
  },
  "total": 0,
  "items": [
    {
      "type": "EXTERNAL",
      "key": "string",
      "id": "string",
      "name": "string",
      "role": {
        "id": "string",
        "name": "string"
      },
      "organisation": {
        "id": "string",
        "name": "string"
      },
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|query|[GetUsersQuery](#schemagetusersquery)|true|none|none|
|total|number(float)|true|none|Total number of records that match the query (without pagination)|
|items|[[GetUserResponse](#schemagetuserresponse)]|true|none|This is the list of paginated results, which will be an array of 20 items<br>or less, unless another limit was specified in the query params|

<h2 id="tocS_GetWentOfflineTriggerResponse">GetWentOfflineTriggerResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetwentofflinetriggerresponse"></a>
<a id="schema_GetWentOfflineTriggerResponse"></a>
<a id="tocSgetwentofflinetriggerresponse"></a>
<a id="tocsgetwentofflinetriggerresponse"></a>

```json
{
  "type": "WentOffline",
  "id": "string",
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

Reader went online after a given threshold

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|id|string|true|none|Unique ID of this Trigger|
|name|string|true|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|enabled|boolean|true|none|Status of the trigger, disabled triggers will not fire|
|actions|[[Action](#schemaaction)]|true|none|The list of actions that fire for this trigger|
|subjectRules|[[Rule](#schemarule)]|true|none|Subject rules filter the possible events that cause this<br>trigger to fire.|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|WentOffline|

<h2 id="tocS_GetWentOnlineTriggerResponse">GetWentOnlineTriggerResponse</h2>
<!-- backwards compatibility -->
<a id="schemagetwentonlinetriggerresponse"></a>
<a id="schema_GetWentOnlineTriggerResponse"></a>
<a id="tocSgetwentonlinetriggerresponse"></a>
<a id="tocsgetwentonlinetriggerresponse"></a>

```json
{
  "type": "WentOnline",
  "id": "string",
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "meta": {
    "created": 0,
    "updated": 0,
    "deleted": 0
  }
}

```

Reader went online after a given threshold

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|id|string|true|none|Unique ID of this Trigger|
|name|string|true|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|enabled|boolean|true|none|Status of the trigger, disabled triggers will not fire|
|actions|[[Action](#schemaaction)]|true|none|The list of actions that fire for this trigger|
|subjectRules|[[Rule](#schemarule)]|true|none|Subject rules filter the possible events that cause this<br>trigger to fire.|
|meta|[IEntityMeta](#schemaientitymeta)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|WentOnline|

<h2 id="tocS_IAntennaRequest">IAntennaRequest</h2>
<!-- backwards compatibility -->
<a id="schemaiantennarequest"></a>
<a id="schema_IAntennaRequest"></a>
<a id="tocSiantennarequest"></a>
<a id="tocsiantennarequest"></a>

```json
{
  "name": "string",
  "port": 0,
  "locationId": "string",
  "location": {
    "name": "string",
    "level": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|port|number(float)|true|none|none|
|locationId|string|false|none|none|
|location|object|false|none|none|
|» name|string|true|none|none|
|» level|string|false|none|none|

<h2 id="tocS_IEmbeddedEntity">IEmbeddedEntity</h2>
<!-- backwards compatibility -->
<a id="schemaiembeddedentity"></a>
<a id="schema_IEmbeddedEntity"></a>
<a id="tocSiembeddedentity"></a>
<a id="tocsiembeddedentity"></a>

```json
{
  "id": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|Unique ID of the embedded entity|
|name|string|true|none|Name of the embedded entity|

<h2 id="tocS_IEntityMeta">IEntityMeta</h2>
<!-- backwards compatibility -->
<a id="schemaientitymeta"></a>
<a id="schema_IEntityMeta"></a>
<a id="tocSientitymeta"></a>
<a id="tocsientitymeta"></a>

```json
{
  "created": 0,
  "updated": 0,
  "deleted": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created|number(float)|true|none|Created timestamp|
|updated|number(float)|false|none|Last updated timestamp|
|deleted|number(float)|false|none|Deletion timestamp|

<h2 id="tocS_IFixedReaderLocation">IFixedReaderLocation</h2>
<!-- backwards compatibility -->
<a id="schemaifixedreaderlocation"></a>
<a id="schema_IFixedReaderLocation"></a>
<a id="tocSifixedreaderlocation"></a>
<a id="tocsifixedreaderlocation"></a>

```json
{
  "type": "FIXED",
  "id": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|id|string|true|none|Unique ID of the embedded entity|
|name|string|true|none|Name of the embedded entity|

#### Enumerated Values

|Property|Value|
|---|---|
|type|FIXED|

<h2 id="tocS_IInventoryItem">IInventoryItem</h2>
<!-- backwards compatibility -->
<a id="schemaiinventoryitem"></a>
<a id="schema_IInventoryItem"></a>
<a id="tocSiinventoryitem"></a>
<a id="tocsiinventoryitem"></a>

```json
{
  "id": "string",
  "name": "string",
  "firstSeen": 0,
  "lastSeen": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|name|string|true|none|none|
|firstSeen|number(float)|true|none|none|
|lastSeen|number(float)|true|none|none|

<h2 id="tocS_ILastLocation">ILastLocation</h2>
<!-- backwards compatibility -->
<a id="schemailastlocation"></a>
<a id="schema_ILastLocation"></a>
<a id="tocSilastlocation"></a>
<a id="tocsilastlocation"></a>

```json
{
  "firstSeen": 0,
  "lastSeen": 0,
  "id": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|firstSeen|number(float)|true|none|none|
|lastSeen|number(float)|true|none|none|
|id|string|true|none|Unique ID of the embedded entity|
|name|string|true|none|Name of the embedded entity|

<h2 id="tocS_INetworkRequest">INetworkRequest</h2>
<!-- backwards compatibility -->
<a id="schemainetworkrequest"></a>
<a id="schema_INetworkRequest"></a>
<a id="tocSinetworkrequest"></a>
<a id="tocsinetworkrequest"></a>

```json
{
  "name": "string",
  "username": "string",
  "password": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|SSID of the network|
|username|string|false|none|Optional network username, this is only required for WPA2 Enterprise networks|
|password|string|false|none|Optional network password, this is not required for open networks|

<h2 id="tocS_IReaderStatus">IReaderStatus</h2>
<!-- backwards compatibility -->
<a id="schemaireaderstatus"></a>
<a id="schema_IReaderStatus"></a>
<a id="tocSireaderstatus"></a>
<a id="tocsireaderstatus"></a>

```json
{
  "online": true,
  "onlineTime": 0,
  "lastReportedTime": 0
}

```

Reader online status information.

TODO: Add other IoT style status information here
e.g. Temperature, WiFi signal, Battery level (for portable readers)

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|online|boolean|true|none|none|
|onlineTime|number(float)|true|none|none|
|lastReportedTime|number(float)|true|none|none|

<h2 id="tocS_IRovingReaderLocation">IRovingReaderLocation</h2>
<!-- backwards compatibility -->
<a id="schemairovingreaderlocation"></a>
<a id="schema_IRovingReaderLocation"></a>
<a id="tocSirovingreaderlocation"></a>
<a id="tocsirovingreaderlocation"></a>

```json
{
  "type": "ROVING",
  "firstSeen": 0,
  "lastSeen": 0,
  "id": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|firstSeen|number(float)|true|none|Last time the location was seen by this reader|
|lastSeen|number(float)|true|none|none|
|id|string|true|none|Unique ID of the embedded entity|
|name|string|true|none|Name of the embedded entity|

#### Enumerated Values

|Property|Value|
|---|---|
|type|ROVING|

<h2 id="tocS_IUpsertedLocation">IUpsertedLocation</h2>
<!-- backwards compatibility -->
<a id="schemaiupsertedlocation"></a>
<a id="schema_IUpsertedLocation"></a>
<a id="tocSiupsertedlocation"></a>
<a id="tocsiupsertedlocation"></a>

```json
{
  "name": "string",
  "level": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|level|string|false|none|none|

<h2 id="tocS_Integrations">Integrations</h2>
<!-- backwards compatibility -->
<a id="schemaintegrations"></a>
<a id="schema_Integrations"></a>
<a id="tocSintegrations"></a>
<a id="tocsintegrations"></a>

```json
{
  "mqtt": {
    "enabled": true,
    "username": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mqtt|[MQTTIntegrationDetails](#schemamqttintegrationdetails)|false|none|none|

<h2 id="tocS_LocationEmbedField">LocationEmbedField</h2>
<!-- backwards compatibility -->
<a id="schemalocationembedfield"></a>
<a id="schema_LocationEmbedField"></a>
<a id="tocSlocationembedfield"></a>
<a id="tocslocationembedfield"></a>

```json
"meta"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|meta|
|*anonymous*|tagIds|
|*anonymous*|readers|

<h2 id="tocS_LocationSearchField">LocationSearchField</h2>
<!-- backwards compatibility -->
<a id="schemalocationsearchfield"></a>
<a id="schema_LocationSearchField"></a>
<a id="tocSlocationsearchfield"></a>
<a id="tocslocationsearchfield"></a>

```json
"name"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|name|

<h2 id="tocS_MQTTAction">MQTTAction</h2>
<!-- backwards compatibility -->
<a id="schemamqttaction"></a>
<a id="schema_MQTTAction"></a>
<a id="tocSmqttaction"></a>
<a id="tocsmqttaction"></a>

```json
{
  "type": "MQTT",
  "topic": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|topic|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|MQTT|

<h2 id="tocS_MQTTDisabled">MQTTDisabled</h2>
<!-- backwards compatibility -->
<a id="schemamqttdisabled"></a>
<a id="schema_MQTTDisabled"></a>
<a id="tocSmqttdisabled"></a>
<a id="tocsmqttdisabled"></a>

```json
{
  "enabled": false
}

```

==== INTEGRATIONS ====

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|enabled|boolean|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|enabled|false|

<h2 id="tocS_MQTTEnabled">MQTTEnabled</h2>
<!-- backwards compatibility -->
<a id="schemamqttenabled"></a>
<a id="schema_MQTTEnabled"></a>
<a id="tocSmqttenabled"></a>
<a id="tocsmqttenabled"></a>

```json
{
  "enabled": true,
  "username": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|enabled|boolean|true|none|none|
|username|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|enabled|true|

<h2 id="tocS_MQTTEnabledWithDetails">MQTTEnabledWithDetails</h2>
<!-- backwards compatibility -->
<a id="schemamqttenabledwithdetails"></a>
<a id="schema_MQTTEnabledWithDetails"></a>
<a id="tocSmqttenabledwithdetails"></a>
<a id="tocsmqttenabledwithdetails"></a>

```json
{
  "password": "string",
  "path": "string",
  "enabled": true,
  "username": "string"
}

```

Extends the base shape returned in the integrations list with
additional information about the integration

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|password|string|true|none|none|
|path|string|true|none|none|
|enabled|boolean|true|none|none|
|username|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|enabled|true|

<h2 id="tocS_MQTTIntegrationDetails">MQTTIntegrationDetails</h2>
<!-- backwards compatibility -->
<a id="schemamqttintegrationdetails"></a>
<a id="schema_MQTTIntegrationDetails"></a>
<a id="tocSmqttintegrationdetails"></a>
<a id="tocsmqttintegrationdetails"></a>

```json
{
  "enabled": true,
  "username": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[MQTTEnabled](#schemamqttenabled)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[MQTTDisabled](#schemamqttdisabled)|false|none|==== INTEGRATIONS ====|

<h2 id="tocS_MQTTSettings">MQTTSettings</h2>
<!-- backwards compatibility -->
<a id="schemamqttsettings"></a>
<a id="schema_MQTTSettings"></a>
<a id="tocSmqttsettings"></a>
<a id="tocsmqttsettings"></a>

```json
{
  "password": "string",
  "path": "string",
  "enabled": true,
  "username": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[MQTTEnabledWithDetails](#schemamqttenabledwithdetails)|false|none|Extends the base shape returned in the integrations list with<br>additional information about the integration|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[MQTTDisabled](#schemamqttdisabled)|false|none|==== INTEGRATIONS ====|

<h2 id="tocS_Manufacturer">Manufacturer</h2>
<!-- backwards compatibility -->
<a id="schemamanufacturer"></a>
<a id="schema_Manufacturer"></a>
<a id="tocSmanufacturer"></a>
<a id="tocsmanufacturer"></a>

```json
"ZEBRA"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|ZEBRA|
|*anonymous*|ZEBRA_IOT_BRIDGE|
|*anonymous*|IMPINJ|
|*anonymous*|BLUECATS|
|*anonymous*|TURCK|
|*anonymous*|THING_MAGIC|
|*anonymous*|IOTX3|
|*anonymous*|OTHER|
|*anonymous*|DETECT_APP|

<h2 id="tocS_ManufacturerPreferences">ManufacturerPreferences</h2>
<!-- backwards compatibility -->
<a id="schemamanufacturerpreferences"></a>
<a id="schema_ManufacturerPreferences"></a>
<a id="tocSmanufacturerpreferences"></a>
<a id="tocsmanufacturerpreferences"></a>

```json
{
  "default": "ZEBRA",
  "enabled": [
    "ZEBRA"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|default|[Manufacturer](#schemamanufacturer)|false|none|none|
|enabled|[[Manufacturer](#schemamanufacturer)]|true|none|none|

<h2 id="tocS_MatchNameRule">MatchNameRule</h2>
<!-- backwards compatibility -->
<a id="schemamatchnamerule"></a>
<a id="schema_MatchNameRule"></a>
<a id="tocSmatchnamerule"></a>
<a id="tocsmatchnamerule"></a>

```json
{
  "type": "MatchName",
  "match": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|match|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|MatchName|

<h2 id="tocS_NetworkWithDeletionFlag">NetworkWithDeletionFlag</h2>
<!-- backwards compatibility -->
<a id="schemanetworkwithdeletionflag"></a>
<a id="schema_NetworkWithDeletionFlag"></a>
<a id="tocSnetworkwithdeletionflag"></a>
<a id="tocsnetworkwithdeletionflag"></a>

```json
{
  "deleteNetwork": true,
  "name": "string",
  "username": "string",
  "password": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|deleteNetwork|boolean|false|none|Flag to delete the specified network, using the 'name' field as an identifier|
|name|string|true|none|SSID of the network|
|username|string|false|none|Optional network username, this is only required for WPA2 Enterprise networks|
|password|string|false|none|Optional network password, this is not required for open networks|

<h2 id="tocS_OrganisationEmbedField">OrganisationEmbedField</h2>
<!-- backwards compatibility -->
<a id="schemaorganisationembedfield"></a>
<a id="schema_OrganisationEmbedField"></a>
<a id="tocSorganisationembedfield"></a>
<a id="tocsorganisationembedfield"></a>

```json
"meta"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|meta|

<h2 id="tocS_PostArrivedAtTriggerRequest">PostArrivedAtTriggerRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostarrivedattriggerrequest"></a>
<a id="schema_PostArrivedAtTriggerRequest"></a>
<a id="tocSpostarrivedattriggerrequest"></a>
<a id="tocspostarrivedattriggerrequest"></a>

```json
{
  "type": "ArrivedAt",
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "name": "string",
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ]
}

```

Asset or Reader moved in relation to selected locations

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|locationRules|[[Rule](#schemarule)]|true|none|Location rules filter the possible events that cause this<br>trigger to fire.|
|name|string|true|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|actions|[[Action](#schemaaction)]|true|none|The list of actions that fire for this trigger|
|subjectRules|[[Rule](#schemarule)]|true|none|Subject rules filter the possible events that cause this<br>trigger to fire.|

#### Enumerated Values

|Property|Value|
|---|---|
|type|ArrivedAt|

<h2 id="tocS_PostAssetRequest">PostAssetRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostassetrequest"></a>
<a id="schema_PostAssetRequest"></a>
<a id="tocSpostassetrequest"></a>
<a id="tocspostassetrequest"></a>

```json
{
  "name": "string",
  "tagIds": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|tagIds|[string]|false|none|none|

<h2 id="tocS_PostAssetsError">PostAssetsError</h2>
<!-- backwards compatibility -->
<a id="schemapostassetserror"></a>
<a id="schema_PostAssetsError"></a>
<a id="tocSpostassetserror"></a>
<a id="tocspostassetserror"></a>

```json
{
  "data": [
    {
      "index": 0,
      "errors": [
        {
          "type": "TagsExistError",
          "message": "string",
          "conflicts": [
            {
              "tagId": "string",
              "type": "LOCATION",
              "id": "string"
            }
          ]
        }
      ]
    }
  ],
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[TagErrorInList](#schematagerrorinlist)]|true|none|none|
|message|string|true|none|none|

<h2 id="tocS_PostAssetsErrorResponse">PostAssetsErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemapostassetserrorresponse"></a>
<a id="schema_PostAssetsErrorResponse"></a>
<a id="tocSpostassetserrorresponse"></a>
<a id="tocspostassetserrorresponse"></a>

```json
{
  "message": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[DefaultError](#schemadefaulterror)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PostAssetsError](#schemapostassetserror)|false|none|none|

<h2 id="tocS_PostAssetsRequest">PostAssetsRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostassetsrequest"></a>
<a id="schema_PostAssetsRequest"></a>
<a id="tocSpostassetsrequest"></a>
<a id="tocspostassetsrequest"></a>

```json
[
  {
    "name": "string",
    "tagIds": [
      "string"
    ]
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[PostAssetRequest](#schemapostassetrequest)]|false|none|none|

<h2 id="tocS_PostAssetsResponse">PostAssetsResponse</h2>
<!-- backwards compatibility -->
<a id="schemapostassetsresponse"></a>
<a id="schema_PostAssetsResponse"></a>
<a id="tocSpostassetsresponse"></a>
<a id="tocspostassetsresponse"></a>

```json
{
  "inserted": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "score": 0,
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "lastLocation": {
        "firstSeen": 0,
        "lastSeen": 0,
        "id": "string",
        "name": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|inserted|number(float)|true|none|Total number of records that were inserted|
|items|[[GetAssetResponse](#schemagetassetresponse)]|true|none|The list of inserted items|

<h2 id="tocS_PostExternalUserRequest">PostExternalUserRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostexternaluserrequest"></a>
<a id="schema_PostExternalUserRequest"></a>
<a id="tocSpostexternaluserrequest"></a>
<a id="tocspostexternaluserrequest"></a>

```json
{
  "type": "EXTERNAL",
  "name": "string",
  "role": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|User type for identifying external API users from internal users|
|name|string|true|none|The User's full name, or identifier of the external API user|
|role|string|true|none|The role ID the new user will be assigned|

#### Enumerated Values

|Property|Value|
|---|---|
|type|EXTERNAL|

<h2 id="tocS_PostInternalUserRequest">PostInternalUserRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostinternaluserrequest"></a>
<a id="schema_PostInternalUserRequest"></a>
<a id="tocSpostinternaluserrequest"></a>
<a id="tocspostinternaluserrequest"></a>

```json
{
  "type": "INTERNAL",
  "email": "string",
  "password": "string",
  "name": "string",
  "role": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|User type for identifying internal users from external API users|
|email|string|true|none|The User's unique email address|
|password|string|false|none|Access password the new user can be optionally assigned.<br>If left blank, one will be generated and sent to the email<br>address specified in the request.|
|name|string|true|none|The User's full name, or identifier of the external API user|
|role|string|true|none|The role ID the new user will be assigned|

#### Enumerated Values

|Property|Value|
|---|---|
|type|INTERNAL|

<h2 id="tocS_PostLevelRequest">PostLevelRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostlevelrequest"></a>
<a id="schema_PostLevelRequest"></a>
<a id="tocSpostlevelrequest"></a>
<a id="tocspostlevelrequest"></a>

```json
{
  "level": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|level|string|true|none|none|

<h2 id="tocS_PostLevelResponse">PostLevelResponse</h2>
<!-- backwards compatibility -->
<a id="schemapostlevelresponse"></a>
<a id="schema_PostLevelResponse"></a>
<a id="tocSpostlevelresponse"></a>
<a id="tocspostlevelresponse"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocS_PostLocationsError">PostLocationsError</h2>
<!-- backwards compatibility -->
<a id="schemapostlocationserror"></a>
<a id="schema_PostLocationsError"></a>
<a id="tocSpostlocationserror"></a>
<a id="tocspostlocationserror"></a>

```json
{
  "data": [
    {
      "index": 0,
      "errors": [
        {
          "type": "TagsExistError",
          "message": "string",
          "conflicts": [
            {
              "tagId": "string",
              "type": "LOCATION",
              "id": "string"
            }
          ]
        }
      ]
    }
  ],
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[TagErrorInList](#schematagerrorinlist)]|true|none|none|
|message|string|true|none|none|

<h2 id="tocS_PostLocationsErrorResponse">PostLocationsErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemapostlocationserrorresponse"></a>
<a id="schema_PostLocationsErrorResponse"></a>
<a id="tocSpostlocationserrorresponse"></a>
<a id="tocspostlocationserrorresponse"></a>

```json
{
  "message": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[DefaultError](#schemadefaulterror)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PostLocationsError](#schemapostlocationserror)|false|none|none|

<h2 id="tocS_PostLocationsRequest">PostLocationsRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostlocationsrequest"></a>
<a id="schema_PostLocationsRequest"></a>
<a id="tocSpostlocationsrequest"></a>
<a id="tocspostlocationsrequest"></a>

```json
[
  {
    "name": "string",
    "level": "string",
    "tagIds": [
      "string"
    ],
    "address": "string",
    "geoLocation": "GeoJSON"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|level|string|false|none|none|
|tagIds|[string]|false|none|If this location can be sensed by a reader you can add the IDs that identify it|
|address|string|false|none|none|
|geoLocation|string|false|none|NOTE: For brevity this option has been set to a string. Any valid GeoJSON object<br>will be accepted for this field. Check https://geojson.org/ for details.|

#### Enumerated Values

|Property|Value|
|---|---|
|geoLocation|GeoJSON|

<h2 id="tocS_PostLocationsResponse">PostLocationsResponse</h2>
<!-- backwards compatibility -->
<a id="schemapostlocationsresponse"></a>
<a id="schema_PostLocationsResponse"></a>
<a id="tocSpostlocationsresponse"></a>
<a id="tocspostlocationsresponse"></a>

```json
{
  "inserted": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "tagIds": [
        "string"
      ],
      "readers": [
        {
          "id": "string",
          "name": "string"
        }
      ],
      "level": "string",
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|inserted|number(float)|true|none|Total number of records that were inserted|
|items|[[GetLocationResponse](#schemagetlocationresponse)]|true|none|The list of inserted items|

<h2 id="tocS_PostMovedTriggerRequest">PostMovedTriggerRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostmovedtriggerrequest"></a>
<a id="schema_PostMovedTriggerRequest"></a>
<a id="tocSpostmovedtriggerrequest"></a>
<a id="tocspostmovedtriggerrequest"></a>

```json
{
  "type": "Moved",
  "name": "string",
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ]
}

```

Asset or Reader moved anywhere (No location rules)

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|name|string|true|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|actions|[[Action](#schemaaction)]|true|none|The list of actions that fire for this trigger|
|subjectRules|[[Rule](#schemarule)]|true|none|Subject rules filter the possible events that cause this<br>trigger to fire.|

#### Enumerated Values

|Property|Value|
|---|---|
|type|Moved|

<h2 id="tocS_PostOrganisationRequest">PostOrganisationRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostorganisationrequest"></a>
<a id="schema_PostOrganisationRequest"></a>
<a id="tocSpostorganisationrequest"></a>
<a id="tocspostorganisationrequest"></a>

```json
{
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Organisation name|

<h2 id="tocS_PostReaderRequest">PostReaderRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostreaderrequest"></a>
<a id="schema_PostReaderRequest"></a>
<a id="tocSpostreaderrequest"></a>
<a id="tocspostreaderrequest"></a>

```json
{
  "name": "string",
  "manufacturer": "ZEBRA",
  "type": "FIXED",
  "locationId": "string",
  "location": {
    "name": "string",
    "level": "string"
  },
  "deviceId": "string",
  "network": {
    "name": "string",
    "username": "string",
    "password": "string"
  },
  "saveNetwork": true,
  "antennas": [
    {
      "name": "string",
      "port": 0,
      "locationId": "string",
      "location": {
        "name": "string",
        "level": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|none|
|manufacturer|[Manufacturer](#schemamanufacturer)|true|none|none|
|type|[ReaderType](#schemareadertype)|true|none|none|
|locationId|string|false|none|locationId is used for specifying an already existing location|
|location|[IUpsertedLocation](#schemaiupsertedlocation)|false|none|none|
|deviceId|string|false|none|device ID for an IOTX3 or phone reader|
|network|[INetworkRequest](#schemainetworkrequest)|false|none|none|
|saveNetwork|boolean|false|none|When this flag is true it will save any wifi details to the account. It will be ignored if no networks are present|
|antennas|[[IAntennaRequest](#schemaiantennarequest)]|false|none|Additional antenna config. This will only take effect for Virtual or Portal readers|

<h2 id="tocS_PostReadersRequest">PostReadersRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostreadersrequest"></a>
<a id="schema_PostReadersRequest"></a>
<a id="tocSpostreadersrequest"></a>
<a id="tocspostreadersrequest"></a>

```json
[
  {
    "name": "string",
    "manufacturer": "ZEBRA",
    "type": "FIXED",
    "locationId": "string",
    "location": {
      "name": "string",
      "level": "string"
    },
    "deviceId": "string",
    "network": {
      "name": "string",
      "username": "string",
      "password": "string"
    },
    "saveNetwork": true,
    "antennas": [
      {
        "name": "string",
        "port": 0,
        "locationId": "string",
        "location": {
          "name": "string",
          "level": "string"
        }
      }
    ]
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[PostReaderRequest](#schemapostreaderrequest)]|false|none|none|

<h2 id="tocS_PostReadersResponse">PostReadersResponse</h2>
<!-- backwards compatibility -->
<a id="schemapostreadersresponse"></a>
<a id="schema_PostReadersResponse"></a>
<a id="tocSpostreadersresponse"></a>
<a id="tocspostreadersresponse"></a>

```json
{
  "inserted": 0,
  "items": [
    {
      "id": "string",
      "name": "string",
      "type": "FIXED",
      "manufacturer": "ZEBRA",
      "deviceId": "string",
      "endpoint": "string",
      "network": "string",
      "location": {
        "type": "FIXED",
        "id": "string",
        "name": "string"
      },
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      },
      "status": {
        "online": true,
        "onlineTime": 0,
        "lastReportedTime": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|inserted|number(float)|true|none|Total number of records that were inserted|
|items|[[GetReaderResponse](#schemagetreaderresponse)]|true|none|The list of inserted items|

<h2 id="tocS_PostRoleRequest">PostRoleRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostrolerequest"></a>
<a id="schema_PostRoleRequest"></a>
<a id="tocSpostrolerequest"></a>
<a id="tocspostrolerequest"></a>

```json
{
  "name": "string",
  "description": "string",
  "permissions": [
    "string"
  ],
  "default": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|true|none|Name of the role|
|description|string|true|none|Short description of the role including the scope of access|
|permissions|[string]|true|none|List of permissions this role has access to, following<br>the entity:action pattern|
|default|boolean|false|none|Whether or not this role is a default system role, available to all organisations|

<h2 id="tocS_PostTriggerRequest">PostTriggerRequest</h2>
<!-- backwards compatibility -->
<a id="schemaposttriggerrequest"></a>
<a id="schema_PostTriggerRequest"></a>
<a id="tocSposttriggerrequest"></a>
<a id="tocsposttriggerrequest"></a>

```json
{
  "type": "ArrivedAt",
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "name": "string",
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ]
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PostArrivedAtTriggerRequest](#schemapostarrivedattriggerrequest)|false|none|Asset or Reader moved in relation to selected locations|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PostMovedTriggerRequest](#schemapostmovedtriggerrequest)|false|none|Asset or Reader moved anywhere (No location rules)|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PostWentOnlineTriggerRequest](#schemapostwentonlinetriggerrequest)|false|none|Reader went online after a given threshold|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PostWentOfflineTriggerRequest](#schemapostwentofflinetriggerrequest)|false|none|Reader went online after a given threshold|

<h2 id="tocS_PostTriggersRequest">PostTriggersRequest</h2>
<!-- backwards compatibility -->
<a id="schemaposttriggersrequest"></a>
<a id="schema_PostTriggersRequest"></a>
<a id="tocSposttriggersrequest"></a>
<a id="tocsposttriggersrequest"></a>

```json
[
  {
    "type": "ArrivedAt",
    "locationRules": [
      {
        "type": "MatchName",
        "match": "string"
      }
    ],
    "name": "string",
    "actions": [
      {
        "type": "Webhook",
        "endpoint": "string"
      }
    ],
    "subjectRules": [
      {
        "type": "MatchName",
        "match": "string"
      }
    ]
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[PostTriggerRequest](#schemaposttriggerrequest)]|false|none|none|

<h2 id="tocS_PostTriggersResponse">PostTriggersResponse</h2>
<!-- backwards compatibility -->
<a id="schemaposttriggersresponse"></a>
<a id="schema_PostTriggersResponse"></a>
<a id="tocSposttriggersresponse"></a>
<a id="tocsposttriggersresponse"></a>

```json
{
  "inserted": 0,
  "items": [
    {
      "type": "ArrivedAt",
      "locationRules": [
        {
          "type": "MatchName",
          "match": "string"
        }
      ],
      "id": "string",
      "name": "string",
      "enabled": true,
      "actions": [
        {
          "type": "Webhook",
          "endpoint": "string"
        }
      ],
      "subjectRules": [
        {
          "type": "MatchName",
          "match": "string"
        }
      ],
      "meta": {
        "created": 0,
        "updated": 0,
        "deleted": 0
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|inserted|number(float)|true|none|Total number of records that were inserted|
|items|[[GetTriggerResponse](#schemagettriggerresponse)]|true|none|The list of inserted items|

<h2 id="tocS_PostUserRequest">PostUserRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostuserrequest"></a>
<a id="schema_PostUserRequest"></a>
<a id="tocSpostuserrequest"></a>
<a id="tocspostuserrequest"></a>

```json
{
  "type": "EXTERNAL",
  "name": "string",
  "role": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PostExternalUserRequest](#schemapostexternaluserrequest)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PostInternalUserRequest](#schemapostinternaluserrequest)|false|none|none|

<h2 id="tocS_PostWentOfflineTriggerRequest">PostWentOfflineTriggerRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostwentofflinetriggerrequest"></a>
<a id="schema_PostWentOfflineTriggerRequest"></a>
<a id="tocSpostwentofflinetriggerrequest"></a>
<a id="tocspostwentofflinetriggerrequest"></a>

```json
{
  "type": "WentOffline",
  "name": "string",
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ]
}

```

Reader went online after a given threshold

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|name|string|true|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|actions|[[Action](#schemaaction)]|true|none|The list of actions that fire for this trigger|
|subjectRules|[[Rule](#schemarule)]|true|none|Subject rules filter the possible events that cause this<br>trigger to fire.|

#### Enumerated Values

|Property|Value|
|---|---|
|type|WentOffline|

<h2 id="tocS_PostWentOnlineTriggerRequest">PostWentOnlineTriggerRequest</h2>
<!-- backwards compatibility -->
<a id="schemapostwentonlinetriggerrequest"></a>
<a id="schema_PostWentOnlineTriggerRequest"></a>
<a id="tocSpostwentonlinetriggerrequest"></a>
<a id="tocspostwentonlinetriggerrequest"></a>

```json
{
  "type": "WentOnline",
  "name": "string",
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ]
}

```

Reader went online after a given threshold

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|name|string|true|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|actions|[[Action](#schemaaction)]|true|none|The list of actions that fire for this trigger|
|subjectRules|[[Rule](#schemarule)]|true|none|Subject rules filter the possible events that cause this<br>trigger to fire.|

#### Enumerated Values

|Property|Value|
|---|---|
|type|WentOnline|

<h2 id="tocS_Preferences">Preferences</h2>
<!-- backwards compatibility -->
<a id="schemapreferences"></a>
<a id="schema_Preferences"></a>
<a id="tocSpreferences"></a>
<a id="tocspreferences"></a>

```json
{
  "tags": {
    "ble": true,
    "rfid": true
  },
  "readers": {
    "type": {
      "default": "FIXED",
      "enabled": [
        "FIXED"
      ]
    },
    "manufacturer": {
      "default": "ZEBRA",
      "enabled": [
        "ZEBRA"
      ]
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tags|[TagPreferences](#schematagpreferences)|false|none|none|
|readers|[ReaderPreferences](#schemareaderpreferences)|false|none|none|

<h2 id="tocS_PutLevelsRequest">PutLevelsRequest</h2>
<!-- backwards compatibility -->
<a id="schemaputlevelsrequest"></a>
<a id="schema_PutLevelsRequest"></a>
<a id="tocSputlevelsrequest"></a>
<a id="tocsputlevelsrequest"></a>

```json
{
  "levels": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|levels|[string]|true|none|none|

<h2 id="tocS_PutLevelsResponse">PutLevelsResponse</h2>
<!-- backwards compatibility -->
<a id="schemaputlevelsresponse"></a>
<a id="schema_PutLevelsResponse"></a>
<a id="tocSputlevelsresponse"></a>
<a id="tocsputlevelsresponse"></a>

```json
{
  "levels": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|levels|[string]|true|none|The new list of levels for this organisation|

<h2 id="tocS_ReaderEmbedField">ReaderEmbedField</h2>
<!-- backwards compatibility -->
<a id="schemareaderembedfield"></a>
<a id="schema_ReaderEmbedField"></a>
<a id="tocSreaderembedfield"></a>
<a id="tocsreaderembedfield"></a>

```json
"meta"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|meta|
|*anonymous*|status|

<h2 id="tocS_ReaderLocation">ReaderLocation</h2>
<!-- backwards compatibility -->
<a id="schemareaderlocation"></a>
<a id="schema_ReaderLocation"></a>
<a id="tocSreaderlocation"></a>
<a id="tocsreaderlocation"></a>

```json
{
  "type": "FIXED",
  "id": "string",
  "name": "string"
}

```

Reader Locations can either be:

FIXED: Are static and don't have a timestamp<br>
ROVING: Are dynamic and have a lastSeen timestamp

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[IFixedReaderLocation](#schemaifixedreaderlocation)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[IRovingReaderLocation](#schemairovingreaderlocation)|false|none|none|

<h2 id="tocS_ReaderPreferences">ReaderPreferences</h2>
<!-- backwards compatibility -->
<a id="schemareaderpreferences"></a>
<a id="schema_ReaderPreferences"></a>
<a id="tocSreaderpreferences"></a>
<a id="tocsreaderpreferences"></a>

```json
{
  "type": {
    "default": "FIXED",
    "enabled": [
      "FIXED"
    ]
  },
  "manufacturer": {
    "default": "ZEBRA",
    "enabled": [
      "ZEBRA"
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|[ReaderTypePreferences](#schemareadertypepreferences)|false|none|==== PREFERENCES ====<br>UI preferences to streamline content and available fields<br>to be only what is relevant for the given organisation|
|manufacturer|[ManufacturerPreferences](#schemamanufacturerpreferences)|false|none|none|

<h2 id="tocS_ReaderSearchField">ReaderSearchField</h2>
<!-- backwards compatibility -->
<a id="schemareadersearchfield"></a>
<a id="schema_ReaderSearchField"></a>
<a id="tocSreadersearchfield"></a>
<a id="tocsreadersearchfield"></a>

```json
"name"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|name|
|*anonymous*|deviceId|

<h2 id="tocS_ReaderType">ReaderType</h2>
<!-- backwards compatibility -->
<a id="schemareadertype"></a>
<a id="schema_ReaderType"></a>
<a id="tocSreadertype"></a>
<a id="tocsreadertype"></a>

```json
"FIXED"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|FIXED|
|*anonymous*|ROVING|
|*anonymous*|VIRTUAL|
|*anonymous*|PORTAL|

<h2 id="tocS_ReaderTypePreferences">ReaderTypePreferences</h2>
<!-- backwards compatibility -->
<a id="schemareadertypepreferences"></a>
<a id="schema_ReaderTypePreferences"></a>
<a id="tocSreadertypepreferences"></a>
<a id="tocsreadertypepreferences"></a>

```json
{
  "default": "FIXED",
  "enabled": [
    "FIXED"
  ]
}

```

==== PREFERENCES ====
UI preferences to streamline content and available fields
to be only what is relevant for the given organisation

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|default|[ReaderType](#schemareadertype)|false|none|none|
|enabled|[[ReaderType](#schemareadertype)]|true|none|none|

<h2 id="tocS_RoleEmbedField">RoleEmbedField</h2>
<!-- backwards compatibility -->
<a id="schemaroleembedfield"></a>
<a id="schema_RoleEmbedField"></a>
<a id="tocSroleembedfield"></a>
<a id="tocsroleembedfield"></a>

```json
"meta"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|meta|

<h2 id="tocS_Rule">Rule</h2>
<!-- backwards compatibility -->
<a id="schemarule"></a>
<a id="schema_Rule"></a>
<a id="tocSrule"></a>
<a id="tocsrule"></a>

```json
{
  "type": "MatchName",
  "match": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[MatchNameRule](#schemamatchnamerule)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[StrictMatchIdRule](#schemastrictmatchidrule)|false|none|none|

<h2 id="tocS_SearchableSortFields">SearchableSortFields</h2>
<!-- backwards compatibility -->
<a id="schemasearchablesortfields"></a>
<a id="schema_SearchableSortFields"></a>
<a id="tocSsearchablesortfields"></a>
<a id="tocssearchablesortfields"></a>

```json
"name"

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[StandardSortFields](#schemastandardsortfields)|false|none|Common sort fields across most GET endpoints|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|relevancy|

<h2 id="tocS_SortOrders">SortOrders</h2>
<!-- backwards compatibility -->
<a id="schemasortorders"></a>
<a id="schema_SortOrders"></a>
<a id="tocSsortorders"></a>
<a id="tocssortorders"></a>

```json
"asc"

```

Sort orders - ascending and descending

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Sort orders - ascending and descending|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|asc|
|*anonymous*|desc|

<h2 id="tocS_StandardSortFields">StandardSortFields</h2>
<!-- backwards compatibility -->
<a id="schemastandardsortfields"></a>
<a id="schema_StandardSortFields"></a>
<a id="tocSstandardsortfields"></a>
<a id="tocsstandardsortfields"></a>

```json
"name"

```

Common sort fields across most GET endpoints

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Common sort fields across most GET endpoints|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|name|
|*anonymous*|updated|
|*anonymous*|created|

<h2 id="tocS_StrictMatchIdRule">StrictMatchIdRule</h2>
<!-- backwards compatibility -->
<a id="schemastrictmatchidrule"></a>
<a id="schema_StrictMatchIdRule"></a>
<a id="tocSstrictmatchidrule"></a>
<a id="tocsstrictmatchidrule"></a>

```json
{
  "type": "StrictMatchId",
  "match": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|match|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|StrictMatchId|

<h2 id="tocS_TagErrorInList">TagErrorInList</h2>
<!-- backwards compatibility -->
<a id="schematagerrorinlist"></a>
<a id="schema_TagErrorInList"></a>
<a id="tocStagerrorinlist"></a>
<a id="tocstagerrorinlist"></a>

```json
{
  "index": 0,
  "errors": [
    {
      "type": "TagsExistError",
      "message": "string",
      "conflicts": [
        {
          "tagId": "string",
          "type": "LOCATION",
          "id": "string"
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|index|number(float)|true|none|Index within the request that errors occurred|
|errors|[oneOf]|true|none|List of errors for the asset at the given index of the request body|

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[TagsExistError](#schematagsexisterror)|false|none|Error structure for revealing tag ID conflicts|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[TagsDuplicatedError](#schematagsduplicatederror)|false|none|Error structure for revealing tag ID conflicts within the request|

<h2 id="tocS_TagPreferences">TagPreferences</h2>
<!-- backwards compatibility -->
<a id="schematagpreferences"></a>
<a id="schema_TagPreferences"></a>
<a id="tocStagpreferences"></a>
<a id="tocstagpreferences"></a>

```json
{
  "ble": true,
  "rfid": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ble|boolean|true|none|none|
|rfid|boolean|true|none|none|

<h2 id="tocS_TagsDuplicatedConflict">TagsDuplicatedConflict</h2>
<!-- backwards compatibility -->
<a id="schematagsduplicatedconflict"></a>
<a id="schema_TagsDuplicatedConflict"></a>
<a id="tocStagsduplicatedconflict"></a>
<a id="tocstagsduplicatedconflict"></a>

```json
{
  "tagId": "string",
  "index": 0
}

```

A single conflict with a new tag ID existing on a previous item in the request

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tagId|string|true|none|Tag ID causing the conflict|
|index|number(float)|true|none|Index in this request the tag ID was first found|

<h2 id="tocS_TagsDuplicatedError">TagsDuplicatedError</h2>
<!-- backwards compatibility -->
<a id="schematagsduplicatederror"></a>
<a id="schema_TagsDuplicatedError"></a>
<a id="tocStagsduplicatederror"></a>
<a id="tocstagsduplicatederror"></a>

```json
{
  "type": "TagsDuplicatedError",
  "message": "string",
  "conflicts": [
    {
      "tagId": "string",
      "index": 0
    }
  ]
}

```

Error structure for revealing tag ID conflicts within the request

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|message|string|true|none|none|
|conflicts|[[TagsDuplicatedConflict](#schematagsduplicatedconflict)]|true|none|[A single conflict with a new tag ID existing on a previous item in the request]|

#### Enumerated Values

|Property|Value|
|---|---|
|type|TagsDuplicatedError|

<h2 id="tocS_TagsExistConflict">TagsExistConflict</h2>
<!-- backwards compatibility -->
<a id="schematagsexistconflict"></a>
<a id="schema_TagsExistConflict"></a>
<a id="tocStagsexistconflict"></a>
<a id="tocstagsexistconflict"></a>

```json
{
  "tagId": "string",
  "type": "LOCATION",
  "id": "string"
}

```

A single conflict with a new tag ID existing on an existing entity

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tagId|string|true|none|Tag ID causing the conflict|
|type|string|true|none|Type of entity the tag ID exists on|
|id|string|true|none|ID of the entity the tag ID exists on|

#### Enumerated Values

|Property|Value|
|---|---|
|type|LOCATION|
|type|ASSET|

<h2 id="tocS_TagsExistError">TagsExistError</h2>
<!-- backwards compatibility -->
<a id="schematagsexisterror"></a>
<a id="schema_TagsExistError"></a>
<a id="tocStagsexisterror"></a>
<a id="tocstagsexisterror"></a>

```json
{
  "type": "TagsExistError",
  "message": "string",
  "conflicts": [
    {
      "tagId": "string",
      "type": "LOCATION",
      "id": "string"
    }
  ]
}

```

Error structure for revealing tag ID conflicts

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|message|string|true|none|none|
|conflicts|[[TagsExistConflict](#schematagsexistconflict)]|true|none|[A single conflict with a new tag ID existing on an existing entity]|

#### Enumerated Values

|Property|Value|
|---|---|
|type|TagsExistError|

<h2 id="tocS_TimestampFormat">TimestampFormat</h2>
<!-- backwards compatibility -->
<a id="schematimestampformat"></a>
<a id="schema_TimestampFormat"></a>
<a id="tocStimestampformat"></a>
<a id="tocstimestampformat"></a>

```json
"epoch"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|epoch|
|*anonymous*|iso|

<h2 id="tocS_TriggerEmbedField">TriggerEmbedField</h2>
<!-- backwards compatibility -->
<a id="schematriggerembedfield"></a>
<a id="schema_TriggerEmbedField"></a>
<a id="tocStriggerembedfield"></a>
<a id="tocstriggerembedfield"></a>

```json
"meta"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|meta|

<h2 id="tocS_TriggerType">TriggerType</h2>
<!-- backwards compatibility -->
<a id="schematriggertype"></a>
<a id="schema_TriggerType"></a>
<a id="tocStriggertype"></a>
<a id="tocstriggertype"></a>

```json
"ArrivedAt"

```

==== TRIGGER TYPES ====

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|==== TRIGGER TYPES ====|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|ArrivedAt|
|*anonymous*|Moved|
|*anonymous*|WentOnline|
|*anonymous*|WentOffline|

<h2 id="tocS_UpdateAssetError">UpdateAssetError</h2>
<!-- backwards compatibility -->
<a id="schemaupdateasseterror"></a>
<a id="schema_UpdateAssetError"></a>
<a id="tocSupdateasseterror"></a>
<a id="tocsupdateasseterror"></a>

```json
{
  "data": {
    "type": "TagsExistError",
    "message": "string",
    "conflicts": [
      {
        "tagId": "string",
        "type": "LOCATION",
        "id": "string"
      }
    ]
  },
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[TagsExistError](#schematagsexisterror)|true|none|Error structure for revealing tag ID conflicts|
|message|string|true|none|none|

<h2 id="tocS_UpdateAssetErrorResponse">UpdateAssetErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemaupdateasseterrorresponse"></a>
<a id="schema_UpdateAssetErrorResponse"></a>
<a id="tocSupdateasseterrorresponse"></a>
<a id="tocsupdateasseterrorresponse"></a>

```json
{
  "message": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[DefaultError](#schemadefaulterror)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UpdateAssetError](#schemaupdateasseterror)|false|none|none|

<h2 id="tocS_UpdateAssetRequest">UpdateAssetRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateassetrequest"></a>
<a id="schema_UpdateAssetRequest"></a>
<a id="tocSupdateassetrequest"></a>
<a id="tocsupdateassetrequest"></a>

```json
{
  "name": "string",
  "archived": true,
  "tagIds": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|archived|boolean|false|none|none|
|tagIds|[string]|false|none|none|

<h2 id="tocS_UpdateLocationError">UpdateLocationError</h2>
<!-- backwards compatibility -->
<a id="schemaupdatelocationerror"></a>
<a id="schema_UpdateLocationError"></a>
<a id="tocSupdatelocationerror"></a>
<a id="tocsupdatelocationerror"></a>

```json
{
  "data": {
    "type": "TagsExistError",
    "message": "string",
    "conflicts": [
      {
        "tagId": "string",
        "type": "LOCATION",
        "id": "string"
      }
    ]
  },
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[TagsExistError](#schematagsexisterror)|true|none|Error structure for revealing tag ID conflicts|
|message|string|true|none|none|

<h2 id="tocS_UpdateLocationErrorResponse">UpdateLocationErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemaupdatelocationerrorresponse"></a>
<a id="schema_UpdateLocationErrorResponse"></a>
<a id="tocSupdatelocationerrorresponse"></a>
<a id="tocsupdatelocationerrorresponse"></a>

```json
{
  "message": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[DefaultError](#schemadefaulterror)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UpdateLocationError](#schemaupdatelocationerror)|false|none|none|

<h2 id="tocS_UpdateLocationRequest">UpdateLocationRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatelocationrequest"></a>
<a id="schema_UpdateLocationRequest"></a>
<a id="tocSupdatelocationrequest"></a>
<a id="tocsupdatelocationrequest"></a>

```json
{
  "name": "string",
  "level": "string",
  "tagIds": [
    "string"
  ],
  "archived": true,
  "address": "string",
  "geoLocation": "GeoJSON"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|level|string|false|none|none|
|tagIds|[string]|false|none|If this location can be sensed by a reader you can add the IDs that identify it|
|archived|boolean|false|none|When set to true it will archive this location and remove it from the UI|
|address|string|false|none|none|
|geoLocation|string|false|none|NOTE: For brevity this option has been set to a string. Any valid GeoJSON object<br>will be accepted for this field. Check https://geojson.org/ for details.|

#### Enumerated Values

|Property|Value|
|---|---|
|geoLocation|GeoJSON|

<h2 id="tocS_UpdateMQTTSettingsRequest">UpdateMQTTSettingsRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatemqttsettingsrequest"></a>
<a id="schema_UpdateMQTTSettingsRequest"></a>
<a id="tocSupdatemqttsettingsrequest"></a>
<a id="tocsupdatemqttsettingsrequest"></a>

```json
{
  "enabled": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|enabled|boolean|true|none|Whether to enable MQTTSettings publishing for this account|

<h2 id="tocS_UpdateOrganisationRequest">UpdateOrganisationRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateorganisationrequest"></a>
<a id="schema_UpdateOrganisationRequest"></a>
<a id="tocSupdateorganisationrequest"></a>
<a id="tocsupdateorganisationrequest"></a>

```json
{
  "name": "string",
  "networks": [
    {
      "deleteNetwork": true,
      "name": "string",
      "username": "string",
      "password": "string"
    }
  ],
  "preferences": {
    "tags": {
      "ble": true,
      "rfid": true
    },
    "readers": {
      "type": {
        "default": "FIXED",
        "enabled": [
          "FIXED"
        ]
      },
      "manufacturer": {
        "default": "ZEBRA",
        "enabled": [
          "ZEBRA"
        ]
      }
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Organisation name|
|networks|[[NetworkWithDeletionFlag](#schemanetworkwithdeletionflag)]|false|none|Update the list of networks attached to the organisation|
|preferences|[Preferences](#schemapreferences)|false|none|none|

<h2 id="tocS_UpdateReaderRequest">UpdateReaderRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatereaderrequest"></a>
<a id="schema_UpdateReaderRequest"></a>
<a id="tocSupdatereaderrequest"></a>
<a id="tocsupdatereaderrequest"></a>

```json
{
  "name": "string",
  "type": "FIXED",
  "archived": true,
  "locationId": "string",
  "location": {
    "name": "string",
    "level": "string"
  },
  "deviceId": "string",
  "network": {
    "name": "string",
    "username": "string",
    "password": "string"
  },
  "saveNetwork": true,
  "antennas": [
    {
      "name": "string",
      "port": 0,
      "locationId": "string",
      "location": {
        "name": "string",
        "level": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|type|[ReaderType](#schemareadertype)|false|none|none|
|archived|boolean|false|none|Boolean flag to to change the archived state of a reader|
|locationId|string|false|none|locationId is used for specifying an already existing location|
|location|object|false|none|If a location object is specified a new location will be created and<br>added to the locations table|
|» name|string|true|none|none|
|» level|string|false|none|none|
|deviceId|string|false|none|device ID for an IOTX3 or phone reader|
|network|object|false|none|Name of saved wifi network|
|» name|string|true|none|none|
|» username|string|false|none|none|
|» password|string|false|none|none|
|saveNetwork|boolean|false|none|When this flag is true it will save any wifi details to the account. It will be ignored if no networks are present|
|antennas|[object]|false|none|Additional antenna config. This will only take effect for Virtual or Portal readers|
|» name|string|false|none|none|
|» port|number(float)|true|none|none|
|» locationId|string|false|none|none|
|» location|object|false|none|none|
|»» name|string|true|none|none|
|»» level|string|false|none|none|

<h2 id="tocS_UpdateTriggerRequest">UpdateTriggerRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdatetriggerrequest"></a>
<a id="schema_UpdateTriggerRequest"></a>
<a id="tocSupdatetriggerrequest"></a>
<a id="tocsupdatetriggerrequest"></a>

```json
{
  "name": "string",
  "enabled": true,
  "actions": [
    {
      "type": "Webhook",
      "endpoint": "string"
    }
  ],
  "subjectRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ],
  "locationRules": [
    {
      "type": "MatchName",
      "match": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|The name of the trigger, for easily identifying the trigger<br>and its purpose|
|enabled|boolean|false|none|Change the status of the trigger, disabled triggers will not fire|
|actions|[[Action](#schemaaction)]|false|none|Change the actions that fire for this trigger, you must send the<br>entire array as part of the request.|
|subjectRules|[[Rule](#schemarule)]|false|none|Change the subject rules to filter the events that cause this<br>trigger to fire, you must send the entire array as part of<br>the request.|
|locationRules|[[Rule](#schemarule)]|false|none|Change the location rules to filter the events that cause this<br>trigger to fire, you must send the entire array as part of<br>the request.<br><br>NOTE: This is only allowed for some events|

<h2 id="tocS_UpdateUserRequest">UpdateUserRequest</h2>
<!-- backwards compatibility -->
<a id="schemaupdateuserrequest"></a>
<a id="schema_UpdateUserRequest"></a>
<a id="tocSupdateuserrequest"></a>
<a id="tocsupdateuserrequest"></a>

```json
{
  "name": "string",
  "role": "string",
  "organisation": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|The User's full name NOTE: We do not enforce unique names|
|role|string|false|none|The role ID the new user will be assigned|
|organisation|string|false|none|If you have system-admin permissions you can move users<br>between organisations|

<h2 id="tocS_UploadAssetsError">UploadAssetsError</h2>
<!-- backwards compatibility -->
<a id="schemauploadassetserror"></a>
<a id="schema_UploadAssetsError"></a>
<a id="tocSuploadassetserror"></a>
<a id="tocsuploadassetserror"></a>

```json
{
  "data": [
    {
      "index": 0,
      "errors": [
        {
          "type": "TagsExistError",
          "message": "string",
          "conflicts": [
            {
              "tagId": "string",
              "type": "LOCATION",
              "id": "string"
            }
          ]
        }
      ]
    }
  ],
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|[[TagErrorInList](#schematagerrorinlist)]|true|none|none|
|message|string|true|none|none|

<h2 id="tocS_UploadAssetsErrorResponse">UploadAssetsErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemauploadassetserrorresponse"></a>
<a id="schema_UploadAssetsErrorResponse"></a>
<a id="tocSuploadassetserrorresponse"></a>
<a id="tocsuploadassetserrorresponse"></a>

```json
{
  "message": "string"
}

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[DefaultError](#schemadefaulterror)|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UploadAssetsError](#schemauploadassetserror)|false|none|none|

<h2 id="tocS_UploadAssetsRequest">UploadAssetsRequest</h2>
<!-- backwards compatibility -->
<a id="schemauploadassetsrequest"></a>
<a id="schema_UploadAssetsRequest"></a>
<a id="tocSuploadassetsrequest"></a>
<a id="tocsuploadassetsrequest"></a>

```json
{
  "data": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|data|string|true|none|NOTE: For brevity this option has been set to a string.<br>Any string or buffer will be accepted.|

<h2 id="tocS_UserEmbedField">UserEmbedField</h2>
<!-- backwards compatibility -->
<a id="schemauserembedfield"></a>
<a id="schema_UserEmbedField"></a>
<a id="tocSuserembedfield"></a>
<a id="tocsuserembedfield"></a>

```json
"meta"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|meta|

<h2 id="tocS_UserType">UserType</h2>
<!-- backwards compatibility -->
<a id="schemausertype"></a>
<a id="schema_UserType"></a>
<a id="tocSusertype"></a>
<a id="tocsusertype"></a>

```json
"INTERNAL"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|INTERNAL|
|*anonymous*|EXTERNAL|

<h2 id="tocS_WebhookAction">WebhookAction</h2>
<!-- backwards compatibility -->
<a id="schemawebhookaction"></a>
<a id="schema_WebhookAction"></a>
<a id="tocSwebhookaction"></a>
<a id="tocswebhookaction"></a>

```json
{
  "type": "Webhook",
  "endpoint": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|true|none|none|
|endpoint|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|Webhook|

