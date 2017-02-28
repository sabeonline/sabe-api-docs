# Progresses

Trainees progresses can be listed here.

## Listing progresses for a trainee

```shell
GET /trainees/{trainee_id}/progresses
```

### Response

```json
  [
    {
      "product_id": 2002,
      "url": "https://training.sabe-extend.com/learn/welcome-to-sabe-extend/consume",
      "active": true,
      "completion": 100,
      "finished_at": "2017-02-21T15:44:50.000+00:00",
      "certificate": "https://training.sabe-extend.com/learn/welcome-to-sabe-extend/certificate.pdf?user_id=1235",
      "completed_chapters": [
        1001, 1002, 1003, 1004
      ],
      "course": {
        "id": 2002,
        "slug": "welcome-to-sabe-extend",
        "title": "Welcome to SABE Extend",
        "image": {
          "small": "http://cdn.sabe-extend.com/content/courses/100/small_image.png",
          "large": "http://cdn.sabe-extend.com/content/courses/100/large_image.png"
        },
        "duration": 1472,
        "language": "en",
        "short_description": "<p>This is a course to learn how to use <b>SABE Extend</b> platform</p>",
        "description": "<p>In this course, you will learn how to create content, publish to your audience and monitor the results.",
        "going_learn": "<p>How to create amazing content</p><p>How to distribute the content to your network</p><p>How to monitor student's activity</p>",
        "intended_for": "<p>Content publishers</p>",
        "attachments_text": "<p>Users manual</p><p>Users manual</p>",
        "tags": ["welcome", "beginners"]
      }
    }
  ]
```

### Progress fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| product_id | id | ID of the product
| url | string | URL to the course consumption console
| active | boolean | Status of the course for the trainee. If false, he will not be able to do the course
| completion | integer | Percentage of completion
| started_at | timestamp | Time of course start. Set at the first time the trainee enters the consumptions console. `null` if trainee has not started
| finished_at | timestamp | Time of course conclusion. `null` if trainee has not ended
| certificate | string | URL of the certificate PDF. `null` if trainee has not ended
| completed_chapters | array | Array with the ids of the chapters that the trainee has completed

### Course fields description

See [Course fields description](courses.md#course-fields-description) in course page.
