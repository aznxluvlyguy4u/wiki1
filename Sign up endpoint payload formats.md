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
  "firstName":"Jane3",
	"lastName" : "Haha",
	"password" : "asdfg",
	"emailAddress": "yubin@jongensvantechniek.nl",
	"address" : {
		"country" : {
			"name" : "Netherlands",
                        "alpha2Code" : "NL",
                        "alpha3Code" : "NLD",
                        "callingCodes": ["57"]
		},
		"city" : {
			"name" : "The Hague"
		},
		"streetName" : "string",
		"streetNumber" : "12",
		"streetBlock" : "A",
		"postalCode" : "string",
		"phone" : {
			"landLine" : "string",
			"cellPhone" : "string",
			"countryCode" : "+031"
		}
	}
}
```

## Error

### Email address already exists

Response when email address already exists

HTTP 403 - Forbidden

Response body

```json
{
  "statusCode" : 403,
  "message": "Email address already exists, therefore cannot continue signup."
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
				"landLine" : "error message",
				"cellPhone" : "error message"
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