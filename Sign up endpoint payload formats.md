# Signup payload formats

As discussed on: 17-04-2019 by Silvia, Yubin & Steve.

# User endpoint

## Sign-up / Register a new user 

**POST** _/api/v1/users/register_

```json
{
	"firstName" : "Yubin",
	"lastName" : "Haha",
	"password" : "Pa$$word",
	"emailAddress": "yubin04@jongensvantechniek.nl",
	"dateOfBirth": "1983-10-18",
	"address" : {
		"country" : {
			"name" : "Netherlands",
            "alpha2Code" : "NL",
            "callingCodes": "57"
		},
		"city" : {
			"name" : "The Hague"
		},
		"streetName" : "string",
		"streetNumber" : "12",
		"streetBlock" : "A",
		"postalCode" : "string",
		"phone" : {
			"phoneNumber" : "string",
            "countryCode" : "+031"
		}
	}
}
```

### Created 

HTTP 201 OK 

Response body

```json
{
    "statusCode": 201,
    "data": {
        "id": 5,
        "uuid": "1960bf4f-6f24-4798-a55b-4ba765fe2e73",
        "firstName": "Yubin",
        "middleName": null,
        "lastName": "Haha",
        "dateOfBirth": "1983-10-18",
        "emailAddress": "yubin04@jongensvantechniek.nl",
        "password": "Pa$$word",
        "address": {
            "id": 5,
            "uuid": "8028258d-06f2-46db-942e-fab033b65a5b",
            "streetName": "string",
            "streetNumber": 12,
            "streetNumberBlock": null,
            "postalCode": "string",
            "phone": {
                "id": 5,
                "uuid": "162d925d-6b94-42bd-8507-0df621a68dc9",
                "phoneNumber" : "string",
                "countryCode": "+031",
                "addresses": []
            },
            "persons": []
        },
        "roles": [],
        "enabled": false
    },
    "status": null
}
```

## Error

### Email address already exists

Response when email address already exists

HTTP 403 - Forbidden

Response body

```json
{
    "statusCode": 403,
    "data": null,
    "status": "Emailaddress exists"
}
```


### Field values are not valid

Response when individual fields are invalid


HTTP 400 - Bad request

Response body

```json
{
	"statusCode" : 400,
	"message" : {
		"firstName":"error message",
		"lastName" : "error message",
		"emailAddress": "error message",
		"address" : {
			"country" : "error message",
			"city" : "error message",
			"streetNumber" : "error message",
			"streetBlock" : "error message",
			"postalCode" : "error message",
			"phone" : {
				"phoneNumber" : "error message",
                                "countryCode" : "error message"
			}
		}
	}
}
```

# Countries endpoint

**GET** /api/v1/countries

HTTP 200 OK

Response body

```json

{
	[
		{
			"name" : "Netherlands",
			"alpha2Code" : "NL",
			"alpha3Code" : "NLD",
			"callingCodes": ["57"]
			
		},
		{
			"name" : "Netherlands",
			"alpha2Code" : "NL",
			"alpha3Code" : "NLD",
			"callingCodes": ["57"]
		}
	]
}

```