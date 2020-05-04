# Flatentals

Flatentals is a web-app that manages apartment rentals. The font-end is developed using React and the back-end APIs are written in Python Django.

## React - Getting Started

These instructions will get you a copy of the projects front-end up and running on your local machine.

### Prerequisites
```
node.js
npm/yarn
```

### Setup

- Clone the front-end repo on your system.

> install node dependencies/modules
```shell
$ npm install
```

> run the server

```shell
$ npm start
```

## Django - Getting Started

These instructions will get you a copy of the projects back-end up and running on your local machine.

### Prerequisites
```
Python
Pip
virtualenv
```

### Setup

- Clone the back-end repo on your system.

> update the database settings in apartment_rentals_be/setting.py

```python
DATABASES = {
    'default': {
        'ENGINE': '',
        'NAME': '',
        'USER': '',
        'PASSWORD': '',
        'HOST': '',
        'PORT': '',
    }
}
```

> create and activate virtual environment

Creating the virtual environment

```shell
$ virtualenv venv
```
Activating the virtual environment

Mac OS / Linux
```shell
$ source venv/bin/activate
```
Windows
```shell
$ venv\Scripts\activate
```

> install the dependencies using the requirements.txt file

```shell
$ pip install -r requirements.txt
```

> make database migrations

```shell
$ python manage.py makemigrations
$ python manage.py migrate
```

> run the server

```shell
$ python manage.py runserver
```

## API End Points

## Users

#### Create User
> HTTP Method: POST

> Endpoint: /user/create/

> Authorization: None

#### Request Payload 
```python
{
	"email": "client@gmail.com",
	"password": "12345",
	"first_name": "John",
	"last_name": "Terry",
	"phone_number": "xxxx-xxxxxxx",
	"role": "client"
}
```

#### Sample Response Body 
```python
{
    "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTg4MjY2MjY4LCJqdGkiOiJmNTkzZTM0ZTY3YjI0NTEyODQyYzU5ZDc5OGU3YmNjNyIsInVzZXJfaWQiOjIyfQ.3X8ThIpInv_V0Sq_VkyHgjD62gfvc1_F5t65iNUwiTI",
    "user": {
        "id": 1,
        "email": "client@gmail.com",
	    "password": "12345",
	    "first_name": "John",
	    "last_name": "Terry",
	    "phone_number": "xxxx-xxxxxxx",
	    "role": "client"
    }
}
```
---

#### User Login
> HTTP Method: GET

> Endpoint: /user/login/

> Authorization: None

#### Request Payload 
```python
{
    "email": "client@gmail.com",
    "password": "A@-#ksjSWj#"
}
```

#### Sample Response Body 
```python
{
    "access": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTkwNDkwMjA0LCJqdGkiOiI2MDUwOTQ5YzkyYmI0OWUwYTMyNGUyNTFhZTJjNmM4YiIsInVzZXJfaWQiOjExfQ.tNbnttDFU_3fGB-M28cUd4-bSH6v1ZeP1Vxta3M-dV4",
    "user": {
        "id": 1,
        "email": "client@gmail.com",
        "first_name": "John",
        "last_name": "Terry",
        "phone_number": "xxxx-xxxxxxx",
        "role": "client"
    }
}
``` 
---

#### User List
> HTTP Method: GET

> Endpoint: /user/list/

> Authorization: Bearer Token

#### Sample Response Body 
```python
{
    "count": 2,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 1,
            "email": "realtor@gmail.com",
            "first_name": "Joey",
            "last_name": "Mark",
            "phone_number": "xxxx-xxxxxxx",
            "role": "realtor"
        },
        {
            "id": 2,
            "email": "client@gmail.com",
            "first_name": "Joey",
            "last_name": "Mark",
            "phone_number": "xxxx-xxxxxxx",
            "role": "client"
        },
    ]
}
``` 
---

#### Realtor List
> HTTP Method: GET

> Endpoint: /user/realtorlist/

> Authorization: Bearer Token

#### Sample Response Body 
```python
{
    "count": 2,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 1,
            "email": "realtor@gmail.com",
            "first_name": "Joey",
            "last_name": "Mark",
            "phone_number": "xxxx-xxxxxxx",
            "role": "realtor"
        },
        {
            "id": 2,
            "email": "joey@gmail.com",
            "first_name": "Joey",
            "last_name": "Mark",
            "phone_number": "xxxx-xxxxxxx",
            "role": "realtor"
        },
    ]
}
```
---

#### User Details
> HTTP Method: GET

> Endpoint: /user/id/

> Authorization: Bearer Token

#### Sample Response Body 
```python
{
    "id": 1,
    "email": "client@gmail.com",
    "first_name": "John",
    "last_name": "Terry",
    "phone_number": "xxxx-xxxxxxx",
    "role": "client"
}
``` 
---

#### User Update
> HTTP Method: PUT

> Endpoint: /user/id/update/

> Authorization: Bearer Token

#### Request Payload 
```python
{
	"password": "12345",
	"first_name": "first name",
	"last_name": "last name",
	"phone_number": "xxxx-xxxxxxx"
}
```

#### Sample Response Body 
```python
{
    "email": "client@gmail.com",
    "password": "12345",
	"first_name": "first name",
	"last_name": "last name",
	"phone_number": "xxxx-xxxxxxx",
    "role": "client"
}
``` 
---

#### User Delete
> HTTP Method: DELETE

> Endpoint: /user/id/delete/

> Authorization: Bearer Token

---

## Apartments

#### Create Apartment
> HTTP Method: POST

> Endpoint: /apartment/create/

> Authorization: Bearer Token

#### Request Payload 
```python
{
    "name": "Apartment 1",
    "description": "This is apartment description",
    "floor_area_size": 500,
    "price_per_month": 99.99,
    "num_rooms": 4,
    "latitude": 33.33,
    "longitude": 45,
    "realtor_id": 1
}
```

#### Sample Response Body 
```python
{
    "id": 1,
	"name": "Apartment 1",
	"description": "This is apartment description",
	"floor_area_size": 500,
	"price_per_month": 99.99,
	"num_rooms": 4,
	"latitude": 33.33,
	"longitude": 45,
	"realtor": {
                "id": 1,
                "email": "realtor@gmail.com",
                "first_name": "John",
                "last_name": "Terry",
                "phone_number": "xxxx-xxxxxxx",
                "role": "realtor"
            }
    }

}
```
---

#### Apartment List
> HTTP Method: GET

> Endpoint: /apartment/list/

> Authorization: Bearer Token

#### Filter Parameters
```
{
    "min_size": 50,
    "max_size": 200,
    "min_price": 100,
    "max_price": 500,
    "min_rooms": 2,
    "max_rooms": 4
}
```

#### Sample Response Body 
```python
{
    "count": 10,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 1,
            "name": "Apartment 1",
            "description": "This is apartment description",
            "floor_area_size": 123.455,
            "price_per_month": 34.22,
            "num_rooms": 2,
            "latitude": "-9.33456600",
            "longitude": "18.23440000",
            "state": "available",
            "added_date": "2020-04-30",
            "realtor": {
                "id": 1,
                "email": "realtor@gmail.com",
                "first_name": "John",
                "last_name": "Terry",
                "phone_number": "xxxx-xxxxxxx",
                "role": "realtor"
            }
        },
        {
            "id": 2,
            "name": "Apartment 2",
            "description": "This is apartment description",
            "floor_area_size": 123.455,
            "price_per_month": 34.22,
            "num_rooms": 2,
            "latitude": "-43.33456600",
            "longitude": "55.23440000",
            "state": "available",
            "added_date": "2020-04-30",
            "realtor": {
                "id": 1,
                "email": "realtor@gmail.com",
                "first_name": "John",
                "last_name": "Terry",
                "phone_number": "xxxx-xxxxxxx",
                "role": "realtor"
            }
        },
}
```
---

#### Apartment Details
> HTTP Method: GET

> Endpoint: /apartment/id/

> Authorization: Bearer Token

#### Sample Response Body 
```python
{
    "id": 1,
    "name": "Apartment 1",
    "description": "This is apartment description",
    "floor_area_size": 123.455,
    "price_per_month": 34.22,
    "num_rooms": 5,
    "latitude": "12.33456600",
    "longitude": "123.23440000",
    "state": "rented",
    "added_date": "2020-04-23",
    "realtor": {
        "id": 1,
        "email": "realtor@gmail.com",
        "first_name": "John",
        "last_name": "Terry",
        "phone_number": "xxxx-xxxxxxx",
        "role": "realtor"
    }
}
```
---

#### Update Apartment
> HTTP Method: PUT

> Endpoint: /apartment/id/update

> Authorization: Bearer Token

#### Request Payload 
```python
{
	"name": "Apartment 1",
	"description": "This is apartment description",
	"floor_area_size": 500,
	"price_per_month": 99.99,
	"num_rooms": 4,
	"latitude": 33.33,
	"longitude": 45,
	"realtor_id": 1,
	"state": "rented",
}
```

#### Sample Response Body 
```python
{
    "id": 1,
    "name": "Apartment 1",
    "description": "This is apartment description",
    "floor_area_size": 123.455,
    "price_per_month": 34.22,
    "num_rooms": 5,
    "latitude": "12.33456600",
    "longitude": "123.23440000",
    "state": "rented",
    "added_date": "2020-04-23",
    "realtor": {
        "id": 1,
        "email": "realtor@gmail.com",
        "first_name": "John",
        "last_name": "Terry",
        "phone_number": "xxxx-xxxxxxx",
        "role": "realtor"
    }
}
```
---

#### Apartment Delete
> HTTP Method: DELETE

> Endpoint: /apartment/id/delete/

> Authorization: Bearer Token

---

