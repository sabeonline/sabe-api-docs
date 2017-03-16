# Trainees

Trainees are all people who are able to see and consume existing courses. You can create, delete and see a trainee's data.

## Creating a trainee

```shell
POST /trainees
```

### Payload

```json
  {
    "trainee": {
      "name": "John Smith",
      "email": "john.smith@yourcompany.com",
      "code": "company_code",
      "groups": [1, 2, 3],
      "initialize": true
    }
  }
```

### Fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| name | string | Required. Person's name
| email | string | Required. Person's email
| code | string | Optional. Company's internal code to identify the trainee
| groups | array | Optional. An array with the ids of the groups where the trainee belongs. These Ids can be found in the Groups page in the [backoffice](https://backoffice.sabe-extend.com) or in [groups](groups.md) endpoint
| initialize | boolean | Optional. Determines if a tranee is created inactive or already activated, with courses.

### Response

```json
  {
    "id": 1234567,
    "name": "John Smith",
    "email": "john.smith@yourcompany.com",
    "code": "company_code",
    "status": "active",
    "groups": [
      {
        "id": 12345678,
        "name": "Awesome trainees"
      }
    ]
  }
```

## Updating a trainee

```shell
PUT /trainees/{trainee_id}
```

[Payload](#payload), [fields](#fields-description) and [response](#response) are the same as trainee creation.

## List trainees

```shell
GET /trainees
```

### Response

```json
  [
    {
      "id": 1234567,
      "name": "John Smith",
      "email": "john.smith@yourcompany.com",
      "code": "company_code",
      "status": "active",
      "groups": [
        {
          "id": 12345678,
          "name": "Awesome trainees"
        }
      ]
    },
    {
      "id": 1234568,
      "name": "Susie Cooper",
      "email": "susie.cooper@yourcompany.com",
      "code": "company_code",
      "status": "disabled",
      "groups": [
        {
          "id": 12345678,
          "name": "Awesome trainees"
        }
      ]
    }
  ]
```

Trainees are [searchable](/README.md#search) and [sortable](/README.md#sort) as described in main page.

* **Searchable fields**

|  field  |  type  |  description  |
|---------|--------|---------------|
| q | string | Free text. Searches in trainee name, email and code |
| status | string | Possible values: `inactive`, `active` and `disabled` |
| group_id | number | Existing group id. Returns all trainees in that specific group |

* **Sortable fields**
  * name (default)
  * id
  * email
  * code

## Show trainee

```shell
GET /trainees/{trainee_id}
```

The [response](#response) is the same as in trainee creation.

## Remove trainee

```shell
DELETE /trainees/{trainee_id}
```
