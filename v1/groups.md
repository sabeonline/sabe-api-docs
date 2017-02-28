# Groups

Trainees can be categorized in groups to make easier to distribute content to different people profiles. Via API only listing is available. To manage groups and trainees you need to do it through the [backoffice](https://backoffice.sabe-extend.com).

## Listing groups

```shell
GET /groups
```

Response

```json
  [
    {
      "id": 1234567,
      "name": "Sales"
    },
    {
      "id": 1234567,
      "name": "Administration"
    },
  ]
```
Groups are [searchable](/README.md#search) and [sortable](/README.md#sort) as described in main page.

* **Searchable fields**

|  field  |  type  |  description  |
|---------|--------|---------------|
| q | string | Free text. Searches in group name |
| status | string | Possible values: `inactive`, `active` and `archived` |

* **Sortable fields**
  * name (default)
  * id
