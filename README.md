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

> Endpoint: /users/login/

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

* **/api/users/login/** (User login endpoint)
* **/api/users/logout/** (User logout endpoint)

```python
let generateProject = project => {
  let code = [];
  for (let js = 0; js < project.length; js++) {
    code.push(js);
  }
};
```

---




A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo




### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
