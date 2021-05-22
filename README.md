# Water My Plants API
## https://ft-water-my-plants-3.herokuapp.com
### What To Know About This API
I've made a LOT of endpoints. Some will be useful, some are just for reference (and maybe you want them, I don't know, I'm not your mom). JSON examples listed underneath this list. Don't care about reference? These are the ones you want:

### [GET] /api/plants/:plant_id
***RESTRICTED ENDPOINT***

See the plant data (including plant owner) at a :plant_id

### [POST] /api/plants/user/:user_id
***RESTRICTED ENDPOINT***

Post a plant to a user's data using the user's user_id

### [PUT] /api/plants/:user_id/:plant_id
***RESTRICTED ENDPOINT***

Edit a plant's information using the user id and the plant id

### [DELETE] /api/plants/:user_id/:plant_id
***RESTRICTED ENDPOINT***

Remove a plant using the user id and the plant id

### [GET] /api/users/:user_id
***RESTRICTED ENDPOINT***

See a specific user's information

### [GET] /api/users/:user_id/plants
***RESTRICTED ENDPOINT***

See all plants created by a single user

### [POST] /api/users/register
Create a new user

### [POST] /api/users/login
Logs in a user, recieves a token for authorization

### [PUT] /api/users/:user_id
***RESTRICTED ENDPOINT***

Edit the user's information

## Plants
##### [GET] /api/plants
***RESTRICTED ENDPOINT***

See the full array of plants
<details>

```JSON
[
    {
        "plant_id": 1,
        "nickname": "Fish",
        "species": "gillyweed",
        "h20_frequency": 3,
        "image": null,
        "plant_owner_id": 1,
        "plant_owner": "connie"
    },
    {
        "plant_id": 2,
        "nickname": "Tailss",
        "species": "dirigible plum",
        "h20_frequency": 3,
        "image": null,
        "plant_owner_id": 2,
        "plant_owner": "michael"
    },
    {
        "plant_id": 3,
        "nickname": "Tyke",
        "species": "mandrake",
        "h20_frequency": 3,
        "image": null,
        "plant_owner_id": 3,
        "plant_owner": "dave"
    },
    {
        "plant_id": 4,
        "nickname": "Pussy Patty",
        "species": "bubotuber",
        "h20_frequency": 3,
        "image": null,
        "plant_owner_id": 4,
        "plant_owner": "veronica"
    },
    {
        "plant_id": 5,
        "nickname": "Wiggles",
        "species": "venomous tentacula",
        "h20_frequency": 3,
        "image": null,
        "plant_owner_id": 5,
        "plant_owner": "jonathan"
    },
    {
        "plant_id": 6,
        "nickname": "Turtle",
        "species": "shrivelpig",
        "h20_frequency": 3,
        "image": null,
        "plant_owner_id": 6,
        "plant_owner": "daniel"
    }
]
```

</details>

##### [GET] /api/plants/:plant_id
***RESTRICTED ENDPOINT***

See the plant data (including plant owner) at a :plant_id
<details>

/api/plants/1

```JSON
{
    "plant_id": 1,
    "nickname": "Fish",
    "species": "gillyweed",
    "h20_frequency": 3,
    "image": null,
    "plant_owner_id": 1,
    "plant_owner": "connie"
}
```

</details>

##### [POST] /api/plants/user/:user_id
***RESTRICTED ENDPOINT***

Post a plant to a user's data using the user's user_id

> *** Required information ***
> nickname
> species
> h20_frequency

> *** Optional information ***
> image

<details>

/api/plants/user/2

```JSON
{
    "plant_id": 9,
    "nickname": "Spike",
    "species": "cactus",
    "h20_frequency": 1200,
    "image": null
}
```

</details>

##### [PUT] /api/plants/:user_id/:plant_id
***RESTRICTED ENDPOINT***

Edit a plant's information using the user id and the plant id

> *** Required information ***
> nickname
> species
> h20_frequency

> *** Optional information ***
> image

<details>

/api/plants/user/2/9

```JSON
{
    "nickname": "Spikey",
    "species": "cactus",
    "h20_frequency": 1200
}
```

</details>

##### [DELETE] /api/plants/:user_id/:plant_id
***RESTRICTED ENDPOINT***

Remove a plant using the user id and the plant id
<details>

/api/plants/user/2/9

```JSON
{
    "message": "Did your plant die? That's okay. I'm only judging you the slightest bit."
}
```

</details>

## Users
##### [GET] /api/users
***RESTRICTED ENDPOINT***

See the full array of users
<details>

```JSON
[
    {
        "user_id": 1,
        "username": "connie",
        "phone_number": "1118675309"
    },
    {
        "user_id": 2,
        "username": "michael",
        "phone_number": "2228675309"
    },
    {
        "user_id": 3,
        "username": "dave",
        "phone_number": "3338675309"
    },
    {
        "user_id": 4,
        "username": "veronica",
        "phone_number": "4448675309"
    },
    {
        "user_id": 5,
        "username": "jonathan",
        "phone_number": "5558675309"
    },
    {
        "user_id": 6,
        "username": "daniel",
        "phone_number": "6668675309"
    }
]
```

</details>

##### [GET] /api/users/:user_id
***RESTRICTED ENDPOINT***

See a specific user's information
<details>

```JSON
{
    "user_id": 3,
    "username": "dave",
    "phone_number": "3338675309"
}
```

</details>

##### [GET] /api/users/:user_id/plants
***RESTRICTED ENDPOINT***

See all plants created by a single user
<details>

```JSON
[
    {
        "plant_id": 3,
        "nickname": "Tyke",
        "species": "mandrake",
        "h20_frequency": 3,
        "image": null
    }
]
```

</details>

##### [POST] /api/users/register
Create a new user

> *** Required information ***
> username
> phone_number
> password

<details>

```JSON
{
    "user_id": 7,
    "username": "gabe",
    "phone_number": "7778675309"
}
```

</details>

##### [POST] /api/users/login
Logs in a user, recieves a token for authorization

> *** Required information ***
> username
> password

<details>

```JSON
{
    "message": "Login successful",
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImdhYmUiLCJpYXQiOjE2MjE2NjEwODMsImV4cCI6MTYyMTc0NzQ4M30.7VWM3Q1JWAgw-HWKpDCu2GZN4AzVlkA-FUZoEIO0oZg"
}
```

</details>

##### [PUT] /api/users/:user_id
***RESTRICTED ENDPOINT***

Edit the user's information

> *** Required information ***
> username
> phone_number
> password

<details>

```JSON
{
    "username": "gabe",
    "password": "password",
    "phone_number": 7778675308
}
```

</details>

##### [DELETE] /api/users/:user_id
***RESTRICTED ENDPOINT***

Delete a user
<details>

```JSON
{
    "message": "Sorry you hate plants."
}
```

</details>