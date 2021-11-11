# OpenAPI_Photo_Management

## Principle

Basic photo management API created with OpenAPI 3 that serve basic CRUD via HTTP

## Ressources

* OpenAPI specification can be found [here](https://swagger.io/specification/).
* Basics about HTTP requests and response codes can be found [here](https://www.restapitutorial.com/lessons/httpmethods.html).


## Requests

| Type | Route | Request Body | Response Body |
| --- | --- | ---| --- |
| POST | `/photo`|Photo|<ul><li> **Status Code**: 201 - <code>json {Success: {message: ‘Photo successfully created’, id: photo_id}}</code></li><li>**Status Code**: 422 - `Error: {message: err}`</li></ul>|
| GET |`/photos`|access|<ul><li>**Status Code**: 200 - `Photos: [{Photo}, ..]`  </li><li>**Status Code**: 404 -  `Error: {message: err}`  </li></ul>|
| GET |`/photo/{photo_id}`|-|<ul><li>**Status Code**: 200 - `Photo: {id: id, name: name, description: description, access: access, location: location, created_date: created_date, modified_date: modified_date}`  </li><li>**Status Code**: 404 -  `Error: {message: err}`  </li></ul>|
| PUT |`/photo/{photo_id}`|Photo|<ul><li>**Status Code**: 200 - `Success: {message: ‘Photo successfully updated’, id: photo_id}`  </li><li>**Status Code**: 404 -  `Error: {message: err}`/li><li>**Status Code**: 422 -  `Error: {message: err}`  </li></ul>|
| DELETE |`/photo/{photo_id}`|-|<ul><li>**Status Code**: 204  </li><li>**Status Code**: 404 -  `Error: {message: err}`  </li></ul>|