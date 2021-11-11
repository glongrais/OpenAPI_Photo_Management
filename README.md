# OpenAPI_Photo_Management

## Principle

Basic photo management API created with OpenAPI 3 that serve basic CRUD via HTTP

### Table of Contents  
[Ressources](#Ressouces)  
[Requests](#Requests)  
[Schemas](#Schemas)   
[Example](#Example)   


## Ressources

* OpenAPI specification can be found [here](https://swagger.io/specification/).
* Basics about HTTP requests and response codes can be found [here](https://www.restapitutorial.com/lessons/httpmethods.html).


## Requests

| Type | Route | Request Body | Response Body |
| --- | --- | ---| --- |
| POST | `/photo`|Photo|<ul><li> **Status Code**: 201 - `Success: {message: ‘Photo successfully created’, id: photo_id}`</li><li>**Status Code**: 422 - `Error: {message: err}`</li></ul>|
| GET |`/photos`|access|<ul><li>**Status Code**: 200 - `Photos: [{Photo}, ..]`  </li><li>**Status Code**: 404 -  `Error: {message: err}`  </li></ul>|
| GET |`/photo/{photo_id}`|-|<ul><li>**Status Code**: 200 - `Photo: {id: id, name: name, description: description, access: access, location: location, created_date: created_date, modified_date: modified_date}`  </li><li>**Status Code**: 404 -  `Error: {message: err}`  </li></ul>|
| PUT |`/photo/{photo_id}`|Photo|<ul><li>**Status Code**: 200 - `Success: {message: ‘Photo successfully updated’, id: photo_id}`  </li><li>**Status Code**: 404 -  `Error: {message: err}`</li><li>**Status Code**: 422 -  `Error: {message: err}`  </li></ul>|
| DELETE |`/photo/{photo_id}`|-|<ul><li>**Status Code**: 204  </li><li>**Status Code**: 404 -  `Error: {message: err}`  </li></ul>|

## Schemas

* `Photo`

    | Attribute | Type | Conditions |
    | --- | --- | --- |
    | id | string | `readOnly: true` |
    | name | string | `required:true`</br>`maxlenght: 20` |
    | description | string | `maxlenght: 100` |
    | access | string | `required:true`</br>`enum: [public, private]` |
    | location | string | `required:true` |
    | file | string | `required:true` |
    | created_date | string | `required:true`</br>`format: date-time` |
    | updated_date | string | `required:true`</br>`format: date-time` |

* `Photos`

    | Attribute | Type | Description |
    | --- | --- | --- |
    | [Photo] | array | An array of photos |

* `Success`

    | Attribute | Type | Conditions |
    | --- | --- | --- |
    | message | string | - |
    | id | string | - |

* `Error`

    | Attribute | Type | Conditions |
    | --- | --- | --- |
    | message | string | - |


## Example

`Photo` schema:

```json
{
  "name": "Photo_3",
  "description": "My dog selfie",
  "access": "public",
  "location": "Skopje",
  "file": "teddy_selfie.jpg",
  "created_date": "1996-08-23T17:32:28Z",
  "modified_date": "2020-12-27T23:45:28Z"
}
```


