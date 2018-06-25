# Course statistics

Overall course statistics can be listed here.

## Listing overall training statistics

```shell
GET /course_statistics
```

### Response

```json
{
    "course_statistic": {
        "activated_courses": 10,
        "completion_average": 25,
        "completed_courses": 5,
        "graded_users": 15,
        "average_grade": 30,
        "certificate_count": 1,
        "average_rating": 0,
        "learn_time": 90000,
        "conclusion_average_time": 1234567
    }
}
```
### Course statistics fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| activated_courses | integer | Total number of activated courses |
| completion_average | integer | Average conclusion rate |
| completed_courses | integer | Total number of courses that reached 100% conclusion rate |
| graded_users | integer | Total number of trainees that have taken the tests |
| average_grade | integer | Average test grade |
| certificate_count | integer| Total number of certificates given |
| average_rating | integer | Average trainee rating of the courses |
| learn_time | integer | Total learning time |
| conclusion_average_time | integer | Average time taken to complete a course |

* **Searchable fields**

|  field  |  type  |  description  |
|---------|--------|---------------|
| product_id | id | Searches in course ids. Returns statistics for that specific course |
| group_id | id | Returns course statistics for that specific group |
