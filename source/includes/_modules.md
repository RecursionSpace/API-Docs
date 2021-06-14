# MODULES

Modules refer to the safety and training "courses" that can be created within the system.

## Module List

>`GET` /v1/modules/{space_id}

```shell
curl "https://api.recursion.space/v1/modules/xxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx" \
  -H "Authorization: Token xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

> RESPONSE

```json
[
    {
        "id": #,
        "name": "Proper Tool Lesson",
        "brand": "DeWaukee",
        "model": "TorqueHammer 3000",
        "general_reading": "<p>Lorem ipsum dolor sit amet....</p>",
        "video": "https://youtube.com",
        "classmaker": "https://classmaker.com",
        "required_training": true,
        "classlink": "https://calendar.com",
        "archive": false

    },
]
```

Returns the details for all modules created at the selected space.

### Returns

| Parameter         |  Type   | Description                                                  |
| ----------------- | :-----: | ------------------------------------------------------------ |
| id                | integer | Identification number of the module.                         |
| name              | string  | The user defined name for the module.                        |
| brand             | string  | Brand name of tool the module is assosiated with.            |
| model             | string  | Model name of the tool the module is associated with.        |
| general_reading   | string  | HTML formatted reading material.                             |
| video             | string  | URL for an instructional video for the module.               |
| classmaker        | string  | URL for the test/quiz of the module.                         |
| required_training | boolean | Indicates if in-person training is a requirement.            |
| classlink         | string  | URL to the registration location for the in-person training. |
| archive           | boolean | Indicator if the module is active or not.                    |

## Module Progress

>`GET`  /v1/moduleprogress/{username} <br> `POST` /v1/moduleprogress/{username}

```shell
curl "https://api.recursion.space/v1/moduleprogress/username" \
 -H "Token: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" \

curl -X POST "https://api.recursion.space/v1/moduleprogress/username" \
 -H "Token: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" \
 -d "module=##"
 -d "param=value"
```

> GET RESPONSE

```json
[
    {
        "module": #,
        "general_reading_completed": true,
        "video_completed": false,
        "classmaker_initiated": true,
        "classmaker_completed": false,
        "required_training_initiated": false,
        "required_training_completed": false,
        "username": "AwesomeMember"
    },
]
```

`GET: Returns the progress for all modules assosiated with a selected user.` <br>
`POST: Update one or more progress parameters for a selected module.`

### Returns

| Parameter                   |  Type   | Description                                                                 |
| --------------------------- | :-----: | --------------------------------------------------------------------------- |
| module                      | integer | The ID of the modules.                                                      |
| general_reading_completed   | boolean | An indication of the user has clicked open the reading material.            |
| video_completed             | boolean | And indication if the user has viewed the video of the module.              |
| classmaker_initiated        | boolean | An indicator that the user has clicked the assosiated exam link.            |
| classmaker_completed        | boolean | Set by the admin once the user has module exam has been passed sucessfully. |
| required_training_initiated | boolean | An indicator that he user has clicked to schedule a training time.          |
| required_training_completed | boolean | Set by the admin once the required training has been complete.              |
| username                    | string  | Username assosiated with the operators account.                             |
