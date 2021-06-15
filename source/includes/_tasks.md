# Master Tasks

## Get All Master Tasks

```javascript
const result = await axios(
    'https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/tasks',
);
```

> The above command returns JSON structured like this:

```json
[
  {
    "category": "Beast Tribe Quests",
    "frequency": "Daily",
    "tasks": [
      "Amalj'aa",
      "Ananta",
      "Dwarves",
      "Ixal",
      "Kobolds",
      "Kojin",
      "Moogles",
      "Namazu",
      "Pixies",
      "Qitari",
      "Sahagin",
      "Sylphs",
      "Vanu Vanu",
      "Vath"
    ]
  },
  {
    "category": "Daily Hunts",
    "frequency": "Daily",
    "tasks": [
      "ARR",
      "Heavensward",
      "Shadowbringers",
      "Stormblood"
    ]
  }
]
```

This endpoint retrieves all master tasks.

### HTTP Request

`GET https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/tasks`

# User Tasks

## Get User Tasks with Today's Status

```javascript
const result = await axios(
    'https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/user/tasks',
);
```

> The above command returns JSON structured like this:

```json
[
  {
    "category": "Gold Saucer",
    "frequency": "Weekly",
    "tasks": [
      {
        "name": "Fashion Report",
        "done": true
      },
      {
        "name": "Jumbo Cactpot",
        "done": false
      }
    ]
  },
  {
    "category": "Raiding",
    "frequency": "Weekly",
    "tasks": [
      {
        "name": "Eden 9 - Umbra",
        "done": true
      }
    ]
  }
]
```

This endpoint retrieves all tasks the user has selected for their list.

### HTTP Request

`GET https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/user/tasks`

## Add Tasks to User List

```javascript
const result = await axios.post('https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/user/tasks', {
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

`POST https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/user/tasks`

### Body Parameters

Parameter | Type | Description
--------- | ----------- | -----------
category | `string` | The category of the task
frequency | `string` | The frequency of the task
tasks | `string[]` | A list of task names

# User Completed Tasks

## Save User Task for Today

```javascript
const result = await axios.post('https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/user/tasks/current', {
  "category": "Gold Saucer",
  "frequency": "Weekly",
  "task": "Jumbo Cactpot",
  "done": true
});
```

> The above command returns a 204 with no content.


This endpoint saves the submitted task status for the current day/week.

### HTTP Request

`POST https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/user/tasks/current`

## Save User Category for Today

```javascript
const result = await axios.post('https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/user/tasks/current', {
  "category": "Gold Saucer",
  "frequency": "Weekly",
  "done": true
});
```

> The above command returns a 204 with no content.


This endpoint saves all tasks under the given category for the current day/week.

### HTTP Request

`POST https://hdnss8awo4.execute-api.us-west-2.amazonaws.com/user/tasks/current`
