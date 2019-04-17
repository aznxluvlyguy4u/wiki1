17-04-2019

##POST to /register
```
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

##Response when emailaddress already exists
```
{
	"statusCode" : 403
}
```

## Response when individual fields are invalid
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