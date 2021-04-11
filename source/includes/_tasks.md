# Master Tasks

## Get All Master Tasks

```javascript
const result = await axios(
    'http://34.219.238.37/tasks',
);
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "Squadron Mission",
    "category": null,
    "frequency": "Daily",
    "orphan": true
  },
  {
    "name": "Treasure Map",
    "category": null,
    "frequency": "Daily",
    "orphan": true
  },
  {
    "name": "Amalj'aa",
    "category": "Beast Tribe Quests",
    "frequency": "Daily",
    "orphan": false
  },
  {
    "name": "Ananta",
    "category": "Beast Tribe Quests",
    "frequency": "Daily",
    "orphan": false
  }
]
```

This endpoint retrieves all master tasks.

### HTTP Request

`GET http://34.219.238.37/tasks`

# User Tasks

## Get All User Tasks

```javascript
const result = await axios(
    'http://34.219.238.37/user/tasks',
);
```

> The above command returns JSON structured like this:

```json
[
  {
    "category": "Gold Saucer",
    "frequency": "Weekly",
    "tasks": [
      "Fashion Report",
      "Jumbo Cactpot"
    ]
  },
  {
    "category": "Raiding",
    "frequency": "Weekly",
    "tasks": [
      "Eden 9 - Umbra"
    ]
  }
]
```

This endpoint retrieves all tasks the user has selected for their list.

### HTTP Request

`GET http://34.219.238.37/user/tasks`

## Save User Tasks

```javascript
const result = await axios.post('http://34.219.238.37/user/tasks', {
  "category": "Gold Saucer",
  "frequency": "Weekly",
  "tasks": [
    "Jumbo Cactpot"
  ]
});
```

> The above command returns JSON structured like this:

```json
{
  "category": "Gold Saucer",
  "frequency": "Weekly",
  "tasks": [
    "Jumbo Cactpot"
  ]
}
```

This endpoint save tasks the user has selected for their list, for a particular category.

### HTTP Request

`POST http://34.219.238.37/user/tasks`

### Body Parameters

Parameter | Type | Description
--------- | ----------- | -----------
category | `string` | The category of the task
frequency | `string` | The frequency of the task
tasks | `string[]` | A list of task names
