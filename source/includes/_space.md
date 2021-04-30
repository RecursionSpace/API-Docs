# SPACE

## Space Details

> `GET` /v1/spaces <br> `GET` /v1/spaces/{space_id}

```shell
curl "https://api.recursion.space/v1/spaces/{xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx}" \
  -H "Authorization: Token xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

> RESPONSE

```json
[
  {
    "id": "xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "The Void",
    "address": "1331 12th Ave",
    "address2": "STE 205",
    "city": "Altoona",
    "state": "PA",
    "zipcode": "16601",
    "country": "United States",
    "email": "demo@recursion.space",
    "timezone": "UTC"
  }
]
```

Return a list of spaces owned by the API Token holder, or return information on a specific space by filtering with the space id.

### Returns

| Parameter |  Type  | Description                              |
| --------- | :----: | ---------------------------------------- |
| id        | string | The uniqe space identifier.              |
| name      | string | Your name for the space.                 |
| address   | string | The physical address of the space.       |
| address2  | string | Address line for STE, UNIT, BLD, ect.    |
| city      | string | City component of the spaces address.    |
| state     | string | State component of the spaces address.   |
| zipcode   | string | Zipcode component of the spaces address. |
| country   | string | Country where the space is located.      |
| email     | string | Primary/General email for the space.     |
| timezone  | string | Selected timezone for the space.         |

## Operators Details

> `GET` /v1/operators/{space_id}

```shell
curl "https://api.recursion.space/v1/operators/xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx" \
  -H "Authorization: Token xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

> RESPONSE

```json
[
  {
    "facility": "xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "cardNumber": "0123456789",
    "phone_number": ,
    "address": "1331 12th Ave",
    "city": "Altoona",
    "state": "PA",
    "zip_code": "16601",
    "username": "DemoUser",
    "first_name": "Lorem",
    "last_name": "Ipsum",
    "email": "demo@recursion.space",
  },
]
```

Retrive information for all operators ("admins") for the selected space.

### Returns

| Parameter    |  Type  | Description                                         |
| ------------ | :----: | --------------------------------------------------- |
| facility     | string | The facility id for which the operator belongs to.  |
| cardNumber   | string | The RFID number assigned to the operator.           |
| phone_number | string | Operator provided phone number.                     |
| address      | string | Operator provided address.                          |
| city         | string | City component of address provided by operator.     |
| state        | string | State component of address provided by operator.    |
| zip_code     | string | Zip Code component of address provided by operator. |
| username     | string | Username assosiated with the operators account.     |
| first_name   | string | Operators first name.                               |
| last_name    | string | Operators last name.                                |
| email        | string | Operator provided email.                            |

## Member Details

> `GET` /v1/members/{space_id}

```shell
curl "https://api.recursion.space/v1/members/xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx" \
  -H "Token: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

> RESPONSE

```json
[
  {
    "cardNumber": "0123456789",
    "access_group": 123,
    "phone_number": "calico",
    "address": 6,
    "city": 7,
    "state": ,
    "zip_code": ,
    "username": ,
    "first_name": ,
    "last_name": ,
    "email": ,
    "restricted_nodes": []
  },
]
```

Retrieve information for all members associated with a space.

### Returns

| Parameter        |  Type   | Description                                                               |
| ---------------- | :-----: | ------------------------------------------------------------------------- |
| cardNumber       | string  | The RFID number assigned to your member.                                  |
| access_group     | integer | The ID for the access group that the member belongs to.                   |
| phone_number     | string  | Member provided phone number.                                             |
| address          | string  | Member provided address.                                                  |
| city             | string  | City component of address provided by member.                             |
| state            | string  | State component of address provided by member.                            |
| zip_code         | string  | Zip Code component of address provided by member.                         |
| username         | string  | Username assosiated with the members account.                             |
| first_name       | string  | Members first name.                                                       |
| last_name        | string  | Members last name.                                                        |
| email            | string  | Member provided email.                                                    |
| restricted_nodes |  array  | List of IDs the member does not have access to within their access group. |

## Access Details

> GET /v1/permissions/{space_id}

```shell
curl "https://api.recursion.space/v1/permissions/xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx" \
  -H "Authorization: Token xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

> RESPONSE

```json
[
  {
    "id": 2,
    "name": "Max",
    "startTime": "unknown",
    "endTime": 5,
    "monday": 10,
    "tuesday": false,
    "wednesday": false,
    "thursday": false,
    "friday": false,
    "saturday": false,
    "sunday": false,
    "twenty_four_seven": true,
    "default_fallback": false,
    "facility": "xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "allowedNodes": [19]
  }
]
```

Returns the available permissions, or access groups, for the space.

### Returns

| Parameter         |     Type      | Description                                                           |
| ----------------- | :-----------: | --------------------------------------------------------------------- |
| id                |    integer    | The ID of the access group.                                           |
| name              |    string     | Name descriptor for the access group.                                 |
| startTime         |    integer    | The daily start time when access is permitted for this group.         |
| endTime           |    integer    | The daily end time when access is no longer permitted for this group. |
| monday            |    boolean    | True if access is is allowed for a Monday, otherwise false.           |
| tuesday           |    boolean    | True if access is is allowed for a Tuesday, otherwise false.          |
| wednesday         |    boolean    | True if access is is allowed for a Wednesday, otherwise false.        |
| thursday          |    boolean    | True if access is is allowed for a Thursday, otherwise false.         |
| friday            |    boolean    | True if access is is allowed for a Friay, otherwise false.            |
| saturday          |    boolean    | True if access is is allowed for a Saturday, otherwise false.         |
| sunday            |    boolean    | True if access is is allowed for a Sunday, otherwise false.           |
| twenty_four_seven |    boolean    | Set true if group is allowed acces 24 hours a day, 7 days a week.     |
| facility          |    string     | The ID for which the access group belongs to.                         |
| allowedNodes      | integer array | List of nodes permitted to be used within this group.                 |
