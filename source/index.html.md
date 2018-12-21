---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - Response

toc_footers:
  - <a href='#'>Documentation Emas-Doc</a>
  - <a href='https://github.com/lord/slate'>Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

  Welcome to the E-mas Document API! You can use our API to access E-mas

### Base Endpoint

`https://e-document-api-dev.e-mas.com`

# Authentication
<aside class="notice">
Some APIs need authenticated in<code>Header Parameters</code>
</aside>

Key | Value | Description
--------- | ------- | -----------
Tokenstring | xxxx | Get token from Login API.

<aside class="notice">
List <code>Roles</code> for access e-mas DOC APIs
</aside>

ID | Key | Description
--------- | ------- | -----------
1 | Super Admin | All Access API.
2 | Admin | Not Allowed API: Update & Delete User, Delete Type, Delete Topic, Delete Document.
3 | Viewer | Not Allowed API: Update - Delete - Create User, Delete - Create - Update Type, Delete - Create - Update Topic, Delete - Upload - Update Document.

## Get Tokenstring
> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJwYXNzd29yZCI6ImZjZTVkMjljYTY2NWI2OTNiZWY3YjU3NGRlMzZkY2NjNjI0MjQxZjMxNTAxODJkODVlODkzMGMxZWM5Y2MyN2RiMGIyMWU4YWVjZjRmMTE2YmQ1ZDZkOWNlOGM5NGMyODZjYzU1YjM2MWI2NzczZGMwMGY2MDBkNjk5M2I2NDhkYTg2YjRkZjFlYmEwN2M1NlxuIiwidGltZSI6IjVjYWE4M2YyMGE4MzhmNGU3ZTQ0MzBiNmFhOTk2Y2I1Y2M1NjRlMzFjZDU4Yzc2NDFlZTZlMWIxMjY0ZmE1ZGRcbiIsInVzZXJuYW1lIjoiNDhkY2FlMDQ0OTA3MzY0MWEzN2QyNjAwMTFkMWFiMjA2YWRiNDU0OTRiOWI2YzNhMTI0Y2YxYjNjZWFmYzZhNjYyNTE1ODRhNDkyOTVlMWZcbiJ9.ZiBbtiYvhykCr7qmLD4eINGzRECHq6O82QnzpPNc7EQ",
        "expired": 1800,
        "roles": "Super Admin",
        "allowed_menu": [
            "dashboard",
            "user",
            "companies",
            "topics",
            "types",
            "documents"
        ],
        "allowed_action": [
            "/v1/user/getall",
            "/v1/user/login",
            "/v1/user/create",
            "/v1/user/update",
            "/v1/company/create",
            "/v1/company/update",
            "/v1/company/getall",
            "/v1/company/delete",
            "/v1/type/getall",
            "/v1/type/create",
            "/v1/type/update",
            "/v1/type/delete",
            "/v1/topic/getall",
            "/v1/topic/create",
            "/v1/topic/update",
            "/v1/topic/delete",
            "/v1/document/upload",
            "/v1/document/getall",
            "/v1/document/download",
            "/v1/document/update",
            "/v1/document/delete"
        ]
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-19T15:26:27.816408084+07:00"
}
```

### HTTP Request 

`POST {{base-endpoint}}/v1/user/login`

### POST Parameters
Key | Required | Description
--------- | ------- | -----------
username | true | Your email has been registered.
password | true | Your password has been registered.

<aside class="notice">
Your token will expired in 30 minutes later.
</aside>

## Refresh Token

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJwYXNzd29yZCI6IjEyOWEzODI2MjEyZjY0NDUyZmQ4NGJhNzdjZTMxNzQ2ZDA2NDVhYWFlZWQ1NjU4ZjM3MjQzYTAwNDQ1YzI0NzVjNjg3MWMwYjRkOTZmMTUxZTFiYzNlNWRlMDYwOGE5YjcyY2M5ODRlZjc5NzY3OWFiYjFmMmMwMDY1YjQwOTliY2E1OTIyNDAzMWE0YzRjMVxuIiwidGltZSI6IjRlNDA0NzFlZjAyOTljY2M5YTQ1MjBhM2E3ODRmYzQ4YzU5ZmU1ZDIxYjhkZDI4NThhMDZiMDAxZDBlNDdmODRcbiIsInVzZXJuYW1lIjoiNDVmYmViY2Y2NWY3ZWQwODY4ZWI2NGU0NDUxNDY0ZGM1ZDYyMGNkODdmMThiZDMzNjM3MmRiZjA2ZDg0NGI4ZmU1Zjc0ZmU0ZTgxNDdjZGFcbiJ9.5F-oM32umgpFpiZpKYqLmCCsREmO3hWjbsD1w1CRxZY",
        "expired": 1800,
        "roles": "Super Admin",
        "allowed_menu": [
            "dashboard",
            "user",
            "companies",
            "topics",
            "types",
            "documents"
        ],
        "allowed_action": [
            "/v1/user/getall",
            "/v1/user/login",
            "/v1/user/create",
            "/v1/user/update",
            "/v1/company/create",
            "/v1/company/update",
            "/v1/company/getall",
            "/v1/company/delete",
            "/v1/type/getall",
            "/v1/type/create",
            "/v1/type/update",
            "/v1/type/delete",
            "/v1/topic/getall",
            "/v1/topic/create",
            "/v1/topic/update",
            "/v1/topic/delete",
            "/v1/document/upload",
            "/v1/document/getall",
            "/v1/document/download",
            "/v1/document/update",
            "/v1/document/delete"
        ]
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T10:38:50.385697878+07:00"
}
```

use this API for get new token before your token first created expired

### HTTP request

`POST {{base-endpoint}}/v1/user/login`

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

# User

## Get User

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "array",
    "data": [
        {
            "id": 22,
            "group_id": 2,
            "username": "mala@gmail.com",
            "is_active": 1,
            "created_date": "2018-12-14T13:46:35+07:00",
            "created_by": "example@mail.com",
            "updated_date": "0001-01-01T00:00:00Z",
            "updated_by": ""
        },
        {
            "id": 21,
            "group_id": 1,
            "username": "malafauzana@gmail.com",
            "is_active": 1,
            "created_date": "2018-12-11T14:12:52+07:00",
            "created_by": "example@mail.com",
            "updated_date": "2018-12-14T16:34:07+07:00",
            "updated_by": "example@mail.com"
        }
    ],
    "total": 20,
    "first_page": "http://e-document-api-dev.e-mas.com/v1/user/getall?per_page=5&page=1",
    "last_page": "http://e-document-api-dev.e-mas.com/v1/user/getall?per_page=5&page=4",
    "next_page": "http://e-document-api-dev.e-mas.com/v1/user/getall?per_page=5&page=2",
    "timestamp": "2018-12-20T10:43:33.977595736+07:00"
}
```

### HTTP Request

`GET {{base-endpoint}}/v1/user/getall`

### Query Parameters
Key | Required | Description
--------- | ------- | -----------
per_page | false | how many data want to show.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Create User

> Response JSON structured like this:

```json
{
    "code": 201,
    "type": "object",
    "data": {
        "id": 23,
        "group_id": 1,
        "username": "adzannyjjj@mail.com",
        "is_active": 1
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T10:44:52.431225557+07:00"
}
```

### HTTP Request

`POST {{base-endpoint}}/v1/user/create`

### POST Parameters
Key | Required | Description
--------- | ------- | -----------
username | true | Your email want to register.
password | true | Your password want to register.
group_id | true | to give privilege access ref: List Roles.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Update User

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "group_id": 1,
        "is_active": 1,
        "username": "adzannyjjj@mail.com"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T11:00:47.670313102+07:00"
}
```

### HTTP Request

`PUT {{base-endpoint}}/v1/user/update`

### PUT Parameters

Key | Required | Description
--------- | ------- | -----------
username | false | Your email want to register.
password | false | Your password want to register.
group_id | false | to give privilege access ref: List Roles.
is_active | true | to give email user can be login or not.

### List Key Is_Active
ID | Description
--------- | ------- | -----------
0 | E-mail in active.
1 | E-mail active.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Forgot Password User

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "email": "example@mail.com",
        "message": "Permintaan Reset Password anada sudah dikirim melalui email dengan alamat example@mail.com"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T11:07:56.509893254+07:00"
}
```

### HTTP Request

`PUT {{base-endpoint}}/v1/user/forgot-password`

### PUT Parameters
Key | Required | Description
--------- | ------- | -----------
email | true | Your email want to Request Forgot Password.

## Reset Password User

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "email": "example@mail.com",
        "message": "Password berhasil diperbaharui"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T11:36:09.099276989+07:00"
}
```

### HTTP Request

`PUT {{base-endpoint}}/v1/user/forgot-password`

### PUT Parameters
Key | Required | Description
--------- | ------- | -----------
password | true | Set New Password.
password_confirm | true | Set Confirm Password same like Field above (New Password).

### Header Parameters
Key | Required | Description
--------- | ------- | -----------
Tokenreset | true | Got token from your mail.

# Company

## Get Company

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "array",
    "data": [
        {
            "id": 18,
            "name": "perusahaan baru",
            "description": "new new new ",
            "created_by": "malafauzana94@gmail.com",
            "updated_by": "",
            "created_date": "2018-12-12T11:19:15+07:00",
            "updated_date": "0001-01-01T00:00:00Z"
        },
        {
            "id": 17,
            "name": "7company",
            "description": "7description company",
            "created_by": "example@mail.com",
            "updated_by": "example@mail.com",
            "created_date": "2018-12-11T11:04:03+07:00",
            "updated_date": "2018-12-11T11:04:31+07:00"
        }
    ],
    "total": 6,
    "first_page": "http://e-document-api-dev.e-mas.com/v1/company/getall?per_page=20&page=1",
    "last_page": "http://e-document-api-dev.e-mas.com/v1/company/getall?per_page=20&page=1",
    "next_page": "",
    "timestamp": "2018-12-20T14:07:27.61204852+07:00"
}
```

### HTTP Request

`GET {{base-endpoint}}/v1/company/getall`

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Create Company

> Response JSON structured like this:

```json
{
    "code": 201,
    "type": "object",
    "data": {
        "id": 19,
        "name": "PT. Aurora Karya Indonesia",
        "description": "Boleh dilihat pegang jangan",
        "created_by": "example@mail.com",
        "updated_by": "",
        "created_date": "2018-12-20T14:16:54.798791686+07:00",
        "updated_date": "0001-01-01T00:00:00Z"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T14:16:54.847414648+07:00"
}
```

### HTTP Request

`POST {{base-endpoint}}/v1/company/create`

### POST Parameters
Key | Required | Description
--------- | ------- | -----------
name | true | Name of Company.
description | true | Company description detail.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Update Company

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "id": 19,
        "name": "PT. Aurora Karya Indonesia",
        "description": "Boleh dilihat pegang jangan oke",
        "created_by": "example@mail.com",
        "updated_by": "example@mail.com",
        "created_date": "2018-12-20T14:16:54+07:00",
        "updated_date": "2018-12-20T14:25:19.716476731+07:00"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T14:25:19.721164321+07:00"
}
```

### HTTP Request

`PUT {{base-endpoint}}/v1/company/update`

### PUT Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of company has registered.
name | true | Name of Company.
description | true | Company description detail.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Delete Parameters

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {},
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T14:38:28.91110367+07:00"
}
```

### HTTP Request

`DELETE {{base-endpoint}}/v1/company/delete`

### Query Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of company has registered.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

# Type

## Get Type

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "array",
    "data": [
        {
            "id": 37,
            "name": "create new type",
            "description": "description new type",
            "created_by": "example@mail.com",
            "updated_by": "",
            "created_date": "2018-12-14T13:44:09+07:00",
            "updated_date": "0001-01-01T00:00:00Z"
        },
        {
            "id": 36,
            "name": "type lama deh",
            "description": "deskripsi type lama deh ",
            "created_by": "example@mail.com",
            "updated_by": "example@mail.com",
            "created_date": "2018-12-13T10:46:35+07:00",
            "updated_date": "2018-12-13T10:46:58+07:00"
        }
    ],
    "total": 32,
    "first_page": "http://e-document-api-dev.e-mas.com/v1/type/getall?per_page=20&page=1",
    "last_page": "http://e-document-api-dev.e-mas.com/v1/type/getall?per_page=20&page=2",
    "next_page": "http://e-document-api-dev.e-mas.com/v1/type/getall?per_page=20&page=2",
    "timestamp": "2018-12-20T15:06:36.547179918+07:00"
}
```

### HTTP Request

`GET {{base-endpoint}}/v1/type/getall`

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Create Type

> Response JSON structured like this:

```json
{
    "code": 201,
    "type": "object",
    "data": {
        "id": 38,
        "name": "PHH",
        "description": "Perjanjian HA HA",
        "created_by": "example@email.com",
        "updated_by": "",
        "created_date": "2018-12-20T15:08:10.443480372+07:00",
        "updated_date": "0001-01-01T00:00:00Z"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T15:08:10.447715035+07:00"
}
```

### HTTP Request

`POST {{base-endpoint}}/v1/type/create`

### POST Parameters
Key | Required | Description
--------- | ------- | -----------
name | true | Name of type.
description | true | Detail from of type.

## Update Type

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "id": 38,
        "name": "PHH",
        "description": "Perjanjian HA HA",
        "created_by": "example@mail.com",
        "updated_by": "example@mail.com",
        "created_date": "2018-12-20T15:08:10+07:00",
        "updated_date": "2018-12-20T15:13:25.074509172+07:00"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T15:13:25.076703701+07:00"
}
```

### HTTP Request

`PUT {{base-endpoint}}/v1/type/update`

### PUT Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of type has registered.
name | true | Name of type.
description | true | Detail from of type.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Delete Type

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {},
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T14:38:28.91110367+07:00"
}
```

### HTTP Request

`DELETE {{base-endpoint}}/vi/type/delete`

### Query Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of type has registered.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

# Topic

## Get Topic

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "array",
    "data": [
        {
            "id": 3,
            "id_company": 1,
            "company_name": "PT. Orori Indonesia",
            "name": "Popular Mainsion",
            "description": "Kerjasama majalah popular",
            "created_by": "example@mail.com",
            "updated_by": "",
            "created_date": "2018-11-21T17:35:05+07:00",
            "updated_date": "0001-01-01T00:00:00Z",
            "email": [
                "example@mail.com",
                "indra.octama@gmail.com"
            ]
        },
        {
            "id": 5,
            "id_company": 1,
            "company_name": "PT. Orori Indonesia",
            "name": "PKL",
            "description": "PKL",
            "created_by": "example@mail.com",
            "updated_by": "",
            "created_date": "2018-11-22T14:36:32+07:00",
            "updated_date": "0001-01-01T00:00:00Z",
            "email": [
                "example@mail.com"
            ]
        }
    ],
    "total": 24,
    "first_page": "http://e-document-api-dev.e-mas.com/v1/topic/getall?per_page=20&page=1",
    "last_page": "http://e-document-api-dev.e-mas.com/v1/topic/getall?per_page=20&page=2",
    "next_page": "http://e-document-api-dev.e-mas.com/v1/topic/getall?per_page=20&page=2",
    "timestamp": "2018-12-20T15:30:05.04077053+07:00"
}
```
### HTTP Request

`GET {{base-endpoint}}/v1/topic/getall`

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Create Topic

> Response JSON structured like this:

```json
{
    "code": 201,
    "type": "object",
    "data": {
        "id": 37,
        "id_company": 1,
        "name": "Fiesta 3",
        "description": "Kerjasama majalah Fiesta 2",
        "email": [
            {
                "email": "example@mail.com"
            },
            {
                "email": "example@mail.com"
            }
        ],
        "created_by": "example@mail.com",
        "created_date": "2018-12-20T16:21:25.42426995+07:00"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T16:21:25.428827296+07:00"
}
```

### HTTP Request

`POST {{base-endpoint}}/v1/topic/create`

### POST Parameters
Key | Required | Description
--------- | ------- | -----------
id_company | true | Identity Document of company has registered.
name | true | Name of topic.
description | true | Detail from of topic.
email | true | who want user want to get notif.

<aside class="notice">
Post parameters <code>email</code>
ex: [{"email":"example@mail.com"},{"email":"example@mail.com"}]
</aside>

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Update Topic

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "id": 27,
        "id_company": 1,
        "name": "Popular Banget",
        "description": "Popular banget",
        "email": [
            {
                "email": "omyank2007i@gmail.com"
            },
            {
                "email": "indra.octama@orori.com"
            }
        ],
        "updated_by": "",
        "updated_date": "2018-12-20T16:25:05.838944313+07:00"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T16:25:05.842980497+07:00"
}
```

### HTTP Request

`PUT {{base-endpoint}}/v1/topic/update`

### PUT Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of topic has registered.
id_company | true | Identity Document of company has registered.
name | true | Name of topic.
description | true | Detail from of topic.
email | true | who want user want to get notif.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Delete Topic

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {},
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-20T16:25:45.730765161+07:00"
}
```

### HTTP Request

`DELETE {{base-endpoint}}/v1/topic/delete`

### Query Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of type has registered.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

# Document

## Get Document

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "array",
    "data": [
        {
            "id": 71,
            "name": "light-bulb-3104355_1280.jpg",
            "file_path": "downloads/2018.jpg",
            "id_type": 31,
            "id_topic": 29,
            "type": "test",
            "topic": "transfer keluar",
            "company": "PT e-mas",
            "is_expired": 0,
            "end_date": "2018-12-19T00:00:00+07:00",
            "created_by": "exapmle@mail.com",
            "updated_by": "SYSTEM AUTO UPDATE EMAIL END DATE",
            "created_date": "2018-12-12T11:17:41+07:00",
            "updated_date": "2018-12-12T11:30:00+07:00"
        }
    ],
    "total": 38,
    "first_page": "http://e-document-api-dev.e-mas.com/v1/document/getall?per_page=1&page=1",
    "last_page": "http://e-document-api-dev.e-mas.com/v1/document/getall?per_page=1&page=38",
    "next_page": "http://e-document-api-dev.e-mas.com/v1/document/getall?per_page=1&page=2",
    "timestamp": "2018-12-20T16:50:36.18958342+07:00"
}
```

### HTTP Request

`GET {{base-endpoint}}/v1/document/getall`

### Query Parameters
Key | Required | Description
--------- | ------- | -----------
per_page | false | how many data want to show.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Download Document

### HTTP Request

`GET {{base-endpoint}}/v1/document/download`

### Query Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of document has uploaded.

## Upload Document

> Response JSON structured like this:

```json
{
    "code": 201,
    "type": "object",
    "data": {
        "id": 72,
        "id_type": 34,
        "id_topic": 3,
        "name": "5.-Object.pdf",
        "file_path": "downloads/2018/December/21/2018-December-21-2-39-1-5.-Object.pdf",
        "end_date": "2019-12-05 00:00:00"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-21T09:39:01.358964355+07:00"
}
```

### HTTP Request

`POST {{base-endpoint}}/v1/document/upload`

### POST Parameters
Key | Required | Description
--------- | ------- | -----------
id_topic | true | Identity Document of company has registered.
id_type | true | Identity Document of type has registered.
end_date | true | Date file is expired.
file | true | File want to upload max size less than 100mb.

<aside class="notice">
Need authenticated <code>Header Parameters</code>
</aside>

## Update Document

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {
        "id": 72,
        "id_type": 34,
        "id_topic": 3,
        "name": "6.-Object.pdf",
        "file_path": "downloads/2018/December/21/2018-December-21-2-50-29-6.-Object.pdf",
        "end_date": "2019-12-19 00:00:00"
    },
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-21T09:50:29.89619903+07:00"
}
```

### HTTP Request

`PUT {{base-endpoint}}/v1/document/update`

### PUT Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of document has uploaded.
id_topic | true | Identity Document of company has registered.
id_type | true | Identity Document of type has registered.
end_date | true | Date file is expired.
file | true | File want to upload max size less than 100mb.

## Delete Document

> Response JSON structured like this:

```json
{
    "code": 200,
    "type": "object",
    "data": {},
    "total": 1,
    "first_page": "",
    "last_page": "",
    "next_page": "",
    "timestamp": "2018-12-21T09:52:11.727053577+07:00"
}
```

### HTTP Request

`DELETE {{base-endpoint}}/v1/document/delete`

### Query Parameters
Key | Required | Description
--------- | ------- | -----------
id | true | Identity Document of document has uploaded.