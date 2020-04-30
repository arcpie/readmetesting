# Flatentals

Flatentals is a web-app that manages apartment rentals. The font-end is developed using ReactJS and the back-end APIs are written in Python Django.

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

## API End Points

## Users

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
    "refresh": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTU4Nzk4NDYwNCwianRpIjoiZDdmNTQzNDI1Y2IxNGUzMGI2YWJjMjM2MDVhMDc5ODYiLCJ1c2VyX2lkIjoxMX0.rJzeTr_BGDj6q17XqQ2UeRrbW7aR8HQh2iLjszAoFEU",
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
            "phone_number": "xxxx-xxxxxx",
            "role": "realtor"
        },
        {
            "id": 2,
            "email": "client@gmail.com",
            "first_name": "Joey",
            "last_name": "Mark",
            "phone_number": "xxxx-xxxxxx",
            "role": "client"
        },
    ]
}
``` 

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
            "phone_number": "xxxx-xxxxxx",
            "role": "realtor"
        },
        {
            "id": 2,
            "email": "joey@gmail.com",
            "first_name": "Joey",
            "last_name": "Mark",
            "phone_number": "xxxx-xxxxxx",
            "role": "realtor"
        },
    ]
}
---
