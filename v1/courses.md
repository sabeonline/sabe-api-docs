# Courses

Details of the course and completing a chapter from external integration.

## Trainee's catalogue

```shell
GET /courses/{course_id}
```

### Response

```json
{
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
  "authors": [
    {
      "first_name": "Patrick",
      "last_name": "Pinto",
      "biography": "This author has a large experience producing SABE Extend courses",
      "avatar": "http://cdn.sabe-extend.com/content/authors/1904/avatar.jpg",
      "gender": 1,
      "kind": "main"
    }
  ],
  "course_modules": [
    {
      "id": 220,
      "title": "Introduction",
      "duration": 298,
      "chapters": [
        {
          "id": 1210,
          "title": "Welcome!",
          "duration": 158,
          "optional": false,
          "content_type": "Video"
        },
        {
          "id": 1211,
          "title": "Author's presentation",
          "duration": 140,
          "optional": true,
          "content_type": "Video"
        }
      ]
    }
  ]
}
```

### Course fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| id | id | ID of the course
| slug | string | Unique string identifier of the course
| title | string | Course title
| image | string | Images's URLs of the course
| duration | integer | Duration in seconds of the course
| language | string | Language of the course. Possible values: `en`, `pt_pt`, `it`, `fr`, `es`, `de`
| short_description | html | Small description of the course
| description | html | Description complement of the course
| going_learn | html | List of useful topics that the course approaches
| intended_for | html | List of who the course is intended for
| attachments_text | html | List of available attachments
| tags | string | List of tags

### Author fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| first_name | string | Author's first name
| last_name | string | Author's last name
| biography | html | Author's biography
| avatar | string | Author's avatar URL
| gender | integer | Author's gender. Possible values: `0`: female, `1`: male,
| kind | string | Type of author's contribution. Possible values: `main`, `guest`

### Module fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| id | id | ID of the module
| title | html | Title
| duration | integer | Duration of the module in seconds

### Chapter fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| id | id | ID of the chapter
| title | html | Title
| duration | integer | Duration of the chapter in seconds
| optional | boolean | Indication if the chapter is optional or mandatory for course completion
| content_type | string | Content type of the chapter. Possible values: `Video`, `Quiz`, `Challenge`, `Evaluation`, `Feedback`, `Slide`

## Completing a course Chapter for a Trainee
Bugle provides a subscription feature where an external service can notify that a Trainee
has completed a Chapter from an external application.

```shell
POST /courses/chaptes/complete
```

### Payload

```json
  {
    "payload_token": <strict_base64_token>
  }
```

### Fields description

|  Name  |  Type  |  Description  |
|--------|--------|---------------|
| payload_token | base64_string | Required. Base64 strict encoded string.

### Payload token information
The `payload_token` parameter must be a valid strict Base64 string, carrying the following information:

```json
  {
    "course_id": <course_id>,
    "trainee_id": <trainee_id>,
    "chapter_id": <chapter_id>
  }
```

### Response status codes
```
204 No Content | 403 Forbidden
```
