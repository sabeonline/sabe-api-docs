# Catalogue

Here, all the available courses for a trainee will be presented. The courses are organized in a catalogue by categories. Each category has multiple items hat can be courses or documents. The catalogue is editable in the [backoffice](https://backoffice.sabe-extend.com) in the `Catalogue` menu. Each trainee may have a different list depending on the permissions configured in the backoffice.

## Trainee's catalogue

```shell
GET /trainees/{trainee_id}/catalogue
```

### Response

```json
  {
    "categories": [
      {
        "id": 100,
        "name": "Introduction to SABE Extend",
        "catalogue_items": [
          {
            "item_type": "Product",
            "item": {
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
              "tags": ["welcome", "beginners"],
            }
          },
          {
            "item_type": "Document",
            "item": {
              "id": 5001,
              "title": "teste",
              "url": "https://cdn.sabe-extend.com/content/documents/5001/welcome.pdf",
              "tags": ["welcome", "beginners"]
            }
          }
        ]
      },
    ]
  }
```

### Category fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| id | id | ID of the category
| name | string | Name of the category

Catalogue items description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| item_type | string | Type of the item that is in the category. Possible values: `Product`, `Document`

### Course fields description

See [Course fields description](courses.md#course-fields-description) in course page.

### Document fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| id | id | ID of the course
| title | string | Course title
| url | string | URL of the document
| tags | string | List of tags
