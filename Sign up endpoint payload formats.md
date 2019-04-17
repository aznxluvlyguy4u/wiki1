# Signup payload formats

As discussed on: 17-04-2019 by Silvia, Yubin & Steve.

## Sign-up / Register a new user 

**POST*** _/api/v1/users/register_

```json
{
	"firstName":"Jane3",
	"lastName" : "Haha",
	"password" : "asdfg",
	"emailAddress": "yubin@jongensvantechniek.nl",
	"address" : {
		"country" : {
			"countryCode" : 31,
			"name" : "Netherlands",
			"alpha2" : "NL"
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
			"mobile" : "string",
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
			"countryCode" : 31,
			"name" : "Netherlands",
			"alpha2" : "NL"
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
			"mobile" : "string",
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

```
{
  "statusCode" : 403,
  "message": "Email address already exists, therefore cannot continue signup."
}
```


### Field values are not valid

Response when individual fields are invalid


HTTP 400 - Bad request

Response body

```
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
				"mobile" : "error message"
			}
		}
	}
}
```

## GET countries response


HTTP 200 OK

Response body

```

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