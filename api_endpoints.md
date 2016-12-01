
#Config

###Get task JSON schema

GET   http://kbhkilder.dk/1508/stable/api/taskschema&task_id=1

###Get searchable fields for collections

GET   http://kbhkilder.dk/1508/stable/api/searchconfig?collection_id=1

#Tasks
###Get tasks

GET   http://kbhkilder.dk/1508/stable/api/tasks


###Get task

GET   http://kbhkilder.dk/1508/stable/api/tasks/1

#Units

###Get units for task

GET   http://kbhkilder.dk/1508/stable/api/tasksunits?task_id=1&index_active=1

###Get unit

GET   http://kbhkilder.dk/1508/stable/api/units/1

#Pages
###Get pages

GET   http://kbhkilder.dk/1508/stable/api/pages?unit_id=1&page_number=12

###Get page

GET   http://kbhkilder.dk/1508/stable/api/pages/2

Returns an array of posts and "next_post" which is a best guess of the position and size of the next post (false when there is no more room for posts)

###Get next available page
GET   http://kbhkilder.dk/1508/stable/api/pages/nextavailable?task_id=1&unit_id=1&current_page_number=1

#Taskpages

###Update task page

PATCH   http://kbhkilder.dk/1508/stable/api/taskspages?task_id=1&page_id=23

```
{  
      "is_done":"1"
}
```

#Posts
###Get entry data for post
GET   http://kbhkilder.dk/1508/stable/api/posts/209

      Returns a post with data for all entries based on the post id

###Get post image
GET   http://kbhkilder.dk/1508/stable/api/posts/188/image

      Returns the image for the given post (in this example post with id 188)


#Entries

###Get entries

GET   http://kbhkilder.dk/1508/stable/api/entries?task_id=1&post_id=201

      Returns the entry for a given task and post (there can be only one entry pr. post and task)

###Get entry

GET   http://kbhkilder.dk/1508/stable/api/entries/6

###Add entry

POST  http://kbhkilder.dk/1508/stable/api/entries
```
{
    "task_id": 1,
    "page_id": 23,
    "post": {
        "x": 0.5,
        "y": 0.5,
        "height": 0.25,
        "width": 0.25
    },
    "persons": {
        "firstnames": "Jensine",
        "lastname": "Hansen",
        "age": 42,
        "civilstatus": "Gift",
        "dateOfDeath": "01-01-1905",
        "yearOfBirth": 1905,
    "deathcauses": [
        {
            "deathcause": "lungebtændelse"
        },
        {
            "deathcause": "hjertefejl"
        }
    ],
    "burials": {
        "chapel": "Alm. Hosp - Almindelig Hospital",
        "parish": "Helliggejst",
        "cemetary": "Mariebjerg"
    },
    "addresses": {}
  }
}
```

###Update entry

PUT   http://kbhkilder.dk/1508/stable/api/entries/76

```
{
    "task_id": 1,
    "page_id": 23,
    "post": {
        "x": 0.5,
        "y": 0.5,
        "height": 0.25,
        "width": 0.25
    },
    "persons": {
        "id": 231,
        "firstnames": "Jensine",
        "lastname": "Hansen",
        "age": 42,
        "civilstatus": "Gift",
        "dateOfDeath": "01-01-1905",
        "yearOfBirth": 1905,
    "deathcauses": [
        {
            "id": 231,
            "deathcause": "lungebtændelse"
        },
        {
            "deathcause": "hjertefejl"
        }
    ],
    "burials": {
        "chapel": "Alm. Hosp - Almindelig Hospital",
        "parish": "Helliggejst",
        "cemetary": "Mariebjerg"
    },
    "addresses": {}
  }
}
```

###Update entry (DEPRECATED)

PATCH   http://kbhkilder.dk/1508/stable/api/entries/76

```
{  
      "entity_name":"persons",
      "field_name" : "firstnames",
      "value":"Niels",
      "concrete_entries_id":178,
      "task_id":1
}
```

#Error reports
###Get error reports by task and post

GET   http://kbhkilder.dk/1508/stable/api/errorreports?task_id=1&post_id=201



###Get error reports by user and task

GET   http://kbhkilder.dk/1508/stable/api/errorreports?relevant_user_id=1&task_id=1

###Create error report

POST    http://kbhkilder.dk/1508/stable/api/errorreports
```
{
      "post_id": 1306,
      "entity_name": "deathcauses",
      "field_name": "deathcause",
      "concrete_entries_id": 1175,
      "comment": "",
      "value": "original_value"
}
```
###Edit error report

PATCH   http://kbhkilder.dk/1508/stable/api/errorreports/7
```
{
    "to_super_user": 1,
    "deleted": 0,
    "deleted_reason": ""
}
```

###Edit multiple error reports

PATCH   http://kbhkilder.dk/1508/stable/api/errorreports
```
[
{
    "id": 119,
    "to_super_user": 1,
    "deleted": 0,
    "deleted_reason": ""
},
{
    "id": 118,
    "to_super_user": 1,
    "deleted": 0,
    "deleted_reason": ""
}
]
```

#Users

###Get user

GET   http://kbhkilder.dk/1508/stable/api/users/621
Returns user info including informations about which tasks the user is superuser for

###Get active users by task and unit

GET   http://kbhkilder.dk/1508/stable/api/activeusers?task_id=1&unit_id=1

###Get user activities

GET   http://kbhkilder.dk/1508/stable/api/useractivities?user_id=607

#Search

Search

GET   http://kbhkilder.dk/1508/stable/api/search? + SOLR query

#Datasources

Datasources

GET   http://kbhkilder.dk/api/datasource/1?q=adelgade
