---
title: Aukai Core API
language_tabs:
  - http: HTTP
  - shell: CURL
  - go: Go
  - javascript: JavaScript
  - python: Python
  - ruby: Ruby
toc_footers: []
includes:
  - errors
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="aukai-core-api">Aukai Core API v0.1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

The Auaki Core API provides programmatic access to your Auakai Warehouses and Logistics Assets

Base URLs:

* <a href="http://aukai.io/">http://aukai.io/</a>

* <a href="https://aukai.io/">https://aukai.io/</a>

<a href="https://aukai.io/m0/terms">Terms of service</a>
Email: <a href="mailto:api.support@aukai.io">API Support</a> Web: <a href="https://aukai.io/support#api">API Support</a> 
License: <a href="http://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

# Authentication

* API Key (ApiKeyAuth)
    - Parameter Name: **Authorization**, in: header. 

<h1 id="aukai-core-api-address">address</h1>

## List Addresses

> Code samples

```http
GET http://aukai.io/address/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/address/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/address/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/address/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/address/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/address/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /address/`

Lists Addresses

> Example responses

> 200 Response

```json
[
  {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  }
]
```

<h3 id="list-addresses-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-addresses-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.Address](#schemamodel.address)]|false|none|none|
|» building_name|string|false|none|BuildingName is the name of the building, e.g., TriSeven Building|
|» country_code|string|false|none|CountryCode abbreviation|
|» country_name|string|false|none|none|
|» created_at|string|false|none|none|
|» deleted_at|string|false|none|none|
|» district_name|string|false|none|BlockBldgName is the name the block and building number|
|» formatted|string|false|none|Formatted address for display in the target language|
|» geo_coder|string|false|none|GeoCoder is the system that was used to resolve this address|
|» geo_coder_ref|string|false|none|GeoCoderRef is the reference within the system used to geocode this Address|
|» id|integer|false|none|none|
|» lang|string|false|none|Lang is th language in which the address is registered|
|» lat|number|false|none|Lat is the GPS latitude|
|» lng|number|false|none|Lon is the GPS longitude|
|» machi_name|string|false|none|MachiName is the name of the town|
|» muni_name|string|false|none|MuniName is the name of the municipality|
|» postal_code|string|false|none|none|
|» region_code|integer|false|none|RegionCode is the code of the region|
|» region_name|string|false|none|RegionName is the name of the region|
|» updated_at|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Create Address

> Code samples

```http
POST http://aukai.io/address/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/address/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/address/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/address/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/address/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/address/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /address/`

Create a Address

> Body parameter

```json
{
  "building_name": "TriSeven Building",
  "country_code": "JP",
  "country_name": "Japan",
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "district_name": "5-10",
  "formatted": "string",
  "geo_coder": "string",
  "geo_coder_ref": "string",
  "id": 0,
  "lang": "ja_jp",
  "lat": 0,
  "lng": 0,
  "machi_name": "浅草",
  "muni_name": "台東区",
  "postal_code": "110-0014",
  "region_code": 13,
  "region_name": "東京都",
  "updated_at": "2019-06-18T05:07:22Z"
}
```

<h3 id="create-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[model.Address](#schemamodel.address)|true|the address to create|

> Example responses

> 200 Response

```json
{
  "building_name": "TriSeven Building",
  "country_code": "JP",
  "country_name": "Japan",
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "district_name": "5-10",
  "formatted": "string",
  "geo_coder": "string",
  "geo_coder_ref": "string",
  "id": 0,
  "lang": "ja_jp",
  "lat": 0,
  "lng": 0,
  "machi_name": "浅草",
  "muni_name": "台東区",
  "postal_code": "110-0014",
  "region_code": 13,
  "region_name": "東京都",
  "updated_at": "2019-06-18T05:07:22Z"
}
```

<h3 id="create-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Address](#schemamodel.address)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Get Address by ID

> Code samples

```http
GET http://aukai.io/address/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/address/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/address/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/address/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/address/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/address/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /address/{id}`

Retrieve a Address

> Example responses

> 200 Response

```json
{
  "building_name": "TriSeven Building",
  "country_code": "JP",
  "country_name": "Japan",
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "district_name": "5-10",
  "formatted": "string",
  "geo_coder": "string",
  "geo_coder_ref": "string",
  "id": 0,
  "lang": "ja_jp",
  "lat": 0,
  "lng": 0,
  "machi_name": "浅草",
  "muni_name": "台東区",
  "postal_code": "110-0014",
  "region_code": 13,
  "region_name": "東京都",
  "updated_at": "2019-06-18T05:07:22Z"
}
```

<h3 id="get-address-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Address](#schemamodel.address)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Update Address

> Code samples

```http
POST http://aukai.io/address/{id} HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/address/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/address/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/address/{id}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/address/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/address/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /address/{id}`

Update attributes of a Address

> Body parameter

```json
{
  "building_name": "TriSeven Building",
  "country_code": "JP",
  "country_name": "Japan",
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "district_name": "5-10",
  "formatted": "string",
  "geo_coder": "string",
  "geo_coder_ref": "string",
  "id": 0,
  "lang": "ja_jp",
  "lat": 0,
  "lng": 0,
  "machi_name": "浅草",
  "muni_name": "台東区",
  "postal_code": "110-0014",
  "region_code": 13,
  "region_name": "東京都",
  "updated_at": "2019-06-18T05:07:22Z"
}
```

<h3 id="update-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The address ID|
|body|body|[model.Address](#schemamodel.address)|true|attributes to change|

> Example responses

> 200 Response

```json
{
  "building_name": "TriSeven Building",
  "country_code": "JP",
  "country_name": "Japan",
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "district_name": "5-10",
  "formatted": "string",
  "geo_coder": "string",
  "geo_coder_ref": "string",
  "id": 0,
  "lang": "ja_jp",
  "lat": 0,
  "lng": 0,
  "machi_name": "浅草",
  "muni_name": "台東区",
  "postal_code": "110-0014",
  "region_code": 13,
  "region_name": "東京都",
  "updated_at": "2019-06-18T05:07:22Z"
}
```

<h3 id="update-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Address](#schemamodel.address)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Delete Address

> Code samples

```http
DELETE http://aukai.io/address/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X DELETE http://aukai.io/address/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://aukai.io/address/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/address/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.delete('http://aukai.io/address/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.delete 'http://aukai.io/address/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /address/{id}`

Delete a Address by ID

<h3 id="delete-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The address ID|

> Example responses

> 200 Response

```json
{
  "building_name": "TriSeven Building",
  "country_code": "JP",
  "country_name": "Japan",
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "district_name": "5-10",
  "formatted": "string",
  "geo_coder": "string",
  "geo_coder_ref": "string",
  "id": 0,
  "lang": "ja_jp",
  "lat": 0,
  "lng": 0,
  "machi_name": "浅草",
  "muni_name": "台東区",
  "postal_code": "110-0014",
  "region_code": 13,
  "region_name": "東京都",
  "updated_at": "2019-06-18T05:07:22Z"
}
```

<h3 id="delete-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The deleted address|[model.Address](#schemamodel.address)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-auth">auth</h1>

## Authenticate

> Code samples

```http
POST http://aukai.io/auth/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/auth/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

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
    req, err := http.NewRequest("POST", "http://aukai.io/auth/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://aukai.io/auth/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://aukai.io/auth/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://aukai.io/auth/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /auth/`

Authenticate a user by username:password credentials and
receive a JSON Web Token to authenticate subsequent API
requests.

> Body parameter

```json
{
  "avatar": "string",
  "email": "string",
  "id": 0,
  "language": "string",
  "name": "string",
  "password": "string",
  "roles": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "users": [
        {
          "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
          "company_id": 1,
          "created_at": "2019-06-18T05:07:22Z",
          "deleted_at": "2019-06-18T05:07:22Z",
          "email": "tanaka.suzuki@aukai.dev",
          "id": 0,
          "language": "ja",
          "name": "Tanaka Suzuki",
          "updated_at": "2019-06-18T05:07:22Z",
          "username": "string"
        }
      ]
    }
  ],
  "username": "string"
}
```

<h3 id="authenticate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[api.UserData](#schemaapi.userdata)|true|username and password|

> Example responses

> 200 Response

```json
{
  "accessToken": {
    "expiresAt": 0,
    "token": "string"
  },
  "refreshToken": {
    "expiresAt": 0,
    "token": "string"
  },
  "status": "string",
  "user": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  }
}
```

<h3 id="authenticate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[api.AuthToken](#schemaapi.authtoken)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Authentication failed|[api.AuthStatus](#schemaapi.authstatus)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|JWT could not be generated|[api.AuthStatus](#schemaapi.authstatus)|

<aside class="success">
This operation does not require authentication
</aside>

## Refresh JWT

> Code samples

```http
POST http://aukai.io/auth/refresh HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/auth/refresh \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

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
    req, err := http.NewRequest("POST", "http://aukai.io/auth/refresh", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://aukai.io/auth/refresh',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://aukai.io/auth/refresh', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://aukai.io/auth/refresh',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /auth/refresh`

Issues a new valid JSON Web Token if the provided Refresh Token
is valid and has not expired.

> Body parameter

```json
{
  "token": "string"
}
```

<h3 id="refresh-jwt-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[api.RefreshTokenData](#schemaapi.refreshtokendata)|true|refresh token provided by /auth/|

> Example responses

> 200 Response

```json
{
  "accessToken": {
    "expiresAt": 0,
    "token": "string"
  },
  "refreshToken": {
    "expiresAt": 0,
    "token": "string"
  },
  "status": "string",
  "user": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  }
}
```

<h3 id="refresh-jwt-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[api.AuthToken](#schemaapi.authtoken)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Refresh token invalid or not provided|[api.AuthStatus](#schemaapi.authstatus)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|JWT could not be generated|[api.AuthStatus](#schemaapi.authstatus)|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|Token|string||JSON Web Token|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="aukai-core-api-company">company</h1>

## List Companies

> Code samples

```http
GET http://aukai.io/company/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/company/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/company/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/company/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/company/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/company/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /company/`

Lists Companies

> Example responses

> 200 Response

```json
[
  {
    "address_en": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "address_ja": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "created_at": "2019-06-18T05:07:22Z",
    "created_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "deleted_at": "2019-06-18T05:07:22Z",
    "id": 0,
    "name_en": "string",
    "name_ja": "string",
    "phone": "string",
    "photos": [
      {
        "attribution": "string",
        "company_id": 0,
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "id": 0,
        "name": "string",
        "ref": "string",
        "ref_type": "string",
        "updated_at": "2019-06-18T05:07:22Z",
        "url": "string",
        "warehouse_id": 0
      }
    ],
    "updated_at": "2019-06-18T05:07:22Z",
    "updated_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "url": "string"
  }
]
```

<h3 id="list-companies-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-companies-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.Company](#schemamodel.company)]|false|none|none|
|» address_en|[model.Address](#schemamodel.address)|false|none|none|
|»» building_name|string|false|none|BuildingName is the name of the building, e.g., TriSeven Building|
|»» country_code|string|false|none|CountryCode abbreviation|
|»» country_name|string|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» district_name|string|false|none|BlockBldgName is the name the block and building number|
|»» formatted|string|false|none|Formatted address for display in the target language|
|»» geo_coder|string|false|none|GeoCoder is the system that was used to resolve this address|
|»» geo_coder_ref|string|false|none|GeoCoderRef is the reference within the system used to geocode this Address|
|»» id|integer|false|none|none|
|»» lang|string|false|none|Lang is th language in which the address is registered|
|»» lat|number|false|none|Lat is the GPS latitude|
|»» lng|number|false|none|Lon is the GPS longitude|
|»» machi_name|string|false|none|MachiName is the name of the town|
|»» muni_name|string|false|none|MuniName is the name of the municipality|
|»» postal_code|string|false|none|none|
|»» region_code|integer|false|none|RegionCode is the code of the region|
|»» region_name|string|false|none|RegionName is the name of the region|
|»» updated_at|string|false|none|none|
|» address_ja|[model.Address](#schemamodel.address)|false|none|none|
|» created_at|string|false|none|none|
|» created_by|[model.User](#schemamodel.user)|false|none|none|
|»» avatar|string|false|none|none|
|»» company_id|integer|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» email|string|true|none|none|
|»» id|integer|false|none|none|
|»» language|string|false|none|none|
|»» name|string|true|none|none|
|»» updated_at|string|false|none|none|
|»» username|string|true|none|none|
|» deleted_at|string|false|none|none|
|» id|integer|false|none|none|
|» name_en|string|true|none|the name in English for the company required: true|
|» name_ja|string|true|none|the name in Japanese for the company required: true|
|» phone|string|false|none|Phone number with country code for contacting the company required: false example: +81 03-4560-3232|
|» photos|[[model.Photo](#schemamodel.photo)]|false|none|photos associated with the company, e.g., logos and buildings required: false|
|»» attribution|string|false|none|Attribution holds the credit for the photographer, or creator of the image|
|»» company_id|integer|false|none|CompanyID associates this Photo with a Company|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» id|integer|false|none|none|
|»» name|string|true|none|Name is the name that should be displayed for the image|
|»» ref|string|false|none|Ref is the ID use to retrieve the image|
|»» ref_type|string|false|none|RefType is the name of the system hosting the image|
|»» updated_at|string|false|none|none|
|»» url|string|false|none|URL is a direct reference URL to the image, or the base64 encoded image|
|»» warehouse_id|integer|false|none|WarehouseID associates this Photo with a Warehouse|
|» updated_at|string|false|none|none|
|» updated_by|[model.User](#schemamodel.user)|false|none|none|
|» url|string|false|none|Website or other reference webpage for the company required: true example: https://aukai.io|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Create Company

> Code samples

```http
POST http://aukai.io/company/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/company/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/company/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/company/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/company/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/company/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /company/`

Create a Company

> Body parameter

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="create-company-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[model.Company](#schemamodel.company)|true|the company to create|

> Example responses

> 200 Response

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="create-company-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Company](#schemamodel.company)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Get Company by ID

> Code samples

```http
GET http://aukai.io/company/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/company/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/company/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/company/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/company/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/company/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /company/{id}`

Retrieve a Company

> Example responses

> 200 Response

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="get-company-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Company](#schemamodel.company)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Update Company

> Code samples

```http
POST http://aukai.io/company/{id} HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/company/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/company/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/company/{id}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/company/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/company/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /company/{id}`

Update attributes of a Company

> Body parameter

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="update-company-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The company ID|
|body|body|[model.Company](#schemamodel.company)|true|attributes to change|

> Example responses

> 200 Response

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="update-company-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Company](#schemamodel.company)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Delete Company

> Code samples

```http
DELETE http://aukai.io/company/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X DELETE http://aukai.io/company/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://aukai.io/company/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/company/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.delete('http://aukai.io/company/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.delete 'http://aukai.io/company/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /company/{id}`

Delete a Company by ID

<h3 id="delete-company-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The company ID|

> Example responses

> 200 Response

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="delete-company-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The deleted company|[model.Company](#schemamodel.company)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## List Company's Warehouses

> Code samples

```http
GET http://aukai.io/company/{id}/warehouse HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/company/{id}/warehouse \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/company/{id}/warehouse", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/company/{id}/warehouse',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/company/{id}/warehouse', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/company/{id}/warehouse',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /company/{id}/warehouse`

Provides a list of Warehouse objects  associated with a company

<h3 id="list-company's-warehouses-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|Company ID|

> Example responses

> 200 Response

```json
[
  {
    "address_en": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "address_ja": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "attrs": [
      {
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "desc_en": "string",
        "desc_ja": "string",
        "id": 0,
        "key": "temp.const",
        "type": "feature",
        "updated_at": "2019-06-18T05:07:22Z",
        "value_en": "Temperature Controlled",
        "value_ja": "定温倉庫"
      }
    ],
    "company_id": 0,
    "created_at": "2019-06-18T05:07:22Z",
    "created_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "deleted_at": "2019-06-18T05:07:22Z",
    "id": 0,
    "name_en": "string",
    "name_ja": "string",
    "parent": null,
    "parent_id": 0,
    "phone": "string",
    "photos": [
      {
        "attribution": "string",
        "company_id": 0,
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "id": 0,
        "name": "string",
        "ref": "string",
        "ref_type": "string",
        "updated_at": "2019-06-18T05:07:22Z",
        "url": "string",
        "warehouse_id": 0
      }
    ],
    "sqmtr": 0,
    "type": "string",
    "updated_at": "2019-06-18T05:07:22Z",
    "updated_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "url": "string"
  }
]
```

<h3 id="list-company's-warehouses-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-company's-warehouses-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.Warehouse](#schemamodel.warehouse)]|false|none|none|
|» address_en|[model.Address](#schemamodel.address)|false|none|none|
|»» building_name|string|false|none|BuildingName is the name of the building, e.g., TriSeven Building|
|»» country_code|string|false|none|CountryCode abbreviation|
|»» country_name|string|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» district_name|string|false|none|BlockBldgName is the name the block and building number|
|»» formatted|string|false|none|Formatted address for display in the target language|
|»» geo_coder|string|false|none|GeoCoder is the system that was used to resolve this address|
|»» geo_coder_ref|string|false|none|GeoCoderRef is the reference within the system used to geocode this Address|
|»» id|integer|false|none|none|
|»» lang|string|false|none|Lang is th language in which the address is registered|
|»» lat|number|false|none|Lat is the GPS latitude|
|»» lng|number|false|none|Lon is the GPS longitude|
|»» machi_name|string|false|none|MachiName is the name of the town|
|»» muni_name|string|false|none|MuniName is the name of the municipality|
|»» postal_code|string|false|none|none|
|»» region_code|integer|false|none|RegionCode is the code of the region|
|»» region_name|string|false|none|RegionName is the name of the region|
|»» updated_at|string|false|none|none|
|» address_ja|[model.Address](#schemamodel.address)|false|none|none|
|» attrs|[[model.WarehouseAttr](#schemamodel.warehouseattr)]|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» desc_en|string|false|none|none|
|»» desc_ja|string|false|none|none|
|»» id|integer|false|none|none|
|»» key|string|false|none|none|
|»» type|string|false|none|none|
|»» updated_at|string|false|none|none|
|»» value_en|string|false|none|none|
|»» value_ja|string|false|none|none|
|» company_id|integer|false|none|none|
|» created_at|string|false|none|none|
|» created_by|[model.User](#schemamodel.user)|false|none|none|
|»» avatar|string|false|none|none|
|»» company_id|integer|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» email|string|true|none|none|
|»» id|integer|false|none|none|
|»» language|string|false|none|none|
|»» name|string|true|none|none|
|»» updated_at|string|false|none|none|
|»» username|string|true|none|none|
|» deleted_at|string|false|none|none|
|» id|integer|false|none|none|
|» name_en|string|true|none|none|
|» name_ja|string|true|none|none|
|» parent|[model.Warehouse](#schemamodel.warehouse)|false|none|none|
|» parent_id|integer|false|none|none|
|» phone|string|false|none|none|
|» photos|[[model.Photo](#schemamodel.photo)]|false|none|none|
|»» attribution|string|false|none|Attribution holds the credit for the photographer, or creator of the image|
|»» company_id|integer|false|none|CompanyID associates this Photo with a Company|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» id|integer|false|none|none|
|»» name|string|true|none|Name is the name that should be displayed for the image|
|»» ref|string|false|none|Ref is the ID use to retrieve the image|
|»» ref_type|string|false|none|RefType is the name of the system hosting the image|
|»» updated_at|string|false|none|none|
|»» url|string|false|none|URL is a direct reference URL to the image, or the base64 encoded image|
|»» warehouse_id|integer|false|none|WarehouseID associates this Photo with a Warehouse|
|» sqmtr|integer|false|none|Sqmt is the usable square meters of the space|
|» type|string|false|none|none|
|» updated_at|string|false|none|none|
|» updated_by|[model.User](#schemamodel.user)|false|none|none|
|» url|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-contact">contact</h1>

## Create Contact Request

> Code samples

```http
POST http://aukai.io/contact/ HTTP/1.1
Host: aukai.io
Content-Type: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/contact/ \
  -H 'Content-Type: application/json'

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
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/contact/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json'

};

$.ajax({
  url: 'http://aukai.io/contact/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('http://aukai.io/contact/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json'
}

result = RestClient.post 'http://aukai.io/contact/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /contact/`

Create a Contact Request and notify Aukai staff.

> Body parameter

```json
{
  "company": "XYZ Corporation",
  "email": "user@aukai.dev",
  "firstName": "Taro",
  "lastName": "Suzuki",
  "message": "string",
  "phone": "+81 03-0000-0000"
}
```

<h3 id="create-contact-request-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[api.ContactRequest](#schemaapi.contactrequest)|true|the contact details of the user|

<h3 id="create-contact-request-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="aukai-core-api-metrics">metrics</h1>

## Get system metrics

> Code samples

```http
GET http://aukai.io/metrics/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/metrics/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/metrics/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/metrics/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/metrics/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/metrics/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /metrics/`

Retrieve a summary of the data registered in the system and
available to the user

> Example responses

> 200 Response

```json
{
  "companies": 200,
  "sqmt": 100000000,
  "users": 4000,
  "warehouses": 1000
}
```

<h3 id="get-system-metrics-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[api.Metrics](#schemaapi.metrics)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-network">network</h1>

## List Networks

<a id="opIdget-companies"></a>

> Code samples

```http
GET http://aukai.io/network/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/network/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/network/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/network/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/network/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/network/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /network/`

Lists Networks

> Example responses

> 200 Response

```json
[
  {
    "comment": "string",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "created_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "deleted_at": "2019-06-18T05:07:22Z",
    "file": {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "dir": "string",
      "ext": "png",
      "filename": "string",
      "id": 1,
      "mime_type": "image/png",
      "ref": "df6301cfb58750fd8707611cea13e9b3",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
    },
    "id": 0,
    "status": "requested",
    "updated_at": "2019-06-18T05:07:22Z",
    "updated_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "warehouse_id": 1
  }
]
```

<h3 id="list-networks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-networks-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.NetworkAssoc](#schemamodel.networkassoc)]|false|none|none|
|» comment|string|false|none|Comment is not stored in the Association, but is extracted from requests and stored in a NetworkEvent object. I would prefer not to have any JSON value here, but we need it in order to enable automatic extraction from submitted JSON. In the ideal scenario we'd be able to extract the comment, but not include it in JSON responses.|
|» company_id|integer|false|none|The Company side of the network association. This will be the company to which the requesting user belongs.|
|» created_at|string|false|none|none|
|» created_by|[model.User](#schemamodel.user)|false|none|none|
|»» avatar|string|false|none|none|
|»» company_id|integer|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» email|string|true|none|none|
|»» id|integer|false|none|none|
|»» language|string|false|none|none|
|»» name|string|true|none|none|
|»» updated_at|string|false|none|none|
|»» username|string|true|none|none|
|» deleted_at|string|false|none|none|
|» file|[storedfile.File](#schemastoredfile.file)|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» dir|string|false|none|Dir is the company ID|
|»» ext|string|false|none|Ext is the extension for the file if it's written to a filesystem|
|»» filename|string|true|none|Filename is the name given to the file, it's usually the same as Ref|
|»» id|integer|false|none|none|
|»» mime_type|string|false|none|MimeType of the file [usually auto detected]|
|»» ref|string|true|none|Ref is the key used to retrieve the file from our object store|
|»» updated_at|string|false|none|none|
|»» url|string|false|none|URL for external systems to use to access the file|
|» id|integer|false|none|none|
|» status|string|false|none|Status is the connection status for the Warehouse and Company|
|» updated_at|string|false|none|none|
|» updated_by|[model.User](#schemamodel.user)|false|none|none|
|» warehouse_id|integer|false|none|The Warehouse side of the network association.|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Create Network

<a id="opIdcreate-network"></a>

> Code samples

```http
POST http://aukai.io/network/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/network/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/network/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/network/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/network/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/network/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /network/`

Create a Network

> Body parameter

```json
{
  "comment": "string",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "file": {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  },
  "id": 0,
  "status": "requested",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "warehouse_id": 1
}
```

<h3 id="create-network-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[model.NetworkAssoc](#schemamodel.networkassoc)|true|the network to create|

> Example responses

> 200 Response

```json
{
  "comment": "string",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "file": {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  },
  "id": 0,
  "status": "requested",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "warehouse_id": 1
}
```

<h3 id="create-network-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.NetworkAssoc](#schemamodel.networkassoc)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Get Network by ID

<a id="opIdget-network-by-id"></a>

> Code samples

```http
GET http://aukai.io/network/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/network/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/network/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/network/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/network/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/network/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /network/{id}`

Retrieve a Network

> Example responses

> 200 Response

```json
{
  "comment": "string",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "file": {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  },
  "id": 0,
  "status": "requested",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "warehouse_id": 1
}
```

<h3 id="get-network-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.NetworkAssoc](#schemamodel.networkassoc)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Update Network

<a id="opIdupdate-network"></a>

> Code samples

```http
POST http://aukai.io/network/{id} HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/network/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/network/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/network/{id}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/network/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/network/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /network/{id}`

Update attributes of a Network

> Body parameter

```json
{
  "comment": "string",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "file": {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  },
  "id": 0,
  "status": "requested",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "warehouse_id": 1
}
```

<h3 id="update-network-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The network ID|
|body|body|[model.NetworkAssoc](#schemamodel.networkassoc)|true|attributes to change|

> Example responses

> 200 Response

```json
{
  "comment": "string",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "file": {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  },
  "id": 0,
  "status": "requested",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "warehouse_id": 1
}
```

<h3 id="update-network-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.NetworkAssoc](#schemamodel.networkassoc)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Delete Network

<a id="opIddelete-network-by-id"></a>

> Code samples

```http
DELETE http://aukai.io/network/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X DELETE http://aukai.io/network/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://aukai.io/network/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/network/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.delete('http://aukai.io/network/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.delete 'http://aukai.io/network/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /network/{id}`

Delete a Network by ID

<h3 id="delete-network-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The network ID|

> Example responses

> 200 Response

```json
{
  "comment": "string",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "file": {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  },
  "id": 0,
  "status": "requested",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "warehouse_id": 1
}
```

<h3 id="delete-network-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The deleted network|[model.NetworkAssoc](#schemamodel.networkassoc)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## List Network Change Events

> Code samples

```http
GET http://aukai.io/network/{id}/events HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/network/{id}/events \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/network/{id}/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/network/{id}/events',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/network/{id}/events', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/network/{id}/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /network/{id}/events`

Retrieves the state changes for the network. Files added to a
Network will be stored in the change events and not in the
actual Network

> Example responses

> 200 Response

```json
[
  {
    "comment": "Lorem Ipsum ...",
    "created_at": "2019-06-18T05:07:22Z",
    "created_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "deleted_at": "2019-06-18T05:07:22Z",
    "file": {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "dir": "string",
      "ext": "png",
      "filename": "string",
      "id": 1,
      "mime_type": "image/png",
      "ref": "df6301cfb58750fd8707611cea13e9b3",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
    },
    "id": 0,
    "network_assoc_id": 1,
    "start": "requested",
    "stop": "approved",
    "updated_at": "2019-06-18T05:07:22Z"
  }
]
```

<h3 id="list-network-change-events-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[resource.NotFoundError](#schemaresource.notfounderror)|

<h3 id="list-network-change-events-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.NetworkEvent](#schemamodel.networkevent)]|false|none|none|
|» comment|string|false|none|Comment is a note attached to the change even by the user that initiates the chagne|
|» created_at|string|false|none|none|
|» created_by|[model.User](#schemamodel.user)|false|none|none|
|»» avatar|string|false|none|none|
|»» company_id|integer|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» email|string|true|none|none|
|»» id|integer|false|none|none|
|»» language|string|false|none|none|
|»» name|string|true|none|none|
|»» updated_at|string|false|none|none|
|»» username|string|true|none|none|
|» deleted_at|string|false|none|none|
|» file|[storedfile.File](#schemastoredfile.file)|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» dir|string|false|none|Dir is the company ID|
|»» ext|string|false|none|Ext is the extension for the file if it's written to a filesystem|
|»» filename|string|true|none|Filename is the name given to the file, it's usually the same as Ref|
|»» id|integer|false|none|none|
|»» mime_type|string|false|none|MimeType of the file [usually auto detected]|
|»» ref|string|true|none|Ref is the key used to retrieve the file from our object store|
|»» updated_at|string|false|none|none|
|»» url|string|false|none|URL for external systems to use to access the file|
|» id|integer|false|none|none|
|» network_assoc_id|integer|false|none|none|
|» start|string|false|none|StartState is the state of the Network connection before this change Event|
|» stop|string|false|none|StopState is the state of the Network connection after this change Event is applied|
|» updated_at|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-places">places</h1>

## Address AutoComplete

> Code samples

```http
GET http://aukai.io/place/autocomplete HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/place/autocomplete \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/place/autocomplete", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/place/autocomplete',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/place/autocomplete', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/place/autocomplete',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /place/autocomplete`

AutoComplete an address in the specified language

> Body parameter

```json
{
  "address": "string",
  "lang": "string",
  "type": "string"
}
```

<h3 id="address-autocomplete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[place.AutoCompleteReq](#schemaplace.autocompletereq)|true|request details|

> Example responses

> 400 Response

```json
"string"
```

<h3 id="address-autocomplete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Google AutoComplete response|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|invalid requests|string|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|unable to fullfil request|string|

<h3 id="address-autocomplete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-file">file</h1>

## Get File contents by Reference

> Code samples

```http
GET http://aukai.io/ref/{ref}/file HTTP/1.1
Host: aukai.io
Accept: image/jpeg

```

```shell
# You can also use wget
curl -X GET http://aukai.io/ref/{ref}/file \
  -H 'Accept: image/jpeg'

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"image/jpeg"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/ref/{ref}/file", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'image/jpeg'

};

$.ajax({
  url: 'http://aukai.io/ref/{ref}/file',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'image/jpeg'
}

r = requests.get('http://aukai.io/ref/{ref}/file', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'image/jpeg'
}

result = RestClient.get 'http://aukai.io/ref/{ref}/file',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /ref/{ref}/file`

Retrieve the contents of a StoredFile by the associated reference.

> Example responses

> 200 Response

<h3 id="get-file-contents-by-reference-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|the raw contents of the file|string|

<aside class="success">
This operation does not require authentication
</aside>

## List Stored Files

> Code samples

```http
GET http://aukai.io/stored-file/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/stored-file/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/stored-file/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/stored-file/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/stored-file/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/stored-file/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /stored-file/`

Lists Stored Files

> Example responses

> 200 Response

```json
[
  {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  }
]
```

<h3 id="list-stored-files-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-stored-files-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[storedfile.File](#schemastoredfile.file)]|false|none|none|
|» created_at|string|false|none|none|
|» deleted_at|string|false|none|none|
|» dir|string|false|none|Dir is the company ID|
|» ext|string|false|none|Ext is the extension for the file if it's written to a filesystem|
|» filename|string|true|none|Filename is the name given to the file, it's usually the same as Ref|
|» id|integer|false|none|none|
|» mime_type|string|false|none|MimeType of the file [usually auto detected]|
|» ref|string|true|none|Ref is the key used to retrieve the file from our object store|
|» updated_at|string|false|none|none|
|» url|string|false|none|URL for external systems to use to access the file|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Create Stored File

> Code samples

```http
POST http://aukai.io/stored-file/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/stored-file/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/stored-file/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/stored-file/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/stored-file/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/stored-file/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /stored-file/`

Create a Stored File

> Body parameter

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "dir": "string",
  "ext": "png",
  "filename": "string",
  "id": 1,
  "mime_type": "image/png",
  "ref": "df6301cfb58750fd8707611cea13e9b3",
  "updated_at": "2019-06-18T05:07:22Z",
  "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
}
```

<h3 id="create-stored-file-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[storedfile.File](#schemastoredfile.file)|true|the file to create|

> Example responses

> 200 Response

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "dir": "string",
  "ext": "png",
  "filename": "string",
  "id": 1,
  "mime_type": "image/png",
  "ref": "df6301cfb58750fd8707611cea13e9b3",
  "updated_at": "2019-06-18T05:07:22Z",
  "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
}
```

<h3 id="create-stored-file-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[storedfile.File](#schemastoredfile.file)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Get File contents by ID

> Code samples

```http
GET http://aukai.io/stored-file/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/stored-file/{id} \
  -H 'Accept: application/json'

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
    req, err := http.NewRequest("GET", "http://aukai.io/stored-file/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://aukai.io/stored-file/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://aukai.io/stored-file/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://aukai.io/stored-file/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /stored-file/{id}`

Retrieve the contents of a StoredFile by the associated ID.

> Example responses

> 200 Response

```json
"string"
```

<h3 id="get-file-contents-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|the raw contents fo the file|string|

<aside class="success">
This operation does not require authentication
</aside>

## Update File

> Code samples

```http
POST http://aukai.io/stored-file/{id} HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/stored-file/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/stored-file/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/stored-file/{id}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/stored-file/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/stored-file/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /stored-file/{id}`

Update attributes of a File

> Body parameter

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "dir": "string",
  "ext": "png",
  "filename": "string",
  "id": 1,
  "mime_type": "image/png",
  "ref": "df6301cfb58750fd8707611cea13e9b3",
  "updated_at": "2019-06-18T05:07:22Z",
  "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
}
```

<h3 id="update-file-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The file ID|
|body|body|[storedfile.File](#schemastoredfile.file)|true|attributes to change|

> Example responses

> 200 Response

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "dir": "string",
  "ext": "png",
  "filename": "string",
  "id": 1,
  "mime_type": "image/png",
  "ref": "df6301cfb58750fd8707611cea13e9b3",
  "updated_at": "2019-06-18T05:07:22Z",
  "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
}
```

<h3 id="update-file-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[storedfile.File](#schemastoredfile.file)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Delete File

> Code samples

```http
DELETE http://aukai.io/stored-file/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X DELETE http://aukai.io/stored-file/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://aukai.io/stored-file/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/stored-file/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.delete('http://aukai.io/stored-file/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.delete 'http://aukai.io/stored-file/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /stored-file/{id}`

Delete a File by ID

<h3 id="delete-file-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The file ID|

> Example responses

> 200 Response

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "dir": "string",
  "ext": "png",
  "filename": "string",
  "id": 1,
  "mime_type": "image/png",
  "ref": "df6301cfb58750fd8707611cea13e9b3",
  "updated_at": "2019-06-18T05:07:22Z",
  "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
}
```

<h3 id="delete-file-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The deleted file|[storedfile.File](#schemastoredfile.file)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-role">role</h1>

## List Roles

> Code samples

```http
GET http://aukai.io/roles/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/roles/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/roles/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/roles/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/roles/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/roles/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /roles/`

List Role names

> Example responses

> 200 Response

```json
[
  "string"
]
```

<h3 id="list-roles-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|e.g., 'admin', 'staff', 'user', 'guest'|Inline|

<h3 id="list-roles-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-user">user</h1>

## Get User

> Code samples

```http
GET http://aukai.io/user/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/user/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/user/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/user/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/user/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/user/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /user/`

Retrieve a User, by one of its paramters: id, username, or email

> Body parameter

```json
{
  "email": "tanaka.suzuki@aukai.io",
  "id": 1,
  "username": "tanaka"
}
```

<h3 id="get-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[api.UserQuery](#schemaapi.userquery)|true|user query|

> Example responses

> 200 Response

```json
{
  "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "email": "tanaka.suzuki@aukai.dev",
  "id": 0,
  "language": "ja",
  "name": "Tanaka Suzuki",
  "updated_at": "2019-06-18T05:07:22Z",
  "username": "string"
}
```

<h3 id="get-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.User](#schemamodel.user)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth, None
</aside>

## Create or Updated User

> Code samples

```http
POST http://aukai.io/user/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/user/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

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
    req, err := http.NewRequest("POST", "http://aukai.io/user/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: 'http://aukai.io/user/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://aukai.io/user/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://aukai.io/user/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /user/`

Create, or Update a User. If a user ID is provided that user
will be updated assuming the auth user has the necessary role,
or is the same user.

> Body parameter

```json
{
  "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "email": "tanaka.suzuki@aukai.dev",
  "id": 0,
  "language": "ja",
  "name": "Tanaka Suzuki",
  "updated_at": "2019-06-18T05:07:22Z",
  "username": "string"
}
```

<h3 id="create-or-updated-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[model.User](#schemamodel.user)|true|the user to create or update|

> Example responses

> 200 Response

```json
{
  "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "email": "tanaka.suzuki@aukai.dev",
  "id": 0,
  "language": "ja",
  "name": "Tanaka Suzuki",
  "updated_at": "2019-06-18T05:07:22Z",
  "username": "string"
}
```

<h3 id="create-or-updated-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.User](#schemamodel.user)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## List Auth User Casbin Roles

> Code samples

```http
GET http://aukai.io/user/casbin HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/user/casbin \
  -H 'Accept: application/json'

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
    req, err := http.NewRequest("GET", "http://aukai.io/user/casbin", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://aukai.io/user/casbin',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://aukai.io/user/casbin', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://aukai.io/user/casbin',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /user/casbin`

Provides list of Casbin roles for the authenticated user

> Example responses

> 200 Response

```json
[
  "string"
]
```

<h3 id="list-auth-user-casbin-roles-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-auth-user-casbin-roles-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Auth User Information

> Code samples

```http
GET http://aukai.io/user/info HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/user/info \
  -H 'Accept: application/json'

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
    req, err := http.NewRequest("GET", "http://aukai.io/user/info", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://aukai.io/user/info',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://aukai.io/user/info', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://aukai.io/user/info',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /user/info`

Provides information about the authenticated user

> Example responses

> 200 Response

```json
{
  "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "email": "tanaka.suzuki@aukai.dev",
  "id": 0,
  "language": "ja",
  "name": "Tanaka Suzuki",
  "updated_at": "2019-06-18T05:07:22Z",
  "username": "string"
}
```

<h3 id="auth-user-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.User](#schemamodel.user)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|

<h3 id="auth-user-information-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## List Auth User Roles

> Code samples

```http
GET http://aukai.io/user/roles HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/user/roles \
  -H 'Accept: application/json'

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
    req, err := http.NewRequest("GET", "http://aukai.io/user/roles", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://aukai.io/user/roles',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://aukai.io/user/roles', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://aukai.io/user/roles',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /user/roles`

Provides list of roles for the authenticated user

> Example responses

> 200 Response

```json
[
  {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "id": 0,
    "name": "string",
    "updated_at": "2019-06-18T05:07:22Z",
    "users": [
      {
        "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
        "company_id": 1,
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "email": "tanaka.suzuki@aukai.dev",
        "id": 0,
        "language": "ja",
        "name": "Tanaka Suzuki",
        "updated_at": "2019-06-18T05:07:22Z",
        "username": "string"
      }
    ]
  }
]
```

<h3 id="list-auth-user-roles-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-auth-user-roles-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.Role](#schemamodel.role)]|false|none|none|
|» created_at|string|false|none|none|
|» deleted_at|string|false|none|none|
|» id|integer|false|none|none|
|» name|string|true|none|none|
|» updated_at|string|false|none|none|
|» users|[[model.User](#schemamodel.user)]|false|none|none|
|»» avatar|string|false|none|none|
|»» company_id|integer|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» email|string|true|none|none|
|»» id|integer|false|none|none|
|»» language|string|false|none|none|
|»» name|string|true|none|none|
|»» updated_at|string|false|none|none|
|»» username|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Delete User

> Code samples

```http
DELETE http://aukai.io/user/{id} HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X DELETE http://aukai.io/user/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://aukai.io/user/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/user/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.delete('http://aukai.io/user/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.delete 'http://aukai.io/user/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /user/{id}`

Delete a User by ID

> Body parameter

```json
{
  "email": "tanaka.suzuki@aukai.io",
  "id": 1,
  "username": "tanaka"
}
```

<h3 id="delete-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|User ID|
|body|body|[api.UserQuery](#schemaapi.userquery)|false|user query|

> Example responses

> 200 Response

```json
{
  "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "email": "tanaka.suzuki@aukai.dev",
  "id": 0,
  "language": "ja",
  "name": "Tanaka Suzuki",
  "updated_at": "2019-06-18T05:07:22Z",
  "username": "string"
}
```

<h3 id="delete-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The deleted user|[model.User](#schemamodel.user)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## List Users

> Code samples

```http
GET http://aukai.io/users/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/users/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/users/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/users/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/users/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/users/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /users/`

Lists Users

> Example responses

> 200 Response

```json
[
  {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  }
]
```

<h3 id="list-users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-users-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.User](#schemamodel.user)]|false|none|none|
|» avatar|string|false|none|none|
|» company_id|integer|false|none|none|
|» created_at|string|false|none|none|
|» deleted_at|string|false|none|none|
|» email|string|true|none|none|
|» id|integer|false|none|none|
|» language|string|false|none|none|
|» name|string|true|none|none|
|» updated_at|string|false|none|none|
|» username|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-system">system</h1>

## Get Version

> Code samples

```http
GET http://aukai.io/version HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/version \
  -H 'Accept: application/json'

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
    req, err := http.NewRequest("GET", "http://aukai.io/version", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://aukai.io/version',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://aukai.io/version', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://aukai.io/version',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /version`

Provides information about the source of the current build, and
the deployment. The server uptime and available domains will
also be included.

> Example responses

> 200 Response

```json
{
  "branch": "master",
  "date": "2019-06-19T03:20:26Z",
  "domains": [
    "['https://aukai.io']"
  ],
  "uptime": "27h14m37.809030294s",
  "version": "1.0.0"
}
```

<h3 id="get-version-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[api.version](#schemaapi.version)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="aukai-core-api-warehouse-attr">warehouse-attr</h1>

## List WarehouseAttr

> Code samples

```http
GET http://aukai.io/warehouse-attr/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/warehouse-attr/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/warehouse-attr/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse-attr/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/warehouse-attr/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/warehouse-attr/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /warehouse-attr/`

Lists WarehouseAttrs

> Example responses

> 200 Response

```json
[
  {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "desc_en": "string",
    "desc_ja": "string",
    "id": 0,
    "key": "temp.const",
    "type": "feature",
    "updated_at": "2019-06-18T05:07:22Z",
    "value_en": "Temperature Controlled",
    "value_ja": "定温倉庫"
  }
]
```

<h3 id="list-warehouseattr-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-warehouseattr-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.WarehouseAttr](#schemamodel.warehouseattr)]|false|none|none|
|» created_at|string|false|none|none|
|» deleted_at|string|false|none|none|
|» desc_en|string|false|none|none|
|» desc_ja|string|false|none|none|
|» id|integer|false|none|none|
|» key|string|false|none|none|
|» type|string|false|none|none|
|» updated_at|string|false|none|none|
|» value_en|string|false|none|none|
|» value_ja|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Create WarehouseAttr

> Code samples

```http
POST http://aukai.io/warehouse-attr/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/warehouse-attr/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/warehouse-attr/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse-attr/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/warehouse-attr/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/warehouse-attr/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /warehouse-attr/`

Create a WarehouseAttr

> Body parameter

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "desc_en": "string",
  "desc_ja": "string",
  "id": 0,
  "key": "temp.const",
  "type": "feature",
  "updated_at": "2019-06-18T05:07:22Z",
  "value_en": "Temperature Controlled",
  "value_ja": "定温倉庫"
}
```

<h3 id="create-warehouseattr-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[model.WarehouseAttr](#schemamodel.warehouseattr)|true|the warehouse-attr to create|

> Example responses

> 200 Response

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "desc_en": "string",
  "desc_ja": "string",
  "id": 0,
  "key": "temp.const",
  "type": "feature",
  "updated_at": "2019-06-18T05:07:22Z",
  "value_en": "Temperature Controlled",
  "value_ja": "定温倉庫"
}
```

<h3 id="create-warehouseattr-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.WarehouseAttr](#schemamodel.warehouseattr)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Get WarehouseAttr by ID

> Code samples

```http
GET http://aukai.io/warehouse-attr/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/warehouse-attr/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/warehouse-attr/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse-attr/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/warehouse-attr/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/warehouse-attr/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /warehouse-attr/{id}`

Retrieve a WarehouseAttr

> Example responses

> 200 Response

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "desc_en": "string",
  "desc_ja": "string",
  "id": 0,
  "key": "temp.const",
  "type": "feature",
  "updated_at": "2019-06-18T05:07:22Z",
  "value_en": "Temperature Controlled",
  "value_ja": "定温倉庫"
}
```

<h3 id="get-warehouseattr-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.WarehouseAttr](#schemamodel.warehouseattr)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Update WarehouseAttr

> Code samples

```http
POST http://aukai.io/warehouse-attr/{id} HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/warehouse-attr/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/warehouse-attr/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse-attr/{id}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/warehouse-attr/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/warehouse-attr/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /warehouse-attr/{id}`

Update attributes of a WarehouseAttr

> Body parameter

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "desc_en": "string",
  "desc_ja": "string",
  "id": 0,
  "key": "temp.const",
  "type": "feature",
  "updated_at": "2019-06-18T05:07:22Z",
  "value_en": "Temperature Controlled",
  "value_ja": "定温倉庫"
}
```

<h3 id="update-warehouseattr-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The warehouse-attr ID|
|body|body|[model.WarehouseAttr](#schemamodel.warehouseattr)|true|attributes to change|

> Example responses

> 200 Response

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "desc_en": "string",
  "desc_ja": "string",
  "id": 0,
  "key": "temp.const",
  "type": "feature",
  "updated_at": "2019-06-18T05:07:22Z",
  "value_en": "Temperature Controlled",
  "value_ja": "定温倉庫"
}
```

<h3 id="update-warehouseattr-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.WarehouseAttr](#schemamodel.warehouseattr)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Delete WarehouseAttr

> Code samples

```http
DELETE http://aukai.io/warehouse-attr/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X DELETE http://aukai.io/warehouse-attr/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://aukai.io/warehouse-attr/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse-attr/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.delete('http://aukai.io/warehouse-attr/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.delete 'http://aukai.io/warehouse-attr/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /warehouse-attr/{id}`

Delete a WarehouseAttr by ID

<h3 id="delete-warehouseattr-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The warehouse-attr ID|

> Example responses

> 200 Response

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "desc_en": "string",
  "desc_ja": "string",
  "id": 0,
  "key": "temp.const",
  "type": "feature",
  "updated_at": "2019-06-18T05:07:22Z",
  "value_en": "Temperature Controlled",
  "value_ja": "定温倉庫"
}
```

<h3 id="delete-warehouseattr-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The deleted warehouse-attr|[model.WarehouseAttr](#schemamodel.warehouseattr)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

<h1 id="aukai-core-api-warehouse">warehouse</h1>

## List Warehouses

<a id="opIdget-companies"></a>

> Code samples

```http
GET http://aukai.io/warehouse/ HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/warehouse/ \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/warehouse/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/warehouse/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/warehouse/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /warehouse/`

Lists Warehouses

> Example responses

> 200 Response

```json
[
  {
    "address_en": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "address_ja": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "attrs": [
      {
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "desc_en": "string",
        "desc_ja": "string",
        "id": 0,
        "key": "temp.const",
        "type": "feature",
        "updated_at": "2019-06-18T05:07:22Z",
        "value_en": "Temperature Controlled",
        "value_ja": "定温倉庫"
      }
    ],
    "company_id": 0,
    "created_at": "2019-06-18T05:07:22Z",
    "created_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "deleted_at": "2019-06-18T05:07:22Z",
    "id": 0,
    "name_en": "string",
    "name_ja": "string",
    "parent": null,
    "parent_id": 0,
    "phone": "string",
    "photos": [
      {
        "attribution": "string",
        "company_id": 0,
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "id": 0,
        "name": "string",
        "ref": "string",
        "ref_type": "string",
        "updated_at": "2019-06-18T05:07:22Z",
        "url": "string",
        "warehouse_id": 0
      }
    ],
    "sqmtr": 0,
    "type": "string",
    "updated_at": "2019-06-18T05:07:22Z",
    "updated_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "url": "string"
  }
]
```

<h3 id="list-warehouses-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="list-warehouses-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[model.Warehouse](#schemamodel.warehouse)]|false|none|none|
|» address_en|[model.Address](#schemamodel.address)|false|none|none|
|»» building_name|string|false|none|BuildingName is the name of the building, e.g., TriSeven Building|
|»» country_code|string|false|none|CountryCode abbreviation|
|»» country_name|string|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» district_name|string|false|none|BlockBldgName is the name the block and building number|
|»» formatted|string|false|none|Formatted address for display in the target language|
|»» geo_coder|string|false|none|GeoCoder is the system that was used to resolve this address|
|»» geo_coder_ref|string|false|none|GeoCoderRef is the reference within the system used to geocode this Address|
|»» id|integer|false|none|none|
|»» lang|string|false|none|Lang is th language in which the address is registered|
|»» lat|number|false|none|Lat is the GPS latitude|
|»» lng|number|false|none|Lon is the GPS longitude|
|»» machi_name|string|false|none|MachiName is the name of the town|
|»» muni_name|string|false|none|MuniName is the name of the municipality|
|»» postal_code|string|false|none|none|
|»» region_code|integer|false|none|RegionCode is the code of the region|
|»» region_name|string|false|none|RegionName is the name of the region|
|»» updated_at|string|false|none|none|
|» address_ja|[model.Address](#schemamodel.address)|false|none|none|
|» attrs|[[model.WarehouseAttr](#schemamodel.warehouseattr)]|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» desc_en|string|false|none|none|
|»» desc_ja|string|false|none|none|
|»» id|integer|false|none|none|
|»» key|string|false|none|none|
|»» type|string|false|none|none|
|»» updated_at|string|false|none|none|
|»» value_en|string|false|none|none|
|»» value_ja|string|false|none|none|
|» company_id|integer|false|none|none|
|» created_at|string|false|none|none|
|» created_by|[model.User](#schemamodel.user)|false|none|none|
|»» avatar|string|false|none|none|
|»» company_id|integer|false|none|none|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» email|string|true|none|none|
|»» id|integer|false|none|none|
|»» language|string|false|none|none|
|»» name|string|true|none|none|
|»» updated_at|string|false|none|none|
|»» username|string|true|none|none|
|» deleted_at|string|false|none|none|
|» id|integer|false|none|none|
|» name_en|string|true|none|none|
|» name_ja|string|true|none|none|
|» parent|[model.Warehouse](#schemamodel.warehouse)|false|none|none|
|» parent_id|integer|false|none|none|
|» phone|string|false|none|none|
|» photos|[[model.Photo](#schemamodel.photo)]|false|none|none|
|»» attribution|string|false|none|Attribution holds the credit for the photographer, or creator of the image|
|»» company_id|integer|false|none|CompanyID associates this Photo with a Company|
|»» created_at|string|false|none|none|
|»» deleted_at|string|false|none|none|
|»» id|integer|false|none|none|
|»» name|string|true|none|Name is the name that should be displayed for the image|
|»» ref|string|false|none|Ref is the ID use to retrieve the image|
|»» ref_type|string|false|none|RefType is the name of the system hosting the image|
|»» updated_at|string|false|none|none|
|»» url|string|false|none|URL is a direct reference URL to the image, or the base64 encoded image|
|»» warehouse_id|integer|false|none|WarehouseID associates this Photo with a Warehouse|
|» sqmtr|integer|false|none|Sqmt is the usable square meters of the space|
|» type|string|false|none|none|
|» updated_at|string|false|none|none|
|» updated_by|[model.User](#schemamodel.user)|false|none|none|
|» url|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Create Warehouse

<a id="opIdcreate-warehouse"></a>

> Code samples

```http
POST http://aukai.io/warehouse/ HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/warehouse/ \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/warehouse/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse/',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/warehouse/', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/warehouse/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /warehouse/`

Create a Warehouse

> Body parameter

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "attrs": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "desc_en": "string",
      "desc_ja": "string",
      "id": 0,
      "key": "temp.const",
      "type": "feature",
      "updated_at": "2019-06-18T05:07:22Z",
      "value_en": "Temperature Controlled",
      "value_ja": "定温倉庫"
    }
  ],
  "company_id": 0,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "parent": null,
  "parent_id": 0,
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "sqmtr": 0,
  "type": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="create-warehouse-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[model.Warehouse](#schemamodel.warehouse)|true|the warehouse to create|

> Example responses

> 200 Response

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "attrs": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "desc_en": "string",
      "desc_ja": "string",
      "id": 0,
      "key": "temp.const",
      "type": "feature",
      "updated_at": "2019-06-18T05:07:22Z",
      "value_en": "Temperature Controlled",
      "value_ja": "定温倉庫"
    }
  ],
  "company_id": 0,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "parent": null,
  "parent_id": 0,
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "sqmtr": 0,
  "type": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="create-warehouse-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Warehouse](#schemamodel.warehouse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Get Warehouse by ID

<a id="opIdget-warehouse-by-id"></a>

> Code samples

```http
GET http://aukai.io/warehouse/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/warehouse/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/warehouse/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/warehouse/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/warehouse/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /warehouse/{id}`

Retrieve a Warehouse

> Example responses

> 200 Response

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "attrs": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "desc_en": "string",
      "desc_ja": "string",
      "id": 0,
      "key": "temp.const",
      "type": "feature",
      "updated_at": "2019-06-18T05:07:22Z",
      "value_en": "Temperature Controlled",
      "value_ja": "定温倉庫"
    }
  ],
  "company_id": 0,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "parent": null,
  "parent_id": 0,
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "sqmtr": 0,
  "type": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="get-warehouse-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Warehouse](#schemamodel.warehouse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Update Warehouse

<a id="opIdupdate-warehouse"></a>

> Code samples

```http
POST http://aukai.io/warehouse/{id} HTTP/1.1
Host: aukai.io
Content-Type: application/json
Accept: application/json

```

```shell
# You can also use wget
curl -X POST http://aukai.io/warehouse/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://aukai.io/warehouse/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse/{id}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.post('http://aukai.io/warehouse/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.post 'http://aukai.io/warehouse/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /warehouse/{id}`

Update attributes of a Warehouse

> Body parameter

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "attrs": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "desc_en": "string",
      "desc_ja": "string",
      "id": 0,
      "key": "temp.const",
      "type": "feature",
      "updated_at": "2019-06-18T05:07:22Z",
      "value_en": "Temperature Controlled",
      "value_ja": "定温倉庫"
    }
  ],
  "company_id": 0,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "parent": null,
  "parent_id": 0,
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "sqmtr": 0,
  "type": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="update-warehouse-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The warehouse ID|
|body|body|[model.Warehouse](#schemamodel.warehouse)|true|attributes to change|

> Example responses

> 200 Response

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "attrs": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "desc_en": "string",
      "desc_ja": "string",
      "id": 0,
      "key": "temp.const",
      "type": "feature",
      "updated_at": "2019-06-18T05:07:22Z",
      "value_en": "Temperature Controlled",
      "value_ja": "定温倉庫"
    }
  ],
  "company_id": 0,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "parent": null,
  "parent_id": 0,
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "sqmtr": 0,
  "type": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="update-warehouse-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.Warehouse](#schemamodel.warehouse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Delete Warehouse

<a id="opIddelete-warehouse-by-id"></a>

> Code samples

```http
DELETE http://aukai.io/warehouse/{id} HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X DELETE http://aukai.io/warehouse/{id} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://aukai.io/warehouse/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.delete('http://aukai.io/warehouse/{id}', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.delete 'http://aukai.io/warehouse/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /warehouse/{id}`

Delete a Warehouse by ID

<h3 id="delete-warehouse-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The warehouse ID|

> Example responses

> 200 Response

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "attrs": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "desc_en": "string",
      "desc_ja": "string",
      "id": 0,
      "key": "temp.const",
      "type": "feature",
      "updated_at": "2019-06-18T05:07:22Z",
      "value_en": "Temperature Controlled",
      "value_ja": "定温倉庫"
    }
  ],
  "company_id": 0,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "parent": null,
  "parent_id": 0,
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "sqmtr": 0,
  "type": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}
```

<h3 id="delete-warehouse-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The deleted warehouse|[model.Warehouse](#schemamodel.warehouse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

## Get Warehouse Tree

<a id="opIdget-warehouse-warehouses"></a>

> Code samples

```http
GET http://aukai.io/warehouse/{id}/tree HTTP/1.1
Host: aukai.io
Accept: application/json

```

```shell
# You can also use wget
curl -X GET http://aukai.io/warehouse/{id}/tree \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer JWT'

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
        "Authorization": []string{"Bearer JWT"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://aukai.io/warehouse/{id}/tree", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer JWT'

};

$.ajax({
  url: 'http://aukai.io/warehouse/{id}/tree',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer JWT'
}

r = requests.get('http://aukai.io/warehouse/{id}/tree', params={

}, headers = headers)

print r.json()

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer JWT'
}

result = RestClient.get 'http://aukai.io/warehouse/{id}/tree',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /warehouse/{id}/tree`

Provides a list of Warehouse objects ordered as a tree

<h3 id="get-warehouse-tree-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|Warehouse ID|

> Example responses

> 200 Response

```json
{
  "warehouse": {
    "address_en": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "address_ja": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "attrs": [
      {
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "desc_en": "string",
        "desc_ja": "string",
        "id": 0,
        "key": "temp.const",
        "type": "feature",
        "updated_at": "2019-06-18T05:07:22Z",
        "value_en": "Temperature Controlled",
        "value_ja": "定温倉庫"
      }
    ],
    "company_id": 0,
    "created_at": "2019-06-18T05:07:22Z",
    "created_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "deleted_at": "2019-06-18T05:07:22Z",
    "id": 0,
    "name_en": "string",
    "name_ja": "string",
    "parent": null,
    "parent_id": 0,
    "phone": "string",
    "photos": [
      {
        "attribution": "string",
        "company_id": 0,
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "id": 0,
        "name": "string",
        "ref": "string",
        "ref_type": "string",
        "updated_at": "2019-06-18T05:07:22Z",
        "url": "string",
        "warehouse_id": 0
      }
    ],
    "sqmtr": 0,
    "type": "string",
    "updated_at": "2019-06-18T05:07:22Z",
    "updated_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "url": "string"
  },
  "warehouses": [
    null
  ]
}
```

<h3 id="get-warehouse-tree-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[model.WarehouseTree](#schemamodel.warehousetree)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
ApiKeyAuth
</aside>

# Schemas

<h2 id="tocSapi.authstatus">api.AuthStatus</h2>

<a id="schemaapi.authstatus"></a>

```json
{
  "status": "string",
  "token": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|string|false|none|none|
|token|string|false|none|none|

<h2 id="tocSapi.authtoken">api.AuthToken</h2>

<a id="schemaapi.authtoken"></a>

```json
{
  "accessToken": {
    "expiresAt": 0,
    "token": "string"
  },
  "refreshToken": {
    "expiresAt": 0,
    "token": "string"
  },
  "status": "string",
  "user": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accessToken|[api.SimpleAuthToken](#schemaapi.simpleauthtoken)|false|none|none|
|refreshToken|[api.SimpleAuthToken](#schemaapi.simpleauthtoken)|false|none|none|
|status|string|false|none|none|
|user|[model.User](#schemamodel.user)|false|none|none|

<h2 id="tocSapi.contactrequest">api.ContactRequest</h2>

<a id="schemaapi.contactrequest"></a>

```json
{
  "company": "XYZ Corporation",
  "email": "user@aukai.dev",
  "firstName": "Taro",
  "lastName": "Suzuki",
  "message": "string",
  "phone": "+81 03-0000-0000"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|company|string|true|none|Company of the contact person|
|email|string|true|none|Email of the contact person|
|firstName|string|true|none|FirstName of the contact person|
|lastName|string|true|none|LastName of the contact person|
|message|string|false|none|Message of the person included (optional)|
|phone|string|true|none|Phone number of the contact person; can include international prefix; otherwise will be assumed to be in Japan|

<h2 id="tocSapi.metrics">api.Metrics</h2>

<a id="schemaapi.metrics"></a>

```json
{
  "companies": 200,
  "sqmt": 100000000,
  "users": 4000,
  "warehouses": 1000
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|companies|integer|false|none|none|
|sqmt|integer|false|none|none|
|users|integer|false|none|none|
|warehouses|integer|false|none|none|

<h2 id="tocSapi.refreshtokendata">api.RefreshTokenData</h2>

<a id="schemaapi.refreshtokendata"></a>

```json
{
  "token": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|token|string|false|none|none|

<h2 id="tocSapi.simpleauthtoken">api.SimpleAuthToken</h2>

<a id="schemaapi.simpleauthtoken"></a>

```json
{
  "expiresAt": 0,
  "token": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|expiresAt|integer|false|none|none|
|token|string|false|none|none|

<h2 id="tocSapi.userdata">api.UserData</h2>

<a id="schemaapi.userdata"></a>

```json
{
  "avatar": "string",
  "email": "string",
  "id": 0,
  "language": "string",
  "name": "string",
  "password": "string",
  "roles": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "users": [
        {
          "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
          "company_id": 1,
          "created_at": "2019-06-18T05:07:22Z",
          "deleted_at": "2019-06-18T05:07:22Z",
          "email": "tanaka.suzuki@aukai.dev",
          "id": 0,
          "language": "ja",
          "name": "Tanaka Suzuki",
          "updated_at": "2019-06-18T05:07:22Z",
          "username": "string"
        }
      ]
    }
  ],
  "username": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|avatar|string|false|none|none|
|email|string|true|none|FIXME: must be unique|
|id|integer|false|none|none|
|language|string|false|none|FIXME: validate is one of en_US, ja_JP|
|name|string|true|none|none|
|password|string|false|none|none|
|roles|[[model.Role](#schemamodel.role)]|false|none|none|
|username|string|true|none|FIXME: must be unique|

<h2 id="tocSapi.userquery">api.UserQuery</h2>

<a id="schemaapi.userquery"></a>

```json
{
  "email": "tanaka.suzuki@aukai.io",
  "id": 1,
  "username": "tanaka"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string|false|none|none|
|id|integer|false|none|none|
|username|string|false|none|none|

<h2 id="tocSapi.version">api.version</h2>

<a id="schemaapi.version"></a>

```json
{
  "branch": "master",
  "date": "2019-06-19T03:20:26Z",
  "domains": [
    "['https://aukai.io']"
  ],
  "uptime": "27h14m37.809030294s",
  "version": "1.0.0"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|branch|string|false|none|none|
|date|string|false|none|none|
|domains|[string]|false|none|none|
|uptime|string|false|none|none|
|version|string|false|none|none|

<h2 id="tocSmodel.address">model.Address</h2>

<a id="schemamodel.address"></a>

```json
{
  "building_name": "TriSeven Building",
  "country_code": "JP",
  "country_name": "Japan",
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "district_name": "5-10",
  "formatted": "string",
  "geo_coder": "string",
  "geo_coder_ref": "string",
  "id": 0,
  "lang": "ja_jp",
  "lat": 0,
  "lng": 0,
  "machi_name": "浅草",
  "muni_name": "台東区",
  "postal_code": "110-0014",
  "region_code": 13,
  "region_name": "東京都",
  "updated_at": "2019-06-18T05:07:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|building_name|string|false|none|BuildingName is the name of the building, e.g., TriSeven Building|
|country_code|string|false|none|CountryCode abbreviation|
|country_name|string|false|none|none|
|created_at|string|false|none|none|
|deleted_at|string|false|none|none|
|district_name|string|false|none|BlockBldgName is the name the block and building number|
|formatted|string|false|none|Formatted address for display in the target language|
|geo_coder|string|false|none|GeoCoder is the system that was used to resolve this address|
|geo_coder_ref|string|false|none|GeoCoderRef is the reference within the system used to geocode this Address|
|id|integer|false|none|none|
|lang|string|false|none|Lang is th language in which the address is registered|
|lat|number|false|none|Lat is the GPS latitude|
|lng|number|false|none|Lon is the GPS longitude|
|machi_name|string|false|none|MachiName is the name of the town|
|muni_name|string|false|none|MuniName is the name of the municipality|
|postal_code|string|false|none|none|
|region_code|integer|false|none|RegionCode is the code of the region|
|region_name|string|false|none|RegionName is the name of the region|
|updated_at|string|false|none|none|

<h2 id="tocSmodel.company">model.Company</h2>

<a id="schemamodel.company"></a>

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address_en|[model.Address](#schemamodel.address)|false|none|the address in English for the company required: false|
|address_ja|[model.Address](#schemamodel.address)|false|none|the address in Japanese for the company required: false|
|created_at|string|false|none|none|
|created_by|[model.User](#schemamodel.user)|false|none|none|
|deleted_at|string|false|none|none|
|id|integer|false|none|none|
|name_en|string|true|none|the name in English for the company required: true|
|name_ja|string|true|none|the name in Japanese for the company required: true|
|phone|string|false|none|Phone number with country code for contacting the company required: false example: +81 03-4560-3232|
|photos|[[model.Photo](#schemamodel.photo)]|false|none|photos associated with the company, e.g., logos and buildings required: false|
|updated_at|string|false|none|none|
|updated_by|[model.User](#schemamodel.user)|false|none|none|
|url|string|false|none|Website or other reference webpage for the company required: true example: https://aukai.io|

<h2 id="tocSmodel.networkassoc">model.NetworkAssoc</h2>

<a id="schemamodel.networkassoc"></a>

```json
{
  "comment": "string",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "file": {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  },
  "id": 0,
  "status": "requested",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "warehouse_id": 1
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|comment|string|false|none|Comment is not stored in the Association, but is extracted from requests and stored in a NetworkEvent object. I would prefer not to have any JSON value here, but we need it in order to enable automatic extraction from submitted JSON. In the ideal scenario we'd be able to extract the comment, but not include it in JSON responses.|
|company_id|integer|false|none|The Company side of the network association. This will be the company to which the requesting user belongs.|
|created_at|string|false|none|none|
|created_by|[model.User](#schemamodel.user)|false|none|none|
|deleted_at|string|false|none|none|
|file|[storedfile.File](#schemastoredfile.file)|false|none|none|
|id|integer|false|none|none|
|status|string|false|none|Status is the connection status for the Warehouse and Company|
|updated_at|string|false|none|none|
|updated_by|[model.User](#schemamodel.user)|false|none|none|
|warehouse_id|integer|false|none|The Warehouse side of the network association.|

<h2 id="tocSmodel.networkevent">model.NetworkEvent</h2>

<a id="schemamodel.networkevent"></a>

```json
{
  "comment": "Lorem Ipsum ...",
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "file": {
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "dir": "string",
    "ext": "png",
    "filename": "string",
    "id": 1,
    "mime_type": "image/png",
    "ref": "df6301cfb58750fd8707611cea13e9b3",
    "updated_at": "2019-06-18T05:07:22Z",
    "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
  },
  "id": 0,
  "network_assoc_id": 1,
  "start": "requested",
  "stop": "approved",
  "updated_at": "2019-06-18T05:07:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|comment|string|false|none|Comment is a note attached to the change even by the user that initiates the chagne|
|created_at|string|false|none|none|
|created_by|[model.User](#schemamodel.user)|false|none|none|
|deleted_at|string|false|none|none|
|file|[storedfile.File](#schemastoredfile.file)|false|none|none|
|id|integer|false|none|none|
|network_assoc_id|integer|false|none|none|
|start|string|false|none|StartState is the state of the Network connection before this change Event|
|stop|string|false|none|StopState is the state of the Network connection after this change Event is applied|
|updated_at|string|false|none|none|

<h2 id="tocSmodel.photo">model.Photo</h2>

<a id="schemamodel.photo"></a>

```json
{
  "attribution": "string",
  "company_id": 0,
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name": "string",
  "ref": "string",
  "ref_type": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "url": "string",
  "warehouse_id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|attribution|string|false|none|Attribution holds the credit for the photographer, or creator of the image|
|company_id|integer|false|none|CompanyID associates this Photo with a Company|
|created_at|string|false|none|none|
|deleted_at|string|false|none|none|
|id|integer|false|none|none|
|name|string|true|none|Name is the name that should be displayed for the image|
|ref|string|false|none|Ref is the ID use to retrieve the image|
|ref_type|string|false|none|RefType is the name of the system hosting the image|
|updated_at|string|false|none|none|
|url|string|false|none|URL is a direct reference URL to the image, or the base64 encoded image|
|warehouse_id|integer|false|none|WarehouseID associates this Photo with a Warehouse|

<h2 id="tocSmodel.role">model.Role</h2>

<a id="schemamodel.role"></a>

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "users": [
    {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created_at|string|false|none|none|
|deleted_at|string|false|none|none|
|id|integer|false|none|none|
|name|string|true|none|none|
|updated_at|string|false|none|none|
|users|[[model.User](#schemamodel.user)]|false|none|none|

<h2 id="tocSmodel.user">model.User</h2>

<a id="schemamodel.user"></a>

```json
{
  "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
  "company_id": 1,
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "email": "tanaka.suzuki@aukai.dev",
  "id": 0,
  "language": "ja",
  "name": "Tanaka Suzuki",
  "updated_at": "2019-06-18T05:07:22Z",
  "username": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|avatar|string|false|none|none|
|company_id|integer|false|none|none|
|created_at|string|false|none|none|
|deleted_at|string|false|none|none|
|email|string|true|none|none|
|id|integer|false|none|none|
|language|string|false|none|none|
|name|string|true|none|none|
|updated_at|string|false|none|none|
|username|string|true|none|none|

<h2 id="tocSmodel.warehouse">model.Warehouse</h2>

<a id="schemamodel.warehouse"></a>

```json
{
  "address_en": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "address_ja": {
    "building_name": "TriSeven Building",
    "country_code": "JP",
    "country_name": "Japan",
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "district_name": "5-10",
    "formatted": "string",
    "geo_coder": "string",
    "geo_coder_ref": "string",
    "id": 0,
    "lang": "ja_jp",
    "lat": 0,
    "lng": 0,
    "machi_name": "浅草",
    "muni_name": "台東区",
    "postal_code": "110-0014",
    "region_code": 13,
    "region_name": "東京都",
    "updated_at": "2019-06-18T05:07:22Z"
  },
  "attrs": [
    {
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "desc_en": "string",
      "desc_ja": "string",
      "id": 0,
      "key": "temp.const",
      "type": "feature",
      "updated_at": "2019-06-18T05:07:22Z",
      "value_en": "Temperature Controlled",
      "value_ja": "定温倉庫"
    }
  ],
  "company_id": 0,
  "created_at": "2019-06-18T05:07:22Z",
  "created_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "deleted_at": "2019-06-18T05:07:22Z",
  "id": 0,
  "name_en": "string",
  "name_ja": "string",
  "parent": null,
  "parent_id": 0,
  "phone": "string",
  "photos": [
    {
      "attribution": "string",
      "company_id": 0,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "id": 0,
      "name": "string",
      "ref": "string",
      "ref_type": "string",
      "updated_at": "2019-06-18T05:07:22Z",
      "url": "string",
      "warehouse_id": 0
    }
  ],
  "sqmtr": 0,
  "type": "string",
  "updated_at": "2019-06-18T05:07:22Z",
  "updated_by": {
    "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
    "company_id": 1,
    "created_at": "2019-06-18T05:07:22Z",
    "deleted_at": "2019-06-18T05:07:22Z",
    "email": "tanaka.suzuki@aukai.dev",
    "id": 0,
    "language": "ja",
    "name": "Tanaka Suzuki",
    "updated_at": "2019-06-18T05:07:22Z",
    "username": "string"
  },
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address_en|[model.Address](#schemamodel.address)|false|none|none|
|address_ja|[model.Address](#schemamodel.address)|false|none|none|
|attrs|[[model.WarehouseAttr](#schemamodel.warehouseattr)]|false|none|none|
|company_id|integer|false|none|none|
|created_at|string|false|none|none|
|created_by|[model.User](#schemamodel.user)|false|none|none|
|deleted_at|string|false|none|none|
|id|integer|false|none|none|
|name_en|string|true|none|none|
|name_ja|string|true|none|none|
|parent|[model.Warehouse](#schemamodel.warehouse)|false|none|none|
|parent_id|integer|false|none|none|
|phone|string|false|none|none|
|photos|[[model.Photo](#schemamodel.photo)]|false|none|none|
|sqmtr|integer|false|none|Sqmt is the usable square meters of the space|
|type|string|false|none|none|
|updated_at|string|false|none|none|
|updated_by|[model.User](#schemamodel.user)|false|none|none|
|url|string|false|none|none|

<h2 id="tocSmodel.warehouseattr">model.WarehouseAttr</h2>

<a id="schemamodel.warehouseattr"></a>

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "desc_en": "string",
  "desc_ja": "string",
  "id": 0,
  "key": "temp.const",
  "type": "feature",
  "updated_at": "2019-06-18T05:07:22Z",
  "value_en": "Temperature Controlled",
  "value_ja": "定温倉庫"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created_at|string|false|none|none|
|deleted_at|string|false|none|none|
|desc_en|string|false|none|none|
|desc_ja|string|false|none|none|
|id|integer|false|none|none|
|key|string|false|none|none|
|type|string|false|none|none|
|updated_at|string|false|none|none|
|value_en|string|false|none|none|
|value_ja|string|false|none|none|

<h2 id="tocSmodel.warehousetree">model.WarehouseTree</h2>

<a id="schemamodel.warehousetree"></a>

```json
{
  "warehouse": {
    "address_en": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "address_ja": {
      "building_name": "TriSeven Building",
      "country_code": "JP",
      "country_name": "Japan",
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "district_name": "5-10",
      "formatted": "string",
      "geo_coder": "string",
      "geo_coder_ref": "string",
      "id": 0,
      "lang": "ja_jp",
      "lat": 0,
      "lng": 0,
      "machi_name": "浅草",
      "muni_name": "台東区",
      "postal_code": "110-0014",
      "region_code": 13,
      "region_name": "東京都",
      "updated_at": "2019-06-18T05:07:22Z"
    },
    "attrs": [
      {
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "desc_en": "string",
        "desc_ja": "string",
        "id": 0,
        "key": "temp.const",
        "type": "feature",
        "updated_at": "2019-06-18T05:07:22Z",
        "value_en": "Temperature Controlled",
        "value_ja": "定温倉庫"
      }
    ],
    "company_id": 0,
    "created_at": "2019-06-18T05:07:22Z",
    "created_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "deleted_at": "2019-06-18T05:07:22Z",
    "id": 0,
    "name_en": "string",
    "name_ja": "string",
    "parent": null,
    "parent_id": 0,
    "phone": "string",
    "photos": [
      {
        "attribution": "string",
        "company_id": 0,
        "created_at": "2019-06-18T05:07:22Z",
        "deleted_at": "2019-06-18T05:07:22Z",
        "id": 0,
        "name": "string",
        "ref": "string",
        "ref_type": "string",
        "updated_at": "2019-06-18T05:07:22Z",
        "url": "string",
        "warehouse_id": 0
      }
    ],
    "sqmtr": 0,
    "type": "string",
    "updated_at": "2019-06-18T05:07:22Z",
    "updated_by": {
      "avatar": "https://www.gravatar.com/avatar/7643816c41a8ad0ba7e7ba48ea1e20a8.jpg?d=&r=g&s=80?imageView2/1/w/80/h/80",
      "company_id": 1,
      "created_at": "2019-06-18T05:07:22Z",
      "deleted_at": "2019-06-18T05:07:22Z",
      "email": "tanaka.suzuki@aukai.dev",
      "id": 0,
      "language": "ja",
      "name": "Tanaka Suzuki",
      "updated_at": "2019-06-18T05:07:22Z",
      "username": "string"
    },
    "url": "string"
  },
  "warehouses": [
    null
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|warehouse|[model.Warehouse](#schemamodel.warehouse)|false|none|none|
|warehouses|[[model.WarehouseTree](#schemamodel.warehousetree)]|false|none|none|

<h2 id="tocSplace.autocompletereq">place.AutoCompleteReq</h2>

<a id="schemaplace.autocompletereq"></a>

```json
{
  "address": "string",
  "lang": "string",
  "type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address|string|true|none|none|
|lang|string|false|none|none|
|type|string|false|none|none|

<h2 id="tocSresource.notfounderror">resource.NotFoundError</h2>

<a id="schemaresource.notfounderror"></a>

```json
{
  "id": 1
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer|false|none|none|

<h2 id="tocSstoredfile.file">storedfile.File</h2>

<a id="schemastoredfile.file"></a>

```json
{
  "created_at": "2019-06-18T05:07:22Z",
  "deleted_at": "2019-06-18T05:07:22Z",
  "dir": "string",
  "ext": "png",
  "filename": "string",
  "id": 1,
  "mime_type": "image/png",
  "ref": "df6301cfb58750fd8707611cea13e9b3",
  "updated_at": "2019-06-18T05:07:22Z",
  "url": "https://aukai.io/ref/df6301cfb58750fd8707611cea13e9b3/file"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|created_at|string|false|none|none|
|deleted_at|string|false|none|none|
|dir|string|false|none|Dir is the company ID|
|ext|string|false|none|Ext is the extension for the file if it's written to a filesystem|
|filename|string|true|none|Filename is the name given to the file, it's usually the same as Ref|
|id|integer|false|none|none|
|mime_type|string|false|none|MimeType of the file [usually auto detected]|
|ref|string|true|none|Ref is the key used to retrieve the file from our object store|
|updated_at|string|false|none|none|
|url|string|false|none|URL for external systems to use to access the file|

