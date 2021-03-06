ModelKit lets users generate predictions on pre-trained machine learning models in the cloud.

> :bulb: Sorta like [npm](https://npmjs.com), but for ML models.

It follows a pretty straightforward approach to run models for now, but there are plans to support image classification and other deep learning models too in the later versions.

## ModelKit Web Client :earth_asia:
This is the web client for ModelKit. It's built with [Next.js](https://nextjs.org/) using the [Ant Design](https://ant.design/docs/react/) UI toolkit.

## Todos
- [ ] Create landing page.
- [ ] Add page to edit user profile.
- [ ] Implement logout (delete JWT cookie & clear navigation history).

# ModelKit Server :wrench: 
'modelkit-api' contains the server for ModelKit. It's built on [FastAPI](https://fastapi.tiangolo.com/). It handles JWT auth, simple feed, disk storage, running predictions and model creation utilities for the client.

# Endpoints


### /feed

#### GET
##### Summary

Feed

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| start | query |  | No |  |
| count | query |  | No |  |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /predict

#### POST
##### Summary

Train

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /login

#### POST
##### Summary

Login

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /signup

#### POST
##### Summary

Signup

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /model/create

#### POST
##### Summary

Create Model

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

### /model/fetch-all

#### GET
##### Summary

Fetch All

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| username | query |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /model/fetch-one

#### GET
##### Summary

Fetch One

##### Parameters

| Name | Located in | Description | Required | Schema |
| ---- | ---------- | ----------- | -------- | ---- |
| uid | query |  | Yes | string |

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /model/upload

#### POST
##### Summary

Create Model

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |
| 422 | Validation Error |

### /

#### GET
##### Summary

Home

##### Responses

| Code | Description |
| ---- | ----------- |
| 200 | Successful Response |

### Models

#### Body_create_model_model_upload_post

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| model | binary |  | Yes |

#### HTTPValidationError

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| detail | [ object ] |  | No |

#### ValidationError

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| loc | [ string ] |  | Yes |
| msg | string |  | Yes |
| type | string |  | Yes |

#### app__routes__auth__login__RequestBody

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| username | string |  | Yes |
| password | string |  | Yes |

#### app__routes__auth__signup__RequestBody

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| username | string |  | Yes |
| name | string |  | Yes |
| password | string |  | Yes |

#### app__routes__predict__RequestBody

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| model_uid | string |  | Yes |
| xtest | [  ] |  | Yes |
