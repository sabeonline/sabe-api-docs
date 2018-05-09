# Trainee statistics

Training statistics can be listed here.

## Listing detailed training statistics

```shell
GET /user_statistics
```

### Response

```json
  [
    {
        "course_name": "Welcome to SABE Extend",
        "user_name": "John Smith",
        "user_email": "john.smith@yourcompany.com",
        "external_code": "external_code",
        "activation_date": "2017-05-31",
        "conclusion_rate": 100,
        "test_grade": 50,
        "test_date": "2017-09-01",
        "certificate": true,
        "conclusion_date": "2017-10-13",
        "course_rating": 5,
        "progress_id": "123abc",
        "product_id": 1234,
        "product_slug": "welcome-to-sabe-extend",
        "trainee_id": 56789,
        "trainee_status_name": "active",
        "groups": [
            111
        ],
        "learn_time": 6000,
        "conclusion_time": 3712852,
        "started_at": "2017-08-31T14:17:20.449Z",
        "finished_at": "2017-10-13T13:38:12.702Z"
    },
  ]
```

### User statistics fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| course_name | string | Name of the course |
| user_name | string | Name of the trainee |
| user_email | string | Email of the trainee |
| external_code | string | Company's internal code to identify the trainee |
| activation_date | timestamp |
| conclusion_rate | integer | Course completion rate (0 to 100) |
| test_grade | integer | Trainee test grade (0 to 100). `null` if the test was not taken |
| test_date | timestamp | Date on which the trainee took the test. `null` if not taken |
| certificate | boolean | `true` when the conclusion rate is equal to 100% and test grade is above 50%, `false` otherwise
| conclusion_date | date | Date of the course conclusion. `null` if not concluded |
| course_rating | integer | Trainee rating of the course. Values can range from `0` to `5`, `null` if none given |
| progress_id | string |
| product_id | id | ID of the product |
| product_slug | string | Slug of the product |
| trainee_id | id | ID of the trainee |
| trainee_status | string | Possible values: `inactive`, `activated`, `deactivated` |
| groups | array | An array with the ids of the groups where the trainee belongs. These Ids can be found in the Groups page in the [backoffice](https://backoffice.sabe-extend.com) or in [groups](groups.md) endpoint
| learn_time | integer | Time consumed in seconds |
| conclusion_time | integer | Overall time consumed by the trainee from start to course completion. `null` if not completed |
| started_at | timestamp | Date on which the trainee began the course |
| finished_at | timestamp | Date on which the trainee finished the course. `null` if not finished |

* **Searchable fields**

|  field  |  type  |  description  |
|---------|--------|---------------|
| q | string | Free text. Searches in trainee name, email and external code |
| product_id | id | Searches in course ids. Returns all statistics of trainees taking that specific course |
| group_id | id | Returns all statistics of trainees in that specific group  |

* **Sortable fields**
  * user_name (default)
  * collaborator_code
  * course_name
  * activation_date
  * conclusion_rate
  * test_grade
  * test_date
  * certificate
  * conclusion_date
  * course_rating
  * conclusion_time
